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
description: 이 부록에는 Teams 및 비즈니스용 Skype에 대한 클라우드 통합의 일부로 하이브리드를 사용 안 하게 하는 자세한 단계가 포함되어 있습니다.
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277252"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="65117-103">클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화</span><span class="sxs-lookup"><span data-stu-id="65117-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="65117-104">모든 사용자를 온-프레미스에서 클라우드로 이동한 후에는 온-프레미스 비즈니스용 Skype 배포를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="65117-105">하드웨어를 제거하는 것 외에도 중요한 단계는 하이브리드를 사용 안 하여 Microsoft 365 또는 Office 365에서 논리적으로 이를 분리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65117-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Microsoft 365 or Office 365 by disabling hybrid.</span></span> <span data-ttu-id="65117-106">하이브리드를 비우는 단계는 다음 3단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="65117-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="65117-107">Microsoft 365 또는 Office 365를 지점으로 DNS 레코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-107">Update DNS records to point to Microsoft 365 or Office 365.</span></span>

2. <span data-ttu-id="65117-108">Microsoft 365 또는 Office 365 조직에서 분할 도메인을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="65117-108">Disable split domain in the Microsoft 365 or Office 365 organization.</span></span>

3. <span data-ttu-id="65117-109">Microsoft 365 또는 Office 365와 통신하는 데 사용할 수 있는 기능을 On-프레미스에서 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="65117-109">Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="65117-110">이러한 단계는 한 단위로 함께 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="65117-111">자세한 내용은 아래를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="65117-111">Details are provided below.</span></span> <span data-ttu-id="65117-112">또한 마이그레이션된 사용자의 전화 번호를 관리하는 데 대한 지침도 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="65117-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

<span data-ttu-id="65117-113">이러한 단계가 완료되면 더 이상 비즈니스용 Skype 서버가 사용되지 않습니다. 이러한 서버를 다시 이미지화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-113">Once these steps are complete, the on-premises Skype for Business servers are no longer used, and these servers can be re-imaged.</span></span>

> [!Important] 
><span data-ttu-id="65117-114">Azure AD Connect를 통해 Active Directory의 msRTCSIP 특성이 Azure AD에 동기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-114">You should continue to let the msRTCSIP attributes in Active Directory sync via Azure AD Connect into Azure AD.</span></span>  <span data-ttu-id="65117-115">지원이 지시하지 않는 한 이러한 특성을 지우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-115">Do not clear any of these attributes unless directed to by Support.</span></span>  <span data-ttu-id="65117-116">모든 Disable-CsUser 환경에서는 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-116">Do not run Disable-CsUser in the on-premises environment.</span></span> <span data-ttu-id="65117-117">사용자의 SIP 주소를 수정해야 하는 경우, 이 작업을 On-premises Active Directory에서 이행하고 아래 설명된 Azure AD Connect를 통해 Azure AD에 이 변경이 동기화될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-117">If you need to modify a user’s SIP address, do this in your on-premises Active Directory and let this change sync into Azure AD via Azure AD Connect as described below.</span></span> <span data-ttu-id="65117-118">마찬가지로 전화 번호를 변경해야 하는 경우 사용자의 LineURI가 이미 On-premises에 정의되어 있는 경우 이 변경을 On-premises Active Directory에서 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-118">Similarly, if you need to change a telephone number and the user’s LineURI is already defined on-premises, you should modify this in the on-premises Active Directory.</span></span>
><span data-ttu-id="65117-119">사용자가온-프레미스에서 마이그레이션한 후 해당 특성을 지우면 사용자에 대한 서비스가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-119">Clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span>


