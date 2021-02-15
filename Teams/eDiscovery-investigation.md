---
title: 콘텐츠에 대한 eDiscovery 조사 수행
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
description: 법적 절차를 위해 전자적으로 저장된 모든 정보를 제출해야 하는 경우와 같이 eDiscovery를 수행해야 하는 경우 수행할 작업을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980462"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="f1136-103">Microsoft Teams에서 콘텐츠에 대한 eDiscovery 조사 수행</span><span class="sxs-lookup"><span data-stu-id="f1136-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="f1136-104">대기업은 종종 모든 ESI(전자 저장 정보)의 제출을 요구하는 높은 페널티 법적 절차에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="f1136-105">Microsoft Teams 콘텐츠는 eDiscovery 조사 중에 검색하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="f1136-106">개요</span><span class="sxs-lookup"><span data-stu-id="f1136-106">Overview</span></span>

<span data-ttu-id="f1136-107">모든 Microsoft Teams 1:1 또는 그룹 채팅은 해당 사용자의 사서함에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="f1136-108">모든 표준 채널 메시지는 팀을 나타내는 그룹 사서함으로 저널링됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="f1136-109">표준 채널에 업로드된 파일은 SharePoint Online 및 비즈니스용 OneDrive에 대한 eDiscovery 기능에서 다루고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="f1136-110">개인 채널의 메시지 및 파일의 [](private-channels.md) eDiscovery는 표준 채널과 다르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="f1136-111">자세한 내용은 개인 [채널의 eDiscovery를 참조하세요.](#ediscovery-of-private-channels)</span><span class="sxs-lookup"><span data-stu-id="f1136-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="f1136-112">모든 Teams 콘텐츠는 eDiscoverable일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="f1136-113">다음 표에서는 Microsoft eDiscovery 도구를 사용하여 검색할 수 있는 콘텐츠 형식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-113">The following table shows the content types that you can search for using Microsoft eDiscovery tools:</span></span>

| <span data-ttu-id="f1136-114">콘텐츠 형식</span><span class="sxs-lookup"><span data-stu-id="f1136-114">Content type</span></span> | <span data-ttu-id="f1136-115">eDiscoverable</span><span class="sxs-lookup"><span data-stu-id="f1136-115">eDiscoverable</span></span> | <span data-ttu-id="f1136-116">참고</span><span class="sxs-lookup"><span data-stu-id="f1136-116">Notes</span></span> |
|:--- | :--- |:--- |
|<span data-ttu-id="f1136-117">오디오 녹음</span><span class="sxs-lookup"><span data-stu-id="f1136-117">Audio recordings</span></span> | <span data-ttu-id="f1136-118">아니요</span><span class="sxs-lookup"><span data-stu-id="f1136-118">No</span></span> | |
|<span data-ttu-id="f1136-119">카드 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="f1136-119">Card content</span></span>|<span data-ttu-id="f1136-120">예</span><span class="sxs-lookup"><span data-stu-id="f1136-120">Yes</span></span>|<span data-ttu-id="f1136-121">자세한 [내용은 카드 콘텐츠](#search-for-card-content) 검색을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1136-121">See [Search for card content](#search-for-card-content) for more information.</span></span>|
|<span data-ttu-id="f1136-122">채팅 링크</span><span class="sxs-lookup"><span data-stu-id="f1136-122">Chat links</span></span> | <span data-ttu-id="f1136-123">예</span><span class="sxs-lookup"><span data-stu-id="f1136-123">Yes</span></span> | |
|<span data-ttu-id="f1136-124">채팅 메시지</span><span class="sxs-lookup"><span data-stu-id="f1136-124">Chat messages</span></span> | <span data-ttu-id="f1136-125">예</span><span class="sxs-lookup"><span data-stu-id="f1136-125">Yes</span></span> |<span data-ttu-id="f1136-126">여기에는 Teams 채널의 콘텐츠, 1:1 채팅, 1:N 그룹 채팅, 게스트 사용자 참가자와의 채팅이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-126">This includes content in Teams channels, 1:1 chats, 1:N group chats, and chats with guest user participants.</span></span>  |
|<span data-ttu-id="f1136-127">코드 코드시트</span><span class="sxs-lookup"><span data-stu-id="f1136-127">Code snippets</span></span> | <span data-ttu-id="f1136-128">아니요</span><span class="sxs-lookup"><span data-stu-id="f1136-128">No</span></span> | |
|<span data-ttu-id="f1136-129">편집된 메시지</span><span class="sxs-lookup"><span data-stu-id="f1136-129">Edited messages</span></span> | <span data-ttu-id="f1136-130">예</span><span class="sxs-lookup"><span data-stu-id="f1136-130">Yes</span></span> | <span data-ttu-id="f1136-131">사용자가 보류 중이면 이전 버전의 편집된 메시지도 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-131">If the user is on hold, previous versions of edited messages are also preserved.</span></span> |
|<span data-ttu-id="f1136-132">이모지, GIF 및 스티커</span><span class="sxs-lookup"><span data-stu-id="f1136-132">Emojis, GIFs, and stickers</span></span> | <span data-ttu-id="f1136-133">예</span><span class="sxs-lookup"><span data-stu-id="f1136-133">Yes</span></span> | |
|<span data-ttu-id="f1136-134">인라인 이미지</span><span class="sxs-lookup"><span data-stu-id="f1136-134">Inline images</span></span> | <span data-ttu-id="f1136-135">예</span><span class="sxs-lookup"><span data-stu-id="f1136-135">Yes</span></span> | |
|<span data-ttu-id="f1136-136">모임 IM 대화</span><span class="sxs-lookup"><span data-stu-id="f1136-136">Meeting IM conversations</span></span> | <span data-ttu-id="f1136-137">예</span><span class="sxs-lookup"><span data-stu-id="f1136-137">Yes</span></span> | |
|<span data-ttu-id="f1136-138">모임 메타데이터<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f1136-138">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="f1136-139">예</span><span class="sxs-lookup"><span data-stu-id="f1136-139">Yes</span></span> |  |
|<span data-ttu-id="f1136-140">채널 이름</span><span class="sxs-lookup"><span data-stu-id="f1136-140">Name of channel</span></span> | <span data-ttu-id="f1136-141">아니요</span><span class="sxs-lookup"><span data-stu-id="f1136-141">No</span></span> | |
|<span data-ttu-id="f1136-142">개인 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="f1136-142">Private channel messages</span></span> | <span data-ttu-id="f1136-143">예</span><span class="sxs-lookup"><span data-stu-id="f1136-143">Yes</span></span> | |
|<span data-ttu-id="f1136-144">따옴표</span><span class="sxs-lookup"><span data-stu-id="f1136-144">Quotes</span></span> | <span data-ttu-id="f1136-145">예</span><span class="sxs-lookup"><span data-stu-id="f1136-145">Yes</span></span> | <span data-ttu-id="f1136-146">따옴표가 추가된 콘텐츠를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-146">Quoted content is searchable.</span></span> <span data-ttu-id="f1136-147">그러나 검색 결과에는 내용이 인용된 것으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-147">However, search results don't indicate that the content was quoted.</span></span> |
|<span data-ttu-id="f1136-148">반응(예: 좋아, 하트 및 기타 반응)</span><span class="sxs-lookup"><span data-stu-id="f1136-148">Reactions (such as likes, hearts, and other reactions)</span></span> | <span data-ttu-id="f1136-149">아니요</span><span class="sxs-lookup"><span data-stu-id="f1136-149">No</span></span> | |
|<span data-ttu-id="f1136-150">제목</span><span class="sxs-lookup"><span data-stu-id="f1136-150">Subject</span></span> | <span data-ttu-id="f1136-151">예</span><span class="sxs-lookup"><span data-stu-id="f1136-151">Yes</span></span> | |
|<span data-ttu-id="f1136-152">테이블</span><span class="sxs-lookup"><span data-stu-id="f1136-152">Tables</span></span> | <span data-ttu-id="f1136-153">예</span><span class="sxs-lookup"><span data-stu-id="f1136-153">Yes</span></span> | |
|||

<span data-ttu-id="f1136-154"><sup>1개</sup> 모임(및 통화) 메타데이터에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-154"><sup>1</sup> Meeting (and call) metadata includes the following:</span></span>

- <span data-ttu-id="f1136-155">모임 시작 및 종료 시간 및 기간</span><span class="sxs-lookup"><span data-stu-id="f1136-155">Meeting start and end time, and duration</span></span>
- <span data-ttu-id="f1136-156">각 참가자에 대한 모임 참가 및 이벤트 나가기</span><span class="sxs-lookup"><span data-stu-id="f1136-156">Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="f1136-157">VOIP 조인/호출</span><span class="sxs-lookup"><span data-stu-id="f1136-157">VOIP join/calls</span></span>
- <span data-ttu-id="f1136-158">익명 조인</span><span class="sxs-lookup"><span data-stu-id="f1136-158">Anonymous join</span></span>
- <span data-ttu-id="f1136-159">페더리된 사용자 조인</span><span class="sxs-lookup"><span data-stu-id="f1136-159">Federated user join</span></span>
- <span data-ttu-id="f1136-160">게스트 사용자 조인</span><span class="sxs-lookup"><span data-stu-id="f1136-160">Guest user join</span></span>

  <span data-ttu-id="f1136-161">이 이미지는 모임 메타데이터의 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-161">The image shows an example of meeting metadata.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="f1136-162">![이미지는 CVR 레코드 모임 메타데이터입니다.](media/conversationOption3.png)</span><span class="sxs-lookup"><span data-stu-id="f1136-162">![Image is of the CVR records meeting metadata.](media/conversationOption3.png)</span></span>

<span data-ttu-id="f1136-163">다음은 모임 중에 참가자 간의 IM 대화 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-163">Here's an example of an IM conversation between participants during the meeting.</span></span>

![Teams의 참가자 간 대화.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f1136-165">![eDiscovery 검색 결과의 참가자 간 대화입니다.](media/MeetingImConversation2.png)</span><span class="sxs-lookup"><span data-stu-id="f1136-165">![Conversation between participants in eDiscovery search results.](media/MeetingImConversation2.png)</span></span>

<span data-ttu-id="f1136-166">eDiscovery 조사 수행에 대한 자세한 내용은 [Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)시작을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1136-166">For more information about conducting an eDiscovery investigation, see [Get started with Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="f1136-167">Microsoft Teams 데이터는 Excel eDiscovery 내보내기 출력에 IM 또는 대화로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-167">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="f1136-168">Outlook에서 파일을 열어 내보낼 때 해당 메시지를 `.pst` 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-168">You can open the `.pst` file in Outlook to view those messages after you export them.</span></span>

<span data-ttu-id="f1136-169">팀의 .pst 파일을 볼 때 모든 대화는 대화 기록 아래에 있는 팀 채팅 폴더에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-169">When viewing the .pst file for the team, all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="f1136-170">메시지의 제목에는 팀 이름과 채널 이름이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-170">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="f1136-171">예를 들어 아래 이미지는 제조 사양 팀의 Project 7 표준 채널에 메시지를 보낸 Bob의 메시지를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-171">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![Outlook의 사용자 사서함에 있는 팀 채팅 폴더 스크린샷](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="f1136-173">사용자의 사서함에 있는 비공개 채팅은 대화 기록 아래에 있는 팀 채팅 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-173">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="f1136-174">개인 채널의 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f1136-174">eDiscovery of private channels</span></span>

<span data-ttu-id="f1136-175">비공개 채널에 전송된 메시지 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-175">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="f1136-176">레코드 제목은 출처 비공개 채널을 표시하도록 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-176">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="f1136-177">각 개인 채널에는 상위 팀 사이트와 별개인 자체 SharePoint 사이트가 있기 때문에 비공개 채널의 파일은 상위 팀과 독립적으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-177">Because each private channel has its own SharePoint site that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="f1136-178">Teams는 팀 내에서 단일 채널의 eDiscovery 검색을 지원하지 않습니다. 따라서 팀 전체를 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-178">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="f1136-179">개인 채널에서 콘텐츠의 eDiscovery 검색을 수행하려면 팀, 개인 채널과 연결된 사이트 모음(파일 포함), 개인 채널 구성원의 사서함(메시지를 포함)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-179">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="f1136-180">다음 단계를 사용하여 eDiscovery 검색에 포함할 개인 채널의 파일 및 메시지를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-180">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="f1136-181">eDiscovery 검색에 개인 채널 파일 포함</span><span class="sxs-lookup"><span data-stu-id="f1136-181">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="f1136-182">이러한 단계를 수행하기 전에 SharePoint Online 관리 셸을 설치하고 [SharePoint Online에 연결합니다.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="f1136-182">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

1. <span data-ttu-id="f1136-183">다음을 실행하여 팀의 비공개 채널과 연결된 모든 SharePoint 사이트 모음 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-183">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="f1136-184">다음 PowerShell 스크립트를 실행하여 팀의 비공개 채널과 연결된 모든 SharePoint 사이트 모음 URL 및 부모 팀 그룹 ID 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-184">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="f1136-185">각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행하여 모든 관련 개인 채널 사이트를 식별합니다$groupID 팀의 그룹 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-185">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="f1136-186">eDiscovery 검색에 개인 채널 메시지 포함</span><span class="sxs-lookup"><span data-stu-id="f1136-186">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="f1136-187">이러한 단계를 수행하기 전에 최신 [버전의 Teams PowerShell](teams-powershell-overview.md) 모듈이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-187">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="f1136-188">다음 명령을 실행하여 팀의 비공개 채널 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-188">Run the following command to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="f1136-189">다음 명령을 실행하여 개인 채널 멤버 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-189">Run the following command to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="f1136-190">[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)검색 쿼리의 일부로 팀의 각 개인 채널에 있는 모든 구성원의 사서함을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-190">Include the mailboxes of all members from each private channel in the team as part of your [eDiscovery search query](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery).</span></span>

## <a name="search-for-content-for-guest-users"></a><span data-ttu-id="f1136-191">게스트 사용자에 대한 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="f1136-191">Search for content for guest users</span></span>

<span data-ttu-id="f1136-192">eDiscovery 도구를 사용하여 조직의 게스트 사용자와 관련된 Teams 콘텐츠를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-192">You can use eDiscovery tools to search for Teams content related to guest users in your organization.</span></span> <span data-ttu-id="f1136-193">게스트 사용자와 연결된 Teams 채팅 콘텐츠는 클라우드 기반 저장소 위치에 유지되고 eDiscovery를 사용하여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-193">Teams chat content that's associated with a guest user is preserved in a cloud-based storage location and can be searched for using eDiscovery.</span></span> <span data-ttu-id="f1136-194">여기에는 게스트 사용자가 조직의 다른 사용자와 참가자인 1:1 및 1:N 채팅 대화에서 콘텐츠를 검색하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-194">This includes searching for content in 1:1 and 1:N chat conversations in which a guest user is a participant with other users in your organization.</span></span> <span data-ttu-id="f1136-195">게스트 사용자가 참가자인 비공개 채널 메시지를 검색하고 *게스트:게스트* 채팅 대화에서 유일한 참가자가 게스트 사용자인 콘텐츠를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-195">You can also search for private channel messages in which a guest user is a participant and search for content in *guest:guest* chat conversations where the only participants are guest users.</span></span>

<span data-ttu-id="f1136-196">게스트 사용자에 대한 콘텐츠를 검색하는 경우:</span><span class="sxs-lookup"><span data-stu-id="f1136-196">To search for content for guest users:</span></span>

1. <span data-ttu-id="f1136-197">Azure AD PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-197">Connect to Azure AD PowerShell.</span></span> <span data-ttu-id="f1136-198">지침은 [PowerShell을 사용하여 Microsoft 365에](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)연결의 "Azure Active Directory PowerShell에 연결" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1136-198">For instructions, see the "Connect with the Azure Active Directory PowerShell" section in [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="f1136-199">이전 항목의 1단계와 2단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-199">Be sure to complete Step 1 and Step 2 in the previous topic.</span></span>

2. <span data-ttu-id="f1136-200">Azure AD PowerShell에 성공적으로 연결한 후 다음 명령을 실행하여 조직의 모든 게스트 사용자에 대한 UPN(사용자 계정 이름)을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-200">After you successfully connect to Azure AD PowerShell, run the following command to display the user principal name (UPN) for all guest users in your organization.</span></span> <span data-ttu-id="f1136-201">4단계에서 검색을 만들 때 게스트 사용자의 UPN을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-201">You have to use the UPN of the guest user when you create the search in step 4.</span></span>

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > <span data-ttu-id="f1136-202">컴퓨터 화면에 사용자 계정 이름 목록을 표시하는 대신 명령의 출력을 텍스트 파일로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-202">Instead of displaying a list of user principal names on the computer screen, you can redirect the output of the command to a text file.</span></span> <span data-ttu-id="f1136-203">이전 명령에 추가하여 이 `> filename.txt` 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-203">You can do this by appending `> filename.txt` to the previous command.</span></span> <span data-ttu-id="f1136-204">사용자 계정 이름이 있는 텍스트 파일이 현재 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-204">The text file with the user principal names will be saved to the current folder.</span></span>

3. <span data-ttu-id="f1136-205">다른 Windows PowerShell Security & 준수 센터 PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-205">In a different Windows PowerShell window, connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="f1136-206">지침은 Security & [준수 센터 PowerShell을 참조하세요.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="f1136-206">For instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="f1136-207">다단계 인증을 사용하여 연결하거나 사용하지 않고 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-207">You can connect with or without using multi-factor authentication.</span></span>

4. <span data-ttu-id="f1136-208">다음 명령을 실행하여 지정된 게스트 사용자가 참가자인 모든 콘텐츠(예: 채팅 메시지 및 전자 메일 메시지)를 검색하는 콘텐츠 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-208">Create a content search that searches for all content (such as chat messages and email messages) in which the specified guest user was a participant by running the following command.</span></span>

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   <span data-ttu-id="f1136-209">예를 들어 게스트 사용자인 Sara Davis와 연결된 콘텐츠를 검색하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-209">For example, to search for content associated with the guest user Sara Davis, you would run the following command.</span></span>

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    <span data-ttu-id="f1136-210">PowerShell을 사용하여 콘텐츠 검색을 만드는 데 대한 자세한 내용은 [New-ComplianceSearch를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)</span><span class="sxs-lookup"><span data-stu-id="f1136-210">For more information about using PowerShell to create content searches, see [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch).</span></span>

5. <span data-ttu-id="f1136-211">다음 명령을 실행하여 4단계에서 만든 콘텐츠 검색을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="f1136-211">Run the following command to start the content search that you created in step 4:</span></span>

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. <span data-ttu-id="f1136-212">이동한 다음 모든 콘텐츠 [https://compliance.microsoft.com](https://compliance.microsoft.com) 검색   >  **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f1136-212">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Show all** > **Content search**.</span></span>

7. <span data-ttu-id="f1136-213">검색 목록에서 4단계에서 만든 검색을 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-213">In the list of searches, select the search that you created in step 4 to display the flyout page.</span></span>

8. <span data-ttu-id="f1136-214">플라이아웃 페이지에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-214">On the flyout page, you can do the following things:</span></span>

   - <span data-ttu-id="f1136-215">검색 **결과를 보고** 콘텐츠를 미리 보려면 결과 보기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-215">Click **View results** to view the search results and preview the content.</span></span>

   - <span data-ttu-id="f1136-216">쿼리 필드 **옆에 있는** **편집을** 클릭하여 편집한 다음 검색을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-216">Next to the **Query** field, click **Edit** to edit and then rerun the search.</span></span> <span data-ttu-id="f1136-217">예를 들어 검색 쿼리를 추가하여 결과 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-217">For example, you can add a search query to narrow the results.</span></span>

   - <span data-ttu-id="f1136-218">결과 **내보내기를 클릭하여** 검색 결과를 내보내고 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-218">Click **Export results** to export and download the search results.</span></span>

## <a name="search-for-card-content"></a><span data-ttu-id="f1136-219">카드 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="f1136-219">Search for card content</span></span>

<span data-ttu-id="f1136-220">Teams 채널의 앱에서 생성한 카드 콘텐츠, 1:1 채팅 및 1xN 채팅은 사서함에 저장되고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-220">Card content generated by apps in Teams channels, 1:1 chats, and 1xN chats is stored in mailboxes and can be searched.</span></span> <span data-ttu-id="f1136-221">*카드는* 짧은 콘텐츠 조각을 위한 UI 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-221">A *card* is a UI container for short pieces of content.</span></span> <span data-ttu-id="f1136-222">카드에는 여러 속성과 첨부 파일이 있을 수 있으며 카드 작업을 트리거할 수 있는 단추를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-222">Cards can have multiple properties and attachments, and can include buttons that can trigger card actions.</span></span> <span data-ttu-id="f1136-223">자세한 내용은 카드를 [참조하세요.](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span><span class="sxs-lookup"><span data-stu-id="f1136-223">For more information, see [Cards](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span></span>

<span data-ttu-id="f1136-224">다른 Teams 콘텐츠와 마찬가지로 카드 콘텐츠가 저장되는 위치는 카드가 사용된 위치를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-224">Like other Teams content, where card content is stored is based on where the card was used.</span></span> <span data-ttu-id="f1136-225">Teams 채널에서 사용되는 카드의 콘텐츠는 Teams 그룹 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-225">Content for cards used in a Teams channel is stored in the Teams group mailbox.</span></span> <span data-ttu-id="f1136-226">1:1 및 1xN 채팅의 카드 콘텐츠는 채팅 참가자의 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-226">Card content for 1:1 and 1xN chats are stored in the mailboxes of the chat participants.</span></span>

<span data-ttu-id="f1136-227">카드 콘텐츠를 검색하기 위해 조건 또는 검색 `kind:microsoftteams` 조건을 `itemclass:IPM.SkypeTeams.Message` 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-227">To search for card content, you can use the `kind:microsoftteams` or `itemclass:IPM.SkypeTeams.Message` search conditions.</span></span> <span data-ttu-id="f1136-228">검색 결과를 검토할 때 Teams 채널의 봇에서 생성된 카드 콘텐츠에는 보낸 **사람/작성자** 전자 메일 속성이 있습니다. 여기서 카드 콘텐츠를 생성한 앱의 `<appname>@teams.microsoft.com` `appname` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-228">When reviewing search results, card content generated by bots in a Teams channel has the **Sender/Author** email property as `<appname>@teams.microsoft.com`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="f1136-229">사용자가 카드 콘텐츠를 생성한 경우 보낸 **사람/작성자의 값이** 사용자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-229">If card content was generated by a user, the value of **Sender/Author** identifies the user.</span></span>

<span data-ttu-id="f1136-230">콘텐츠 검색 결과에서 카드 콘텐츠를 볼 때 콘텐츠는 메시지에 첨부 파일로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-230">When viewing card content in Content search results, the content appears as an attachment to the message.</span></span> <span data-ttu-id="f1136-231">첨부 파일 이름은 카드 콘텐츠를 생성한 앱의 `appname.html` `appname` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-231">The attachment is named `appname.html`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="f1136-232">다음 스크린샷은 Teams 및 검색 결과에 카드 콘텐츠(Asana라는 앱의 경우)가 나타나는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="f1136-232">The following screenshots show how card content (for an app named Asana) appears in Teams and in the results of a search.</span></span>

<span data-ttu-id="f1136-233">**Teams의 카드 콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="f1136-233">**Card content in Teams**</span></span>

![Teams 채널 메시지의 카드 콘텐츠](media/CardContentTeams.png)

<span data-ttu-id="f1136-235">**검색 결과의 카드 콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="f1136-235">**Card content in search results**</span></span>
  
![콘텐츠 검색 결과의 동일한 카드 콘텐츠](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> <span data-ttu-id="f1136-237">현재 카드 콘텐츠의 이미지를 검색 결과에 표시(예: 이전 스크린샷의 확인 표시)에 표시하기 위해 검색 결과를 보는 데 사용하는 동일한 브라우저 세션의 다른 탭에 있는 Teams에 https://teams.microsoft.com) 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-237">To display images from card content in search results at this time (such as the checkmarks in the previous screenshot), you have to be signed into Teams (at https://teams.microsoft.com) in a different tab in the same browser session that you use to view the search results.</span></span> <span data-ttu-id="f1136-238">그렇지 않으면 이미지 자리 표시자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-238">Otherwise, image placeholders are displayed.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="f1136-239">고급 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f1136-239">Advanced eDiscovery</span></span>

<span data-ttu-id="f1136-240">고급 [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)워크플로를 사용하여 일부 Microsoft Teams 콘텐츠를 검색하고 보존할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-240">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="f1136-241">eDiscovery는 다양한 검색, 보류 및 내보내기 기능을 제공하는 반면 고급 eDiscovery는 규정 준수 관리자에게 데이터 원본을 식별하고 해당 콘텐츠를 분석하는 더 많은 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-241">While eDiscovery provides a range of search, hold, and export functionality, Advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="f1136-242">Teams 콘텐츠에 대한 고급 eDiscovery 관리 워크플로</span><span class="sxs-lookup"><span data-stu-id="f1136-242">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="f1136-243">관할권은 다양한 팀의 구성원일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-243">Custodians might be a member of various teams.</span></span> <span data-ttu-id="f1136-244">이러한 양도인과 관련된 Teams 콘텐츠를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-244">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="f1136-245">관리인 워크플로에 대한 지침은 [고급 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)사례에 관리인 추가를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1136-245">For instructions on the custodian workflow, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

<span data-ttu-id="f1136-246">양도인을 추가한 후 다음  단추를 클릭한 다음 추가 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-246">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="f1136-247">그러면 추가 위치를 선택하라는 메시지가 표시되는 창이 표시됩니다. 그러면 해당 데이터에 대한 모든 양도자 구성원 자격 및 해당 SharePoint 사이트 위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-247">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="f1136-248">이러한 모든 데이터 원본 및 팀에서 eDiscovery에 사용할 콘텐츠를 선택한 다음 해당 사용자와 식별된 모든 데이터 원본을 보류하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-248">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="f1136-249">Exchange 콘텐츠, OneDrive 콘텐츠 또는 둘 다를 포함할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-249">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="f1136-250">Exchange 콘텐츠에는 전자 메일, 사서함에 저장된 Teams 콘텐츠 등 사용자의 사서함에 있는 모든 응용 프로그램 콘텐츠가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-250">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="f1136-251">OneDrive 콘텐츠에는 사용자의 콘텐츠뿐만 아니라 OneDrive에 저장된 모든 Teams 콘텐츠(예: 1:1 채팅, 1:N 채팅, 채팅에서 공유된 파일)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-251">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="f1136-252">또한 채널 채팅 메시지 및 권한이 있는 파일을 포함하기 위해 양도관이 구성원인 팀을 연결하는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-252">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="f1136-253">또한 다른 모든 팀은 양도인과 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-253">Additionally, any other team can be associated with a custodian.</span></span>

> [!NOTE]
> <span data-ttu-id="f1136-254">개인 채널의 메시지 및 파일의 [](private-channels.md) eDiscovery는 표준 채널과 다르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-254">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="f1136-255">자세한 내용은 개인 [채널의 eDiscovery를 참조하세요.](#ediscovery-of-private-channels)</span><span class="sxs-lookup"><span data-stu-id="f1136-255">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="f1136-256">데이터 원본 보류</span><span class="sxs-lookup"><span data-stu-id="f1136-256">Placing a data source on hold</span></span>

<span data-ttu-id="f1136-257">보유자로 지정하는 특정 사용자가 없는 경우 전체 데이터 원본을 보류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-257">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="f1136-258">보류에 대한 자세한 내용은 [고급 eDiscovery의](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)보류 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1136-258">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="f1136-259">Teams 콘텐츠에 대한 보류를 만들 때 보류에 포함할 위치를 모두 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-259">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="f1136-260">사용자가 콘텐츠를 삭제하거나 변경하는 경우에도 보류는 해당 콘텐츠의 모든 이전 버전 복사본을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-260">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="f1136-261">선택적 쿼리를 사용하여 키워드, 날짜 범위, 작성자 및 기타 여러 조건을 기반으로 보류에 대한 조건을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-261">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="f1136-262">키워드를 지정하지 않으면 해당 데이터 원본의 모든 키워드가 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-262">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="f1136-263">고급 eDiscovery 검색</span><span class="sxs-lookup"><span data-stu-id="f1136-263">Advanced eDiscovery searches</span></span>

<span data-ttu-id="f1136-264">Teams 콘텐츠를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-264">Teams content can also be searched.</span></span> <span data-ttu-id="f1136-265">검색에 대한 자세한 내용은 [고급 eDiscovery에서](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)사례에 대한 데이터 수집을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1136-265">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="f1136-266">하나의 메시지가 검색 쿼리와 일치하는 경우 검색은 전체 대화를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-266">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="f1136-267">검색 쿼리를 만들 때 이미 선택한 모든 원본을 검색할 수 있도록 보금자 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-267">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="f1136-268">사용자에게 매핑되지 않은 Teams 사이트와 같은 비지원 출처를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-268">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="f1136-269">선택적 쿼리를 사용하여 Teams 콘텐츠 내에서 검색 범위를 좁힐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-269">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="f1136-270">검색을 만들어 선택한 후 선택한 검색에서 수행할 수 있는 추가 세부 정보 및 작업이 있는 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-270">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="f1136-271">통계 단추를  클릭하면 위치 유형, 콘텐츠의 원본, 콘텐츠가 그룹 사서함, 개별 사용자 사서함 또는 SharePoint 사이트에 있는지 여부에 따라 분석 결과를 포함하여 검색에 대한 통계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-271">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="f1136-272">따라서 검색 결과에 기여하는 원본의 분석 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-272">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="f1136-273">또한 쿼리 **보기를** 사용할 수 있으므로 결과에 기여하는 개별 키워드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-273">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="f1136-274">검색을 마무리한 후 결과 추가를 클릭하여 집합 단추를 검토하고 검토 집합에 추가할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="f1136-274">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="f1136-275">검토 집합에 대한 자세한 내용은 이 문서의 후반부에 있는 [고급 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) 및 [검토](#review-sets-workflow) 집합 워크플로에서 검토 집합 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1136-275">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="f1136-276">일반 검토 집합 및 대화 검토 집합</span><span class="sxs-lookup"><span data-stu-id="f1136-276">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="f1136-277">검토 집합에 검색을 추가할 때 일반 검토 집합 또는 대화 검토 집합에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-277">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="f1136-278">일반 검토 집합은 내보내기와 유사합니다. Teams 콘텐츠에 대한 개별 파일을 제공하며 기본 보기로 콘텐츠를 `.msg` 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-278">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="f1136-279">일반적으로 다른 소프트웨어 도구를 사용하여 나중에 파일을 다시 처리하려면 일반 검토 집합을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-279">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="f1136-280">대화 검토 집합은 대화를 보다 직관적이고 스레드된 보기로 제공합니다. 관련 메시지를 적절한 순서로 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-280">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f1136-281">![대화 검토 집합의 스크린샷](media/conversationOptions2.png)</span><span class="sxs-lookup"><span data-stu-id="f1136-281">![Screenshot of conversation review set](media/conversationOptions2.png)</span></span>

<span data-ttu-id="f1136-282">재배치와 같은 기능은 두 가지 유형의 검토 집합에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-282">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="f1136-283">검토 집합에 대한 자세한 내용은 고급 [eDiscovery의 대화 검토를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)</span><span class="sxs-lookup"><span data-stu-id="f1136-283">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="f1136-284">컬렉션 옵션</span><span class="sxs-lookup"><span data-stu-id="f1136-284">Collection options</span></span>

<span data-ttu-id="f1136-285">검토 집합에 추가할 때 대화 검색 옵션 및 Teams  대화를 포함하여 창의  컬렉션 옵션 섹션 아래에 확인란으로 사용할 수 있는 몇 가지 옵션이 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f1136-285">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="f1136-286">이러한 옵션을 사용하도록 설정하면 검토 집합의 일부인 개별 Teams 메시지도 컨텍스트에 따라 추가 메시지와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-286">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="f1136-287">예를 들어 쿼리가 구체적이고 하나의 메시지만 결과로 반환되는 경우 이러한 옵션을 사용하도록 설정하면 쿼리와 일치하는 메시지까지 이어지는 여러 메시지가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-287">For example, if your query is specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="f1136-288">많은 논리 조건은 추가 메시지가 쿼리와 일치하는 메시지에 컨텍스트를 제공하는지 여부를 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-288">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="f1136-289">예를 들어 Teams 콘텐츠의 경우 이러한 옵션을 사용하도록 설정하면 메시지가 스레드되는 방식 때문에 부모 메시지와 모든 자식 메시지를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-289">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="f1136-290">메시지 타임스탬프도 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-290">Message time stamps are also checked.</span></span> <span data-ttu-id="f1136-291">메시지가 쿼리와 일치하는 경우 4시간 범위 내에서 앞에 오거나 4시간 범위 내에 이어진 인접한 메시지는 대화의 일부로 간주하며 결과에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-291">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="f1136-292">검색 쿼리와 일치하는 컨텍스트 메시지가 반환될지 확실해야 하는 경우 이러한 옵션을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-292">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="f1136-293">모든 콘텐츠를 수집하거나 쿼리의 결과로 더 많은 메시지가 반환될 수 있도록 검색의 날짜 범위를 넓히면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-293">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="f1136-294">검토 집합 워크플로</span><span class="sxs-lookup"><span data-stu-id="f1136-294">Review sets workflow</span></span>

<span data-ttu-id="f1136-295">검토 집합 탭을 클릭하여 기존 검토 집합을 보거나 새 검토 집합을 **만들 수** 있습니다. 검토 집합에 대한 자세한 내용은 [고급 eDiscovery에서](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)검토 집합 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1136-295">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="f1136-296">문서 외에도 전자 메일, Teams 메시지, Yammer 및 기타 콘텐츠를 검토 집합에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-296">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="f1136-297">검토 집합 내에서 콘텐츠 검색 및 사용자 지정 쿼리 만들기와 같은 다른 컨텍스트에서 수행할 수 있는 많은 동일한 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-297">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="f1136-298">이러한 작업은 검토 집합에 추가된 항목에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-298">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="f1136-299">검토 **집합 관리 단추는** 분석, 요약 보고, 추가된 부하 집합 수 등의 추가 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-299">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="f1136-300">데이터의 시각화 및 차트에 액세스하려면 오른쪽 위에 있는 **개별 결과** 검색 프로필 \>  보기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-300">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="f1136-301">이러한 차트에서 에지(wedge)를 클릭하여 대화형으로 쿼리할 콘텐츠 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-301">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="f1136-302">예를 들어 Teams 콘텐츠만 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-302">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="f1136-303">수동으로 작성하는 쿼리를 저장하는 경우처럼 이러한 쿼리를 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-303">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="f1136-304">요약 보기, 텍스트 보기 및 주석 추가 보기</span><span class="sxs-lookup"><span data-stu-id="f1136-304">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="f1136-305">검토 집합에서 Teams 대화를 클릭하면 전체 Teams 대화를 개별적으로 상호 작용할 수 있는 메시지 목록으로 표시하는 요약 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-305">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="f1136-306">메시지 오른쪽의 아래쪽 화살표를 클릭하여 메시지 세부 정보를 보거나 개별 파일을 다운로드할 수 있는 상황에 맞는 메뉴를 `.msg` 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-306">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="f1136-307">메시지 세부 정보를 클릭하면 메타데이터 요약 또는 메시지의 전체 메타데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-307">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="f1136-308">PDF를 다운로드하려면 요약 보기의 오른쪽 위에 있는 다운로드 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-308">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="f1136-309">텍스트 보기 **탭을 클릭하여** Teams 대화의 추출된 텍스트에 대한 일반 텍스트 보기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-309">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="f1136-310">이 일반 텍스트 콘텐츠는 내보내기에 적합하며 다른 소프트웨어 도구를 사용하여 쉽게 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-310">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="f1136-311">주석 보기 **탭을 클릭하여** 주석 기능에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-311">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="f1136-312">이 탭에는 Teams 대화와 같은 형식으로 콘텐츠가 표시되지만 편집을 위한 추가 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-312">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="f1136-313">연필 도구를 사용하여 노트를 작성하거나, 메시지에 그리거나, 세분화하여 스크래치 아웃(스크래치)을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-313">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="f1136-314">영역을 검은색으로 표시하고 "Redacted"로 표시하는 직사각형을 그리는 데 사용할 수 있는 영역 재배치 도구도 있습니다. </span><span class="sxs-lookup"><span data-stu-id="f1136-314">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="f1136-315">다음은 사용자 간의 스레드 대화에 대한 시정된 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-315">Here's an example of a redacted file for threaded conversation between users.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f1136-316">![변경된 파일의 스크린샷](media/RedactedFileExample.png)</span><span class="sxs-lookup"><span data-stu-id="f1136-316">![Screenshot of redacted file](media/RedactedFileExample.png)</span></span>

<span data-ttu-id="f1136-317">주석 추가 **보기** 탭의 아래쪽에는  태그 지정 패널을 표시하는 문서 태그 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-317">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="f1136-318">이 패널 내에서 Teams 대화 내의 모든 메시지에 태그를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-318">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="f1136-319">대화에 "흥미로운 항목"이 포함되어 있는지 여부, 내보내기에 포함해야 하는지 여부, 추가 검토가 필요한지 여부 등 대화에 응답 또는 응답하지 않음, 권한 있는 항목 또는 권한 없는 것으로 레이블을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-319">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="f1136-320">사용자 지정 가능한 다른 태그를 관리하고 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-320">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="f1136-321">작업 메뉴</span><span class="sxs-lookup"><span data-stu-id="f1136-321">Action menu</span></span>

<span data-ttu-id="f1136-322">검토 집합 창 내에서 작업 내보내기 를 클릭하여 콘텐츠를 **내보낼 수** \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f1136-322">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="f1136-323">내보낼 때 사용할 수 있는 다양한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-323">There are many options available when exporting.</span></span>

<span data-ttu-id="f1136-324">모든 Teams 메시지에 대한 모든 메타데이터가 포함된 파일을 내보내려면 파일 로드 확인란을 **클릭하여** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-324">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="f1136-325">파일에 콘텐츠에 적용한 태그를 포함하려면 태그 확인란을  클릭하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-325">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="f1136-326">**네이티브 파일 옵션을 사용하여** 파일을 네이티브 형식으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-326">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="f1136-327">대화를 하나의 파일로 내보내거나 개별 채팅 메시지를 별도의 파일로 모두 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-327">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="f1136-328">텍스트 **파일 옵션을** 사용하면 일반 텍스트 버전의 콘텐츠를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-328">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="f1136-329">검토 집합에서 Teams 대화의 일반 텍스트 보기를 얻는 방법에 대한 자세한 내용은 위의 요약 보기, 텍스트 보기 및 주석 [추가 보기를 참조하세요.](#summary-view-text-view-and-annotate-view)</span><span class="sxs-lookup"><span data-stu-id="f1136-329">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="f1136-330">위의 요약 [보기,](#summary-view-text-view-and-annotate-view) 텍스트 보기 및 주석 추가 보기 섹션에 설명된 대로 콘텐츠에 편집을 적용한 경우 편집된 네이티브를 변환된 **PDF로** 바꾸기 옵션을 선택하여 네이티브 파일을 PDF의 변환된 복사본으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-330">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="f1136-331">Microsoft에서 제공한 Azure Blob Storage 컨테이너로 내보내거나 사용자 자신의 Azure Blob Storage 컨테이너를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-331">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="f1136-332">내보내기 프로세스를 시작할 준비가 됐을 때 내보내기 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-332">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="f1136-333">Azure [Blob Storage](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) 컨테이너에 액세스하고 내보내기 완료 후 내보낼 콘텐츠를 다운로드하는 방법에 대한 자세한 내용은 내보내기 작업 다운로드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1136-333">See [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="f1136-334">내보내는 데 시간이 연장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-334">Exporting can take an extended period of time.</span></span> <span data-ttu-id="f1136-335">내보내기 프로세스의 상태를 추적하려면 **검토** 집합 탭을 종료하고 내보내기 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f1136-335">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f1136-336">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f1136-336">Related topics</span></span>

- [<span data-ttu-id="f1136-337">Microsoft 365의 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f1136-337">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="f1136-338">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="f1136-338">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
