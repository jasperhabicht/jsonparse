# Test files

| Test file | Tests performed |
| :---      | :---            |
| `test001` | Parsing of JSON strings, inline and from file; parsing of strings, numbers, null, booleans, arrays and objects |
| `test002` | Parsing of Unicode in JSON strings, inline and from file; parsing of Unicode (basic and other planes) as key and value |
| `test003` | Parsing of arrays: `JSONParseArrayUse`, `\JSONParseArrayMapFunction` and `\JSONParseArrayMapInline` |
| `test004` | ~~Parsing of JSON escape sequences (except `\u`)~~ |
| `test005` | Parsing of nested JSON strings via `\x` |
| `test006` | Parsing of replacements for JSON escape sequences |
| `test007` | Parsing of JSON escape sequences for Unicode (`\u`) including conversion of surrogate pairs |
| `test008` | Parsing of custom separators for arrays and children; parsing of custom replacements for boolean and null values |
| `test100` | Validation of JSON numbers |
| `test200` | Checking for high and low surrogate |
