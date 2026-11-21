# ChangesResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[ChangesPublic]**](ChangesPublic.md) |  | 

## Example

```python
from chickenstats_api.models.changes_response import ChangesResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ChangesResponse from a JSON string
changes_response_instance = ChangesResponse.from_json(json)
# print the JSON string representation of the object
print(ChangesResponse.to_json())

# convert the object into a dict
changes_response_dict = changes_response_instance.to_dict()
# create an instance of ChangesResponse from a dict
changes_response_from_dict = ChangesResponse.from_dict(changes_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


