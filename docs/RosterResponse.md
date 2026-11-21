# RosterResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[RosterPublic]**](RosterPublic.md) |  | 

## Example

```python
from chickenstats_api.models.roster_response import RosterResponse

# TODO update the JSON string below
json = "{}"
# create an instance of RosterResponse from a JSON string
roster_response_instance = RosterResponse.from_json(json)
# print the JSON string representation of the object
print(RosterResponse.to_json())

# convert the object into a dict
roster_response_dict = roster_response_instance.to_dict()
# create an instance of RosterResponse from a dict
roster_response_from_dict = RosterResponse.from_dict(roster_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


