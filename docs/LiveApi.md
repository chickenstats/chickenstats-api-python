# chickenstats_api.LiveApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**read_live_games**](LiveApi.md#read_live_games) | **GET** /api/v1/live/games | Read Live Games
[**read_live_pbp**](LiveApi.md#read_live_pbp) | **GET** /api/v1/live/play_by_play | Read Live Pbp


# **read_live_games**
> List[LiveGamesPublic] read_live_games()

Read Live Games

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.live_games_public import LiveGamesPublic
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
    api_instance = chickenstats_api.LiveApi(api_client)

    try:
        # Read Live Games
        api_response = api_instance.read_live_games()
        print("The response of LiveApi->read_live_games:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LiveApi->read_live_games: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**List[LiveGamesPublic]**](LiveGamesPublic.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_live_pbp**
> LivePbpResponse read_live_pbp(game_id=game_id, limit=limit, offset=offset, with_total=with_total)

Read Live Pbp

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.live_pbp_response import LivePbpResponse
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
    api_instance = chickenstats_api.LiveApi(api_client)
    game_id = [56] # List[int] |  (optional)
    limit = 10000 # int |  (optional) (default to 10000)
    offset = 0 # int |  (optional) (default to 0)
    with_total = True # bool |  (optional) (default to True)

    try:
        # Read Live Pbp
        api_response = api_instance.read_live_pbp(game_id=game_id, limit=limit, offset=offset, with_total=with_total)
        print("The response of LiveApi->read_live_pbp:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LiveApi->read_live_pbp: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **game_id** | [**List[int]**](int.md)|  | [optional] 
 **limit** | **int**|  | [optional] [default to 10000]
 **offset** | **int**|  | [optional] [default to 0]
 **with_total** | **bool**|  | [optional] [default to True]

### Return type

[**LivePbpResponse**](LivePbpResponse.md)

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

