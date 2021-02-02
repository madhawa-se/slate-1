---
title: CONNECTME API v1.2
language_tabs:
  - python: Python
  - ruby: Ruby
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="connectme-api">CONNECTME API v1.2</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

List of api endpoints

Base URLs:

# Authentication

- HTTP Authentication, scheme: bearer 

<h1 id="connectme-api-api">Api</h1>

## AppController_getApiInformation

<a id="opIdAppController_getApiInformation"></a>

`GET /`

<h3 id="appcontroller_getapiinformation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="connectme-api-message">Message</h1>

## MessageController_getMessagesForConversation

<a id="opIdMessageController_getMessagesForConversation"></a>

`GET /message/message-page-list/{coversation_id}`

*Get paginated messages in a conversation*

<h3 id="messagecontroller_getmessagesforconversation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|coversation_id|path|number|true|none|
|page|query|number|true|Page number|
|limit|query|number|true|Message limit|

> Example responses

> 200 Response

```json
{
  "totalCount": 585,
  "page": 1,
  "limit": 5,
  "data": [
    {
      "messageId": "1219ed11910a47d1aa8c202436fdff1e",
      "conversationId": 1,
      "direction": "SENT",
      "content": "Hi , Whats up ?",
      "datetime": "2021-01-08T08:55:30.422Z",
      "status": "PENDING",
      "attachments": []
    },
    {
      "messageId": "744ed9d3e7114267b76297cbb00a232b",
      "conversationId": 1,
      "direction": "SENT",
      "content": "\n",
      "datetime": "2020-12-01T10:04:16.303Z",
      "status": "PENDING",
      "attachments": [
        {
          "attachmentId": 31,
          "order": null,
          "type": "IMAGE",
          "filename": "ice.jpg",
          "filesize": 289516
        }
      ]
    },
    {
      "messageId": "7c6f8ee5b91e497d9cfddaaea9acf906",
      "conversationId": 1,
      "direction": "SENT",
      "content": "\n",
      "datetime": "2020-12-18T11:35:34.781Z",
      "status": "PENDING",
      "attachments": [
        {
          "attachmentId": 97,
          "order": null,
          "type": "VIDEO",
          "filename": "59f17da9-ced4-4f64-8a41-52ca08ed22f5-earth.mp4",
          "filesize": 3114374
        }
      ]
    },
    {
      "messageId": "1079950cafbf4b9d978b04e746e4bcd1",
      "conversationId": 1,
      "direction": "RECEIVED",
      "content": null,
      "datetime": "2020-12-17T03:18:34.472Z",
      "status": "PENDING",
      "attachments": [
        {
          "attachmentId": 87,
          "order": null,
          "type": "AUDIO",
          "filename": "768e708b-985a-4e9c-813f-4e718dc33748-media-1608175116539-incomming.mpga",
          "filesize": 5377729
        }
      ]
    }
  ]
}
```

<h3 id="messagecontroller_getmessagesforconversation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Conversation Page|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|you don't have access to this conversation|None|

<h3 id="messagecontroller_getmessagesforconversation-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## MessageController_create

<a id="opIdMessageController_create"></a>

`POST /message`

*Get paginated messages in a conversation*

> Body parameter

```json
{
  "type": "object",
  "properties": {
    "direction": {
      "type": "object",
      "description": "Message direction : recieve or send"
    },
    "to": {
      "type": "number",
      "description": "User id of the recipent"
    },
    "companyName": {
      "type": "number",
      "description": "depricated : remove"
    },
    "text": {
      "type": "function",
      "description": "MessageContent"
    },
    "mediaUrl": {
      "type": "string",
      "description": "Relative url of the media file (image,audio,video,document) for media messages"
    },
    "documentType": {
      "type": "object",
      "description": "Type of the attached document. image, audio,video .."
    },
    "type": {
      "type": "object",
      "description": "Type of the message"
    },
    "attachmentId": {
      "type": "number",
      "description": "Attachment ID"
    }
  },
  "required": [
    "direction",
    "to",
    "companyName",
    "text",
    "mediaUrl",
    "documentType",
    "type",
    "attachmentId"
  ]
}
```

