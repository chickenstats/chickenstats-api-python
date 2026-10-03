# chickenstats_api.StatsApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**read_game_stats**](StatsApi.md#read_game_stats) | **GET** /api/v1/chicken_nhl/stats/game | Read Game Stats
[**read_season_stats**](StatsApi.md#read_season_stats) | **GET** /api/v1/chicken_nhl/stats/season | Read Season Stats
[**read_stats_game_ids**](StatsApi.md#read_stats_game_ids) | **GET** /api/v1/chicken_nhl/stats/game_ids | Read Stats Game Ids


# **read_game_stats**
> StatsGameResponse read_game_stats(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions, game_id=game_id, level=level, player=player, api_id=api_id, eh_id=eh_id, team=team, opp_team=opp_team, strength_state=strength_state, score_state=score_state, teammates=teammates, opposition=opposition, include=include)

Read Game Stats

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.stats_game_response import StatsGameResponse
from chickenstats_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.chickenstats.com
# See configuration.py for a list of all supported configuration parameters.
configuration = chickenstats_api.Configuration(
    host = "https://api.chickenstats.com"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

configuration.access_token = os.environ["ACCESS_TOKEN"]

# Enter a context with an instance of the API client
with chickenstats_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = chickenstats_api.StatsApi(api_client)
    limit = 10000 # int |  (optional) (default to 10000)
    offset = 0 # int |  (optional) (default to 0)
    with_total = True # bool | Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. `total` is then -1 and `has_next` still works. (optional) (default to True)
    season = [56] # List[int] |  (optional)
    sessions = ['sessions_example'] # List[str] |  (optional)
    game_id = [56] # List[int] |  (optional)
    level = 'level_example' # str |  (optional)
    player = ['player_example'] # List[str] |  (optional)
    api_id = [56] # List[int] |  (optional)
    eh_id = ['eh_id_example'] # List[str] |  (optional)
    team = ['team_example'] # List[str] |  (optional)
    opp_team = ['opp_team_example'] # List[str] |  (optional)
    strength_state = ['strength_state_example'] # List[str] |  (optional)
    score_state = True # bool |  (optional)
    teammates = True # bool |  (optional)
    opposition = True # bool |  (optional)
    include = ['include_example'] # List[str] |  (optional)

    try:
        # Read Game Stats
        api_response = api_instance.read_game_stats(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions, game_id=game_id, level=level, player=player, api_id=api_id, eh_id=eh_id, team=team, opp_team=opp_team, strength_state=strength_state, score_state=score_state, teammates=teammates, opposition=opposition, include=include)
        print("The response of StatsApi->read_game_stats:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling StatsApi->read_game_stats: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**|  | [optional] [default to 10000]
 **offset** | **int**|  | [optional] [default to 0]
 **with_total** | **bool**| Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. &#x60;total&#x60; is then -1 and &#x60;has_next&#x60; still works. | [optional] [default to True]
 **season** | [**List[int]**](int.md)|  | [optional] 
 **sessions** | [**List[str]**](str.md)|  | [optional] 
 **game_id** | [**List[int]**](int.md)|  | [optional] 
 **level** | **str**|  | [optional] 
 **player** | [**List[str]**](str.md)|  | [optional] 
 **api_id** | [**List[int]**](int.md)|  | [optional] 
 **eh_id** | [**List[str]**](str.md)|  | [optional] 
 **team** | [**List[str]**](str.md)|  | [optional] 
 **opp_team** | [**List[str]**](str.md)|  | [optional] 
 **strength_state** | [**List[str]**](str.md)|  | [optional] 
 **score_state** | **bool**|  | [optional] 
 **teammates** | **bool**|  | [optional] 
 **opposition** | **bool**|  | [optional] 
 **include** | [**List[str]**](str.md)|  | [optional] 

### Return type

[**StatsGameResponse**](StatsGameResponse.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_season_stats**
> StatsSeasonResponse read_season_stats(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions, player=player, api_id=api_id, eh_id=eh_id, team=team, opp_team=opp_team, strength_state=strength_state, score_state=score_state, teammates=teammates, opposition=opposition, include=include)

Read Season Stats

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.stats_season_response import StatsSeasonResponse
from chickenstats_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.chickenstats.com
# See configuration.py for a list of all supported configuration parameters.
configuration = chickenstats_api.Configuration(
    host = "https://api.chickenstats.com"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

configuration.access_token = os.environ["ACCESS_TOKEN"]

# Enter a context with an instance of the API client
with chickenstats_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = chickenstats_api.StatsApi(api_client)
    limit = 10000 # int |  (optional) (default to 10000)
    offset = 0 # int |  (optional) (default to 0)
    with_total = True # bool | Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. `total` is then -1 and `has_next` still works. (optional) (default to True)
    season = [56] # List[int] |  (optional)
    sessions = ['sessions_example'] # List[str] |  (optional)
    player = ['player_example'] # List[str] |  (optional)
    api_id = [56] # List[int] |  (optional)
    eh_id = ['eh_id_example'] # List[str] |  (optional)
    team = ['team_example'] # List[str] |  (optional)
    opp_team = ['opp_team_example'] # List[str] |  (optional)
    strength_state = ['strength_state_example'] # List[str] |  (optional)
    score_state = True # bool |  (optional)
    teammates = True # bool |  (optional)
    opposition = True # bool |  (optional)
    include = ['include_example'] # List[str] |  (optional)

    try:
        # Read Season Stats
        api_response = api_instance.read_season_stats(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions, player=player, api_id=api_id, eh_id=eh_id, team=team, opp_team=opp_team, strength_state=strength_state, score_state=score_state, teammates=teammates, opposition=opposition, include=include)
        print("The response of StatsApi->read_season_stats:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling StatsApi->read_season_stats: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**|  | [optional] [default to 10000]
 **offset** | **int**|  | [optional] [default to 0]
 **with_total** | **bool**| Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. &#x60;total&#x60; is then -1 and &#x60;has_next&#x60; still works. | [optional] [default to True]
 **season** | [**List[int]**](int.md)|  | [optional] 
 **sessions** | [**List[str]**](str.md)|  | [optional] 
 **player** | [**List[str]**](str.md)|  | [optional] 
 **api_id** | [**List[int]**](int.md)|  | [optional] 
 **eh_id** | [**List[str]**](str.md)|  | [optional] 
 **team** | [**List[str]**](str.md)|  | [optional] 
 **opp_team** | [**List[str]**](str.md)|  | [optional] 
 **strength_state** | [**List[str]**](str.md)|  | [optional] 
 **score_state** | **bool**|  | [optional] 
 **teammates** | **bool**|  | [optional] 
 **opposition** | **bool**|  | [optional] 
 **include** | [**List[str]**](str.md)|  | [optional] 

### Return type

[**StatsSeasonResponse**](StatsSeasonResponse.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_stats_game_ids**
> List[int] read_stats_game_ids(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions)

Read Stats Game Ids

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.chickenstats.com
# See configuration.py for a list of all supported configuration parameters.
configuration = chickenstats_api.Configuration(
    host = "https://api.chickenstats.com"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

configuration.access_token = os.environ["ACCESS_TOKEN"]

# Enter a context with an instance of the API client
with chickenstats_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = chickenstats_api.StatsApi(api_client)
    limit = 10000 # int |  (optional) (default to 10000)
    offset = 0 # int |  (optional) (default to 0)
    with_total = True # bool | Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. `total` is then -1 and `has_next` still works. (optional) (default to True)
    season = [56] # List[int] |  (optional)
    sessions = ['sessions_example'] # List[str] |  (optional)

    try:
        # Read Stats Game Ids
        api_response = api_instance.read_stats_game_ids(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions)
        print("The response of StatsApi->read_stats_game_ids:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling StatsApi->read_stats_game_ids: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**|  | [optional] [default to 10000]
 **offset** | **int**|  | [optional] [default to 0]
 **with_total** | **bool**| Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. &#x60;total&#x60; is then -1 and &#x60;has_next&#x60; still works. | [optional] [default to True]
 **season** | [**List[int]**](int.md)|  | [optional] 
 **sessions** | [**List[str]**](str.md)|  | [optional] 

### Return type

**List[int]**

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

