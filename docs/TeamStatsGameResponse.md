# TeamStatsGameResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[TeamStatsGame]**](TeamStatsGame.md) |  | 

## Example

```python
from chickenstats_api.models.team_stats_game_response import TeamStatsGameResponse

# TODO update the JSON string below
json = "{}"
# create an instance of TeamStatsGameResponse from a JSON string
team_stats_game_response_instance = TeamStatsGameResponse.from_json(json)
# print the JSON string representation of the object
print(TeamStatsGameResponse.to_json())

# convert the object into a dict
team_stats_game_response_dict = team_stats_game_response_instance.to_dict()
# create an instance of TeamStatsGameResponse from a dict
team_stats_game_response_from_dict = TeamStatsGameResponse.from_dict(team_stats_game_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


