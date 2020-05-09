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
ms.openlocfilehash: c6d042095298f6cab8d9474a521b9362ece13e0d
ms.sourcegitcommit: 0dda90122769385529f78f70b0467848da97e5ec
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173974"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="24acb-103">클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화</span><span class="sxs-lookup"><span data-stu-id="24acb-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="24acb-104">모든 사용자를 온-프레미스에서 클라우드로 이동한 후에는 온-프레미스 비즈니스용 Skype 배포를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="24acb-105">하드웨어를 제거하는 것 외에 중요한 단계는 하이브리드를 비활성화하여 Office 365에서 온-프레미스 배포를 논리적으로 분리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="24acb-106">하이브리드를 사용 하지 않도록 설정 하는 단계는 3 단계로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-106">Disabling hybrid consists of 3 steps:</span></span>

- <span data-ttu-id="24acb-107">Office 365를 가리키도록 DNS 레코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-107">Update DNS records to point to Office 365.</span></span>
- <span data-ttu-id="24acb-108">Office 365 조 직에서 도메인 분할을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-108">Disable split domain in the Office 365 organization.</span></span>
- <span data-ttu-id="24acb-109">온-프레미스에서 Office 365와 통신 하는 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="24acb-110">이러한 단계는 하나의 단위로 함께 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="24acb-111">세부 정보는 아래에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-111">Details are provided below.</span></span> <span data-ttu-id="24acb-112">또한 온-프레미스 배포의 연결이 끊어지면 마이그레이션된 사용자의 전화 번호를 관리 하기 위한 지침이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Important] 
><span data-ttu-id="24acb-113">Azure AD를 통해 Active Directory sync의 Msrtcsip-gateways 특성을 Azure AD에 연결 하는 작업을 계속 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-113">You should continue to let the msRTCSIP attributes in Active Directory sync via Azure AD Connect into Azure AD.</span></span>  <span data-ttu-id="24acb-114">이 기능을 지원 하지 않으면 이러한 특성을 지우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-114">Do not clear any of these attributes unless directed to by Support.</span></span>  <span data-ttu-id="24acb-115">온-프레미스 환경에서 사용 안 함-CsUser를 실행 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="24acb-115">Do not run Disable-CsUser in the on-premises environment.</span></span> <span data-ttu-id="24acb-116">사용자의 SIP 주소를 수정 해야 하는 경우 온-프레미스 Active Directory에서이 작업을 수행 하 고 아래 설명 된 대로 Azure ad를 통해 Azure AD를 통해이 변경 내용을 동기화 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-116">If you need to modify a user’s SIP address, do this in your on-premises Active Directory and let this change sync into Azure AD via Azure AD Connect as described below.</span></span> <span data-ttu-id="24acb-117">마찬가지로 전화 번호를 변경 해야 하는 경우 사용자의 LineURI가 이미 온-프레미스에 정의 되어 있는 경우 온-프레미스 Active Directory에서이를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-117">Similarly, if you need to change a telephone number and the user’s LineURI is already defined on-premises, you should modify this in the on-premises Active Directory.</span></span>
><span data-ttu-id="24acb-118">온-프레미스에서 마이그레이션한 후 온-프레미스 Msrtcsip-gateways 특성을 지우면 사용자에 대 한 서비스가 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-118">Clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span>



