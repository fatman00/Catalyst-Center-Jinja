# Manipulation of string
Jinja2 in the Catalyst Center supports manipulation of string

## String selection
```
{% set text = "Hello World!" %}
Here we're selecting a single character:
{{ text[0:1] }}
{{ text[6:7] }}
```

## String length
```
{% set text = "Hello World!" %}
This is an example of a "method": {{ text.length() }}
This is an example of a "Filter": {{ text | length }}
```

## String Manipulation
- **capitalize:** This filter will capitalize the first character of a string, as long as the first character is alphabetical. In other words, if a string starts with something like a space or a number, no capitalization will be applied.
- **title:** This filter will capitalize the first letter of every distinct word found in a string. Any group of alphabetical characters separated by a space will be considered a word.
- **upper:** This filter transforms all alphabetical characters in a string into uppercase letters.
- **lower:** This filter is the opposite of `upper`, it converts all alphabetical characters to lowercase letters
- **trim:** This filter will remove any beginning or trailing whitespace characters (a space) found in a string. It only removes spaces from the beginning and end of a string; spaces in the middle of a string will remain intact.
- **length:** This filter returns the integer number representing the length of a string—that is, the number of characters it contains.
- **replace():** This filter searches for the occurrence of a string of characters and replaces them with the value that you specify.

```
{% set text_2 = "hello world!" %}
{% set text_3 = " HELLO WORLD!" %}
Capitalize: {{ text_2 | capitalize }}
Title: {{ text_2 | title }}
Upper: {{ text_2 | upper }}
Lower: {{ text_3 | lower }}
Trim: {{ text_3 | trim }}
Length: {{ text_3 | length }}
Replace: {{ text_2 | replace("hello", "goodbye") }}
```

## New string heading??!!!?!?!?!?!
- **contains():** This method searches for a substring inside of the string variable that you use it on and returns either true or false.
- **indexOf():** This method searches for the first occurrence of a character inside the string variable that you use it on and returns the integer index number where the character was found.
- **replaceAll():** The replaceAll() method operates similarly to the replace() method. But replaces all occurances of the search string.
- **split():** The split method will split any string into an list at the char specified.

## CLI template
```
interface Vlan{{mgmtvlan}}
 ip address {{ipaddr}} 255.255.255.0
 no shutdown
!
! Using split to seperate the IP addres by octet. Notice the \\ escape  chars
{% set list1 = ipaddr.split('\\.') %}
ip default-gateway {{list1[0]}}.{{list1[1]}}.{{list1[2]}}.1
```
