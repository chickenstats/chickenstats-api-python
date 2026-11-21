# TeamStatsSeasonResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[TeamStatsSeason]**](TeamStatsSeason.md) |  | 

## Example

```python
from chickenstats_api.models.team_stats_season_response import TeamStatsSeasonResponse

# TODO update the JSON string below
json = "{}"
# create an instance of TeamStatsSeasonResponse from a JSON string
team_stats_season_response_instance = TeamStatsSeasonResponse.from_json(json)
# print the JSON string representation of the object
print(TeamStatsSeasonResponse.to_json())

# convert the object into a dict
team_stats_season_response_dict = team_stats_season_response_instance.to_dict()
# create an instance of TeamStatsSeasonResponse from a dict
team_stats_season_response_from_dict = TeamStatsSeasonResponse.from_dict(team_stats_season_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