1.  <span data-ttu-id="24acb-119">*Office 365를 가리키도록 DNS를 업데이트 합니다.*</span><span class="sxs-lookup"><span data-stu-id="24acb-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="24acb-120">비즈니스용 Skype 레코드가 온-프레미스 배포 대신 Office 365를 가리키도록 온-프레미스 조직에 대 한 조직의 기존 외부 DNS 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-120">The organization’s existing external DNS records for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="24acb-121">특히 다음 사항에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-121">Specifically:</span></span>

    |<span data-ttu-id="24acb-122">레코드 유형</span><span class="sxs-lookup"><span data-stu-id="24acb-122">Record type</span></span>|<span data-ttu-id="24acb-123">이름</span><span class="sxs-lookup"><span data-stu-id="24acb-123">Name</span></span>|<span data-ttu-id="24acb-124">TTL</span><span class="sxs-lookup"><span data-stu-id="24acb-124">TTL</span></span>|<span data-ttu-id="24acb-125">값</span><span class="sxs-lookup"><span data-stu-id="24acb-125">Value</span></span>|<span data-ttu-id="24acb-126">용도</span><span class="sxs-lookup"><span data-stu-id="24acb-126">Purpose</span></span>|
    |---|---|---|---|---|
    |<span data-ttu-id="24acb-127">SRV</span><span class="sxs-lookup"><span data-stu-id="24acb-127">SRV</span></span>|<span data-ttu-id="24acb-128">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="24acb-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="24acb-129">3600</span><span class="sxs-lookup"><span data-stu-id="24acb-129">3600</span></span>|<span data-ttu-id="24acb-130">100 1 5061 sipfed.online.lync.com>. <span>com</span><span class="sxs-lookup"><span data-stu-id="24acb-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|<span data-ttu-id="24acb-131">페더레이션을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="24acb-131">Enables federation</span></span>|
    |<span data-ttu-id="24acb-132">SRV</span><span class="sxs-lookup"><span data-stu-id="24acb-132">SRV</span></span>|<span data-ttu-id="24acb-133">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="24acb-133">_sip._tls</span></span>|<span data-ttu-id="24acb-134">3600</span><span class="sxs-lookup"><span data-stu-id="24acb-134">3600</span></span>|<span data-ttu-id="24acb-135">100 1 443 sipdir.online.lync.com>. <span>com</span><span class="sxs-lookup"><span data-stu-id="24acb-135">100 1 443 sipdir.online.lync.<span>com</span></span>|<span data-ttu-id="24acb-136">비즈니스용 Skype 사용자에 게 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-136">Required for Skype for Business users</span></span>|
    |<span data-ttu-id="24acb-137">CNAME</span><span class="sxs-lookup"><span data-stu-id="24acb-137">CNAME</span></span>| <span data-ttu-id="24acb-138">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="24acb-138">lyncdiscover</span></span>|   <span data-ttu-id="24acb-139">3600</span><span class="sxs-lookup"><span data-stu-id="24acb-139">3600</span></span>|   <span data-ttu-id="24acb-140">webdir. s e t. <span>com</span><span class="sxs-lookup"><span data-stu-id="24acb-140">webdir.online.lync.<span>com</span></span>|<span data-ttu-id="24acb-141">비즈니스용 Skype 사용자에 게 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-141">Required for Skype for Business users</span></span>|
    |<span data-ttu-id="24acb-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="24acb-142">CNAME</span></span>| <span data-ttu-id="24acb-143">sip</span><span class="sxs-lookup"><span data-stu-id="24acb-143">sip</span></span>|    <span data-ttu-id="24acb-144">3600</span><span class="sxs-lookup"><span data-stu-id="24acb-144">3600</span></span>|   <span data-ttu-id="24acb-145">sipdir.online.lync.com>. <span>com</span><span class="sxs-lookup"><span data-stu-id="24acb-145">sipdir.online.lync.<span>com</span></span>|<span data-ttu-id="24acb-146">이전 레거시 SIP 전화에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-146">Required only for older legacy SIP phones</span></span>|

    <span data-ttu-id="24acb-147">또한 모임 또는 전화 걸기 (있는 경우)에 대 한 CNAME 레코드를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-147">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span>

    > [!Note] 
    > <span data-ttu-id="24acb-148">드문 경우에는 조직에 대해 온-프레미스에서 Office 365로 DNS를 변경 하면 다른 조직이 페더레이션 구성을 업데이트할 때까지 다른 조직과의 페더레이션이 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-148">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="24acb-149">이전 직접 페더레이션 모델 (허용 된 파트너 서버 라고도 함)을 사용 하는 모든 페더레이션 조직에서는 프록시 FQDN을 제거 하기 위해 조직에 대해 허용 되는 도메인 항목을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-149">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="24acb-150">이 레거시 페더레이션 모델은 DNS SRV 레코드를 기반으로 하지 않으므로 이러한 구성은 조직이 클라우드로 이동한 후에 최신 상태가 되지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-150">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="24acb-151">Sipfed.online.lync.com>에 대해 호스팅 공급자가 사용 하도록 설정 되지 않은 페더레이션 조직입니다. <span>com은 해당 구성을 사용 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-151">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="24acb-152">이 상황은 페더레이션 조직이 전적으로 온-프레미스이 고 하이브리드 또는 온라인 테 넌 트와도 페더레이션 되지 않은 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-152">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="24acb-153">이러한 경우 이러한 조직과의 페더레이션은 호스팅 공급자를 사용 하도록 설정할 때까지 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-153">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="24acb-154">페더레이션 파트너가 직접 페더레이션을 사용 하 고 있거나 온라인 또는 하이브리드 조직과 페더레이션 되지 않은 것으로 의심 되는 경우 클라우드로의 마이그레이션을 완료 하기 위해 준비 하는 것과 관련 하 여이에 대 한 정보를 보내 드릴 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-154">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

