# ShiftsResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[ShiftsPublic]**](ShiftsPublic.md) |  | 

## Example

```python
from chickenstats_api.models.shifts_response import ShiftsResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ShiftsResponse from a JSON string
shifts_response_instance = ShiftsResponse.from_json(json)
# print the JSON string representation of the object
print(ShiftsResponse.to_json())

# convert the object into a dict
shifts_response_dict = shifts_response_instance.to_dict()
# create an instance of ShiftsResponse from a dict
shifts_response_from_dict = ShiftsResponse.from_dict(shifts_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


