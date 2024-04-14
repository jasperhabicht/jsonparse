![Version 0.5.7](https://img.shields.io/badge/version-0.5.7-blue)

# The `jsonparse` package

The `jsonparse` package provides an easy way to read in JSON data from files or strings in LaTeX documents, parse the data and store it in a user-defined token variable. The package allows accessing the stored data via a JavaScript-flavored syntax.

Using the commands `\JSONParseFromFile` or `\JSONParse`, JSON data can be stored in a token variable. Using the command `\JSONParseGetValue`, certain entried can be extracted from the stored data.

---

Let's assume a file with the name `example.json` is stored in the working directory with the following contents:

```
{
  "givenName": "Joe",
  "familyName": "Public",
  "points": 1.7,
  "hasCertification": true,
  "address": {
    "streetAddress": "10 Main St",
    "locality": "Cityville",
    "postalCode": "12345"
  },
  "contactPoint": [
    {
      "contactType": "office",
      "telephone": "+1 (555) 555-1234"
    },
    {
      "contactType": "mobile",
      "telephone": "+1 (555) 555-6789"
    }
  ],
  "children": [
    "Tom,
    "Doug",
    "Harry"
  ],
  "memberOf": null
}
```

We can store it in the token variable `\myJSONdata` using the command `\JSONParseFromFile{\myJSONdata}{example.json}`. Calling the command `\JSONParseGetValue{\myJSONdata}{contactPoint[0].telephone}` would then result in the output `+1 (555) 555-1234` (indices are zero-based per default). 

This package including all files is subject to the LPPL 1.3c license.