<h3 id="messagecontroller_create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MessageRequestDto](#schemamessagerequestdto)|true|none|

> Example responses

> 200 Response

```json
{
  "totalCount": 585,
  "page": 1,
  "limit": 5,
  "data": [
    {
      "messageId": "1219ed11910a47d1aa8c202436fdff1e",
      "conversationId": 1,
      "direction": "SENT",
      "content": "Hi , Whats up ?",
      "datetime": "2021-01-08T08:55:30.422Z",
      "status": "PENDING",
      "attachments": []
    },
    {
      "messageId": "744ed9d3e7114267b76297cbb00a232b",
      "conversationId": 1,
      "direction": "SENT",
      "content": "\n",
      "datetime": "2020-12-01T10:04:16.303Z",
      "status": "PENDING",
      "attachments": [
        {
          "attachmentId": 31,
          "order": null,
          "type": "IMAGE",
          "filename": "ice.jpg",
          "filesize": 289516
        }
      ]
    },
    {
      "messageId": "7c6f8ee5b91e497d9cfddaaea9acf906",
      "conversationId": 1,
      "direction": "SENT",
      "content": "\n",
      "datetime": "2020-12-18T11:35:34.781Z",
      "status": "PENDING",
      "attachments": [
        {
          "attachmentId": 97,
          "order": null,
          "type": "VIDEO",
          "filename": "59f17da9-ced4-4f64-8a41-52ca08ed22f5-earth.mp4",
          "filesize": 3114374
        }
      ]
    },
    {
      "messageId": "1079950cafbf4b9d978b04e746e4bcd1",
      "conversationId": 1,
      "direction": "RECEIVED",
      "content": null,
      "datetime": "2020-12-17T03:18:34.472Z",
      "status": "PENDING",
      "attachments": [
        {
          "attachmentId": 87,
          "order": null,
          "type": "AUDIO",
          "filename": "768e708b-985a-4e9c-813f-4e718dc33748-media-1608175116539-incomming.mpga",
          "filesize": 5377729
        }
      ]
    }
  ]
}
```

<h3 id="messagecontroller_create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Conversation Page|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|you don't have access to this conversation|None|

<h3 id="messagecontroller_create-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## MessageController_messageIn

<a id="opIdMessageController_messageIn"></a>

`POST /message/messagein`

> Body parameter

```json
{
  "type": "object",
  "properties": {}
}
```

<h3 id="messagecontroller_messagein-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[InMessage](#schemainmessage)|true|none|

<h3 id="messagecontroller_messagein-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## MessageController_messageStatusIn

<a id="opIdMessageController_messageStatusIn"></a>

`POST /message/status`

> Body parameter

```json
{
  "type": "object",
  "properties": {}
}
```

<h3 id="messagecontroller_messagestatusin-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MessageReport](#schemamessagereport)|true|none|

<h3 id="messagecontroller_messagestatusin-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## MessageController_startNewChat

<a id="opIdMessageController_startNewChat"></a>

`POST /message/new-chat`

> Body parameter

```json
{
  "type": "object",
  "properties": {}
}
```

<h3 id="messagecontroller_startnewchat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[NewChatRequest](#schemanewchatrequest)|true|none|

<h3 id="messagecontroller_startnewchat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## MessageController_searchMessage

<a id="opIdMessageController_searchMessage"></a>

`GET /message/message-search/{term}`

<h3 id="messagecontroller_searchmessage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="connectme-api-authenticate">Authenticate</h1>

## AuthController_register

<a id="opIdAuthController_register"></a>

`POST /auth/signup`

*Signup to the system*

> Body parameter

```json
{
  "type": "object",
  "properties": {}
}
```

<h3 id="authcontroller_register-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RegisterUserDto](#schemaregisteruserdto)|true|none|

