# Lab 03 (Sep 18) Questions & Key

This document contains the questions for Lab 03: DNS. 

## Questions

1. What does the command `dig +short example.com` do, and what does it provide in response? 
2. Recall the pattern for constructing the domain name for your server: [uniqname].projectst.si.umich.edu. What is the domain name for your server? 
3. Use the `dig` command to query your server. What is the command to return only the "answer" section of the response?  
4. The `dig` "answer" is roughly equivalent to the DNS record for your server. Use the command for the above response, and pipe the output to a file named UNIQNAME-dns-record.txt (where UNIQNAME is your uniqname). Provide the `dig` command and the resulting text file. 

## Bonus

5. Note that you can ask for multiple domain names. For example: `dig +noall +answer si.umich.edu umich.edu wisc.edu education.wisc.edu`. The response is a good use case for a tool like `awk`. If you use a pipe to route the data from dig to awk, can you produce a comma-separated-values-like output of just the domain and the IP address? 
  * We discussed the `awk` language in class very briefly. If you want to learn more about it, you can look at the G-AWK manual at https://www.gnu.org/software/gawk/manual/gawk.html. It is very useful for parsing data in columns, which is a frequent pattern seen in the command line/text interface. Variables are named with dollar signs `$1` and the output patterns are enclosed in curly braces `{}`. This should be very similar to the exmaple presented in the slack channel, but you will need to add in a comma for the output. 