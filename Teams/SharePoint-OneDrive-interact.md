---
title: SharePoint Online 및 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online과 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법, 즉 개인 채팅 파일 저장 방법, 팀, 채널, 문서 라이브러리 간의 관계에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28a4a968fc9e478c3a13fb38acd1019221b5dcb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233023"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="69fb4-103">SharePoint Online 및 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="69fb4-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="69fb4-104">다음 세션에서 팀이 Azure Active Directory (AAD), Office 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive와 상호 작용 하는 방법에 대해 알아보세요. [Microsoft 팀의 기초](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="69fb4-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="69fb4-105">Microsoft 팀의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에서 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="69fb4-106">대화 내에서 공유 된 파일은 문서 라이브러리에 자동으로 추가 되며 SharePoint에 설정 된 사용 권한 및 파일 보안 옵션은 팀 내에 자동으로 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="69fb4-107">개인 채팅 파일은 발신자의 비즈니스용 OneDrive 폴더에 저장 되며, 모든 참가자에 게 파일 공유 프로세스의 일부로 사용 권한이 자동으로 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="69fb4-108">사용자가 SharePoint Online 라이선스를 할당 하 고 사용 하도록 설정 하지 않은 경우 Office 365의 비즈니스용 OneDrive 저장소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="69fb4-109">파일 공유는 채널에서 계속 작동 하지만, 사용자는 Office 365의 비즈니스용 OneDrive 저장소 없이도 채팅에서 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="69fb4-110">SharePoint Online 문서 라이브러리 및 비즈니스용 OneDrive에 파일을 저장 하면 테 넌 트 수준에서 구성 된 모든 준수 규칙이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="69fb4-111">현재 Microsoft 팀에서는 SharePoint 온-프레미스와 통합이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-111">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="69fb4-112">다음은 팀, 채널, 문서 라이브러리 간의 관계 예입니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="69fb4-113">모든 팀에 대해 SharePoint 사이트가 만들어지고 **공유 문서** 폴더가 팀에 대해 만든 기본 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-113">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="69fb4-114">**일반** 채널 (각 팀의 기본 채널)을 포함 하 여 각 채널에는 **공유 문서의**폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-114">Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![SharePoint Online의 공유 문서 폴더 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="69fb4-116">현재 기본 SharePoint 사이트 및 문서 라이브러리를 다른 항목으로 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="69fb4-117">당신이 원하는 대로이를 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="69fb4-118">[팀 로드맵](https://aka.ms/teamsroadmap) 또는 [팀 UserVoice](https://aka.ms/TeamsUserVoice) 를 확인 하 여 예정 된 기능을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="69fb4-119">기존 SharePoint 사이트 페이지나 기존 SharePoint 문서 라이브러리에 연결 되는 탭을 팀에 추가 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="69fb4-120">탭 옆에 있는 더하기 기호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="69fb4-121">기존 SharePoint 사이트 페이지 또는 기존 문서 라이브러리의 **문서 라이브러리** 에 대해 **SharePoint** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="69fb4-122">적절 한 페이지 또는 문서 라이브러리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="69fb4-123">모든 사용자에 대해 OneDrive 폴더 **Microsoft 팀 채팅 파일** 은 다른 사용자 (1:1 또는 1: 다)와 개인 채팅 내에 공유 된 모든 파일을 저장 하는 데 사용 되며, 사용 권한은 의도 된 사용자 에게만 액세스를 제한 하도록 자동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Microsoft 팀 채팅 파일 이라는 OneDrive 폴더의 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="69fb4-125">채널 파일 탭</span><span class="sxs-lookup"><span data-stu-id="69fb4-125">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="69fb4-126">팀의 **파일** 탭은 SharePoint 문서 보기와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-126">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="69fb4-127">사용자는 **파일** 탭에서 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-127">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="69fb4-128">**새** 파일 메뉴의 추가 옵션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69fb4-128">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="69fb4-129">파일을 로컬 드라이브에 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-129">Sync files to their local drive.</span></span>
- <span data-ttu-id="69fb4-130">**모든 문서** 메뉴에서 **목록** 보기를 바둑판식으로 압축 하 여 **목록을** **타일** 보기로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-130">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="69fb4-131">주의가 필요 하거나 맬웨어가 있는 파일을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-131">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="69fb4-132">파일의 읽기 전용 또는 체크 아웃 여부를 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-132">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="69fb4-133">파일을 체크 아웃 하 고 체크 인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-133">Check out and check in files.</span></span>
- <span data-ttu-id="69fb4-134">파일의 정렬 순서를 고정, 제거 및 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-134">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="69fb4-135">메타 데이터가 필요한 파일 식별</span><span class="sxs-lookup"><span data-stu-id="69fb4-135">Identify which files need metadata</span></span>
- <span data-ttu-id="69fb4-136">여러 필터 옵션 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-136">Choose from many more filter options.</span></span>
- <span data-ttu-id="69fb4-137">열 머리글을 기준으로 파일을 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-137">Group files based on column headings.</span></span>
- <span data-ttu-id="69fb4-138">열 설정 수정 (왼쪽 또는 오른쪽, 숨기기) 및 열 너비를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-138">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="69fb4-139">기본 링크 종류 설정</span><span class="sxs-lookup"><span data-stu-id="69fb4-139">Default link type setting</span></span>

<span data-ttu-id="69fb4-140">SharePoint 및 OneDrive에는 파일에 대해 만들어지는 링크에 대 한 기본 링크 종류를 지정 하는 관리자 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-140">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="69fb4-141">팀은 관리자가 SharePoint 및 OneDrive에 대해 설정한 설정을 다시 사용 하 여 동일한 접근 방식을 채택 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-141">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="69fb4-142">이 접근 방법에 대 한 자세한 내용은 [사용자가 공유할 링크를 가져올 때 기본 링크 유형 변경](https://docs.microsoft.com/sharepoint/change-default-sharing-link)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69fb4-142">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="69fb4-143">추가 정보</span><span class="sxs-lookup"><span data-stu-id="69fb4-143">More information</span></span>

<span data-ttu-id="69fb4-144">SharePoint에서 팀과 공동 작업 하는 방법에 대 한 자세한 내용은 [sharepoint 및 팀](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69fb4-144">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="69fb4-145">팀의 게스트 환경에 대 한 자세한 내용은 [게스트 환경을](guest-experience.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="69fb4-145">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

