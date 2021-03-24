---
title: Microsoft Teams에서 콘텐츠 검색 사용
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft 365 준수 센터에서 콘텐츠 검색을 사용하여 Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 OneNote에 저장된 Microsoft Teams 콘텐츠를 검색하는 방법을 알아보겠습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3758f96dc4755303ce8ccf3cae4443deb2a5cd99
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094288"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="550ce-103">Microsoft Teams에서 콘텐츠 검색 사용</span><span class="sxs-lookup"><span data-stu-id="550ce-103">Use Content search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="550ce-104">개인 채널에서 메시지 및 [](private-channels.md) 파일의 콘텐츠 검색은 표준 채널과 다르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="550ce-105">자세한 내용은 개인 [채널의 콘텐츠 검색을 참조하세요.](#content-search-of-private-channels)</span><span class="sxs-lookup"><span data-stu-id="550ce-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="550ce-106">콘텐츠 검색은 Exchange, SharePoint Online 및 비즈니스용 OneDrive에 걸쳐 Microsoft Teams 정보를 쿼리하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-106">Content search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="550ce-107">자세한 내용은 [Microsoft 365의 콘텐츠 검색을 참조하세요.](/microsoft-365/compliance/content-search)</span><span class="sxs-lookup"><span data-stu-id="550ce-107">To learn more, see [Content search in Microsoft 365](/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="550ce-108">예를 들어,  제조 사양 사서함 및 제조 사양 SharePoint 사이트에 대한 콘텐츠 검색을 사용하여 Exchange에서 Teams 표준 채널 대화, SharePoint Online의 파일 업로드 및 수정, OneNote 변경 내용에 대해 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-108">For example, using **Content search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="550ce-109">콘텐츠 검색에 쿼리 조건을  추가하여 반환된 결과를 좁힐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="550ce-110">위의 예제에서는 "새 팩터리 **사양"을** 키워드로 사용한 콘텐츠를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="550ce-111">검색 조건을 추가한 후 분석하기 위해 보고서 또는 실제 콘텐츠를 컴퓨터에 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-111">After adding search conditions, you can export a report or the actual content to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="550ce-112">개인 채널의 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="550ce-112">Content search of private channels</span></span>

<span data-ttu-id="550ce-113">비공개 채널에 전송된 메시지 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="550ce-114">레코드 제목은 출처 비공개 채널을 표시하도록 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="550ce-115">각 개인 채널에는 부모 팀 사이트와 별개인 자체 SharePoint 사이트 모음이 있기 때문에 개인 채널의 파일은 부모 팀과 독립적으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="550ce-116">팀은 단일 채널의 콘텐츠 검색을 지원하지 않습니다. 따라서 팀 전체를 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="550ce-117">개인 채널의 콘텐츠 검색을 수행하려면 팀, 개인 채널과 연결된 사이트 모음(파일 포함), 개인 채널 구성원의 사서함(메시지를 포함)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="550ce-118">다음 단계를 사용하여 콘텐츠 검색에 포함할 개인 채널의 파일 및 메시지를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="550ce-119">콘텐츠 검색에 개인 채널 파일 포함</span><span class="sxs-lookup"><span data-stu-id="550ce-119">Include private channel files in a content search</span></span>

<span data-ttu-id="550ce-120">이러한 단계를 수행하기 전에 SharePoint Online 관리 셸을 설치하고 [SharePoint Online에 연결합니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="550ce-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="550ce-121">다음을 실행하여 팀의 개인 채널과 연결된 모든 SharePoint 사이트 모음 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="550ce-122">다음 PowerShell 스크립트를 실행하여 팀의 개인 채널 및 부모 팀 그룹 ID와 연결된 모든 SharePoint 사이트 모음 URL 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="550ce-123">각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행하여 모든 관련 개인 채널 사이트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="550ce-124">콘텐츠 검색에 개인 채널 메시지 포함</span><span class="sxs-lookup"><span data-stu-id="550ce-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="550ce-125">이러한 단계를 수행하기 전에 최신 [버전의 Teams PowerShell](teams-powershell-overview.md) 모듈이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="550ce-126">다음을 실행하여 팀에서 개인 채널 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="550ce-127">다음을 실행하여 개인 채널 구성원 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="550ce-128">콘텐츠 검색 쿼리의 일부로 팀의 각 개인 채널의 모든 구성원의 사서함을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="550ce-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="550ce-129">Related topics</span></span>

- [<span data-ttu-id="550ce-130">Microsoft 365 준수 센터의 eDiscovery 사례</span><span class="sxs-lookup"><span data-stu-id="550ce-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](/Office365/SecurityCompliance/ediscovery-cases)