---
title: Microsoft 팀의 개인 채널 수명 주기 관리
author: lanachin
ms.author: v-lanac
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
description: 조직의 개인 채널 수명 주기를 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 154cde6ad8371b2d9f902bf3803f48e72ade0a77
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321705"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Microsoft 팀의 개인 채널 수명 주기 관리

여기에서 조직의 [개인 채널](private-channels.md) 수명 주기를 관리 하는 데 필요한 지침을 확인할 수 있습니다.

> [!IMPORTANT]
> 이 문서의 PowerShell 단계를 사용 하 여 개인 채널을 관리 하는 경우 [Powershell 테스트 갤러리](https://www.poshtestgallery.com/packages/MicrosoftTeams/)에서 팀 powershell 모듈의 최신 시험판 버전을 설치 하 고 사용 해야 합니다. 모듈을 설치 하는 방법에 대 한 단계는 [팀 PowerShell 모듈의 시험판 버전 설치](install-prerelease-teams-powershell-module.md)를 참조 하세요. 공개적으로 사용할 수 있는 팀 PowerShell 모듈의 최신 버전은 비공개 채널 관리를 지원 하지 않습니다.

## <a name="set-whether-team-members-can-create-private-channels"></a>팀 구성원이 개인 채널을 만들 수 있는지 여부 설정

팀 소유자는 멤버가 팀 설정에서 비공개 채널을 만들 수 있도록 설정 하거나 해제할 수 있습니다. 이렇게 하려면 팀의 **설정** 탭에서 **구성원에 게 개인 채널을 만들도록 허용**을 설정 하거나 해제 합니다.

관리자는 Graph API를 사용 하 여 구성원이 특정 팀에서 개인 채널을 만들 수 있는지 여부를 제어할 수 있습니다. 예제는 다음과 같습니다.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>조직의 사용자가 개인 채널을 만들 수 있는지 여부 설정

관리자는 Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 조직에서 개인 채널을 만들 수 있는 사용자를 제어 하는 정책을 설정할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

팀 정책을 사용 하 여 조직에서 개인 채널을 만들 수 있는 사용자를 설정 합니다. 자세히 알아보려면 [팀에서 팀 정책 관리](teams-policies.md)를 참조 하세요.

### <a name="using-powershell"></a>PowerShell 사용

**CsTeamsChannelsPolicy** 를 사용 하 여 조직에서 개인 채널을 만들 수 있는 사용자를 설정 합니다. **AllowPrivateChannelCreation** 매개 변수를 **true** 로 설정 하 여 정책을 할당 한 사용자가 개인 채널을 만들 수 있도록 합니다. 매개 변수를 **false** 로 설정 하면 정책이 할당 된 사용자에 대해 개인 채널을 만드는 기능이 꺼집니다.

자세한 내용은 [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)를 참조 하세요.

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>팀 소유자 대신 개인 채널 만들기

관리자는 PowerShell 또는 Graph API를 사용 하 여 팀 소유자 대신 개인 채널을 만들 수 있습니다. 예를 들어 조직에서 개인 채널을 중앙에서 만들려면이 작업을 수행 해야 할 수 있습니다.

### <a name="using-powershell"></a>PowerShell 사용

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>그래프 API 사용

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

## <a name="get-a-list-of-all-private-channel-messages"></a>모든 개인 채널 메시지 목록 가져오기

보관 및 감사 목적으로 개인 채널에 게시 된 모든 메시지 및 응답의 목록을 가져올 수 있습니다.  그래프 API를 사용 하 여이 작업을 수행 하는 방법은 다음과 같습니다.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>팀의 모든 개인 채널에 대 한 SharePoint Url 찾기

개인 채널의 파일에 대해 eDiscovery 또는 보관을 수행 하려는 경우 또는 특정 개인 채널에 파일을 배치 하는 사용자 지정 앱을 빌드 하려는 경우 각 개인 채널에 대해 생성 되는 고유한 SharePoint 사이트 모음을 쿼리 하는 방법을 원하는 경우를 원할 것입니다.

관리자는 PowerShell 또는 Graph Api 명령을 사용 하 여 이러한 Url을 쿼리할 수 있습니다.

### <a name="using-powershell"></a>PowerShell 사용

1. 관리자 계정을 사용 하 여 [SharePoint Online 관리 셸에](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 설치 하 고 연결 합니다.
2. &lt;팀의 그룹 id 인 group_id 다음을 실행 합니다 &gt; . (팀에 대 한 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>그래프 API 사용

[그래프 탐색기](https://developer.microsoft.com/graph/graph-explorer)를 통해 이러한 명령을 수행해 볼 수 있습니다.

1. 다음을 사용 하 여 지정 된 팀의 개인 채널 Id 목록을 가져올 수 있으며, 여기에서 <group_id> 팀의 그룹 ID입니다. 이후 통화에 필요 합니다. (팀에 대 한 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.)

    **요청당**

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

2. SharePoint URL을 가져오려는 각 개인 채널에 대해 다음 요청을 수행 합니다 ( &lt; channel_id &gt; 는 채널 id).

    **요청당**

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>개인 채널의 소유자 및 구성원의 역할 나열 및 업데이트

개인 채널의 특정 구성원을 소유자로 승격 해야 하는지 여부를 결정 하려면 개인 채널의 소유자와 구성원을 나열 하 고 싶을 수 있습니다. 이 문제는 조직을 남겨진 개인 채널의 소유자가 있고 개인 채널에서 채널의 소유권을 요구 하는 관리자 도움말이 필요한 경우에 발생할 수 있습니다.

관리자는 PowerShell 또는 Graph Api 명령을 사용 하 여 이러한 Url을 쿼리할 수 있습니다.

### <a name="using-powershell"></a>PowerShell 사용

1. 다음을 실행 합니다 (여기서 &lt; group_id &gt; 는 팀의 그룹 id이 고 &lt; channel_name는 &gt; 채널 이름입니다.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. 구성원을 소유자로 승격 합니다.

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>그래프 API 사용

[그래프 탐색기](https://developer.microsoft.com/graph/graph-explorer)를 통해 이러한 명령을 수행해 볼 수 있습니다.

1. &lt; &gt; 팀의 그룹 id이 고 &lt; channel_id &gt; 채널 id 인 경우에는 다음을 사용 group_id.

    **요청당**

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
2. 다음을 사용 하 여 구성원을 소유자로 승격 합니다 ( &lt; group_id &gt; , &lt; channel_id &gt; , &lt; id &gt; 는 이전 호출에서 반환 됩니다. &lt; &gt; &lt; 이전 호출에서 반환 된 id와 userId는 &gt; 같지 않으며 호환 되지 않습니다. Id를 사용 하 고 있는지 확인 &lt; &gt; 합니다.

    **요청당**

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
    - [목록 채널](https://docs.microsoft.com/graph/api/channel-list)
    - [채널 만들기](https://docs.microsoft.com/graph/api/channel-post)
    - [채널에 구성원 추가](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [채널의 구성원 업데이트](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [채널에서 구성원 제거](https://docs.microsoft.com/graph/api/conversationmember-delete)
