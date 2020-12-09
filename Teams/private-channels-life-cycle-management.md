---
title: Microsoft Teams에서 개인 채널의 수명 주기 관리
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
description: 조직에서 개인 채널의 수명 주기를 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 336d97071c30bca145d26f4c853d5bb30265721f
ms.sourcegitcommit: 68dffc3aca46992448bc2be0689bfd352e016316
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49601663"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Microsoft Teams에서 개인 채널의 수명 주기 관리

조직에서 개인 채널의 수명 주기를 관리하는 데 필요한 [지침을](private-channels.md) 찾을 수 있습니다.

> [!IMPORTANT]
> 이 문서의 PowerShell 단계를 사용하여 개인 채널을 관리하는 경우 PowerShell 갤러리에서 Teams PowerShell 공개 미리 보기 모듈을 설치하고 [사용해야 합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams/) 모듈을 설치하는 방법에 대한 단계는 [Microsoft Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md) 최신 일반 공급 Teams PowerShell 모듈은 개인 채널 관리를 지원하지 않습니다.

## <a name="set-whether-team-members-can-create-private-channels"></a>팀 구성원이 비공개 채널을 만들 수 있는지 여부 설정

팀 소유자는 구성원이 팀 설정에서 비공개 채널을 만들 수 있는 기능을 끄거나 끄면 됩니다. 이렇게하려면 팀의 **Settings** 설정 탭에서 구성원이 비공개 채널을 만들 수 있도록 허용을 **끄거나 니다.**

관리자는 Graph API를 사용하여 구성원이 특정 팀에서 비공개 채널을 만들 수 있는지 여부를 제어할 수 있습니다. 예제는 다음과 같습니다.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>조직의 사용자가 개인 채널을 만들 수 있는지 여부 설정

관리자는 Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 개인 채널을 만들 수 있는 조직의 사용자를 제어할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

팀 정책을 사용하여 개인 채널을 만들 수 있는 조직의 사용자를 설정할 수 있습니다. 자세한 내용은 [Teams에서 팀 정책 관리를 참조합니다.](teams-policies.md)

### <a name="using-powershell"></a>PowerShell 사용

**CsTeamsChannelsPolicy를** 사용하여 개인 채널을 만들 수 있는 조직의 사용자를 설정할 수 있습니다. 정책이 할당된 사용자가 개인 채널을 만들 수 있도록 **AllowPrivateChannelCreation** 매개 변수를 **true로** 설정하세요. 매개 변수를 **false로** 설정하면 정책이 할당된 사용자에 대한 개인 채널을 만드는 기능을 해제합니다.

자세한 내용은 [New-CsTeamsChannelsPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>팀 소유자를 대신하여 비공개 채널 만들기

관리자는 PowerShell 또는 Graph API를 사용하여 팀 소유자를 대신하여 개인 채널을 만들 수 있습니다. 예를 들어 조직에서 개인 채널을 중앙 집중화하려는 경우 이 작업을 원할 수 있습니다.

### <a name="using-powershell"></a>PowerShell 사용

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Graph API 사용

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

## <a name="get-a-list-of-all-private-channel-messages"></a>모든 개인 채널 메시지 목록을 찾습니다.

보관 및 감사를 위해 개인 채널에 게시된 모든 메시지 및 응답 목록을 얻을 수 있습니다.  Graph API를 사용하여 이 작업을 하는 방법에는 다음과 같은 것이 있습니다.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>팀의 모든 비공개 채널에 대한 SharePoint URL 찾기

개인 채널의 파일에 대한 eDiscovery 또는 법적 보류를 수행하려는 경우 또는 특정 개인 채널에 파일을 저장하는 사용자 지정 앱을 빌드하려는 경우 각 개인 채널에 대해 생성된 고유한 SharePoint 사이트 모음을 쿼리하는 방법을 원할 것입니다.

관리자는 PowerShell 또는 Graph API 명령을 사용하여 이러한 URL을 쿼리할 수 있습니다.

### <a name="using-powershell"></a>PowerShell 사용

1. 관리자 계정으로 [SharePoint Online 관리](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 셸을 설치하고 연결합니다.
2. 다음을 실행합니다. 여기서 group_id &lt; &gt; 팀의 그룹 ID입니다. (팀 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Graph API 사용

Graph Explorer를 통해 이러한 명령을 [시도할 수 있습니다.](https://developer.microsoft.com/graph/graph-explorer)

1. 다음을 사용하여 팀의 그룹 ID인 경우, <group_id> 팀의 개인 채널 ID 목록을 얻습니다. 후속 호출에서 필요합니다. (팀 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.)

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

2. SharePoint URL을 사용하려는 각 개인 채널에 대해 다음을 요청합니다. 여기서 channel_id &lt; &gt; ID입니다.

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

개인 채널의 소유자 및 구성원을 나열하여 개인 채널의 특정 멤버를 소유자로 승격해야 하는지 여부를 결정할 수 있습니다. 이 경우 조직을 떠날 개인 채널의 소유자가 있으며 개인 채널에 채널 소유권을 요구하는 관리자의 도움이 필요한 경우 이 문제를 발생될 수 있습니다.

관리자는 Microsoft Teams 관리 센터, PowerShell 또는 Graph API를 사용하여 이러한 작업을 수행할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

Microsoft Teams 관리 센터를 사용하여 팀 구성원을 관리하는 방법에 대한 자세한 내용은 Microsoft Teams 관리 센터에서 팀 [관리를 참조하세요.](manage-teams-in-modern-portal.md)

### <a name="using-powershell"></a>PowerShell 사용

1. 다음을 실행합니다. 여기서 group_id ID는 팀의 그룹 &lt; &gt; ID이고 channel_name &lt; &gt; 이름입니다.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. 구성원을 소유자로 승격합니다.

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Graph API 사용

Graph Explorer를 통해 이러한 명령을 [시도할 수 있습니다.](https://developer.microsoft.com/graph/graph-explorer)

1. 다음을 사용하세요. 여기서 group_id 팀의 그룹 ID이고 channel_id &lt; &gt; &lt; &gt; ID입니다.

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
2. 다음을 사용하여 멤버를 소유자로 승격합니다. 여기서 group_id, channel_id 및 ID가 이전 호출에서 &lt; &gt; &lt; &gt; &lt; &gt; 반환됩니다. 이전 호출에서 반환된 ID와 userId는 동일하지 않습니다. 서로 &lt; &gt; &lt; &gt; 교환할 수 없습니다. ID를 &lt; 사용하는지 확인 &gt;

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

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Microsoft Graph API를 사용하여 Teams에서 작업](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [채널 나열](https://docs.microsoft.com/graph/api/channel-list)
    - [채널 만들기](https://docs.microsoft.com/graph/api/channel-post)
    - [채널에 구성원 추가](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [채널에서 구성원 업데이트](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [채널에서 구성원 제거](https://docs.microsoft.com/graph/api/conversationmember-delete)
