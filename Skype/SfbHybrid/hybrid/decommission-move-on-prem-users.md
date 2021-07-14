---
title: 클라우드로 사용자 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 사용자 이동을 해제하기 전에 비즈니스용 Skype 환경을 해제합니다.
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420813"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="aea94-103">사내 환경을 해제하기 전에 필요한 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="aea94-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="aea94-104">이 문서에서는 필요한 사용자를 Microsoft 클라우드로 이동한 후, 해당 환경을 해제하기 전에 microsoft 클라우드로 이동하는 비즈니스용 Skype 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="aea94-105">이 단계는 다음 단계 중 1단계로, 프레미스 환경을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="aea94-106">**1단계. 필요한 모든 사용자를 온라인에서 프레미스로 이동**</span><span class="sxs-lookup"><span data-stu-id="aea94-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="aea94-107">(이 문서)</span><span class="sxs-lookup"><span data-stu-id="aea94-107">(This article)</span></span>

- <span data-ttu-id="aea94-108">2단계.</span><span class="sxs-lookup"><span data-stu-id="aea94-108">Step 2.</span></span> <span data-ttu-id="aea94-109">[하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="aea94-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="aea94-110">3단계.</span><span class="sxs-lookup"><span data-stu-id="aea94-110">Step 3.</span></span> <span data-ttu-id="aea94-111">[하이브리드 응용 프로그램 끝점을](decommission-move-on-prem-endpoints.md)온라인 프레미스에서 온라인으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span> <span data-ttu-id="aea94-112">이 단계를 완료할 때까지 위의 2단계를 수행하는 시간 사이에 기존 하이브리드 응용 프로그램 끝점을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-112">Be aware that any existing hybrid application endpoints will not be discoverable between the time you perform Step 2 above until you complete this step.</span></span> <span data-ttu-id="aea94-113">동일한 유지 관리 창에서 2단계와 3단계를 모두 수행하기로 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-113">You should plan to do both steps 2 and 3 in the same maintenance window.</span></span>

- <span data-ttu-id="aea94-114">4단계.</span><span class="sxs-lookup"><span data-stu-id="aea94-114">Step 4.</span></span> <span data-ttu-id="aea94-115">[배포 에서 프레미스 비즈니스용 Skype 제거합니다.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="aea94-115">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="aea94-116">필요한 모든 사용자를 사내에서 클라우드로 이동</span><span class="sxs-lookup"><span data-stu-id="aea94-116">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="aea94-117">마이그레이션을 완료한 후에도 계속 사용할 모든 사용자는 먼저 사내에서 클라우드로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-117">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="aea94-118">사용자는 사내 관리 도구를 사용하여 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-118">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="aea94-119">자세한 내용은 [Move users between on-premises and cloud을 참조합니다.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="aea94-119">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="aea94-120">모든 계정을 사용하는 사용자가 비즈니스용 Skype 서버 계정을 사용할 수 Teams 이러한 사용자는 모든 기능을 사용할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="aea94-120">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="aea94-121">이러한 사용자는 여전히 온라인 또는 비즈니스용 Skype 사용하여 다른 사용자와 상호 비즈니스용 Skype 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-121">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="aea94-122">이러한 사용자는 자신의 클라이언트에서 PSTN 통화를 받을 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-122">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="aea94-123">따라서 이러한 사용자를 온라인으로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-123">Therefore, you must move these users to online.</span></span> <span data-ttu-id="aea94-124">또한 이 단계에서는 모든 연락처 또는 모임이 비즈니스용 Skype 서버 마이그레이션되도록 Teams.</span><span class="sxs-lookup"><span data-stu-id="aea94-124">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="aea94-125">사내 배포에 남은 사용자가 있는 경우 PowerShell 창에서 다음 cmdlet을 비즈니스용 Skype 서버 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-125">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="aea94-126">사용자가 반환되는 경우 출력을 검토하여 계정을 클라우드로 이동해야 하는지 여부를 확인한 다음 해당 사용자에 대해 여기에 있는 단계를 [따릅니다.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="aea94-126">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="aea94-127">더 이상 필요하지 않습니다. 사용자 계정의 경우 PowerShell cmdlet에 비즈니스용 Skype 서버 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-127">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="aea94-128">이 Disable-CsUser 실행하면 필터 조건을 비즈니스용 Skype 모든 사용자에 대한 모든 비즈니스용 Skype 특성이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-128">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="aea94-129">계속하기 전에 이러한 계정이 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aea94-129">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="aea94-130">이제 하이브리드 구성을 [사용하지 않도록 설정할 준비가 완료되었습니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="aea94-130">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aea94-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aea94-131">See also</span></span>

- [<span data-ttu-id="aea94-132">온-프레미스 비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="aea94-132">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="aea94-133">하이브리드 구성을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="aea94-133">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="aea94-134">하이브리드 응용 프로그램 끝점을 사내에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="aea94-134">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="aea94-135">온-프레미스 비즈니스용 Skype 배포 제거</span><span class="sxs-lookup"><span data-stu-id="aea94-135">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




