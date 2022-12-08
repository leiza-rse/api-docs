# *re3dragon API - Documentation*

* Developers:
  * family-names: Thiery
  * given-names: Florian
  * orcid: https://orcid.org/0000-0002-3246-3531
  * affiliation: RGZM, Mainz, Germany
* Software:
  * MIT License

## GET remote item

`GET re3dragon/rest/item/`

**Description**

returns a resolved remote item as JSKOS

**Requires authentication**

none

**Parameters**

* **uri** *(mendatory)* — [String] URI

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	"uri": String,
	"displayLabel.en": String,
	"displayDesc.en": String,
	"prefLabel": {},
	"scopeNote": {},
	"broader": [],
	"narrower": [],
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET Getty AAT Concept 300262907
  * http://host/arspi/rest/item?uri=http://vocab.getty.edu/aat/300262907

## GET remote item by search

`GET re3dragon/rest/search/`

**Description**

returns resolved remote items as JSKOS

**Requires authentication**

none

**Parameters**

* **q** *(mendatory)* — [String] Search String
* **repo** *(mendatory)* — [String] {gettyaat;wikidata;iconclass}

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	"uri": String,
	"displayLabel.en": String,
	"displayDesc.en": String,
	"prefLabel": {},
	"scopeNote": {},
	"broader": [],
	"narrower": [],
	"similarity": {}
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET items from Getty AAT related to religion
  * http://host/arspi/rest/search?q=religion&repo=gettyaat

## GET remote item by ids

`GET re3dragon/rest/items/`

**Description**

returns resolved remote items as JSKOS

**Requires authentication**

none

**Parameters**

* **ids** *(mendatory)* — [String Comma Separated] {obj1,obj2,...}

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	[
		"uri": String,
		"displayLabel.en": String,
		"displayDesc.en": String,
		"prefLabel": {},
		"scopeNote": {},
		"broader": [],
		"narrower": []
	], []
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET items from Getty AAT by IDs 300262907 and 300178739
  * http://host/arspi/rest/items?ids=http://vocab.getty.edu/aat/300262907,http://vocab.getty.edu/aat/300178739

## GET draon lairs

`GET re3dragon/rest/lairs/`

**Description**

returns dragon lairs

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
	[
		"id": String,
		"type": String,
		"scheme": String,
		"legaltype": String,
		"wikidata": String,
		"quality": String,
		"group": String
	], []
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* GET dragon lairs
  * http://host/arspi/rest/lairs