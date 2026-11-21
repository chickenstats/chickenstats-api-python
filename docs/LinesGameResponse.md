# LinesGameResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[LinesGame]**](LinesGame.md) |  | 

## Example

```python
from chickenstats_api.models.lines_game_response import LinesGameResponse

# TODO update the JSON string below
json = "{}"
# create an instance of LinesGameResponse from a JSON string
lines_game_response_instance = LinesGameResponse.from_json(json)
# print the JSON string representation of the object
print(LinesGameResponse.to_json())

# convert the object into a dict
lines_game_response_dict = lines_game_response_instance.to_dict()
# create an instance of LinesGameResponse from a dict
lines_game_response_from_dict = LinesGameResponse.from_dict(lines_game_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


