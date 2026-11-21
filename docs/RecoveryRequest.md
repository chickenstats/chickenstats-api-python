# RecoveryRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**email** | **str** |  | 
**code** | **str** |  | 

## Example

```python
from chickenstats_api.models.recovery_request import RecoveryRequest

# TODO update the JSON string below
json = "{}"
# create an instance of RecoveryRequest from a JSON string
recovery_request_instance = RecoveryRequest.from_json(json)
# print the JSON string representation of the object
print(RecoveryRequest.to_json())

# convert the object into a dict
recovery_request_dict = recovery_request_instance.to_dict()
# create an instance of RecoveryRequest from a dict
recovery_request_from_dict = RecoveryRequest.from_dict(recovery_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


