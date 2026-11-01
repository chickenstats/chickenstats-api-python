# chickenstats_api.LoginApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**login_firebase_token**](LoginApi.md#login_firebase_token) | **POST** /api/v1/login/firebase-token | Login Firebase Token
[**login_refresh**](LoginApi.md#login_refresh) | **POST** /api/v1/login/refresh | Login Refresh
[**login_verify_token**](LoginApi.md#login_verify_token) | **POST** /api/v1/login/verify-token | Login Verify Token
[**recover_password**](LoginApi.md#recover_password) | **POST** /api/v1/password-recovery/{email} | Recover Password
[**recover_password_html_content**](LoginApi.md#recover_password_html_content) | **POST** /api/v1/password-recovery-html-content/{email} | Recover Password Html Content
[**reset_password**](LoginApi.md#reset_password) | **POST** /api/v1/reset-password/ | Reset Password
[**test_token**](LoginApi.md#test_token) | **POST** /api/v1/login/test-token | Test Token


# **login_firebase_token**
> Token login_firebase_token(username, password, grant_type=grant_type, scope=scope, client_id=client_id, client_secret=client_secret)

Login Firebase Token

Exchange email + password for the backend's own local session token.

For use with API data endpoints (this is the OAuth2 password-grant
tokenUrl both Swagger's "Authorize" button and API/SDK clients use).
Verifies the password against Firebase first, then mints a local token
via the same path login_verify_token uses -- see _mint_session_token's
own docstring for why this isn't Firebase's raw ID token.

### Example


```python
import chickenstats_api
from chickenstats_api.models.token import Token
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
    api_instance = chickenstats_api.LoginApi(api_client)
    username = 'username_example' # str | 
    password = 'password_example' # str | 
    grant_type = 'grant_type_example' # str |  (optional)
    scope = '' # str |  (optional) (default to '')
    client_id = 'client_id_example' # str |  (optional)
    client_secret = 'client_secret_example' # str |  (optional)

    try:
        # Login Firebase Token
        api_response = api_instance.login_firebase_token(username, password, grant_type=grant_type, scope=scope, client_id=client_id, client_secret=client_secret)
        print("The response of LoginApi->login_firebase_token:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LoginApi->login_firebase_token: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **username** | **str**|  | 
 **password** | **str**|  | 
 **grant_type** | **str**|  | [optional] 
 **scope** | **str**|  | [optional] [default to &#39;&#39;]
 **client_id** | **str**|  | [optional] 
 **client_secret** | **str**|  | [optional] 

### Return type

[**Token**](Token.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **login_refresh**
> Token login_refresh(refresh_token_request)

Login Refresh

Exchange a refresh token for a new access token, rotating the refresh token.

No Firebase round-trip -- this is the whole point (a long-running
script/CLI can stay authenticated without re-prompting for
credentials). Tier comes from a live Firebase custom-claims lookup
(_firebase_standing), same source get_current_user_tier's own
CF-service-token path already uses, since there's no fresh ID token
here to read a stripeRole claim off of directly. Rotation: the
presented refresh token is revoked and a new one issued on every
successful call, same principle as any refresh-token system -- limits
a leaked token to a single use before it stops working silently.

### Example


```python
import chickenstats_api
from chickenstats_api.models.refresh_token_request import RefreshTokenRequest
from chickenstats_api.models.token import Token
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
    api_instance = chickenstats_api.LoginApi(api_client)
    refresh_token_request = chickenstats_api.RefreshTokenRequest() # RefreshTokenRequest | 

    try:
        # Login Refresh
        api_response = api_instance.login_refresh(refresh_token_request)
        print("The response of LoginApi->login_refresh:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LoginApi->login_refresh: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **refresh_token_request** | [**RefreshTokenRequest**](RefreshTokenRequest.md)|  | 

### Return type

[**Token**](Token.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **login_verify_token**
> Token login_verify_token(id_token)

Login Verify Token

Exchange a Firebase ID token for a local session token.

Takes a client-obtained Firebase ID token (e.g. from "Sign in with Google") and
returns a local HS256 session token for the FastHTML frontend's session cookie.

### Example


```python
import chickenstats_api
from chickenstats_api.models.id_token import IdToken
from chickenstats_api.models.token import Token
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
    api_instance = chickenstats_api.LoginApi(api_client)
    id_token = chickenstats_api.IdToken() # IdToken | 

    try:
        # Login Verify Token
        api_response = api_instance.login_verify_token(id_token)
        print("The response of LoginApi->login_verify_token:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LoginApi->login_verify_token: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id_token** | [**IdToken**](IdToken.md)|  | 

### Return type

[**Token**](Token.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **recover_password**
> Message recover_password(email)

Recover Password

Always returns 200 to prevent email enumeration.

### Example


```python
import chickenstats_api
from chickenstats_api.models.message import Message
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
    api_instance = chickenstats_api.LoginApi(api_client)
    email = 'email_example' # str | 

    try:
        # Recover Password
        api_response = api_instance.recover_password(email)
        print("The response of LoginApi->recover_password:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LoginApi->recover_password: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **email** | **str**|  | 

### Return type

[**Message**](Message.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **recover_password_html_content**
> str recover_password_html_content(email)

Recover Password Html Content

HTML Content for Password Recovery.

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
    api_instance = chickenstats_api.LoginApi(api_client)
    email = 'email_example' # str | 

    try:
        # Recover Password Html Content
        api_response = api_instance.recover_password_html_content(email)
        print("The response of LoginApi->recover_password_html_content:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LoginApi->recover_password_html_content: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **email** | **str**|  | 

### Return type

**str**

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/html, application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **reset_password**
> Message reset_password(new_password)

Reset Password

Reset password using the token from the recovery email.

### Example


```python
import chickenstats_api
from chickenstats_api.models.message import Message
from chickenstats_api.models.new_password import NewPassword
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
    api_instance = chickenstats_api.LoginApi(api_client)
    new_password = chickenstats_api.NewPassword() # NewPassword | 

    try:
        # Reset Password
        api_response = api_instance.reset_password(new_password)
        print("The response of LoginApi->reset_password:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LoginApi->reset_password: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **new_password** | [**NewPassword**](NewPassword.md)|  | 

### Return type

[**Message**](Message.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **test_token**
> UserPublic test_token()

Test Token

Test access token.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.user_public import UserPublic
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
    api_instance = chickenstats_api.LoginApi(api_client)

    try:
        # Test Token
        api_response = api_instance.test_token()
        print("The response of LoginApi->test_token:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LoginApi->test_token: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**UserPublic**](UserPublic.md)

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

