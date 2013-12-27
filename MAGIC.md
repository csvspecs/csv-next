
# Magic / Shortcuts

Ideas for making comma separated values easier to read and write



## Auto Keys

If the first field is all lowercase (e.g. [a-z]+), assume it's a key.

    newyork, New York

If the first field is NOT all lowercase, auto add the key (e.g New York becomse newyork).

    New York

equals

    newyork, New York




## Alternative Names (Titles)

Use the pipe | to separate alternative names (titles).

    Barcelona|FC Barcelona|F.C. Barcelona|Fútbol Club Barcelona


## Alternative Languages

Assume translations in square brackets [] are alternative English names (titles).

    Bayern [Baviria]


## Newline Breaks with //

Use double slash // for newline breaks inside a field.

    Saint James's Gate // Dublin 8


## Tags

Assume last field (if all lowercase plus underscore plus space plus pipe) are tags


Conventions:

- First field if all lowercase assumed key  e.g. guinness
- Last field if all lowercase assumed tags  e.g. irish_dry_stout|dry_stout|stout


## Quotes are Quotes   -   No Special Meaning (No Need for Double Quotes etc.)

## Escape Commas \,   -  Avoids Quotes

    Fuller\, Smith & Turner

Ideas

Option 1: Use a different character for comma , e.g. |  (in an address field)

    London | W4 2QB

equals

    London \, W4 2QB



## Default Values Encoded in File Name or Directory Structure / Name

    europe/at-austria/beers.txt

- continent key is europe
- country key is at
- record type is beer


