# chickenstats_api.UsersApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**authenticator_changed**](UsersApi.md#authenticator_changed) | **POST** /api/v1/users/me/authenticator/changed | Record an authenticator change
[**confirm_email_change**](UsersApi.md#confirm_email_change) | **POST** /api/v1/users/email/confirm | Confirm an email change
[**create_api_token**](UsersApi.md#create_api_token) | **POST** /api/v1/users/me/tokens | Make an API token
[**delete_sign_in_method**](UsersApi.md#delete_sign_in_method) | **DELETE** /api/v1/users/me/sign-in-methods/{provider} | Remove a sign-in method
[**delete_user_me**](UsersApi.md#delete_user_me) | **DELETE** /api/v1/users/me | Delete your account
[**list_api_tokens**](UsersApi.md#list_api_tokens) | **GET** /api/v1/users/me/tokens | Your API tokens
[**read_link_token**](UsersApi.md#read_link_token) | **POST** /api/v1/users/me/sign-in-methods/link-token | Start linking a sign-in method
[**read_newsletter**](UsersApi.md#read_newsletter) | **GET** /api/v1/users/me/newsletter | Newsletter preference
[**read_sign_in_methods**](UsersApi.md#read_sign_in_methods) | **GET** /api/v1/users/me/sign-in-methods | Your sign-in methods
[**read_usage**](UsersApi.md#read_usage) | **GET** /api/v1/users/me/usage | Your usage this month
[**read_user_me**](UsersApi.md#read_user_me) | **GET** /api/v1/users/me | Your account
[**request_email_change**](UsersApi.md#request_email_change) | **POST** /api/v1/users/me/email | Change your email
[**resend_verification**](UsersApi.md#resend_verification) | **POST** /api/v1/users/me/resend-verification | Resend the verification email
[**revoke_all_api_tokens**](UsersApi.md#revoke_all_api_tokens) | **DELETE** /api/v1/users/me/tokens | Revoke every API token
[**revoke_api_token**](UsersApi.md#revoke_api_token) | **DELETE** /api/v1/users/me/tokens/{token_id} | Revoke an API token
[**signup**](UsersApi.md#signup) | **POST** /api/v1/users/signup | Sign up
[**update_newsletter**](UsersApi.md#update_newsletter) | **PATCH** /api/v1/users/me/newsletter | Change newsletter preference
[**update_password_me**](UsersApi.md#update_password_me) | **PATCH** /api/v1/users/me/password | Change your password
[**update_user_me**](UsersApi.md#update_user_me) | **PATCH** /api/v1/users/me | Update your account


# **authenticator_changed**
> Token authenticator_changed()

Record an authenticator change

End the other sessions after an authenticator app goes on or off.

The browser turns the app on or off with Firebase directly, then calls
this. Every session ends, ours and Firebase's, so a device that signed in
before the change has to sign in again under the new rule. The caller gets
a new token with the same claims and expiry as the one it sent, in a
session of its own so signing out still ends it, which is what keeps this
browser signed in. It needs a sign-in in the last ten minutes, as the
change itself does.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

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

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

configuration.access_token = os.environ["ACCESS_TOKEN"]

# Enter a context with an instance of the API client
with chickenstats_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = chickenstats_api.UsersApi(api_client)

    try:
        # Record an authenticator change
        api_response = api_instance.authenticator_changed()
        print("The response of UsersApi->authenticator_changed:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->authenticator_changed: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**Token**](Token.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **confirm_email_change**
> Message confirm_email_change(email_change_confirm)

Confirm an email change

Move the account to the address the link was sent to.

No session needed: the link is the proof, and it may be opened on another
device. It names the address the account had, so it is spent once the
change is made, and a later change makes an older link useless.

Stripe, then Firebase, then Postgres, and each step is undone if a later
one fails: an account whose three addresses disagree cannot sign in, buy
or open its portal. Firebase keeps its uid, so the stripeRole claim comes
along; the user row keeps its id, so contributor flags, the service token
and refresh-token ownership do too. Usage rows are re-keyed in the same
commit as the address.

### Example


```python
import chickenstats_api
from chickenstats_api.models.email_change_confirm import EmailChangeConfirm
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
    api_instance = chickenstats_api.UsersApi(api_client)
    email_change_confirm = chickenstats_api.EmailChangeConfirm() # EmailChangeConfirm | 

    try:
        # Confirm an email change
        api_response = api_instance.confirm_email_change(email_change_confirm)
        print("The response of UsersApi->confirm_email_change:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->confirm_email_change: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **email_change_confirm** | [**EmailChangeConfirm**](EmailChangeConfirm.md)|  | 

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
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_api_token**
> ApiTokenCreated create_api_token(api_token_create)

Make an API token

A named token for scripts, the SDKs and chickenstats, shown this once.

It reads data with your live tier and nothing else: it can't manage the
account or make another token. It lasts until revoked, or expires_in_days.
It needs a sign-in in the last ten minutes, so a stolen session can't
leave a token behind that outlives it.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.api_token_create import ApiTokenCreate
from chickenstats_api.models.api_token_created import ApiTokenCreated
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
    api_instance = chickenstats_api.UsersApi(api_client)
    api_token_create = chickenstats_api.ApiTokenCreate() # ApiTokenCreate | 

    try:
        # Make an API token
        api_response = api_instance.create_api_token(api_token_create)
        print("The response of UsersApi->create_api_token:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->create_api_token: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **api_token_create** | [**ApiTokenCreate**](ApiTokenCreate.md)|  | 

### Return type

[**ApiTokenCreated**](ApiTokenCreated.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_sign_in_method**
> Message delete_sign_in_method(provider)

Remove a sign-in method

Remove a way in, unless it is the last one.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

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

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

configuration.access_token = os.environ["ACCESS_TOKEN"]

# Enter a context with an instance of the API client
with chickenstats_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = chickenstats_api.UsersApi(api_client)
    provider = 'provider_example' # str | 

    try:
        # Remove a sign-in method
        api_response = api_instance.delete_sign_in_method(provider)
        print("The response of UsersApi->delete_sign_in_method:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->delete_sign_in_method: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **provider** | **str**|  | 

### Return type

[**Message**](Message.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

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

# **delete_user_me**
> Message delete_user_me()

Delete your account

Delete own account everywhere, ending any subscription now (see _purge).

Only just after a sign-in: a stolen session could otherwise end a
subscription and an account that can't be brought back.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

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

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

configuration.access_token = os.environ["ACCESS_TOKEN"]

# Enter a context with an instance of the API client
with chickenstats_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = chickenstats_api.UsersApi(api_client)

    try:
        # Delete your account
        api_response = api_instance.delete_user_me()
        print("The response of UsersApi->delete_user_me:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->delete_user_me: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**Message**](Message.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_api_tokens**
> List[ApiTokenPublic] list_api_tokens()

Your API tokens

Your named tokens, newest first. The tokens themselves are never shown again.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.api_token_public import ApiTokenPublic
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
    api_instance = chickenstats_api.UsersApi(api_client)

    try:
        # Your API tokens
        api_response = api_instance.list_api_tokens()
        print("The response of UsersApi->list_api_tokens:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->list_api_tokens: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**List[ApiTokenPublic]**](ApiTokenPublic.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_link_token**
> LinkToken read_link_token()

Start linking a sign-in method

A Firebase custom token, for the account page to add a method with.

Verified accounts only: otherwise someone holding an unproven address could
attach their own Google or GitHub to it before its owner arrives. And only
just after a sign-in, so a stolen session can't add a way in of its own.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.link_token import LinkToken
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
    api_instance = chickenstats_api.UsersApi(api_client)

    try:
        # Start linking a sign-in method
        api_response = api_instance.read_link_token()
        print("The response of UsersApi->read_link_token:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->read_link_token: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**LinkToken**](LinkToken.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_newsletter**
> Newsletters read_newsletter()

Newsletter preference

Which newsletters this account gets, as Ghost has it now.

The paid one needs Ghost's paid access: bought from Ghost itself, or
given with Pro, Elite, a contributor or a superuser account.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.newsletters import Newsletters
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
    api_instance = chickenstats_api.UsersApi(api_client)

    try:
        # Newsletter preference
        api_response = api_instance.read_newsletter()
        print("The response of UsersApi->read_newsletter:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->read_newsletter: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**Newsletters**](Newsletters.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_sign_in_methods**
> SignInMethods read_sign_in_methods()

Your sign-in methods

The ways into this account (API-172).

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.sign_in_methods import SignInMethods
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
    api_instance = chickenstats_api.UsersApi(api_client)

    try:
        # Your sign-in methods
        api_response = api_instance.read_sign_in_methods()
        print("The response of UsersApi->read_sign_in_methods:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->read_sign_in_methods: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**SignInMethods**](SignInMethods.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_usage**
> Usage read_usage()

Your usage this month

Data requests counted so far this month, against the tier's allowance.

The same count the quota checks, so the account page and the X-Quota
headers can't disagree.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.usage import Usage
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
    api_instance = chickenstats_api.UsersApi(api_client)

    try:
        # Your usage this month
        api_response = api_instance.read_usage()
        print("The response of UsersApi->read_usage:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->read_usage: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**Usage**](Usage.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_user_me**
> UserPublic read_user_me()

Your account

Get current user, with the tier they have now and whether they are verified.

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
    api_instance = chickenstats_api.UsersApi(api_client)

    try:
        # Your account
        api_response = api_instance.read_user_me()
        print("The response of UsersApi->read_user_me:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->read_user_me: %s\n" % e)
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
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **request_email_change**
> Message request_email_change(email_change_request)

Change your email

Email a link to a new address; the change happens when it is clicked.

Nothing moves here. The address is the account's identity in Firebase,
Stripe and the quota, so it changes only once the new one has proved it
receives mail (API-20, BR-03). A verified account only: an unproven
address has no claim to hand on. And a recent sign-in, since the link
goes to an address whoever asks chooses.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.email_change_request import EmailChangeRequest
from chickenstats_api.models.message import Message
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
    api_instance = chickenstats_api.UsersApi(api_client)
    email_change_request = chickenstats_api.EmailChangeRequest() # EmailChangeRequest | 

    try:
        # Change your email
        api_response = api_instance.request_email_change(email_change_request)
        print("The response of UsersApi->request_email_change:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->request_email_change: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **email_change_request** | [**EmailChangeRequest**](EmailChangeRequest.md)|  | 

### Return type

[**Message**](Message.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **resend_verification**
> Message resend_verification()

Resend the verification email

Trigger Firebase to resend the verification email.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

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

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

configuration.access_token = os.environ["ACCESS_TOKEN"]

# Enter a context with an instance of the API client
with chickenstats_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = chickenstats_api.UsersApi(api_client)

    try:
        # Resend the verification email
        api_response = api_instance.resend_verification()
        print("The response of UsersApi->resend_verification:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->resend_verification: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**Message**](Message.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **revoke_all_api_tokens**
> revoke_all_api_tokens()

Revoke every API token

Stop every named token at once. Sessions are left signed in.

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
    api_instance = chickenstats_api.UsersApi(api_client)

    try:
        # Revoke every API token
        api_instance.revoke_all_api_tokens()
    except Exception as e:
        print("Exception when calling UsersApi->revoke_all_api_tokens: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **revoke_api_token**
> revoke_api_token(token_id)

Revoke an API token

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
    api_instance = chickenstats_api.UsersApi(api_client)
    token_id = 'token_id_example' # str | 

    try:
        # Revoke an API token
        api_instance.revoke_api_token(token_id)
    except Exception as e:
        print("Exception when calling UsersApi->revoke_api_token: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token_id** | **str**|  | 

### Return type

void (empty response body)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **signup**
> Message signup(user_register)

Sign up

Public self-registration. Creates a local user, a Firebase user, and a Ghost member.

The reply is the same whether or not the address already has an account,
so signup cannot be used to learn who has one (API-246). A taken address
is left as it is; its owner can sign in or reset the password.

It takes no password (API-316). The Firebase account gets a random one
nobody knows, and the person chooses theirs once the verification link
has proven the address (POST /verify-email). Taken at signup, a
squatter's password became a working way into the real owner's account
the moment the owner clicked the link.

Every account is a newsletter member, which keeps access in step. It gets
email only once the address is proven, and only if the person asked to
there; the signup box, off by default, only ticks that one ahead.

An address that already has a row is refused, active or not (changed
2026-10-17). Signing up over a deactivated account used to reset its
password and re-enable it for whoever asked, keeping its flags, its
service credentials and its Stripe portal. Reactivation is an admin
action now (PATCH /users/{id} with is_active).

The accounts are made after the reply (API-316). Made before it, only a
new address waited on Firebase and the mail, so the time the reply took
said what the words didn't.

An address with a Firebase account but no row is a deleted account if that
Firebase account is disabled, which is what deleting left behind before
it deleted the Firebase user too (API-233). That account is deleted and
made again, so the new one starts unverified and with no claims; enabling
it handed the newcomer the old owner's verified flag. An enabled one
belongs to someone, so it is refused rather than having its password
changed.

### Example


```python
import chickenstats_api
from chickenstats_api.models.message import Message
from chickenstats_api.models.user_register import UserRegister
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
    api_instance = chickenstats_api.UsersApi(api_client)
    user_register = chickenstats_api.UserRegister() # UserRegister | 

    try:
        # Sign up
        api_response = api_instance.signup(user_register)
        print("The response of UsersApi->signup:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->signup: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_register** | [**UserRegister**](UserRegister.md)|  | 

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
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_newsletter**
> Newsletters update_newsletter(newsletter_preference)

Change newsletter preference

Turn each newsletter on or off. Membership itself stays either way.

Verified accounts only, so nobody can sign up someone else's address.
The paid one is left off for an account without paid access.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.newsletter_preference import NewsletterPreference
from chickenstats_api.models.newsletters import Newsletters
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
    api_instance = chickenstats_api.UsersApi(api_client)
    newsletter_preference = chickenstats_api.NewsletterPreference() # NewsletterPreference | 

    try:
        # Change newsletter preference
        api_response = api_instance.update_newsletter(newsletter_preference)
        print("The response of UsersApi->update_newsletter:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->update_newsletter: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **newsletter_preference** | [**NewsletterPreference**](NewsletterPreference.md)|  | 

### Return type

[**Newsletters**](Newsletters.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_password_me**
> Message update_password_me(update_password)

Change your password

Update own password in Firebase. Verifies current password against Firebase before changing.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.message import Message
from chickenstats_api.models.update_password import UpdatePassword
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
    api_instance = chickenstats_api.UsersApi(api_client)
    update_password = chickenstats_api.UpdatePassword() # UpdatePassword | 

    try:
        # Change your password
        api_response = api_instance.update_password_me(update_password)
        print("The response of UsersApi->update_password_me:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->update_password_me: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **update_password** | [**UpdatePassword**](UpdatePassword.md)|  | 

### Return type

[**Message**](Message.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_user_me**
> UserPublic update_user_me(user_update_me)

Update your account

Update own user. The email address cannot be changed here.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.user_public import UserPublic
from chickenstats_api.models.user_update_me import UserUpdateMe
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
    api_instance = chickenstats_api.UsersApi(api_client)
    user_update_me = chickenstats_api.UserUpdateMe() # UserUpdateMe | 

    try:
        # Update your account
        api_response = api_instance.update_user_me(user_update_me)
        print("The response of UsersApi->update_user_me:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->update_user_me: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_update_me** | [**UserUpdateMe**](UserUpdateMe.md)|  | 

### Return type

[**UserPublic**](UserPublic.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | No token, or an expired or revoked one: error_description is token_expired (refresh), token_revoked (sign in again), recent_sign_in_required (sign in again for this change), or named_token_expired or named_token_revoked (make a new API token). |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

