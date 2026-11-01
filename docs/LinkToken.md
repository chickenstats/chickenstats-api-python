# LinkToken


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**token** | **str** |  | 

## Example

```python
from chickenstats_api.models.link_token import LinkToken

# TODO update the JSON string below
json = "{}"
# create an instance of LinkToken from a JSON string
link_token_instance = LinkToken.from_json(json)
# print the JSON string representation of the object
print(LinkToken.to_json())

# convert the object into a dict
link_token_dict = link_token_instance.to_dict()
# create an instance of LinkToken from a dict
link_token_from_dict = LinkToken.from_dict(link_token_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


