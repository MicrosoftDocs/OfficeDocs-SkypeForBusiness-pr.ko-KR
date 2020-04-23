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
ms.openlocfilehash: 053d632b5a07b7ce7cca8ef7a1ddf45a673bcf59
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780147"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="577c0-103">클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화</span><span class="sxs-lookup"><span data-stu-id="577c0-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="577c0-104">모든 사용자를 온-프레미스에서 클라우드로 이동한 후에는 온-프레미스 비즈니스용 Skype 배포를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="577c0-105">하드웨어를 제거하는 것 외에 중요한 단계는 하이브리드를 비활성화하여 Office 365에서 온-프레미스 배포를 논리적으로 분리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="577c0-106">하이브리드를 사용 하지 않도록 설정 하는 단계는 3 단계로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="577c0-107">Office 365를 가리키도록 DNS 레코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="577c0-108">Office 365 조 직에서 도메인 분할을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-108">Disable split domain in the Office 365 organization.</span></span>

3. <span data-ttu-id="577c0-109">온-프레미스에서 Office 365와 통신 하는 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="577c0-110">이러한 단계는 하나의 단위로 함께 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="577c0-111">세부 정보는 아래에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-111">Details are provided below.</span></span> <span data-ttu-id="577c0-112">또한 온-프레미스 배포의 연결이 끊어지면 마이그레이션된 사용자의 전화 번호를 관리 하기 위한 지침이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="577c0-113">드문 경우에는 조직에 대해 온-프레미스에서 Office 365로 DNS를 변경 하면 다른 조직이 페더레이션 구성을 업데이트할 때까지 다른 조직과의 페더레이션이 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="577c0-114">이전 직접 페더레이션 모델 (허용 된 파트너 서버 라고도 함)을 사용 하는 모든 페더레이션 조직에서는 프록시 FQDN을 제거 하기 위해 조직에 대해 허용 되는 도메인 항목을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="577c0-115">이 레거시 페더레이션 모델은 DNS SRV 레코드를 기반으로 하지 않으므로 이러한 구성은 조직이 클라우드로 이동한 후에 최신 상태가 되지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="577c0-116">Sipfed.online.lync.com>에 대해 호스팅 공급자가 사용 하도록 설정 되지 않은 페더레이션 조직입니다. <span>com은 해당 구성을 사용 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="577c0-117">이 상황은 페더레이션 조직이 전적으로 온 적이 있고 하이브리드 또는 온라인 테 넌 트와도 페더레이션 되지 않은 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="577c0-118">이러한 경우 이러한 조직과의 페더레이션은 호스팅 공급자를 사용 하도록 설정할 때까지 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="577c0-119">페더레이션 파트너가 직접 페더레이션을 사용 하거나 온라인 또는 하이브리드 조직과 페더레이션 되어 있다고 생각 되는 경우 클라우드로의 마이그레이션을 완료 하기 위해 준비할 때 이러한 정보를이에 대 한 통신으로 보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="577c0-120">*Office 365를 가리키도록 DNS를 업데이트 합니다.*</span><span class="sxs-lookup"><span data-stu-id="577c0-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="577c0-121">비즈니스용 Skype 레코드가 온-프레미스 배포 대신 Office 365를 가리키도록 온-프레미스 조직에 대 한 조직의 외부 DNS를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="577c0-122">특히 다음 사항에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-122">Specifically:</span></span>

    |<span data-ttu-id="577c0-123">레코드 유형</span><span class="sxs-lookup"><span data-stu-id="577c0-123">Record type</span></span>|<span data-ttu-id="577c0-124">이름</span><span class="sxs-lookup"><span data-stu-id="577c0-124">Name</span></span>|<span data-ttu-id="577c0-125">TTL</span><span class="sxs-lookup"><span data-stu-id="577c0-125">TTL</span></span>|<span data-ttu-id="577c0-126">값</span><span class="sxs-lookup"><span data-stu-id="577c0-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="577c0-127">SRV</span><span class="sxs-lookup"><span data-stu-id="577c0-127">SRV</span></span>|<span data-ttu-id="577c0-128">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="577c0-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="577c0-129">3600</span><span class="sxs-lookup"><span data-stu-id="577c0-129">3600</span></span>|<span data-ttu-id="577c0-130">100 1 5061 sipfed.online.lync.com>. <span>com</span><span class="sxs-lookup"><span data-stu-id="577c0-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="577c0-131">SRV</span><span class="sxs-lookup"><span data-stu-id="577c0-131">SRV</span></span>|<span data-ttu-id="577c0-132">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="577c0-132">_sip._tls</span></span>|<span data-ttu-id="577c0-133">3600</span><span class="sxs-lookup"><span data-stu-id="577c0-133">3600</span></span>|<span data-ttu-id="577c0-134">100 1 443 sipdir.online.lync.com>. <span>com</span><span class="sxs-lookup"><span data-stu-id="577c0-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="577c0-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="577c0-135">CNAME</span></span>| <span data-ttu-id="577c0-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="577c0-136">lyncdiscover</span></span>|   <span data-ttu-id="577c0-137">3600</span><span class="sxs-lookup"><span data-stu-id="577c0-137">3600</span></span>|   <span data-ttu-id="577c0-138">webdir. s e t. <span>com</span><span class="sxs-lookup"><span data-stu-id="577c0-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="577c0-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="577c0-139">CNAME</span></span>| <span data-ttu-id="577c0-140">sip</span><span class="sxs-lookup"><span data-stu-id="577c0-140">sip</span></span>|    <span data-ttu-id="577c0-141">3600</span><span class="sxs-lookup"><span data-stu-id="577c0-141">3600</span></span>|   <span data-ttu-id="577c0-142">sipdir.online.lync.com>. <span>com</span><span class="sxs-lookup"><span data-stu-id="577c0-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="577c0-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="577c0-143">CNAME</span></span>| <span data-ttu-id="577c0-144">조건</span><span class="sxs-lookup"><span data-stu-id="577c0-144">meet</span></span>|   <span data-ttu-id="577c0-145">3600</span><span class="sxs-lookup"><span data-stu-id="577c0-145">3600</span></span>|   <span data-ttu-id="577c0-146">webdir. s e t. <span>com</span><span class="sxs-lookup"><span data-stu-id="577c0-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="577c0-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="577c0-147">CNAME</span></span>| <span data-ttu-id="577c0-148">dialin</span><span class="sxs-lookup"><span data-stu-id="577c0-148">dialin</span></span>  |<span data-ttu-id="577c0-149">3600</span><span class="sxs-lookup"><span data-stu-id="577c0-149">3600</span></span>|  <span data-ttu-id="577c0-150">webdir. s e t. <span>com</span><span class="sxs-lookup"><span data-stu-id="577c0-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="577c0-151">*Office 365 조 직에서 공유 SIP 주소 공간을 사용 하지 않도록 설정 합니다.*</span><span class="sxs-lookup"><span data-stu-id="577c0-151">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="577c0-152">아래 명령은 비즈니스용 Skype Online PowerShell 창에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="577c0-153">*온-프레미스에서 Office 365와 통신 하는 기능을 사용 하지 않도록 설정 합니다.*</span><span class="sxs-lookup"><span data-stu-id="577c0-153">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="577c0-154">아래 명령은 온-프레미스 PowerShell 창에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-154">The command below needs to be done from an on-premises PowerShell window:</span></span>
