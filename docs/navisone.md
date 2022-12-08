# *ARS3D API - Documentation*

## GET status

` GET http://localhost:8084/ars3dapi/`

**Description**

returns metadata of the API and maven configs.

**Requires authentication**

none

**Parameters**

none

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSON Object

**Response**

```json
{
	"git": {},
	"database-connection": {},
	"maven": {},
	"project": {},
	"war": {}
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* https://java-dev.rgzm.de/ars3dapi

## GET features of an object

` GET http://localhost:8084/spi/features`

**Description**

returns all features, featuregroups and scenes of an object

**Requires authentication**

none

**Parameters**

* **q** *(required)* — [String] URI with prefix.
* **type** *(optional)* — [String] {feature;featuregroup;scene}.

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSON Object

**Response**

```json
{
	"features": [],
	"featuregroups": [],
	"scenes": []
}
```

```json
{
	"date": "2020-02-26T11:37:12.493+01:00",
	"process": "ars3dgp:1582713432493",
	"f": "ars3df:fbe04333-d501-4058-98f0-a990b9eba0ce",
	"observations": [],
	"processstate": "test",
	"typelabel": "Applique (positive)",
	"label": "asdsadasd",
	"type": "ars:FeatureType_Applique",
	"geom": "'{'selectionpolygon':[[-36.845232983550574,34.107175427304725,42.513339517633334],[4.0789305986819855,35.148786891432174,37.58398055446757],[-61.680198796342474,-9.841206777724546,49.94657957211528],[-2.9573409885244466,-14.347221598928389,32.756039423764086]],'crackpolygons':[],'edgepolygons':[],'overlappolygons':[],'kinkpolygons':[],'unnamed6polygons':[],'unnamed7polygons':[],'unnamed8polygons':[],'unnamed9polygons':[],'unnamed10polygons':[],'visualpolygon':[],'visualscenepolygon':[]}'"
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* all elements: https://java-dev.rgzm.de/ars3dapi/features?q=ars3do:57052b95-ca87-4d40-b59c-7c4128f78b23
* features: https://java-dev.rgzm.de/ars3dapi/features?q=ars3do:57052b95-ca87-4d40-b59c-7c4128f78b23&type=feature

## GET feature by ID

` GET http://localhost:8084/spi/features/{id}`

**Description**

returns a feature by its URI

**Requires authentication**

none

**Parameters**

* **id** *(required)* — [String] URI with prefix.

**Headers**

`Accept: application/json;charset=UTF-8`

`Accept-Encoding: *` `Accept-Encoding: gzip`

**Return format**

JSON Object

**Response**

```json
{
	"date": "2020-02-26T11:37:12.493+01:00",
	"process": "ars3dgp:1582713432493",
	"f": "ars3df:fbe04333-d501-4058-98f0-a990b9eba0ce",
	"observations": [],
	"processstate": "test",
	"typelabel": "Applique (positive)",
	"label": "asdsadasd",
	"type": "ars:FeatureType_Applique",
	"geom": "'{'selectionpolygon':[[-36.845232983550574,34.107175427304725,42.513339517633334],[4.0789305986819855,35.148786891432174,37.58398055446757],[-61.680198796342474,-9.841206777724546,49.94657957211528],[-2.9573409885244466,-14.347221598928389,32.756039423764086]],'crackpolygons':[],'edgepolygons':[],'overlappolygons':[],'kinkpolygons':[],'unnamed6polygons':[],'unnamed7polygons':[],'unnamed8polygons':[],'unnamed9polygons':[],'unnamed10polygons':[],'visualpolygon':[],'visualscenepolygon':[]}'"
}
```

**Response Codes**

* *200 OK* — ok.
* *500 Internal Server Error* — server error.

**Examples**

* https://java-dev.rgzm.de/ars3dapi/features/ars3df:fbe04333-d501-4058-98f0-a990b9eba0ce

> TODO /objects
