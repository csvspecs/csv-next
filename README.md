# Better Comma-Separated Values (CSV) Format Notes


## Why?

Let's make the comma-separated values (CSV) format better.
Why? Because it's great and it can be greater!


## What's great about CSV?

- Simple
- Plain text

~~~
barcelona, Barcelona|FC Barcelona|F.C. Barcelona|Fútbol Club Barcelona,    BAR,     city:barcelona
madrid,    R. Madrid|Real Madrid|Real Madrid CF|Real Madrid Club de Fútbol,  RMD,       city:madrid
~~~

## What's missing?

- No comments
- No blank lines
- No multi-line records
- No data types (or text patterns or field tags / markers e.g. km2 or % or ° or similar)
- No unordered fields (that is, fields depend on position) or variable number of fields per record
- No groups


## Extras

- [Comments](COMMENTS.md)
- [Magic](MAGIC.md)
    - [Types](TYPES.md)
        - [Names](NAMES.md)    -- Brussel • Bruxelles   [de]
        - [Numbers](NUMBERS.md)  -- 12.3m, 13.4k
        - [Units](UNITS.md)  -- km2, hl, %, etc.
        - [Properties n Attributes](PROPS.md)  -- city:barcelona, wikipedia:Barcelona
        - [Keys](KEYS.md)  -- first field
        - [Tags](TAGS.md)  -- last field
    - [Files n Folders](FILES.md)
    - [Groups n Headers](GROUPS.md)

-- add page/entry for multi line style  -- e.g. use MULTI.md? or RECORDS.md?
-- add spaces, commas n quotes page (incl. escape, tab rules ..) ??  -- e.g. SPACE.md ?
-- add COMMENTS_ALT.md  -- e.g. move alternative (not-supported) styles/ideas



### Comments

Example:

~~~
#################################################
# Primera División de España - La Liga 2013/14

barcelona, Barcelona|FC Barcelona|F.C. Barcelona|Fútbol Club Barcelona,    BAR,     city:barcelona
...
~~~

#### End-of-Line Comments



### Blank Lines

Example:

~~~
barcelona, Barcelona|FC Barcelona|F.C. Barcelona|Fútbol Club Barcelona,    BAR,     city:barcelona
espanyol,  Espanyol|RCD Espanyol|R.C.D. Espanyol|Espanyol Barcelona|Real CD Espanyol|Real Club Deportivo Espanyol|Real Club Deportivo Español,  ESP, city:barcelona

madrid,    R. Madrid|Real Madrid|Real Madrid CF|Real Madrid Club de Fútbol,  RMD,       city:madrid
atletico,  Atlético|Atlético Madrid|Club Atlético de Madrid,   ATL,              city:madrid
...
~~~

### Multi-line Records


Ideas

Option 1:  2nd (3rd and so on) lines starting with three dots e.g.  ... followed by at least one non-space character

Option 2:  2nd line starting with three spaces followed by at least one non-space character


### Unordered Fields



Others?


## Alternative (Plain Text) Formats

