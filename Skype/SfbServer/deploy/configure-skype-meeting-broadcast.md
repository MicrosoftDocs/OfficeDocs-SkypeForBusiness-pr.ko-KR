---
title: Skype 모임 브로드캐스트에 대한 프레미스 배포 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '요약: 비즈니스용 Skype 서버 하이브리드 배포를 위해 Skype 모임 브로드캐스트를 구성하기 위해 수행하는 단계에 대해 설명합니다.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820708"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="e2977-103">Skype 모임 브로드캐스트에 대한 프레미스 배포 구성</span><span class="sxs-lookup"><span data-stu-id="e2977-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="e2977-104">**요약:** 비즈니스용 Skype 서버 하이브리드 배포를 위해 Skype 모임 브로드캐스트를 구성하기 위해 수행하는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="e2977-105">Skype 모임 브로드캐스트는 Office 365의 일부인 온라인 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="e2977-106">비즈니스용 Skype 서버를 실행하고 있으며 사용자 환경에서 Skype 모임 브로드캐스트를 사용하려는 경우 이 항목의 구성 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="e2977-107">시작하기 전에 비즈니스용 Skype Online을 통해 하이브리드 환경을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="e2977-108">자세한 내용은 비즈니스용 Skype 서버와 비즈니스용 [Skype Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 간의 하이브리드 연결 계획과 비즈니스용 Skype 서버와 비즈니스용 Skype Online 간에 하이브리드 연결 [배포를 참조하세요.](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="e2977-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="e2977-109">Skype 모임 브로드캐스트에 대한 하이브리드 환경 구성</span><span class="sxs-lookup"><span data-stu-id="e2977-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="e2977-110">Skype 모임 브로드캐스트를 위한 환경을 준비하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="e2977-111">비즈니스용 Skype Online 리소스와의 페더 연결 구성</span><span class="sxs-lookup"><span data-stu-id="e2977-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="e2977-112">SIP 페더전 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="e2977-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="e2977-113">비즈니스용 Skype Online 리소스와의 페더 연결 구성</span><span class="sxs-lookup"><span data-stu-id="e2977-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="e2977-114">비즈니스용 Skype Online 리소스와의 페더전을 사용하도록 설정하려면 SIP 페더타임 공급자에 대해 외부 액세스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="e2977-115">비즈니스용 Skype 서버 제어판을 사용하여 이 작업을 수행하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="e2977-116">비즈니스용 Skype 서버 제어판을 시작하고 왼쪽에서 **외부** 액세스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="e2977-117">**SIP 페더리트 공급자를 선택하고** 새로 **고치기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e2977-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="e2977-118">다음 설정을 사용하여 새 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="e2977-119">**이 공급자와의 통신을 사용하도록 설정:**</span><span class="sxs-lookup"><span data-stu-id="e2977-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="e2977-120">선택됨</span><span class="sxs-lookup"><span data-stu-id="e2977-120">Selected</span></span>  <br/> |
|<span data-ttu-id="e2977-121">**공급자 이름:**</span><span class="sxs-lookup"><span data-stu-id="e2977-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="e2977-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="e2977-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="e2977-123">**액세스 에지 서비스(FQDN):**    필수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="e2977-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="e2977-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="e2977-125">**기본 확인 수준:**</span><span class="sxs-lookup"><span data-stu-id="e2977-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="e2977-126">사용자가 이 공급자를 사용하는 모든 사용자와 통신할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="e2977-127">비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행하여 비즈니스용 Skype Online 리소스와의 페더 관리를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="e2977-128">SIP 페더전 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="e2977-128">Configure SIP federated domains</span></span>

<span data-ttu-id="e2977-129">그런 다음 허용 도메인 목록에 SIP 페더리 도메인을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="e2977-130">나열된 각 도메인에 대해 이 단계를 반복하여 4개 새 SIP 페더타임 도메인을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="e2977-131">이러한 도메인은 비즈니스용 Skype Online에서 사용되는 지역별 데이터 센터용입니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="e2977-132">비즈니스용 Skype 서버 제어판을 시작하고 왼쪽에서 **외부** 액세스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="e2977-133">**SIP 페더리트 도메인을 선택하고** 새로 **고치기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e2977-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="e2977-134">도메인 이름 **또는 FQDN의** 경우 다음 각 도메인에 대해 이 절차를 반복하여 도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="e2977-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e2977-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="e2977-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e2977-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="e2977-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e2977-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="e2977-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="e2977-138">resources.lync.com</span></span>
    
<span data-ttu-id="e2977-139">비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행하여 SIP 페더타 도메인에 대한 외부 액세스를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="e2977-140">이러한 구성 단계를 완료한 후 배포에서 Skype 모임 브로드캐스트 사용을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2977-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="e2977-141">Skype 모임 브로드캐스트에 대한 자세한 내용은 [Skype](https://go.microsoft.com/fwlink/?LinkId=617071) 모임 브로드캐스트란? 및 Skype 모임 [브로드캐스트 관리자 가이드를 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=617075)</span><span class="sxs-lookup"><span data-stu-id="e2977-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

