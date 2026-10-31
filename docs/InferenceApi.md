# chickenstats_api.InferenceApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**read_pred_goal**](InferenceApi.md#read_pred_goal) | **GET** /api/v1/inference/pred_goal | Read Pred Goal


# **read_pred_goal**
> PredGoalResponse read_pred_goal(game_id=game_id, season=season, sessions=sessions, limit=limit, offset=offset, with_total=with_total)

Read Pred Goal

Pre-computed pred_goal values from pbpcs for shot/miss/goal events.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.pred_goal_response import PredGoalResponse
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
    api_instance = chickenstats_api.InferenceApi(api_client)
    game_id = [56] # List[int] |  (optional)
    season = [56] # List[int] |  (optional)
    sessions = ['sessions_example'] # List[str] |  (optional)
    limit = 56 # int | Rows per page. When omitted, 10,000 or your tier's maximum, whichever is smaller; the response's `limit` says which. A value over your tier's maximum is refused with a 400. (optional)
    offset = 0 # int |  (optional) (default to 0)
    with_total = True # bool |  (optional) (default to True)

    try:
        # Read Pred Goal
        api_response = api_instance.read_pred_goal(game_id=game_id, season=season, sessions=sessions, limit=limit, offset=offset, with_total=with_total)
        print("The response of InferenceApi->read_pred_goal:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling InferenceApi->read_pred_goal: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **game_id** | [**List[int]**](int.md)|  | [optional] 
 **season** | [**List[int]**](int.md)|  | [optional] 
 **sessions** | [**List[str]**](str.md)|  | [optional] 
 **limit** | **int**| Rows per page. When omitted, 10,000 or your tier&#39;s maximum, whichever is smaller; the response&#39;s &#x60;limit&#x60; says which. A value over your tier&#39;s maximum is refused with a 400. | [optional] 
 **offset** | **int**|  | [optional] [default to 0]
 **with_total** | **bool**|  | [optional] [default to True]

### Return type

[**PredGoalResponse**](PredGoalResponse.md)

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

