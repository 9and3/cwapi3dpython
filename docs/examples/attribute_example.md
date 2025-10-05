---
hide:
  - toc
---

# attribute_controller

## Conditions 

```python
import  attribute_controller  as ac     # import module
import  element_controller    as ec   


# get active element_ids
element_ids = ec.get_active_identifiable_element_ids()

for element_id in element_ids:
    if ac.is_panel(element_id): # returns boolean
        print (True)
    else:
        print (False)
```

```python
import  attribute_controller  as ac     # import module
import  element_controller    as ec   
import  cadwork


# get active element_ids
element_ids = ec.get_active_identifiable_element_ids()

for element_id in element_ids:
    element_type = ac.get_element_type(element_id)
    if element_type.is_rectangular_beam():
        # do something
```

## set attributes
```python
import  attribute_controller  as ac     # import module
import  element_controller    as ec   

element_ids = ec.get_active_identifiable_element_ids()

ac.set_user_attribute_name(11, "ExampleAttribute")
ac.set_user_attribute(element_ids, 11, "Hello World!")
```

## get attributes
```python
import  attribute_controller  as ac     # import module
import  element_controller    as ec   


# get active element_ids
element_ids = ec.get_active_identifiable_element_ids()

for element_id in element_ids:
    user_attr = ac.get_user_attribute(element_id, 20) # 20 = attribute number
    user_attr_name = ac.get_user_attribute_name(20)
    element_guid = ec.get_element_cadwork_guid(element_id)
    
    print(user_a_name, 
          user_a,
          element_guid
          )
```
