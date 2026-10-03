# RosterPublic


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**season** | **int** |  | 
**session** | **str** |  | 
**game_id** | **int** |  | 
**api_id** | **int** |  | [optional] 
**team** | **str** |  | 
**jersey** | **int** |  | [optional] 
**position** | **str** |  | [optional] 
**starter** | **int** |  | [optional] 
**rookie** | **int** |  | [optional] 
**captain** | **int** |  | [optional] 
**alternate_captain** | **int** |  | [optional] 
**status** | **str** |  | [optional] 
**active** | **int** |  | [optional] 
**player** | [**PlayerPublic**](PlayerPublic.md) |  | [optional] 
**game** | [**GamePublic**](GamePublic.md) |  | [optional] 

## Example

```python
from chickenstats_api.models.roster_public import RosterPublic

# TODO update the JSON string below
json = "{}"
# create an instance of RosterPublic from a JSON string
roster_public_instance = RosterPublic.from_json(json)
# print the JSON string representation of the object
print(RosterPublic.to_json())

# convert the object into a dict
roster_public_dict = roster_public_instance.to_dict()
# create an instance of RosterPublic from a dict
roster_public_from_dict = RosterPublic.from_dict(roster_public_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


