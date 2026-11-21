# PbpPublic


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | 
**season** | **int** |  | 
**session** | **str** |  | 
**game_id** | **int** |  | 
**event_idx** | **int** |  | 
**period** | **int** |  | 
**period_seconds** | **int** |  | 
**game_seconds** | **int** |  | 
**strength_state** | **str** |  | [optional] 
**event_team** | **str** |  | [optional] 
**opp_team** | **str** |  | [optional] 
**event** | **str** |  | 
**description** | **str** |  | [optional] 
**zone** | **str** |  | [optional] 
**coords_x** | **float** |  | [optional] 
**coords_y** | **float** |  | [optional] 
**danger** | **int** |  | [optional] 
**high_danger** | **int** |  | [optional] 
**player_1_api_id** | **int** |  | [optional] 
**player_1_type** | **str** |  | [optional] 
**player_2_api_id** | **int** |  | [optional] 
**player_2_type** | **str** |  | [optional] 
**player_3_api_id** | **int** |  | [optional] 
**player_3_type** | **str** |  | [optional] 
**score_state** | **str** |  | [optional] 
**score_diff** | **int** |  | 
**forwards_percent** | **float** |  | 
**opp_forwards_percent** | **float** |  | 
**shot_type** | **str** |  | [optional] 
**event_length** | **int** |  | [optional] 
**event_distance** | **float** |  | [optional] 
**pbp_distance** | **float** |  | [optional] 
**event_angle** | **float** |  | [optional] 
**penalty** | **str** |  | [optional] 
**penalty_length** | **int** |  | [optional] 
**event_team_skaters** | **int** |  | [optional] 
**teammates_api_id** | **str** |  | [optional] 
**own_goalie_api_id** | **int** |  | [optional] 
**forwards_api_id** | **str** |  | [optional] 
**forwards_count** | **int** |  | [optional] 
**defense_api_id** | **str** |  | [optional] 
**defense_count** | **int** |  | [optional] 
**opp_strength_state** | **str** |  | [optional] 
**opp_score_state** | **str** |  | [optional] 
**opp_score_diff** | **int** |  | [optional] 
**opp_team_skaters** | **int** |  | [optional] 
**opp_team_on_api_id** | **str** |  | [optional] 
**opp_goalie_api_id** | **int** |  | [optional] 
**opp_forwards_api_id** | **str** |  | [optional] 
**opp_forwards_count** | **int** |  | [optional] 
**opp_defense_api_id** | **str** |  | [optional] 
**opp_defense_count** | **int** |  | [optional] 
**home_score** | **int** |  | 
**home_score_diff** | **int** |  | 
**away_score** | **int** |  | 
**away_score_diff** | **int** |  | 
**is_home** | **int** |  | 
**is_away** | **int** |  | 
**home_skaters** | **int** |  | 
**away_skaters** | **int** |  | 
**home_on_api_id** | **str** |  | [optional] 
**away_on_api_id** | **str** |  | [optional] 
**home_forwards_api_id** | **str** |  | [optional] 
**home_forwards_count** | **int** |  | [optional] 
**home_forwards_percent** | **float** |  | [optional] 
**home_defense_api_id** | **str** |  | [optional] 
**home_defense_count** | **int** |  | [optional] 
**home_goalie_api_id** | **int** |  | [optional] 
**away_forwards_api_id** | **str** |  | [optional] 
**away_forwards_count** | **int** |  | [optional] 
**away_forwards_percent** | **float** |  | [optional] 
**away_defense_api_id** | **str** |  | [optional] 
**away_defense_count** | **int** |  | [optional] 
**away_goalie_api_id** | **int** |  | [optional] 
**change_on_count** | **int** |  | [optional] 
**change_off_count** | **int** |  | [optional] 
**change_on_api_id** | **str** |  | [optional] 
**change_off_api_id** | **str** |  | [optional] 
**change_on_forwards_count** | **int** |  | [optional] 
**change_off_forwards_count** | **int** |  | [optional] 
**change_on_forwards_api_id** | **str** |  | [optional] 
**change_off_forwards_api_id** | **str** |  | [optional] 
**change_on_defense_count** | **int** |  | [optional] 
**change_off_defense_count** | **int** |  | [optional] 
**change_on_defense_api_id** | **str** |  | [optional] 
**change_off_defense_api_id** | **str** |  | [optional] 
**change_on_goalie_count** | **int** |  | [optional] 
**change_off_goalie_count** | **int** |  | [optional] 
**change_on_goalie_api_id** | **str** |  | [optional] 
**change_off_goalie_api_id** | **str** |  | [optional] 
**base_xg** | **float** |  | [optional] 
**base_xg_adj** | **float** |  | [optional] 
**context_xg** | **float** |  | [optional] 
**context_xg_adj** | **float** |  | [optional] 
**pred_goal** | **float** |  | [optional] 
**pred_goal_adj** | **float** |  | [optional] 
**goal** | **int** |  | [optional] [default to 0]
**goal_adj** | **float** |  | [optional] [default to 0]
**hd_goal** | **int** |  | [optional] [default to 0]
**shot** | **int** |  | [optional] [default to 0]
**shot_adj** | **float** |  | [optional] [default to 0]
**hd_shot** | **int** |  | [optional] [default to 0]
**miss** | **int** |  | [optional] [default to 0]
**miss_adj** | **float** |  | [optional] [default to 0]
**hd_miss** | **int** |  | [optional] [default to 0]
**fenwick** | **int** |  | [optional] [default to 0]
**fenwick_adj** | **float** |  | [optional] [default to 0]
**hd_fenwick** | **int** |  | [optional] [default to 0]
**corsi** | **int** |  | [optional] [default to 0]
**corsi_adj** | **float** |  | [optional] [default to 0]
**block** | **int** |  | [optional] [default to 0]
**block_adj** | **float** |  | [optional] [default to 0]
**teammate_block** | **int** |  | [optional] [default to 0]
**teammate_block_adj** | **float** |  | [optional] [default to 0]
**hit** | **int** |  | [optional] [default to 0]
**give** | **int** |  | [optional] [default to 0]
**take** | **int** |  | [optional] [default to 0]
**fac** | **int** |  | [optional] [default to 0]
**penl** | **int** |  | [optional] [default to 0]
**change** | **int** |  | [optional] [default to 0]
**stop** | **int** |  | [optional] [default to 0]
**chl** | **int** |  | [optional] [default to 0]
**ozf** | **int** |  | [optional] [default to 0]
**nzf** | **int** |  | [optional] [default to 0]
**dzf** | **int** |  | [optional] [default to 0]
**ozc** | **int** |  | [optional] [default to 0]
**nzc** | **int** |  | [optional] [default to 0]
**dzc** | **int** |  | [optional] [default to 0]
**otf** | **int** |  | [optional] [default to 0]
**pen0** | **int** |  | [optional] [default to 0]
**pen2** | **int** |  | [optional] [default to 0]
**pen4** | **int** |  | [optional] [default to 0]
**pen5** | **int** |  | [optional] [default to 0]
**pen10** | **int** |  | [optional] [default to 0]
**cs_version** | **str** |  | [optional] 
**shootout_attempt** | **int** |  | [optional] 
**shootout_goal** | **int** |  | [optional] 
**player** | [**PlayerPublic**](PlayerPublic.md) |  | [optional] 
**game** | [**GamePublic**](GamePublic.md) |  | [optional] 

## Example

```python
from chickenstats_api.models.pbp_public import PbpPublic

# TODO update the JSON string below
json = "{}"
# create an instance of PbpPublic from a JSON string
pbp_public_instance = PbpPublic.from_json(json)
# print the JSON string representation of the object
print(PbpPublic.to_json())

# convert the object into a dict
pbp_public_dict = pbp_public_instance.to_dict()
# create an instance of PbpPublic from a dict
pbp_public_from_dict = PbpPublic.from_dict(pbp_public_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


