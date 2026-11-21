# RapmResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[RapmScores]**](RapmScores.md) |  | 

## Example

```python
from chickenstats_api.models.rapm_response import RapmResponse

# TODO update the JSON string below
json = "{}"
# create an instance of RapmResponse from a JSON string
rapm_response_instance = RapmResponse.from_json(json)
# print the JSON string representation of the object
print(RapmResponse.to_json())

# convert the object into a dict
rapm_response_dict = rapm_response_instance.to_dict()
# create an instance of RapmResponse from a dict
rapm_response_from_dict = RapmResponse.from_dict(rapm_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


