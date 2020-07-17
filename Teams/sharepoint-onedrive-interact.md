---
title: SharePoint Online 및 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & 팀과 비즈니스용 OneDrive 상호 작용 개인 채팅 파일 저장소 팀, 표준 채널, & 문서 라이브러리 간의 상호 작용을 &.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a66cacf7a60b020b4b56e0824d0a275efdf704f8
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45140946"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="45945-103">SharePoint Online 및 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="45945-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="45945-104">팀에서 AAD (Azure Active Directory), Microsoft 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive를 상호 작용 하는 방법에 대 한 자세한 내용은 [Microsoft 팀의 기초](https://aka.ms/teams-foundations) 를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="45945-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="45945-105">Microsoft 팀의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 표준 채널은 기본 팀 사이트 문서 라이브러리 내에서 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45945-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="45945-106">대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에 설정된 사용 권한 및 파일 보안 옵션은 Teams에서 자동으로 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="45945-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="45945-107">SharePoint에서 사이트 주소를 변경 했을 때의 영향을 확인 하려면 [사이트 주소 변경을](https://docs.microsoft.com/sharepoint/change-site-address)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45945-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="45945-108">이 문서는 표준 채널에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45945-108">This article applies only to standard channels.</span></span> <span data-ttu-id="45945-109">개인 채널의 아키텍처가 표준 채널과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="45945-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="45945-110">각 개인 채널에는 상위 팀 사이트와는 별도의 SharePoint 사이트 모음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="45945-111">자세한 내용은 [Microsoft 팀의 개인 채널](private-channels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45945-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="45945-112">개인 채팅 파일은 발신자의 비즈니스용 OneDrive 폴더에 저장 되며, 모든 참가자에 게 파일 공유 프로세스의 일부로 사용 권한이 자동으로 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45945-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="45945-113">사용자가 SharePoint Online 라이선스를 할당 하 고 사용 하도록 설정 하지 않은 경우 Microsoft 365 또는 Office 365에 비즈니스용 OneDrive 저장소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="45945-114">파일 공유는 표준 채널에서 계속 작동 하지만, Microsoft 365 또는 Office 365의 비즈니스용 OneDrive 저장소 없이는 채팅에서 파일을 공유할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45945-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="45945-115">SharePoint Online 문서 라이브러리와 비즈니스용 OneDrive에 파일을 저장하면 테넌트 수준에서 구성된 모든 규정 준수 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="45945-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="45945-116">현재 Microsoft 팀에서는 SharePoint 온-프레미스와 통합이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="45945-117">다음은 팀, 표준 채널, 문서 라이브러리 간의 관계 예입니다.</span><span class="sxs-lookup"><span data-stu-id="45945-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="45945-118">모든 팀에 대해 SharePoint 사이트가 만들어지고 **공유 문서** 폴더가 팀에 대해 만든 기본 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="45945-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="45945-119">**일반** 채널 (각 팀의 기본 채널)을 포함 하 여 각 표준 채널은 **공유 문서**에 폴더를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![SharePoint Online의 공유 문서 폴더 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="45945-121">현재 기본 SharePoint 사이트 및 문서 라이브러리를 다른 항목으로 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="45945-122">당신이 원하는 대로이를 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="45945-123">[팀 로드맵](https://aka.ms/teamsroadmap) 또는 [팀 UserVoice](https://aka.ms/TeamsUserVoice) 를 확인 하 여 예정 된 기능을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="45945-124">기존 SharePoint 사이트 페이지나 기존 SharePoint 문서 라이브러리에 연결 되는 탭을 팀에 추가 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="45945-125">탭 옆에 있는 더하기 기호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="45945-126">기존 SharePoint 사이트 페이지 또는 기존 문서 라이브러리의 **문서 라이브러리** 에 대해 **SharePoint** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="45945-127">적절 한 페이지 또는 문서 라이브러리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="45945-128">모든 사용자에 대해 OneDrive 폴더 **Microsoft 팀 채팅 파일** 은 다른 사용자 (1:1 또는 1: 다)와 개인 채팅 내에 공유 된 모든 파일을 저장 하는 데 사용 되며, 사용 권한은 의도 된 사용자 에게만 액세스를 제한 하도록 자동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45945-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Microsoft 팀 채팅 파일 이라는 OneDrive 폴더의 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="45945-130">공용 팀의 경우 SharePoint 팀 사이트는 "외부 사용자를 제외한 모든 사람" 액세스 권한을 사용 하 여 프로 비전 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45945-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="45945-131">해당 팀의 구성원이 아닌 사용자는 팀에 공개 팀이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="45945-132">그러나 sharepoint 팀 사이트의 URL을 사용 하 여 SharePoint 팀 사이트의 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="45945-133">채널 파일 탭</span><span class="sxs-lookup"><span data-stu-id="45945-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="45945-134">팀의 **파일** 탭은 SharePoint 문서 보기와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="45945-135">사용자는 **파일** 탭에서 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="45945-136">**새** 파일 메뉴의 추가 옵션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45945-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="45945-137">파일을 로컬 드라이브에 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="45945-138">**모든 문서** 메뉴에서 **목록** 보기를 바둑판식으로 압축 하 여 **목록을** **타일** 보기로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="45945-139">주의가 필요 하거나 맬웨어가 있는 파일을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="45945-140">파일의 읽기 전용 또는 체크 아웃 여부를 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="45945-141">파일을 체크 아웃 하 고 체크 인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-141">Check out and check in files.</span></span>
- <span data-ttu-id="45945-142">파일의 정렬 순서를 고정, 제거 및 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="45945-143">메타 데이터가 필요한 파일 식별</span><span class="sxs-lookup"><span data-stu-id="45945-143">Identify which files need metadata</span></span>
- <span data-ttu-id="45945-144">여러 필터 옵션 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="45945-145">열 머리글을 기준으로 파일을 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-145">Group files based on column headings.</span></span>
- <span data-ttu-id="45945-146">열 설정 수정 (왼쪽 또는 오른쪽, 숨기기) 및 열 너비를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45945-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="45945-147">기본 링크 종류 설정</span><span class="sxs-lookup"><span data-stu-id="45945-147">Default link type setting</span></span>

<span data-ttu-id="45945-148">SharePoint 및 OneDrive에는 파일에 대해 만들어지는 링크에 대 한 기본 링크 종류를 지정 하는 관리자 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="45945-149">팀은 관리자가 SharePoint 및 OneDrive에 대해 설정한 설정을 다시 사용 하 여 동일한 접근 방식을 채택 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="45945-150">이 접근 방법에 대 한 자세한 내용은 [사용자가 공유할 링크를 가져올 때 기본 링크 유형 변경](https://docs.microsoft.com/sharepoint/change-default-sharing-link)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45945-150">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="45945-151">추가 정보</span><span class="sxs-lookup"><span data-stu-id="45945-151">More information</span></span>

<span data-ttu-id="45945-152">SharePoint에서 팀과 공동 작업 하는 방법에 대 한 자세한 내용은 [sharepoint 및 팀](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45945-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="45945-153">팀의 게스트 환경에 대 한 자세한 내용은 [게스트 환경을](guest-experience.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="45945-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>
