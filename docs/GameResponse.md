# GameResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[GamePublic]**](GamePublic.md) |  | 

## Example

```python
from chickenstats_api.models.game_response import GameResponse

# TODO update the JSON string below
json = "{}"
# create an instance of GameResponse from a JSON string
game_response_instance = GameResponse.from_json(json)
# print the JSON string representation of the object
print(GameResponse.to_json())

# convert the object into a dict
game_response_dict = game_response_instance.to_dict()
# create an instance of GameResponse from a dict
game_response_from_dict = GameResponse.from_dict(game_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


