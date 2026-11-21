# LinesSeasonResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[LinesSeason]**](LinesSeason.md) |  | 

## Example

```python
from chickenstats_api.models.lines_season_response import LinesSeasonResponse

# TODO update the JSON string below
json = "{}"
# create an instance of LinesSeasonResponse from a JSON string
lines_season_response_instance = LinesSeasonResponse.from_json(json)
# print the JSON string representation of the object
print(LinesSeasonResponse.to_json())

# convert the object into a dict
lines_season_response_dict = lines_season_response_instance.to_dict()
# create an instance of LinesSeasonResponse from a dict
lines_season_response_from_dict = LinesSeasonResponse.from_dict(lines_season_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


