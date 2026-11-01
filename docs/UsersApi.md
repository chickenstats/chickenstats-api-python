# chickenstats_api.UsersApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**confirm_email_change**](UsersApi.md#confirm_email_change) | **POST** /api/v1/users/email/confirm | Confirm Email Change
[**delete_sign_in_method**](UsersApi.md#delete_sign_in_method) | **DELETE** /api/v1/users/me/sign-in-methods/{provider} | Delete Sign In Method
[**delete_user_me**](UsersApi.md#delete_user_me) | **DELETE** /api/v1/users/me | Delete User Me
[**get_programmatic_credentials**](UsersApi.md#get_programmatic_credentials) | **GET** /api/v1/users/me/programmatic-credentials | Get Programmatic Credentials
[**read_link_token**](UsersApi.md#read_link_token) | **POST** /api/v1/users/me/sign-in-methods/link-token | Read Link Token
[**read_sign_in_methods**](UsersApi.md#read_sign_in_methods) | **GET** /api/v1/users/me/sign-in-methods | Read Sign In Methods
[**read_user_me**](UsersApi.md#read_user_me) | **GET** /api/v1/users/me | Read User Me
[**request_email_change**](UsersApi.md#request_email_change) | **POST** /api/v1/users/me/email | Request Email Change
[**resend_verification**](UsersApi.md#resend_verification) | **POST** /api/v1/users/me/resend-verification | Resend Verification
[**rotate_programmatic_credentials**](UsersApi.md#rotate_programmatic_credentials) | **POST** /api/v1/users/me/programmatic-credentials/rotate | Rotate Programmatic Credentials
[**signup**](UsersApi.md#signup) | **POST** /api/v1/users/signup | Signup
[**update_password_me**](UsersApi.md#update_password_me) | **PATCH** /api/v1/users/me/password | Update Password Me
[**update_user_me**](UsersApi.md#update_user_me) | **PATCH** /api/v1/users/me | Update User Me


# **confirm_email_change**
> Message confirm_email_change(email_change_confirm)

Confirm Email Change

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
        # Confirm Email Change
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
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_sign_in_method**
> Message delete_sign_in_method(provider)

Delete Sign In Method

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
        # Delete Sign In Method
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
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_user_me**
> Message delete_user_me()

Delete User Me

Delete own user and disable Firebase account.

Refused while the account has a live Stripe subscription: deleting it left
the subscription billing and took away the portal it is cancelled from.

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
        # Delete User Me
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

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_programmatic_credentials**
> ProgrammaticCredentials get_programmatic_credentials()

Get Programmatic Credentials

Return the CF client ID for programmatic access. The secret is never retrievable —.

rotate credentials if the secret was lost.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.programmatic_credentials import ProgrammaticCredentials
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
        # Get Programmatic Credentials
        api_response = api_instance.get_programmatic_credentials()
        print("The response of UsersApi->get_programmatic_credentials:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->get_programmatic_credentials: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**ProgrammaticCredentials**](ProgrammaticCredentials.md)

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

# **read_link_token**
> LinkToken read_link_token()

Read Link Token

A Firebase custom token, for the account page to add a method with.

Verified accounts only: otherwise someone holding an unproven address could
attach their own Google or GitHub to it before its owner arrives.

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
        # Read Link Token
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

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_sign_in_methods**
> SignInMethods read_sign_in_methods()

Read Sign In Methods

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
        # Read Sign In Methods
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

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_user_me**
> UserPublic read_user_me()

Read User Me

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
        # Read User Me
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

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **request_email_change**
> Message request_email_change(email_change_request)

Request Email Change

Email a link to a new address; the change happens when it is clicked.

Nothing moves here. The address is the account's identity in Firebase,
Stripe and the quota, so it changes only once the new one has proved it
receives mail (API-20, BR-03). A verified account only: an unproven
address has no claim to hand on.

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
        # Request Email Change
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
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **resend_verification**
> Message resend_verification()

Resend Verification

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
        # Resend Verification
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

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **rotate_programmatic_credentials**
> ProgrammaticCredentials rotate_programmatic_credentials()

Rotate Programmatic Credentials

Delete the existing CF service token and issue a new one. The new secret is.

returned once in the response and optionally emailed. Store it immediately.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.programmatic_credentials import ProgrammaticCredentials
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
        # Rotate Programmatic Credentials
        api_response = api_instance.rotate_programmatic_credentials()
        print("The response of UsersApi->rotate_programmatic_credentials:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UsersApi->rotate_programmatic_credentials: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**ProgrammaticCredentials**](ProgrammaticCredentials.md)

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

# **signup**
> UserPublic signup(user_register)

Signup

Public self-registration. Creates a local user, a Firebase user, and a Ghost member.

An address that already has a row is refused, active or not (changed
2026-10-17). Signing up over a deactivated account used to reset its
password and re-enable it for whoever asked, keeping its flags, its
service credentials and its Stripe portal. Reactivation is an admin
action now (PATCH /users/{id} with is_active).

An address with a Firebase account but no row is a deleted account if that
Firebase account is disabled, which is what deleting leaves behind: it is
given the new password and enabled again, so the address can be used once
more. An enabled one belongs to someone, so it is refused rather than
having its password changed.

### Example


```python
import chickenstats_api
from chickenstats_api.models.user_public import UserPublic
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
        # Signup
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

[**UserPublic**](UserPublic.md)

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

# **update_password_me**
> Message update_password_me(update_password)

Update Password Me

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
        # Update Password Me
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
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_user_me**
> UserPublic update_user_me(user_update_me)

Update User Me

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
        # Update User Me
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
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

