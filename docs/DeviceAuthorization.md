# DeviceAuthorization


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**device_code** | **str** |  | 
**user_code** | **str** |  | 
**verification_uri** | **str** |  | 
**verification_uri_complete** | **str** |  | 
**expires_in** | **int** |  | 
**interval** | **int** |  | 

## Example

```python
from chickenstats_api.models.device_authorization import DeviceAuthorization

# TODO update the JSON string below
json = "{}"
# create an instance of DeviceAuthorization from a JSON string
device_authorization_instance = DeviceAuthorization.from_json(json)
# print the JSON string representation of the object
print(DeviceAuthorization.to_json())

# convert the object into a dict
device_authorization_dict = device_authorization_instance.to_dict()
# create an instance of DeviceAuthorization from a dict
device_authorization_from_dict = DeviceAuthorization.from_dict(device_authorization_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


