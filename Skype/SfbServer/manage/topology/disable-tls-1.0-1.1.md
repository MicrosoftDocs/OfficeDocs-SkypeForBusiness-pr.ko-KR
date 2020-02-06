---
title: 비즈니스용 Skype 서버 2015에서 TLS 1.0/1.1 비활성화
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '요약: 사용자의 환경에서 TLS 1.0 및 1.1의 비활성화를 준비하고 구현합니다.'
ms.openlocfilehash: 691dcc170830b3efa6129d23401930fcf1c149cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817149"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="e3919-103">비즈니스용 Skype 서버 2015에서 TLS 1.0/1.1 비활성화</span><span class="sxs-lookup"><span data-stu-id="e3919-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="e3919-104">이 문서의 목적은 사용자의 환경에서 TLS 1.0 및 1.1의 비활성화를 준비하고 구현하는 데 필요한 지침을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="e3919-105">이 프로세스에는 방대한 계획 및 준비 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="e3919-106">조직에서 TLS 1.0 및 1.1를 비활성화하는 계획을 수립하면서 이 문서의 모든 정보를 주의해서 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="e3919-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="e3919-107">TLS 1.0/1.1의 비활성화로 많은 외부 종속성과 연결 조건이 영향을 받을 수 있으므로 방대한 계획과 테스트가 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="e3919-108">이 문서의 내용</span><span class="sxs-lookup"><span data-stu-id="e3919-108">In this article</span></span>

