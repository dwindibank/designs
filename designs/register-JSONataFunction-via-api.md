---
state: draft
---

# Register and Remove JSONata functions via API

## Summary

Adding an API so that additional JSONata functions could be added would make good extension point. 

## Authors

 - @dustinw (node-red forum) / @dwindibank (github)

## Details

This section provides the detailed information for the proposal. This template
does not provide a structure for this section, but it should address:

 1. any public APIs it introduces
 2. the user experience of the feature - what it does and how it is used
 3. any migration concerns
 4. mock-up UI designs

 
### UI Changes ###
There should be no visible UI changs unless the registerJSONataFunction API method is called. In that case the new function should show up in the Snipts provided in the JSONata editor. 

editor-client/src/vendor/jsonata/formatter.js

### Documentation Impacts ### 

* New API methods will be documented so that API docs can be generated (e.g. @node-red_util.html https://nodered.org/docs/api/modules/v/0.20.0/@node-red_util.html)

#### Other ####

* The structre used in jsonata.functions (jsonata/formatter.js) is not clear and shold be documented somewhere. The structure used here this is different from the JSONata sig as per: http://docs.jsonata.org/embedding-extending#function-signature-syntax
* Add a cookbook example?

The discussion on the initial PR will provide guidance on what further material
is needed.

## Ref

- https://discourse.nodered.org/t/feature-request-register-jsonata-function/7381
- https://github.com/node-red/node-red/wiki/Design:-Node-module-lifecycle

## History

- 2019-03-07 - Initial draft
