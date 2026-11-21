# EmailVerified


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**message** | **str** |  | 
**password_token** | **str** |  | [optional] 

## Example

```python
from chickenstats_api.models.email_verified import EmailVerified

# TODO update the JSON string below
json = "{}"
# create an instance of EmailVerified from a JSON string
email_verified_instance = EmailVerified.from_json(json)
# print the JSON string representation of the object
print(EmailVerified.to_json())

# convert the object into a dict
email_verified_dict = email_verified_instance.to_dict()
# create an instance of EmailVerified from a dict
email_verified_from_dict = EmailVerified.from_dict(email_verified_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


