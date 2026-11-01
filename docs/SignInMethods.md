# SignInMethods


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**methods** | **List[str]** |  | 

## Example

```python
from chickenstats_api.models.sign_in_methods import SignInMethods

# TODO update the JSON string below
json = "{}"
# create an instance of SignInMethods from a JSON string
sign_in_methods_instance = SignInMethods.from_json(json)
# print the JSON string representation of the object
print(SignInMethods.to_json())

# convert the object into a dict
sign_in_methods_dict = sign_in_methods_instance.to_dict()
# create an instance of SignInMethods from a dict
sign_in_methods_from_dict = SignInMethods.from_dict(sign_in_methods_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


