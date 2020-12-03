# interpolate variables or dynamic variable names
https://docs.ansible.com/ansible/latest/reference_appendices/faq.html#when-should-i-use-also-how-to-interpolate-variables-or-dynamic-variable-names



if you need to use a dynamic variable use the following as appropriate:

`{{ hostvars[inventory_hostname]['somevar_' + other_var] }}`

For ‘non host vars’ you can use the vars lookup plugin:
`{{ lookup('vars', 'somevar_' + other_var) }}`
