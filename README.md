Amateur radio test data
=======================

One of the major challenges for authors of Amateur Radio software is
mapping callsigns (such as 'M0PRL') to their associated geographical
area (England).

An excellent list of entity mappings is available from
[Club Log](http://www.clublog.org/), but it doesn't tell the whole
story; there are many irregularities and historical quirks in radio
licensing and dealing with some of them requires dedicated code rather
than a straightforward mapping.

The problem with writing code for such exceptions is, of course, making
sure of your coverage and accuracy without a good list of test cases,
which is where this project comes in...

Here you will find a central, shared list of test data for entity
resolution routines.  Contributions are encouraged; just send a pull
request or raise an issue.

File format
-----------

The format of the test data is designed to be as easy as possible to
parse using a wide range of languages and platforms.

### Comments

Comments start with a `#' and extend to the end of the line.

### Records

Each record is a single line, terminated by a `\n'.  Fields are
separated by single tab characters.

### Fields

 1. Callsign.
 2. ADIF ID of correct DXCC entity.
 3. Date and time, in ISO-8601 extended format wrapped in double
    quotes. The timezone is always UTC.  If this is unspecified the
    field contains `nil' (unquoted), in which case you should check
    using the current date and time.
 4. Optional notes, as a string delimited by double quotes.  It is
    not possible to escape the delimiters, so you can't include
    double quotes in the note itself.

License
-------

This work is licensed under a
[Creative Commons Attribution-ShareAlike 3.0 Unported License]
(http://creativecommons.org/licenses/by-sa/3.0/deed.en_US)