1.  <span data-ttu-id="65117-120">*Microsoft 365 또는 Office 365를 지점으로 DNS를 업데이트합니다.*</span><span class="sxs-lookup"><span data-stu-id="65117-120">*Update DNS to point to Microsoft 365 or  Office 365.*</span></span>
<span data-ttu-id="65117-121">비즈니스용 Skype 레코드가 Microsoft 365 또는 Office 365 대신 Microsoft 365를 지원할 수 있도록 조직에 대한 조직의 외부 DNS를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 or Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="65117-122">특히 다음 사항에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-122">Specifically:</span></span>

    |<span data-ttu-id="65117-123">레코드 유형</span><span class="sxs-lookup"><span data-stu-id="65117-123">Record type</span></span>|<span data-ttu-id="65117-124">이름</span><span class="sxs-lookup"><span data-stu-id="65117-124">Name</span></span>|<span data-ttu-id="65117-125">TTL</span><span class="sxs-lookup"><span data-stu-id="65117-125">TTL</span></span>|<span data-ttu-id="65117-126">값</span><span class="sxs-lookup"><span data-stu-id="65117-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="65117-127">SRV</span><span class="sxs-lookup"><span data-stu-id="65117-127">SRV</span></span>|<span data-ttu-id="65117-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="65117-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="65117-129">3600</span><span class="sxs-lookup"><span data-stu-id="65117-129">3600</span></span>|<span data-ttu-id="65117-130">100 1 5061 sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="65117-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="65117-131">SRV</span><span class="sxs-lookup"><span data-stu-id="65117-131">SRV</span></span>|<span data-ttu-id="65117-132">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="65117-132">_sip._tls</span></span>|<span data-ttu-id="65117-133">3600</span><span class="sxs-lookup"><span data-stu-id="65117-133">3600</span></span>|<span data-ttu-id="65117-134">100 1 443 sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="65117-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="65117-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="65117-135">CNAME</span></span>| <span data-ttu-id="65117-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="65117-136">lyncdiscover</span></span>|   <span data-ttu-id="65117-137">3600</span><span class="sxs-lookup"><span data-stu-id="65117-137">3600</span></span>|   <span data-ttu-id="65117-138">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="65117-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="65117-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="65117-139">CNAME</span></span>| <span data-ttu-id="65117-140">sip</span><span class="sxs-lookup"><span data-stu-id="65117-140">sip</span></span>|    <span data-ttu-id="65117-141">3600</span><span class="sxs-lookup"><span data-stu-id="65117-141">3600</span></span>|   <span data-ttu-id="65117-142">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="65117-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="65117-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="65117-143">CNAME</span></span>| <span data-ttu-id="65117-144">meet</span><span class="sxs-lookup"><span data-stu-id="65117-144">meet</span></span>|   <span data-ttu-id="65117-145">3600</span><span class="sxs-lookup"><span data-stu-id="65117-145">3600</span></span>|   <span data-ttu-id="65117-146">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="65117-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="65117-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="65117-147">CNAME</span></span>| <span data-ttu-id="65117-148">dialin</span><span class="sxs-lookup"><span data-stu-id="65117-148">dialin</span></span>  |<span data-ttu-id="65117-149">3600</span><span class="sxs-lookup"><span data-stu-id="65117-149">3600</span></span>|  <span data-ttu-id="65117-150">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="65117-150">webdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="65117-151">또한 meet 또는 dialin(있는 경우)에 대한 CNAME 레코드를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-151">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="65117-152">마지막으로 내부 네트워크에서 비즈니스용 Skype에 대한 DNS 레코드를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-152">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="65117-153">드물지만 DNS를 조직에 대한 Office 365를 설정하는 데 DNS를 변경하면 다른 조직이 페더링 구성을 업데이트할 때까지 일부 다른 조직과의 페더링이 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-153">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="65117-154">이전 Direct Federation 모델(허용 파트너 서버라고도 알려지음)을 사용하는 페더타 조직은 해당 조직에 대해 허용되는 도메인 항목을 업데이트하여 프록시 FQDN을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-154">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="65117-155">이 레거시 페더ation 모델은 DNS SRV 레코드를 기반으로 하지 않습니다. 따라서 조직이 클라우드로 이동하면 이러한 구성이 최신이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65117-155">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="65117-156">sipfed.online.lync에 <span> 대해 호스팅 공급자를 사용하도록 설정하지 않은 페더링된 조직 com에서 구성을 업데이트하여 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-156">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="65117-157">이 상황은 페더러이트 조직이 전적으로 하이브리드 또는 온라인 테넌트와 페더러이트된 적이 없는 경우만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-157">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="65117-158">이러한 경우 호스팅 공급자를 사용하도록 설정해야 이러한 조직과의 페더링이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-158">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="65117-159">페더러이트 파트너 중 어느 한 명도 직접 페더ation을 사용 중일 수 있는 것으로 의심되거나 온라인 또는 하이브리드 조직과 페더전되지 않은 것으로 의심되는 경우 클라우드로의 마이그레이션을 완료할 준비를 할 때 이에 대한 커뮤니케이션을 해당 파트너에게 보낼 것을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-159">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="65117-160">*Microsoft 365 또는 Office 365 조직에서 공유 SIP 주소 공간을 사용하지 않도록 설정*</span><span class="sxs-lookup"><span data-stu-id="65117-160">*Disable shared SIP address space in Microsoft 365 or Office 365 organization.*</span></span>