> Example responses

> 200 Response

```json
{
  "userId": 1,
  "firstName": "madhawa",
  "lastName": "samarawicrama",
  "phone": "+94717936775"
}
```

<h3 id="authcontroller_register-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account created|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Access forbidden to unconnected profiles|Inline|

<h3 id="authcontroller_register-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## AuthController_login

<a id="opIdAuthController_login"></a>

`POST /auth/login`

*Login to the system*

> Body parameter

```json
{
  "type": "object",
  "properties": {
    "email": {
      "type": "string",
      "description": "User email address"
    },
    "password": {
      "type": "string",
      "description": "User password"
    }
  },
  "required": [
    "email",
    "password"
  ]
}
```

<h3 id="authcontroller_login-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[LoginUserDto](#schemaloginuserdto)|true|none|

> Example responses

> 200 Response

```json
{
  "name": "ice.jpg",
  "size": 289516,
  "documentType": "IMAGE",
  "attachmentId": 100
}
```

<h3 id="authcontroller_login-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Login sucessfully|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Login failed.please check the username and password and try again|Inline|

<h3 id="authcontroller_login-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="connectme-api-contact">Contact</h1>

## ContactController_getAll

<a id="opIdContactController_getAll"></a>

`GET /contact`

<h3 id="contactcontroller_getall-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## ContactController_update

<a id="opIdContactController_update"></a>

`PUT /contact`

> Body parameter

```json
{
  "type": "object",
  "properties": {}
}
```

<h3 id="contactcontroller_update-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UpdateUserDto](#schemaupdateuserdto)|true|none|

<h3 id="contactcontroller_update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## ContactController_getMessagesForConversation

<a id="opIdContactController_getMessagesForConversation"></a>

`GET /contact/search/{phone}`

<h3 id="contactcontroller_getmessagesforconversation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="connectme-api-conversation">Conversation</h1>

## ConversationController_checkChatAvailibility

<a id="opIdConversationController_checkChatAvailibility"></a>

`GET /conversation/chat-time-report/{conversationId}`

*Get state of chat window ; whatsapp specific endpoint*

<h3 id="conversationcontroller_checkchatavailibility-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|conversationId|path|number|true|none|

> Example responses

> 200 Response

```json
{
  "lastFreeMessageTime": "2021-01-08T08:55:30.422Z",
  "comparedTime": "2021-01-20T11:32:09.568Z",
  "duration": 0
}
```

<h3 id="conversationcontroller_checkchatavailibility-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Chat window status|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|you don't have access to this conversation|None|

<h3 id="conversationcontroller_checkchatavailibility-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## ConversationController_getPagedConversation

<a id="opIdConversationController_getPagedConversation"></a>

`GET /conversation/conversation-page-list`

*Get paginated conversation list for specific company*

<h3 id="conversationcontroller_getpagedconversation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|true|Page number|
|limit|query|number|true|Message limit|

> Example responses

> 200 Response

```json
{
  "totalCount": 20,
  "page": "1",
  "limit": "2",
  "data": [
    {
      "conversationId": 3,
      "companyId": 1,
      "userId": 143,
      "channelId": 1,
      "lastUpdateTime": null,
      "lastFreeMessageTime": null,
      "user": {
        "userId": 143,
        "firstName": "new",
        "lastName": "user",
        "phone": "+94775777794"
      }
    },
    {
      "conversationId": 4,
      "companyId": 1,
      "userId": 144,
      "channelId": 1,
      "lastUpdateTime": null,
      "lastFreeMessageTime": null,
      "user": {
        "userId": 144,
        "firstName": "new",
        "lastName": "user",
        "phone": "+94717936771"
      }
    }
  ]
}
```

<h3 id="conversationcontroller_getpagedconversation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Conversation Page|Inline|

<h3 id="conversationcontroller_getpagedconversation-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

<h1 id="connectme-api-media">Media</h1>

## MediaController_saveAttachment

<a id="opIdMediaController_saveAttachment"></a>

