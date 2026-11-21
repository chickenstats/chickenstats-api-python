# chickenstats_api.StandingsApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**read_standings**](StandingsApi.md#read_standings) | **GET** /api/v1/chicken_nhl/standings | Standings


# **read_standings**
> StandingsResponse read_standings(season=season, team=team)

Standings

### Example


```python
import chickenstats_api
from chickenstats_api.models.standings_response import StandingsResponse
from chickenstats_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.chickenstats.com
# See configuration.py for a list of all supported configuration parameters.
configuration = chickenstats_api.Configuration(
    host = "https://api.chickenstats.com"
)


# Enter a context with an instance of the API client
with chickenstats_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = chickenstats_api.StandingsApi(api_client)
    season = [56] # List[int] |  (optional)
    team = ['team_example'] # List[str] |  (optional)

    try:
        # Standings
        api_response = api_instance.read_standings(season=season, team=team)
        print("The response of StandingsApi->read_standings:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling StandingsApi->read_standings: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **season** | [**List[int]**](int.md)|  | [optional] 
 **team** | [**List[str]**](str.md)|  | [optional] 

### Return type

[**StandingsResponse**](StandingsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

