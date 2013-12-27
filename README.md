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


## Extras


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


### YAML

Cons:

- Tabs (\t) not allowed/supported; break reader/documents


### TOML

Cons:

- Requires quoted strings


Others?