```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="577c0-155">온-프레미스에서 마이그레이션된 사용자에 대 한 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="577c0-155">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="577c0-156">관리자는 온-프레미스 배포를 해제 한 후에도 이전에 비즈니스용 Skype 서버에서 클라우드로 이동한 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-156">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="577c0-157">다음과 같은 두 가지 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-157">There are two different possibilities:</span></span>

- <span data-ttu-id="577c0-158">사용자에 게 이동 하기 전에 LineURI 온-프레미스에 대 한 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-158">The user did not have a value for LineURI on-premises before the move.</span></span> 

  <span data-ttu-id="577c0-159">이 경우 비즈니스용 Skype Online PowerShell 모듈의 [CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 에서-onpremLineUri 매개 변수를 사용 하 여 lineuri를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-159">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

- <span data-ttu-id="577c0-160">사용자에 게 이동 하기 전에 LineURI 온-프레미스가 있었습니다 (사용자가 Enterprise Voice를 사용할 수 있도록 설정 된 경우).</span><span class="sxs-lookup"><span data-stu-id="577c0-160">The user had a LineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="577c0-161">LineURI를 변경 하려면 온-프레미스 Active Directory에서이 작업을 수행 하 고 값이 Azure AD로 흐를 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-161">If you want to change the LineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="577c0-162">여기에는 온-프레미스 비즈니스용 Skype 서버가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="577c0-163">대신,이 특성은 온-프레미스 Active Directory에서 직접 편집할 수 있으며, Active Directory 사용자 및 컴퓨터 MMC 스냅인을 사용 하거나 PowerShell을 사용 하 여 Msrtcsip-gateways.</span><span class="sxs-lookup"><span data-stu-id="577c0-163">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="577c0-164">MMC 스냅인을 사용 하는 경우 사용자의 속성 페이지를 열고 특성 편집기 탭을 클릭 한 다음 Msrtcsip-gateways을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="577c0-164">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Active Directory 사용자 및 컴퓨터 도구](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="577c0-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="577c0-166">See also</span></span>

[<span data-ttu-id="577c0-167">팀 및 비즈니스용 Skype에 대 한 클라우드 통합</span><span class="sxs-lookup"><span data-stu-id="577c0-167">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
