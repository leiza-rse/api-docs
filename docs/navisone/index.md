# *NoPI - Documentation*

* Developers:
  * family-names: Thiery
  * given-names: Florian
  * orcid: https://orcid.org/0000-0002-3246-3531
  * affiliation: RGZM, Mainz, Germany
* Software:
  * MIT License

## GET list of objects by search

`GET navis/rest/searchobj/`

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
  * http://host/navis/rest/searchobj?qs=terra
* GET objects described with Shell first (4525) or Mortice-and-tennon (4514)
  * http://host/navis/rest/searchobj?q=4525,4514&mode=OR
* GET objects described with Shell first (4525) and Mortice-and-tennon (4514)
  * http://host/navis/rest/searchobj?q=4525,4514&mode=AND

## GET list of entities for a group of objects

`GET navis/rest/searchitems/`

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
  * http://host/navis/rest/searchitems?lut=lut_objecttype&list=200001,200002,200003,200004,200005

## GET object by ID

`GET navis/rest/objects/:id`

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
  * http://host/navis/rest/objects/200232

## GET key list for objects

`GET navis/rest/keysobjects`

**Description**

returns a list of keys used for objects

**Requires authentication**

none

**Parameters**

none

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	"id": String,
	"en": String,
	"de": String
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET key list for objects
  * http://host/navis/rest/keysobjects

## GET key list for freatures

`GET navis/rest/keysfeatures`

**Description**

returns a list of keys used for features

**Requires authentication**

none

**Parameters**

none

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	"id": String,
	"en": String,
	"de": String
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET key list for objects
  * http://host/navis/rest/keysfeatures