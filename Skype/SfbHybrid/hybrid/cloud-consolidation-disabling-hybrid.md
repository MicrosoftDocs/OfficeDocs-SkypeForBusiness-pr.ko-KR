---
title: 클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화
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
description: 이 문서에는 Teams 및 비즈니스용 Skype에 대한 클라우드 통합의 일부로 하이브리드를 사용 안 하게 하는 자세한 단계가 포함되어 있습니다.
ms.openlocfilehash: 5528172c6a9309a0884c9417a64da589f0f0d4a4
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593856"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-the-cloud"></a><span data-ttu-id="8670d-103">하이브리드 구성을 사용하지 않도록 설정하여 클라우드로의 마이그레이션 완료</span><span class="sxs-lookup"><span data-stu-id="8670d-103">Disable your hybrid configuration to complete migration to the cloud</span></span>

<span data-ttu-id="8670d-104">이 문서에서는 비즈니스용 Skype 환경을 해제하기 전에 하이브리드 구성을 사용하지 않도록 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="8670d-105">이 단계는 다음 단계 중 2단계로, 프레미스 환경을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="8670d-106">1단계.</span><span class="sxs-lookup"><span data-stu-id="8670d-106">Step 1.</span></span> <span data-ttu-id="8670d-107">필요한 모든 사용자 및 [응용 프로그램 끝점을](decommission-move-on-prem-users.md)프레미스에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="8670d-107">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="8670d-108">**2단계. 하이브리드 구성을 사용하지 않도록 설정**</span><span class="sxs-lookup"><span data-stu-id="8670d-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="8670d-109">(이 문서)</span><span class="sxs-lookup"><span data-stu-id="8670d-109">(This article)</span></span>

