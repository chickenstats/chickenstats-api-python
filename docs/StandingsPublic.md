# StandingsPublic


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**season** | **int** |  | 
**team** | **str** |  | 
**points** | **int** |  | [optional] 
**points_percentage** | **float** |  | [optional] 
**wins** | **int** |  | [optional] 
**losses** | **int** |  | [optional] 
**otl** | **int** |  | [optional] 
**games_played** | **int** |  | [optional] 
**goals_scored** | **int** |  | [optional] 
**goals_against** | **int** |  | [optional] 
**streak** | **str** |  | [optional] 
**last_updated** | **datetime** |  | [optional] 

## Example

```python
from chickenstats_api.models.standings_public import StandingsPublic

# TODO update the JSON string below
json = "{}"
# create an instance of StandingsPublic from a JSON string
standings_public_instance = StandingsPublic.from_json(json)
# print the JSON string representation of the object
print(StandingsPublic.to_json())

# convert the object into a dict
standings_public_dict = standings_public_instance.to_dict()
# create an instance of StandingsPublic from a dict
standings_public_from_dict = StandingsPublic.from_dict(standings_public_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