`POST /media/save`

*Save media to web server*

> Body parameter

```yaml
type: object
properties:
  file:
    type: string
    format: binary

```

<h3 id="mediacontroller_saveattachment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» file|body|string(binary)|false|none|

> Example responses

> 201 Response

```json
{
  "name": "ice.jpg",
  "size": 289516,
  "documentType": "IMAGE",
  "attachmentId": 100
}
```

<h3 id="mediacontroller_saveattachment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Media saved successfully|Inline|

<h3 id="mediacontroller_saveattachment-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

<h1 id="connectme-api-template">Template</h1>

## TemplateController_getAllTemplates

<a id="opIdTemplateController_getAllTemplates"></a>

`GET /template`

*Get all Whatsapp message templates*

> Example responses

> 200 Response

```json
[
  {
    "content": "Hi {{1}}! Thanks for contacting Us.  We are happy to create your demo account and will send you login credentials shortly..",
    "templateId": 1
  },
  {
    "content": "Your {{1}} order of {{2}} has shipped and should be delivered on {{3}}. Details : {{4}}",
    "templateId": 2
  }
]
```

<h3 id="templatecontroller_getalltemplates-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All messsage templates|Inline|

<h3 id="templatecontroller_getalltemplates-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

<h1 id="connectme-api-profile">Profile</h1>

## ProfileController_getProfile

<a id="opIdProfileController_getProfile"></a>

`GET /profile/{profileId}`

*Get the profile of a contact.*

<h3 id="profilecontroller_getprofile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|profileId|path|number|true|none|

> Example responses

> 200 Response

```json
{
  "userId": 1,
  "firstName": "madhawa",
  "lastName": "samarawicrama",
  "phone": "+94717936775"
}
```

<h3 id="profilecontroller_getprofile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get user rofile|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Access forbidden to unconnected profiles|Inline|

<h3 id="profilecontroller_getprofile-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## ProfileController_update

<a id="opIdProfileController_update"></a>

`PUT /profile`

*Update contact profile information*

> Body parameter

```json
{
  "type": "object",
  "properties": {
    "firstName": {
      "type": "string",
      "description": "First name"
    },
    "lastName": {
      "type": "string",
      "description": "Last name"
    },
    "phone": {
      "type": "string",
      "description": "Phone number"
    },
    "userId": {
      "type": "string",
      "description": "User id"
    }
  },
  "required": [
    "firstName",
    "lastName",
    "phone",
    "userId"
  ]
}
```

<h3 id="profilecontroller_update-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ProfileDataDto](#schemaprofiledatadto)|true|none|

> Example responses

> 200 Response

```json
{
  "status": true,
  "message": "Profile Update sucessfully"
}
```

<h3 id="profilecontroller_update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Update sucessfull|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Access forbidden to unconnected profiles|Inline|

<h3 id="profilecontroller_update-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

# Schemas

<h2 id="tocS_MessageRequestDto">MessageRequestDto</h2>
<!-- backwards compatibility -->
<a id="schemamessagerequestdto"></a>
<a id="schema_MessageRequestDto"></a>
<a id="tocSmessagerequestdto"></a>
<a id="tocsmessagerequestdto"></a>

