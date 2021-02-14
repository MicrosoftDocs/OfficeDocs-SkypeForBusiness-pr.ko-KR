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
description: PowerShell 컨트롤을 사용하여 Microsoft Teams를 관리하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852159"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="a7ea2-103">Microsoft Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="a7ea2-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="a7ea2-104">Microsoft Teams PowerShell은 PowerShell 명령줄에서 직접 Teams를 관리하기 위한 cmdlet 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="a7ea2-105">.NET Standard로 작성된 Teams PowerShell은 Azure Cloud Shell을 포함한 모든 플랫폼에서 Windows의 PowerShell 5.1, PowerShell 6.x 이상에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="a7ea2-106">PowerShell 사용을 시작하기 전에 먼저 PowerShell을 [설치해야 합니다.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="a7ea2-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="a7ea2-107">PowerShell 7 및 Teams PowerShell에는 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="a7ea2-108">문제가 해결될 때까지 PowerShell 5.1을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="a7ea2-109">릴리스</span><span class="sxs-lookup"><span data-stu-id="a7ea2-109">Releases</span></span>


<span data-ttu-id="a7ea2-110">Teams PowerShell은 두 가지 릴리스 유형으로 [PowerShell 갤러리에서](https://www.powershellgallery.com/packages/MicrosoftTeams) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="a7ea2-111">**GA(일반 공급)**: 프로덕션이 준비된 cmdlet, 월별 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7ea2-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="a7ea2-112">**공개 미리 보기:** 기능에 대한 초기 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="a7ea2-113">GA보다 더 자주 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="a7ea2-114">두 릴리스의 기능 추가 및 향상된 기능에 대한 자세한 내용은 [Teams PowerShell 릴리스 정보를 참조하세요.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="a7ea2-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="a7ea2-115">PowerShell을 사용하여 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="a7ea2-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="a7ea2-116">Teams PowerShell 모듈을 사용하여 Teams를 완전히 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="a7ea2-117">[Microsoft Teams PowerShell 모듈: Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)모듈에는 팀, 채팅 및 채널을 관리하기 위한 cmdlet이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="a7ea2-118">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 공개 릴리스는 비즈니스용 Skype Online Connector와 통합되어 Teams PowerShell 관리를 위한 단일 모듈을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-118">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="a7ea2-119">[비즈니스용 Skype PowerShell 커넥터:](https://www.microsoft.com/download/details.aspx?id=39366)비즈니스용 Skype PowerShell 커넥터는 이제 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ea2-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="a7ea2-120">이러한 모듈을 사용하여 Teams를 관리하는 전체 가이드는 [Teams PowerShell을 사용하여 Teams 관리를 참조하세요.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="a7ea2-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="a7ea2-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a7ea2-121">Related topics</span></span>

[<span data-ttu-id="a7ea2-122">Teams PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="a7ea2-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="a7ea2-123">Teams PowerShell을 통해 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="a7ea2-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="a7ea2-124">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="a7ea2-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="a7ea2-125">Microsoft Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="a7ea2-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="a7ea2-126">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="a7ea2-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="a7ea2-127">Microsoft Teams 관리자 역할을 사용하여 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="a7ea2-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
