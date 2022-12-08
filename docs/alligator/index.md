# *Alligator API - Documentation*

* Developers
  * Developer
    * family-names: Thiery
    * given-names: Florian
    * orcid: https://orcid.org/0000-0002-3246-3531
    * affiliation: RGZM, Mainz, Germany
  * Developer
    * family-names: Mees
    * given-names: Allard W.
    * orcid: https://orcid.org/0000-0002-7634-5342
    * affiliation: RGZM, Mainz, Germany
* Software:
  * MIT License

## POST distance matrix

`POST alligator/rest/matrixdist/`

**Description**

returns a matrix of calculated 3D distances

**Requires authentication**

none

**Parameters**

* **body** *(mendatory)* — [File/AGT-TSV-String] *.agt file

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	[]
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

## POST distance matrix

`POST alligator/rest/matrixallen/`

**Description**

returns a matrix of allen relations

**Requires authentication**

none

**Parameters**

* **body** *(mendatory)* — [File/AGT-TSV-String] *.agt file

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
{
	[]
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

## POST graph

`POST alligator/rest/graph/`

**Description**

returns a JSON of edges and nodes

**Requires authentication**

none

**Parameters**

* **body** *(mendatory)* — [File/AGT-TSV-String] *.agt file

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONObject

**Response**

```json
{
	"edges": {
		"label": String,
		"from": String,
		"to": String
	}, {
		"label": String,
		"from": String,
		"to": String
	}
	"nodes": {
		"id": String,
		"label": String
	}, {
		"id": String,
		"label": String
	}
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

## POST timeline

`POST alligator/rest/timeline/`

**Description**

returns a JSON of time intervals

**Requires authentication**

none

**Parameters**

* **body** *(mendatory)* — [File/AGT-TSV-String] *.agt file

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSONArray

**Response**

```json
[
	{
		"content": String,
		"className": String,
		"id": String,
		"start": Integer,
		"end": Integer,
		"nn_start": String,
		"nn_end": String
	}
]
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

## POST turtle

`POST alligator/rest/turtle/`

**Description**

returns a RDF/Turtle representation

**Requires authentication**

none

**Parameters**

* **body** *(mendatory)* — [File/AGT-TSV-String] *.agt file

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

RDF/Turtle

**Response**

```sql
@prefix alligator: <http://rgzm.github.io/alligator/ontology#> .
@prefix ae: <http://example.net/event#> .
@prefix time: <http://www.w3.org/2006/time#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix dc: <http://purl.org/dc/elements/1.1/> .

ae:xm2bd7 a alligator:event .
ae:xm2bd7 a time:Interval .
ae:xm2bd7 dc:identifier "xm2bd7" .
ae:xm2bd7 rdfs:label "fruehkaiserzeitlich" .
ae:xm2bd7 alligator:estimatedstart "1.0" .
ae:xm2bd7 alligator:estimatedend "150.0" .
ae:xm2bd7 alligator:cax "-0.266" .
ae:xm2bd7 alligator:cay "0.253" .
ae:xm2bd7 alligator:caz "0.0072" .
ae:xm2bd7 alligator:startfixed "true" .
ae:xm2bd7 alligator:endfixed "true" .
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

## POST cypher

`POST alligator/rest/turtle/`

**Description**

returns a Cypher representation

**Requires authentication**

none

**Parameters**

* **body** *(mendatory)* — [File/AGT-TSV-String] *.agt file

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

CYPHER

**Response**

```sql
CREATE (R6N9Be:Event{label: 'fruehkaiserzeitlich'})
CREATE (xlePDg:Event{label: '2ndHalfFirstCentury'})
...
MERGE (R6N9Be)-[:EQUALS]->(R6N9Be)
MERGE (R6N9Be)-[:DURINGi]->(xlePDg)
...
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

## POST AMT rdf

`POST alligator/rest/turtle/`

**Description**

returns a Academic Meta Tool RDF/TTL representation

**Requires authentication**

none

**Parameters**

* **body** *(mendatory)* — [File/AGT-TSV-String] *.agt file

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

RDF/Turtle

**Response**

```sql
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix amt: <http://academic-meta-tool.xyz/vocab#> .
@prefix rgzm: <http://rgzm.de/datingmechanism#> .

rgzm:GAPkVX amt:instanceOf rgzm:Event .
rgzm:GAPkVX rdfs:label "fruehkaiserzeitlich" .
rgzm:MD4Ege amt:instanceOf rgzm:Event .
rgzm:MD4Ege rdfs:label "2ndHalfFirstCentury" .
...
_:MzPokYe3Pk rdf:subject rgzm:GAPkVX. 
_:MzPokYe3Pk rdf:object rgzm:MD4Ege. 
_:MzPokYe3Pk rdf:predicate rgzm:di. 
_:MzPokYe3Pk amt:weight "0.99". 
_:dPan165oD2 rdf:subject rgzm:GAPkVX. 
_:dPan165oD2 rdf:object rgzm:Y9O8PV. 
_:dPan165oD2 rdf:predicate rgzm:di. 
_:dPan165oD2 amt:weight "0.99".
...
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.