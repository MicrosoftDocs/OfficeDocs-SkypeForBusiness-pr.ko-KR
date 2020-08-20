---
title: eDiscovery 콘텐츠 조사
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 법률 절차에 대한 모든 전자 저장 정보를 제출해야 하는 경우와 같이 eDiscovery를 수행해야 하는 경우 수행할 작업에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4679d8ed59ab8eec0fb856961f646d1f20049ff3
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814114"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="eef01-103">Microsoft Teams에서 콘텐츠에 대한 eDiscovery 조사 조사</span><span class="sxs-lookup"><span data-stu-id="eef01-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="eef01-104">대기업은 종종 ESI(전자 저장 정보)를 제출하는 합리적인 법률 의문 사항으로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="eef01-105">eDiscovery 조사 중에 Microsoft Teams 콘텐츠를 검색하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="eef01-106">개요</span><span class="sxs-lookup"><span data-stu-id="eef01-106">Overview</span></span>

<span data-ttu-id="eef01-107">모든 Microsoft Teams 1:1 또는 그룹 채팅은 해당 사용자의 사서함을 통해 업무를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="eef01-108">모든 표준 채널 메시지는 팀을 나타내는 그룹 사서함으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="eef01-109">표준 채널에서 업로드한 파일은 SharePoint Online 및 비즈니스용 OneDrive의 eDiscovery 기능에 대해 다됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="eef01-110">비공개 채널에서 메시지와 [파일을 보낸 후에는 표준](private-channels.md) 채널에서와 다르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="eef01-111">자세한 내용은 [비공개 채널e의 eDiscovery를 참조하세요.](#ediscovery-of-private-channels)</span><span class="sxs-lookup"><span data-stu-id="eef01-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="eef01-112">모든 Teams 콘텐츠를 Discover로 기능할 수 있는 것은 아닌 경우.</span><span class="sxs-lookup"><span data-stu-id="eef01-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="eef01-113">다음 표에서는 eDiscovery를 통해 찾을 수 있는 콘텐츠 형식을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-113">The following table shows the content types that can be located through eDiscovery.</span></span>

| <span data-ttu-id="eef01-114">콘텐츠 형식</span><span class="sxs-lookup"><span data-stu-id="eef01-114">Content type</span></span> | <span data-ttu-id="eef01-115">eDiscoverable</span><span class="sxs-lookup"><span data-stu-id="eef01-115">eDiscoverable</span></span> | <span data-ttu-id="eef01-116">참고</span><span class="sxs-lookup"><span data-stu-id="eef01-116">Notes</span></span> |
|:--- | --- |:--- |
| <span data-ttu-id="eef01-117">Teams 채팅 메시지</span><span class="sxs-lookup"><span data-stu-id="eef01-117">Teams chat messages</span></span> | <span data-ttu-id="eef01-118">예</span><span class="sxs-lookup"><span data-stu-id="eef01-118">Yes</span></span> |  |
| <span data-ttu-id="eef01-119">비공개 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="eef01-119">Private channel messages</span></span> | <span data-ttu-id="eef01-120">예</span><span class="sxs-lookup"><span data-stu-id="eef01-120">Yes</span></span> | |
| <span data-ttu-id="eef01-121">채널 이름</span><span class="sxs-lookup"><span data-stu-id="eef01-121">Name of channel</span></span> | <span data-ttu-id="eef01-122">아니요</span><span class="sxs-lookup"><span data-stu-id="eef01-122">No</span></span> | |
| <span data-ttu-id="eef01-123">모임 메신저 대화</span><span class="sxs-lookup"><span data-stu-id="eef01-123">Meeting IM conversations</span></span> | <span data-ttu-id="eef01-124">예</span><span class="sxs-lookup"><span data-stu-id="eef01-124">Yes</span></span> | |
| <span data-ttu-id="eef01-125">모임 메타데이터<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="eef01-125">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="eef01-126">예</span><span class="sxs-lookup"><span data-stu-id="eef01-126">Yes</span></span> |  |
| <span data-ttu-id="eef01-127">편집된 메시지</span><span class="sxs-lookup"><span data-stu-id="eef01-127">Edited messages</span></span> | <span data-ttu-id="eef01-128">예</span><span class="sxs-lookup"><span data-stu-id="eef01-128">Yes</span></span> | <span data-ttu-id="eef01-129">사용자가 보류 중인 경우 이전 버전의 편집된 메시지는 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-129">If the user is on hold, previous versions of edited messages are preserved.</span></span> |
| <span data-ttu-id="eef01-130">이모지, GMO, 스티커</span><span class="sxs-lookup"><span data-stu-id="eef01-130">Emojis, GIFs, stickers</span></span> | <span data-ttu-id="eef01-131">예</span><span class="sxs-lookup"><span data-stu-id="eef01-131">Yes</span></span> | |
| <span data-ttu-id="eef01-132">코드 조각</span><span class="sxs-lookup"><span data-stu-id="eef01-132">Code snippets</span></span> | <span data-ttu-id="eef01-133">아니요</span><span class="sxs-lookup"><span data-stu-id="eef01-133">No</span></span> | |
| <span data-ttu-id="eef01-134">채팅 링크</span><span class="sxs-lookup"><span data-stu-id="eef01-134">Chat links</span></span> | <span data-ttu-id="eef01-135">예</span><span class="sxs-lookup"><span data-stu-id="eef01-135">Yes</span></span> | |
| <span data-ttu-id="eef01-136">다시 작음(예: 듣기, 하트 등)</span><span class="sxs-lookup"><span data-stu-id="eef01-136">Reactions (likes, hearts, and so on)</span></span> | <span data-ttu-id="eef01-137">아니요</span><span class="sxs-lookup"><span data-stu-id="eef01-137">No</span></span> | |
| <span data-ttu-id="eef01-138">인라인 이미지</span><span class="sxs-lookup"><span data-stu-id="eef01-138">Inline images</span></span> | <span data-ttu-id="eef01-139">예</span><span class="sxs-lookup"><span data-stu-id="eef01-139">Yes</span></span> | |
| <span data-ttu-id="eef01-140">테이블</span><span class="sxs-lookup"><span data-stu-id="eef01-140">Tables</span></span> | <span data-ttu-id="eef01-141">예</span><span class="sxs-lookup"><span data-stu-id="eef01-141">Yes</span></span> | |
| <span data-ttu-id="eef01-142">제목</span><span class="sxs-lookup"><span data-stu-id="eef01-142">Subject</span></span> | <span data-ttu-id="eef01-143">예</span><span class="sxs-lookup"><span data-stu-id="eef01-143">Yes</span></span> | |
| <span data-ttu-id="eef01-144">시/따옴표</span><span class="sxs-lookup"><span data-stu-id="eef01-144">Quotes</span></span> | <span data-ttu-id="eef01-145">예</span><span class="sxs-lookup"><span data-stu-id="eef01-145">Yes</span></span> | <span data-ttu-id="eef01-146">인용된 콘텐츠를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-146">Quoted content is searchable.</span></span> <span data-ttu-id="eef01-147">그러나 검색 결과로는 콘텐츠가 할당되었음을 나타내지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-147">However, search results don't indicate that the content was quoted.</span></span> |
| <span data-ttu-id="eef01-148">오디오 녹음</span><span class="sxs-lookup"><span data-stu-id="eef01-148">Audio recordings</span></span> | <span data-ttu-id="eef01-149">아니요</span><span class="sxs-lookup"><span data-stu-id="eef01-149">No</span></span> | |

<span data-ttu-id="eef01-150"><sup>모임</sup> 메타데이터에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-150"><sup>1</sup> Meeting metadata includes the following:</span></span>

- <span data-ttu-id="eef01-151">모임 또는 통화 시작 시간 및 종료 시간 및 기간</span><span class="sxs-lookup"><span data-stu-id="eef01-151">Meeting or call start and end time, and duration</span></span>
- <span data-ttu-id="eef01-152">각 참가자에 대한 통화/모임 참가 및 종료</span><span class="sxs-lookup"><span data-stu-id="eef01-152">Call/Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="eef01-153">VOIP 참가/호출</span><span class="sxs-lookup"><span data-stu-id="eef01-153">VOIP join/calls</span></span>
- <span data-ttu-id="eef01-154">익명 참가</span><span class="sxs-lookup"><span data-stu-id="eef01-154">Anonymous join</span></span>
- <span data-ttu-id="eef01-155">페더레이스 사용자 참가</span><span class="sxs-lookup"><span data-stu-id="eef01-155">Federated user join</span></span>
- <span data-ttu-id="eef01-156">게스트 사용자 참가</span><span class="sxs-lookup"><span data-stu-id="eef01-156">Guest user join</span></span>

<span data-ttu-id="eef01-157">이미지는 메타데이터 예제를 보여 주는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-157">The image shows an example of the metadata.</span></span>

![이미지는 CVR 레코드 모임 메타데이터입니다.](media/conversationOption3.png)

<span data-ttu-id="eef01-159">다음은 모임 중에 참가자 간의 메신저 대화의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-159">Here's an example of IM conversation between participants during the meeting.</span></span>

![이미지는 참가자들 간의 대화입니다.](media/MeetingIMConversations.png)

![이미지는 참가자들 간의 대화입니다.](media/MeetingImConversation2.png)

<span data-ttu-id="eef01-162">Microsoft Teams 콘텐츠에 대한 eDiscovery 조사를 수행하려면 [Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)시작에서 1단계를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="eef01-162">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [Get started with Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="eef01-163">Microsoft Teams 데이터는 Excel eDiscovery 내보내기 출력에서 메신저 대화 또는 대화로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-163">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="eef01-164">Outlook에서 파일을 `.pst` 열어 내보낸 후에 해당 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-164">You can open the `.pst` file in Outlook to view those messages after export.</span></span>

<span data-ttu-id="eef01-165">팀에 대한 .pst 파일을 보고 있는 경우 모든 대화가 팀 채팅 폴더의 대화 내용 아래에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-165">When viewing the .pst file for the team, all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="eef01-166">메시지 제목에는 팀 이름과 채널 이름이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-166">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="eef01-167">예를 들어 아래 이미지는 제조 사양 팀의 Project 7 표준 채널을 메시지를 받는 부동소의 메시지를 보여주고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-167">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![Outlook 사용자 사서함에 있는 팀 채팅 폴더 스크린샷](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="eef01-169">사용자의 사서함에 있는 비공개 채팅은 팀 채팅 폴더 아래에 대화 내용 아래에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-169">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="eef01-170">eDiscovery of pvate Channels</span><span class="sxs-lookup"><span data-stu-id="eef01-170">eDiscovery of private channels</span></span>

<span data-ttu-id="eef01-171">비공개 채널에 전송된 메시지 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-171">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="eef01-172">레코드 제목은 출처 비공개 채널을 표시하도록 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-172">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="eef01-173">각 비공개 채널에는 상위 팀 사이트와 별도로 별도의 SharePoint 사이트 모음이 있으므로 비공개 채널의 파일은 상위 팀과 개별적으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-173">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="eef01-174">Teams는 팀 내의 단일 채널에 대한 eDiscovery 검색을 지원하지 않으므로 전체 팀이 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-174">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="eef01-175">비공개 채널에서 콘텐츠를 eDiscovery 콘텐츠를 검색하려면 팀 전반에서 검색하고(파일 포함) 및 비공개 채널 구성원의 사서함(메시지를 포함하기 위한) 개인 채널 구성원의 사서함을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-175">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="eef01-176">다음 단계에 따라 eDiscovery 검색에 포함할 개인 채널에서 파일 및 메시지를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-176">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="eef01-177">eDiscovery 검색에 개인 채널 파일 포함</span><span class="sxs-lookup"><span data-stu-id="eef01-177">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="eef01-178">이러한 단계를 수행하기 전에 [SharePoint Online 관리 셸을 설치하고 SharePoint Online에 연결합니다.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="eef01-178">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="eef01-179">다음을 실행하여 팀의 비공개 채널과 연결된 모든 SharePoint 사이트 모음 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-179">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="eef01-180">다음 PowerShell 스크립트를 실행하여 팀의 비공개 채널과 연결된 모든 SharePoint 사이트 모음 URL 목록과 상위 팀 ID의 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-180">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="eef01-181">각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행하여 모든 적정 비공개 채널 사이트를 식별합니다. 여기에서 $groupID 팀의 그룹 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-181">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="eef01-182">eDiscovery 검색에 개인 채널 메시지 포함</span><span class="sxs-lookup"><span data-stu-id="eef01-182">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="eef01-183">이러한 단계를 수행하기 전에 최신 [버전의 Teams PowerShell 모듈이 설치되어 있는지 확인합니다.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="eef01-183">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="eef01-184">다음을 실행하여 팀의 비공개 채널 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-184">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="eef01-185">다음을 실행하여 비공개 채널 구성원 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-185">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="eef01-186">eDiscovery 검색 쿼리의 일부로 팀에 있는 각 비공개 채널의 모든 구성원에 대한 사서함을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-186">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="eef01-187">고급 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="eef01-187">Advanced eDiscovery</span></span>

<span data-ttu-id="eef01-188">일부 Microsoft Teams 콘텐츠는 고급 [eDiscovery 워크플로를 사용하여 검색하고 보관할 수 있습니다.](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)</span><span class="sxs-lookup"><span data-stu-id="eef01-188">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="eef01-189">eDiscovery는 단일 검색, 보관 및 내보내기 기능으로 이어지는 여러 사용자만 고급 eDiscovery는 데이터 원본을 식별하고 해당 콘텐츠를 분석하는 데 더 많은 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-189">While eDiscovery provides a range of search, hold, and export functionality, advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="eef01-190">Teams 콘텐츠에 대한 고급 eDiscovery 중요 도우미 워크플로</span><span class="sxs-lookup"><span data-stu-id="eef01-190">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="eef01-191">오토토마의는 다양한 팀의 구성원일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-191">Custodians might be a member of various teams.</span></span> <span data-ttu-id="eef01-192">이러한 대중어와 연관된 Teams 콘텐츠를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-192">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="eef01-193">구현워자 워크플로의 배경 및 지침은 [고급 eDiscovery 워크플로를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)</span><span class="sxs-lookup"><span data-stu-id="eef01-193">For background and instructions on the custodian workflow, see [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span>

<span data-ttu-id="eef01-194">에버디아어를 추가한 후에 다음 단추를 **클릭하고** 추가 단추를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eef01-194">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="eef01-195">그런 다음 추가 위치를 선택하라는 창에 55개의 추가 위치를 선택하면 해당 보유자의 구성원 자격과 해당 데이터에 해당하는 SharePoint 사이트 위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-195">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="eef01-196">이러한 모든 데이터 원본과 팀에서 eDiscovery에 사용할 콘텐츠를 선택한 다음 해당 사용자와 보류로 식별한 모든 데이터 원본을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-196">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="eef01-197">Exchange 콘텐츠, OneDrive 콘텐츠 또는 둘 다를 포함할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-197">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="eef01-198">Exchange 콘텐츠에는 사용자의 사서함에 포함된 모든 응용 프로그램 콘텐츠(예: 전자 메일, 해당 사서함에 저장된 Teams 콘텐츠 등)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-198">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="eef01-199">OneDrive 콘텐츠에는 사용자의 콘텐츠를 포함할 수 있지만 1:1 채팅, 1:N 채팅, 채팅과 같은 OneDrive에 저장된 모든 Teams 콘텐츠도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-199">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="eef01-200">또한 대리인 팀을 연결할 수 있는 옵션이 있으므로 채널 채팅 메시지와 보상자에 액세스하는 사람이 액세스할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-200">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="eef01-201">또한 다른 팀은 또한 인보자와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-201">Additionally, any other team can be associated with a custodian.</span></span> <span data-ttu-id="eef01-202">자세한 내용은 [고급 eDiscovery 사례에 오고항목 추가를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)</span><span class="sxs-lookup"><span data-stu-id="eef01-202">For more information, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

> [!NOTE]
> <span data-ttu-id="eef01-203">비공개 채널에서 메시지와 [파일을 보낸 후에는 표준](private-channels.md) 채널에서와 다르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-203">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="eef01-204">자세한 내용은 [비공개 채널e의 eDiscovery를 참조하세요.](#ediscovery-of-private-channels)</span><span class="sxs-lookup"><span data-stu-id="eef01-204">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="eef01-205">데이터 원본 보류</span><span class="sxs-lookup"><span data-stu-id="eef01-205">Placing a data source on hold</span></span>

<span data-ttu-id="eef01-206">보유자로 지정할 특정 사용자가 없는 경우 전체 데이터 원본을 보류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-206">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="eef01-207">보류에 대한 자세한 내용은 [고급 eDiscovery에서 보류 관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)</span><span class="sxs-lookup"><span data-stu-id="eef01-207">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="eef01-208">Teams 콘텐츠를 보류하려면 보류에 포함할 위치를 모두 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-208">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="eef01-209">사용자가 콘텐츠를 삭제하거나 변경하더라도 보류에 포함한 콘텐츠의 사본이 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-209">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="eef01-210">키워드, 날짜 범위, 만든 이, 기타 여러 조건을 기준으로 보류 조건을 설정하기 위한 선택 쿼리를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-210">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="eef01-211">키워드를 지정하지 하면 해당 데이터 원본의 모든 항목이 보존되는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-211">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="eef01-212">고급 eDiscovery 검색</span><span class="sxs-lookup"><span data-stu-id="eef01-212">Advanced eDiscovery searches</span></span>

<span data-ttu-id="eef01-213">Teams 콘텐츠를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-213">Teams content can also be searched.</span></span> <span data-ttu-id="eef01-214">검색에 대한 자세한 내용은 [고급 eDiscovery에서 사례에 대한 데이터수집을 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)</span><span class="sxs-lookup"><span data-stu-id="eef01-214">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="eef01-215">검색 쿼리와 일치하는 메시지가 없더라도 전체 대화가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-215">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="eef01-216">검색 쿼리를 만들 때 에대한자를 선택하여 이미 선택한 모든 출처를 검색하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-216">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="eef01-217">사용자에게 매핑되지 않은 Teams 사이트와 같은 바시처리스트 원본을 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-217">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="eef01-218">선택적 쿼리를 Teams 콘텐츠 내에서 검색 범위를 좁용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-218">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="eef01-219">검색을 만들어 선택하고 나면 선택한 검색에 대해 수행할 수 있는 추가 세부 정보와 작업이 나열된 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-219">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="eef01-220">**통계 단추를** 클릭하면 위치 유형에 맞는 분석, 콘텐츠의 원래 소스, 그룹 사서함의 콘텐츠 위치, 개별 사용자 사서함 또는 SharePoint 사이트 등 검색에 대한 통계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-220">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="eef01-221">따라서 검색 결과에 어떤 출처가 적으로 어떤 원인이 있는지 분석 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-221">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="eef01-222">또한 쿼리 **보기도 사용할** 수 있도록 쿼리 보기라고 표시되어 있어 결과에 어떤 개별 키워드가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-222">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="eef01-223">검색을 완료하고 나면 결과 추가를 클릭하여 결과를 **검토하며** 검토 집합에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-223">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="eef01-224">검토 집합에 대한 자세한 내용은 이 문서의 [뒷부분에 나오는 고급 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) 및 [리뷰 설정 워크플로에서](#review-sets-workflow) 검토 설정 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eef01-224">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="eef01-225">일반 검토 집합 및 대화 검토 집합</span><span class="sxs-lookup"><span data-stu-id="eef01-225">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="eef01-226">검토 집합에 검색을 추가할 때 정상 검토 집합 또는 대화 검토 집합 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-226">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="eef01-227">일반적인 검토 집합은 내보내기와 비사유합니다. Teams 콘텐츠에 대한 `.msg` 개별 파일을 제공하고 기본 보기에 콘텐츠를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-227">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="eef01-228">다른 소프트웨어 도구를 사용하여 나중에 파일을 다시 처리하려는 경우 일반적인 검토 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-228">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="eef01-229">대화 검토 목록은 대화에 더욱 관부분적이고 시각적인 보기를 제공합니다. 관련 메시지를 올바된 순서로 함께 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-229">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

![대화 검토 집합 스크린샷](media/conversationOptions2.png)

<span data-ttu-id="eef01-231">다시 알림과 같은 기능은 두 유형의 검토 집합에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-231">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="eef01-232">검토 설정에 대한 자세한 내용은 [고급 eDiscovery에서의 대화를 검토하세요.](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)</span><span class="sxs-lookup"><span data-stu-id="eef01-232">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="eef01-233">컬렉션 옵션</span><span class="sxs-lookup"><span data-stu-id="eef01-233">Collection options</span></span>

<span data-ttu-id="eef01-234">검토 설정에 추가하면 대화 검색 옵션 및 Teams 대화를 비롯하여 창의 컬렉션 **Conversation Retrieval Options** 옵션 섹션에서 여러 옵션을 사용할 **수 있습니다.** **Collection Options**</span><span class="sxs-lookup"><span data-stu-id="eef01-234">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="eef01-235">이러한 옵션을 활성화하면 검토 설정에 포함된 모든 개별 Teams 메시지에 주위의 텍스트수정 메시지도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-235">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="eef01-236">예를 들어 쿼리가 매우 특정이며 한 메시지만 결과값으로 반환되는 경우 이러한 옵션을 사용하도록 설정하면 여러 메시지가 쿼리와 일치하는 메시지를 전달하고 후바로 팔로우할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-236">For example, if your query is very specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="eef01-237">많은 논리 조건을 사용하여 메시지가 쿼리와 일치하는 메시지에 특정 인식을 제공하는지 여부를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-237">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="eef01-238">예를 들어 Teams 콘텐츠의 경우 이러한 옵션을 사용하도록 설정하면 메시지가 스레드되는 방식으로 인해 상위 메시지와 모든 자식 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-238">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="eef01-239">메시지 타임스탬프도 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-239">Message time stamps are also checked.</span></span> <span data-ttu-id="eef01-240">메시지가 쿼리와 일치하는 경우, 4시간 이내에 또는 4시간 이내에 이어지는 메시지는 대화에 포함되며 결과에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-240">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="eef01-241">검색 쿼리와 일치하는 상황별 메시지가 반환될 특정 메시지가 검색 쿼리에 반환될지를 특정게 하는 경우 이러한 옵션을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-241">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="eef01-242">모든 콘텐츠를 수집하거나 더 많은 메시지가 쿼리 결과로 반환되도록 검색 범위의 날짜 범위를 넓히거나 검색 범위의 범위를 넓히게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-242">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="eef01-243">설정 워크플로 검토</span><span class="sxs-lookup"><span data-stu-id="eef01-243">Review sets workflow</span></span>

<span data-ttu-id="eef01-244">검토 설정 탭을 클릭하면 기존 검토 집합을 보거나 새 목록을 **만들 수** 있습니다. 검토 집합에 대한 자세한 내용은 [고급 eDiscovery에서 리뷰 설정 관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)</span><span class="sxs-lookup"><span data-stu-id="eef01-244">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="eef01-245">문서 외에도 검토를 설정할 전자 메일, Teams 메시지 Yammer, 기타 콘텐츠를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-245">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="eef01-246">검토 집합 내에서 콘텐츠 검색 및 사용자 지정 쿼리 작성 등과 같이 다른 상황에서 수행할 수 있는 것은 다수의 동일한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-246">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="eef01-247">이러한 작업은 검토 집합에 추가된 항목에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-247">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="eef01-248">검토 **설정 관리 단추는** 분석, 요약 보고, 추가된 로드 집합 수 등의 추가 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-248">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="eef01-249">데이터의 시각화 및 차트에 액세스하려면 오른쪽 **위에서** \> **개별 결과 검색 프로필** 보기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-249">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="eef01-250">이 차트의 방사를 클릭하여 쿼리하려는 콘텐츠의 형식을 대화형으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-250">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="eef01-251">예를 들어 Teams 콘텐츠만 쿼리하라고 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-251">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="eef01-252">이러한 쿼리를 수동으로 작성하는 것과 마찬가지로 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-252">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="eef01-253">요약 보기, 텍스트 보기 및 주의 주기 탭</span><span class="sxs-lookup"><span data-stu-id="eef01-253">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="eef01-254">검토 설정에서 Teams 대화를 클릭하면 Teams 대화가 **Summary view**전체 Teams 대화가 개별적으로 조작할 수 있는 메시지 목록으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-254">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="eef01-255">메시지의 오른쪽에 있는 아래쪽 화살표를 클릭하여 메시지 세부 정보를 보거나 개별 파일을 다운로드할 수 있는 상황에 맞는 메뉴를 `.msg` 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-255">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="eef01-256">메시지 세부 정보를 클릭하면 메타데이터 또는 메시지의 전체 메타데이터에 대한 요약이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-256">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="eef01-257">PDF를 다운로드하려면 요약 보기 오른쪽 위에 있는 다운로드 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-257">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="eef01-258">텍스트 **보기 탭을** 클릭하여 Teams 대화와 추출된 텍스트의 일반 텍스트 보기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-258">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="eef01-259">이 일반 텍스트 콘텐츠는 내보내기에 적제하고 다른 소프트웨어 도구를 사용하여 쉽게 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-259">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="eef01-260">주제 **기능에 액세스하려면 주제 탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-260">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="eef01-261">이 탭은 Teams 대화와 비합하되만 편집할 수 있는 추가 옵션이 있는 형식의 콘텐츠를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-261">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="eef01-262">노트를 작성하거나, 메시지에 그리거나, 정제로 명의하기 쉽게 작성하는 데 사용할 수 있는 연필 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-262">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="eef01-263">영역의 **정확도를** 사용하여 해당 영역을 이사각형으로 그리고 "Redacted"로 표시하는 사각형을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-263">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="eef01-264">다음은 사용자 들 사이에 스레드된 대화에 대한 실제로 해당 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-264">Here's an example of a redacted file for threaded conversation between users.</span></span>

![복구된 파일 스크린샷](media/RedactedFileExample.png)

<span data-ttu-id="eef01-266">주석 **번역 탭 하단에는** **태그 패널이** 표시되는 태그 문서 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-266">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="eef01-267">이 패널 내에서 Teams 대화 내의 모든 메시지에 태그를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-267">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="eef01-268">대화에 응답 또는 응답성 없이, 사용 여부와 상관없이 부여되거나 여부에 상관없이 내보내기에 포함할지 여부, 검토가 필요한지 여부 등으로 텍스트에 레이블을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-268">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="eef01-269">또한 기타 사용자 지정 가능한 태그를 관리하고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-269">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="eef01-270">작업 메뉴</span><span class="sxs-lookup"><span data-stu-id="eef01-270">Action menu</span></span>

<span data-ttu-id="eef01-271">검토 집합 내에서 작업 내보내기를 클릭하여 콘텐츠를 내보낼 **수** \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="eef01-271">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="eef01-272">내보낼 때 사용할 수 있는 다양한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-272">There are many options available when exporting.</span></span>

<span data-ttu-id="eef01-273">모든 Teams 메시지에 대한 모든 메타데이터를 포함하는 파일을 내보내려면 파일 로드 **확인란을 클릭하여** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-273">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="eef01-274">파일에 적용한 모든 태그를 파일에 포함하려면 태그 **확인란을 클릭하여 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eef01-274">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="eef01-275">기본 **파일 옵션을 사용하여 파일을** 기본 형식으로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-275">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="eef01-276">대화를 하나의 파일로 내보내거나 별도의 파일에 있는 모든 개별 채팅 메시지로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-276">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="eef01-277">텍스트 **파일 옵션을** 사용하면 콘텐츠의 일반 텍스트 버전을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-277">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="eef01-278">검토 집합에서 Teams 대화의 일반 텍스트 보기를 구하는 방법에 대한 자세한 내용은 요약 보기, [텍스트 보기, 위의](#summary-view-text-view-and-annotate-view) 주의 표시를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eef01-278">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="eef01-279">위의 요약 [보기,](#summary-view-text-view-and-annotate-view) 텍스트 보기 및 주석 보기 섹션에 설명된 대로 콘텐츠에 대한 수정사항을 적용한 경우 다시 **적용된 원리를** 선택하고 변환된 PDF 로그를 PDF의 변환된 복사본으로 대체하는 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-279">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="eef01-280">Microsoft가 제공하는 Azure blob 저장소 컨테이너로 내보내거나 자체 Azure Blob 저장소 컨테이너를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-280">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="eef01-281">내보내기 프로세스를 시작할 준비가 되면 내보내기 단추를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eef01-281">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="eef01-282">Azure blob [저장소 컨테이너에](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) 액세스하고 내보내기가 완료된 후 내보낸 콘텐츠를 다운로드하는 방법에 대한 자세한 내용은 내보내기 작업을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eef01-282">See [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="eef01-283">내보내기에는 오프라인 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef01-283">Exporting can take an extended period of time.</span></span> <span data-ttu-id="eef01-284">내보내기 프로세스의 상태를 추적하려면 검토 설정 **탭을 종료하고 내보내기** **탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eef01-284">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eef01-285">관련 항목</span><span class="sxs-lookup"><span data-stu-id="eef01-285">Related topics</span></span>

- [<span data-ttu-id="eef01-286">Microsoft 365의 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="eef01-286">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="eef01-287">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="eef01-287">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
