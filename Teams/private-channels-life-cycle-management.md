---
title: Graph API를 사용하여 Microsoft Teams의 개인 채널 관리
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
description: Graph API를 사용하여 조직의 개인 채널을 관리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: e97d808bd9f544ef611b0b5e4b0456d302b4013d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117746"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="fbe37-103">Microsoft Teams에서 개인 채널의 수명 주기 관리</span><span class="sxs-lookup"><span data-stu-id="fbe37-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="fbe37-104">여기서는 Graph API를 사용하여 조직의 [Teams](./private-channels.md) 개인 채널을 관리하는 데 필요한 지침을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-104">Here you'll find the guidance you need to manage use the Graph API to manage [Teams private channels](./private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="fbe37-105">팀 구성원이 개인 채널을 만들 수 있는지 여부를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="fbe37-106">관리자는 Graph API를 사용하여 구성원이 특정 팀에서 개인 채널을 만들 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-106">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="fbe37-107">다음은 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-107">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="fbe37-108">팀 소유자를 대신하여 개인 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="fbe37-108">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="fbe37-109">관리자는 Graph API를 사용하여 팀 소유자를 대신하여 개인 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-109">As an admin, you can use the Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="fbe37-110">예를 들어 조직에서 개인 채널을 중앙 집중화하려는 경우 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-110">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="fbe37-111">모든 개인 채널 메시지 목록 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-111">Get a list of all private channel messages</span></span>

<span data-ttu-id="fbe37-112">보관 및 감사를 위해 개인 채널에 게시된 모든 메시지 및 응답 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-112">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="fbe37-113">Graph API를 사용하여 이 작업을 하는 방법에는 다음과 같은 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-113">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="fbe37-114">팀의 모든 개인 채널에 대한 SharePoint URL 찾기</span><span class="sxs-lookup"><span data-stu-id="fbe37-114">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="fbe37-115">eDiscovery를 수행하거나 개인 채널의 파일에 대한 법적 보류를 수행하거나 특정 개인 채널에 파일을 저장하는 사용자 지정 앱을 빌드하려는 경우 각 개인 채널에 대해 만든 고유한 SharePoint 사이트 모음을 쿼리하는 방법을 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-115">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="fbe37-116">관리자는 Graph API 명령을 사용하여 이러한 URL을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-116">As an admin, you can use Graph APIs commands to query these URLs.</span></span>

<span data-ttu-id="fbe37-117">Graph Explorer를 통해 이러한 명령을 [시도할 수 있습니다.](https://developer.microsoft.com/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="fbe37-117">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="fbe37-118">다음을 사용하여 팀의 그룹 ID인 해당 팀에 대한 <group_id> 채널 ID 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-118">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="fbe37-119">후속 호출에서 이 호출이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-119">You'll need this in subsequent calls.</span></span> <span data-ttu-id="fbe37-120">(팀에 대한 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-120">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="fbe37-121">**요청**</span><span class="sxs-lookup"><span data-stu-id="fbe37-121">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="fbe37-122">**응답**</span><span class="sxs-lookup"><span data-stu-id="fbe37-122">**Response**</span></span>

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

2. <span data-ttu-id="fbe37-123">SharePoint URL을 받을 각 개인 채널에 대해 다음 요청을 하고 채널 ID는 channel_id &lt; &gt; 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-123">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="fbe37-124">**요청**</span><span class="sxs-lookup"><span data-stu-id="fbe37-124">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="fbe37-125">**응답**</span><span class="sxs-lookup"><span data-stu-id="fbe37-125">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="fbe37-126">개인 채널에서 소유자 및 구성원의 역할 나열 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="fbe37-126">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="fbe37-127">개인 채널의 소유자 및 구성원을 나열하여 개인 채널의 특정 구성원을 소유자에게 승격해야 하는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-127">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="fbe37-128">개인 채널 소유자가 조직을 떠났고 개인 채널에 채널 소유권을 요구하는 관리자의 도움이 필요한 경우 이러한 일이 일어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-128">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="fbe37-129">관리자는 Graph API를 사용하여 이러한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-129">As an admin, you can use the Graph API to perform these actions.</span></span>

<span data-ttu-id="fbe37-130">Graph Explorer를 통해 이러한 명령을 [시도할 수 있습니다.](https://developer.microsoft.com/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="fbe37-130">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="fbe37-131">다음을 사용하여 group_id 팀의 그룹 ID이고 channel_id &lt; &gt; &lt; &gt; ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-131">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="fbe37-132">**요청**</span><span class="sxs-lookup"><span data-stu-id="fbe37-132">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="fbe37-133">**응답**</span><span class="sxs-lookup"><span data-stu-id="fbe37-133">**Response**</span></span>

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
2. <span data-ttu-id="fbe37-134">다음을 사용하여 구성원을 소유자로 승격하고, group_id , channel_id 및 id가 이전 &lt; &gt; &lt; 호출에서 &gt; &lt; &gt; 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-134">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="fbe37-135">이전 호출에서 반환된 ID 및 userId는 동일하지 &lt; &gt; &lt; &gt; 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-135">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="fbe37-136">ID를 &lt; 사용하는지 확인 &gt; 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbe37-136">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="fbe37-137">**요청**</span><span class="sxs-lookup"><span data-stu-id="fbe37-137">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="fbe37-138">**응답**</span><span class="sxs-lookup"><span data-stu-id="fbe37-138">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="fbe37-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fbe37-139">Related topics</span></span>

[<span data-ttu-id="fbe37-140">Microsoft Graph API를 사용하여 Teams에서 작업</span><span class="sxs-lookup"><span data-stu-id="fbe37-140">Use the Microsoft Graph API to work with Teams</span></span>](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[<span data-ttu-id="fbe37-141">채널 나열</span><span class="sxs-lookup"><span data-stu-id="fbe37-141">List channels</span></span>](/graph/api/channel-list)

[<span data-ttu-id="fbe37-142">채널 만들기</span><span class="sxs-lookup"><span data-stu-id="fbe37-142">Create channel</span></span>](/graph/api/channel-post)

[<span data-ttu-id="fbe37-143">채널에 멤버 추가</span><span class="sxs-lookup"><span data-stu-id="fbe37-143">Add member to channel</span></span>](/graph/api/conversationmember-add)

[<span data-ttu-id="fbe37-144">채널에서 멤버 업데이트</span><span class="sxs-lookup"><span data-stu-id="fbe37-144">Update member in channel</span></span>](/graph/api/conversationmember-update)

[<span data-ttu-id="fbe37-145">채널에서 멤버 제거</span><span class="sxs-lookup"><span data-stu-id="fbe37-145">Remove member from channel</span></span>](/graph/api/conversationmember-delete)