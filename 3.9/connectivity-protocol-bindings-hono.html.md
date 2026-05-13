# Eclipse Hono binding

You use the Eclipse Hono binding to integrate Ditto with Eclipse Hono without manually configuring Kafka topics, header mappings, or SASL settings.

> **TL;DR**: Configure a Hono connection with `connectionType: \

## Overview

The Hono connection type is a convenience wrapper around the
[Kafka connection](connectivity-protocol-bindings-kafka2.html). It automatically applies the
correct header mappings, address formats, and Kafka `specificConfig` settings required to
communicate with Eclipse Hono.

Most of the [Kafka connection documentation](connectivity-protocol-bindings-kafka2.html) applies,
with the exceptions described below.

> **Note:** A Hono connection is associated with _one_ Hono tenant. Create a separate connection for
            each tenant. The tenant ID is configured via `specificConfig.honoTenantId`.

## Connection URI format

You do **not** specify the `uri` in a Hono connection -- it is generated automatically from the
connectivity service configuration:

* `ditto.connectivity.hono.base-uri` -- protocol, host, and port
* `ditto.connectivity.hono.username` -- Kafka username
* `ditto.connectivity.hono.password` -- Kafka password

The resulting URI follows the format `tcp://username:password@host:port`.

You must restart the service after changing these properties.

## Source configuration

### Source addresses

Source `addresses` use aliases that resolve to Kafka topics at runtime:

| Alias | Resolved Kafka topic |
|-------|---------------------|
| `event` | `hono.event.<honoTenantId>` |
| `telemetry` | `hono.telemetry.<honoTenantId>` |
| `command_response` | `hono.command_response.<honoTenantId>` |

If `specificConfig.honoTenantId` is not set, the connection ID is used instead.

### Source reply target

The reply target `address` alias `command` resolves to:

* `hono.command.<honoTenantId>/<thingId>`

Header mappings for the reply target are auto-generated. For `telemetry` and `event` sources:

* `device_id`: `{{ thing:id }}`
* `subject`: `{{ header:subject | fn:default(topic:action-subject) | fn:default(topic:criterion) }}-response`
* `correlation-id`: `{{ header:correlation-id }}`

For `command_response` sources:

* `correlation-id`: `{{ header:correlation-id }}`
* `status`: `{{ header:status }}`

Any additional manually defined header mappings are merged with the auto-generated ones.

```json
{
  "addresses": ["event"],
  "consumerCount": 1,
  "qos": 1,
  "authorizationContext": ["ditto:inbound-auth-subject"],
  "enforcement": {
    "input": "{{ header:device_id }}",
    "filters": ["{{ entity:id }}"]
  },
  "headerMapping": {},
  "payloadMapping": ["Ditto"],
  "replyTarget": {
    "enabled": true,
    "address": "command",
    "expectedResponseTypes": ["response", "error", "nack"]
  },
  "acknowledgementRequests": {
    "includes": []
  },
  "declaredAcks": []
}
```

### Source header mapping

No source header mappings are required for Hono connections. The header mappings documented for
[Kafka connections](connectivity-protocol-bindings-kafka2.html#source-header-mapping) are still
available if needed.

## Target configuration

### Target address

The only valid target `address` alias is `command`, which resolves to:

* `hono.command.<honoTenantId>/<thingId>`

### Target header mapping

Target header mappings are auto-generated:

* `device_id`: `{{ thing:id }}`
* `subject`: `{{ header:subject | fn:default(topic:action-subject) }}`
* `response-required`: `{{ header:response-required }}`
* `correlation-id`: `{{ header:correlation-id }}`

Additional manually defined mappings are merged with the auto-generated ones.

```json
{
  "address": "command",
  "topics": [
    "_/_/things/twin/events",
    "_/_/things/live/messages"
  ],
  "authorizationContext": ["ditto:outbound-auth-subject"]
}
```

## Specific configuration options

| Property | Description | Default |
|----------|-------------|---------|
| `honoTenantId` | Hono tenant ID for this connection | connection ID |
| `groupId` | Kafka consumer group ID | connection ID |
| `debugEnabled` | Include debug information in acknowledgements | `false` |

The following properties are set automatically from the connectivity service configuration and
cannot be overridden:

* `bootstrapServers` -- from `ditto.connectivity.hono.bootstrap-servers`
* `saslMechanism` -- from `ditto.connectivity.hono.sasl-mechanism`

The `validateCertificates` connection property is also set automatically from
`ditto.connectivity.hono.validate-certificates`.

## Example connection JSON

```json
{
  "id": "connection-for-hono-example-tenant",
  "connectionType": "hono",
  "connectionStatus": "open",
  "failoverEnabled": true,
  "specificConfig": {
    "honoTenantId": "example-tenant"
  },
  "sources": [{
    "addresses": ["event"],
    "consumerCount": 1,
    "qos": 1,
    "authorizationContext": ["ditto:inbound-auth-subject"],
    "enforcement": {
      "input": "{{ header:device_id }}",
      "filters": ["{{ entity:id }}"]
    },
    "headerMapping": {},
    "payloadMapping": ["Ditto"],
    "replyTarget": {
      "enabled": true,
      "address": "command",
      "expectedResponseTypes": ["response", "error", "nack"]
    },
    "acknowledgementRequests": {
      "includes": []
    },
    "declaredAcks": []
  }],
  "targets": [{
    "address": "command",
    "topics": [
      "_/_/things/twin/events",
      "_/_/things/live/messages"
    ],
    "authorizationContext": ["ditto:outbound-auth-subject"]
  }]
}
```

### Connectivity service configuration example

```
ditto {
  connection {
    hono {
      base-uri = "tcp://localhost:9092"
      username = "honoUsername"
      password = "honoPassword"
      sasl-mechanism = "PLAIN"
      bootstrap-servers = "localhost:9092"
      validateCertificates = true
      ca = "-----BEGIN CERTIFICATE-----\n<trusted certificate>\n-----END CERTIFICATE-----"
    }
  }
}
```

## Troubleshooting

Use the `retrieveHonoConnection` piggyback command to inspect the fully resolved Hono connection
with all auto-generated properties. This is useful for debugging but the output cannot be used
directly to create a new connection.

## Further reading

* [Kafka 2.x binding](connectivity-protocol-bindings-kafka2.html) -- underlying Kafka connection details
* [Connections overview](basic-connections.html) -- connection model and configuration
* [Payload mapping](connectivity-mapping.html) -- transform message payloads
