![Version 0.2.8](https://img.shields.io/badge/version-0.2.8-blue)

# The `jsonparse` package

The `jsonparse` package provides an easy way to read in JSON data from files or strings in LaTeX documents, parse the data and store it in a user-defined token variable. The package allows accessing the stored data via a JS-flavored syntax.

Using the commands `\JSONParseFromFile` or `\JSONParse`, JSON data can be stored in a token variable. Using the command `\JSONParseGetValue`, certain entried can be extracted from the stored data.

---

Let's assume a file with the name `example.json` is stored in the working directory with the following contents:

```
{
  "first_name": "John",
  "last_name": "Smith",
  "is_alive": true,
  "age": 27,
  "address": {
    "street_address": "21 2nd Street",
    "city": "New York",
    "state": "NY",
    "postal_code": "10021-3100"
  },
  "phone_numbers": [
    {
      "type": "home",
      "number": "212 555-1234"
    },
    {
      "type": "office",
      "number": "646 555-4567"
    }
  ],
  "children": [
    "Catherine",
    "Thomas",
    "Trevor"
  ],
  "spouse": null
}
```

We can store it in the token variable `\myJSONdata` using the command `\JSONParseFromFile{\myJSONdata}{example.json}`. Calling the command `\JSONParseGetValue{\myJSONdata}{phone_numbers[0].number}` would then result in the output `212 555-1234` (indices are zero-based per default). 

This package including all files is subject to the LPPL 1.3c license.
