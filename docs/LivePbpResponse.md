# LivePbpResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[LivePbpPublic]**](LivePbpPublic.md) |  | 

## Example

```python
from chickenstats_api.models.live_pbp_response import LivePbpResponse

# TODO update the JSON string below
json = "{}"
# create an instance of LivePbpResponse from a JSON string
live_pbp_response_instance = LivePbpResponse.from_json(json)
# print the JSON string representation of the object
print(LivePbpResponse.to_json())

# convert the object into a dict
live_pbp_response_dict = live_pbp_response_instance.to_dict()
# create an instance of LivePbpResponse from a dict
live_pbp_response_from_dict = LivePbpResponse.from_dict(live_pbp_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


