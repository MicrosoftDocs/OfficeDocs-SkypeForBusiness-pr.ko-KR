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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="8aac6-103">Microsoft 팀의 개인 채널 수명 주기 관리</span><span class="sxs-lookup"><span data-stu-id="8aac6-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="8aac6-104">여기에서 조직의 [개인 채널](private-channels.md) 수명 주기를 관리 하는 데 필요한 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8aac6-105">이 문서의 PowerShell 단계를 사용 하 여 개인 채널을 관리 하는 경우 [Powershell 테스트 갤러리](https://www.poshtestgallery.com/packages/MicrosoftTeams/)에서 팀 powershell 모듈의 최신 시험판 버전을 설치 하 고 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="8aac6-106">모듈을 설치 하는 방법에 대 한 단계는 [팀 PowerShell 모듈의 시험판 버전 설치](install-prerelease-teams-powershell-module.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8aac6-106">For steps on how to install the module, see [Install the pre-release version of the Teams PowerShell module](install-prerelease-teams-powershell-module.md).</span></span> <span data-ttu-id="8aac6-107">공개적으로 사용할 수 있는 팀 PowerShell 모듈의 최신 버전은 비공개 채널 관리를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-107">The latest publicly available version of the Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="8aac6-108">팀 구성원이 개인 채널을 만들 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="8aac6-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="8aac6-109">팀 소유자는 멤버가 팀 설정에서 비공개 채널을 만들 수 있도록 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="8aac6-110">이렇게 하려면 팀의 **설정** 탭에서 **구성원에 게 개인 채널을 만들도록 허용**을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="8aac6-111">관리자는 Graph API를 사용 하 여 구성원이 특정 팀에서 개인 채널을 만들 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="8aac6-112">예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="8aac6-113">조직의 사용자가 개인 채널을 만들 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="8aac6-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="8aac6-114">관리자는 Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 조직에서 개인 채널을 만들 수 있는 사용자를 제어 하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8aac6-115">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="8aac6-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="8aac6-116">팀 정책을 사용 하 여 조직에서 개인 채널을 만들 수 있는 사용자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="8aac6-117">자세히 알아보려면 [팀에서 팀 정책 관리](teams-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8aac6-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8aac6-118">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8aac6-118">Using PowerShell</span></span>

<span data-ttu-id="8aac6-119">**CsTeamsChannelsPolicy** 를 사용 하 여 조직에서 개인 채널을 만들 수 있는 사용자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="8aac6-120">**AllowPrivateChannelCreation** 매개 변수를 **true** 로 설정 하 여 정책을 할당 한 사용자가 개인 채널을 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="8aac6-121">매개 변수를 **false** 로 설정 하면 정책이 할당 된 사용자에 대해 개인 채널을 만드는 기능이 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="8aac6-122">자세한 내용은 [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8aac6-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="8aac6-123">팀 소유자 대신 개인 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="8aac6-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="8aac6-124">관리자는 PowerShell 또는 Graph API를 사용 하 여 팀 소유자 대신 개인 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="8aac6-125">예를 들어 조직에서 개인 채널을 중앙에서 만들려면이 작업을 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8aac6-126">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8aac6-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="8aac6-127">그래프 API 사용</span><span class="sxs-lookup"><span data-stu-id="8aac6-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="8aac6-128">모든 개인 채널 메시지 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="8aac6-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="8aac6-129">보관 및 감사 목적으로 개인 채널에 게시 된 모든 메시지 및 응답의 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="8aac6-130">그래프 API를 사용 하 여이 작업을 수행 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="8aac6-131">팀의 모든 개인 채널에 대 한 SharePoint Url 찾기</span><span class="sxs-lookup"><span data-stu-id="8aac6-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="8aac6-132">개인 채널의 파일에 대해 eDiscovery 또는 보관을 수행 하려는 경우 또는 특정 개인 채널에 파일을 배치 하는 사용자 지정 앱을 빌드 하려는 경우 각 개인 채널에 대해 생성 되는 고유한 SharePoint 사이트 모음을 쿼리 하는 방법을 원하는 경우를 원할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="8aac6-133">관리자는 PowerShell 또는 Graph Api 명령을 사용 하 여 이러한 Url을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8aac6-134">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8aac6-134">Using PowerShell</span></span>

1. <span data-ttu-id="8aac6-135">관리자 계정을 사용 하 여 [SharePoint Online 관리 셸에](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="8aac6-136">&lt;팀의 그룹 id 인 group_id 다음을 실행 합니다 &gt; .</span><span class="sxs-lookup"><span data-stu-id="8aac6-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="8aac6-137">(팀에 대 한 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="8aac6-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="8aac6-138">그래프 API 사용</span><span class="sxs-lookup"><span data-stu-id="8aac6-138">Using Graph API</span></span>

<span data-ttu-id="8aac6-139">[그래프 탐색기](https://developer.microsoft.com/graph/graph-explorer)를 통해 이러한 명령을 수행해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="8aac6-140">다음을 사용 하 여 지정 된 팀의 개인 채널 Id 목록을 가져올 수 있으며, 여기에서 <group_id> 팀의 그룹 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="8aac6-141">이후 통화에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="8aac6-142">(팀에 대 한 링크에서 그룹 ID를 쉽게 찾을 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="8aac6-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="8aac6-143">**요청당**</span><span class="sxs-lookup"><span data-stu-id="8aac6-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="8aac6-144">**응답**</span><span class="sxs-lookup"><span data-stu-id="8aac6-144">**Response**</span></span>

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

2. <span data-ttu-id="8aac6-145">SharePoint URL을 가져오려는 각 개인 채널에 대해 다음 요청을 수행 합니다 ( &lt; channel_id &gt; 는 채널 id).</span><span class="sxs-lookup"><span data-stu-id="8aac6-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="8aac6-146">**요청당**</span><span class="sxs-lookup"><span data-stu-id="8aac6-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="8aac6-147">**응답**</span><span class="sxs-lookup"><span data-stu-id="8aac6-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="8aac6-148">개인 채널의 소유자 및 구성원의 역할 나열 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="8aac6-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="8aac6-149">개인 채널의 특정 구성원을 소유자로 승격 해야 하는지 여부를 결정 하려면 개인 채널의 소유자와 구성원을 나열 하 고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="8aac6-150">이 문제는 조직을 남겨진 개인 채널의 소유자가 있고 개인 채널에서 채널의 소유권을 요구 하는 관리자 도움말이 필요한 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="8aac6-151">관리자는 PowerShell 또는 Graph Api 명령을 사용 하 여 이러한 Url을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8aac6-152">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8aac6-152">Using PowerShell</span></span>

1. <span data-ttu-id="8aac6-153">다음을 실행 합니다 (여기서 &lt; group_id &gt; 는 팀의 그룹 id이 고 &lt; channel_name는 &gt; 채널 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="8aac6-154">구성원을 소유자로 승격 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="8aac6-155">그래프 API 사용</span><span class="sxs-lookup"><span data-stu-id="8aac6-155">Using Graph API</span></span>

<span data-ttu-id="8aac6-156">[그래프 탐색기](https://developer.microsoft.com/graph/graph-explorer)를 통해 이러한 명령을 수행해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="8aac6-157">&lt; &gt; 팀의 그룹 id이 고 &lt; channel_id &gt; 채널 id 인 경우에는 다음을 사용 group_id.</span><span class="sxs-lookup"><span data-stu-id="8aac6-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="8aac6-158">**요청당**</span><span class="sxs-lookup"><span data-stu-id="8aac6-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="8aac6-159">**응답**</span><span class="sxs-lookup"><span data-stu-id="8aac6-159">**Response**</span></span>

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
2. <span data-ttu-id="8aac6-160">다음을 사용 하 여 구성원을 소유자로 승격 합니다 ( &lt; group_id &gt; , &lt; channel_id &gt; , &lt; id &gt; 는 이전 호출에서 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="8aac6-161">&lt; &gt; &lt; 이전 호출에서 반환 된 id와 userId는 &gt; 같지 않으며 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="8aac6-162">Id를 사용 하 고 있는지 확인 &lt; &gt; 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aac6-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="8aac6-163">**요청당**</span><span class="sxs-lookup"><span data-stu-id="8aac6-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="8aac6-164">**응답**</span><span class="sxs-lookup"><span data-stu-id="8aac6-164">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="8aac6-165">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8aac6-165">Related topics</span></span>

- [<span data-ttu-id="8aac6-166">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="8aac6-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="8aac6-167">Microsoft Graph API를 사용하여 Teams에서 작업</span><span class="sxs-lookup"><span data-stu-id="8aac6-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="8aac6-168">목록 채널</span><span class="sxs-lookup"><span data-stu-id="8aac6-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="8aac6-169">채널 만들기</span><span class="sxs-lookup"><span data-stu-id="8aac6-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="8aac6-170">채널에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="8aac6-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="8aac6-171">채널의 구성원 업데이트</span><span class="sxs-lookup"><span data-stu-id="8aac6-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="8aac6-172">채널에서 구성원 제거</span><span class="sxs-lookup"><span data-stu-id="8aac6-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
