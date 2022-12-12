# *ARS3D API - Documentation*

* Developers:
  * family-names: Thiery
  * given-names: Florian
  * orcid: https://orcid.org/0000-0002-3246-3531
  * affiliation: RGZM, Mainz, Germany
* Software:
  * MIT License

## GET list of objects

`GET ars3d/rest/objects/`

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
  * http://host/ars3d/rest/objects
* GET objects including "erot" in the label
  * http://host/ars3d/rest/objects?q=erot

## GET object by ID

`GET ars3d/rest/objects/:id`

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
  * http://host/ars3d/rest/objects/ars3do:32f176e7-2baa-4801-87f6-bf62e37b1458?mode=label

## GET list of features

`GET ars3d/rest/features/`

**Description**

returns a list of features that belongs to an object

**Requires authentication**

none

**Parameters**

* **q** *(optional)* — [String] ARS3D Object ID with PREFIX ars3do:

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	"features": [
		"f": String,
		"label": String,
		"typelabel": String,
		"manufacturinglabel": String,
		"date": String,
		"geom": String,
		"observations": []
	],
	"featuregroups": [],
	"interpretations": []
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET feature list of object 32f176e7-2baa-4801-87f6-bf62e37b1458
  * http://host/ars3d/rest/features?q=ars3do:32f176e7-2baa-4801-87f6-bf62e37b1458

## GET feature by ID

`GET ars3d/rest/features/:id`

**Description**

returns a ARS3D feature

**Requires authentication**

none

**Parameters**

* **id** *(mendatory)* — [String] ARS3D Feature ID with PREFIX ars3df:

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	"f": String,
	"label": String,
	"typelabel": String,
	"manufacturinglabel": String,
	"date": String,
	"geom": String,
	"observations": []
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET feature 41d92517-5e73-4847-aca2-b70cf3d86d54
  * http://host/ars3d/rest/features/ars3df:41d92517-5e73-4847-aca2-b70cf3d86d54

## GET fixed values

`GET ars3d/rest/fixedvalues/:id`

**Description**

returns value list for a domain

**Requires authentication**

none

**Parameters**

* **id** *(mendatory)* — [String] {observationclasses;conditions;residences;findspots;manufacturingfeaturetypes;shapes;featuretypes;periods;materials;activities;objecttypes;conditiontypes;manufacturingobjecttypes}

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	"id: String,
	"label": String
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET shapes
  * http://host/ars3d/rest/fixedvalues/shapes
* GET materials
  * http://host/ars3d/rest/fixedvalues/materials