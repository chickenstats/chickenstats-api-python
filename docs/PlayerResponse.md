# PlayerResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[PlayerPublic]**](PlayerPublic.md) |  | 

## Example

```python
from chickenstats_api.models.player_response import PlayerResponse

# TODO update the JSON string below
json = "{}"
# create an instance of PlayerResponse from a JSON string
player_response_instance = PlayerResponse.from_json(json)
# print the JSON string representation of the object
print(PlayerResponse.to_json())

# convert the object into a dict
player_response_dict = player_response_instance.to_dict()
# create an instance of PlayerResponse from a dict
player_response_from_dict = PlayerResponse.from_dict(player_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


