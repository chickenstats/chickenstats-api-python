# TeamPublic


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**code** | **str** |  | 
**team_name** | **str** |  | [optional] 
**division** | **str** |  | [optional] 
**conference** | **str** |  | [optional] 

## Example

```python
from chickenstats_api.models.team_public import TeamPublic

# TODO update the JSON string below
json = "{}"
# create an instance of TeamPublic from a JSON string
team_public_instance = TeamPublic.from_json(json)
# print the JSON string representation of the object
print(TeamPublic.to_json())

# convert the object into a dict
team_public_dict = team_public_instance.to_dict()
# create an instance of TeamPublic from a dict
team_public_from_dict = TeamPublic.from_dict(team_public_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


