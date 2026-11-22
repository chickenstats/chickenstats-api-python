# MfaChallenge


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**error** | **str** |  | 
**error_description** | **str** |  | 
**mfa_token** | **str** |  | 

## Example

```python
from chickenstats_api.models.mfa_challenge import MfaChallenge

# TODO update the JSON string below
json = "{}"
# create an instance of MfaChallenge from a JSON string
mfa_challenge_instance = MfaChallenge.from_json(json)
# print the JSON string representation of the object
print(MfaChallenge.to_json())

# convert the object into a dict
mfa_challenge_dict = mfa_challenge_instance.to_dict()
# create an instance of MfaChallenge from a dict
mfa_challenge_from_dict = MfaChallenge.from_dict(mfa_challenge_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


