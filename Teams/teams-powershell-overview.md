---
title: Microsoft Teams PowerShell 개요
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell 컨트롤을 사용하여 관리 방법을 Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768357"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="08163-103">Microsoft Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="08163-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="08163-104">Microsoft Teams PowerShell은 PowerShell 명령줄에서 직접 Teams 관리하기 위한 cmdlet 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="08163-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="08163-105">.NET Standard로 Teams PowerShell은 Azure Cloud Shell을 포함한 모든 플랫폼에서 PowerShell 5.1 Windows PowerShell 6.x 이상에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="08163-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="08163-106">PowerShell을 사용하려면 먼저 를 [설치해야 합니다.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="08163-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="08163-107">PowerShell 7 및 PowerShell에 대한 알려진 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08163-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="08163-108">문제가 해결될 때까지 PowerShell 5.1을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="08163-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="08163-109">릴리스</span><span class="sxs-lookup"><span data-stu-id="08163-109">Releases</span></span>


<span data-ttu-id="08163-110">Teams PowerShell은 두 가지 릴리스 유형으로 [PowerShell 갤러리에서](https://www.powershellgallery.com/packages/MicrosoftTeams) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08163-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="08163-111">**GA(일반 공급)**: 프로덕션 준비 cmdlet, 월별 업데이트.</span><span class="sxs-lookup"><span data-stu-id="08163-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="08163-112">**공개 미리 보기**: 기능에 대한 초기 액세스.</span><span class="sxs-lookup"><span data-stu-id="08163-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="08163-113">GA보다 더 자주 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08163-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="08163-114">두 릴리스에 대한 기능 추가 및 개선에 대한 자세한 내용은 [PowerShell 릴리스 Teams 참조하세요.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="08163-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="08163-115">PowerShell을 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="08163-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="08163-116">PowerShell 모듈을 Teams 사용하여 다음을 완벽하게 Teams.</span><span class="sxs-lookup"><span data-stu-id="08163-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="08163-117">[Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)모듈: Teams PowerShell 모듈에는 팀, 채팅 및 채널을 관리하기 위한 cmdlet이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08163-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="08163-118">Teams PowerShell 공개 릴리스 버전 2.0 이상에는 모든 비즈니스용 Skype 온라인 커넥터 cmdlet이 포함되어 있습니다. [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 관리를 위한 단일 Teams 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08163-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 2.0 or higher includes all  Skype for Business Online Connector cmdlets, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="08163-119">[비즈니스용 Skype PowerShell 커넥터:](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)비즈니스용 Skype PowerShell 커넥터는 이제 PowerShell Teams 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="08163-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="08163-120">이 모듈을 사용하여 Teams 전체 가이드는 [PowerShell을](teams-powershell-managing-teams.md)사용하여 Teams Teams 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08163-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="08163-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="08163-121">Related topics</span></span>

[<span data-ttu-id="08163-122">PowerShell Teams 설치</span><span class="sxs-lookup"><span data-stu-id="08163-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="08163-123">PowerShell을 Teams Teams 관리</span><span class="sxs-lookup"><span data-stu-id="08163-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="08163-124">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="08163-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="08163-125">Microsoft Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="08163-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="08163-126">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="08163-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="08163-127">관리 Microsoft Teams 관리자 역할을 사용하여 Teams</span><span class="sxs-lookup"><span data-stu-id="08163-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
