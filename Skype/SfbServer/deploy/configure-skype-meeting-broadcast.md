---
title: Skype 모임 브로드캐스트에 대 한 온-프레미스 배포 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 온-프레미스 비즈니스용 skype Server 하이브리드 배포에 대해 Skype 모임 브로드캐스트를 구성 하기 위해 수행 해야 하는 단계에 대해 알아보세요.'
ms.openlocfilehash: 8bdbb163f5ef867711ce109bc923ba0ec8401ffa
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790946"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="66c87-103">Skype 모임 브로드캐스트에 대 한 온-프레미스 배포 구성</span><span class="sxs-lookup"><span data-stu-id="66c87-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="66c87-104">**요약:** 온-프레미스 비즈니스용 skype Server 하이브리드 배포에 대해 Skype 모임 브로드캐스트를 구성 하기 위해 수행 해야 하는 단계에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="66c87-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="66c87-105">Skype 모임 브로드캐스트는 Office 365의 일부인 온라인 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="66c87-106">Skype for Business Server 온-프레미스를 실행 중이 고 해당 환경에서 Skype 모임 브로드캐스트를 사용 하려는 경우이 항목의 구성 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="66c87-107">시작 하기 전에 비즈니스용 Skype Online을 사용 하 여 하이브리드에 맞게 환경을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="66c87-108">자세한 내용은 비즈니스용 [Skype 서버 및 비즈니스용 Skype online 간 하이브리드 연결 계획](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 을 참조 하 고 비즈니스용 [skype 서버와 비즈니스용 skype online 간 하이브리드 연결을 배포](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="66c87-109">Skype 모임 브로드캐스트를 위한 하이브리드 환경 구성</span><span class="sxs-lookup"><span data-stu-id="66c87-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="66c87-110">Skype 모임 브로드캐스트를 위해 환경을 준비 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="66c87-111">비즈니스용 Skype Online 리소스를 사용 하 여 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="66c87-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="66c87-112">SIP 페더레이션 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="66c87-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="66c87-113">비즈니스용 Skype Online 리소스를 사용 하 여 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="66c87-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="66c87-114">비즈니스용 Skype Online 리소스와 페더레이션을 사용 하도록 설정 하려면 SIP 페더레이션 공급자에 대 한 외부 액세스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="66c87-115">비즈니스용 Skype 서버 제어판을 사용 하 여이 작업을 수행 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="66c87-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="66c87-116">비즈니스용 Skype 서버 제어판을 시작 하 고 왼쪽에서 **외부 액세스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="66c87-117">**SIP 페더레이션 공급자** 를 선택 하 고 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="66c87-118">다음 설정을 사용 하 여 새 공급자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="66c87-119">**이 공급자와 통신 사용:**</span><span class="sxs-lookup"><span data-stu-id="66c87-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="66c87-120">선택한</span><span class="sxs-lookup"><span data-stu-id="66c87-120">Selected</span></span>  <br/> |
|<span data-ttu-id="66c87-121">**공급자 이름:**</span><span class="sxs-lookup"><span data-stu-id="66c87-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="66c87-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="66c87-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="66c87-123">**액세스에 지 서비스 (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="66c87-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="66c87-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="66c87-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="66c87-125">**기본 확인 수준:**</span><span class="sxs-lookup"><span data-stu-id="66c87-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="66c87-126">사용자가이 공급자를 사용 하 여 모든 사용자와 통신할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="66c87-127">비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행 하 여 비즈니스용 Skype Online 리소스에서 페더레이션을 사용 하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="66c87-128">SIP 페더레이션 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="66c87-128">Configure SIP federated domains</span></span>

<span data-ttu-id="66c87-129">다음으로 허용 된 도메인 목록에 SIP 페더레이션 도메인을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="66c87-130">나열 된 각 도메인에 대해 이러한 단계를 반복 하 여 4 개의 새로운 SIP 페더레이션 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="66c87-131">이러한 도메인은 비즈니스용 Skype Online에서 사용 되는 지역 데이터 센터에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="66c87-132">비즈니스용 Skype 서버 제어판을 시작 하 고 왼쪽에서 **외부 액세스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="66c87-133">**SIP 페더레이션 도메인** 을 선택 하 고 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="66c87-134">**도메인 이름 (또는 FQDN):** 다음 각 도메인에 대해이 절차를 반복 하 여 도메인을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="66c87-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="66c87-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="66c87-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="66c87-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="66c87-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="66c87-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="66c87-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="66c87-138">resources.lync.com</span></span>
    
<span data-ttu-id="66c87-139">비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행 하 여 SIP 페더레이션 도메인에 대 한 외부 액세스를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="66c87-140">이러한 구성 단계를 완료 한 후에는 배포에서 Skype 모임 브로드캐스트를 사용 하 여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66c87-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="66c87-141">Skype 모임 브로드캐스트에 대 한 자세한 내용은 skype [모임 브로드캐스트 소개](https://go.microsoft.com/fwlink/?LinkId=617071) 및 [Skype 모임 브로드캐스트 관리 가이드](https://go.microsoft.com/fwlink/?LinkId=617075)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66c87-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

