# chickenstats_api.TeamsApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**read_teams**](TeamsApi.md#read_teams) | **GET** /api/v1/chicken_nhl/teams | Teams


# **read_teams**
> TeamResponse read_teams()

Teams

### Example


```python
import chickenstats_api
from chickenstats_api.models.team_response import TeamResponse
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
    api_instance = chickenstats_api.TeamsApi(api_client)

    try:
        # Teams
        api_response = api_instance.read_teams()
        print("The response of TeamsApi->read_teams:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling TeamsApi->read_teams: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**TeamResponse**](TeamResponse.md)

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

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

