CsvStreamingParser
==================

Streaming parser of CSV in JavaScript. Initially written for [Fintracker](https://github.com/paul-lysak/fintracker).
The goal was to make a parser which accepts chunks of file and as enough information is collected produces JavaScript objects.
Thus you don't need to keep the whole file in memory.
Doesn't have external dependencies, only needs AMD loader (Dojo, RequireJS, CurlJS etc.) in order to plug into the program.

If you need more info about the library please feel free to contact me.

##Usage

Included into some script as AMD module, check your modules loader documentation for details. Once you've got module object you can use the parser:

  var p = new CsvStreamingParser(); //create parser - once for parsed file
  var objects = p.parse( ...string with first piece of file...); //get objects for first piece of CSV file
  ..process objects
  objects = p.parse(...second piece...); //geet objects for second piece
  ...process objects
  ...parse other pieces
  var lastObject = p.end(); //get last object
  ..process last object

First row of CSV file is considered as object value keys. So for example such file:

  field1, field2, field3
  "val1", 123, true
  "val2", 234, false

would produce two objects: {field1: "val1", field2: 123, field3: true} and {field1: "val2", field2: 234, field3: false}

Resulting objects are not produced until parser has a complete row. If current piece has unterminated row then it is automatically prepended
to next piece and included into next piece result. So each separate call to p.parse() or p.end() may produce no objects or produce more objects tham
contained into its piece.  

p.parse() returns an array. If no objects available it returns empty array.

p.end() returns an object. If no object available it returns null 

##License

Licensed under Apache 2.0 license: 
http://www.apache.org/licenses/LICENSE-2.0.txt