2.  <span data-ttu-id="24acb-155">*Office 365 조 직에서 공유 SIP 주소 공간을 사용 하지 않도록 설정 합니다.*</span><span class="sxs-lookup"><span data-stu-id="24acb-155">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="24acb-156">아래 명령은 비즈니스용 Skype Online PowerShell 창에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-156">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="24acb-157">*온-프레미스에서 Office 365와 통신 하는 기능을 사용 하지 않도록 설정 합니다.*</span><span class="sxs-lookup"><span data-stu-id="24acb-157">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="24acb-158">아래 명령은 온-프레미스 PowerShell 창에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-158">The command below needs to be done from an on-premises PowerShell window:</span></span>

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="24acb-159">온-프레미스에서 마이그레이션된 사용자에 대 한 sip 주소 및 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="24acb-159">Manage sip addresses and phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="24acb-160">관리자는 온-프레미스 배포를 해제 한 후에도 이전에 비즈니스용 Skype 서버에서 클라우드로 이동한 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-160">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="24acb-161">사용자의 SIP 주소 또는 사용자의 회선 URI를 변경 하거나, SIP 주소 또는 줄 URI가 온-프레미스 Active Directory에 이미 정의 되어 있는 경우 온-프레미스 Active Directory에서이 작업을 수행 하 고 값이 Azure AD로 흐르도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-161">If you want to make changes to a user’s SIP address or to a user’s Line URI (and the SIP address or Line URI is already defined in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="24acb-162">여기에는 온-프레미스 비즈니스용 Skype 서버가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="24acb-163">대신, Active Directory 사용자 및 컴퓨터 MMC 스냅인을 사용 하거나 PowerShell을 사용 하 여 온-프레미스 Active Directory에서 직접 이러한 특성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-163">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="24acb-164">MMC 스냅인을 사용 하는 경우 사용자의 속성 페이지를 열고 특성 편집기 탭을 클릭 한 다음 수정할 적절 한 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-164">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="24acb-165">사용자의 SIP 주소를 수정 하려면를 `msRTCSIP-PrimaryUserAddress`수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-165">To modify a user’s SIP address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="24acb-166">또한 특성에 `ProxyAddresses` sip 값이 포함 되어 있으면의 `msRTCSIP-PrimaryUserAddress`새 값과 일치 하도록 sip 값을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-166">In addition, if the `ProxyAddresses` attribute contains a SIP value, update that SIP value to match the new value of `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="24acb-167">SIP 값이 포함 되어 있지 않은 경우에는 비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-167">If it does not contain a SIP value, you can leave it blank.</span></span>

- <span data-ttu-id="24acb-168">사용자의 전화 번호를 수정 하려면 `msRTCSIP-Line` *이미 값이 있는 경우*수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-168">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 사용자 및 컴퓨터 도구](../media/disable-hybrid-1.png)
  
<span data-ttu-id="24acb-170">이전에 사용자가 이동 하기 전에 온-프레미스 `LineURI` 에 대 한 값을 갖고 있지 않은 경우 비즈니스용 Skype Online PowerShell 모듈에서-`onpremLineUri` [csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 의-Parameter를 사용 하 여 lineuri를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24acb-170">If the user did not originally have a value for `LineURI` on-premises before the move, you can modify the LineURI using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>


## <a name="see-also"></a><span data-ttu-id="24acb-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24acb-171">See also</span></span>

[<span data-ttu-id="24acb-172">팀 및 비즈니스용 Skype에 대 한 클라우드 통합</span><span class="sxs-lookup"><span data-stu-id="24acb-172">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
