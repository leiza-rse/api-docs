# *NoPI - Documentation*

## GET list of objects by search

`GET nopi/rest/searchobj/`

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
	"id": String,
	"label": String,
	"thumbnail": String
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

## GET list of entities for a group of objects

`GET nopi/rest/searchitems/`

**Description**

returns a list of entities in a look-up-table that matches to a list ob object IDs

**Requires authentication**

none

**Parameters**

* **lut** *(optional)* — [String] {lut_objecttype;lut_material;lut_technique;lut_culture;lut_person;lut_depository}.
* **list** *(optional)* — [String Comma Separated] {obj1,obj2,...}.

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	"id": String,
	"count": String,
	"label_en": String,
	"label_de": String
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET object types from objects 200001-200005
  * http://host/nopi/rest/searchitems?lut=lut_objecttype&list=200001,200002,200003,200004,200005

## GET object by ID

`GET nopi/rest/objects/:id`

**Description**

returns a NAVIS object

**Requires authentication**

none

**Parameters**

* **id** *(mendatory)* — [String] Object ID.

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	"id": String,
	"uri": String,
	"name": String,
	"features_count": Integer,
	"hastype": Integer,
	"metadata" : {},
	"image_primary" : {},
	"images" : {},
	"features" : {},
	"datings" : {},
	"keywords" : {},
	"keys_list" : {},
	"keywords_list" : {},
	"images" : {},
	"literature" : {}
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET object 200232
  * http://host/nopi/rest/objects/200232