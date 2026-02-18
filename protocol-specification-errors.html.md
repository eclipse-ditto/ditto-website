# Protocol specification for errors

Ditto Protocol messages of [error responses](basic-signals-errorresponse.html) transport information about encountered 
[errors](basic-errors.html), e.g. client errors or server errors:

[JSON Schema: jsonschema/protocol-error_response.json](../jsonschema/protocol-error_response.json)

The **error** codes Ditto provides in addition to the HTTP **status** code
(e.g. error codes like "things:thing.tooLarge") is not to be considered as API and must therefore not be relied on.  
It might change without prior notice.

## Examples

Examples for error responses can be found here:
* [Things error response examples](protocol-examples-errorresponses.html)
* [Policies error response examples](protocol-examples-policies-errorresponses.html)
