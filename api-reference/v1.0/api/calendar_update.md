# Update calendar

Update the properties of calendar object.
### Prerequisites
One of the following **scopes** is required to execute this API: 
*Calendars.ReadWrite*
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /me/calendar
PATCH /users/<id | userPrincipalName>/calendar
PATCH /groups/<id>/calendar
PATCH /drive/root/createdByUser/calendar
PATCH /me/calendars/<id>
PATCH /users/<id | userPrincipalName>/calendars/<id>
PATCH /me/calendarGroup/calendars/<id>
PATCH /users/<id | userPrincipalName>/calendarGroup/calendars/<id>
PATCH /me/calendarGroups/<id>/calendars/<id>
PATCH /users/<id | userPrincipalName>/calendarGroups/<id>/calendars/<id>
PATCH /groups/<id>/calendar
```
### Request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer <token>. Required. |

### Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|changeKey|String|Identifies the version of the calendar object. Every time the calendar is changed, ChangeKey  changes as well. This allows Exchange to apply changes to the correct version of the object.|
|color|String|Specifies the color theme to distinguish the calendar from other calendars in a UI. The property values are: LightBlue=0, LightGreen=1, LightOrange=2, LightGray=3, LightYellow=4, LightTeal=5, LightPink=6, LightBrown=7, LightRed=8, MaxColor=9, Auto=-1|
|name|String|The calendar name.|

### Response
If successful, this method returns a `200 OK` response code and updated [calendar](../resources/calendar.md) object in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_calendar"
}-->
```http
PATCH https://graph.microsoft.com/v1.0/me/calendar
Content-type: application/json
Content-length: 48

{
  "name": "name-value",
  "color": {
  }
}
```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.calendar"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 98

{
  "name": "name-value",
  "color": {
  },
  "changeKey": "changeKey-value",
  "id": "id-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update calendar",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
