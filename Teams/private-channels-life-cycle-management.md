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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="1cab3-103">Microsoft Teams에서 개인 채널의 수명 주기 관리</span><span class="sxs-lookup"><span data-stu-id="1cab3-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="1cab3-104">조직에서 개인 채널의 수명 주기를 관리하는 데 필요한 [지침을](private-channels.md) 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cab3-105">이 문서의 PowerShell 단계를 사용하여 개인 채널을 관리하는 경우 PowerShell 갤러리에서 Teams PowerShell 공개 미리 보기 모듈을 설치하고 [사용해야 합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams/)</span><span class="sxs-lookup"><span data-stu-id="1cab3-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="1cab3-106">모듈을 설치하는 방법에 대한 단계는 [Microsoft Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="1cab3-106">For steps on how to install the module, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span> <span data-ttu-id="1cab3-107">최신 일반 공급 Teams PowerShell 모듈은 개인 채널 관리를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-107">The latest General Availability Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="1cab3-108">팀 구성원이 비공개 채널을 만들 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="1cab3-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="1cab3-109">팀 소유자는 구성원이 팀 설정에서 비공개 채널을 만들 수 있는 기능을 끄거나 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="1cab3-110">이렇게하려면 팀의 **Settings** 설정 탭에서 구성원이 비공개 채널을 만들 수 있도록 허용을 **끄거나 니다.**</span><span class="sxs-lookup"><span data-stu-id="1cab3-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="1cab3-111">관리자는 Graph API를 사용하여 구성원이 특정 팀에서 비공개 채널을 만들 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="1cab3-112">예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="1cab3-113">조직의 사용자가 개인 채널을 만들 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="1cab3-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="1cab3-114">관리자는 Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 개인 채널을 만들 수 있는 조직의 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1cab3-115">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="1cab3-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="1cab3-116">팀 정책을 사용하여 개인 채널을 만들 수 있는 조직의 사용자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="1cab3-117">자세한 내용은 [Teams에서 팀 정책 관리를 참조합니다.](teams-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1cab3-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1cab3-118">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="1cab3-118">Using PowerShell</span></span>

<span data-ttu-id="1cab3-119">**CsTeamsChannelsPolicy를** 사용하여 개인 채널을 만들 수 있는 조직의 사용자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="1cab3-120">정책이 할당된 사용자가 개인 채널을 만들 수 있도록 **AllowPrivateChannelCreation** 매개 변수를 **true로** 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="1cab3-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="1cab3-121">매개 변수를 **false로** 설정하면 정책이 할당된 사용자에 대한 개인 채널을 만드는 기능을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="1cab3-122">자세한 내용은 [New-CsTeamsChannelsPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1cab3-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="1cab3-123">팀 소유자를 대신하여 비공개 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="1cab3-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="1cab3-124">관리자는 PowerShell 또는 Graph API를 사용하여 팀 소유자를 대신하여 개인 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="1cab3-125">예를 들어 조직에서 개인 채널을 중앙 집중화하려는 경우 이 작업을 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1cab3-126">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="1cab3-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="1cab3-127">Graph API 사용</span><span class="sxs-lookup"><span data-stu-id="1cab3-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="1cab3-128">모든 개인 채널 메시지 목록을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="1cab3-129">보관 및 감사를 위해 개인 채널에 게시된 모든 메시지 및 응답 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="1cab3-130">Graph API를 사용하여 이 작업을 하는 방법에는 다음과 같은 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="1cab3-131">팀의 모든 비공개 채널에 대한 SharePoint URL 찾기</span><span class="sxs-lookup"><span data-stu-id="1cab3-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="1cab3-132">개인 채널의 파일에 대한 eDiscovery 또는 법적 보류를 수행하려는 경우 또는 특정 개인 채널에 파일을 저장하는 사용자 지정 앱을 빌드하려는 경우 각 개인 채널에 대해 생성된 고유한 SharePoint 사이트 모음을 쿼리하는 방법을 원할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="1cab3-133">관리자는 PowerShell 또는 Graph API 명령을 사용하여 이러한 URL을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1cab3-134">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="1cab3-134">Using PowerShell</span></span>

