# chickenstats_api.AuthApi

All URIs are relative to *https://api.chickenstats.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**approve_device_sign_in**](AuthApi.md#approve_device_sign_in) | **POST** /api/v1/auth/device/approve | Approve a device sign-in
[**confirm_recovery**](AuthApi.md#confirm_recovery) | **POST** /api/v1/auth/recovery/confirm | Confirm a recovery sign-in
[**end_all_sessions**](AuthApi.md#end_all_sessions) | **DELETE** /api/v1/auth/sessions | Sign out everywhere
[**get_token**](AuthApi.md#get_token) | **POST** /api/v1/auth/token | Get a token
[**make_recovery_codes**](AuthApi.md#make_recovery_codes) | **POST** /api/v1/users/me/recovery-codes | Make recovery codes
[**recover_password**](AuthApi.md#recover_password) | **POST** /api/v1/password-recovery/ | Send a password reset email
[**reset_password**](AuthApi.md#reset_password) | **POST** /api/v1/reset-password/ | Reset a password
[**revoke_token**](AuthApi.md#revoke_token) | **POST** /api/v1/auth/revoke | Sign out one session
[**set_password**](AuthApi.md#set_password) | **POST** /api/v1/set-password/ | Choose a first password
[**start_device_sign_in**](AuthApi.md#start_device_sign_in) | **POST** /api/v1/auth/device | Start a device sign-in
[**use_recovery_code**](AuthApi.md#use_recovery_code) | **POST** /api/v1/auth/recovery | Sign in with a recovery code
[**verify_email**](AuthApi.md#verify_email) | **POST** /api/v1/verify-email | Verify an email address
[**whoami**](AuthApi.md#whoami) | **GET** /api/v1/auth/whoami | Who a token signs in as


# **approve_device_sign_in**
> Message approve_device_sign_in(device_approval)

Approve a device sign-in

Approve or deny the device showing this code, for the signed-in person.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.device_approval import DeviceApproval
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
    api_instance = chickenstats_api.AuthApi(api_client)
    device_approval = chickenstats_api.DeviceApproval() # DeviceApproval | 

    try:
        # Approve a device sign-in
        api_response = api_instance.approve_device_sign_in(device_approval)
        print("The response of AuthApi->approve_device_sign_in:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->approve_device_sign_in: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_approval** | [**DeviceApproval**](DeviceApproval.md)|  | 

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

# **confirm_recovery**
> Message confirm_recovery(recovery_confirm)

Confirm a recovery sign-in

Turn the account's authenticator app off and end every session.

No session needed: the emailed link is the proof. A link is spent once
the app is off, and also by any later end of the account's sessions,
since it was issued before the stamp that leaves.

### Example


```python
import chickenstats_api
from chickenstats_api.models.message import Message
from chickenstats_api.models.recovery_confirm import RecoveryConfirm
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
    api_instance = chickenstats_api.AuthApi(api_client)
    recovery_confirm = chickenstats_api.RecoveryConfirm() # RecoveryConfirm | 

    try:
        # Confirm a recovery sign-in
        api_response = api_instance.confirm_recovery(recovery_confirm)
        print("The response of AuthApi->confirm_recovery:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->confirm_recovery: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **recovery_confirm** | [**RecoveryConfirm**](RecoveryConfirm.md)|  | 

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

# **end_all_sessions**
> end_all_sessions()

Sign out everywhere

End every session on every device, this one included.

Named API tokens are left alone; revoke those at /users/me/tokens.

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
    api_instance = chickenstats_api.AuthApi(api_client)

    try:
        # Sign out everywhere
        api_instance.end_all_sessions()
    except Exception as e:
        print("Exception when calling AuthApi->end_all_sessions: %s\n" % e)
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

# **get_token**
> Token get_token(grant_type=grant_type, username=username, password=password, refresh_token=refresh_token, subject_token=subject_token, subject_token_type=subject_token_type, device_code=device_code, mfa_token=mfa_token, otp=otp, client_id=client_id, client_secret=client_secret, scope=scope)

Get a token

The OAuth 2.0 token endpoint (RFC 6749), form-encoded.

Grants: password (username, password); refresh_token; Firebase sign-in as a
token exchange (RFC 8693: subject_token, subject_token_type
urn:ietf:params:oauth:token-type:id_token); the device grant (RFC 8628:
device_code from /auth/device); and urn:chickenstats:params:oauth:grant-type:mfa-otp
(mfa_token, otp) after a password grant's mfa_required. client_id is
accepted and ignored.

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
    api_instance = chickenstats_api.AuthApi(api_client)
    grant_type = 'grant_type_example' # str |  (optional)
    username = 'username_example' # str |  (optional)
    password = 'password_example' # str |  (optional)
    refresh_token = 'refresh_token_example' # str |  (optional)
    subject_token = 'subject_token_example' # str |  (optional)
    subject_token_type = 'subject_token_type_example' # str |  (optional)
    device_code = 'device_code_example' # str |  (optional)
    mfa_token = 'mfa_token_example' # str |  (optional)
    otp = 'otp_example' # str |  (optional)
    client_id = 'client_id_example' # str |  (optional)
    client_secret = 'client_secret_example' # str |  (optional)
    scope = 'scope_example' # str |  (optional)

    try:
        # Get a token
        api_response = api_instance.get_token(grant_type=grant_type, username=username, password=password, refresh_token=refresh_token, subject_token=subject_token, subject_token_type=subject_token_type, device_code=device_code, mfa_token=mfa_token, otp=otp, client_id=client_id, client_secret=client_secret, scope=scope)
        print("The response of AuthApi->get_token:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->get_token: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **grant_type** | **str**|  | [optional] 
 **username** | **str**|  | [optional] 
 **password** | **str**|  | [optional] 
 **refresh_token** | **str**|  | [optional] 
 **subject_token** | **str**|  | [optional] 
 **subject_token_type** | **str**|  | [optional] 
 **device_code** | **str**|  | [optional] 
 **mfa_token** | **str**|  | [optional] 
 **otp** | **str**|  | [optional] 
 **client_id** | **str**|  | [optional] 
 **client_secret** | **str**|  | [optional] 
 **scope** | **str**|  | [optional] 

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
**400** | An RFC 6749 error. |  -  |
**403** | mfa_required: the account has an authenticator app. Send mfa_token and the code as otp with grant_type urn:chickenstats:params:oauth:grant-type:mfa-otp. |  -  |
**429** | Too many attempts; wait and retry. |  -  |
**503** | Firebase didn&#39;t answer; retry. A refresh token stays live. |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **make_recovery_codes**
> RecoveryCodes make_recovery_codes()

Make recovery codes

A new set of ten codes, voiding the old. They are shown this once.

Needs a sign-in in the last ten minutes, like the authenticator change it
backs up, and an authenticator app to stand in for.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.recovery_codes import RecoveryCodes
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
    api_instance = chickenstats_api.AuthApi(api_client)

    try:
        # Make recovery codes
        api_response = api_instance.make_recovery_codes()
        print("The response of AuthApi->make_recovery_codes:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->make_recovery_codes: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**RecoveryCodes**](RecoveryCodes.md)

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

# **recover_password**
> Message recover_password(password_recovery)

Send a password reset email

Always returns 200 to prevent email enumeration.

### Example


```python
import chickenstats_api
from chickenstats_api.models.message import Message
from chickenstats_api.models.password_recovery import PasswordRecovery
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
    api_instance = chickenstats_api.AuthApi(api_client)
    password_recovery = chickenstats_api.PasswordRecovery() # PasswordRecovery | 

    try:
        # Send a password reset email
        api_response = api_instance.recover_password(password_recovery)
        print("The response of AuthApi->recover_password:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->recover_password: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **password_recovery** | [**PasswordRecovery**](PasswordRecovery.md)|  | 

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

# **reset_password**
> Message reset_password(new_password)

Reset a password

Set a password with the token from the recovery email.

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
    api_instance = chickenstats_api.AuthApi(api_client)
    new_password = chickenstats_api.NewPassword() # NewPassword | 

    try:
        # Reset a password
        api_response = api_instance.reset_password(new_password)
        print("The response of AuthApi->reset_password:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->reset_password: %s\n" % e)
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

# **revoke_token**
> revoke_token(token=token, token_type_hint=token_type_hint, client_id=client_id)

Sign out one session

Revoke a token (RFC 7009).

A refresh or access token ends its session; a named API token stops working.
Always 200, even for a token that was never valid, so it reveals nothing.

### Example


```python
import chickenstats_api
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
    api_instance = chickenstats_api.AuthApi(api_client)
    token = 'token_example' # str |  (optional)
    token_type_hint = 'token_type_hint_example' # str |  (optional)
    client_id = 'client_id_example' # str |  (optional)

    try:
        # Sign out one session
        api_instance.revoke_token(token=token, token_type_hint=token_type_hint, client_id=client_id)
    except Exception as e:
        print("Exception when calling AuthApi->revoke_token: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token** | **str**|  | [optional] 
 **token_type_hint** | **str**|  | [optional] 
 **client_id** | **str**|  | [optional] 

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Revoked, or was never valid |  -  |
**400** | An RFC 6749 error. |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_password**
> Message set_password(new_password)

Choose a first password

Choose a new account's password with the token its verified address got.

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
    api_instance = chickenstats_api.AuthApi(api_client)
    new_password = chickenstats_api.NewPassword() # NewPassword | 

    try:
        # Choose a first password
        api_response = api_instance.set_password(new_password)
        print("The response of AuthApi->set_password:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->set_password: %s\n" % e)
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

# **start_device_sign_in**
> DeviceAuthorization start_device_sign_in(client_id=client_id, scope=scope)

Start a device sign-in

Sign in a machine with no browser (RFC 8628).

Show the person user_code and verification_uri, then poll /auth/token with
the device grant every `interval` seconds until they approve it.

### Example


```python
import chickenstats_api
from chickenstats_api.models.device_authorization import DeviceAuthorization
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
    api_instance = chickenstats_api.AuthApi(api_client)
    client_id = 'client_id_example' # str |  (optional)
    scope = 'scope_example' # str |  (optional)

    try:
        # Start a device sign-in
        api_response = api_instance.start_device_sign_in(client_id=client_id, scope=scope)
        print("The response of AuthApi->start_device_sign_in:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->start_device_sign_in: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **client_id** | **str**|  | [optional] 
 **scope** | **str**|  | [optional] 

### Return type

[**DeviceAuthorization**](DeviceAuthorization.md)

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

# **use_recovery_code**
> Message use_recovery_code(recovery_request)

Sign in with a recovery code

Spend a code and email the account a link that turns its app off.

The answer is _SENT whatever happens, so it never says whether the code
was right. And a code is spent only once its link has gone to the mail
server: with no mail configured it isn't tried, and a failed send rolls
the spend back, so the code still works.

### Example


```python
import chickenstats_api
from chickenstats_api.models.message import Message
from chickenstats_api.models.recovery_request import RecoveryRequest
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
    api_instance = chickenstats_api.AuthApi(api_client)
    recovery_request = chickenstats_api.RecoveryRequest() # RecoveryRequest | 

    try:
        # Sign in with a recovery code
        api_response = api_instance.use_recovery_code(recovery_request)
        print("The response of AuthApi->use_recovery_code:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->use_recovery_code: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **recovery_request** | [**RecoveryRequest**](RecoveryRequest.md)|  | 

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

# **verify_email**
> EmailVerified verify_email(email_verification)

Verify an email address

Prove an address with the code from its verification email (API-335).

No session needed: the link is the proof, and it may be opened on another
device. A session from before stays unverified, since the claim is baked
into its token and an unproven address gets no refresh token, so the
person signs in again to use the account. The code is never logged.

The announcements box on that page is the signup's opt-in, applied now
that the address is proven.

An account that has never had a session gets a token to choose its
password, and whatever password it had is replaced first: signup takes
none, and one set before the address was proven isn't the owner's to keep.

### Example


```python
import chickenstats_api
from chickenstats_api.models.email_verification import EmailVerification
from chickenstats_api.models.email_verified import EmailVerified
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
    api_instance = chickenstats_api.AuthApi(api_client)
    email_verification = chickenstats_api.EmailVerification() # EmailVerification | 

    try:
        # Verify an email address
        api_response = api_instance.verify_email(email_verification)
        print("The response of AuthApi->verify_email:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->verify_email: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **email_verification** | [**EmailVerification**](EmailVerification.md)|  | 

### Return type

[**EmailVerified**](EmailVerified.md)

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

# **whoami**
> WhoAmI whoami()

Who a token signs in as

The tier and account a session or named token reads data as.

Not metered, so checking a token costs no request, on any tier.

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import chickenstats_api
from chickenstats_api.models.who_am_i import WhoAmI
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
    api_instance = chickenstats_api.AuthApi(api_client)

    try:
        # Who a token signs in as
        api_response = api_instance.whoami()
        print("The response of AuthApi->whoami:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AuthApi->whoami: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**WhoAmI**](WhoAmI.md)

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

