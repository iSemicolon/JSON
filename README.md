# JSON

JSON:

{ //OBJECT


“id”:1212,
“isActive”: true,
“balance”: “$12”;
“age”:24,
“name”:”palash”,
“gender”: “male”,
“email”: “@gma”

“address”: “kolkata”,

“tags” :[ “a”, “b”, “c”],

“friends”{

{
“id”:12,
“name”: “lee cooper”,
}

{
“id”:13,
“name”: “hask”,
}

“favourite”: “banana”
},



“id”:1313,
“isActive”: false,
“balance”: “$50”;
“age”:36,
“name”:”pah”,
“gender”: “female”,
“email”: “@gma”

“address”: “kolkata”,

“tags” :[ “a”, “b”, “c”],

“friends”{

{
“id”:12,
“name”: “lee cooper”,
}

{
“id”:13,
“name”: “hask”,
}

“favourite”: “banana”
},



//retriving data from json.


By using json path we can retrieve data from json ,

JSONPath is a query language for JSON, similar to Xpath for xml

path used using .or [] noation.

Dot notation:

$.store.book[0].title

or bracketnotation

$[‘store][‘book’][0][‘title’]

$ is optional or represents the root object ot array can be omitted

example: 
$.foo.bar and foo.bar are the same,
and so are $[0].status and [0].status


json path expressions ::

$-root object of array
.property-select the specify property from parent object
[‘property’]- selects the specified property in a parent object , be sure to put single quotes around the property name

[n]- slect the nth element from array. Index statt from zero

[index-1, insex-2...]- select array elements from specified indexex and returns a array list
..property:  recursive decents searches for the specified property name recursively and returns an array of all values with this property name always return a list, even if just one property found

* = select all properties from array

[start:end ]- select array elements from the start index and upto , but not including end index
[start:]- from start to end

[:n]- first n elements from array and returns alist
[-n:]- last n elements and returns a list
[?(expression)]: filter expression – it select all the elements from object or array which satisfies the condition and return an list
[(expresiion)]- for explicit property example: [(@length-1)]
@used in filter expressoion to refer current node being processed


//case -sensitive INCLUDING PROPERTY ANE AND VALUE 
//JSONPATH DOENT HAVE OPERATIONS FOR ACESSING CURRENT AND SIBLING NODES FROM GIVEN NODE



{ "store": {
    "book": [ 
      { "category": "reference",
        "author": "Nigel Rees",
        "title": "Sayings of the Century",
        "price": 8.95
      },
      { "category": "fiction",
        "author": "Evelyn Waugh",
        "title": "Sword of Honour",
        "price": 12.99
      },
      { "category": "fiction",
        "author": "Herman Melville",
        "title": "Moby Dick",
        "isbn": "0-553-21311-3",
        "price": 8.99
      },
      { "category": "fiction",
        "author": "J. R. R. Tolkien",
        "title": "The Lord of the Rings",
        "isbn": "0-395-19395-8",
        "price": 22.99
      }
    ],
    "bicycle": {
      "color": "red",
      "price": 19.95
    }
  }
}




1. FIND ALL STORE ELEMENTS
$.store.bicycle.color
2.bicycle color value

$.store.bicycle.color

3.prices of all books
$.store..price

4. titles of books
$.store..title
$..title

5.data of all books
$.store.book[*]

6. data of 2nd book
$.store.book[1]

7.only first two books
$.store.book[0:2]

8. 2nd and 3rd book
$.store.book[1,2]

9.2nd and 3rd books author
$.store.book[1,2].author

10.last two records
$.store.book[-2:0]

11.books having isbn properties
$..book[?(@.isbn)]

12.don’t have isbn properties
$..book[?(!@.isbn)]

13. book price is less than <10
$..book[?(@.price<10)]

14. pathfind website

https://jsonpathfinder.com/

15. json query validation
https://jsonpath.com/







