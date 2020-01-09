---
title: Microsoft 팀의 콘텐츠 eDiscovery 조사 수행
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
description: 법률 소송 절차에 대해 전자적으로 저장 된 모든 정보를 제출 해야 하는 경우와 같이 eDiscovery를 preform 해야 할 경우 수행할 작업에 대해 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43105db9a4e12d658bf5cf2e9c2c8897fdc918e3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989793"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="1e432-103">Microsoft 팀의 콘텐츠 eDiscovery 조사 수행</span><span class="sxs-lookup"><span data-stu-id="1e432-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="1e432-104">대규모 기업은 모든 ESI (전자적 저장 정보) 제출을 요구 하는 높은 벌칙 법률 소송 절차에 게 노출 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="1e432-105">모든 팀 1:1 또는 그룹 채팅은 각 사용자의 사서함으로 저널링 되며, 모든 표준 채널 메시지가 팀을 나타내는 그룹 사서함으로 저널링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="1e432-106">표준 채널로 업로드 되는 파일은 SharePoint Online 및 비즈니스용 OneDrive의 eDiscovery 기능에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="1e432-107">[개인 채널](private-channels.md) 의 메시지 및 파일 eDiscovery은 표준 채널과 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="1e432-108">자세히 알아보려면 [개인 채널 eDiscovery](#ediscovery-of-private-channels)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1e432-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

1.  <span data-ttu-id="1e432-109">Microsoft 팀 콘텐츠를 사용 하 여 eDiscovery 조사를 수행 하려면 [이](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) 링크의 1 단계를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-109">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="1e432-110">Microsoft 팀 데이터가 Excel eDiscovery 내보내기 출력에 IM 또는 대화로 표시 되며,을 탑재할 수 있습니다. PST에서 해당 메시지를 보려면 내보내기를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-110">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="1e432-111">를 탑재 하는 경우. PST 팀의 경우 대화 내용 아래의 팀 채팅 폴더에 모든 대화가 보관 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-111">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="1e432-112">메시지 제목은 팀 및 채널에 맞춰 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-112">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="1e432-113">아래 이미지를 검토 하 여 제조 사양 팀의 프로젝트 7 표준 채널을 messaged 하는 Bob 으로부터이 메시지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-113">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Outlook의 사용자 사서함에 있는 팀 채팅 폴더 스크린샷](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="1e432-115">사용자의 사서함에서 개인 채팅을 보려면 대화 내용 아래의 팀 채팅 폴더에도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-115">To see private chats in a user’s mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="1e432-116">게스트 대 게스트 채팅 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1e432-116">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="1e432-117">현재 게스트가 1:1 또는 1: N 채팅에 참여 하는 시나리오의 경우, 해당 채팅 메시지의 eDiscovery이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-117">Presently, for a scenario where only guests are participating in 1:1 or 1:N chat, we don't support eDiscovery of those chat messages.</span></span> 

<span data-ttu-id="1e432-118">사서함이 없으면 게스트 간 채팅 (가정용 테 넌 트 사용자가 없는 1xN 채팅)이 인덱싱되지 않으며 결과적으로 eDiscovery에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-118">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="1e432-119">게스트 대 게스트 채팅에 eDiscovery 기능을 활용 하기 위해 클라우드 기반 사서함 (또는 팬텀 사서함)을 만들어 1xN 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-119">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="1e432-120">팀 채팅 데이터는 클라우드 기반 사서함에 저장 된 후 eDiscovery 및 준수 콘텐츠 검색을 위해 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-120">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="1e432-121">다음 그림은 사서함이 없는 게스트 대 게스트 채팅에 대해 eDiscovery가 작동 하는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-121">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![비-게스트-사서함이 포함 된 채팅](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="1e432-123">개인 채널 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1e432-123">eDiscovery of private channels</span></span>

<span data-ttu-id="1e432-124">개인 채널로 전송 된 메시지의 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-124">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="1e432-125">레코드의 제목은 전송 된 개인 채널을 나타내도록 서식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-125">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="1e432-126">각 개인 채널은 상위 팀 사이트와 별도의 고유한 SharePoint 사이트 모음을 포함 하므로 개인 채널의 파일은 상위 팀과 독립적으로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-126">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="1e432-127">팀은 단일 채널의 eDiscovery 기능을 지원 하지 않으므로 전체 팀을 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-127">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="1e432-128">개인 채널에서 콘텐츠를 eDiscovery 검색 하려면 팀에서 검색 하 고, 개인 채널과 연결 된 사이트 모음 (파일 포함)과 개인 채널 구성원의 사서함 (메시지 포함)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-128">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="1e432-129">EDiscovery 검색에 포함할 개인 채널의 파일 및 메시지를 식별 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-129">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="1e432-130">EDiscovery 검색에 개인 채널 파일 포함</span><span class="sxs-lookup"><span data-stu-id="1e432-130">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="1e432-131">이 단계를 수행 하기 전에 [Sharepoint Online 관리 셸을 설치 하 고 Sharepoint online에 연결](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-131">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="1e432-132">팀의 개인 채널과 연결 된 모든 SharePoint 사이트 모음 목록을 가져오려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-132">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="1e432-133">다음 PowerShell 스크립트를 실행 하 여 팀의 개인 채널과 해당 상위 팀 그룹 ID와 연결 된 모든 SharePoint 사이트 모음 Url 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-133">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="1e432-134">각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행 하 여 해당 팀의 그룹 ID 인 모든 관련 개인 채널 사이트를 식별 $groupID 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-134">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="1e432-135">EDiscovery 검색에 개인 채널 메시지 포함</span><span class="sxs-lookup"><span data-stu-id="1e432-135">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="1e432-136">이 단계를 수행 하기 전에 [최신 버전의 팀 PowerShell 모듈이](teams-powershell-overview.md) 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-136">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="1e432-137">다음을 실행 하 여 팀의 비공개 채널 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-137">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="1e432-138">다음을 실행 하 여 개인 채널 구성원 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-138">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="1e432-139">EDiscovery 검색 쿼리의 일부로 팀의 각 개인 채널에 있는 모든 구성원의 사서함을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e432-139">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e432-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1e432-140">Related topics</span></span>

- [<span data-ttu-id="1e432-141">팀 PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="1e432-141">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
