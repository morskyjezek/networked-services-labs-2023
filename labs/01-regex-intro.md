# Lab 01 (Aug 28) Key

This document contains the questions and solutions to the question from Lab 01. 

## Questions

Consult the following text document - https://lccn.loc.gov/2016959361/marcxml - and answer the questions below using regular expressions: 

*How many subfield entries are there?*

Answer: 92

Regex: /<subfield/

*How could you find ISO-8601 formatted dates (using regular expressions)? (In other words, provide the regex that would match such a date.)* 

Answer: search using the following regex

Regex: /\d{4}-\d{2}-\d{2}/

A more precise regex could be: /(19|20)\d{2}-(0|1)\d-(0|1|2|3)\d/

*How would you find an ISBN number? Are there any ISBN numbers?* 

Answer: ISBN numbers are 13 or 10 digits. The 13-digit ISBNs start with 978. 

Regex: /978-?\d{10}/

*How many occurrences of computer (singular, plural, upper-lower)?*

Answer: there are 7 instances of the word computer, no plural.

Regex: /[Cc]omputers?/

Are there any web addresses in the text? How many?  

Answer: Yes. There are two web addresses. 

Regex: /https?:\/\/\w{3,4}\.[\w-]+\.\w{3}\//

Note: there may be other variations that will match this pattern. 

*Can you isolate the domains and protocol designations of the web addresses? (That is, are they http? https? Are they www? Another? .com? .gov? etc)*

Yes. As below, group 1 matches the protocol; group 2 matches the subdomain; group 3 matchest the top-level domain.

Regex: /(https?):\/\/(\w{3})\.[\w-]+(\.\w{3})\//gm