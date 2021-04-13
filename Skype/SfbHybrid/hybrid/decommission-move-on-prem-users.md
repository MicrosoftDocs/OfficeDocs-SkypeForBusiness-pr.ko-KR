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
description: 비즈니스용 Skype를 해제하기 전에 사용자를 이동하세요.
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656674"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="7cfcc-103">사내 환경을 해제하기 전에 필요한 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="7cfcc-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="7cfcc-104">이 문서에서는 필요한 사용자를 Microsoft 클라우드로 이동한 후, 비즈니스용 Skype 환경을 해제하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="7cfcc-105">이 단계는 다음 단계 중 1단계로, 프레미스 환경을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="7cfcc-106">**1단계. 필요한 모든 사용자를 온라인에서 프레미스로 이동**</span><span class="sxs-lookup"><span data-stu-id="7cfcc-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="7cfcc-107">(이 문서)</span><span class="sxs-lookup"><span data-stu-id="7cfcc-107">(This article)</span></span>

- <span data-ttu-id="7cfcc-108">2단계.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-108">Step 2.</span></span> <span data-ttu-id="7cfcc-109">[하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="7cfcc-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="7cfcc-110">3단계.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-110">Step 3.</span></span> <span data-ttu-id="7cfcc-111">[하이브리드 응용 프로그램 끝점을](decommission-move-on-prem-endpoints.md)프레미스에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="7cfcc-111">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="7cfcc-112">4단계.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-112">Step 4.</span></span> <span data-ttu-id="7cfcc-113">[비즈니스용 Skype 배포를 제거합니다.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="7cfcc-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="7cfcc-114">필요한 모든 사용자를 사내에서 클라우드로 이동</span><span class="sxs-lookup"><span data-stu-id="7cfcc-114">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="7cfcc-115">마이그레이션을 완료한 후에도 계속 사용할 모든 사용자는 먼저 사내에서 클라우드로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-115">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="7cfcc-116">사용자는 사내 관리 도구를 사용하여 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-116">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="7cfcc-117">자세한 내용은 [Move users between on-premises and cloud을 참조합니다.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="7cfcc-117">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="7cfcc-118">비즈니스용 Skype 서버 계정이 있는 사용자가 Teams를 사용할 수 있는 것은 가능하기는 하지만 이러한 사용자는 Teams의 전체 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-118">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="7cfcc-119">이러한 사용자는 비즈니스용 Skype를 여전히 사용하는 다른 사용자(온라인 또는 사내에 관계 없이)와 상호 연결하거나 페더러에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-119">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="7cfcc-120">이러한 사용자는 Teams 클라이언트에서 PSTN 통화를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-120">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="7cfcc-121">따라서 이러한 사용자를 온라인으로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-121">Therefore, you must move these users to online.</span></span> <span data-ttu-id="7cfcc-122">또한 이 단계를 통해 비즈니스용 Skype 서버에서 만든 연락처 또는 모임이 Teams로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-122">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="7cfcc-123">사내 배포에 남은 사용자가 있는 경우 비즈니스용 Skype 서버 PowerShell 창에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-123">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="7cfcc-124">사용자가 반환되는 경우 출력을 검토하여 계정을 클라우드로 이동해야 하는지 여부를 확인한 다음 해당 사용자에 대해 여기에 있는 단계를 [따릅니다.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="7cfcc-124">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="7cfcc-125">더 이상 필요하지 않습니다. 사용자 계정의 경우 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-125">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="7cfcc-126">이 Disable-CsUser 실행하면 필터 조건을 충족하는 모든 사용자의 모든 비즈니스용 Skype 특성이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-126">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="7cfcc-127">계속하기 전에 이러한 계정이 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcc-127">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="7cfcc-128">이제 하이브리드 구성을 [사용하지 않도록 설정할 준비가 완료되었습니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="7cfcc-128">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7cfcc-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7cfcc-129">See also</span></span>

- [<span data-ttu-id="7cfcc-130">온-프레미스 비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="7cfcc-130">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="7cfcc-131">하이브리드 구성을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="7cfcc-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="7cfcc-132">하이브리드 응용 프로그램 끝점을 사내에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="7cfcc-132">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="7cfcc-133">온-프레미스 비즈니스용 Skype 배포 제거</span><span class="sxs-lookup"><span data-stu-id="7cfcc-133">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