- XML (Extensible Markup Language)
- JSON (JavaScript Object Notation)
- YAML (YAML Ain't Markup Language - formerly Yet Another Markup Language)
- PROPS (key value pairs)
- INI   (key value pairs plus sections)
- TOML  (key value pairs plus sections plus data types, that is, arrays, bools, dates, etc.)
- SEXPS (S-Expressions, that is, symbolic expressions - Lisp-style)
- RDF Triplets (Resource Description Framework)
- HTML Microformat




### XML

- Supports Comments    - Yes
- Supports Blank Lines - Yes
- Supports Unordered Fields - Yes
- Supports Multi-line Records - Yes
- Supports Data Types  - No (Everything is a String/Text)


Cons:

- Verbose (compared to CSV, that is, requires header for every record and field)


### JSON

- Supports Comments    - ???
- Supports Blank Lines - Yes
- Supports Unordered Fields - Yes
- Supports Multi-line Records - Yes

Cons:

- Verbose (requires quoted strings, requires array or hash envelope)
- Programming language-oriented (e.g. uses {},[], etc.)


More JSON Formats:

#### JSON Lines

web: [jsonlines.org](http://jsonlines.org)

One Line, One Record - Newline (nl or \n) Separated

```
["Name", "Session", "Score", "Completed"]
["Gilbert", "2013", 24, true]
["Alexa", "2013", 29, true]
["May", "2012B", 14, false]
["Deloise", "2012A", 19, true] 
```

Pros:

- Supports JSON Datatypes (Numbers, Bool, Null, etc.)


or nested data records e.g.

```
{"name": "Gilbert", "wins": [["straight", "7♣"], ["one pair", "10♥"]]}
{"name": "Alexa", "wins": [["two pair", "4♠"], ["two pair", "9♠"]]}
{"name": "May", "wins": []}
{"name": "Deloise", "wins": [["three of a kind", "5♣"]]}
```


#### NDJSON - Newline Delmited JSON

web: [ndjson.org](http://ndjson.org), 
github: [ndjson](https://github.com/ndjson)


1. Line Separator is '\n' 
2. Each Line is a valid JSON Value

```
{"some":"thing"}
{"foo":17,"bar":false,"quux":true}
{"may":{"include":"nested","objects":["and","arrays"]}}
```

(Source: [specs.okfnlabs.org/ndjson](http://specs.okfnlabs.org/ndjson))



#### JSON5 - Modern JSON - JSON for the ES5 Era

web: [json5.org](http://json5.org),
github: [json5](https://github.com/json5)

JSON for "Humans" (not Machines). Adds:

- Comments- Allow both inline (single-line) and block (multi-line) comments are allowed (like ES5)
- Keys can be unquoted if they're valid identifiers e.g. a-z0-9 (like ES5)
- Single and double quoted strings (like ES5)
- Allows multi-line string with backslash (like ES5)
- Allow trailing commas for arrays and objects.
- And some more.

```
// This file is written in JSON5 syntax, naturally, but npm needs a regular
// JSON file, so compile via `npm run build`. Be sure to keep both in sync!

{
    name: 'json5',
    version: '0.5.0',
    description: 'JSON for the ES5 era.',
    keywords: ['json', 'es5'],
    author: 'Aseem Kishore <aseem.kishore@gmail.com>',
    contributors: [
        // TODO: Should we remove this section in favor of GitHub's list?
        // https://github.com/json5/json5/contributors
        'Max Nanasy <max.nanasy@gmail.com>',
        'Andrew Eisenberg <andrew@eisenberg.as>',
        'Jordan Tucker <jordanbtucker@gmail.com>',
    ],
    main: 'lib/json5.js',
    bin: 'lib/cli.js',
    files: ["lib/"],
    dependencies: {},
    devDependencies: {
        gulp: "^3.9.1",
        'gulp-jshint': "^2.0.0",
        jshint: "^2.9.1",
        'jshint-stylish': "^2.1.0",
        mocha: "^2.4.5"
    },
    scripts: {
        build: 'node ./lib/cli.js -c package.json5',
        test: 'mocha --ui exports --reporter spec',
            // TODO: Would it be better to define these in a mocha.opts file?
    },
    homepage: 'http://json5.org/',
    license: 'MIT',
    repository: {
        type: 'git',
        url: 'https://github.com/json5/json5',
    },
}
```

#### HJSON - A "Human" User Interface for JSON

web: [hjson.org](http://hjson.org),
github: [hjson](https://github.com/hjson)

- Commas Optional
- Add comments, hash-style (#), line-style (//) and block-style (/* */)
- Allow Keys without quotes
- Allow Strings without quotes
- Allow Multi-line strings Python-style e.g. ''' text '''

```
{
  // use #, // or /**/ comments,
  // omit quotes for keys
  key: 1
  // omit quotes for strings
  contains: everything on this line
  // omit commas at the end of a line
  cool: {
    foo: 1
    bar: 2
  }
  // allow trailing commas
  list: [
    1,
    2,
  ]
  // and use multiline strings
  realist:
    '''
    My half empty glass,
    I will fill your empty half.
    Now you are half full.
    '''
}
```


### YAML

Cons:

- Tabs (\t) not allowed/supported; break reader/documents


### TOML

Cons:

- Requires quoted strings


Others?


