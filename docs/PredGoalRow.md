# PredGoalRow


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**game_id** | **int** |  | 
**event_idx** | **int** |  | 
**season** | **int** |  | 
**session** | **str** |  | 
**event** | **str** |  | 
**period** | **int** |  | 
**period_seconds** | **int** |  | 
**player_1_api_id** | **int** |  | 
**base_xg** | **float** |  | 
**context_xg** | **float** |  | 
**pred_goal** | **float** |  | 

## Example

```python
from chickenstats_api.models.pred_goal_row import PredGoalRow

# TODO update the JSON string below
json = "{}"
# create an instance of PredGoalRow from a JSON string
pred_goal_row_instance = PredGoalRow.from_json(json)
# print the JSON string representation of the object
print(PredGoalRow.to_json())

# convert the object into a dict
pred_goal_row_dict = pred_goal_row_instance.to_dict()
# create an instance of PredGoalRow from a dict
pred_goal_row_from_dict = PredGoalRow.from_dict(pred_goal_row_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


