# LiveGamesPublic


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**game_id** | **int** |  | 
**game_date** | **str** |  | 
**home_team** | **str** |  | 
**away_team** | **str** |  | 
**game_state** | **str** |  | 
**period** | **int** |  | 
**time_remaining** | **str** |  | 
**home_score** | **int** |  | 
**away_score** | **int** |  | 
**last_updated** | **datetime** |  | 
**xg_status** | **str** |  | [optional] 

## Example

```python
from chickenstats_api.models.live_games_public import LiveGamesPublic

# TODO update the JSON string below
json = "{}"
# create an instance of LiveGamesPublic from a JSON string
live_games_public_instance = LiveGamesPublic.from_json(json)
# print the JSON string representation of the object
print(LiveGamesPublic.to_json())

# convert the object into a dict
live_games_public_dict = live_games_public_instance.to_dict()
# create an instance of LiveGamesPublic from a dict
live_games_public_from_dict = LiveGamesPublic.from_dict(live_games_public_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


