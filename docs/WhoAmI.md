# WhoAmI


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**tier** | **str** |  | 
**kind** | **str** |  | 
**prefix** | **str** |  | [optional] 
**email** | **str** |  | 

## Example

```python
from chickenstats_api.models.who_am_i import WhoAmI

# TODO update the JSON string below
json = "{}"
# create an instance of WhoAmI from a JSON string
who_am_i_instance = WhoAmI.from_json(json)
# print the JSON string representation of the object
print(WhoAmI.to_json())

# convert the object into a dict
who_am_i_dict = who_am_i_instance.to_dict()
# create an instance of WhoAmI from a dict
who_am_i_from_dict = WhoAmI.from_dict(who_am_i_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


