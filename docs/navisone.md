# *NoPI - Documentation*

## GET list of objects by search

`GET http://host/nopi/rest/searchobj/`

**Description**

returns a list of objects that matches keys or a substring

**Requires authentication**

none

**Parameters**

* **qs** *(optional)* — [String] searchstring.
* **q** *(optional)* — [String Comma Separated] {obj1,obj2,...}.
* **mode** *(optional)* — [String] {AND;OR}.

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	"thumbnail": {},
	"id": {},
	"label": {},
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET objects including "terra" in the label
  * http://host/nopi/rest/searchobj?qs=terra
* GET objects described with Shell first (4525) or Mortice-and-tennon (4514)
  * http://host/nopi/rest/searchobj?q=4525,4514&mode=OR
* GET objects described with Shell first (4525) and Mortice-and-tennon (4514)
  * http://host/nopi/rest/searchobj?q=4525,4514&mode=AND