- <span data-ttu-id="8670d-110">3단계.</span><span class="sxs-lookup"><span data-stu-id="8670d-110">Step 3.</span></span> <span data-ttu-id="8670d-111">[비즈니스용 Skype 배포를 제거합니다.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="8670d-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="overview"></a><span data-ttu-id="8670d-112">개요</span><span class="sxs-lookup"><span data-stu-id="8670d-112">Overview</span></span>

<span data-ttu-id="8670d-113">비즈니스용 Skype의 모든 사용자를 Microsoft 365의 Teams 전용으로 업그레이드한 후 비즈니스용 Skype 배포를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-113">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="8670d-114">비즈니스용 Skype 배포를 해제하고 하드웨어를 제거하기 전에 하이브리드를 해제하여 Microsoft 365에서 논리적으로 배포를 분리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-114">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="8670d-115">하이브리드를 비동기화하는 단계는 다음 세 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-115">Disabling hybrid consists of the following three steps:</span></span>

1. <span data-ttu-id="8670d-116">Microsoft 365를 가리키도록 DNS 레코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-116">Update DNS records to point to Microsoft 365.</span></span>

2. <span data-ttu-id="8670d-117">Microsoft 365 조직에서 공유 sip 주소 공간("분할 도메인"이라고도 알려지기)을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-117">Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization.</span></span>

3. <span data-ttu-id="8670d-118">Microsoft 365와 통신하는 기능을 사내에서 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8670d-118">Disable the ability in on-premises to communicate with Microsoft 365.</span></span>

<span data-ttu-id="8670d-119">이러한 단계는 비즈니스용 Skype 서버의 사내 배포를 Microsoft 365와 논리적으로 분리하며 단위로 함께 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-119">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and should be done together as a unit.</span></span> <span data-ttu-id="8670d-120">이 문서에서는 각 단계에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-120">Details for each step are provided in this article.</span></span> <span data-ttu-id="8670d-121">완료되면 아래 참조된 두 가지 방법 중 하나를 사용하여 비즈니스용 Skype 배포를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-121">Once that is complete, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced below.</span></span>

> [!Important] 
> <span data-ttu-id="8670d-122">이 논리적 분리가 완료되면, 사내 Active Directory의 msRTCSIP 특성은 여전히 값을 가지며 Azure AD Connect를 통해 Azure AD로 계속 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-122">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="8670d-123">사내 환경을 해제하는 방법은 이러한 특성을 그대로 두는지 아니면 먼저 해당 특성을 On-프레미스 Active Directory에서 지우는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-123">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="8670d-124">사내에서 마이그레이션한 후 사내 msRTCSIP 특성을 지우면 사용자에 대한 서비스가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-124">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="8670d-125">두 가지 해제 방법의 세부 정보 및 장단점에 대한 설명은 나중에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-125">Details and tradeoffs of the two decommissioning approaches are described later.</span></span>

## <a name="detailed-steps"></a><span data-ttu-id="8670d-126">세부 단계</span><span class="sxs-lookup"><span data-stu-id="8670d-126">Detailed Steps</span></span>

1. <span data-ttu-id="8670d-127">*Microsoft 365를 지점으로 DNS를 업데이트합니다.*</span><span class="sxs-lookup"><span data-stu-id="8670d-127">*Update DNS to point to Microsoft 365.*</span></span> <span data-ttu-id="8670d-128">비즈니스용 Skype 레코드가 Microsoft 365를 프레미스 배포가 아닌 Microsoft 365를 지점으로 하게 하기 위해 조직에 대한 조직의 외부 DNS를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-128">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="8670d-129">특히 다음 사항에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-129">Specifically:</span></span>

    |<span data-ttu-id="8670d-130">레코드 유형</span><span class="sxs-lookup"><span data-stu-id="8670d-130">Record type</span></span>|<span data-ttu-id="8670d-131">이름</span><span class="sxs-lookup"><span data-stu-id="8670d-131">Name</span></span>|<span data-ttu-id="8670d-132">TTL</span><span class="sxs-lookup"><span data-stu-id="8670d-132">TTL</span></span>|<span data-ttu-id="8670d-133">값</span><span class="sxs-lookup"><span data-stu-id="8670d-133">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="8670d-134">SRV</span><span class="sxs-lookup"><span data-stu-id="8670d-134">SRV</span></span>|<span data-ttu-id="8670d-135">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="8670d-135">_sipfederationtls._tcp</span></span>|<span data-ttu-id="8670d-136">3600</span><span class="sxs-lookup"><span data-stu-id="8670d-136">3600</span></span>|<span data-ttu-id="8670d-137">100 1 5061 sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="8670d-137">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8670d-138">SRV</span><span class="sxs-lookup"><span data-stu-id="8670d-138">SRV</span></span>|<span data-ttu-id="8670d-139">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="8670d-139">_sip._tls</span></span>|<span data-ttu-id="8670d-140">3600</span><span class="sxs-lookup"><span data-stu-id="8670d-140">3600</span></span>|<span data-ttu-id="8670d-141">100 1 443 sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="8670d-141">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8670d-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="8670d-142">CNAME</span></span>| <span data-ttu-id="8670d-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8670d-143">lyncdiscover</span></span>|   <span data-ttu-id="8670d-144">3600</span><span class="sxs-lookup"><span data-stu-id="8670d-144">3600</span></span>|   <span data-ttu-id="8670d-145">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="8670d-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8670d-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="8670d-146">CNAME</span></span>| <span data-ttu-id="8670d-147">sip</span><span class="sxs-lookup"><span data-stu-id="8670d-147">sip</span></span>|    <span data-ttu-id="8670d-148">3600</span><span class="sxs-lookup"><span data-stu-id="8670d-148">3600</span></span>|   <span data-ttu-id="8670d-149">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="8670d-149">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="8670d-150">또한 meet 또는 dialin(있는 경우)에 대한 CNAME 레코드를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-150">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="8670d-151">마지막으로 내부 네트워크에서 비즈니스용 Skype에 대한 DNS 레코드를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-151">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="8670d-152">드문 경우지만 DNS를 조직의 Microsoft 365로 설정하는 경우 다른 조직에서 페더링 구성을 업데이트할 때까지 일부 다른 조직과의 페더링이 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-152">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="8670d-153">이전 Direct Federation 모델(허용 파트너 서버라고도 지칭)을 사용하는 페더러된 조직은 조직에 대해 허용되는 도메인 항목을 업데이트하여 프록시 FQDN을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-153">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="8670d-154">이 레거시 페더전 모델은 DNS SRV 레코드를 기반으로 하지 않습니다. 따라서 조직이 클라우드로 이동하면 이러한 구성이 최신이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-154">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="8670d-155">sipfed.online.lync에 대해 호스팅 공급자를 사용하도록 설정하지 않은 페더링된 조직입니다. <span> com은 구성을 업데이트하여 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-155">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="8670d-156">이 상황은 페더러드 조직이 전적으로 사내에 있으며 하이브리드 또는 온라인 테넌트와 페더러이트한 적이 없는 경우만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-156">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="8670d-157">이 경우 호스팅 공급자를 사용하도록 설정해야 이러한 조직과의 페더링이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-157">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="8670d-158">페더더러 파트너 중 한 자가 직접 페더ation을 사용 중일 수 있는 것으로 의심되거나 온라인 또는 하이브리드 조직과 페더러이트되지 않은 것으로 의심되는 경우 클라우드로의 마이그레이션을 완료할 준비를 할 때 이에 대한 통신을 해당 파트너에게 보내는 것이 좋은 제안입니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-158">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="8670d-159">*Microsoft 365 조직에서 공유 sip 주소 공간을 사용하지 않도록 설정*</span><span class="sxs-lookup"><span data-stu-id="8670d-159">*Disable shared sip address space in Microsoft 365 organization.*</span></span> <span data-ttu-id="8670d-160">아래 명령은 비즈니스용 Skype Online PowerShell 창에서 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-160">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  <span data-ttu-id="8670d-161">*Microsoft 365와 통신하는 기능을 사내에서 사용하지 않도록 설정*</span><span class="sxs-lookup"><span data-stu-id="8670d-161">*Disable the ability in on-premises to communicate with Microsoft 365.*</span></span> <span data-ttu-id="8670d-162">아래 명령은 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-162">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="8670d-163">사용자를 사내에서 클라우드로 이동한 후 특성 관리</span><span class="sxs-lookup"><span data-stu-id="8670d-163">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="8670d-164">기본적으로 이전에 비즈니스용 Skype 서버를 사용하도록 설정되어 클라우드로 이동한 모든 사용자는 여전히 msRTCSIP 특성이 사내 Active Directory에 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-164">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="8670d-165">이러한 특성, 특히 sip 주소(msRTCSIP-PrimaryUserAddress) 및 잠재적으로 전화 번호(msRTCSIP-Line)는 Azure AD에 계속 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-165">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="8670d-166">msRTCSIP 특성 중 어느 것이든 변경해야 하는 경우 이러한 변경 내용은 On-premises Active Directory에서 적용한 다음 Azure AD와 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-166">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="8670d-167">그러나 비즈니스용 Skype 서버 배포가 제거되면 비즈니스용 Skype 서버 도구를 사용하여 이러한 특성을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-167">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="8670d-168">이 상황을 처리하는 두 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-168">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="8670d-169">비즈니스용 Skype 서버 계정에 대해 사용하도록 설정된 사용자를 그대로 사용하고 Active Directory 도구를 사용하여 msRTCSIP 특성을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-169">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="8670d-170">이렇게 하면 마이그레이션된 사용자의 서비스가 손실되지 않고, 전체 해제 없이 서버를 제거(예: 지우기)하여 비즈니스용 Skype 서버 배포를 쉽게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-170">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="8670d-171">그러나 새로 라이선스가 부여된 사용자는 이러한 특성을 On-premises Active Directory에 채우지 못하며 온라인에서 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-171">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="8670d-172">모든 msRTCSIP 특성을 모든 msRTCSIP 특성의 선택을 취소하고 온라인 도구를 사용하여 이러한 특성을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-172">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="8670d-173">이 방법을 사용하면 기존 사용자와 새 사용자에 대해 일관된 관리 방식을 사용할 수 있습니다. 그러나 잠재적으로는 사내 해제 프로세스 중에 서비스가 일시적으로 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-173">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="8670d-174">방법 1 - Active Directory에서 사용자의 sip 주소 및 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="8670d-174">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="8670d-175">관리자는 이전의 비즈니스용 Skype 서버에서 클라우드로 이동된 사용자를 관리할 수 있습니다. 이 사용자는 사내 배포가 해제된 후에도 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-175">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="8670d-176">사용자의 sip 주소 또는 사용자의 전화 번호(및 sip 주소 또는 전화 번호에 이미 On-premises Active Directory에 값이 있는 경우)를 변경하려는 경우, 이 작업을 On-premises Active Directory에서 이 작업을 하고 값이 Azure AD로 흐르게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-176">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="8670d-177">이 서버에는 비즈니스용 Skype 서버가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-177">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="8670d-178">대신, Active Directory 사용자 및 컴퓨터 MMC 스냅인(아래 그림과 같이)을 사용하거나 PowerShell을 사용하여 이러한 특성을 On-premises Active Directory에서 직접 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-178">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="8670d-179">MMC 스냅인을 사용하는 경우 사용자의 속성 페이지를 열고 특성 편집기 탭을 클릭한 후 수정할 적절한 특성을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-179">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="8670d-180">사용자의 sip 주소를 수정하려면 를 `msRTCSIP-PrimaryUserAddress` 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-180">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="8670d-181">특성에 sip 주소가 포함되어 있는 경우 해당 값을 모범 사례로 `ProxyAddresses` 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-181">Note, if the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="8670d-182">의 sip 주소가 채워진 경우 O365에서 무시해도 다른 사내 구성 요소에서 사용할 `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-182">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="8670d-183">사용자의 전화 번호를 수정하려면 값이 이미 있는 경우 `msRTCSIP-Line` *수정합니다.*</span><span class="sxs-lookup"><span data-stu-id="8670d-183">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 사용자 및 컴퓨터 도구](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="8670d-185">사용자가 이동하기 전에 원래의 값이 아닌 경우 비즈니스용 Skype Online PowerShell 모듈의 `msRTCSIP-Line` `onpremLineUri` [Set-CsUser cmdlet에서](/powershell/module/skype/set-csuser?view=skype-ps) - 매개 변수를 사용하여 전화 번호를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-185">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="8670d-186">하이브리드를 사용하지 않도록 설정한 후 새로 만든 사용자는 이러한 단계를 수행하지 않고 클라우드에서 직접 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-186">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="8670d-187">이러한 방법과 msRTCSIP 특성을 모두 사용하는 것뿐만 아니라 이러한 방법을 사용하는 것이 편한 경우, 단순히 비즈니스용 Skype 서버를 다시 이미지로 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-187">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="8670d-188">그러나 모든 msRTCSIP 특성을 지우고 비즈니스용 Skype 서버의 기존 제거를 원하는 경우 방법 2를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-188">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="8670d-189">방법 2 - Active Directory의 모든 사내 사용자에 대한 비즈니스용 Skype 특성 지우기</span><span class="sxs-lookup"><span data-stu-id="8670d-189">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="8670d-190">이 옵션을 사용하려면 이전에 비즈니스용 Skype 서버에서 클라우드로 이동한 사용자를 다시 프로비전해야 했기 때문에 추가 작업 및 적절한 계획이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-190">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="8670d-191">이러한 사용자는 전화 시스템이 없는 사용자와 전화 시스템이 있는 사용자 등 두 가지 범주로 분류될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-191">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="8670d-192">전화 시스템을 사용할 경우 전화 번호를 클라우드로 전환할 때 전화 번호가 일시적으로 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-192">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="8670d-193">**대량 사용자 작업을 시작하기 전에 적은 수의 사용자가 전화 시스템을 포함하는 파일럿을 수행하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="8670d-193">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="8670d-194">대규모 배포의 경우 사용자는 서로 다른 시간 창의 소규모 그룹에서 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-194">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="8670d-195">이 프로세스는 일치하는 sip 주소와 UserPrincipalName이 있는 사용자에게 가장 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-195">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="8670d-196">이러한 두 특성에서 일치하지 않는 값이 있는 사용자가 있는 조직의 경우 원활한 전환을 위해 아래에서 설명한에 따라 특히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-196">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="8670d-197">자동 전화 걸기 또는 통화 큐에 대해 사내 하이브리드 응용 프로그램 끝점을 구성한 경우 비즈니스용 Skype 서버를 해제하기 전에 이러한 끝점을 Microsoft 365로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-197">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="8670d-198">다음의 비즈니스용 Skype PowerShell cmdlet이 빈 결과를 반환하는지 확인</span><span class="sxs-lookup"><span data-stu-id="8670d-198">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="8670d-199">결과가 비어 있는 것은 사용자가 사내에 있거나 Microsoft 365로 이동되거나 비활성화된 사용자가 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-199">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="8670d-200">다음의 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 사용자 데이터를 내보내어 사용자의 현재 전화 번호(LineUri), UserPrincipalName 및 관련 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-200">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="8670d-201">파일 열기 SfbUserSettings.csv 모든 사용자 데이터를 성공적으로 내보낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-201">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="8670d-202">이 파일의 복사본을 보관하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-202">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="8670d-203">다음 단계에서는 사용자를 처리하기 위해 이 파일을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-203">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="8670d-204">다음 단계에서 사용할 사용자 그룹이 있는 파일을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="8670d-204">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="8670d-205">첫 번째 사용자 그룹이 성공적으로 완료되면 다음 사용자 그룹으로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-205">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="8670d-206">아래 예제에서는 사용자 그룹이 사전순으로 선택되지만 사용자를 처리하고자 하는 방식과 일치하는 기준에 따라 사용자를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-206">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="8670d-207">파일 열기 SfbUsers.csv 사용자 데이터가 성공적으로 내보혔는지 확인하기 전에</span><span class="sxs-lookup"><span data-stu-id="8670d-207">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="8670d-208">이후 단계에서 이 파일의 LineUri(전화 번호), UserPrincipalName, SamAccountName 및 SipAddress가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-208">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="8670d-209">업데이트할 준비가 된 사용자 집합에 대해 Active Directory에서 비즈니스용 Skype 서버와 관련된 특성 정보를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-209">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="8670d-210">아래와 같이 이 프로세스에는 2단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-210">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="8670d-211">이 단계를 실행한 후 다음 AAD 동기화 주기가 완료되면 이전에 비즈니스용 Skype 서버에서 클라우드로 이동한 전화 시스템을 사용 중인 사용자는 8단계가 성공적으로 완료되고 9단계에서 확인될 때까지 전화를 걸고 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-211">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="8670d-212">또한 해당 단계에 해당 정보가 필요하기 때문에 2단계에 따라 사용자의 전화 번호 및 관련 정보를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-212">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="8670d-213">다음으로, 동일한 사용자 집합에 대해, 다음을 사용하여 msRTCSIP-DeploymentLocator의 값을 지우고, 다음을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-213">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="8670d-214">다음의 비즈니스용 Skype PowerShell cmdlet을 실행하여 sip 주소 값을 다시 On-premises Active Directory proxyAddresses에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-214">Run the following on-premise Skype for Business PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="8670d-215">이렇게 하면 이 특성을 사용 하는 상호 연산 문제가 방지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-215">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="8670d-216">Azure AD 동기화 실행</span><span class="sxs-lookup"><span data-stu-id="8670d-216">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="8670d-217">사용자 프로비전이 완료될 때까지 기다렸다가</span><span class="sxs-lookup"><span data-stu-id="8670d-217">Wait for user provisioning to complete.</span></span> <span data-ttu-id="8670d-218">다음 비즈니스용 Skype Online PowerShell 명령을 실행하여 사용자 프로비전 진행 상황을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-218">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="8670d-219">다음 비즈니스용 Skype Online PowerShell 명령은 프로세스가 완료된 즉시 빈 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-219">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="8670d-220">다음 비즈니스용 Skype Online PowerShell 명령을 실행하여 전화 번호를 할당하고 사용자가 전화 시스템을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-220">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="8670d-221">여전히 비즈니스용 Skype 끝점(Skype 클라이언트 또는 제3자 전화)이 있는 경우 -HostedVoiceMail을 $true.</span><span class="sxs-lookup"><span data-stu-id="8670d-221">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="8670d-222">조직에서 음성 사용 가능 사용자에 대해 Teams 끝점만 사용하는 경우 이 설정은 사용자에게 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-222">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="8670d-223">전화 시스템 기능이 있는 사용자가 올바르게 프로비전되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-223">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="8670d-224">다음 비즈니스용 Skype Online PowerShell 명령은 프로세스가 완료된 즉시 빈 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-224">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="8670d-225">모든 사용자가 처리될 때까지 3-9단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8670d-225">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="8670d-226">다음 두 PowerShell 명령을 실행하여 모든 사용자가 성공적으로 처리된지 확인</span><span class="sxs-lookup"><span data-stu-id="8670d-226">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="8670d-227">On-premises Skype for Business Server on-premises PowerShell command:</span><span class="sxs-lookup"><span data-stu-id="8670d-227">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="8670d-228">비즈니스용 Skype Online PowerShell 명령:</span><span class="sxs-lookup"><span data-stu-id="8670d-228">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="8670d-229">방법 2의 모든 단계를 완료한 후 [](decommission-remove-on-prem.md) 비즈니스용 Skype 서버 배포를 제거하는 추가 단계는 비즈니스용 Skype 서버 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8670d-229">After you have completed all steps in Method 2, refer to [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="8670d-230">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8670d-230">See also</span></span>

- [<span data-ttu-id="8670d-231">Teams 및 비즈니스용 Skype를 위한 클라우드 통합</span><span class="sxs-lookup"><span data-stu-id="8670d-231">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="8670d-232">비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="8670d-232">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)