```json
{
  "type": "object",
  "properties": {
    "direction": {
      "type": "object",
      "description": "Message direction : recieve or send"
    },
    "to": {
      "type": "number",
      "description": "User id of the recipent"
    },
    "companyName": {
      "type": "number",
      "description": "depricated : remove"
    },
    "text": {
      "type": "function",
      "description": "MessageContent"
    },
    "mediaUrl": {
      "type": "string",
      "description": "Relative url of the media file (image,audio,video,document) for media messages"
    },
    "documentType": {
      "type": "object",
      "description": "Type of the attached document. image, audio,video .."
    },
    "type": {
      "type": "object",
      "description": "Type of the message"
    },
    "attachmentId": {
      "type": "number",
      "description": "Attachment ID"
    }
  },
  "required": [
    "direction",
    "to",
    "companyName",
    "text",
    "mediaUrl",
    "documentType",
    "type",
    "attachmentId"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|direction|object|true|none|Message direction : recieve or send|
|to|number|true|none|User id of the recipent|
|companyName|number|true|none|depricated : remove|
|text|function|true|none|MessageContent|
|mediaUrl|string|true|none|Relative url of the media file (image,audio,video,document) for media messages|
|documentType|object|true|none|Type of the attached document. image, audio,video ..|
|type|object|true|none|Type of the message|
|attachmentId|number|true|none|Attachment ID|

<h2 id="tocS_InMessage">InMessage</h2>
<!-- backwards compatibility -->
<a id="schemainmessage"></a>
<a id="schema_InMessage"></a>
<a id="tocSinmessage"></a>
<a id="tocsinmessage"></a>

```json
{
  "type": "object",
  "properties": {}
}

```

### Properties

*None*

<h2 id="tocS_MessageReport">MessageReport</h2>
<!-- backwards compatibility -->
<a id="schemamessagereport"></a>
<a id="schema_MessageReport"></a>
<a id="tocSmessagereport"></a>
<a id="tocsmessagereport"></a>

```json
{
  "type": "object",
  "properties": {}
}

```

### Properties

*None*

<h2 id="tocS_NewChatRequest">NewChatRequest</h2>
<!-- backwards compatibility -->
<a id="schemanewchatrequest"></a>
<a id="schema_NewChatRequest"></a>
<a id="tocSnewchatrequest"></a>
<a id="tocsnewchatrequest"></a>

```json
{
  "type": "object",
  "properties": {}
}

```

### Properties

*None*

<h2 id="tocS_RegisterUserDto">RegisterUserDto</h2>
<!-- backwards compatibility -->
<a id="schemaregisteruserdto"></a>
<a id="schema_RegisterUserDto"></a>
<a id="tocSregisteruserdto"></a>
<a id="tocsregisteruserdto"></a>

```json
{
  "type": "object",
  "properties": {}
}

```

### Properties

*None*

<h2 id="tocS_LoginUserDto">LoginUserDto</h2>
<!-- backwards compatibility -->
<a id="schemaloginuserdto"></a>
<a id="schema_LoginUserDto"></a>
<a id="tocSloginuserdto"></a>
<a id="tocsloginuserdto"></a>

```json
{
  "type": "object",
  "properties": {
    "email": {
      "type": "string",
      "description": "User email address"
    },
    "password": {
      "type": "string",
      "description": "User password"
    }
  },
  "required": [
    "email",
    "password"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string|true|none|User email address|
|password|string|true|none|User password|

<h2 id="tocS_UpdateUserDto">UpdateUserDto</h2>
<!-- backwards compatibility -->
<a id="schemaupdateuserdto"></a>
<a id="schema_UpdateUserDto"></a>
<a id="tocSupdateuserdto"></a>
<a id="tocsupdateuserdto"></a>

```json
{
  "type": "object",
  "properties": {}
}

```

### Properties

*None*

<h2 id="tocS_ProfileDataDto">ProfileDataDto</h2>
<!-- backwards compatibility -->
<a id="schemaprofiledatadto"></a>
<a id="schema_ProfileDataDto"></a>
<a id="tocSprofiledatadto"></a>
<a id="tocsprofiledatadto"></a>

```json
{
  "type": "object",
  "properties": {
    "firstName": {
      "type": "string",
      "description": "First name"
    },
    "lastName": {
      "type": "string",
      "description": "Last name"
    },
    "phone": {
      "type": "string",
      "description": "Phone number"
    },
    "userId": {
      "type": "string",
      "description": "User id"
    }
  },
  "required": [
    "firstName",
    "lastName",
    "phone",
    "userId"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|firstName|string|true|none|First name|
|lastName|string|true|none|Last name|
|phone|string|true|none|Phone number|
|userId|string|true|none|User id|

