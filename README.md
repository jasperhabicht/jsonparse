![Version 1.6.0](https://img.shields.io/badge/version-1.6.0-blue)

![Jason, the JSON parsing horse](https://github.com/jasperhabicht/jsonparse/assets/6378801/ddfddc70-bf5f-4121-ba45-4b9128875d85)

# The `jsonparse` package

The `jsonparse` package provides a handy way to read in JSON data from files 
or strings in LaTeX documents, parse the data and store it in a user-defined 
token variable. The package allows accessing the stored data via a 
JavaScript-flavored syntax.

Using the commands `\JSONParseFromFile` or `\JSONParse`, JSON data can be 
stored in a token variable. Using the command `\JSONParseValue`, entries can 
be extracted from the stored data.

---

Let's assume a file with the name `example.json` is stored in the working 
directory with the following contents:

```json
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
    "Tom",
    "Doug",
    "Harry"
  ],
  "memberOf": null
}
```

We can store it in the token variable `\myJSONdata` using the command 
`\JSONParseFromFile{\myJSONdata}{example.json}`. Calling the command 
`\JSONParseValue{\myJSONdata}{contactPoint[0].telephone}` would then result in 
the output `+1 (555) 555-1234` (indices are zero-based per default). The 
package allows for parsing JSON data inline as well.

The package also offers several commands for looping through arrays and 
accessing individual elements, for example to typeset them in tabular form or 
to plot their values using packages such as PGFPlots.

Adding commas between the items of the children array can be done with:
```tex
\JSONParseArrayUse{\myJSONdata}{children}{, }
```

A tabular listing the contact points of above JSON file can be created with:
```tex
\begin{tabular}{cc}
\textbf{Contact Type} & \textbf{Telephone} \\
\JSONParseArrayMapInline{\myJSONdata}{contactPoint}{%
  \JSONParseValue{\myJSONdata}{contactPoint[#1].contactType} & 
  \JSONParseValue{\myJSONdata}{contactPoint[#1].telephone} \\
}
\end{tabular}
```

The package also provides a few helper commands such as to validate a JSON 
number or to convert Unicode surrogate pairs to the relevant Unicode codepoint.

---

This package including all files is subject to the LPPL 1.3c license. 
Copyright 2024&ndash;2025 Jasper Habicht (mail(at)jasperhabicht.de).

Jason, the JSON parsing horse: Copyright 2024&ndash;2025 Hannah Klöber.
