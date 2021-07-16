---
title: 하이브리드를 사용하지 않도록 설정하여 하이브리드 전용으로 Teams 완료
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 문서에는 클라우드 통합 및 클라우드 통합의 일부로 하이브리드를 Teams 비즈니스용 Skype.
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453647"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="797bb-103">하이브리드 구성을 사용하지 않도록 설정하여 하이브리드 구성만 Teams 완료</span><span class="sxs-lookup"><span data-stu-id="797bb-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="797bb-104">이 문서에서는 하이브리드 구성을 해제하기 전에 하이브리드 구성을 사용하지 않도록 설정하는 비즈니스용 Skype 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="797bb-105">이 단계는 다음 단계 중 2단계로, 프레미스 환경을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="797bb-106">1단계.</span><span class="sxs-lookup"><span data-stu-id="797bb-106">Step 1.</span></span> <span data-ttu-id="797bb-107">필요한 모든 사용자를 프레미스에서 [온라인으로 이동](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="797bb-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="797bb-108">**2단계. 하이브리드 구성을 사용하지 않도록 설정**</span><span class="sxs-lookup"><span data-stu-id="797bb-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="797bb-109">(이 문서)</span><span class="sxs-lookup"><span data-stu-id="797bb-109">(This article)</span></span>

- <span data-ttu-id="797bb-110">3단계.</span><span class="sxs-lookup"><span data-stu-id="797bb-110">Step 3.</span></span> <span data-ttu-id="797bb-111">[하이브리드 응용 프로그램 끝점을](decommission-move-on-prem-endpoints.md)온라인 프레미스에서 온라인으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="797bb-112">4단계.</span><span class="sxs-lookup"><span data-stu-id="797bb-112">Step 4.</span></span> <span data-ttu-id="797bb-113">[배포 에서 프레미스 비즈니스용 Skype 제거합니다.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="797bb-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="797bb-114">2단계와 3단계 완료 사이에 기존 하이브리드 응용 프로그램 끝점을 검색할 수 없는 것이기 때문에 2단계와 3단계는 동일한 유지 관리 기간에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>


## <a name="summary"></a><span data-ttu-id="797bb-115">요약</span><span class="sxs-lookup"><span data-stu-id="797bb-115">Summary</span></span>

<span data-ttu-id="797bb-116">모든 사용자를 비즈니스용 Skype 프레미스에서 Teams Microsoft 365 배포를 해제할 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span>

<span data-ttu-id="797bb-117">하이브리드 배포를 해제하고 비즈니스용 Skype 배포를 해제하고 하드웨어를 제거하기 전에 하이브리드를 해제하여 Microsoft 365 배포와 논리적으로 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="797bb-118">하이브리드를 비동기화하는 단계는 다음 네 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="797bb-119">[을(를) 지점으로 하여 DNS 레코드를 Microsoft 365.](#update-dns-to-point-to-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="797bb-119">[Update DNS records to point to Microsoft 365](#update-dns-to-point-to-microsoft-365).</span></span>

2. <span data-ttu-id="797bb-120">조직의 동시 사용 모드를 을 로 [Teams 변경합니다.](#change-the-coexistence-mode-for-your-organization-to-teams-only)</span><span class="sxs-lookup"><span data-stu-id="797bb-120">[Change the coexistence mode for your organization to Teams Only](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span></span>

3. <span data-ttu-id="797bb-121">조직에서 공유 sip 주소 공간("분할 [도메인"이라고도 하는)을 사용하지 Microsoft 365 합니다.](#disable-shared-sip-address-space-in-microsoft-365-organization)</span><span class="sxs-lookup"><span data-stu-id="797bb-121">[Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization](#disable-shared-sip-address-space-in-microsoft-365-organization).</span></span>

4. [<span data-ttu-id="797bb-122">프레미스 및 프레미스 간의 통신을 사용하지 않도록 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="797bb-122">Disable communication between on-premises and Microsoft 365</span></span>](#disable-communication-between-on-premises-and-microsoft-365)

<span data-ttu-id="797bb-123">이러한 단계는 온-프레미스 배포를 논리적으로 비즈니스용 Skype 서버 Microsoft 365 조직이 완전히 Teams 전용이 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="797bb-124">이러한 단계를 완료한 후 를 해제한 후 특성을 관리하는 방법 결정에 참조된 두 가지 방법 중 하나를 사용하여 비즈니스용 Skype 배포를 해제할 수 [있습니다.](cloud-consolidation-managing-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="797bb-124">After you've completed these steps, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

> [!Important] 
> <span data-ttu-id="797bb-125">이 논리적 분리가 완료되면, 사내 Active Directory의 msRTCSIP 특성은 여전히 값을 가지며 Azure AD 계정을 통해 Azure AD로 커넥트 계속 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-125">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="797bb-126">사내 환경을 해제하는 방법은 이러한 특성을 그대로 두는지 아니면 먼저 해당 특성을 On-프레미스 Active Directory에서 지우는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-126">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="797bb-127">사내에서 마이그레이션한 후 사내 msRTCSIP 특성을 지우면 사용자에 대한 서비스가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-127">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="797bb-128">두 가지 해제 방법의 세부 정보 및 장단점은 해지 후 특성을 관리하는 방법 결정에 [설명되어 있습니다.](cloud-consolidation-managing-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="797bb-128">Details and tradeoffs of the two decommissioning approaches are described in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

## <a name="update-dns-to-point-to-microsoft-365"></a><span data-ttu-id="797bb-129">DNS를 업데이트하여 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="797bb-129">Update DNS to point to Microsoft 365</span></span>

<span data-ttu-id="797bb-130">비즈니스용 Skype 레코드가 Microsoft 365 대신 조직의 외부 DNS를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-130">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> 

<span data-ttu-id="797bb-131">또한 meet 또는 dialin(있는 경우)에 대한 CNAME 레코드를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-131">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="797bb-132">마지막으로 내부 네트워크에서 비즈니스용 Skype DNS 레코드를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-132">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

<span data-ttu-id="797bb-133">DNS 레코드 업데이트에 대한 자세한 내용은 [Update DNS entries to enable your organization to be all Teams.](decommission-manage-dns-entries.md)</span><span class="sxs-lookup"><span data-stu-id="797bb-133">For details about updating DNS records, see [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span></span>

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a><span data-ttu-id="797bb-134">조직의 동시 사용 모드를 2016만 Teams 변경</span><span class="sxs-lookup"><span data-stu-id="797bb-134">Change the coexistence mode for your organization to Teams Only</span></span>

<span data-ttu-id="797bb-135">이 단계를 통해 조직의 새 사용자가 항상 사용자 전용 사용자로 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-135">This step ensures that any new user in your organization is always created as a Teams Only user.</span></span> 

<span data-ttu-id="797bb-136">테넌트 모드를 Teams 1단계에서 누락된 모든 사내 DNS 레코드가 존재하는지 자동으로 확인하고 출력에서 이러한 레코드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-136">Attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span> <span data-ttu-id="797bb-137">테넌트 모드를 Teams 조직의 모든 DNS 레코드가 업데이트될 때까지만 성공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-137">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organization are updated.</span></span> 

<span data-ttu-id="797bb-138">테넌트 모드를 Teams PowerShell 창에서만 Teams 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-138">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

<span data-ttu-id="797bb-139">또는 "Teams 설정" -> "업그레이드" 아래에서 Teams 관리 센터를 사용하여 테넌트 공존 모드를 TeamsOnly로 변경할 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-139">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a><span data-ttu-id="797bb-140">조직에서 공유 sip 주소 Microsoft 365 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="797bb-140">Disable shared sip address space in Microsoft 365 organization</span></span>
    
<span data-ttu-id="797bb-141">공유 sip 주소 공간을 사용하지 않도록 설정하기 위해 PowerShell 창의 Teams 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="797bb-141">To disable shared sip address space, run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a><span data-ttu-id="797bb-142">프레미스 및 프레미스 간의 통신을 사용하지 않도록 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="797bb-142">Disable communication between on-premises and Microsoft 365</span></span>

<span data-ttu-id="797bb-143">On-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:</span><span class="sxs-lookup"><span data-stu-id="797bb-143">To disable communication between the on-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:</span></span>

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a><span data-ttu-id="797bb-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="797bb-144">See also</span></span>

- [<span data-ttu-id="797bb-145">비즈니스 및 Teams 클라우드 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="797bb-145">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="797bb-146">온-프레미스 비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="797bb-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

