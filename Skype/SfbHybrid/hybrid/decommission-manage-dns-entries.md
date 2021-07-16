---
title: 사내 환경을 해제할 때 DNS 항목 관리
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
description: On-premises 비즈니스용 Skype 해제할 때 DNS 항목을 관리하는 방법에 대한 지침입니다.
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458995"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a><span data-ttu-id="25ade-103">조직이 모든 사용자만 사용할 수 있도록 DNS Teams 업데이트</span><span class="sxs-lookup"><span data-stu-id="25ade-103">Update DNS entries to enable your organization to be all Teams Only</span></span>

<span data-ttu-id="25ade-104">이전에 온-프레미스 비즈니스용 Skype 서버 또는 Lync Server를 배포한 조직에는 온-프레미스 배포를 비즈니스용 Skype DNS 항목이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-104">Organizations that previously had on-premises deployments of Skype for Business Server or Lync Server may still have DNS entries that point to an on-premises Skype for Business deployment.</span></span> <span data-ttu-id="25ade-105">이러한 레코드는 조직에 사용자가 있는 경우 비즈니스용 Skype 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-105">These records are required if your organization includes on-premises Skype for Business users.</span></span> <span data-ttu-id="25ade-106">그러나 조직에 더 이상 온-프레미스 비즈니스용 Skype Lync Server 사용자가 없는 경우 이러한 레코드는 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-106">However, once your organization no longer has any on-premises Skype for Business or Lync Server users, these records are no longer required.</span></span> <span data-ttu-id="25ade-107">또한 실제로, 마이그레이션을 완료하는 일부로, Teams 레코드를 업데이트하여 Microsoft 365 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-107">And in fact, as part of completing the migration from on-premises to Teams, these records must be updated to point to Microsoft 365 or removed.</span></span> <span data-ttu-id="25ade-108">Microsoft는 이 단계를 취할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-108">Microsoft cannot take this step for you.</span></span>

<span data-ttu-id="25ade-109">전체 테넌트에 TeamsOnly를 부여하려고 할 Teams DNS를 확인하여 조직에 대한 이러한 DNS 레코드가 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-109">When attempting to grant TeamsOnly to the entire tenant, Teams will check DNS to determine if any of these DNS records exist for your organization.</span></span> <span data-ttu-id="25ade-110">레코드가 발견되어 레코드가 다른 레코드를 Microsoft 365 경우 테넌트 공존 모드를 TeamsOnly로 변경하려고 하면 디자인에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-110">If any records are found, and if they point to something other than Microsoft 365, the attempt to change the tenant coexistence mode to TeamsOnly will fail by design.</span></span> <span data-ttu-id="25ade-111">이 디자인은 테넌트에 TeamsOnly 모드를 실수로 적용하지 못하게 하는 하이브리드 조직을 방지하기 위한 것입니다. 이렇게 하면 모든 비즈니스용 Skype 사용자(Teams 또는 테넌트 사용 여부에 비즈니스용 Skype)에 대한 페더넌트가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-111">This design is to prevent hybrid organizations with on-premises users from mistakenly applying TeamsOnly mode to the tenant--because doing so would break federation for any on-premises Skype for Business users (whether using Teams or Skype for Business).</span></span>

<span data-ttu-id="25ade-112">또한 전체 테넌트에 TeamsOnly를 부여할 수 있도록 이러한 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-112">Furthermore, these records must be updated so that you can grant TeamsOnly to the entire tenant.</span></span>

