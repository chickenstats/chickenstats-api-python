# PasswordRecovery


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**email** | **str** |  | 

## Example

```python
from chickenstats_api.models.password_recovery import PasswordRecovery

# TODO update the JSON string below
json = "{}"
# create an instance of PasswordRecovery from a JSON string
password_recovery_instance = PasswordRecovery.from_json(json)
# print the JSON string representation of the object
print(PasswordRecovery.to_json())

# convert the object into a dict
password_recovery_dict = password_recovery_instance.to_dict()
# create an instance of PasswordRecovery from a dict
password_recovery_from_dict = PasswordRecovery.from_dict(password_recovery_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


