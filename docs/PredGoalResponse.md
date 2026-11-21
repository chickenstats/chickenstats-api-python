# PredGoalResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** |  | 
**total** | **int** |  | 
**limit** | **int** |  | 
**offset** | **int** |  | 
**has_next** | **bool** |  | 
**notice** | **str** |  | [optional] 
**data** | [**List[PredGoalRow]**](PredGoalRow.md) |  | 

## Example

```python
from chickenstats_api.models.pred_goal_response import PredGoalResponse

# TODO update the JSON string below
json = "{}"
# create an instance of PredGoalResponse from a JSON string
pred_goal_response_instance = PredGoalResponse.from_json(json)
# print the JSON string representation of the object
print(PredGoalResponse.to_json())

# convert the object into a dict
pred_goal_response_dict = pred_goal_response_instance.to_dict()
# create an instance of PredGoalResponse from a dict
pred_goal_response_from_dict = PredGoalResponse.from_dict(pred_goal_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


