
https://www.middlewareinventory.com/blog/ansible-dict/

# Dictionary Example
Quote: In the following playbook example, we are going to create a dictionary named userdata using the default filter and adding elements to it using the combine filter
```
- name: Dictionary playbook example
  hosts: localhost
  tasks:

    - name: Create and Add items to dictionary
      set_fact:
        userdata: "{{ userdata | default({}) | combine ({ item.key : item.value }) }}"
      with_items:
        - { 'key': 'Name' , 'value': 'SaravAK'}
        - { 'key': 'Email' , 'value': 'sarav@gritfy.com'}
        - { 'key': 'Location' , 'value': 'Coimbatore'}
        - { 'key': 'Nationality' , 'value': 'Indian'}

    -  name: Display the Dictionary
       debug: var=userdata
```


# List Example
https://ttl255.com/ansible-appending-to-lists-and-dictionaries/
Similar concept applies to combining dictionaries. Here we assign an empty dictionary to the newly initiated variable. In the assignment expression we will need to use filter "combine" to add new key-value pairs to the existing dictionary.

```
- name: Add Cisco and Airsta devices to the list
  set_fact:
    devices: "{{ devices + [item] }}"
  with_items:
   - "{{ cisco }}"
```
