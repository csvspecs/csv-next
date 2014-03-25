
## Comments


Supported styles:

### Start-of-Line Comments

~~~
#  Comment here
## Comment here
~~~

Used by: Shell, Ruby, Git (Config), Java Properties (?)  - Others ???


~~~
-- Comment here
~~~

Used by: SQL (?), Ada (?), Haskell ? - Others


~~~
; Comment here
~~~

Used by: Git (Config), Windows INI (?) - Others

~~~
%% Comment here
~~~

Used by: TeX, LaTeX (?)


More candidates:

~~~
// Comment here
~~~

Used by: C++, C#, JavaScript (?), Java (?)

~~~
/*  */
~~~

Used by: C, CSS, Java, JavaScript (?)


~~~
____________________
~~~

All Underscores




### Multi-Line Blocks

~~~
__END__
~~~

Used by: Ruby

~~~
__BEGIN__
__END__
~~~

Used by: Ruby


### End-of-Line Comments

Check:

- Must have leading space? Why? Why not?
- Must have trailing space?  Why? Why not?

e.g.

~~~
data data data _#_ comment here   -- will not include #1 or Object#blank?
data data data _--_ comment here
~~~


### Inline (Embedded) Comments

How to comment out a block inside a line? Use

~~~
{# }
or
{# #}
~~~

Why? Why not?


