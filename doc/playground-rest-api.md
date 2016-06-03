# Playground REST API

Version: 0.1.0

## Overview

|Description|Request|Response|
|---|---|---|
|Get all plays|GET /plays HTTP/1.0|HTTP/1.0 200 OK|
|Get a play|GET /plays/1 HTTP/1.0|HTTP/1.0 200 OK|
|Save a new play|POST /plays HTTP/1.0|HTTP/1.0 201 Created|
|Update existing play|PUT /plays/1 HTTP/1.0|HTTP/1.0 200 OK|
|Delete existing play|DELETE /plays/1 HTTP/1.0|HTTP/1.0 200 OK|

## Details

### Get all plays

Request:

```
GET /plays HTTP/1.0
```

Response:
```
HTTP/1.0 200 OK
Content-Type: application/json

[
	{
		"id": 1,
		"name": "Play A"
	},
	{
		"id": 2,
		"name": "Play B"
	},
	{
		"id": 3,
		"name": "Play C"
	}
]
```

### Get a play

Request:

```
GET /plays/1 HTTP/1.0
```

Response:
```
HTTP/1.0 200 OK
Content-Type: application/json

{
	"id": 1,
	"name": "Play A",
	"html": "<p>Hello world!</p>",
	"css": "p { color: red }",
	"js": "document.querySelector('p').onclick = function() { alert('Hello world!') };"
}
```

### Saving a new play

Request:

```
POST /plays HTTP/1.0
Content-Type: application/json

{
	"name": "Play D",
	"html": "<p>Hello buddy!</p>",
	"css": "p { color: blue }",
	"js": "document.querySelector('p').onclick = function() { alert('Hello buddy!') };"
}
```

Response:
```
HTTP/1.0 201 Created
Location: /plays/4
```

### Update existing play

Request:
```
PUT /plays/1 HTTP/1.0
Content-Type: application/json

{
	"name": "Play X",
	"html": "<p>Hello X!</p>",
	"css": "p { color: green }",
	"js": "document.querySelector('p').onclick = function() { alert('Hello X!') };"
}
```

Response:
```
HTTP/1.0 200 OK
```


### Delete existing play

Request:
```
DELETE /plays/1 HTTP/1.0
```

Response:
```
HTTP/1.0 200 OK
```