> [!Note] 
> <span data-ttu-id="25ade-113">드문 경우지만 DNS를 조직에 대한 Microsoft 365 설정으로 변경하면 다른 조직에서 페더링 구성을 업데이트할 때까지 일부 다른 조직과의 페더링이 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-113">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
>
> - <span data-ttu-id="25ade-114">이전 Direct Federation 모델(허용 파트너 서버라고도 지칭)을 사용하는 페더러된 조직은 조직에 대해 허용되는 도메인 항목을 업데이트하여 프록시 FQDN을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="25ade-115">이 레거시 페더전 모델은 DNS SRV 레코드를 기반으로 하지 않습니다. 따라서 조직이 클라우드로 이동하면 이러한 구성이 최신이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
> 
> - <span data-ttu-id="25ade-116">sipfed.online.lync에 대해 호스팅 공급자를 사용하도록 설정하지 않은 페더링된 조직입니다. <span> com은 구성을 업데이트하여 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="25ade-117">이 상황은 페더러드 조직이 전적으로 사내에 있으며 하이브리드 또는 온라인 테넌트와 페더러이트한 적이 없는 경우만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-117">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="25ade-118">이 경우 호스팅 공급자를 사용하도록 설정해야 이러한 조직과의 페더링이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
>
> <span data-ttu-id="25ade-119">페더더러 파트너 중 한 자가 직접 페더ation을 사용 중일 수 있는 것으로 의심되거나 온라인 또는 하이브리드 조직과 페더러이트되지 않은 것으로 의심되는 경우 클라우드로의 마이그레이션을 완료할 준비를 할 때 이에 대한 통신을 해당 파트너에게 보내는 것이 좋은 제안입니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-119">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

## <a name="how-to-identify-stale-dns-records"></a><span data-ttu-id="25ade-120">부실한 DNS 레코드를 식별하는 방법</span><span class="sxs-lookup"><span data-stu-id="25ade-120">How to identify stale DNS records</span></span>

<span data-ttu-id="25ade-121">조직에서 모든 DNS 레코드만 Teams DNS 레코드를 식별하려면 Teams 관리 센터를 사용하여 공존 모드를 TeamsOnly로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-121">To identify any DNS records that prevent your organization from becoming all Teams Only, you can use the Teams admin center  to change the coexistence mode to TeamsOnly.</span></span> <span data-ttu-id="25ade-122">업그레이드 **에서 Org 전체**  ->  **Teams 로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="25ade-122">Go to **Org-wide setting** -> **Teams Upgrade**.</span></span> <span data-ttu-id="25ade-123">조직이 모든 DNS 레코드를 Teams 오류 메시지에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-123">Any DNS records that prevent the organization from becoming Teams Only will be included in the error message.</span></span>  <span data-ttu-id="25ade-124">DNS 레코드가 발견되지 않으면 조직의 공존 모드가 TeamsOnly로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-124">In the event no DNS records are found, the coexistence mode for your organization will be changed to TeamsOnly.</span></span> 

## <a name="how-to-remove-stale-dns-records"></a><span data-ttu-id="25ade-125">부실한 DNS 레코드를 제거하는 방법</span><span class="sxs-lookup"><span data-stu-id="25ade-125">How to remove stale DNS records</span></span>

<span data-ttu-id="25ade-126">조직에 더 이상 온-프레미스 비즈니스용 Skype 서버 또는 Lync Server 사용자가 없는 경우 다음을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-126">If your organization no longer has any on-premises Skype for Business Server or Lync Server users, you must do the following:</span></span>

- <span data-ttu-id="25ade-127">DNS 비즈니스용 Skype 업데이트하여(Microsoft 365 배포 대신) DNS 레코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-127">Update Skype for Business DNS records to point to Microsoft 365 (instead of the on-premises deployment).</span></span>

- <span data-ttu-id="25ade-128">SIP 비즈니스용 Skype 더 이상 사용되지 않으면 DNS 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-128">Remove Skype for Business DNS records if the SIP domain is no longer used.</span></span> 

<span data-ttu-id="25ade-129">다음 레코드를 찾은 각 도메인에서 다음과 같이 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="25ade-129">In each domain where you find any of the following records, update them as follows:</span></span>

