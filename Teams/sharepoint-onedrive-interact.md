---
title: SharePoint 및 OneDrive 상호 작용하는 Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive 상호 작용을 Teams. 개인 채팅 파일 & 팀, 표준 채널, 문서 & 상호 작용합니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855957"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a><span data-ttu-id="ed531-103">SharePoint 및 OneDrive 상호 작용하는 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed531-103">How SharePoint and OneDrive interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="ed531-104">다음 세션을 통해 Teams(AAD), Azure Active Directory, Microsoft 365, Exchange SharePoint 및 [OneDrive:](https://aka.ms/teams-foundations) Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed531-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="ed531-105">각 Microsoft Teams 팀 사이트가 SharePoint 팀 사이트가 있으며, 팀의 각 표준 채널은 기본 팀 사이트 문서 라이브러리 내의 폴더를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-105">Each team in Microsoft Teams has a team site in SharePoint, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="ed531-106">각 [개인 채널은](private-channels.md) 자체적으로 별도의 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-106">Each [private channel](private-channels.md) gets its own, separate SharePoint site.</span></span>

<span data-ttu-id="ed531-107">대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에 설정된 사용 권한 및 파일 보안 옵션은 Teams에서 자동으로 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-107">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="ed531-108">사이트 주소 변경의 영향을 확인 SharePoint 사이트 주소 변경 [을 참조하세요.](/sharepoint/change-site-address)</span><span class="sxs-lookup"><span data-stu-id="ed531-108">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

<span data-ttu-id="ed531-109">개인 채팅 파일은 보낸 사람 OneDrive 폴더에 저장되며 파일 공유 프로세스의 일부로 모든 참가자에게 권한이 자동으로 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-109">Private chat files are stored in the sender's OneDrive folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="ed531-110">사용자가 라이선스에 할당되지 SharePoint 경우 사용자에게 OneDrive 저장소가 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed531-110">If users aren't assigned SharePoint licenses, they don't have OneDrive storage in Microsoft 365.</span></span> <span data-ttu-id="ed531-111">파일 공유는 표준 채널에서 작동하지만 사용자는 채팅에서 파일을 공유할 수 OneDrive 저장하지 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed531-111">File sharing works in standard channels, but users won't be able to share files in chats without OneDrive storage in Microsoft 365.</span></span>

<span data-ttu-id="ed531-112">파일을 문서 라이브러리에 SharePoint 및 OneDrive 조직 수준에서 구성된 모든 규정 준수 규칙이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-112">By storing the files in the SharePoint document library and OneDrive, all compliance rules configured at the organization level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="ed531-113">SharePoint 서버와의 통합은 지원되지 Teams.</span><span class="sxs-lookup"><span data-stu-id="ed531-113">Integration with SharePoint Server is not supported for Teams.</span></span>

<span data-ttu-id="ed531-114">다음은 팀, 표준 채널 및 문서 라이브러리 간의 관계 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-114">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="ed531-115">모든 팀에 대해 SharePoint 사이트가 만들어지며 공유 **문서** 폴더는 팀에 대해 만든 기본 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-115">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="ed531-116">일반 채널(각  팀의 기본 채널)을 포함한 각 표준 채널에는 공유 문서의 **폴더가 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="ed531-116">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![공유 문서 폴더의 다이어그램에서 SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="ed531-118">기본 사이트 SharePoint 및 문서 라이브러리를 다른 사이트로 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-118">The default SharePoint site and document library can't be replaced with a different one.</span></span>

<span data-ttu-id="ed531-119">모든 사용자에 대해 채팅 OneDrive  Microsoft Teams 폴더는 다른 사용자와 개인 채팅 내에서 공유된 모든 파일을 저장하는 데 사용됩니다(1:1 또는 1:다), 의도된 사용자에 대한 액세스를 제한하기 위해 자동으로 구성된 권한.</span><span class="sxs-lookup"><span data-stu-id="ed531-119">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![채팅 파일이라는 OneDrive 폴더의 Microsoft Teams 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="ed531-121">공용 팀의 경우 SharePoint 팀 사이트는 "외부 사용자를 제외한 모든 사용자" 액세스로 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-121">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="ed531-122">공개 팀은 해당 팀의 구성원이 아닌 Teams 공개 팀에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-122">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="ed531-123">그러나 팀 사이트의 URL을 사용하여 SharePoint 팀 사이트의 콘텐츠에 액세스할 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-123">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="ed531-124">채널 파일 탭</span><span class="sxs-lookup"><span data-stu-id="ed531-124">Channel Files tab</span></span>

<span data-ttu-id="ed531-125">**문서의** 파일 탭은 Teams 문서 보기와 SharePoint 밀접하게 입니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-125">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="ed531-126">파일 **탭에서** 사용자는 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-126">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="ed531-127">새 파일 메뉴에서 추가 **옵션을** 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed531-127">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="ed531-128">파일을 로컬 드라이브에 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-128">Sync files to their local drive.</span></span>
- <span data-ttu-id="ed531-129">모든 **문서 메뉴에서** 목록  보기에서 **압축 목록으로** **타일 보기로 전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed531-129">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="ed531-130">주의가 필요하거나 맬웨어가 있는 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-130">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="ed531-131">파일이 읽기 전용인지 또는 체크 아웃인지 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-131">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="ed531-132">파일을 체크 아웃하고 체크 인합니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-132">Check out and check in files.</span></span>
- <span data-ttu-id="ed531-133">파일 정렬 순서를 고정, 고정 및 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-133">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="ed531-134">메타데이터가 필요한 파일 식별</span><span class="sxs-lookup"><span data-stu-id="ed531-134">Identify which files need metadata</span></span>
- <span data-ttu-id="ed531-135">더 많은 필터 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-135">Choose from many more filter options.</span></span>
- <span data-ttu-id="ed531-136">열 제목을 기준으로 파일을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-136">Group files based on column headings.</span></span>
- <span data-ttu-id="ed531-137">열 설정(왼쪽 또는 오른쪽 이동, 숨기기) 및 열 너비를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-137">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="ed531-138">기본 링크 유형 설정</span><span class="sxs-lookup"><span data-stu-id="ed531-138">Default link type setting</span></span>

<span data-ttu-id="ed531-139">사용자가 파일을 공유하는 경우 기본적으로 표시된 공유 링크의 유형은 SharePoint 관리 센터에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed531-139">The type of sharing link shown by default when a user shared a file is set in the SharePoint admin center.</span></span> <span data-ttu-id="ed531-140">사용자가 [정보를 공유하기 위한](/sharepoint/change-default-sharing-link) 링크를 얻을 때 기본 링크 형식 변경을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed531-140">See [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed531-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ed531-141">Related topics</span></span>

<span data-ttu-id="ed531-142">[SharePoint 및 Teams: 더 나은 을 함께 사용할 수 있습니다.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="ed531-142">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

[<span data-ttu-id="ed531-143">게스트 환경의 모양</span><span class="sxs-lookup"><span data-stu-id="ed531-143">What the guest experience is like</span></span>](guest-experience.md)