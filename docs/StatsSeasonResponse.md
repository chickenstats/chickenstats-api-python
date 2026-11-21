# StatsSeasonResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[StatsSeason]**](StatsSeason.md) |  | 

## Example

```python
from chickenstats_api.models.stats_season_response import StatsSeasonResponse

# TODO update the JSON string below
json = "{}"
# create an instance of StatsSeasonResponse from a JSON string
stats_season_response_instance = StatsSeasonResponse.from_json(json)
# print the JSON string representation of the object
print(StatsSeasonResponse.to_json())

# convert the object into a dict
stats_season_response_dict = stats_season_response_instance.to_dict()
# create an instance of StatsSeasonResponse from a dict
stats_season_response_from_dict = StatsSeasonResponse.from_dict(stats_season_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


