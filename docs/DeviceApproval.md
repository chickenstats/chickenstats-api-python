# DeviceApproval


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**user_code** | **str** |  | 
**approve** | **bool** |  | 

## Example

```python
from chickenstats_api.models.device_approval import DeviceApproval

# TODO update the JSON string below
json = "{}"
# create an instance of DeviceApproval from a JSON string
device_approval_instance = DeviceApproval.from_json(json)
# print the JSON string representation of the object
print(DeviceApproval.to_json())

# convert the object into a dict
device_approval_dict = device_approval_instance.to_dict()
# create an instance of DeviceApproval from a dict
device_approval_from_dict = DeviceApproval.from_dict(device_approval_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