| <span data-ttu-id="25ade-130">레코드 유형</span><span class="sxs-lookup"><span data-stu-id="25ade-130">Record type</span></span> | <span data-ttu-id="25ade-131">이름</span><span class="sxs-lookup"><span data-stu-id="25ade-131">Name</span></span> | <span data-ttu-id="25ade-132">TTL</span><span class="sxs-lookup"><span data-stu-id="25ade-132">TTL</span></span> | <span data-ttu-id="25ade-133">우선 순위</span><span class="sxs-lookup"><span data-stu-id="25ade-133">Priority</span></span> | <span data-ttu-id="25ade-134">가중치</span><span class="sxs-lookup"><span data-stu-id="25ade-134">Weight</span></span> | <span data-ttu-id="25ade-135">포트</span><span class="sxs-lookup"><span data-stu-id="25ade-135">Port</span></span> | <span data-ttu-id="25ade-136">값</span><span class="sxs-lookup"><span data-stu-id="25ade-136">Value</span></span> |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| <span data-ttu-id="25ade-137">SRV</span><span class="sxs-lookup"><span data-stu-id="25ade-137">SRV</span></span> | <span data-ttu-id="25ade-138">_sipfederationtls.tcp</span><span class="sxs-lookup"><span data-stu-id="25ade-138">_sipfederationtls.tcp</span></span> | <span data-ttu-id="25ade-139">3600</span><span class="sxs-lookup"><span data-stu-id="25ade-139">3600</span></span> |  <span data-ttu-id="25ade-140">100</span><span class="sxs-lookup"><span data-stu-id="25ade-140">100</span></span> | <span data-ttu-id="25ade-141">1 </span><span class="sxs-lookup"><span data-stu-id="25ade-141">1</span></span> | <span data-ttu-id="25ade-142">5061</span><span class="sxs-lookup"><span data-stu-id="25ade-142">5061</span></span>  | <span data-ttu-id="25ade-143">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="25ade-143">sipfed.online.lync.com</span></span> |
| <span data-ttu-id="25ade-144">SRV</span><span class="sxs-lookup"><span data-stu-id="25ade-144">SRV</span></span> | <span data-ttu-id="25ade-145">_sip.tls</span><span class="sxs-lookup"><span data-stu-id="25ade-145">_sip.tls</span></span> | <span data-ttu-id="25ade-146">3600</span><span class="sxs-lookup"><span data-stu-id="25ade-146">3600</span></span>  | <span data-ttu-id="25ade-147">100</span><span class="sxs-lookup"><span data-stu-id="25ade-147">100</span></span> |    <span data-ttu-id="25ade-148">1 </span><span class="sxs-lookup"><span data-stu-id="25ade-148">1</span></span>   | <span data-ttu-id="25ade-149">443</span><span class="sxs-lookup"><span data-stu-id="25ade-149">443</span></span>   | <span data-ttu-id="25ade-150">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="25ade-150">sipdir.online.lync.com</span></span> |
| <span data-ttu-id="25ade-151">CNAME</span><span class="sxs-lookup"><span data-stu-id="25ade-151">CNAME</span></span> | <span data-ttu-id="25ade-152">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="25ade-152">lyncdiscover</span></span> |    <span data-ttu-id="25ade-153">3600</span><span class="sxs-lookup"><span data-stu-id="25ade-153">3600</span></span> |  <span data-ttu-id="25ade-154">해당 없음</span><span class="sxs-lookup"><span data-stu-id="25ade-154">N/A</span></span> |   <span data-ttu-id="25ade-155">해당 없음</span><span class="sxs-lookup"><span data-stu-id="25ade-155">N/A</span></span> |   <span data-ttu-id="25ade-156">해당 없음</span><span class="sxs-lookup"><span data-stu-id="25ade-156">N/A</span></span> |   <span data-ttu-id="25ade-157">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="25ade-157">webdir.online.lync.com</span></span> |
| <span data-ttu-id="25ade-158">CNAME</span><span class="sxs-lookup"><span data-stu-id="25ade-158">CNAME</span></span> |   <span data-ttu-id="25ade-159">sip</span><span class="sxs-lookup"><span data-stu-id="25ade-159">sip</span></span> | <span data-ttu-id="25ade-160">3600</span><span class="sxs-lookup"><span data-stu-id="25ade-160">3600</span></span> |    <span data-ttu-id="25ade-161">해당 없음</span><span class="sxs-lookup"><span data-stu-id="25ade-161">N/A</span></span> |   <span data-ttu-id="25ade-162">해당 없음</span><span class="sxs-lookup"><span data-stu-id="25ade-162">N/A</span></span>  | <span data-ttu-id="25ade-163">해당 없음</span><span class="sxs-lookup"><span data-stu-id="25ade-163">N/A</span></span> |    <span data-ttu-id="25ade-164">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="25ade-164">sipdir.online.lync.com</span></span> |
|||||||