- [<span data-ttu-id="e3919-109">배경 및 범위</span><span class="sxs-lookup"><span data-stu-id="e3919-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="e3919-110">필수 구성 요소 및 프로세스</span><span class="sxs-lookup"><span data-stu-id="e3919-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="e3919-111">고급 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="e3919-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="e3919-112">배경</span><span class="sxs-lookup"><span data-stu-id="e3919-112">Background</span></span>

<span data-ttu-id="e3919-113">비즈니스용 Skype 서버 온-프레미스에 대한TSL 1.0 및 1.1 비활성화 지원을 제공하는 주요 견인 요소는 결제카드산업(PCI) 보안표준협의회와 연방 정보 처리 표준 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="e3919-114">PCI 요구 사항에 대한 자세한 내용은 [여기](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="e3919-115">Microsoft는 조직이 이러한 요구 사항 혹은 그 외의 요구 사항을 준수해야 하는지에 대한 지침은 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="e3919-116">환경에서 TLS 1.0 및/또는 1.1의 비활성화가 필요한지는 사용자가 판단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="e3919-117">Microsoft는 [여기에](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/) 사용할 수 있는 TLS에 대한 백서를 만들었으며 또한 이 [Exchange 블로그](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)에서 사용할 수 있는 배경 읽기를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="e3919-118">지원 가능성 범위</span><span class="sxs-lookup"><span data-stu-id="e3919-118">Supportability Scope</span></span>

<span data-ttu-id="e3919-119">*범위*는 지원 가능성 범위를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="e3919-120">*완벽히 테스트했고 지원되는*은 당사가 나열된 제품 버전에 대한 TLS 1.0 및 1.1의 비활성화를 완벽히 지원하고 테스트하였음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="e3919-121">*현재 조사 중*은 당사가 이들 제품을 TLS 비활성화 지원의 범위에 포함시킬지를 적극적으로 조사하고 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="e3919-122">*범위를 벗어남*은 이들 제품 버전이 TLS 1.0 혹은 1.1의 비활성화를 지원하지 않고 작동하지 않을 것임을 의미합니다(참고 예외사항 제시).</span><span class="sxs-lookup"><span data-stu-id="e3919-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="e3919-123">완벽히 테스트했고 지원되는 서버</span><span class="sxs-lookup"><span data-stu-id="e3919-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="e3919-124">비즈니스용 Skype 서버 2019 CU1 17.0.2046.123(2019년 7월) 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="e3919-125">Windows Server 2012(KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 또는 대체 업데이트), 2012 R2 또는 2016에서의 비즈니스용 Skype 서버 2015 CU9 6.0.9319.548(2019년 5월) 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="e3919-126">Windows Server 2008 R2, 2012(KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 또는 대체 업데이트) 또는 2012 R2에서 현재 실행 중인 업그레이드된 비즈니스용 Skype 서버 2015 CU9 6.0.9319.548(2019년 5월) 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="e3919-127">Exchange 연결 및 Exchange Server 2010 SP3 RU19 이상을 사용하는 Outlook 웹 앱 [여기](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)에 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="e3919-128">비즈니스용 Skype 서버 2015 CU6 HF2 이상을 사용하는 Survivable Branch Appliance(SBA)(판매자가 적정 업데이트를 패키지화했으며 어플라이언스에서도 사용할 수 있는지를 판매자와 확인하세요)</span><span class="sxs-lookup"><span data-stu-id="e3919-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="e3919-129">비즈니스용 Skype 서버 2015 CU6 HF2 이상을 사용하는 Survivable Branch Server(SBS)</span><span class="sxs-lookup"><span data-stu-id="e3919-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="e3919-130">Lync Server 2013 **Edge 역할만**, 이는 Edge 역할이 Windows Fabric 1.0에 종속되지 않았기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="e3919-131">완벽히 테스트했고 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="e3919-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="e3919-132">Lync 2013(비즈니스용 Skype) 데스크톱 클라이언트, MSI 및 C2R(기본 [15.0.5023.1000 이상을 포함)](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="e3919-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="e3919-133">비즈니스용 Skype 2016 데스크톱 클라이언트, MSI [16.0.4678.1000 이상](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)(기본 포함)</span><span class="sxs-lookup"><span data-stu-id="e3919-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="e3919-134">비즈니스용 Skype 2016를 간편 실행은 [2018년 4월](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) 업데이트를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="e3919-135">매월 그리고 반기를 대상으로 16\.0\.9126\.2152 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="e3919-136">반기 및 지연 채널, 16\.0\.8431\.2242 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="e3919-137">Mac의 비즈니스용 Skype 16.15 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="e3919-138">iOS용 비즈니스용 Skype 및 Android 6.19 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="e3919-139">Microsoft Teams Rooms(이전에는 Skype 회의실 시스템 V2 SRS V2로 알려짐) 4.0.64.0 (2018년 12월) 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="e3919-140">KB4499162 기반 Team 버전에 대한 Surface Hub 업데이트(2019년 5월, OS 빌드 15063.1835) 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="e3919-141">Skype 웹 앱 2015 CU6 HF2 이상(서버와 함께 제공)</span><span class="sxs-lookup"><span data-stu-id="e3919-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="e3919-142">현재 조사 중</span><span class="sxs-lookup"><span data-stu-id="e3919-142">Currently being investigated</span></span>

- <span data-ttu-id="e3919-143">통화 품질 대시보드(TLS 1.0, 1.1을 비활성화한 후 새로운 설치, 아래를 참조하세요)\*</span><span class="sxs-lookup"><span data-stu-id="e3919-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="e3919-144">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="e3919-144">Out of scope</span></span>

<span data-ttu-id="e3919-145">언급된 경우를 제외하고 다음의 제품은 TLS 1.0/1.1 비활성화 지원의 범위에 있지 않으므로 TLS 1.0 및 1.1이 비활성화된 환경에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="e3919-146">즉, 아직 범위를 벗어난 서버나 클라이언트를 사용하는 경우 비즈니스용 Skype 서버 온-프레미스를 배포하는 데 어디에서나 TLS 1.0/1.1을 비활성화해야 하는 경우 이들을 업데이트하거나 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="e3919-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3919-147">Lync Server 2013</span></span>
- <span data-ttu-id="e3919-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e3919-148">Lync Server 2010</span></span>
- <span data-ttu-id="e3919-149">Windows Server 2008 이하</span><span class="sxs-lookup"><span data-stu-id="e3919-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="e3919-150">Mac용 Lync 2011</span><span class="sxs-lookup"><span data-stu-id="e3919-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="e3919-151">모바일용 Lync 2013 - iOS, iPad, Android 또는 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="e3919-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="e3919-152">Lync "MX" Windows Store 클라이언트</span><span class="sxs-lookup"><span data-stu-id="e3919-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="e3919-153">Lync 채팅방 시스템(a.k.a.</span><span class="sxs-lookup"><span data-stu-id="e3919-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="e3919-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="e3919-154">SRSv1).</span></span> <span data-ttu-id="e3919-155">LRS이 2018년 10월 9일에 지원을 종료했으며 TLS 1.2를 지원하도록 업데이트되지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="e3919-156">모든 Lync 2010 클라이언트</span><span class="sxs-lookup"><span data-stu-id="e3919-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="e3919-157">Lync Phone Edition- [여기에](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035) 업데이트된 지침서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="e3919-158">2013 기반 Survivable Branch Appliance(SBA) 혹은 Survivable Branch Server(SBS)</span><span class="sxs-lookup"><span data-stu-id="e3919-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="e3919-159">Cloud Connector Edition(CCE)</span><span class="sxs-lookup"><span data-stu-id="e3919-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="e3919-160">Windows Phone용 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="e3919-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="e3919-161">예외</span><span class="sxs-lookup"><span data-stu-id="e3919-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="e3919-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3919-162">Lync Server 2013</span></span>

<span data-ttu-id="e3919-163">Lync Server 2013는 Windows Fabric 버전 1.0에 종속되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="e3919-164">Lync Server 2013의 설계 단계에서 복제, 고가용성 및 내결함성을 제공하기 위해 Windows Fabric 1.0이 그 강력하고 새로운 배포 아키텍처로 인해 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="e3919-165">시간이 지나면서 비즈니스용 Skype 서버와 Windows Fabric이 모두 이후 버전에서 중요한 재설계를 통해 이 공동 아키텍처를 크게 개선시켰습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="e3919-166">예를 들어 현재 비즈니스용 Skype 서버 2015는 Windows Fabric 3.0을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="e3919-167">아쉽게도 Windows Fabric 1.0는 **TLS 1.2를 지원하지 않습니다. 그러나 TLS 1.2와 작동하도록 당사는 Lync Server 2013를 업데이트할 것입니다**.</span><span class="sxs-lookup"><span data-stu-id="e3919-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="e3919-168">업데이트는 Lync Server 2013의 다음 누적 업데이트에서 제공될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="e3919-169">공동 존재, 마이그레이션, 페더레이션 및 하이브리드 시나리오를 사용하기 위해 TLS 1.2 지원을 제공하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="e3919-170">조직에서 TLS 1.0 및 1.1을 비활성화해야 하고 현재 Lync Server 2013를 사용하고 있는 경우, 업그레이드를 준비하거나 또는 병렬로 비즈니스용 Skype 서버 2015 이상으로 마이그레이션(새로운 풀, 사용자 이동)을 해야할 가능성을 염두에 두고 계획 프로세스를 시작할 것을 권장합니다. </span><span class="sxs-lookup"><span data-stu-id="e3919-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="e3919-171">또는 비즈니스용 Skype Online으로의 마이그레이션을 신속히 진행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="e3919-172">통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="e3919-172">Call Quality Dashboard</span></span>

<span data-ttu-id="e3919-173">온-프레미스 통화 품질 대시보드는 현재 새로 설치하는 동안 TLS 1.0에 종속성을 가지고 있습니다(사용자의 온-프레미스 환경에 최초 설치).</span><span class="sxs-lookup"><span data-stu-id="e3919-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="e3919-174">현재 이 문제를 조사 중이며 가까운 장래에 픽스를 릴리스할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="e3919-175">CQD를 설치하고 또한 TLS 1.0을 비활성화하려는 경우에는 먼저 CQD 설치를 완료한 다음 TLS 1.0 비활성화를 진행할 것을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="e3919-176">타사 장치</span><span class="sxs-lookup"><span data-stu-id="e3919-176">Third-party devices</span></span>

<span data-ttu-id="e3919-177">3PIP 휴대폰, 비디오 회의, 역방향 프록시 및 부하 분산 장치와 같은 타사 장치에서 TLS 1.2 지원 가능성을 확인하고 신중하게 테스트하며 필요한 경우 판매자에게 문의하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="e3919-178">Edge 서버에서 TLS 1.0/1.1을 비활성화할 때의 페더레이션 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e3919-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="e3919-179">Edge 서버에서 TLS 1.0/1.1의 비활성화를 신중하게 계획하고 그 영향을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="e3919-180">TLS 1.0 및 1.1이 비활성화되면 다른 조직이 사용자의 조직과 더 이상 페더레이션을 할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="e3919-181">Edge 서버에서 TLS 1.0/1.1을 사용할 수 있도록 선택하여 패치가 없는(SfB 2015, Lync 2013) 또는 이전의(2010) 외부 시스템과 하위 호환성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="e3919-182">Microsoft는 Edge 네트워크(또는 네트워크)가 PCI 표준에 속하는지에 대한 조언이나 권고를 제공할 수 없으며 이는 개별 회사에서 판단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="e3919-183">비즈니스용 Skype Online은 현재 TLS 1.2를 사용할 수 있으므로, 하이브리드/페더레이션에 영향을 주지 않을 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="e3919-184">PIC(공용 IM 연결)를 Skype 소비자 서비스로의 연결: TLS 1.0/1.1의 비활성화가 [Skype 연결성](../../deploy/deploy-skype-connectivity.md)에 영향을 주지 않을 것으로 예상됩니다. Microsoft PIC Gateway는 이미 TLS 1.2를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="e3919-185">필수 구성 요소 및 프로세스</span><span class="sxs-lookup"><span data-stu-id="e3919-185">Prerequisites and process</span></span>

<span data-ttu-id="e3919-186">위에서 설명한 경우를 제외하고 TLS 1.0 및 1.1이 서버의 범위를 벗어나 비활성화가 되면 클라이언트와 장치가 제대로 작동하지 않거나 전혀 작동하지 않게됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="e3919-187">이는 잠시 진행을 멈추고 Microsoft에서 제공하는 업데이트된 지침을 기다려야함을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="e3919-188">모든 요구 사항을 충족하고 격차를 해결할 계획이 있다면 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="e3919-189">높은 수준에서 비즈니스용 Skype 서버 2019는설치 시 절차가 준비되어 있지만 비즈니스용 Skype 서버 2015는 CU9를 설치하고 .NET 및 SQL에 필수 업데이트의 적용 및 필수 레지스트리 키의 배포 그리고 마지막으로 별도의 OS 구성 업데이트 라운드를(즉, 레지스트리 파일 가져오기를 통해 TLS 1.0 및 1.1 비활성화) 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="e3919-190">사용자 환경의 모든 서버에서 TLS 1.0 및 1.1을 비활성화하기 전에 비즈니스용 Skype 서버 2015 CU6 HF2를 포함하여 모든 필수 구성 요소를 설치하는 것은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="e3919-191">Edge 역할 및 SQL Backends을 비롯한 모든 비즈니스용 Skype 서버에 업데이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="e3919-192">또한 모든 지원되는(범위 내의) 클라이언트가 필수 최소 버전으로 업데이트되어 있는지도 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="e3919-193">관리 워크스테이션을 업데이트하는 것도 잊지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="e3919-194">당사는 비즈니스용 Skype 서버를 업그레이드하는 데 "인사이드 아웃" 작업의 일반적인 순서를 따르고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="e3919-195">평소와 같은 방식으로 디렉터 풀, 영구적 채팅 및 페어링된 풀을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="e3919-196">업그레이드를 위한 순서와 방법에 대한 내용은 [여기](topology.md)와 [여기](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="e3919-197">고급 프로세스</span><span class="sxs-lookup"><span data-stu-id="e3919-197">High-level process</span></span>

1. <span data-ttu-id="e3919-198">프로덕션 서버를 구성하기 전에 랩에서 모든 단계를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="e3919-199">업데이트되는 개별 서버마다 그리고 각각의 내보낸 레지스트리를 백업하고 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="e3919-200">서버 간에는 레지스트리를 공유할 수 없습니다. 고유한 컴퓨터 기반의 키를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="e3919-201">모든 비즈니스용 Skype 서버 2015를 CU9 이상으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="e3919-202">비즈니스용 Skype 서버 2019의 경우 CU1 이상으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="e3919-203">모든 서버에 모든 필수 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="e3919-204">필수 구성 요소 레지스트리 키를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="e3919-205">모든 범위에 있는 클라이언트가 업데이트되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="e3919-206">레지스트리 가져오기를 통해 TLS 1.0 및 1.1을 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="e3919-207">워크로드가 예상대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="e3919-208">문제가 발생할 경우 문제를 문제 해결을 진행하여 해결하고 또는</span><span class="sxs-lookup"><span data-stu-id="e3919-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="e3919-209">2 단계에서 레지스트리를 복원하여 TLS 1.0 및 1.1을 다시 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="e3919-210">TLS 1.2만 사용 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="e3919-211">모든 서버에 모든 필수 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="e3919-212">비즈니스용 Skype 서버 2015 배포 시 운영 체제 수준에서 TLS 1.0 및 1.1의 비활성화를 시작하기 전에 방대한 종속성 업데이트를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="e3919-213">TLS 1.2를 지원할 수 있는 최소 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="e3919-214">TLS 1.0 및 1.1의 비활성화를 시작하기 전에 사용자 환경에서 모든 비즈니스용 Skype 서버에 모든 필수 업데이트를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="e3919-215">비즈니스용 Skype 서버 2015 CU9 6.0.9319.548(2019년 5월) 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="e3919-216">레지스트리에서 SchUseStrongCrypto를 사용하도록 설정한 경우(아래에서 제공) [.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="e3919-217">모든 비즈니스용 Skype 2015 서버 및 백엔드에서 SQL을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="e3919-218">Enterprise Edition Pool SQL 백엔드를 먼저 업데이트하고 해당 FEs를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="e3919-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), 이상/SQL Server 2012 SP2 + CU16 이상/[SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), 이상/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="e3919-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="e3919-220">SQL Server 2012용 SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e3919-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="e3919-221">[SQL Server용 Microsoft ODBC Driver 11](https://www.microsoft.com/download/details.aspx?id=36434), 이상</span><span class="sxs-lookup"><span data-stu-id="e3919-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="e3919-222">SQL Server 2014 SP2용 공유 관리 개체</span><span class="sxs-lookup"><span data-stu-id="e3919-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="e3919-223">SQL server 2014 SP2용 SQLSysClrTypes</span><span class="sxs-lookup"><span data-stu-id="e3919-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="e3919-224">권장되는 작업 순서대로 사전 필수 구성 요소를 설치하는 기본 단계</span><span class="sxs-lookup"><span data-stu-id="e3919-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="e3919-225">모든 서버에 비즈니스용 Skype 서버 CU9 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="e3919-226">업데이트기를 사용하여 구성 요소에 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="e3919-227">문서화된 절차에 따라 데이터베이스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="e3919-228">비즈니스용 Skype 서버 2015의 경우 KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)를 참조합니다. </span><span class="sxs-lookup"><span data-stu-id="e3919-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="e3919-229">다른 변경 사항을 진행하기 전에 배포 시 제품 기능에 대한 유효성 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="e3919-230">.NET 4.7 설치 관리자를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="e3919-231">참조: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="e3919-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="e3919-232">프론트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중단되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="e3919-233">참조: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="e3919-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="e3919-234">예 (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="e3919-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="e3919-235">예 (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e3919-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="e3919-236">설치 관리자 패키지를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-236">Run the installer package.</span></span>
    7. <span data-ttu-id="e3919-237">서버를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-237">Reboot the server.</span></span>
3. <span data-ttu-id="e3919-238">모든 서버에서 SQL Express 2014를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="e3919-239">참조: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="e3919-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="e3919-240">SQL 2014 SP2를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="e3919-241">참조: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="e3919-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="e3919-242">서버에 있는 폴더에 설치 미디어를 복사합니다(예: C:\ 01_2014SqlSp2).</span><span class="sxs-lookup"><span data-stu-id="e3919-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="e3919-243">프론트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중단되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="e3919-244">예 (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="e3919-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="e3919-245">예 (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e3919-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="e3919-246">관리 명령 프롬프트를 열고 설치한 모든 구성 요소와 인스턴스를 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="e3919-247">예: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="e3919-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="e3919-248">SQL Native Client를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="e3919-249">참조: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="e3919-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="e3919-250">[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)에서 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="e3919-251">프론트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중단되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="e3919-252">예 (Standard Edition): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="e3919-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="e3919-253">예 (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e3919-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="e3919-254">설치된 SQL 인스턴스의 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="e3919-255">예: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="e3919-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="e3919-256">예: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="e3919-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="e3919-257">예 (Standard Edition만): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="e3919-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="e3919-258">업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-258">Install the update.</span></span>
5. <span data-ttu-id="e3919-259">TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server))에 대한 지원을 포함 하도록 SQL Server용 ODBC Driver 11을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="e3919-260">[SQL Server용 ODBC 드라이버 11 - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="e3919-261">프론트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중단되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="e3919-262">예 (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="e3919-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="e3919-263">예 (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e3919-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="e3919-264">업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-264">Install the update.</span></span>
6. <span data-ttu-id="e3919-265">필수 구성 요소 레지스트리 키를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="e3919-266">필수 구성 요소 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="e3919-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="e3919-267">다음의 테스트를 복사하여 메모장에 붙여 넣고 TLSPreReq 또는 원하는 이름으로 바꾼 다음 가져오기를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="e3919-268">Enterprise Edition 풀에 대한 SQL 백엔드의 경우 필수 구성 요소 및 TLS의 비활성화는 SQL 또는 OS 업데이트와 같이 처리해야 합니다. 참고: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="e3919-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="e3919-269">필수 구성 요소 응용 프로그램과 TLS 비활성화 단계는 결합될 수 있지만 운영 체제 수준에서 TLS 1.0 및 1.1의 비활성화를 진행하기 전에 모든 필수 구성 요소를 적용할 것을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="e3919-270">최상의 방법은 모든 필수 구성 요소를 배포하고 모든 작업이 제대로 수행되었는지 확인한 후 나중에 TLS 1.0/1.1의 비활성화를 진행하여 환경을 준비하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="e3919-271">레지스트리 가져오기를 통해 TLS 1.0 및 1.1을 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="e3919-272">다음 단계를 진행하기 전에 *모든 필수 구성 요소를 완료하였고 비즈니스용 Skype 서버를 업데이트했는지를 확인합니다*.</span><span class="sxs-lookup"><span data-stu-id="e3919-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="e3919-273">다음의 텍스트를 메모장 파일에 복사하고 **TLSDisable.reg**로 파일의 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="e3919-274">TLS 1.0 및 1.1을 비활성화하려는 각 서버에서 .reg 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="e3919-275">서버를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-275">Reboot the server.</span></span> <span data-ttu-id="e3919-276">서비스가 다시 온라인 상태가 되면 다음 서버로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="e3919-277">Enterprise Edition 풀에 대한 접근 방법은 OS 업데이트에 대해 수행하는 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="e3919-278">여기에서 TLS 1.0 및 1.1의 비활성화 보다 더 많은 작업을 수행하고 있음을 확인하셨을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="e3919-279">당사는 암호 제품군 재정렬(위에 설명한 대로) 및 일부 오래된 weak 암호의 비활성화를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="e3919-280">이번이 당사가 비즈니스용 Skype 서버에서 SCHANNEL 및 Crypto API에 대한 이러한 변경 사항을 공식으로 지원하는 최초 지원이며 이들 변경 사항만이 현재 당사가 지원하 고 테스트를 거친 사항임을 참고하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="e3919-281">차후에 추가 구성을 고려할 수도 있지만 지금으로서는 구현 시 레지스트리 가져오기 파일을 수정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e3919-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="e3919-282">워크로드가 예상대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="e3919-283">환경에서 TLS 1.0 및 1.1가 비활성화된 후에는 IM & 현재 상태, P2P 통화, Enterprise Voice 등과 같은 모든 주요 워크로드가 예상 대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="e3919-284">**TLS 1.2만 사용 중인지 확인합니다**.</span><span class="sxs-lookup"><span data-stu-id="e3919-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="e3919-285">보안 팀이 비즈니스용 Skype에 대한 새로운 감사를 수행하여 이전 프로토콜 TLS 1.0 및 1.1가 더 이상 사용되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="e3919-286">또는 TLS 1.0 및 TLS 1.1를 비활성화한 후 Internet Explorer를 사용하여 비즈니스용 Skype 서버 2015에서 웹 서비스로의 TLS 연결을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="e3919-287">Internet Explorer를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="e3919-288">**도구** > **인터넷 옵션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="e3919-289">**고급** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="e3919-290">**설정**에서 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="e3919-291">TLS 1.0, TLS 1.1 및 TLS 1.2이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="e3919-292">SfB 2015 풀의 내부 웹 서비스 URL을 검색합니다(제대로 연결되어야 함).</span><span class="sxs-lookup"><span data-stu-id="e3919-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="e3919-293">다시 Internet Explorer로 돌아가 **TLS 1.2만 사용** 옵션을 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="e3919-294">SfB 2015 풀의 내부 웹 서비스 URL을 다시 검색합니다(연결되지 않아야 함).</span><span class="sxs-lookup"><span data-stu-id="e3919-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![인터넷 옵션](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="e3919-296">고급 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="e3919-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="e3919-297">일부 종속성 필수 구성 요소가 비즈니스용 Skype Ser 2015에서 TLS 1.2를 지원하는데 필요하므로 RTM 미디어에서 TLS 1.0과 1.1가 해제된 시스템에 설치 시 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="e3919-298">**환경에서 TLS 1.0 및 1.1이 비활성화된 경우 새 Standard Edition 서버나 Enterprise Edition 풀 배포.**</span><span class="sxs-lookup"><span data-stu-id="e3919-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="e3919-299">**옵션 1:**[SmartSetup](../../deploy/install/install-skype-for-business-server.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="e3919-300">당사는 향후 CU에서 업데이트된 SQL 바이너리를 수용할 수 있는 SmartSetup을 업데이트하고 있으며 향후에 이 문서를 업데이트할 것임을 참고하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="e3919-301">**옵션 2:** 로컬 SQL 인스턴스를 사전 설치(RTCLOCAL 및 LLYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="e3919-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="e3919-302">SQL Express 2014 SP2(SQLEXPR_x64.exe)를 다운로드하고 FE의 로컬 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="e3919-303">폴더 경로가 <SQL_FOLDER_PATH>라고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="e3919-304">PowerShell 또는 명령 프롬프트를 시작하고 <SQL_FOLDER_PATH>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="e3919-305">아래 명령을 실행하여 RTCLOCAL SQL 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="e3919-306">진행하기 전에 SQLEXPR_x64.exe가 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="e3919-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="e3919-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="e3919-308">아래 명령을 실행하여 RTCLOCAL SQL 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="e3919-309">다음 단계로 넘어가기 전에 SQLEXPR_x64.exe가 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="e3919-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="e3919-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="e3919-311">비즈니스용 Skype 서버 2015 RTM 설치를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="e3919-312">위의 필수 구성 요소 섹션에서 나머지 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="e3919-313">**옵션 3:** 로컬 설치 미디어 디렉터리에서 바이너리를 다음과 같이 수동으로 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="e3919-314">비즈니스용 Skype 서버 및 Exchange 서버의 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="e3919-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="e3919-315">.NET 4.7를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="e3919-316">**참고:** 처음에는 비즈니스용 Skype 서버 2015 CU5 (6.0.9319.281)에서 .NET 4.7에 대한 지원을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="e3919-317">따라서 아래 단계에서는 주 설치 이전의 핵심 구성 요소를 업데이트할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="e3919-318">다운로드: https://www.microsoft.com/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="e3919-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="e3919-319">참고: [비즈니스용 Skype 서버 2015 배포 이전에 설치해야 하는 소프트웨어](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="e3919-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="e3919-320">ISO 파일/폴더를 복사.</span><span class="sxs-lookup"><span data-stu-id="e3919-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="e3919-321">비즈니스용 Skype 서버 2015 ISO를 첨부한 상태에서 드라이브의 루트 디렉터리를 첨부된 대로 엽니다(예: D: 파일 탐색기의 \).</span><span class="sxs-lookup"><span data-stu-id="e3919-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="e3919-322">모든 폴더와 파일을 로컬 디스크의 폴더(예: C:\SkypeForBusiness2015ISO)로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="e3919-323">**참고**: 구성 요소를 설치하기 전에 TLS 1.2를 지원하기 위해 일부 파일을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="e3919-324">MSI/EXE 패키지 대체.</span><span class="sxs-lookup"><span data-stu-id="e3919-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="e3919-325">로컬 컴퓨터의 설치 미디어의 /Setup/amd64/ 폴더의 기존 MSI 및 EXE 패키지를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="e3919-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="e3919-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="e3919-327">로컬 컴퓨터에서 SQLEXPR_x64으로 이름을 변경하고 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="e3919-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="e3919-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="e3919-329">**참고**: 필요한 경우 sqlncli.msi로 이름을 변경한 다음 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="e3919-330">SQL 관리 개체: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="e3919-330">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="e3919-331">**참고:** 기능 팩은 다운로드 가능한 많은 항목을 포함할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="e3919-332">SharedManagementObjects.msi만 다운로드하록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="e3919-333">**참고**: 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="e3919-334">SQL CLR 유형: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="e3919-334">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="e3919-335">**참고:** 기능 팩은 다운로드 가능한 많은 항목을 포함할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="e3919-336">CQLSysClrTypes.msi만 다운로드하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="e3919-337">**참고**: 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="e3919-338">핵심 구성 요소 설치.</span><span class="sxs-lookup"><span data-stu-id="e3919-338">Install Core Components:</span></span> 
    - <span data-ttu-id="e3919-339">설치 미디어의 Setup/amd64/ 폴더에서 Setup.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="e3919-340">지침에 따라 핵심 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="e3919-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="e3919-341">핵심 구성 요소를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-341">Close Core Components.</span></span>
6. <span data-ttu-id="e3919-342">핵심 구성 요소를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-342">Update Core Components:</span></span> 
    - <span data-ttu-id="e3919-343">비즈니스용 Skype 업데이트 설치 관리자를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="e3919-344">설치 관리자를 실행하여 핵심 구성 요소를 업데이트하고 성능 카운터를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="e3919-345">**참고:** CU6HF2 릴리스의 자동 업데이트 기능은 현재 CU6까지만 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="e3919-346">따라서 6.0.9319.516에 핵심 구성 요소를 업데이트하려면 업데이트기를 별도로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="e3919-347">참조: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="e3919-347">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="e3919-348">관리 도구 설치(선택 사항):</span><span class="sxs-lookup"><span data-stu-id="e3919-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="e3919-349">업데이트된 파일을 사용하여 Microsoft SQL Server 2012 Native Client, SQL server 2014 관리 개체(x64) 및 SQL 2014 Server(x64)용Microsoft System CLR 유형을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="e3919-350">추가로 비즈니스용 Skype 서버 2015 토폴로지 작성기와 제어판을 로컬 컴퓨터에서 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="e3919-351">로컬 구성 저장소 설치(1단계):</span><span class="sxs-lookup"><span data-stu-id="e3919-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="e3919-352">배포 마법사를 열고 설치 혹은 비즈니스 서버 시스템용 비즈니스용 Skype 업데이트를 클릭한 다음 1단계, 로컬 구성 저장소 설치에서 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="e3919-353">**로컬 구성 저장소 설치** 대화 상자에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="e3919-354">![로컬 구성 저장소 대화 상자 설치](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="e3919-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="e3919-355">결과를 검토하고 작업 상태가 완료로 되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="e3919-356">**로그 보기**를 클릭하여 결과 로그 파일을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="e3919-357">![완료로 표시되는 작업 상태](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="e3919-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="e3919-358">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-358">Click **Finish**.</span></span>
9. <span data-ttu-id="e3919-359">비즈니스용 Skype 서버 구성 요소 설치 또는 제거(2단계):</span><span class="sxs-lookup"><span data-stu-id="e3919-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="e3919-360">배포 마법사를 열고 **비즈니스용 Skype 서버 시스템 설치 혹은 업데이트**를 클릭하고 2단계, 비즈니스용 Skype 서버 구성 요소 설치 혹은 제거에서 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="e3919-361">비즈니스용 Skype 서버 구성 요소 설정 대화 상자에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="e3919-362">![비즈니스용 Skype 서버 구성 요소 설치 창](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="e3919-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="e3919-363">로그 보기를 사용하여 로그를 검토하고 설치가 문제없이 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="e3919-364">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3919-364">Click **Finish**.</span></span>
10. <span data-ttu-id="e3919-365">필요에 따라 추가 설치 및 구성 작업을 진행 합니다(이 시점에서 일반 설치 절차를 다시 시작할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="e3919-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
