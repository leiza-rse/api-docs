# *ARSPI - Documentation*

* Developers:
  * family-names: Thiery
  * given-names: Florian
  * orcid: https://orcid.org/0000-0002-3246-3531
  * affiliation: RGZM, Mainz, Germany
* Software:
  * MIT License

## GET list of objects

`GET arspi/rest/objects/`

**Description**

returns a list of objects that matches a substring

**Requires authentication**

none

**Parameters**

* **q** *(optional)* — [String] searchstring

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
	"label": String,
	"type": String,
	"thumbnail": String
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET object list
  * http://host/arspi/rest/objects
* GET objects including "erot" in the label
  * http://host/arspi/rest/objects?q=erot

## GET object by ID

`GET arspi/rest/objects/:id`

**Description**

returns a ARS3D object

**Requires authentication**

none

**Parameters**

* **id** *(mendatory)* — [String] ARS3D Object ID with PREFIX ars3do:
* **mode** *(mendatory)* — [String] {label}

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
	"label": String,
	"type": String,
	"date": String,
	"thumbnail": String,
	"period": String,
	"shape" : String,
	"arachne" : String,
	"arachneobj" : String,
	"condition_type" : String,
	"findspot" : String,
	"material" : String,
	"manufacturing_type" : String,
	"residence" : String
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET object 32f176e7-2baa-4801-87f6-bf62e37b1458
  * http://host/arspi/rest/objects/ars3do:32f176e7-2baa-4801-87f6-bf62e37b1458?mode=label