# Standard-Json-Response
This document identify how a standard Json API response should be.
 please feel free to contribute !


##### Full structure of response :
```
{
	"data": {...},
	"errors": {...},
	"meta": {...}
}
```

##### Resource Objects:
```
   {
 	"type": "articles",
 	"id": "1",
 	"attributes": {
 		"title": "Rails is Omakase",
 		"price": 25000
 	},
 	"relationships": {
 		"author": {
 			"links": {
 				"self": "/articles/1/relationships/author",
 				"related": "/articles/1/author"
 			},
 			"data": {
 				"type": "people",
 				"id": "9"
 			},
 			"meta": {}
 		}
 	},
 	"Links": {
 		"self": "http://example.com/posts",
 		"related": {
 			"href": "http://example.com/articles/1/comments",
 			"meta": {
 				"count": 10
 			}
 		}


 	},
 	"meta": {
 		"copyright": "Copyright 2015 Example Corp.",
 		"authors": [
 			"Yehuda Katz",
 			"Steve Klabnik",
 			"Dan Gebhardt",
 			"Tyler Kellen"
 		]
 	}
 }
```

#### Error Object :  

```text
{
	"errors": [{
		"id": 1,
		"links": {
			"about": "http://thisis.com/link/about/the/problem"
		},
		"status": 400,
		"code": "application code here",
		"title": "title of error",
		"details": "",
		"source": {
			"pointer": "requested uri",
			"parameter": "uri query strings"
		},
		"meta": {}
	}]
}
```

##### Relationships Object:
```text
"relationships": {
    "author": {
        "links": {
            "self": "/articles/1/relationships/author",
            "related": "/articles/1/author"
        },
        "data": {
            "type": "people",
            "id": "9"
        },
        "meta": {}
    }
}
```

#### Links Object :
```text
"Links": {
    "self": "http://example.com/posts",
    "related": {
        "href": "http://example.com/articles/1/comments",
        "meta": {
            "count": 10
        }
    }


}
```

#### Meta Object :
```text
"meta": {
    "copyright": "Copyright 2015 Example Corp.",
    "authors": [
        "Yehuda Katz",
        "Steve Klabnik",
        "Dan Gebhardt",
        "Tyler Kellen"
    ]
}
```
#### useful links 
```
https://byrondover.github.io/post/restful-api-guidelines/
https://medium.com/@shazow/how-i-design-json-api-responses-71900f00f2db
https://phalt.co/api-response-formats/
http://editor.swagger.io/#/

```
