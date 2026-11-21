# PbpResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[PbpPublic]**](PbpPublic.md) |  | 
**next_cursor** | **str** |  | [optional] 

## Example

```python
from chickenstats_api.models.pbp_response import PbpResponse

# TODO update the JSON string below
json = "{}"
# create an instance of PbpResponse from a JSON string
pbp_response_instance = PbpResponse.from_json(json)
# print the JSON string representation of the object
print(PbpResponse.to_json())

# convert the object into a dict
pbp_response_dict = pbp_response_instance.to_dict()
# create an instance of PbpResponse from a dict
pbp_response_from_dict = PbpResponse.from_dict(pbp_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