<span data-ttu-id="65117-161">아래 명령은 비즈니스용 Skype Online PowerShell 창에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-161">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="65117-162">*Microsoft 365 또는 Office 365와 통신하는 데 사용할 수 있는 기능을 On-프레미스에서 사용하지 않도록 설정*</span><span class="sxs-lookup"><span data-stu-id="65117-162">*Disable ability in on-premises to communicate with Microsoft 365 or Office 365.*</span></span>  
<span data-ttu-id="65117-163">아래 명령은 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-163">The command below needs to be done from an on-premises PowerShell window:</span></span>

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="65117-164">On-premises에서 마이그레이션된 사용자의 sip 주소 및 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="65117-164">Manage sip addresses and phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="65117-165">관리자는 이전의 비즈니스용 Skype 서버에서 클라우드로 이동한 사용자를 관리할 수 있습니다. 이 경우, 이 경우, 해당 사용자는 프레미스 배포가 해제된 후에도 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-165">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="65117-166">사용자의 SIP 주소 또는 사용자의 줄 URI를 변경하려는 경우(그리고 SIP 주소 또는 줄 URI가 이미 On-프레미스 Active Directory에 정의되어 있는 경우) 이 작업을 통해 값이 Azure AD로 흐르게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-166">If you want to make changes to a user’s SIP address or to a user’s Line URI (and the SIP address or Line URI is already defined in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="65117-167">이 서버에는 비즈니스용 Skype 서버가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-167">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="65117-168">대신 Active Directory 사용자 및 컴퓨터 MMC 스냅인을 사용하거나 PowerShell을 사용하여 이러한 특성을 직접 On-프레미스 Active Directory에서 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-168">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="65117-169">MMC 스냅인을 사용하는 경우 사용자의 속성 페이지를 열고 특성 편집기 탭을 클릭한 다음 수정할 적절한 특성을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-169">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="65117-170">사용자의 SIP 주소를 수정하려면 `msRTCSIP-PrimaryUserAddress` .</span><span class="sxs-lookup"><span data-stu-id="65117-170">To modify a user’s SIP address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="65117-171">또한 특성에 SIP 값이 포함되어 있는 경우 해당 SIP 값을 새 값과 일치하게 `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="65117-171">In addition, if the `ProxyAddresses` attribute contains a SIP value, update that SIP value to match the new value of `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="65117-172">SIP 값이 포함되어 있지 않은 경우 비워 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65117-172">If it does not contain a SIP value, you can leave it blank.</span></span>

- <span data-ttu-id="65117-173">사용자의 전화 번호를 수정하려면 값이 이미 `msRTCSIP-Line` *있는 경우 수정합니다.*</span><span class="sxs-lookup"><span data-stu-id="65117-173">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 사용자 및 컴퓨터 도구](../media/disable-hybrid-1.png)
  
<span data-ttu-id="65117-175">사용자가 이동하기 전에 원래의 값이 없는 경우 비즈니스용 Skype Online PowerShell 모듈의 `LineURI` `onpremLineUri` [Set-CsUser cmdlet에서](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) - 매개 변수를 사용하여 LineURI를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65117-175">If the user did not originally have a value for `LineURI` on-premises before the move, you can modify the LineURI using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>


## <a name="see-also"></a><span data-ttu-id="65117-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65117-176">See also</span></span>

[<span data-ttu-id="65117-177">Teams 및 비즈니스용 Skype를 위한 클라우드 통합</span><span class="sxs-lookup"><span data-stu-id="65117-177">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
