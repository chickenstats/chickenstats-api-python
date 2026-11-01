# UserPublic


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**email** | **str** |  | 
**is_active** | **bool** |  | [optional] [default to True]
**is_superuser** | **bool** |  | [optional] [default to False]
**is_contributor** | **bool** |  | [optional] [default to False]
**full_name** | **str** |  | [optional] 
**tier** | **str** |  | [optional] [default to 'free']
**id** | **str** |  | 
**tools_write** | **bool** |  | [optional] [default to False]
**cf_client_id** | **str** |  | [optional] 
**email_verified** | **bool** |  | [optional] 

## Example

```python
from chickenstats_api.models.user_public import UserPublic

# TODO update the JSON string below
json = "{}"
# create an instance of UserPublic from a JSON string
user_public_instance = UserPublic.from_json(json)
# print the JSON string representation of the object
print(UserPublic.to_json())

# convert the object into a dict
user_public_dict = user_public_instance.to_dict()
# create an instance of UserPublic from a dict
user_public_from_dict = UserPublic.from_dict(user_public_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


