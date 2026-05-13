# Protocol specification for connections

The Connections specification defines the Ditto Protocol topic structure and announcements for managed connections.

> **TL;DR**: Connection announcements use the topic pattern `_/connectionId/connections/announcements/subject`. Ditto publishes `opened` and `closed` announcements when a connection's state changes.

## Topic structure for Connections

A valid topic consists of these elements:

```
_/<connectionId>/connections/announcements/<subject>
```

1. `_`: empty namespace placeholder (connections have no namespace).
2. `connectionId`: the ID of the connection.
3. `group`: always `connections`.
4. `criterion`: `announcements`.
5. `subject`: the announcement name.

> **Note:** The topic path of the *connections* group does not contain a namespace since there is
no correlation between namespaces and connections. Also there is no channel unlike the *things* group.

## Announcements

A connection announcement contains the announcement name as the last segment of the topic:

```
_/<connectionId>/connections/announcements/<announcement-name>
```

The Ditto Protocol representation:

[JSON Schema: jsonschema/protocol-announcement.json](../jsonschema/protocol-announcement.json)

### ConnectionOpenedAnnouncement

Ditto publishes this announcement when a connection is being opened.

| Field | Value |
|---|---|
| **topic** | `_/<connectionId>/connections/announcements/opened` |
| **path** | `/` |
| **value** | JSON object with `openedAt` (ISO-8601 timestamp). |

**Example:** [Connection opened announcement](protocol-examples-connections-announcement-opened.html)

### ConnectionClosedAnnouncement

Ditto publishes this announcement when a connection is being closed gracefully.

| Field | Value |
|---|---|
| **topic** | `_/<connectionId>/connections/announcements/closed` |
| **path** | `/` |
| **value** | JSON object with `closedAt` (ISO-8601 timestamp). |

**Example:** [Connection closed announcement](protocol-examples-connections-announcement-closed.html)

## Further reading

- [Connections](basic-connections.html) -- connection concepts and configuration
- [Protocol specification](protocol-specification.html) -- the full message format reference
