# chickenstats_api.ShiftsApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**read_shifts**](ShiftsApi.md#read_shifts) | **GET** /api/v1/chicken_nhl/shifts | Read Shifts
[**read_shifts_game_ids**](ShiftsApi.md#read_shifts_game_ids) | **GET** /api/v1/chicken_nhl/shifts/game_ids | Read Shifts Game Ids


# **read_shifts**
> ShiftsResponse read_shifts(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions, game_id=game_id, api_id=api_id, team=team, period=period, include=include)

Read Shifts

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.shifts_response import ShiftsResponse
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
    api_instance = chickenstats_api.ShiftsApi(api_client)
    limit = 56 # int | Rows per page. When omitted, 10,000 or your tier's maximum, whichever is smaller; the response's `limit` says which. A value over your tier's maximum is refused with a 400. (optional)
    offset = 0 # int |  (optional) (default to 0)
    with_total = True # bool | Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. `total` is then -1 and `has_next` still works. (optional) (default to True)
    season = [56] # List[int] |  (optional)
    sessions = ['sessions_example'] # List[str] |  (optional)
    game_id = [56] # List[int] |  (optional)
    api_id = [56] # List[int] |  (optional)
    team = ['team_example'] # List[str] |  (optional)
    period = [56] # List[int] |  (optional)
    include = ['include_example'] # List[str] |  (optional)

    try:
        # Read Shifts
        api_response = api_instance.read_shifts(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions, game_id=game_id, api_id=api_id, team=team, period=period, include=include)
        print("The response of ShiftsApi->read_shifts:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ShiftsApi->read_shifts: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| Rows per page. When omitted, 10,000 or your tier&#39;s maximum, whichever is smaller; the response&#39;s &#x60;limit&#x60; says which. A value over your tier&#39;s maximum is refused with a 400. | [optional] 
 **offset** | **int**|  | [optional] [default to 0]
 **with_total** | **bool**| Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. &#x60;total&#x60; is then -1 and &#x60;has_next&#x60; still works. | [optional] [default to True]
 **season** | [**List[int]**](int.md)|  | [optional] 
 **sessions** | [**List[str]**](str.md)|  | [optional] 
 **game_id** | [**List[int]**](int.md)|  | [optional] 
 **api_id** | [**List[int]**](int.md)|  | [optional] 
 **team** | [**List[str]**](str.md)|  | [optional] 
 **period** | [**List[int]**](int.md)|  | [optional] 
 **include** | [**List[str]**](str.md)|  | [optional] 

### Return type

[**ShiftsResponse**](ShiftsResponse.md)

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

# **read_shifts_game_ids**
> List[int] read_shifts_game_ids(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions)

Read Shifts Game Ids

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
    api_instance = chickenstats_api.ShiftsApi(api_client)
    limit = 56 # int | Rows per page. When omitted, 10,000 or your tier's maximum, whichever is smaller; the response's `limit` says which. A value over your tier's maximum is refused with a 400. (optional)
    offset = 0 # int |  (optional) (default to 0)
    with_total = True # bool | Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. `total` is then -1 and `has_next` still works. (optional) (default to True)
    season = [56] # List[int] |  (optional)
    sessions = ['sessions_example'] # List[str] |  (optional)

    try:
        # Read Shifts Game Ids
        api_response = api_instance.read_shifts_game_ids(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions)
        print("The response of ShiftsApi->read_shifts_game_ids:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ShiftsApi->read_shifts_game_ids: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| Rows per page. When omitted, 10,000 or your tier&#39;s maximum, whichever is smaller; the response&#39;s &#x60;limit&#x60; says which. A value over your tier&#39;s maximum is refused with a 400. | [optional] 
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

