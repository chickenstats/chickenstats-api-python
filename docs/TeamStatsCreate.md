# TeamStatsCreate


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**toi** | **float** |  | 
**gf** | **int** |  | [optional] [default to 0]
**ga** | **int** |  | [optional] [default to 0]
**gf_adj** | **float** |  | [optional] [default to 0]
**ga_adj** | **float** |  | [optional] [default to 0]
**hdgf** | **int** |  | [optional] [default to 0]
**hdga** | **int** |  | [optional] [default to 0]
**base_xgf** | **float** |  | [optional] [default to 0]
**base_xga** | **float** |  | [optional] [default to 0]
**base_xgf_adj** | **float** |  | [optional] [default to 0]
**base_xga_adj** | **float** |  | [optional] [default to 0]
**context_xgf** | **float** |  | [optional] [default to 0]
**context_xga** | **float** |  | [optional] [default to 0]
**context_xgf_adj** | **float** |  | [optional] [default to 0]
**context_xga_adj** | **float** |  | [optional] [default to 0]
**xgf** | **float** |  | [optional] [default to 0]
**xga** | **float** |  | [optional] [default to 0]
**xgf_adj** | **float** |  | [optional] [default to 0]
**xga_adj** | **float** |  | [optional] [default to 0]
**sf** | **int** |  | [optional] [default to 0]
**sa** | **int** |  | [optional] [default to 0]
**sf_adj** | **float** |  | [optional] [default to 0]
**sa_adj** | **float** |  | [optional] [default to 0]
**hdsf** | **int** |  | [optional] [default to 0]
**hdsa** | **int** |  | [optional] [default to 0]
**ff** | **int** |  | [optional] [default to 0]
**fa** | **int** |  | [optional] [default to 0]
**ff_adj** | **float** |  | [optional] [default to 0]
**fa_adj** | **float** |  | [optional] [default to 0]
**hdff** | **int** |  | [optional] [default to 0]
**hdfa** | **int** |  | [optional] [default to 0]
**cf** | **int** |  | [optional] [default to 0]
**ca** | **int** |  | [optional] [default to 0]
**cf_adj** | **float** |  | [optional] [default to 0]
**ca_adj** | **float** |  | [optional] [default to 0]
**bsf** | **int** |  | [optional] [default to 0]
**bsa** | **int** |  | [optional] [default to 0]
**bsf_adj** | **float** |  | [optional] [default to 0]
**bsa_adj** | **float** |  | [optional] [default to 0]
**msf** | **int** |  | [optional] [default to 0]
**msa** | **int** |  | [optional] [default to 0]
**msf_adj** | **float** |  | [optional] [default to 0]
**msa_adj** | **float** |  | [optional] [default to 0]
**hdmsf** | **int** |  | [optional] [default to 0]
**hdmsa** | **int** |  | [optional] [default to 0]
**teammate_block** | **int** |  | [optional] [default to 0]
**teammate_block_adj** | **float** |  | [optional] [default to 0]
**hf** | **int** |  | [optional] [default to 0]
**ht** | **int** |  | [optional] [default to 0]
**ozf** | **int** |  | [optional] [default to 0]
**nzf** | **int** |  | [optional] [default to 0]
**dzf** | **int** |  | [optional] [default to 0]
**fow** | **int** |  | [optional] [default to 0]
**fol** | **int** |  | [optional] [default to 0]
**ozfw** | **int** |  | [optional] [default to 0]
**ozfl** | **int** |  | [optional] [default to 0]
**nzfw** | **int** |  | [optional] [default to 0]
**nzfl** | **int** |  | [optional] [default to 0]
**dzfw** | **int** |  | [optional] [default to 0]
**dzfl** | **int** |  | [optional] [default to 0]
**pent0** | **int** |  | [optional] [default to 0]
**pent2** | **int** |  | [optional] [default to 0]
**pent4** | **int** |  | [optional] [default to 0]
**pent5** | **int** |  | [optional] [default to 0]
**pent10** | **int** |  | [optional] [default to 0]
**pend0** | **int** |  | [optional] [default to 0]
**pend2** | **int** |  | [optional] [default to 0]
**pend4** | **int** |  | [optional] [default to 0]
**pend5** | **int** |  | [optional] [default to 0]
**pend10** | **int** |  | [optional] [default to 0]
**season** | **int** |  | 
**session** | **str** |  | 
**game_id** | **int** |  | 
**team** | **str** |  | 
**opp_team** | **str** |  | [optional] 
**strength_state** | **str** |  | [optional] 
**period** | **int** |  | [optional] 
**score_state** | **str** |  | [optional] 

## Example

```python
from chickenstats_api.models.team_stats_create import TeamStatsCreate

# TODO update the JSON string below
json = "{}"
# create an instance of TeamStatsCreate from a JSON string
team_stats_create_instance = TeamStatsCreate.from_json(json)
# print the JSON string representation of the object
print(TeamStatsCreate.to_json())

# convert the object into a dict
team_stats_create_dict = team_stats_create_instance.to_dict()
# create an instance of TeamStatsCreate from a dict
team_stats_create_from_dict = TeamStatsCreate.from_dict(team_stats_create_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


