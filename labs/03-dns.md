# Lab 03 (Sep 18) Questions & Key

This document contains the questions for Lab 03: DNS. 

## Questions

1. What does the command `dig +short example.com` do, and what does it provide in response? 

Answer: It provides the "short" DNS entry for example.com, which is its IP address.

2. Recall the pattern for constructing the domain name for your server: [uniqname].projectst.si.umich.edu. What is the domain name for your server? 

Answer: this will depend on the user. For user `jajohnst`, the server domain is `jajohnst.projectst.si.umich.edu`. You should be able to query this with `curl` on the command line, or to request this resource in a browser.

3. Use the `dig` command to query your server. What is the command to return only the "answer" section of the response?  

Answer `dig +noall +answer DOMAIN`

4. The `dig` "answer" is roughly equivalent to the DNS record for your server. Use the command for the above response, and pipe the output to a file named UNIQNAME-dns-record.txt (where UNIQNAME is your uniqname). Provide the `dig` command and the resulting text file. 

Answer: Use the above command but output it to a file using the `>` output direction.

File should look something like this: 

`jajohnst.projectst.si.umich.edu. 1800 IN A	141.211.185.70`


## Bonus

5. Note that you can ask for multiple domain names. For example: `dig +noall +answer si.umich.edu umich.edu wisc.edu education.wisc.edu`. The response is a good use case for a tool like `awk`. If you use a pipe to route the data from dig to awk, can you produce a comma-separated-values-like output of just the domain and the IP address? 
  * We discussed the `awk` language in class very briefly. If you want to learn more about it, you can look at the G-AWK manual at https://www.gnu.org/software/gawk/manual/gawk.html. It is very useful for parsing data in columns, which is a frequent pattern seen in the command line/text interface. Variables are named with dollar signs `$1` and the output patterns are enclosed in curly braces `{}`. This should be very similar to the exmaple presented in the slack channel, but you will need to add in a comma for the output. 

Answer: 
```bash
dig +noall +answer si.umich.edu umich.edu wisc.edu education.wisc.edu | awk '{print $1,",",$NF}'
```

Output:
```
si.umich.edu. , 18.221.166.136
umich.edu. , 141.211.243.251
wisc.edu. , 144.92.9.70
education.wisc.edu. , 99.83.210.234
education.wisc.edu. , 75.2.33.159
```