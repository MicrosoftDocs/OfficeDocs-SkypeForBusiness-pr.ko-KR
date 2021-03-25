---
title: SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & OneDrive for Business 상호 작용; 개인 채팅 파일 & 팀, 표준 채널, 문서 & 상호 작용합니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b69b156e5cea0ff63925e91f5e3c077c794b3425
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117036"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="e0698-103">SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법</span><span class="sxs-lookup"><span data-stu-id="e0698-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="e0698-104">Teams에서 AAD(Azure Active Directory), Microsoft 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive와 상호 작용하는 방법을 알아보려면 [Microsoft Teams의 기초](https://aka.ms/teams-foundations) 세션을 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="e0698-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="e0698-105">Microsoft Teams의 각 팀에는 SharePoint Online에 팀 사이트가 있으며, 팀의 각 표준 채널은 기본 팀 사이트 문서 라이브러리 내의 폴더를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="e0698-106">대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에 설정된 사용 권한 및 파일 보안 옵션은 Teams에서 자동으로 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="e0698-107">SharePoint에서 사이트 주소를 변경하는 영향은 사이트 [주소 변경 을 참조하세요.](/sharepoint/change-site-address)</span><span class="sxs-lookup"><span data-stu-id="e0698-107">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="e0698-108">이 문서는 표준 채널에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-108">This article applies only to standard channels.</span></span> <span data-ttu-id="e0698-109">개인 채널에 대한 아키텍처는 표준 채널과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="e0698-110">각 개인 채널에는 부모 팀 사이트와 별개인 자체 SharePoint 사이트 모음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="e0698-111">자세한 내용은 [Microsoft Teams의 개인 채널을 참조하세요.](private-channels.md)</span><span class="sxs-lookup"><span data-stu-id="e0698-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="e0698-112">개인 채팅 파일은 보낸 사람이 비즈니스용 OneDrive 폴더에 저장되며, 파일 공유 프로세스의 일부로 모든 참가자에게 권한이 자동으로 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="e0698-113">사용자에게 SharePoint Online 라이선스가 할당되지 않고 사용하도록 설정되어 있지 않은 경우, 사용자는 Microsoft 365 또는 Office 365에 비즈니스용 OneDrive 저장소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e0698-114">파일 공유는 표준 채널에서 계속 작동하지만 Microsoft 365 또는 Office 365의 비즈니스용 OneDrive 저장소 없이는 채팅에서 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="e0698-115">SharePoint Online 문서 라이브러리와 비즈니스용 OneDrive에 파일을 저장하면 테넌트 수준에서 구성된 모든 규정 준수 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="e0698-116">현재 Microsoft Teams에서는 SharePoint On-프레미스와의 통합이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="e0698-117">다음은 팀, 표준 채널 및 문서 라이브러리 간의 관계 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="e0698-118">모든 팀에 대해 SharePoint 사이트가 만들어지며 공유 **문서** 폴더는 팀에 대해 만든 기본 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="e0698-119">일반 채널(각  팀의 기본 채널)을 포함한 각 표준 채널에는 공유 문서의 **폴더가 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e0698-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![SharePoint Online의 공유 문서 폴더 다이어그램입니다.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="e0698-121">현재 기본 SharePoint 사이트 및 문서 라이브러리를 다른 사이트로 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="e0698-122">원하는 것을 듣게 됐고 고려 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="e0698-123">Teams [로드맵](https://aka.ms/teamsroadmap) 또는 [Teams UserVoice를](https://aka.ms/TeamsUserVoice) 확인하여 다가오는 기능을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="e0698-124">기존 SharePoint 사이트 페이지 또는 기존 SharePoint 문서 라이브러리에 연결되는 탭을 팀에 추가하는 경우:</span><span class="sxs-lookup"><span data-stu-id="e0698-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="e0698-125">탭 옆에 있는 더하기 기호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="e0698-126">기존 SharePoint 사이트 페이지의 **SharePoint** 또는 기존 문서 라이브러리의 **문서** 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="e0698-127">적절한 페이지 또는 문서 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="e0698-128">모든 사용자에 대해 OneDrive 폴더 **Microsoft Teams Chat Files는** 다른 사용자와 개인 채팅 내에서 공유된 모든 파일을 저장하는 데 사용됩니다(1:1 또는 1:다), 의도된 사용자에 대한 액세스를 제한하기 위해 자동으로 구성된 권한.</span><span class="sxs-lookup"><span data-stu-id="e0698-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Microsoft Teams 채팅 파일이라는 OneDrive 폴더 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="e0698-130">공용 팀의 경우 SharePoint 팀 사이트는 "외부 사용자를 제외한 모든 사용자" 액세스로 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="e0698-131">공개 팀은 해당 팀의 구성원이 아닌 사람에 대한 Teams에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="e0698-132">그러나 SharePoint 팀 사이트의 URL을 사용하여 SharePoint 팀 사이트의 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="e0698-133">채널 파일 탭</span><span class="sxs-lookup"><span data-stu-id="e0698-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="e0698-134">**Teams의** 파일 탭은 SharePoint 문서 보기와 밀접하게 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="e0698-135">파일 **탭에서** 사용자는 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="e0698-136">새 파일 메뉴에서 추가 **옵션을** 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0698-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="e0698-137">파일을 로컬 드라이브에 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="e0698-138">모든 **문서 메뉴에서** 목록  보기에서 **압축 목록으로** **타일 보기로 전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0698-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="e0698-139">주의가 필요하거나 맬웨어가 있는 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="e0698-140">파일이 읽기 전용인지 또는 체크 아웃인지 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="e0698-141">파일을 체크 아웃하고 체크 인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-141">Check out and check in files.</span></span>
- <span data-ttu-id="e0698-142">파일 정렬 순서를 고정, 고정 및 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="e0698-143">메타데이터가 필요한 파일 식별</span><span class="sxs-lookup"><span data-stu-id="e0698-143">Identify which files need metadata</span></span>
- <span data-ttu-id="e0698-144">더 많은 필터 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="e0698-145">열 제목을 기준으로 파일을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-145">Group files based on column headings.</span></span>
- <span data-ttu-id="e0698-146">열 설정(왼쪽 또는 오른쪽 이동, 숨기기) 및 열 너비를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="e0698-147">기본 링크 유형 설정</span><span class="sxs-lookup"><span data-stu-id="e0698-147">Default link type setting</span></span>

<span data-ttu-id="e0698-148">SharePoint 및 OneDrive에는 파일에 대해 만든 링크에 대한 기본 링크 유형을 지정하기 위한 관리자 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="e0698-149">팀은 관리자가 SharePoint 및 OneDrive에 대해 설정하는 설정을 다시 사용하여 동일한 방법을 채택하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0698-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="e0698-150">이 접근 방식에 대한 자세한 내용은 사용자가 공유에 대한 링크를 얻을 때 기본 링크 형식 [변경에 설명되어 있습니다.](/sharepoint/change-default-sharing-link)</span><span class="sxs-lookup"><span data-stu-id="e0698-150">More details about this approach are described in [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="e0698-151">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e0698-151">More information</span></span>

<span data-ttu-id="e0698-152">SharePoint가 Teams와 함께 작동하는 방법에 대한 자세한 내용은 SharePoint 및 Teams: 더 나은 함께 [를 참조하세요.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="e0698-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="e0698-153">Teams의 게스트 경험에 대한 자세한 내용은 게스트 환경이 어떻게 [됐는가를 읽어보아야 합니다.](guest-experience.md)</span><span class="sxs-lookup"><span data-stu-id="e0698-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>