# UserUpdateMe


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**full_name** | **str** |  | [optional] 

## Example

```python
from chickenstats_api.models.user_update_me import UserUpdateMe

# TODO update the JSON string below
json = "{}"
# create an instance of UserUpdateMe from a JSON string
user_update_me_instance = UserUpdateMe.from_json(json)
# print the JSON string representation of the object
print(UserUpdateMe.to_json())

# convert the object into a dict
user_update_me_dict = user_update_me_instance.to_dict()
# create an instance of UserUpdateMe from a dict
user_update_me_from_dict = UserUpdateMe.from_dict(user_update_me_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


