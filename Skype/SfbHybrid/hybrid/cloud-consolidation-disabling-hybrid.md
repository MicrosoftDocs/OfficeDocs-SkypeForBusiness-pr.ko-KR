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
description: 이 부록에는 팀 및 비즈니스용 Skype에 대 한 클라우드 통합의 일부로 서 하이브리드를 사용 하지 않도록 설정 하는 자세한 단계가 포함 되어 있습니다.
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277252"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="268a5-103">클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화</span><span class="sxs-lookup"><span data-stu-id="268a5-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="268a5-104">모든 사용자를 온-프레미스에서 클라우드로 이동한 후에는 온-프레미스 비즈니스용 Skype 배포를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="268a5-105">하드웨어를 제거 하는 것 외에도, 하이브리드를 사용 하지 않도록 설정 하 여 온-프레미스 배포를 Microsoft 365 또는 Office 365에서 논리적으로 구분 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Microsoft 365 or Office 365 by disabling hybrid.</span></span> <span data-ttu-id="268a5-106">하이브리드를 사용 하지 않도록 설정 하는 단계는 3 단계로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="268a5-107">Microsoft 365 또는 Office 365를 가리키도록 DNS 레코드를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-107">Update DNS records to point to Microsoft 365 or Office 365.</span></span>

2. <span data-ttu-id="268a5-108">Microsoft 365 또는 Office 365 조 직에서 도메인 분할을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-108">Disable split domain in the Microsoft 365 or Office 365 organization.</span></span>

3. <span data-ttu-id="268a5-109">온-프레미스에서 Microsoft 365 또는 Office 365와 통신 하는 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-109">Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="268a5-110">이러한 단계는 하나의 단위로 함께 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="268a5-111">세부 정보는 아래에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-111">Details are provided below.</span></span> <span data-ttu-id="268a5-112">또한 온-프레미스 배포의 연결이 끊어지면 마이그레이션된 사용자의 전화 번호를 관리 하기 위한 지침이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

<span data-ttu-id="268a5-113">이러한 단계가 완료 되 면 온-프레미스 비즈니스용 Skype 서버는 더 이상 사용 되지 않으며, 이러한 서버를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-113">Once these steps are complete, the on-premises Skype for Business servers are no longer used, and these servers can be re-imaged.</span></span>

> [!Important] 
><span data-ttu-id="268a5-114">Azure AD를 통해 Active Directory sync의 Msrtcsip-gateways 특성을 Azure AD에 연결 하는 작업을 계속 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-114">You should continue to let the msRTCSIP attributes in Active Directory sync via Azure AD Connect into Azure AD.</span></span>  <span data-ttu-id="268a5-115">이 기능을 지원 하지 않으면 이러한 특성을 지우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-115">Do not clear any of these attributes unless directed to by Support.</span></span>  <span data-ttu-id="268a5-116">온-프레미스 환경에서 사용 안 함-CsUser를 실행 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="268a5-116">Do not run Disable-CsUser in the on-premises environment.</span></span> <span data-ttu-id="268a5-117">사용자의 SIP 주소를 수정 해야 하는 경우 온-프레미스 Active Directory에서이 작업을 수행 하 고 아래 설명 된 대로 Azure ad를 통해 Azure AD를 통해이 변경 내용을 동기화 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-117">If you need to modify a user’s SIP address, do this in your on-premises Active Directory and let this change sync into Azure AD via Azure AD Connect as described below.</span></span> <span data-ttu-id="268a5-118">마찬가지로 전화 번호를 변경 해야 하는 경우 사용자의 LineURI가 이미 온-프레미스에 정의 되어 있는 경우 온-프레미스 Active Directory에서이를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-118">Similarly, if you need to change a telephone number and the user’s LineURI is already defined on-premises, you should modify this in the on-premises Active Directory.</span></span>
><span data-ttu-id="268a5-119">온-프레미스에서 마이그레이션한 후 온-프레미스 Msrtcsip-gateways 특성을 지우면 사용자에 대 한 서비스가 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-119">Clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span>


