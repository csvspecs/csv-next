
## Names


### Optional Name Additions

Use the `()` to mark optional name parts

~~~
(Ciudad de) México
~~~

Will become:

~~~
México
Ciudad de México
~~~

Check: Also include (Ciudad de) México? Why? Why not?


### Commentrary Name Additions

Use the `{}` to mark commentary parts in names (will not get included in name - but may get processed e.g. for tags etc. - works like a user exit/processing instruction)

~~~
Ottakringer Gold Fassl Pur {Bio}
~~~

Will become:

~~~
Ottakringer Gold Fassl Pur
~~~


### Name Parts

use the `‹›` or `<>` to mark parts in names

~~~
‹Ottakringer› ‹Gold Fassl› Pur
<Ottakringer> <Gold Fassl> Pur  or
~~~

Will become:

~~~
Ottakringer Gold Fassl Pur      => plus parts: Ottakringer, Gold Fassl
~~~


### Alternative Names

Use the pipe `|` to separate alternative names

~~~
Los Angeles|L.A.
~~~

Will become:

~~~
Los Angeles
L.A.
~~~


### English Names/Translation

Use brackets `[]` to mark English names/translations

~~~
Antwerpen [Antwerp]
~~~

Will become:

~~~
Antwerpen
Antwerp [en]
~~~


### Non-English Names/Translations

Use trailing brackets `[]` with the language code

~~~
Brugge[nl] Bruges[fr] Brügge[de]      or
Brugge [nl]|Bruges [fr]|Brügge [de]
~~~

Will become

~~~
Brugge [nl]
Bruges [fr]
Brügge [de] 
~~~


### Bi-Lingual, Tri-Lingual Names

Use the bullet (black small circle) e.g. `•` char as separator

~~~
Brussel • Bruxelles
~~~

Will become (three-in-one)

~~~
Brussel • Bruxelles
Brussel [nl]
Bruxelles [fr]
~~~


### Transliteration ?? (to be done)

~~~
Moskva::Москва [Moscow]   ??
Moskva::Москва[ru] [Moscow]  ??

Sankt-Peterburg->Санкт-Петербур [St. Petersburg]  ??
Sankt-Peterburg->Санкт-Петербур[ru] [St. Petersburg]  ??
~~~

Will become

~~~
???
~~~



### References / Links

- add Open Street Map names wiki page

