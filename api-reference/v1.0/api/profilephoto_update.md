# Update profilephoto

Update the photo for signed-in **user**, **group** or a **contact**.
### Prerequisites
One of the following **scopes** is required to execute this API for: 
* Profile photo of signed-in **user** - *User.ReadWrite.All; User.ReadWrite*
* Profile photo of a **group** - *Group.ReadWrite.All* 
* Photo of a **contact** - *Contacts.ReadWrite*
### HTTP request to update the photo
<!-- { "blockType": "ignored" } -->
```http
PATCH /me/photo/$value
PATCH /users/<id | userPrincipalName>/photo/$value
PATCH /groups/<id>/photo/$value
PATCH /me/contacts/<id>/photo/$value
PATCH /users/<id | userPrincipalName>/contacts/<id>/photo/$value
PATCH /me/contactfolders/<contactFolderId>/contacts/<id>/photo/$value
PATCH /users/<id | userPrincipalName>/contactfolders/<contactFolderId>/contacts/<id>/photo/$value
```
### Request headers
| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer <token>. Required.  |
| Content-Type  | image/jpeg. Required.  |

### Request body
In the request body, include the binary data of the photo in the request body.

### Response
If successful, this method returns a `200 OK` response code.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_profilephoto"
}-->
```http
PATCH https://graph.microsoft.com/v1.0/me/photo/$value
Content-type: image/jpeg

Binary data for the image

```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.profilephoto"
} -->
```http
HTTP/1.1 200 OK
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update profilephoto",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->