1.  <span data-ttu-id="268a5-120">*Microsoft 365 또는 Office 365를 가리키도록 DNS를 업데이트 합니다.*</span><span class="sxs-lookup"><span data-stu-id="268a5-120">*Update DNS to point to Microsoft 365 or  Office 365.*</span></span>
<span data-ttu-id="268a5-121">비즈니스용 Skype 레코드가 온-프레미스 배포 대신 Microsoft 365 또는 Office 365를 가리키도록 온-프레미스 조직에 대 한 조직의 외부 DNS를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 or Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="268a5-122">특히 다음 사항에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-122">Specifically:</span></span>

    |<span data-ttu-id="268a5-123">레코드 유형</span><span class="sxs-lookup"><span data-stu-id="268a5-123">Record type</span></span>|<span data-ttu-id="268a5-124">이름</span><span class="sxs-lookup"><span data-stu-id="268a5-124">Name</span></span>|<span data-ttu-id="268a5-125">TTL</span><span class="sxs-lookup"><span data-stu-id="268a5-125">TTL</span></span>|<span data-ttu-id="268a5-126">값</span><span class="sxs-lookup"><span data-stu-id="268a5-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="268a5-127">SRV</span><span class="sxs-lookup"><span data-stu-id="268a5-127">SRV</span></span>|<span data-ttu-id="268a5-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="268a5-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="268a5-129">3600</span><span class="sxs-lookup"><span data-stu-id="268a5-129">3600</span></span>|<span data-ttu-id="268a5-130">100 1 5061 sipfed.online.lync.com> <span> . ccw</span><span class="sxs-lookup"><span data-stu-id="268a5-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="268a5-131">SRV</span><span class="sxs-lookup"><span data-stu-id="268a5-131">SRV</span></span>|<span data-ttu-id="268a5-132">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="268a5-132">_sip._tls</span></span>|<span data-ttu-id="268a5-133">3600</span><span class="sxs-lookup"><span data-stu-id="268a5-133">3600</span></span>|<span data-ttu-id="268a5-134">100 1 443 sipdir.online.lync.com> <span> . ccw</span><span class="sxs-lookup"><span data-stu-id="268a5-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="268a5-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="268a5-135">CNAME</span></span>| <span data-ttu-id="268a5-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="268a5-136">lyncdiscover</span></span>|   <span data-ttu-id="268a5-137">3600</span><span class="sxs-lookup"><span data-stu-id="268a5-137">3600</span></span>|   <span data-ttu-id="268a5-138">webdir. <span> s e t. ccw</span><span class="sxs-lookup"><span data-stu-id="268a5-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="268a5-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="268a5-139">CNAME</span></span>| <span data-ttu-id="268a5-140">sip</span><span class="sxs-lookup"><span data-stu-id="268a5-140">sip</span></span>|    <span data-ttu-id="268a5-141">3600</span><span class="sxs-lookup"><span data-stu-id="268a5-141">3600</span></span>|   <span data-ttu-id="268a5-142"><span>sipdir.online.lync.com>. ccw</span><span class="sxs-lookup"><span data-stu-id="268a5-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="268a5-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="268a5-143">CNAME</span></span>| <span data-ttu-id="268a5-144">조건</span><span class="sxs-lookup"><span data-stu-id="268a5-144">meet</span></span>|   <span data-ttu-id="268a5-145">3600</span><span class="sxs-lookup"><span data-stu-id="268a5-145">3600</span></span>|   <span data-ttu-id="268a5-146">webdir. <span> s e t. ccw</span><span class="sxs-lookup"><span data-stu-id="268a5-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="268a5-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="268a5-147">CNAME</span></span>| <span data-ttu-id="268a5-148">dialin</span><span class="sxs-lookup"><span data-stu-id="268a5-148">dialin</span></span>  |<span data-ttu-id="268a5-149">3600</span><span class="sxs-lookup"><span data-stu-id="268a5-149">3600</span></span>|  <span data-ttu-id="268a5-150">webdir. <span> s e t. ccw</span><span class="sxs-lookup"><span data-stu-id="268a5-150">webdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="268a5-151">또한 모임 또는 전화 걸기 (있는 경우)에 대 한 CNAME 레코드를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-151">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="268a5-152">마지막으로 내부 네트워크에 있는 비즈니스용 Skype에 대 한 모든 DNS 레코드를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-152">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="268a5-153">드문 경우에는 조직에 대해 온-프레미스에서 Office 365로 DNS를 변경 하면 다른 조직이 페더레이션 구성을 업데이트할 때까지 다른 조직과의 페더레이션이 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-153">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="268a5-154">이전 직접 페더레이션 모델 (허용 된 파트너 서버 라고도 함)을 사용 하는 모든 페더레이션 조직에서는 프록시 FQDN을 제거 하기 위해 조직에 대해 허용 되는 도메인 항목을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-154">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="268a5-155">이 레거시 페더레이션 모델은 DNS SRV 레코드를 기반으로 하지 않으므로 이러한 구성은 조직이 클라우드로 이동한 후에 최신 상태가 되지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-155">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="268a5-156">Sipfed.online.lync.com> <span> 에 대해 호스팅 공급자가 사용 하도록 설정 되지 않은 페더레이션 조직입니다. com은 해당 구성을 사용 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-156">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="268a5-157">이 상황은 페더레이션 조직이 전적으로 온-프레미스이 고 하이브리드 또는 온라인 테 넌 트와도 페더레이션 되지 않은 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-157">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="268a5-158">이러한 경우 이러한 조직과의 페더레이션은 호스팅 공급자를 사용 하도록 설정할 때까지 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-158">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="268a5-159">페더레이션 파트너가 직접 페더레이션을 사용 하 고 있거나 온라인 또는 하이브리드 조직과 페더레이션 되지 않은 것으로 의심 되는 경우 클라우드로의 마이그레이션을 완료 하기 위해 준비 하는 것과 관련 하 여이에 대 한 정보를 보내 드릴 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-159">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="268a5-160">*Microsoft 365 또는 Office 365 조 직에서 공유 SIP 주소 공간을 사용 하지 않도록 설정 합니다.*</span><span class="sxs-lookup"><span data-stu-id="268a5-160">*Disable shared SIP address space in Microsoft 365 or Office 365 organization.*</span></span>
