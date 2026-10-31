# chickenstats_api.RapmApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**read_rapm**](RapmApi.md#read_rapm) | **GET** /api/v1/chicken_nhl/rapm | Read Rapm


# **read_rapm**
> RapmResponse read_rapm(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions, situation=situation, player=player, api_id=api_id, eh_id=eh_id, team=team, pos=pos)

Read Rapm

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.rapm_response import RapmResponse
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
    api_instance = chickenstats_api.RapmApi(api_client)
    limit = 56 # int | Rows per page. When omitted, 10,000 or your tier's maximum, whichever is smaller; the response's `limit` says which. A value over your tier's maximum is refused with a 400. (optional)
    offset = 0 # int |  (optional) (default to 0)
    with_total = True # bool | Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. `total` is then -1 and `has_next` still works. (optional) (default to True)
    season = [56] # List[int] |  (optional)
    sessions = ['sessions_example'] # List[str] |  (optional)
    situation = ['situation_example'] # List[str] |  (optional)
    player = ['player_example'] # List[str] |  (optional)
    api_id = [56] # List[int] |  (optional)
    eh_id = ['eh_id_example'] # List[str] |  (optional)
    team = ['team_example'] # List[str] |  (optional)
    pos = ['pos_example'] # List[str] |  (optional)

    try:
        # Read Rapm
        api_response = api_instance.read_rapm(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions, situation=situation, player=player, api_id=api_id, eh_id=eh_id, team=team, pos=pos)
        print("The response of RapmApi->read_rapm:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RapmApi->read_rapm: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| Rows per page. When omitted, 10,000 or your tier&#39;s maximum, whichever is smaller; the response&#39;s &#x60;limit&#x60; says which. A value over your tier&#39;s maximum is refused with a 400. | [optional] 
 **offset** | **int**|  | [optional] [default to 0]
 **with_total** | **bool**| Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. &#x60;total&#x60; is then -1 and &#x60;has_next&#x60; still works. | [optional] [default to True]
 **season** | [**List[int]**](int.md)|  | [optional] 
 **sessions** | [**List[str]**](str.md)|  | [optional] 
 **situation** | [**List[str]**](str.md)|  | [optional] 
 **player** | [**List[str]**](str.md)|  | [optional] 
 **api_id** | [**List[int]**](int.md)|  | [optional] 
 **eh_id** | [**List[str]**](str.md)|  | [optional] 
 **team** | [**List[str]**](str.md)|  | [optional] 
 **pos** | [**List[str]**](str.md)|  | [optional] 

### Return type

[**RapmResponse**](RapmResponse.md)

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

