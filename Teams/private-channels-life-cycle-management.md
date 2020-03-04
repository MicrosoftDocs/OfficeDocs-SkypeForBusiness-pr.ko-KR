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
ms.openlocfilehash: 7cd7701a66c03dfc71d89f007eae4addaed0c89a
ms.sourcegitcommit: f23c428043bb0b37c9a8600e64691bc2a1f2e874
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2020
ms.locfileid: "42403747"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="b7366-103">Microsoft 팀의 개인 채널 수명 주기 관리</span><span class="sxs-lookup"><span data-stu-id="b7366-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="b7366-104">여기에서 조직의 [개인 채널](private-channels.md) 수명 주기를 관리 하는 데 필요한 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7366-105">이 문서의 PowerShell 단계를 사용 하 여 개인 채널을 관리 하는 경우 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈을 설치 하 고 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="b7366-106">이 작업을 수행 하는 방법에 대 한 단계는 [Powershell 테스트 갤러리에서 최신 팀 PowerShell 모듈 설치](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7366-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="b7366-107">최근에 공개적으로 사용할 수 있는 팀 PowerShell 모듈 (현재 [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3))은 비공개 채널 관리를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="b7366-108">팀 구성원이 개인 채널을 만들 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="b7366-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="b7366-109">팀 소유자는 멤버가 팀 설정에서 비공개 채널을 만들 수 있도록 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="b7366-110">이렇게 하려면 팀의 **설정** 탭에서 **구성원에 게 개인 채널을 만들도록 허용**을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="b7366-111">관리자는 Graph API를 사용 하 여 구성원이 특정 팀에서 개인 채널을 만들 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="b7366-112">예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="b7366-113">조직의 사용자가 개인 채널을 만들 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="b7366-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="b7366-114">관리자는 Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 조직에서 개인 채널을 만들 수 있는 사용자를 제어 하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b7366-115">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="b7366-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b7366-116">팀 정책을 사용 하 여 조직에서 개인 채널을 만들 수 있는 사용자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="b7366-117">자세히 알아보려면 [팀에서 팀 정책 관리](teams-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7366-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b7366-118">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="b7366-118">Using PowerShell</span></span>

<span data-ttu-id="b7366-119">**CsTeamsChannelsPolicy** 를 사용 하 여 조직에서 개인 채널을 만들 수 있는 사용자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="b7366-120">**AllowPrivateChannelCreation** 매개 변수를 **true** 로 설정 하 여 정책을 할당 한 사용자가 개인 채널을 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="b7366-121">매개 변수를 **false** 로 설정 하면 정책이 할당 된 사용자에 대해 개인 채널을 만드는 기능이 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="b7366-122">자세한 내용은 [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7366-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="b7366-123">팀 소유자 대신 개인 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="b7366-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="b7366-124">관리자는 PowerShell 또는 Graph API를 사용 하 여 팀 소유자 대신 개인 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="b7366-125">예를 들어 조직에서 개인 채널을 중앙에서 만들려면이 작업을 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b7366-126">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="b7366-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="b7366-127">그래프 API 사용</span><span class="sxs-lookup"><span data-stu-id="b7366-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="b7366-128">모든 개인 채널 메시지 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="b7366-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="b7366-129">보관 및 감사 목적으로 개인 채널에 게시 된 모든 메시지 및 응답의 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="b7366-130">그래프 API를 사용 하 여이 작업을 수행 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="b7366-131">팀의 모든 개인 채널에 대 한 SharePoint Url 찾기</span><span class="sxs-lookup"><span data-stu-id="b7366-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="b7366-132">개인 채널의 파일에 대해 eDiscovery 또는 보관을 수행 하 고 있는지, 또는 특정 개인 채널에 파일을 배치 하는 lob (기간 업무) 앱을 작성 하는 경우에는 다음에 대해 생성 되는 고유한 SharePoint 사이트 모음을 쿼리 하는 방법을 원할 것입니다. 각 개인 채널.</span><span class="sxs-lookup"><span data-stu-id="b7366-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="b7366-133">관리자는 PowerShell 또는 Graph Api 명령을 사용 하 여 이러한 Url을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b7366-134">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="b7366-134">Using PowerShell</span></span>

1. <span data-ttu-id="b7366-135">관리자 계정을 사용 하 여 [SharePoint Online 관리 셸에](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="b7366-136">팀의 그룹 ID 인 &lt;group_id&gt; 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-136">Run the following, where &lt;group_id&gt; is the group ID of the team.</span></span> <span data-ttu-id="b7366-137">(팀에 대 한 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b7366-137">(You can easily find the group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="b7366-138">그래프 API 사용</span><span class="sxs-lookup"><span data-stu-id="b7366-138">Using Graph API</span></span>

<span data-ttu-id="b7366-139">[그래프 탐색기](https://developer.microsoft.com/graph/graph-explorer)를 통해 이러한 명령을 수행해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="b7366-140">다음을 사용 하 여 지정 된 팀의 개인 채널 Id 목록을 가져올 수 있으며, 여기에서 <group_id> 팀의 그룹 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="b7366-141">이후 통화에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="b7366-142">(팀에 대 한 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b7366-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="b7366-143">**요청당**</span><span class="sxs-lookup"><span data-stu-id="b7366-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="b7366-144">**응답**</span><span class="sxs-lookup"><span data-stu-id="b7366-144">**Response**</span></span>

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

2. <span data-ttu-id="b7366-145">SharePoint URL을 가져오려는 각 개인 채널에 대해 다음 요청을 수행 합니다 ( &lt;channel_id&gt; 는 채널 id).</span><span class="sxs-lookup"><span data-stu-id="b7366-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="b7366-146">**요청당**</span><span class="sxs-lookup"><span data-stu-id="b7366-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="b7366-147">**응답**</span><span class="sxs-lookup"><span data-stu-id="b7366-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="b7366-148">개인 채널의 소유자 및 구성원의 역할 나열 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="b7366-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="b7366-149">개인 채널의 특정 구성원을 소유자로 승격 해야 하는지 여부를 결정 하려면 개인 채널의 소유자와 구성원을 나열 하 고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="b7366-150">이 문제는 조직을 남겨진 개인 채널의 소유자가 있고 개인 채널에서 채널의 소유권을 요구 하는 관리자 도움말이 필요한 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="b7366-151">관리자는 PowerShell 또는 Graph Api 명령을 사용 하 여 이러한 Url을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b7366-152">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="b7366-152">Using PowerShell</span></span>

1. <span data-ttu-id="b7366-153">다음을 실행 합니다 ( &lt;여기서&gt; group_id는 팀의 그룹 id이 고 &lt;channel_name&gt; 는 채널 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> –MembershipType Private -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="b7366-154">구성원을 소유자로 승격 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> –MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="b7366-155">그래프 API 사용</span><span class="sxs-lookup"><span data-stu-id="b7366-155">Using Graph API</span></span>

<span data-ttu-id="b7366-156">[그래프 탐색기](https://developer.microsoft.com/graph/graph-explorer)를 통해 이러한 명령을 수행해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="b7366-157">팀의 그룹 ID이 &lt;고&gt; &lt;channel_id&gt; 채널 id 인 경우에는 다음을 사용 group_id.</span><span class="sxs-lookup"><span data-stu-id="b7366-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="b7366-158">**요청당**</span><span class="sxs-lookup"><span data-stu-id="b7366-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="b7366-159">**응답**</span><span class="sxs-lookup"><span data-stu-id="b7366-159">**Response**</span></span>

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
2.  <span data-ttu-id="b7366-160">다음을 사용 하 여 구성원을 소유자로 승격 &lt;합니다 (group_id&gt;, &lt;channel_id&gt;, &lt;id&gt; 는 이전 호출에서 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="b7366-161">이전 호출 &lt;에서&gt; 반환 &lt;된&gt; id와 userId는 같지 않으며 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="b7366-162">Id &lt;&gt;를 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="b7366-163">**요청당**</span><span class="sxs-lookup"><span data-stu-id="b7366-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="b7366-164">**응답**</span><span class="sxs-lookup"><span data-stu-id="b7366-164">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="b7366-165">팀 Powershell 모듈</span><span class="sxs-lookup"><span data-stu-id="b7366-165">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="b7366-166">PowerShell 테스트 갤러리에서 최신 팀 PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="b7366-166">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="b7366-167">최근에 공개적으로 사용할 수 있는 팀 PowerShell 모듈 (현재 [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3))은 비공개 채널 관리를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-167">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span> <span data-ttu-id="b7366-168">이 단계를 사용 하 여 PowerShell 테스트 갤러리에서 개인 채널 지원 (현재 1.0.18)을 사용 하 여 최신 버전의 팀 PowerShell 모듈을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-168">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.18) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="b7366-169">PowerShell 테스트 갤러리에서 팀 PowerShell 모듈을 공용 PowerShell 갤러리의 모듈 버전과 나란히 설치 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b7366-169">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="b7366-170">이 단계에 따라 먼저 공용 PowerShell 갤러리에서 팀 PowerShell 모듈을 제거 하 고 PowerShell 테스트 갤러리에서 최신 버전의 모듈을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-170">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="b7366-171">모든 기존 PowerShell 세션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-171">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="b7366-172">Windows PowerShell 모듈의 새 인스턴스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-172">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="b7366-173">공용 PowerShell 갤러리에서 팀 PowerShell 모듈을 제거 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-173">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="b7366-174">모든 기존 PowerShell 세션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-174">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="b7366-175">Windows PowerShell 모듈을 다시 시작 하 고 다음을 실행 하 여 PowerShell 테스트 갤러리를 신뢰할 수 있는 원본으로 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-175">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="b7366-176">PowerShell 테스트 갤러리에서 최신 팀 PowerShell 모듈을 설치 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-176">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="b7366-177">다음을 실행 하 여 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈이 성공적으로 설치 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-177">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="b7366-178">PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈로 업데이트</span><span class="sxs-lookup"><span data-stu-id="b7366-178">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="b7366-179">PowerShell 테스트 갤러리에서 팀 PowerShell 모듈을 이미 설치한 경우 다음 단계를 사용 하 여 최신 버전으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-179">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="b7366-180">모든 기존 PowerShell 세션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-180">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="b7366-181">Windows PowerShell 모듈의 새 인스턴스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-181">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="b7366-182">다음을 실행 하 여 PowerShell 테스트 갤러리에서 현재 설치 된 버전의 팀 PowerShell 모듈을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-182">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="b7366-183">다음을 실행 하 여 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈이 성공적으로 설치 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7366-183">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="b7366-184">관련 주제</span><span class="sxs-lookup"><span data-stu-id="b7366-184">Related topics</span></span>

- [<span data-ttu-id="b7366-185">팀 PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="b7366-185">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="b7366-186">Microsoft Graph API를 사용 하 여 팀과 공동 작업</span><span class="sxs-lookup"><span data-stu-id="b7366-186">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="b7366-187">목록 채널</span><span class="sxs-lookup"><span data-stu-id="b7366-187">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="b7366-188">채널 만들기</span><span class="sxs-lookup"><span data-stu-id="b7366-188">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="b7366-189">채널에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="b7366-189">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="b7366-190">채널의 구성원 업데이트</span><span class="sxs-lookup"><span data-stu-id="b7366-190">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="b7366-191">채널에서 구성원 제거</span><span class="sxs-lookup"><span data-stu-id="b7366-191">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