<span data-ttu-id="268a5-161">아래 명령은 비즈니스용 Skype Online PowerShell 창에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-161">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="268a5-162">*온-프레미스에서 Microsoft 365 또는 Office 365와 통신 하는 기능을 사용 하지 않도록 설정 합니다.*</span><span class="sxs-lookup"><span data-stu-id="268a5-162">*Disable ability in on-premises to communicate with Microsoft 365 or Office 365.*</span></span>  
<span data-ttu-id="268a5-163">아래 명령은 온-프레미스 PowerShell 창에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-163">The command below needs to be done from an on-premises PowerShell window:</span></span>

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="268a5-164">온-프레미스에서 마이그레이션된 사용자에 대 한 sip 주소 및 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="268a5-164">Manage sip addresses and phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="268a5-165">관리자는 온-프레미스 배포를 해제 한 후에도 이전에 비즈니스용 Skype 서버에서 클라우드로 이동한 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-165">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="268a5-166">사용자의 SIP 주소 또는 사용자의 회선 URI를 변경 하거나, SIP 주소 또는 줄 URI가 온-프레미스 Active Directory에 이미 정의 되어 있는 경우 온-프레미스 Active Directory에서이 작업을 수행 하 고 값이 Azure AD로 흐르도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-166">If you want to make changes to a user’s SIP address or to a user’s Line URI (and the SIP address or Line URI is already defined in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="268a5-167">여기에는 온-프레미스 비즈니스용 Skype 서버가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-167">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="268a5-168">대신, Active Directory 사용자 및 컴퓨터 MMC 스냅인을 사용 하거나 PowerShell을 사용 하 여 온-프레미스 Active Directory에서 직접 이러한 특성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-168">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="268a5-169">MMC 스냅인을 사용 하는 경우 사용자의 속성 페이지를 열고 특성 편집기 탭을 클릭 한 다음 수정할 적절 한 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-169">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="268a5-170">사용자의 SIP 주소를 수정 하려면를 수정 `msRTCSIP-PrimaryUserAddress` 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-170">To modify a user’s SIP address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="268a5-171">또한 `ProxyAddresses` 특성에 sip 값이 포함 되어 있으면의 새 값과 일치 하도록 sip 값을 업데이트 `msRTCSIP-PrimaryUserAddress` 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-171">In addition, if the `ProxyAddresses` attribute contains a SIP value, update that SIP value to match the new value of `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="268a5-172">SIP 값이 포함 되어 있지 않은 경우에는 비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-172">If it does not contain a SIP value, you can leave it blank.</span></span>

- <span data-ttu-id="268a5-173">사용자의 전화 번호를 수정 하려면 `msRTCSIP-Line` *이미 값이 있는 경우*수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-173">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 사용자 및 컴퓨터 도구](../media/disable-hybrid-1.png)
  
<span data-ttu-id="268a5-175">이전에 사용자가 이동 하기 전에 온-프레미스에 대 한 값을 갖고 있지 않은 경우 `LineURI` `onpremLineUri` 비즈니스용 Skype Online PowerShell 모듈에서- [csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 의-parameter를 사용 하 여 lineuri를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="268a5-175">If the user did not originally have a value for `LineURI` on-premises before the move, you can modify the LineURI using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>


## <a name="see-also"></a><span data-ttu-id="268a5-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="268a5-176">See also</span></span>

[<span data-ttu-id="268a5-177">팀 및 비즈니스용 Skype에 대 한 클라우드 통합</span><span class="sxs-lookup"><span data-stu-id="268a5-177">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