1. <span data-ttu-id="1cab3-135">관리자 계정으로 [SharePoint Online 관리](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 셸을 설치하고 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="1cab3-136">다음을 실행합니다. 여기서 group_id &lt; &gt; 팀의 그룹 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="1cab3-137">(팀 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="1cab3-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="1cab3-138">Graph API 사용</span><span class="sxs-lookup"><span data-stu-id="1cab3-138">Using Graph API</span></span>

<span data-ttu-id="1cab3-139">Graph Explorer를 통해 이러한 명령을 [시도할 수 있습니다.](https://developer.microsoft.com/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="1cab3-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="1cab3-140">다음을 사용하여 팀의 그룹 ID인 경우, <group_id> 팀의 개인 채널 ID 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="1cab3-141">후속 호출에서 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="1cab3-142">(팀 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="1cab3-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="1cab3-143">**요청**</span><span class="sxs-lookup"><span data-stu-id="1cab3-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="1cab3-144">**응답**</span><span class="sxs-lookup"><span data-stu-id="1cab3-144">**Response**</span></span>

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

2. <span data-ttu-id="1cab3-145">SharePoint URL을 사용하려는 각 개인 채널에 대해 다음을 요청합니다. 여기서 channel_id &lt; &gt; ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="1cab3-146">**요청**</span><span class="sxs-lookup"><span data-stu-id="1cab3-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="1cab3-147">**응답**</span><span class="sxs-lookup"><span data-stu-id="1cab3-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="1cab3-148">개인 채널에서 소유자 및 구성원의 역할 나열 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="1cab3-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="1cab3-149">개인 채널의 소유자 및 구성원을 나열하여 개인 채널의 특정 멤버를 소유자로 승격해야 하는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="1cab3-150">이 경우 조직을 떠날 개인 채널의 소유자가 있으며 개인 채널에 채널 소유권을 요구하는 관리자의 도움이 필요한 경우 이 문제를 발생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="1cab3-151">관리자는 Microsoft Teams 관리 센터, PowerShell 또는 Graph API를 사용하여 이러한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-151">As an admin, you can use the Microsoft Teams admin center, PowerShell, or Graph API to perform these actions.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1cab3-152">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="1cab3-152">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="1cab3-153">Microsoft Teams 관리 센터를 사용하여 팀 구성원을 관리하는 방법에 대한 자세한 내용은 Microsoft Teams 관리 센터에서 팀 [관리를 참조하세요.](manage-teams-in-modern-portal.md)</span><span class="sxs-lookup"><span data-stu-id="1cab3-153">To learn how to manage team members using the Microsoft Teams admin center, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1cab3-154">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="1cab3-154">Using PowerShell</span></span>

1. <span data-ttu-id="1cab3-155">다음을 실행합니다. 여기서 group_id ID는 팀의 그룹 &lt; &gt; ID이고 channel_name &lt; &gt; 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-155">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="1cab3-156">구성원을 소유자로 승격합니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-156">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="1cab3-157">Graph API 사용</span><span class="sxs-lookup"><span data-stu-id="1cab3-157">Using Graph API</span></span>

<span data-ttu-id="1cab3-158">Graph Explorer를 통해 이러한 명령을 [시도할 수 있습니다.](https://developer.microsoft.com/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="1cab3-158">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="1cab3-159">다음을 사용하세요. 여기서 group_id 팀의 그룹 ID이고 channel_id &lt; &gt; &lt; &gt; ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-159">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="1cab3-160">**요청**</span><span class="sxs-lookup"><span data-stu-id="1cab3-160">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="1cab3-161">**응답**</span><span class="sxs-lookup"><span data-stu-id="1cab3-161">**Response**</span></span>

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
2. <span data-ttu-id="1cab3-162">다음을 사용하여 멤버를 소유자로 승격합니다. 여기서 group_id, channel_id 및 ID가 이전 호출에서 &lt; &gt; &lt; &gt; &lt; &gt; 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-162">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="1cab3-163">이전 호출에서 반환된 ID와 userId는 동일하지 않습니다. 서로 &lt; &gt; &lt; &gt; 교환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cab3-163">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="1cab3-164">ID를 &lt; 사용하는지 확인 &gt;</span><span class="sxs-lookup"><span data-stu-id="1cab3-164">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="1cab3-165">**요청**</span><span class="sxs-lookup"><span data-stu-id="1cab3-165">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="1cab3-166">**응답**</span><span class="sxs-lookup"><span data-stu-id="1cab3-166">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="1cab3-167">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1cab3-167">Related topics</span></span>

- [<span data-ttu-id="1cab3-168">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="1cab3-168">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="1cab3-169">Microsoft Graph API를 사용하여 Teams에서 작업</span><span class="sxs-lookup"><span data-stu-id="1cab3-169">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="1cab3-170">채널 나열</span><span class="sxs-lookup"><span data-stu-id="1cab3-170">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="1cab3-171">채널 만들기</span><span class="sxs-lookup"><span data-stu-id="1cab3-171">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="1cab3-172">채널에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="1cab3-172">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="1cab3-173">채널에서 구성원 업데이트</span><span class="sxs-lookup"><span data-stu-id="1cab3-173">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="1cab3-174">채널에서 구성원 제거</span><span class="sxs-lookup"><span data-stu-id="1cab3-174">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
