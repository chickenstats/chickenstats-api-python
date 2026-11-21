# Newsletters


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**announcements** | **bool** |  | 
**paid** | **bool** |  | 
**paid_access** | **bool** |  | 

## Example

```python
from chickenstats_api.models.newsletters import Newsletters

# TODO update the JSON string below
json = "{}"
# create an instance of Newsletters from a JSON string
newsletters_instance = Newsletters.from_json(json)
# print the JSON string representation of the object
print(Newsletters.to_json())

# convert the object into a dict
newsletters_dict = newsletters_instance.to_dict()
# create an instance of Newsletters from a dict
newsletters_from_dict = Newsletters.from_dict(newsletters_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


