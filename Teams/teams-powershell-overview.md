---
title: Microsoft 팀 PowerShell 개요
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
description: PowerShell 컨트롤을 사용 하 여 Microsoft 팀을 관리 하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5385430c7db8aab0adf1efbaec546134e9adf388
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943991"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="b41b4-103">Microsoft 팀 PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="b41b4-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="b41b4-104">Microsoft 팀 PowerShell은 PowerShell 명령줄에서 직접 팀을 관리 하는 cmdlet 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="b41b4-105">.NET Standard로 작성 된 팀 PowerShell은 Azure Shell을 포함 하 여 모든 플랫폼에서 Windows, PowerShell 6. x 및 그 이상의 PowerShell 5.1에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows,PowerShell 6.x and higher on all platforms including Azure Shell.</span></span>

<span data-ttu-id="b41b4-106">PowerShell 사용을 시작 하려면 먼저 [설치](teams-powershell-install.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="b41b4-107">PowerShell 7 및 팀 PowerShell에 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="b41b4-108">문제가 해결 될 때까지 PowerShell 5.1을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="b41b4-109">릴리스가</span><span class="sxs-lookup"><span data-stu-id="b41b4-109">Releases</span></span>


<span data-ttu-id="b41b4-110">두 릴리스 유형의 [Powershell 갤러리](https://www.powershellgallery.com/packages/MicrosoftTeams) 에서 팀 powershell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="b41b4-111">**일반 가용성 (GA)**: 프로덕션에서 사용할 수 있는 cmdlet, 업데이트 된 월간.</span><span class="sxs-lookup"><span data-stu-id="b41b4-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="b41b4-112">**공개 미리 보기**: 기능에 대 한 조기 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="b41b4-113">GA 보다 자주 업데이트 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="b41b4-114">두 릴리스 모두의 기능 추가 및 개선 사항에 대 한 자세한 내용은 [팀 PowerShell 릴리스 정보](teams-powershell-release-notes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b41b4-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="b41b4-115">PowerShell을 사용 하 여 팀 관리</span><span class="sxs-lookup"><span data-stu-id="b41b4-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="b41b4-116">이러한 PowerShell 모듈을 모두 사용 하 여 팀을 완전 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-116">You'll use both of these PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="b41b4-117">[Microsoft 팀 powershell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams/): 팀 powershell 모듈에는 팀, 채팅 및 채널을 관리 하는 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

- <span data-ttu-id="b41b4-118">비즈니스용 [Skype powershell 모듈](https://www.microsoft.com/download/details.aspx?id=39366): 비즈니스용 skype powershell 모듈에는 모임, 전화 시스템 및 정책 기능을 관리 하는 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-118">[Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell module contains the cmdlets to manage meetings, phone system, and policies features.</span></span>

<span data-ttu-id="b41b4-119">이러한 모듈을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀으로 팀 관리 PowerShell](teams-powershell-managing-teams.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b41b4-119">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b41b4-120">최신 [팀 powershell 공개 미리 보기 릴리스](https://www.powershellgallery.com/packages/MicrosoftTeams/) 는 비즈니스용 Skype Online 커넥터와 통합 되어 팀 PowerShell 관리를 위한 단일 모듈을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41b4-120">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b41b4-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b41b4-121">Related topics</span></span>

[<span data-ttu-id="b41b4-122">팀 PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="b41b4-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="b41b4-123">팀을 사용 하 여 팀 관리 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b41b4-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="b41b4-124">팀 PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="b41b4-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="b41b4-125">Microsoft 팀 cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="b41b4-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="b41b4-126">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="b41b4-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="b41b4-127">Microsoft 팀 관리자 역할을 사용 하 여 팀 관리</span><span class="sxs-lookup"><span data-stu-id="b41b4-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
