# RapmScores


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** |  | 
**api_id** | **int** |  | 
**season** | **int** |  | 
**session** | **str** |  | 
**situation** | **str** |  | 
**team** | **str** |  | [optional] 
**pos** | **str** |  | [optional] 
**pos2** | **str** |  | [optional] 
**toi_minutes** | **float** |  | [optional] 
**def_toi_minutes** | **float** |  | [optional] 
**rapm_off** | **float** |  | [optional] 
**rapm_def** | **float** |  | [optional] 
**off_coeff_corsi** | **float** |  | [optional] 
**off_coeff_goals** | **float** |  | [optional] 
**def_coeff_corsi** | **float** |  | [optional] 
**def_coeff_goals** | **float** |  | [optional] 
**metric_for_context_xg** | **float** |  | [optional] 
**metric_against_context_xg** | **float** |  | [optional] 
**metric_diff_context_xg** | **float** |  | [optional] 
**metric_for_corsi** | **float** |  | [optional] 
**metric_against_corsi** | **float** |  | [optional] 
**metric_diff_corsi** | **float** |  | [optional] 
**metric_for_goals** | **float** |  | [optional] 
**metric_against_goals** | **float** |  | [optional] 
**metric_diff_goals** | **float** |  | [optional] 
**on_ice_for_60_context_xg** | **float** |  | [optional] 
**on_ice_against_60_context_xg** | **float** |  | [optional] 
**on_ice_diff_60_context_xg** | **float** |  | [optional] 
**on_ice_for_60_corsi** | **float** |  | [optional] 
**on_ice_against_60_corsi** | **float** |  | [optional] 
**on_ice_diff_60_corsi** | **float** |  | [optional] 
**on_ice_for_60_goals** | **float** |  | [optional] 
**on_ice_against_60_goals** | **float** |  | [optional] 
**on_ice_diff_60_goals** | **float** |  | [optional] 
**total_rapm_context_xg** | **float** |  | [optional] 
**total_rapm_corsi** | **float** |  | [optional] 
**total_rapm_goals** | **float** |  | [optional] 
**off_coeff_context_xg_z** | **float** |  | [optional] 
**off_coeff_corsi_z** | **float** |  | [optional] 
**off_coeff_goals_z** | **float** |  | [optional] 
**def_coeff_context_xg_z** | **float** |  | [optional] 
**def_coeff_corsi_z** | **float** |  | [optional] 
**def_coeff_goals_z** | **float** |  | [optional] 
**metric_for_context_xg_z** | **float** |  | [optional] 
**metric_against_context_xg_z** | **float** |  | [optional] 
**metric_diff_context_xg_z** | **float** |  | [optional] 
**metric_for_corsi_z** | **float** |  | [optional] 
**metric_against_corsi_z** | **float** |  | [optional] 
**metric_diff_corsi_z** | **float** |  | [optional] 
**metric_for_goals_z** | **float** |  | [optional] 
**metric_against_goals_z** | **float** |  | [optional] 
**metric_diff_goals_z** | **float** |  | [optional] 
**on_ice_for_60_context_xg_z** | **float** |  | [optional] 
**on_ice_against_60_context_xg_z** | **float** |  | [optional] 
**on_ice_diff_60_context_xg_z** | **float** |  | [optional] 
**on_ice_for_60_corsi_z** | **float** |  | [optional] 
**on_ice_against_60_corsi_z** | **float** |  | [optional] 
**on_ice_diff_60_corsi_z** | **float** |  | [optional] 
**on_ice_for_60_goals_z** | **float** |  | [optional] 
**on_ice_against_60_goals_z** | **float** |  | [optional] 
**on_ice_diff_60_goals_z** | **float** |  | [optional] 
**total_rapm_context_xg_z** | **float** |  | [optional] 
**total_rapm_corsi_z** | **float** |  | [optional] 
**total_rapm_goals_z** | **float** |  | [optional] 

## Example

```python
from chickenstats_api.models.rapm_scores import RapmScores

# TODO update the JSON string below
json = "{}"
# create an instance of RapmScores from a JSON string
rapm_scores_instance = RapmScores.from_json(json)
# print the JSON string representation of the object
print(RapmScores.to_json())

# convert the object into a dict
rapm_scores_dict = rapm_scores_instance.to_dict()
# create an instance of RapmScores from a dict
rapm_scores_from_dict = RapmScores.from_dict(rapm_scores_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


