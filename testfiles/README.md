# Test files

The following tests are performed upon Push or Pull-Request. The first column depicts the name of the `.lvt` file. All tests are compared against `.tlg` files, except for `testßß3`, `testß04` and  `testß10` which are compared against `.vle` files. Most tests are tested with PDFTeX while some tests (involving Unicode) are performed using LuaTeX.

| Test file | Compared against | PDFTeX | LuaTeX | Tests performed |
| :---      | :---             | :---:  | :---:  | :---            |
| `test001` | `.tlg` | ✅ |    | Parsing of JSON strings, inline and from file; parsing of strings, numbers, null, booleans, arrays and objects |
| `test002` | `.tlg` |    | ✅ | Parsing of Unicode in JSON strings, inline and from file; parsing of Unicode (BMP and other planes) as key and value |
| `test003` | `.vle` | ✅ |    | Parsing of arrays: `\JSONParseArrayCount`, `\JSONParseArrayUse`, `\JSONParseArrayMapFunction` and `\JSONParseArrayMapInline` |
| `test004` | `.vle` | ✅ |    | Parsing of JSON escape sequences (except `\u`) |
| `test005` | `.tlg` | ✅ |    | Parsing of nested JSON strings via `\x`; indexing not zero-based |
| `test006` | `.tlg` | ✅ |    | Parsing of replacements for JSON escape sequences |
| `test007` | `.tlg` | ✅ | ✅ | Parsing of JSON escape sequences for Unicode (`\u`) including conversion of surrogate pairs |
| `test008` | `.tlg` | ✅ |    | Parsing of custom separators for arrays and children; parsing of custom replacements for boolean and null values |
| `test009` | `.tlg` | ✅ |    | Externalizing of parsed data |
| `test010` | `.vle` | ✅ |    | Use of `\JSONParseKeys` and `\JSONParseFilter` |
| `test011` | `.vle` | ✅ |    | Use of TeX escape sequences |
| `test100` | `.tlg` | ✅ |    | Validation of JSON numbers |
| `test200` | `.tlg` | ✅ |    | Checking for high and low surrogates; checking conversion of surrogate pairs |
