# Catalyst-Center-Jinja
CLI Templates used in Catalyst Center.

This repo will containe some snippets of Jinja2 code that works in the Catalyst Center to automate DayN configuration.

The final format is yet to be desided but so far it will just contain small snippets.
## Jinja Basics
Jinja code is set apart from any plaintext in a template (which is simply reprinted to the output) by using one of three types of delimiters to surround it:
### Statements
These contain any programming logic that the Jinja templating engine should execute.

- `{% %}`
- `{% set ipaddr = "172.16.150.10" %}`

### Expressions
These typically surround variable names, and they tell Jinja to print the contents of the variable to the output.

- `{{ }}`
- `{{ ipaddr }}`

### Comments
These are used to surround any comment text placed in the template. Comments are useful for explaining how a template works or giving additional detail.

- `{# #}`

### For loops
Looping through numbers to 11
```
{% for number in range(11) -%}
  {{ number }},
{%- endfor %}
```

Looping through a list:
```
{% set deviceTypes = ['Routers', 'Switches and Hubs', 'Voice and Telephony', 'Wireless Controller', 'Wireless Sensor'] %}
Device types (in multiple lines):
{% for deviceType in deviceTypes -%}
  deviceType : {{ deviceType }}
{% endfor %}
```

Looping through a key value pair
```
{% for iname, idata in interfaces.items() -%}
interface {{ iname }}
 description {{ idata.description }}
 ip address {{ idata.ipv4_address }}
{% endfor %}
```

### If statement

# References
- https://ciscolearning.github.io/cisco-learning-codelabs/posts/cat-center-j2-part-1/#0
- https://ttl255.com/jinja2-tutorial-part-2-loops-and-conditionals/
