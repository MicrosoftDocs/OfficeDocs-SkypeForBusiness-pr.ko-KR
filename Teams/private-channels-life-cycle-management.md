---
title: API를 사용하여 Microsoft Teams Graph 관리
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: API를 사용하여 조직의 개인 채널을 관리하는 Graph 대해 자세히 알아보습니다.
ms.openlocfilehash: 263c490156a3dc02ddc8f81233a049ff020c72f8
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278531"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>개인 채널의 수명 주기를 Microsoft Teams

여기에서 관리해야 하는 지침은 조직의 개인 채널을 관리하기 [](./private-channels.md) 위해 Graph API를 Teams 있습니다.

## <a name="set-whether-team-members-can-create-private-channels"></a>팀 구성원이 개인 채널을 만들 수 있는지 여부를 설정합니다.

관리자는 특정 팀 API를 사용하여 Graph 팀에서 개인 채널을 만들 수 있는지 여부를 제어할 수 있습니다. 다음은 예제입니다.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>팀 소유자를 대신하여 개인 채널 만들기

관리자는 팀 소유자를 대신하여 Graph API를 사용하여 개인 채널을 만들 수 있습니다. 예를 들어 조직에서 개인 채널을 중앙 집중화하려는 경우 이 작업을 할 수 있습니다.

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a>모든 개인 채널 메시지 목록 얻습니다.

보관 및 감사를 위해 개인 채널에 게시된 모든 메시지 및 응답 목록을 얻을 수 있습니다.  이 작업을 위해 Graph API를 사용하는 방법에는 다음과 같은 것이 있습니다.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>팀의 SharePoint 모든 개인 채널에 대한 URL 찾기

eDiscovery를 수행하거나 개인 채널의 파일에 대한 법적 보류를 수행하려는 경우 또는 특정 개인 채널에 파일을 저장하는 사용자 지정 앱을 빌드하려는 경우 각 개인 채널에 대해 만든 고유한 SharePoint 사이트 모음을 쿼리하는 방법을 원할 수 있습니다.

관리자는 API 명령에 Graph 이러한 URL을 쿼리할 수 있습니다.

탐색기 를 통해 이러한 [명령을 Graph 수 있습니다.](https://developer.microsoft.com/graph/graph-explorer)

1. 다음을 사용하여 팀의 그룹 ID인 해당 팀에 대한 <group_id> 채널 ID 목록을 얻습니다. 후속 호출에서 이 호출이 필요합니다. (팀에 대한 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.

    **요청**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **응답**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
    
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

2. URL을 얻게 SharePoint 각 개인 채널에 대해 채널 ID인 channel_id 요청을 &lt; &gt; 합니다.

    **요청**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **응답**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
      
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>개인 채널에서 소유자 및 구성원의 역할 나열 및 업데이트

개인 채널의 소유자 및 구성원을 나열하여 개인 채널의 특정 구성원을 소유자에게 승격해야 하는지 여부를 결정할 수 있습니다. 개인 채널 소유자가 조직을 떠났고 개인 채널에 채널 소유권을 요구하는 관리자의 도움이 필요한 경우 이러한 일이 일어날 수 있습니다.

관리자는 이러한 작업을 수행하기 위해 Graph API를 사용할 수 있습니다.

탐색기 를 통해 이러한 [명령을 Graph 수 있습니다.](https://developer.microsoft.com/graph/graph-explorer)

1. 다음을 사용하여 group_id 팀의 그룹 ID이고 channel_id &lt; &gt; &lt; &gt; ID입니다.

    **요청**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```

    **응답**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams({group_id}')/channels('{channel_id}')/members",
          "@odata.count": 2,
          "value": [
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
                  "id": "id-value",
                  "roles": [],
                  "displayName": "display-name-value",
                  "userId": "userId-value",
                  "email": "email-value"
              },
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
              "id": "id-value",
              "roles": ["owner"],
              "displayName": "display-name-value",
              "userId": "userId-value",
              "email": "email-value"
              }
          ]
    }
    ```

2. 다음을 사용하여 구성원을 소유자로 승격하고, group_id , channel_id 및 id가 이전 &lt; &gt; &lt; 호출에서 &gt; &lt; &gt; 반환됩니다. 이전 호출에서 반환된 ID 및 userId는 동일하지 &lt; &gt; &lt; &gt; 않습니다. ID를 &lt; 사용하는지 확인 &gt; 합니다.

    **요청**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **응답**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>관련 항목

[Microsoft Graph API를 사용하여 Teams에서 작업](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[채널 나열](/graph/api/channel-list)

[채널 만들기](/graph/api/channel-post)

[채널에 멤버 추가](/graph/api/conversationmember-add)

[채널에서 멤버 업데이트](/graph/api/conversationmember-update)

[채널에서 멤버 제거](/graph/api/conversationmember-delete)