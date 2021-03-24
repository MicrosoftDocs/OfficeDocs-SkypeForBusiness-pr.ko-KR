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
description: PowerShell 컨트롤을 사용하여 Microsoft Teams를 관리하는 방법을 학습합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d191d4d1dbb9c3d3d2f206bce76e9d3ddd7d78d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094118"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="eb7d4-103">Microsoft Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="eb7d4-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="eb7d4-104">Microsoft Teams PowerShell은 PowerShell 명령줄에서 직접 Teams를 관리하기 위한 cmdlet 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="eb7d4-105">.NET 표준으로 작성된 Teams PowerShell은 Azure Cloud Shell을 비롯한 모든 플랫폼에서 Windows의 PowerShell 5.1, PowerShell 6.x 이상에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="eb7d4-106">PowerShell을 사용하려면 먼저 를 [설치해야 합니다.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="eb7d4-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="eb7d4-107">PowerShell 7 및 Teams PowerShell에 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="eb7d4-108">문제가 해결될 때까지 PowerShell 5.1을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="eb7d4-109">릴리스</span><span class="sxs-lookup"><span data-stu-id="eb7d4-109">Releases</span></span>


<span data-ttu-id="eb7d4-110">Teams PowerShell은 두 가지 릴리스 유형으로 [PowerShell 갤러리에서](https://www.powershellgallery.com/packages/MicrosoftTeams) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="eb7d4-111">**GA(일반 공급)**: 프로덕션 준비 cmdlet, 월별 업데이트.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="eb7d4-112">**공개 미리 보기**: 기능에 대한 초기 액세스.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="eb7d4-113">GA보다 더 자주 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="eb7d4-114">두 릴리스에 대한 기능 추가 및 개선에 대한 자세한 내용은 [Teams PowerShell 릴리스 노트 를 참조하세요.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="eb7d4-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="eb7d4-115">PowerShell을 사용하여 팀 관리</span><span class="sxs-lookup"><span data-stu-id="eb7d4-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="eb7d4-116">Teams PowerShell 모듈을 사용하여 Teams를 완전히 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="eb7d4-117">[Microsoft Teams PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams/): Teams PowerShell 모듈에는 팀, 채팅 및 채널을 관리하기 위한 cmdlet이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="eb7d4-118">[Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 공개 릴리스 버전 1.1.6 이상은 비즈니스용 Skype Online 커넥터와 통합되어 Teams PowerShell 관리를 위한 단일 모듈을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 1.1.6 or later is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="eb7d4-119">[비즈니스용 Skype PowerShell 커넥터:](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)비즈니스용 Skype PowerShell 커넥터는 이제 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="eb7d4-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="eb7d4-120">이러한 모듈을 사용하여 Teams를 관리하는 전체 가이드는 [Teams PowerShell을 사용하여 Teams 관리를 참조하세요.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="eb7d4-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="eb7d4-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="eb7d4-121">Related topics</span></span>

[<span data-ttu-id="eb7d4-122">Teams PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="eb7d4-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="eb7d4-123">Teams PowerShell을 통해 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="eb7d4-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="eb7d4-124">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="eb7d4-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="eb7d4-125">Microsoft Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="eb7d4-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="eb7d4-126">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="eb7d4-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="eb7d4-127">Microsoft Teams 관리자 역할을 사용하여 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="eb7d4-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)