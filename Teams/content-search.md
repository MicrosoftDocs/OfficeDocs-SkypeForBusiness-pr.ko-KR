---
title: Microsoft 팀에서 콘텐츠 검색 사용
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
description: Microsoft 팀에서 콘텐츠 검색을 사용 하 여 Exchange, SharePoint Online, 비즈니스용 OneDrive, OneNote에서 Microsoft 팀 정보를 쿼리 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d05d815a74fc395c06763920014b7de453847bec
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121528"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="3aa1b-103">Microsoft 팀에서 콘텐츠 검색 사용</span><span class="sxs-lookup"><span data-stu-id="3aa1b-103">Use Content Search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="3aa1b-104">[개인 채널](private-channels.md) 의 메시지 및 파일의 콘텐츠 검색은 표준 채널과 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="3aa1b-105">자세히 알아보려면 [개인 채널의 콘텐츠 검색](#content-search-of-private-channels)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="3aa1b-106">콘텐츠 검색은 Exchange, SharePoint Online, 비즈니스용 OneDrive에 걸친 Microsoft 팀 정보를 쿼리 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-106">Content Search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="3aa1b-107">자세한 내용은 [Microsoft 365 또는 Office 365의 콘텐츠 검색](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-107">To learn more, read [Content Search in Microsoft 365 or Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span></span>

<span data-ttu-id="3aa1b-108">예를 들어 제조 스펙 사서함 및 제조 사양 SharePoint 사이트에 대 한 **콘텐츠 검색** 을 사용 하 여 Exchange에서 팀 표준 채널 대화, sharepoint Online의 파일 업로드 및 수정, OneNote 변경 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-108">For example, using **Content Search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="3aa1b-109">또한 **콘텐츠 검색** 에 쿼리 조건을 추가 하 여 반환 되는 결과의 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="3aa1b-110">위의 예제에서는 "**New Factory 스펙"** 키워드를 사용한 콘텐츠를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="3aa1b-111">검색 조건을 추가 하 고 나면 분석을 위해 보고서 또는 데이터를 컴퓨터로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-111">After adding search conditions, you can export a report or the data to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="3aa1b-112">개인 채널의 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="3aa1b-112">Content search of private channels</span></span>

<span data-ttu-id="3aa1b-113">비공개 채널에 전송된 메시지 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="3aa1b-114">레코드 제목은 출처 비공개 채널을 표시하도록 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="3aa1b-115">각 개인 채널은 상위 팀 사이트와 별도의 고유한 SharePoint 사이트 모음을 포함 하므로 개인 채널의 파일은 상위 팀과 독립적으로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="3aa1b-116">팀은 단일 채널의 콘텐츠 검색을 지원 하지 않으므로 전체 팀을 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="3aa1b-117">개인 채널의 콘텐츠 검색을 수행 하려면 팀, 개인 채널에 연결 된 사이트 모음 (파일 포함) 및 개인 채널 구성원의 사서함 (메시지 포함)에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="3aa1b-118">콘텐츠 검색에 포함할 개인 채널의 파일 및 메시지를 식별 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="3aa1b-119">콘텐츠 검색에 개인 채널 파일 포함</span><span class="sxs-lookup"><span data-stu-id="3aa1b-119">Include private channel files in a content search</span></span>

<span data-ttu-id="3aa1b-120">이 단계를 수행 하기 전에 [Sharepoint Online 관리 셸을 설치 하 고 Sharepoint online에 연결](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="3aa1b-121">팀의 개인 채널과 연결 된 모든 SharePoint 사이트 모음 목록을 가져오려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="3aa1b-122">다음 PowerShell 스크립트를 실행 하 여 팀의 개인 채널과 해당 상위 팀 그룹 ID와 연결 된 모든 SharePoint 사이트 모음 Url 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="3aa1b-123">각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행 하 여 모든 관련 개인 채널 사이트를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="3aa1b-124">콘텐츠 검색에 개인 채널 메시지 포함</span><span class="sxs-lookup"><span data-stu-id="3aa1b-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="3aa1b-125">이 단계를 수행 하기 전에 [최신 버전의 팀 PowerShell 모듈이](teams-powershell-overview.md) 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="3aa1b-126">다음을 실행 하 여 팀의 비공개 채널 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="3aa1b-127">다음을 실행 하 여 개인 채널 구성원 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="3aa1b-128">콘텐츠 검색 쿼리의 일부로 팀의 각 개인 채널에 있는 모든 구성원의 사서함을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa1b-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3aa1b-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3aa1b-129">Related topics</span></span>

- [<span data-ttu-id="3aa1b-130">Microsoft 365 준수 센터의 eDiscovery 사례</span><span class="sxs-lookup"><span data-stu-id="3aa1b-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 