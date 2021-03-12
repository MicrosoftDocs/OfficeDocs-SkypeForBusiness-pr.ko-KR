---
title: 비즈니스용 Skype 서버에서 TLS 1.0/1.1을 사용하지 않도록 설정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 환경에서 TLS 1.0 및 1.1을 사용할 수 없는 경우를 준비하고 구현합니다.
ms.openlocfilehash: 214605f80c79d7ecb334aeca49d29210e888b511
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726399"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="8bb47-103">비즈니스용 Skype 서버에서 TLS 1.0/1.1을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8bb47-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="8bb47-104">이 문서는 환경에서 TLS 1.0 및 1.1의 사용 안 하게 설정하는 것을 준비하고 구현하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-104">This article helps you prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="8bb47-105">이 프로세스에서는 광범위한 계획과 준비가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="8bb47-106">조직에서 TLS 1.0 및 1.1을 사용하지 않도록 설정하는 계획을 세우면 이 문서의 모든 정보를 주의 깊게 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="8bb47-106">Carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="8bb47-107">TLS 1.0/1.1을 사용할 수 없는 경우 영향을 줄 수 있는 많은 외부 종속성 및 연결 조건이 있으므로 광범위한 계획 및 테스트가 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-107">There are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

- [<span data-ttu-id="8bb47-108">백그라운드 및 범위</span><span class="sxs-lookup"><span data-stu-id="8bb47-108">Background and scope</span></span>](#background-and-scope)
- [<span data-ttu-id="8bb47-109">선행 절차 및</span><span class="sxs-lookup"><span data-stu-id="8bb47-109">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="8bb47-110">고급 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="8bb47-110">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a><span data-ttu-id="8bb47-111">백그라운드 및 범위</span><span class="sxs-lookup"><span data-stu-id="8bb47-111">Background and scope</span></span>

<span data-ttu-id="8bb47-112">비즈니스용 Skype 서버 On-Premises에 대한 TLS 1.0 및 1.1 비활성화 지원을 제공하기 위한 기본 드라이버는 PCI(Payment Card Industry) 보안 표준 위원회 및 연방 정보 처리 표준 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-112">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="8bb47-113">PCI 요구 사항에 대한 자세한 내용은 에서 찾을 수 [있습니다.](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)</span><span class="sxs-lookup"><span data-stu-id="8bb47-113">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="8bb47-114">Microsoft는 조직이 이러한 요구 사항 또는 기타 요구 사항을 준수해야 하는지 여부에 대한 지침을 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-114">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="8bb47-115">환경에서 TLS 1.0 및/또는 1.1을 사용하지 않도록 설정하는 데 필요한지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-115">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="8bb47-116">Microsoft는 여기에서 사용할 수 있는 [](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)TLS에 대한 백서를 생성했습니다. 또한 이 Exchange 블로그에서 사용할 수 있는 배경 읽기를 [권장합니다.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="8bb47-116">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="8bb47-117">지원 가능성 범위</span><span class="sxs-lookup"><span data-stu-id="8bb47-117">Supportability Scope</span></span>

<span data-ttu-id="8bb47-118">*범위는* 지원 가능성 경계를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-118">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="8bb47-119">*완전히 테스트 및* 지원되는 것은 나열된 제품 버전에 대해 TLS 1.0 및 1.1의 사용 안 을 완전히 지원하고 테스트했다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-119">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="8bb47-120">*현재 조사 중이란* 의미일 수 있습니다. TLS 비활성화 지원을 위해 이러한 제품을 범위로 가져오는 것을 적극적으로 조사하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-120">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="8bb47-121">*범위를 벗어났다는* 것은 이러한 제품 버전이 TLS 1.0 또는 1.1의 사용 안 을 지원하지 않는 것으로, 예외를 제외하고는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-121">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="8bb47-122">완전히 테스트 및 지원되는 서버</span><span class="sxs-lookup"><span data-stu-id="8bb47-122">Fully tested and supported servers</span></span>

- <span data-ttu-id="8bb47-123">비즈니스용 Skype 서버 2019 CU1 17.0.2046.123(2019년 6월) 이상</span><span class="sxs-lookup"><span data-stu-id="8bb47-123">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="8bb47-124">비즈니스용 Skype 서버 2015 CU9 6.0.9319.548(2019년 5월) 이상( Windows Server 2012(KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 또는 변경된 업데이트 사용), 2012 R2 또는 2016.</span><span class="sxs-lookup"><span data-stu-id="8bb47-124">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="8bb47-125">Windows Server 2008 R2, 2012(KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 또는 업그레이드된 업데이트) 또는 2012 R2에서 CU9 6.0.9319.548(2019년 5월) 이상이 있는 업그레이드된 비즈니스용 Skype 서버 2015</span><span class="sxs-lookup"><span data-stu-id="8bb47-125">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="8bb47-126">Exchange 연결 및 Outlook Web App Exchange Server 2010 SP3 RU19 이상, [여기에](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/) 지침</span><span class="sxs-lookup"><span data-stu-id="8bb47-126">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="8bb47-127">비즈니스용 Skype 서버 2015 CU6 HF2 이상이 있는 SBA(Survivable Branch Appliance)(공급업체에 적절한 업데이트를 패키지로 만들며 어플라이언스에서 사용할 수 있도록 설정되어 있는지 공급업체에 확인)</span><span class="sxs-lookup"><span data-stu-id="8bb47-127">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="8bb47-128">비즈니스용 Skype 서버 2015 CU6 HF2 이상을 통해 SBS(Survivable Branch Server)</span><span class="sxs-lookup"><span data-stu-id="8bb47-128">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="8bb47-129">Lync Server 2013 **에지 역할만** 입니다. 이는 에지 역할이 Windows Fabric 1.0에 종속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-129">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="8bb47-130">완전히 테스트 및 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8bb47-130">Fully tested and supported clients</span></span>

- <span data-ttu-id="8bb47-131">Lync 2013(비즈니스용 Skype) 데스크톱 클라이언트, MSI 및 C2R(기본 [15.0.5023.1000 이상 포함)](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="8bb47-131">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="8bb47-132">비즈니스용 Skype 2016 데스크톱 클라이언트, MSI [16.0.4678.1000](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)이상, 기본 포함</span><span class="sxs-lookup"><span data-stu-id="8bb47-132">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="8bb47-133">비즈니스용 Skype 2016 실행하려면 [2018년 4월 업데이트가](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) 필요하세요.</span><span class="sxs-lookup"><span data-stu-id="8bb47-133">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="8bb47-134">월별 및 Semi-Annual, 16 \. 0 \. 9126 \. 2152 이상</span><span class="sxs-lookup"><span data-stu-id="8bb47-134">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="8bb47-135">Semi-Annual 및 지연 채널, 16 \. 0 \. 8431 \. 2242 이상</span><span class="sxs-lookup"><span data-stu-id="8bb47-135">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="8bb47-136">Mac의 비즈니스용 Skype 16.15 이상</span><span class="sxs-lookup"><span data-stu-id="8bb47-136">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="8bb47-137">iOS 및 Android 6.19 이상용 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="8bb47-137">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="8bb47-138">Microsoft Teams 룸(이전의 Skype 룸 시스템 V2 SRS V2) 4.0.64.0(2018년 12월) 이상</span><span class="sxs-lookup"><span data-stu-id="8bb47-138">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="8bb47-139">KB4499162(2019년 5월, OS 빌드 15063.1835) 이상을 기반으로 하는 Team Edition용 Surface Hub 업데이트</span><span class="sxs-lookup"><span data-stu-id="8bb47-139">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="8bb47-140">Skype Web App 2015 CU6 HF2 이상(서버와 함께 배송)</span><span class="sxs-lookup"><span data-stu-id="8bb47-140">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="8bb47-141">현재 조사 중</span><span class="sxs-lookup"><span data-stu-id="8bb47-141">Currently being investigated</span></span>

- <span data-ttu-id="8bb47-142">통화 품질 대시보드(TLS 1.0, 1.1이 비활성화된 후 새 설치, 아래 참조)\*</span><span class="sxs-lookup"><span data-stu-id="8bb47-142">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="8bb47-143">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="8bb47-143">Out of scope</span></span>

<span data-ttu-id="8bb47-144">설명된 경우를 제외하고 다음 제품은 TLS 1.0/1.1 사용 안 의 지원 범위에 있지 않을 뿐만 아니라 TLS 1.0 및 1.1이 비활성화된 환경에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-144">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="8bb47-145">즉, 여전히 범위를 벗어났다가 서버나 클라이언트를 활용하는 경우 비즈니스용 Skype 서버의 모든 곳에서 TLS 1.0/1.1을 사용하지 않도록 설정해야 하는 경우 이를 업데이트하거나 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-145">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="8bb47-146">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bb47-146">Lync Server 2013</span></span>
- <span data-ttu-id="8bb47-147">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8bb47-147">Lync Server 2010</span></span>
- <span data-ttu-id="8bb47-148">Windows Server 2008 이상</span><span class="sxs-lookup"><span data-stu-id="8bb47-148">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="8bb47-149">Mac 2011용 Lync</span><span class="sxs-lookup"><span data-stu-id="8bb47-149">Lync for Mac 2011</span></span>
- <span data-ttu-id="8bb47-150">Lync 2013 for Mobile - iOS, iPad, Android 또는 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="8bb47-150">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="8bb47-151">Lync "MX" Windows 스토어 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8bb47-151">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="8bb47-152">Lync 룸 시스템(a.k.a.</span><span class="sxs-lookup"><span data-stu-id="8bb47-152">Lync Room System (a.k.a.</span></span> <span data-ttu-id="8bb47-153">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="8bb47-153">SRSv1).</span></span> <span data-ttu-id="8bb47-154">LRS는 2018년 10월 9일 지원이 종료된 후 TLS 1.2를 지원하기 위해 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-154">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="8bb47-155">모든 Lync 2010 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8bb47-155">All Lync 2010 clients</span></span>
- <span data-ttu-id="8bb47-156">Lync Phone Edition - 여기에서 지침이 [업데이트되었습니다.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)</span><span class="sxs-lookup"><span data-stu-id="8bb47-156">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="8bb47-157">2013 기반 SBA(Survivable Branch Appliance) 또는 SBS(Survivable Branch Server)</span><span class="sxs-lookup"><span data-stu-id="8bb47-157">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="8bb47-158">CCE(Cloud Connector Edition)</span><span class="sxs-lookup"><span data-stu-id="8bb47-158">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="8bb47-159">Windows Phone용 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="8bb47-159">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="8bb47-160">예외</span><span class="sxs-lookup"><span data-stu-id="8bb47-160">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="8bb47-161">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bb47-161">Lync Server 2013</span></span>

<span data-ttu-id="8bb47-162">Lync Server 2013은 Windows Fabric 버전 1.0에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-162">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="8bb47-163">Lync Server 2013의 디자인 단계에서 Windows Fabric 1.0은 복제, 고가용성 및 내결함성을 제공하기 위해 고급 및 새로운 분산 아키텍처로 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-163">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="8bb47-164">시간이 지날 때 비즈니스용 Skype 서버와 Windows Fabric은 모두 후속 버전에서 중요한 재설계를 통해 이 공동 아키텍처를 크게 개선했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-164">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="8bb47-165">예를 들어 현재 비즈니스용 Skype 2015 서버는 Windows Fabric 3.0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-165">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="8bb47-166">그러나 Windows Fabric 1.0은 **TLS 1.2를 지원하지 않습니다.  그러나 TLS 1.2에서 작동하기 위해 Lync Server 2013을 업데이트할 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="8bb47-166">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="8bb47-167">이 업데이트는 Lync Server 2013의 다음 누적 업데이트에 추가될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-167">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="8bb47-168">공조, 마이그레이션, 페더전 및 하이브리드 시나리오를 사용할 수 있도록 TLS 1.2 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-168">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="8bb47-169">조직에서 TLS 1.0 및 1.1을 사용하지 않도록 설정해야 하는 경우 현재 Lync Server 2013을 사용하는 경우 계획 프로세스를 시작하는 것이 좋습니다. 즉, 현재 업그레이드를 진행하거나 비즈니스용 Skype 서버 2015 이상으로 나란히 마이그레이션(새 풀, 사용자 이동)을 진행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-169">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="8bb47-170">또는 비즈니스용 Skype Online으로의 마이그레이션을 가속화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-170">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="8bb47-171">통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="8bb47-171">Call Quality Dashboard</span></span>

<span data-ttu-id="8bb47-172">현재 새 설치 중에(사내 환경에 처음 설치할 때) On-Premises Call Quality Dashboard는 TLS 1.0에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-172">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="8bb47-173">We are currently investigating this issue and plan to release a fix in the near future.</span><span class="sxs-lookup"><span data-stu-id="8bb47-173">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="8bb47-174">CQD를 설치하고 TLS 1.0도 사용하지 않도록 설정하려면 먼저 CQD 설치를 완료한 다음 TLS 1.0 비활성화를 진행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-174">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="8bb47-175">비즈니스용 Skype SDN 관리자</span><span class="sxs-lookup"><span data-stu-id="8bb47-175">Skype for Business SDN Manager</span></span>

<span data-ttu-id="8bb47-176">데이터베이스를 사용하는 비즈니스용 Skype SQL 새 설치 중에 TLS 1.0에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-176">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="8bb47-177">데이터베이스의 SQL 사용하여 비즈니스용 Skype SDN 관리자를 설치하고 TLS 1.0도 사용하지 않도록 설정하려면 먼저 비즈니스용 Skype SDN 관리자를 완료한 다음 TLS 1.0 비활성화를 진행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-177">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="8bb47-178">설치 전에 TLS 1.0을 사용하지 않도록 설정한 경우 비즈니스용 Skype SDN 관리자 SQL 데이터베이스를 호스팅하는 데 사용할 SQL Server 서버에서 TLS 1.0을 다시 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-178">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="8bb47-179">타사 장치</span><span class="sxs-lookup"><span data-stu-id="8bb47-179">Third-party devices</span></span>

<span data-ttu-id="8bb47-180">3PIP 전화, 비디오 회의, 역방향 Proxies 및 부하 균형 장치와 같은 타사 장치에서는 TLS 1.2 지원 가능성의 유효성을 검사하고 신중하게 테스트한 후 필요한 경우 공급업체에 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-180">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="8bb47-181">에지 서버에서 TLS 1.0/1.1을 사용할 수 없는 경우의 페더링 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8bb47-181">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="8bb47-182">에지 서버에서 TLS 1.0/1.1을 사용할 수 없는 경우의 영향을 신중하게 계획하고 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-182">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="8bb47-183">TLS 1.0 및 1.1을 사용하지 않도록 설정하면 다른 조직이 더 이상 조직과 페더러이트할 수 없는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-183">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="8bb47-184">패치되지 않은(SfB 2015, Lync 2013) 또는 이전(2010) 외부 시스템과의 호환성을 유지하기 위해 에지 서버에서 TLS 1.0/1.1을 사용하도록 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-184">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="8bb47-185">Microsoft는 에지 네트워크(또는 네트워크)가 PCI 표준에 속하는지 여부에 대한 조언이나 권장 사항을 제공할 수 없습니다. 개별 회사에서 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-185">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="8bb47-186">비즈니스용 Skype Online은 현재 TLS 1.2를 사용할 수 있으므로 온라인과의 하이브리드/페더러에 아무 영향도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-186">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="8bb47-187">PIC(공용 IM 연결)에서 Skype 소비자 서비스에 연결: Skype 연결에 영향을 미치기 위해 TLS 1.0/1.1을 사용할 수 [없습니다.](../../deploy/deploy-skype-connectivity.md) Microsoft PIC 게이트웨이는 이미 TLS 1.2를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-187">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="8bb47-188">선행 절차 및</span><span class="sxs-lookup"><span data-stu-id="8bb47-188">Prerequisites and process</span></span>

<span data-ttu-id="8bb47-189">위에서 언급한 경우를 제외하고 TLS 1.0 및 1.1이 범위를 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-189">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="8bb47-190">이는 Microsoft의 업데이트된 지침을 일시 중지하고 기다려야 하다는 의미일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-190">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="8bb47-191">모든 요구 사항을 충족하고 격차를 해결할 계획이 있는 경우 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-191">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="8bb47-192">비즈니스용 Skype 서버 2019는 설치 시 절차를 완료할 수 있는 반면 비즈니스용 Skype 서버 2015는 CU9를 설치하고, .NET 및 SQL에 선행 요구 업데이트를 적용하고, 선행 레지스트리 키를 배포하고, 마지막으로 별도의 OS 구성 업데이트 라운드(예: 레지스트리 파일 가져오기에서 TLS 1.0 및 1.1을 사용 안 하도록 설정)하도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-192">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="8bb47-193">환경의 모든 서버에서 TLS 1.0 및 1.1을 사용할 수 있도록 설정하기 전에 비즈니스용 Skype 서버 2015 CU6 HF2를 비롯한 모든 선행 구성 요소의 설치를 완료하는 것이 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-193">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="8bb47-194">Edge 역할 및 백 SQL 포함하여 모든 비즈니스용 Skype 서버에는 업데이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-194">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="8bb47-195">또한 지원되는(범위 내) 클라이언트가 필요한 최소 버전으로 업데이트되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-195">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="8bb47-196">관리 Workstation도 업데이트하는 것을 잊지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8bb47-196">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="8bb47-197">비즈니스용 Skype 서버를 업그레이드하기 위한 "내부" 작업의 일반적인 순서를 따르고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-197">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="8bb47-198">일반적으로와 동일한 방식으로 Director 풀, 영구 채팅 및 페어링된 풀을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-198">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="8bb47-199">업그레이드 순서 및 방법은 여기와 [여기에서](topology.md) [다를 수 있습니다.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="8bb47-199">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="8bb47-200">높은 수준의 프로세스</span><span class="sxs-lookup"><span data-stu-id="8bb47-200">High-level process</span></span>

1. <span data-ttu-id="8bb47-201">프로덕션 서버를 구성하기 전에 랩의 모든 단계를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-201">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="8bb47-202">업데이트할 각 개별 서버에서 내보낼 레지스트리 복사본을 백업하고 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-202">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="8bb47-203">서버 간에는 레지스트리를 공유할 수 없습니다. 이러한 키에는 고유한 컴퓨터 기반 키가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-203">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="8bb47-204">모든 비즈니스용 Skype 2015 서버를 CU9 이상으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-204">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="8bb47-205">비즈니스용 Skype 서버 2019의 경우 CU1 이상으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-205">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="8bb47-206">모든 서버에 모든 선행 준비를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-206">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="8bb47-207">선행 레지스트리 키를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-207">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="8bb47-208">범위 내 클라이언트가 모두 업데이트되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-208">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="8bb47-209">레지스트리 가져오기에서 TLS 1.0 및 1.1을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8bb47-209">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="8bb47-210">워크로드가 예상대로 작동하고 있는지 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-210">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="8bb47-211">문제가 발생하면 문제 해결 또는</span><span class="sxs-lookup"><span data-stu-id="8bb47-211">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="8bb47-212">2단계에서 레지스트리를 복원하여 TLS 1.0 및 1.1을 다시 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="8bb47-212">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="8bb47-213">TLS 1.2만 사용 중이지 않은지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-213">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="8bb47-214">모든 서버에 필요한 설치</span><span class="sxs-lookup"><span data-stu-id="8bb47-214">Install prerequisites to all servers</span></span>

<span data-ttu-id="8bb47-215">비즈니스용 Skype 서버 2015 배포의 운영 체제 수준에서 TLS 1.0 및 1.1을 사용하지 않도록 설정하기 전에 광범위한 종속성 업데이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-215">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="8bb47-216">다음은 TLS 1.2를 지원할 수 있는 최소 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-216">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="8bb47-217">TLS 1.0 및 1.1을 사용 안 하게 설정하기 전에 환경의 모든 비즈니스용 Skype 서버에 모든 선행 업데이트를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-217">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="8bb47-218">비즈니스용 Skype 서버 2015 CU9 6.0.9319.548(2019년 5월) 이상</span><span class="sxs-lookup"><span data-stu-id="8bb47-218">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="8bb47-219">.NET Framework SchUseStrongCrypto를 사용하여 [4.7](https://www.microsoft.com/download/details.aspx?id=55167) 이상을 사용할 수 있습니다(아래 제공).</span><span class="sxs-lookup"><span data-stu-id="8bb47-219">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="8bb47-220">SQL 비즈니스용 Skype 2015 서버 및 백디드에서 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-220">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="8bb47-221">Enterprise Edition 풀 SQL 먼저 백end를 업데이트한 다음 해당 FES를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-221">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="8bb47-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)이상/ SQL Server 2012 SP2 + CU16 이상/SQL Server [2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)이상/ SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="8bb47-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="8bb47-223">SQL Server 2012용 SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="8bb47-223">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="8bb47-224">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span><span class="sxs-lookup"><span data-stu-id="8bb47-224">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="8bb47-225">SQL Server 2014 SP2용 공유 관리 개체</span><span class="sxs-lookup"><span data-stu-id="8bb47-225">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="8bb47-226">SQL server 2014 SP2용 SQLSysClrTypes</span><span class="sxs-lookup"><span data-stu-id="8bb47-226">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="8bb47-227">권장되는 작업 순서로 선행 준비 단계를 설치하는 기본 단계</span><span class="sxs-lookup"><span data-stu-id="8bb47-227">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="8bb47-228">모든 서버에 비즈니스용 Skype 서버 CU9 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-228">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="8bb47-229">업데이트 프로그램을 사용하여 구성 요소에 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-229">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="8bb47-230">문서화된 절차에 따라 데이터베이스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-230">Update databases according to documented procedures.</span></span> <span data-ttu-id="8bb47-231">비즈니스용 Skype 서버 2015의 경우 KB [3061064를 참조하세요.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="8bb47-231">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="8bb47-232">다른 변경 내용을 적용하기 전에 배포에서 제품 기능의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-232">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="8bb47-233">.NET 4.7 오프라인 설치 관리자를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-233">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="8bb47-234">참조: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="8bb47-234">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="8bb47-235">프런트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중지되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-235">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="8bb47-236">참조: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="8bb47-236">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="8bb47-237">예(Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="8bb47-237">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="8bb47-238">예(Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="8bb47-238">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="8bb47-239">설치 관리자 패키지를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-239">Run the installer package.</span></span>
    7. <span data-ttu-id="8bb47-240">서버를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-240">Reboot the server.</span></span>
3. <span data-ttu-id="8bb47-241">모든 SQL Express 2014를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-241">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="8bb47-242">참조: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="8bb47-242">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="8bb47-243">SQL 2014 SP2 다운로드</span><span class="sxs-lookup"><span data-stu-id="8bb47-243">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="8bb47-244">참조: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="8bb47-244">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="8bb47-245">서버의 폴더에 설치 미디어 복사(예: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="8bb47-245">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="8bb47-246">프런트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중지됨 확인</span><span class="sxs-lookup"><span data-stu-id="8bb47-246">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="8bb47-247">예(Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="8bb47-247">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="8bb47-248">예(Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="8bb47-248">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="8bb47-249">관리자 명령 프롬프트를 열고 설치된 모든 구성 요소 및 인스턴스 업그레이드</span><span class="sxs-lookup"><span data-stu-id="8bb47-249">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="8bb47-250">예: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="8bb47-250">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="8bb47-251">기본 SQL 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-251">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="8bb47-252">참조: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="8bb47-252">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="8bb47-253">에서 다운로드 [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="8bb47-253">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="8bb47-254">프런트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중지되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-254">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="8bb47-255">예(Standard Edition): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="8bb47-255">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="8bb47-256">예(Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="8bb47-256">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="8bb47-257">설치된 SQL 실행 중지</span><span class="sxs-lookup"><span data-stu-id="8bb47-257">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="8bb47-258">예: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="8bb47-258">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="8bb47-259">예: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="8bb47-259">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="8bb47-260">예(Standard Edition에만 해당): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="8bb47-260">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="8bb47-261">업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-261">Install the update.</span></span>
5. <span data-ttu-id="8bb47-262">TLS 1.2(SQL Server)에 대한 지원을 포함하기 위해 ODBC 드라이버 [11을 업데이트합니다(KB 3135244).](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="8bb47-262">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="8bb47-263">ODBC [드라이버 11 for SQL Server - Windows를 다운로드합니다.](https://www.microsoft.com/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="8bb47-263">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="8bb47-264">프런트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중지되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-264">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="8bb47-265">예제(Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="8bb47-265">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="8bb47-266">예(Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="8bb47-266">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="8bb47-267">업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-267">Install the update.</span></span>
6. <span data-ttu-id="8bb47-268">선행 레지스트리 키를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-268">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="8bb47-269">사전 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="8bb47-269">Pre-requisite registry keys</span></span>

<span data-ttu-id="8bb47-270">다음 테스트를 복사하여 메모장에 붙여넣고 TLSPreReq.reg 또는 선택한 이름을 변경한 다음 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="8bb47-270">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

<span data-ttu-id="8bb47-271">Enterprise edition SQL 풀에 대한 백 엔드의 경우, 선행 및 TLS 사용 안 은 모든 업데이트 또는 OS SQL 처리해야 합니다. 참조: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="8bb47-271">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="8bb47-272">선행 응용 프로그램과 TLS를 사용할 수 없는 단계는 모두 결합할 수 있는 반면 운영 체제 수준에서 TLS 1.0 및 1.1을 계속 사용 안 하게 되기 전에 모든 선행 단계를 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-272">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="8bb47-273">모범 사례 방법은 모든 선행 구성을 배포하고 모든 워크로드가 예상대로 올바르게 작동하고 유효성을 검사한 다음 나중에 TLS 1.0/1.1을 사용하지 않도록 설정하여 환경을 준비하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-273">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="8bb47-274">레지스트리 가져오기에서 TLS 1.0 및 1.1을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8bb47-274">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="8bb47-275">다음 단계를 진행하기 전에 모든 선행 작업을 완료하고 비즈니스용 Skype 서버를 *업데이트해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="8bb47-275">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="8bb47-276">다음 텍스트를 메모장 파일에 복사하고 **TLSDisable.reg로 이름을 변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="8bb47-276">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

<span data-ttu-id="8bb47-277">TLS 1.0 및 1.1을 사용하지 않도록 설정할 각 서버에서 .reg 파일을 가져오면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-277">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="8bb47-278">서버를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-278">Reboot the server.</span></span> <span data-ttu-id="8bb47-279">서비스가 다시 온라인이 되돌아오면 다음 서버로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="8bb47-279">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="8bb47-280">Enterprise Edition 풀에 대한 접근 방식은 모든 OS 업데이트에 대해 취할 수 있는 방식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-280">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="8bb47-281">여기에서 TLS 1.0 및 1.1을 사용 안 하게 하는 것 이상으로 많은 작업을 수행하고 있는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-281">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="8bb47-282">당사는 위에서 설명한 대로 암호 제품군 다시 주문 및 일부 이전 약한 암호의 비동기화가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-282">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="8bb47-283">비즈니스용 Skype 서버에서 SCHANNEL 및 Crypto API에 대한 이러한 변경 내용을 공식적으로 지원한 것은 이번이 처음입니다. 이 변경 내용은 현재 지원 및 테스트한 유일한 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-283">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="8bb47-284">향후에 추가 구성을 고려할 수 있지만 현재는 구현에서 레지스트리 가져오기 파일을 수정하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-284">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="8bb47-285">워크로드가 예상대로 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8bb47-285">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="8bb47-286">환경에서 TLS 1.0 및 1.1을 사용하지 않도록 설정한 경우 IM & 현재 상태, P2P 통화, Enterprise Voice 등의 모든 주요 워크로드가 예상대로 작동하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-286">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="8bb47-287">**TLS 1.2만 사용 중이면 유효성 검사**</span><span class="sxs-lookup"><span data-stu-id="8bb47-287">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="8bb47-288">보안 팀이 비즈니스용 Skype 트래픽에 대한 새 감사를 수행하여 이전 프로토콜 TLS 1.0 및 1.1이 더 이상 사용되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-288">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="8bb47-289">또는 TLS Internet Explorer TLS 1.1을 사용하지 않도록 설정한 후 비즈니스용 Skype 서버 2015에서 웹 서비스에 대한 TLS 연결을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-289">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="8bb47-290">시작 Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8bb47-290">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="8bb47-291">도구   >  **인터넷 옵션 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8bb47-291">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="8bb47-292">고급 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-292">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="8bb47-293">**설정에서** 아래쪽으로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-293">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="8bb47-294">TLS 1.0, TLS 1.1 및 TLS 1.2가 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-294">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="8bb47-295">SfB 2015 풀의 내부 웹 서비스 URL을 검색합니다(성공적으로 연결해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="8bb47-295">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="8bb47-296">다시 Internet Explorer **TLS 1.2만** 사용 옵션을 사용하지 않도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="8bb47-296">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="8bb47-297">SfB 2015 풀의 내부 웹 서비스 URL을 다시 검색합니다(연결하지 못해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="8bb47-297">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![인터넷 옵션](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="8bb47-299">고급 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="8bb47-299">Advanced deployment scenarios</span></span>

<span data-ttu-id="8bb47-300">비즈니스용 Skype 서버 2015에서 TLS 1.2를 지원하는 데 일부 종속성 필수 구성이 필요하기 때문에 TLS 1.0 및 1.1이 비활성화된 모든 시스템에서 RTM 미디어에서 설치가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-300">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="8bb47-301">**환경에서 TLS 1.0 및 1.1을 사용하지 않도록 설정한 경우 새 Standard Edition Server 또는 Enterprise Edition 풀 배포**</span><span class="sxs-lookup"><span data-stu-id="8bb47-301">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="8bb47-302">**옵션 1:** [SmartSetup을 사용 합니다.](../../deploy/install/install-skype-for-business-server.md)</span><span class="sxs-lookup"><span data-stu-id="8bb47-302">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="8bb47-303">향후 CU에서 업데이트된 SQL 이진을 수용하기 위해 SmartSetup을 업데이트하고 있으며 향후 이 문서가 업데이트될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-303">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="8bb47-304">**옵션 2:** 로컬 SQL 인스턴스 사전 설치(RTCLOCAL 및 LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="8bb47-304">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="8bb47-305">FE의 로컬 폴더에 SQL Express 2014 SP2(SQLEXPR_x64.exe)를 다운로드하여 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-305">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="8bb47-306">폴더 경로 <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="8bb47-306">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="8bb47-307">PowerShell 또는 명령 프롬프트를 시작하고 <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="8bb47-307">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="8bb47-308">아래 명령을 SQL RTCLOCAL 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-308">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="8bb47-309">계속하기 SQLEXPR_x64.exe 완료될 때까지 기다렸다가 다음을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-309">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="8bb47-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="8bb47-310">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="8bb47-311">아래 명령을 SQL LYNCLOCAL 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-311">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="8bb47-312">다음 SQLEXPR_x64.exe 완료될 때까지 기다렸다가 다음 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-312">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="8bb47-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="8bb47-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="8bb47-314">비즈니스용 Skype 서버 2015 RTM 설치를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-314">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="8bb47-315">위의 선행 구성자 섹션에 있는 나머지 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-315">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="8bb47-316">**옵션 3:** 다음과 같이 로컬 설치 미디어 디렉터리의 이진 파일을 수동으로 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-316">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="8bb47-317">비즈니스용 Skype 서버의 설치 선행 준비</span><span class="sxs-lookup"><span data-stu-id="8bb47-317">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="8bb47-318">.NET 4.7을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-318">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="8bb47-319">**참고:** 먼저 비즈니스용 Skype 서버 2015 CU5(6.0.9319.281)에서 .NET 4.7에 대한 지원을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-319">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="8bb47-320">따라서 아래 이후 단계에서는 주 설치 전에 핵심 구성 요소를 업데이트할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-320">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="8bb47-321">다운로드: https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="8bb47-321">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="8bb47-322">참조: [비즈니스용 Skype 서버 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment) 배포 전에 설치해야 하는 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="8bb47-322">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="8bb47-323">ISO 파일/폴더를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-323">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="8bb47-324">비즈니스용 Skype 서버 2015 ISO가 연결된 경우 연결된 드라이브의 루트 디렉터리를 파일 탐색기에서 (예: D: 를 \) 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-324">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="8bb47-325">모든 폴더와 파일을 로컬 디스크의 폴더에 복사합니다(예: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="8bb47-325">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="8bb47-326">**참고:** 구성 요소를 설치하기 전에 일부 파일을 업데이트하여 TLS 1.2를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-326">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="8bb47-327">MSI/EXE 패키지 바꾸기:</span><span class="sxs-lookup"><span data-stu-id="8bb47-327">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="8bb47-328">로컬 컴퓨터의 설치 미디어의 /Setup/amd64/ 폴더에 있는 기존 MSI 및 EXE 패키지를 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-328">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="8bb47-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="8bb47-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="8bb47-330">이름을 SQLEXPR_x64 로컬 컴퓨터로 이름을 바꾸고 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-330">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="8bb47-331">SQL 기본 클라이언트: https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="8bb47-331">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="8bb47-332">**참고:** 필요한 경우 이름을 sqlncli.msi 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-332">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="8bb47-333">SQL 관리 개체: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="8bb47-333">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="8bb47-334">**참고:** 기능 팩에는 다운로드할 수 있는 많은 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-334">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="8bb47-335">를 선택하여 SharedManagementObjects.msi만 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-335">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="8bb47-336">**참고:** 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-336">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="8bb47-337">SQL CLR 형식: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="8bb47-337">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="8bb47-338">**참고:** 기능 팩에는 다운로드할 수 있는 많은 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-338">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="8bb47-339">Select to download CQLSysClrTypes.msi only</span><span class="sxs-lookup"><span data-stu-id="8bb47-339">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="8bb47-340">**참고:** 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-340">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="8bb47-341">핵심 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-341">Install Core Components:</span></span> 
    - <span data-ttu-id="8bb47-342">설치 Setup.exe/amd64/ 폴더에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-342">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="8bb47-343">지침에 따라 핵심 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="8bb47-343">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="8bb47-344">핵심 구성 요소를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-344">Close Core Components.</span></span>
6. <span data-ttu-id="8bb47-345">핵심 구성 요소 업데이트:</span><span class="sxs-lookup"><span data-stu-id="8bb47-345">Update Core Components:</span></span> 
    - <span data-ttu-id="8bb47-346">비즈니스용 Skype 업데이트 설치 관리자를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-346">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="8bb47-347">설치 관리자를 실행하여 핵심 구성 요소를 업데이트하고 성능 카운터를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-347">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="8bb47-348">**참고:** CU6HF2 릴리스를 현재 자동 업데이트 기능은 CU6까지만 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-348">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="8bb47-349">따라서 핵심 구성 요소를 6.0.9319.516으로 업데이트하려면 업데이트를 별도로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-349">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="8bb47-350">참조: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="8bb47-350">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="8bb47-351">관리 도구 설치(선택 사항):</span><span class="sxs-lookup"><span data-stu-id="8bb47-351">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="8bb47-352">이렇게 하면 업데이트된 파일을 사용하여 Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects(x64) 및 SQL Server 2014(x64)에 대한 Microsoft System CLR 형식이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-352">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="8bb47-353">또한 비즈니스용 Skype 서버 2015 토폴로지 작성기 및 제어판을 로컬 컴퓨터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-353">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="8bb47-354">로컬 구성 저장소 설치(1단계):</span><span class="sxs-lookup"><span data-stu-id="8bb47-354">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="8bb47-355">배포 마법사를 열고 비즈니스용 Skype 서버 시스템 설치  또는 업데이트를 클릭한 다음 1단계: 로컬 구성 저장소 설치에서 실행을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-355">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="8bb47-356">로컬 **구성 저장소** 설치 대화 **상자에서 다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-356">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="8bb47-357">![로컬 구성 저장소 설치 대화 상자](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="8bb47-357">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="8bb47-358">결과를 검토하고 작업 상태가 완료가 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-358">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="8bb47-359">로그 보기를 클릭하여 결과 로그 **파일을 검토합니다.**</span><span class="sxs-lookup"><span data-stu-id="8bb47-359">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="8bb47-360">![작업 상태가 완료로 표시](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="8bb47-360">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="8bb47-361">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-361">Click **Finish**.</span></span>
9. <span data-ttu-id="8bb47-362">비즈니스용 Skype 서버 구성 요소 설정 또는 제거(2단계):</span><span class="sxs-lookup"><span data-stu-id="8bb47-362">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="8bb47-363">배포 마법사를 열고 비즈니스용 Skype 서버 시스템  설치 또는 업데이트를 클릭한 다음 2단계: 비즈니스용 **Skype** 서버 구성 요소 설정 또는 제거에서 실행을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-363">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="8bb47-364">**비즈니스용** Skype 서버 구성 요소 설정 대화 상자에서 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-364">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="8bb47-365">![비즈니스용 Skype 서버 구성 요소 설정 창](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="8bb47-365">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="8bb47-366">로그 보기를 사용하여 로그를 검토하고 설치가 문제 없이 완료된지 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-366">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="8bb47-367">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb47-367">Click **Finish**.</span></span>
10. <span data-ttu-id="8bb47-368">필요한 경우 추가 설치 및 구성을 계속 진행합니다(이 시점에서 일반 설치 절차를 다시 시작할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="8bb47-368">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
