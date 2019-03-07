---
state: draft
---

# Register and Remove JSONata functions via API

## Summary

Adding API methods so that additional JSONata functions could be added. 

## Authors

 - @dustinw (node-red forum) / @dwindibank (github)

## Details

* `RED.util.registerJSONataFunction (name, function, signature="", snipt="")`
* `RED.util.removeJSONataFunction (name)`
* `RED.util.getJSONataFunctions()`  returns array of objects that have the functions and the meta-data for the functions for use in JSONata expressions

prepareJSONataExpression would have to be updated to call getJSONataFunctions (or maybe a helper function). Ideally the expr.assign and expr.registerFunction function calls in prepareJSONataExpression would be removed and registerJSONataFunction would be called for flowContext, globalContext, env & clone

 
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
