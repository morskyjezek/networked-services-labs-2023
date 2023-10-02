# Lab 04 (Sep 25) Questions & Key


1. What function do you use in Python to create a regex pattern?

```python
re.compile(r'') # the regex goes inbetween the quotes inside the parentheses
```

1. What does the re `.search()` method return?

This returns the first string that matches the given regular expression.

1. How can you display or return the strings that are matched? (The use of `group` can be a bit unexpected in the implementation of this python library.)

Using the return from search, findall, or finditer, you can use the `.group` or `.match` methods to display the matched content. 

1. The `findall()` method can return a list of strings or a list of tuples. Why would it return one or the other? 

The findall function returns tuples if groups are specified within the regular expression. If there are not groups, then the match object is a string.

1. The `finditer()` method allows you to loop through the match string and do something for each return. Write a block of code that searches the contents of the `mbox-short.txt` file to identify IP addresses, then writes each to file called `ip-addresses.txt`. Add the output file to your repo with the notebook. 

For the solution to this question, please see the code in this notebook: https://github.com/morskyjezek/networked-services-labs-2023/blob/main/python-regex-ip-address-demo.ipynb