# StatsGameResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[StatsGame]**](StatsGame.md) |  | 

## Example

```python
from chickenstats_api.models.stats_game_response import StatsGameResponse

# TODO update the JSON string below
json = "{}"
# create an instance of StatsGameResponse from a JSON string
stats_game_response_instance = StatsGameResponse.from_json(json)
# print the JSON string representation of the object
print(StatsGameResponse.to_json())

# convert the object into a dict
stats_game_response_dict = stats_game_response_instance.to_dict()
# create an instance of StatsGameResponse from a dict
stats_game_response_from_dict = StatsGameResponse.from_dict(stats_game_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


