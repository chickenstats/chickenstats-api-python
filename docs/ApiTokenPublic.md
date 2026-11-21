# ApiTokenPublic


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** |  | 
**name** | **str** |  | 
**prefix** | **str** |  | 
**created_at** | **datetime** |  | 
**last_used_at** | **datetime** |  | 
**expires_at** | **datetime** |  | 

## Example

```python
from chickenstats_api.models.api_token_public import ApiTokenPublic

# TODO update the JSON string below
json = "{}"
# create an instance of ApiTokenPublic from a JSON string
api_token_public_instance = ApiTokenPublic.from_json(json)
# print the JSON string representation of the object
print(ApiTokenPublic.to_json())

# convert the object into a dict
api_token_public_dict = api_token_public_instance.to_dict()
# create an instance of ApiTokenPublic from a dict
api_token_public_from_dict = ApiTokenPublic.from_dict(api_token_public_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


