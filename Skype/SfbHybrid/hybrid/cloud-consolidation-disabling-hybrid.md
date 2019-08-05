---
title: 클라우드로 마이그레이션을 완료 하기 위해 하이브리드을 사용 하지 않도록 설정
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 부록에는 비즈니스용 Skype를 위한 클라우드 통합의 일부로 하이브리드을 사용 하지 않도록 설정 하는 단계에 대 한 자세한 단계가 포함 되어 있습니다.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185505"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="ebdfd-103">클라우드로 마이그레이션을 완료 하기 위해 하이브리드을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="ebdfd-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="ebdfd-104">모든 사용자를 온-프레미스에서 클라우드로 이동한 후에는 온-프레미스 Skype 비즈니스 배포를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="ebdfd-105">하드웨어를 제거 하는 것 외에도, 하이브리드을 사용 하지 않도록 설정 하 여 Office 365에서 온-프레미스 배포를 논리적으로 구분 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="ebdfd-106">하이브리드을 사용 하지 않도록 설정 하는 단계는 3 단계로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="ebdfd-107">Office 365를 가리키도록 DNS 레코드를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="ebdfd-108">Office 365 테 넌 트에서 도메인 분할을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="ebdfd-109">Office 365와 통신 하기 위해 프레미스의 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="ebdfd-110">이러한 단계는 하나의 단위로 함께 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="ebdfd-111">세부 정보는 아래에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="ebdfd-112">드문 경우이 든 조직에서 DNS를 가리키는 Office 365를 사용 하 여 다른 조직이 페더레이션 구성을 업데이트할 때까지 다른 조직과 페더레이션 하는 것을 중지 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="ebdfd-113">이전 직접 페더레이션 모델 (허용 된 파트너 서버 라고도 함)을 사용 하는 모든 페더레이션 조직에서는 해당 조직에 대해 허용 된 도메인 항목을 업데이트 하 여 프록시 FQDN을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="ebdfd-114">이 레거시 페더레이션 모델은 DNS SRV 레코드를 기반으로 하지 않으므로 이러한 구성은 조직이 클라우드로 이동 하 고 나면 오래 된 것이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="ebdfd-115">Sipfed에 대해 사용 하도록 설정 된 호스팅 공급자가 없는 모든 페더레이션 조직입니다. <span>이 기능을 사용 하도록 설정 하려면 com에서 구성을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="ebdfd-116">이 상황은 페더레이션 조직이 전적으로 구내이 고 하이브리드 또는 온라인 테 넌 트와 페더레이션 되지 않은 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="ebdfd-117">이러한 경우 이러한 조직과의 페더레이션이 호스팅 공급자를 사용 하도록 설정 해야 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="ebdfd-118">페더레이션 파트너가 직접 페더레이션 또는 온라인 또는 하이브리드 조직과 페더레이션 할 수 있다고 의심 되는 경우 클라우드로의 마이그레이션을 완료 하기 위해 해당 사용자에 게이에 대 한 통신을 보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="ebdfd-119">*Office 365를 가리키도록 DNS를 업데이트 합니다.*</span><span class="sxs-lookup"><span data-stu-id="ebdfd-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="ebdfd-120">온-프레미스 조직에 대 한 조직의 외부 DNS는 온-프레미스 배포 대신 Office 365를 가리키도록 비즈니스용 Skype 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="ebdfd-121">개발</span><span class="sxs-lookup"><span data-stu-id="ebdfd-121">Specifically:</span></span>

    |<span data-ttu-id="ebdfd-122">레코드 종류</span><span class="sxs-lookup"><span data-stu-id="ebdfd-122">Record type</span></span>|<span data-ttu-id="ebdfd-123">이름</span><span class="sxs-lookup"><span data-stu-id="ebdfd-123">Name</span></span>|<span data-ttu-id="ebdfd-124">TTL</span><span class="sxs-lookup"><span data-stu-id="ebdfd-124">TTL</span></span>|<span data-ttu-id="ebdfd-125">값</span><span class="sxs-lookup"><span data-stu-id="ebdfd-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="ebdfd-126">SRV</span><span class="sxs-lookup"><span data-stu-id="ebdfd-126">SRV</span></span>|<span data-ttu-id="ebdfd-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="ebdfd-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="ebdfd-128">3600</span><span class="sxs-lookup"><span data-stu-id="ebdfd-128">3600</span></span>|<span data-ttu-id="ebdfd-129">100 1 5061 sipfed. 온라인. i a a. <span>com</span><span class="sxs-lookup"><span data-stu-id="ebdfd-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ebdfd-130">SRV</span><span class="sxs-lookup"><span data-stu-id="ebdfd-130">SRV</span></span>|<span data-ttu-id="ebdfd-131">_ sip. tls</span><span class="sxs-lookup"><span data-stu-id="ebdfd-131">_sip._tls</span></span>|<span data-ttu-id="ebdfd-132">3600</span><span class="sxs-lookup"><span data-stu-id="ebdfd-132">3600</span></span>|<span data-ttu-id="ebdfd-133">100 1 443 sipdir. 온라인. i a a. <span>com</span><span class="sxs-lookup"><span data-stu-id="ebdfd-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ebdfd-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="ebdfd-134">CNAME</span></span>| <span data-ttu-id="ebdfd-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ebdfd-135">lyncdiscover</span></span>|   <span data-ttu-id="ebdfd-136">3600</span><span class="sxs-lookup"><span data-stu-id="ebdfd-136">3600</span></span>|   <span data-ttu-id="ebdfd-137">webdir. 온라인. i a lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ebdfd-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ebdfd-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="ebdfd-138">CNAME</span></span>| <span data-ttu-id="ebdfd-139">sip</span><span class="sxs-lookup"><span data-stu-id="ebdfd-139">sip</span></span>|    <span data-ttu-id="ebdfd-140">3600</span><span class="sxs-lookup"><span data-stu-id="ebdfd-140">3600</span></span>|   <span data-ttu-id="ebdfd-141">sipdir. 온라인. i a a. <span>com</span><span class="sxs-lookup"><span data-stu-id="ebdfd-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ebdfd-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="ebdfd-142">CNAME</span></span>| <span data-ttu-id="ebdfd-143">시켜</span><span class="sxs-lookup"><span data-stu-id="ebdfd-143">meet</span></span>|   <span data-ttu-id="ebdfd-144">3600</span><span class="sxs-lookup"><span data-stu-id="ebdfd-144">3600</span></span>|   <span data-ttu-id="ebdfd-145">webdir. 온라인. i a lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ebdfd-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ebdfd-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="ebdfd-146">CNAME</span></span>| <span data-ttu-id="ebdfd-147">전화 접속</span><span class="sxs-lookup"><span data-stu-id="ebdfd-147">dialin</span></span>  |<span data-ttu-id="ebdfd-148">3600</span><span class="sxs-lookup"><span data-stu-id="ebdfd-148">3600</span></span>|  <span data-ttu-id="ebdfd-149">webdir. 온라인. i a lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ebdfd-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="ebdfd-150">*Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하지 않도록 설정 합니다.*</span><span class="sxs-lookup"><span data-stu-id="ebdfd-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="ebdfd-151">아래 명령은 비즈니스용 Skype Online PowerShell 창에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="ebdfd-152">*Office 365와 통신 하기 위해 프레미스의 기능을 사용 하지 않도록 설정 합니다.*</span><span class="sxs-lookup"><span data-stu-id="ebdfd-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="ebdfd-153">아래 명령은 온-프레미스 PowerShell 창에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="ebdfd-154">이전에 비즈니스용 Skype Online 세션을 가져온 적이 있는 경우 새 비즈니스용 Skype PowerShell 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdfd-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="ebdfd-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebdfd-155">See also</span></span>

[<span data-ttu-id="ebdfd-156">팀 및 비즈니스용 Skype에 대 한 클라우드 통합</span><span class="sxs-lookup"><span data-stu-id="ebdfd-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)