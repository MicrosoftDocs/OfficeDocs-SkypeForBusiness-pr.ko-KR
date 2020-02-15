---
title: 비즈니스용 Skype 서버 2015에서 TLS 1.0/1.1 사용 안 함
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
description: '요약: 환경에서 TLS 1.0 및 1.1을 준비 하 고 사용 하지 않도록 설정 합니다.'
ms.openlocfilehash: 0a25060463ed3b67db8ca523171c2bc48660293d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42012751"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="45c95-103">비즈니스용 Skype 서버 2015에서 TLS 1.0/1.1 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="45c95-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="45c95-104">이 문서의 목적은 환경에서 TLS 1.0 및 1.1을 준비 하 고 사용 하지 않도록 설정 하는 데 필요한 지침을 제공 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="45c95-105">이 프로세스에서는 광범위 한 계획 및 준비를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="45c95-106">조직에 대해 TLS 1.0 및 1.1을 사용 하지 않도록 설정 하는 계획을 수립할 때이 문서의 모든 정보를 신중 하 게 검토 하십시오.</span><span class="sxs-lookup"><span data-stu-id="45c95-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="45c95-107">TLS 1.0/1.1을 사용 하지 않도록 설정 하면 영향을 받을 수 있는 외부 종속성 및 연결 조건이 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="45c95-108">이 문서의 내용</span><span class="sxs-lookup"><span data-stu-id="45c95-108">In this article</span></span>

- [<span data-ttu-id="45c95-109">배경 및 범위</span><span class="sxs-lookup"><span data-stu-id="45c95-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="45c95-110">필수 구성 요소 및 프로세스</span><span class="sxs-lookup"><span data-stu-id="45c95-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="45c95-111">고급 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="45c95-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="45c95-112">화면</span><span class="sxs-lookup"><span data-stu-id="45c95-112">Background</span></span>

<span data-ttu-id="45c95-113">비즈니스용 Skype 서버에서 온-프레미스에 TLS 1.0 및 1.1 disable 지원을 제공 하기 위한 기본 드라이버는 PCI (결제 카드 업계) 보안 표준 Council 및 연방 정보 처리 표준 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="45c95-114">PCI 요구 사항에 대 한 자세한 내용은 [여기](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="45c95-115">Microsoft는 조직이 이러한 요구 사항을 준수 해야 하는지 여부에 대 한 지침을 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="45c95-116">환경에서 TLS 1.0 및/또는 1.1을 사용 하지 않도록 설정 하는 데 필요한 지를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="45c95-117">Microsoft는 [여기](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)에서 사용할 수 있는 백서를 제공 했으며이 [Exchange 블로그에서](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)사용할 수 있는 배경 읽기도 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="45c95-118">지원 범위</span><span class="sxs-lookup"><span data-stu-id="45c95-118">Supportability Scope</span></span>

<span data-ttu-id="45c95-119">*범위* 는 지원 가능성 경계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="45c95-120">*완벽 하 게 테스트 및 지원 됨* 은 나열 된 제품 버전에 대 한 TLS 1.0 및 1.1의 비활성화를 완벽 하 게 지원 하 고 테스트를 거쳤습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="45c95-121">*현재 조사 중인* 것은 바로 여기에 해당 하는 것입니다. 이 제품은 TLS 사용 안 함 지원에 대 한 범위를 적극적으로 조사 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="45c95-122">*범위를 벗어나* 이러한 제품 버전은 TLS 1.0 또는 1.1 사용 안 함을 지원 하지 않으며, 주의할 예외로 인해 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="45c95-123">완벽 하 게 테스트 되 고 지원 되는 서버</span><span class="sxs-lookup"><span data-stu-id="45c95-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="45c95-124">비즈니스용 Skype 서버 2019 C U 1 17.0.2046.123 (6 월 2019 일 이상)</span><span class="sxs-lookup"><span data-stu-id="45c95-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="45c95-125">Windows Server 2012 (CU9 6.0.9319.548), 2012 R2 또는 2016 [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 과 같은 비즈니스용 Skype 서버 2015 (2019 년 5 월) 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="45c95-126">Windows Server 2008 R2, 2012 (6.0.9319.548 [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 또는 대체 업데이트 포함) 또는 2012 R2에서 CU9 (2019) 이상으로, 전체 업그레이드 된 비즈니스용 Skype 서버 2015</span><span class="sxs-lookup"><span data-stu-id="45c95-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="45c95-127">Exchange Server 2010 SP3 RU19 이상에서 제공 하는 exchange 연결 및 Outlook Web App [, 지침](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="45c95-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="45c95-128">Sba (survivable Branch (SBA) for 비즈니스용 Skype 서버 2015 CU6 HF2 이상이 있거나 (공급 업체에 게 appropiate 업데이트를 패키지 했으며 사용자의 기기에 사용할 수 있게 되었는지 확인)</span><span class="sxs-lookup"><span data-stu-id="45c95-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="45c95-129">비즈니스용 Skype 서버 2015 CU6 HF2 이상이 있는 sba (survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="45c95-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="45c95-130">Lync Server 2013에 **지**역할만이는 edge 역할에 Windows Fabric 1.0에 대 한 종속성이 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="45c95-131">완벽 하 게 테스트 되 고 지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="45c95-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="45c95-132">Lync 2013 (비즈니스용 Skype) 데스크톱 클라이언트, MSI 및 C2R (기본 [15.0.5023.1000 이상](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334) 포함)</span><span class="sxs-lookup"><span data-stu-id="45c95-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="45c95-133">기본을 포함 하 여 비즈니스용 Skype 2016 데스크톱 클라이언트, MSI [16.0.4678.1000 이상](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)</span><span class="sxs-lookup"><span data-stu-id="45c95-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="45c95-134">비즈니스용 Skype 2016을 클릭 하 여 실행 [4 월 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) 업데이트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="45c95-135">매월 및 반기 대상, 16\.0\.9126\.2152 이상</span><span class="sxs-lookup"><span data-stu-id="45c95-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="45c95-136">반기 및 지연 채널, 16\.0\.8431\.2242 이상</span><span class="sxs-lookup"><span data-stu-id="45c95-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="45c95-137">Mac 용 비즈니스용 Skype 16.15 이상</span><span class="sxs-lookup"><span data-stu-id="45c95-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="45c95-138">IOS 및 Android 6.19 이상 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="45c95-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="45c95-139">Microsoft 팀 대화방 (이전에는 Skype 대화방 시스템 V2 SRS V2) 4.0.64.0 (12 월 2018) 이상</span><span class="sxs-lookup"><span data-stu-id="45c95-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="45c95-140">KB4499162 기반 Team edition에 대 한 Surface Hub update (2019, OS 빌드 15063.1835) 이상</span><span class="sxs-lookup"><span data-stu-id="45c95-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="45c95-141">Skype Web App 2015 CU6 HF2 이상 (서버와 함께 제공)</span><span class="sxs-lookup"><span data-stu-id="45c95-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="45c95-142">현재 조사 중</span><span class="sxs-lookup"><span data-stu-id="45c95-142">Currently being investigated</span></span>

- <span data-ttu-id="45c95-143">통화 품질 대시보드 (TLS 1.0, 1.1가 사용 하지 않도록 설정 된 새 설치, 아래 참조) \*</span><span class="sxs-lookup"><span data-stu-id="45c95-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="45c95-144">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="45c95-144">Out of scope</span></span>

<span data-ttu-id="45c95-145">명시 된 경우를 제외 하 고 다음 제품은 TLS 1.0/1.1 사용 안 함 지원에 대 한 범위에 포함 되지 않으며 TLS 1.0 및 1.1가 사용 되지 않도록 설정 된 환경에서는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="45c95-146">즉, 범위 외의 서버 또는 클라이언트를 계속 사용 하는 경우에는 비즈니스용 Skype 서버 온-프레미스 배포의 모든 위치에서 TLS 1.0/1.1을 해제 해야 하는 경우이를 업데이트 하거나 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="45c95-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45c95-147">Lync Server 2013</span></span>
- <span data-ttu-id="45c95-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="45c95-148">Lync Server 2010</span></span>
- <span data-ttu-id="45c95-149">Windows Server 2008 또는 낮은</span><span class="sxs-lookup"><span data-stu-id="45c95-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="45c95-150">Mac 2011용 Lync</span><span class="sxs-lookup"><span data-stu-id="45c95-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="45c95-151">모바일-iOS, iPad, Android 또는 Windows Phone 용 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="45c95-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="45c95-152">Lync "MX" Windows 스토어 클라이언트</span><span class="sxs-lookup"><span data-stu-id="45c95-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="45c95-153">Lync 대화방 시스템 (있는 경우)</span><span class="sxs-lookup"><span data-stu-id="45c95-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="45c95-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="45c95-154">SRSv1).</span></span> <span data-ttu-id="45c95-155">LRS는 2018 년 10 월 9 일에 대 한 지원 종료에 도달 했으며 TLS 1.2를 지원 하도록 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="45c95-156">모든 Lync 2010 클라이언트</span><span class="sxs-lookup"><span data-stu-id="45c95-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="45c95-157">Lync Phone Edition-업데이트 된 지침이 [여기](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="45c95-158">2013 기반 Sba (survivable Branch 기기 (SBA) 또는 Sba (survivable 분기 서버 (SBS)</span><span class="sxs-lookup"><span data-stu-id="45c95-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="45c95-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="45c95-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="45c95-160">비즈니스용 Skype for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="45c95-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="45c95-161">예외</span><span class="sxs-lookup"><span data-stu-id="45c95-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="45c95-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45c95-162">Lync Server 2013</span></span>

<span data-ttu-id="45c95-163">Lync Server 2013는 Windows Fabric 버전 1.0에 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="45c95-164">Lync Server 2013의 디자인 단계에서 Windows Fabric 1.0은 뛰어난 및 새로운 분산 아키텍처를 위해 복제, 고가용성 및 내결함성을 제공 하기 위해 선택 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="45c95-165">시간이 지남에 따라 비즈니스용 Skype 서버와 Windows Fabric이 모두 후속 버전에서 주요 다시 디자인을 통해 이러한 공동 아키텍처를 크게 개선 했습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="45c95-166">현재 비즈니스용 Skype 2015 서버는 Windows Fabric 3.0를 사용 합니다 (예:</span><span class="sxs-lookup"><span data-stu-id="45c95-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="45c95-167">아쉽게도 Windows Fabric 1.0에서는 **TLS 1.2을 지원 하지 않습니다.  그러나 TLS 1.2에서 작동 하도록 Lync Server 2013를 업데이트 합니다**.</span><span class="sxs-lookup"><span data-stu-id="45c95-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="45c95-168">이는 Lync Server 2013의 다음 누적 업데이트에서 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="45c95-169">공동 존재, 마이그레이션, 페더레이션 및 하이브리드 시나리오를 사용 하도록 TLS 1.2 지원을 제공 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="45c95-170">조직이 TLS 1.0 및 1.1을 사용 하지 않도록 설정 해야 하는 경우 현재 Lync Server 2013을 사용 하는 경우에는 전체 업그레이드 또는 병렬 마이그레이션 (새 풀, 사용자 이동)을 Skype로 마이그레이션하는 것이 가능 하도록 계획 프로세스를 시작 하는 것이 좋습니다. Business Server 2015 이상</span><span class="sxs-lookup"><span data-stu-id="45c95-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="45c95-171">또는 비즈니스용 Skype 온라인으로의 마이그레이션을 빠르게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="45c95-172">통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="45c95-172">Call Quality Dashboard</span></span>

<span data-ttu-id="45c95-173">온-프레미스 통화 품질 대시보드는 현재 온-프레미스 환경에 설치 하는 동안 새로 설치 하는 동안 TLS 1.0에 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="45c95-174">현재이 문제를 조사 중 이며 곧 수정 프로그램을 출시할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="45c95-175">CQD를 설치 하 고 TLS 1.0도 사용 하지 않도록 설정 하려는 경우에는 먼저 CQD 설치를 완료 한 후 TLS 1.0 사용 안 함을 사용 하 여 진행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="45c95-176">타사 장치</span><span class="sxs-lookup"><span data-stu-id="45c95-176">Third-party devices</span></span>

<span data-ttu-id="45c95-177">3PIP 휴대폰, 비디오 회의, 역방향 프록시 및 부하 분산 장치와 같은 타사 장치에서는 TLS 1.2 지원 가능성을 확인 하 고 신중한 테스트를 수행 하 고 필요한 경우 공급 업체에 문의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="45c95-178">에 지 서버에서 TLS 1.0/1.1을 사용 하지 않도록 설정할 때의 페더레이션 고려 사항</span><span class="sxs-lookup"><span data-stu-id="45c95-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="45c95-179">에 지 서버에서 TLS 1.0/1.1을 사용 하지 않도록 설정 하는 경우를 신중 하 게 계획 하 고 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="45c95-180">TLS 1.0 및 1.1를 사용 하지 않도록 설정 하면 다른 조직이 더 이상 조직과 페더레이션 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="45c95-181">에 지 서버에서 TLS 1.0/1.1을 사용 하도록 설정 하 여 패치가 적용 되지 않은 (SfB 2015, Lync 2013) 또는 이전 (2010) 외부 시스템에 대 한 이전 버전과의 호환성을 유지 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="45c95-182">Microsoft는에 지 네트워크 (또는 네트워크)가 PCI 표준에 속하는지 여부에 대 한 조언을 제공 하거나 권장 사항을 제공할 수 없습니다. 이는 개별 회사에서 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="45c95-183">비즈니스용 Skype Online은 현재 TLS 1.2를 사용할 수 있으므로 하이브리드/페더레이션에 대 한 영향은 온라인에서 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="45c95-184">PIC (공용 IM 연결)-Skype 소비자 서비스: [Skype 연결](../../deploy/deploy-skype-connectivity.md)에 영향을 주는 TLS 1.0/1.1을 사용 하지 않도록 설정할 예정입니다. Microsoft PIC 게이트웨이는 이미 TLS 1.2을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="45c95-185">필수 구성 요소 및 프로세스</span><span class="sxs-lookup"><span data-stu-id="45c95-185">Prerequisites and process</span></span>

<span data-ttu-id="45c95-186">위에서 언급 한 경우를 제외 하 고, TLS 1.0 및 1.1을 사용 하지 않도록 설정한 경우 클라이언트와 장치가 제대로 작동 하거나 모든 서버를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="45c95-187">이는 Microsoft의 업데이트 된 지침을 일시 중지 하 고 기다려야 할 수 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="45c95-188">모든 요구 사항을 충족 하 고 주소 차이에 대 한 계획을 수립 하는 것이 만족 되 면 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="45c95-189">높은 수준에서 비즈니스용 Skype 서버 2019는 설치 시에 절차를 준비 하 고, 비즈니스용 Skype 서버 2015에서는 CU9을 설치 하 고, .NET 및 SQL에 필수 구성 요소 업데이트를 적용 하 고, 필수 레지스트리 키를 배포 하 고, 필요에 따라 별도의 작업을 수행 해야 합니다. OS 구성 업데이트 반올림 (예: 레지스트리 파일 가져오기를 통해 TLS 1.0 및 1.1 사용 안 함)</span><span class="sxs-lookup"><span data-stu-id="45c95-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="45c95-190">환경의 모든 서버에서 TLS 1.0 및 1.1을 사용 하지 않도록 설정 하기 전에 비즈니스용 Skype 서버 2015 CU6 HF2을 포함 하 여 모든 필수 구성 요소의 설치를 완료 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="45c95-191">Edge 역할 및 SQL Backends를 비롯 한 모든 비즈니스용 Skype 서버에 업데이트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="45c95-192">또한 지원 되는 모든 클라이언트 (범위)가 필요한 최소 버전으로 업데이트 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="45c95-193">관리 워크스테이션을 업데이트 하는 것도 잊지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="45c95-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="45c95-194">비즈니스용 Skype 서버를 업그레이드 하는 데 일반적인 "내부 출력" 작업 순서를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="45c95-195">일반적인 경우와 같은 방식으로 디렉터 풀, 영구 채팅 및 페어링 된 풀을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="45c95-196">업그레이드 [순서 및 방법은](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) [여기](topology.md) 에서 다루고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="45c95-197">높은 수준의 프로세스</span><span class="sxs-lookup"><span data-stu-id="45c95-197">High-level process</span></span>

1. <span data-ttu-id="45c95-198">프로덕션 서버를 구성 하기 전에 랩에서 모든 단계를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="45c95-199">각 서버와 업데이트할 모든 개별 서버의 내보낸 레지스트리 복사본을 백업 및 보존 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="45c95-200">서버 간에는 레지스트리를 공유할 수 없습니다. 고유한 컴퓨터 기반 키를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="45c95-201">비즈니스용 Skype 2015 서버를 모두 CU9 이상으로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="45c95-202">비즈니스용 Skype 서버 2019의 경우 C U 1 이상으로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="45c95-203">모든 서버에 모든 필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="45c95-204">필수 구성 요소 레지스트리 키를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="45c95-205">모든 범위 내 클라이언트가 업데이트 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="45c95-206">레지스트리 가져오기를 통해 TLS 1.0 및 1.1을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="45c95-207">작업 부하가 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="45c95-208">문제가 발생 하면 문제를 해결 하 고 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="45c95-209">2 단계의 레지스트리를 복원 하 여 TLS 1.0 및 1.1을 다시 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="45c95-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="45c95-210">TLS 1.2만 사용 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="45c95-211">모든 서버에 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="45c95-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="45c95-212">비즈니스용 Skype 서버 2015 배포의 운영 체제 수준에서 TLS 1.0 및 1.1을 사용 하지 않도록 설정 하기 전에 광범위 한 종속성 업데이트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="45c95-213">TLS 1.2를 지원할 수 있는 최소 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="45c95-214">TLS 1.0 및 1.1을 사용 하지 않도록 설정 하기 전에 해당 환경의 모든 비즈니스용 Skype 서버에 모든 필수 업데이트를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="45c95-215">비즈니스용 Skype 서버 2015 CU9 6.0.9319.548 (2019 년 5 월) 이상</span><span class="sxs-lookup"><span data-stu-id="45c95-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="45c95-216">SchUseStrongCrypto에서 사용 하도록 설정 된 [.Net Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) 이상 (아래 제공 됨)</span><span class="sxs-lookup"><span data-stu-id="45c95-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="45c95-217">SQL은 모든 비즈니스용 Skype 2015 서버 및 backends에서 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="45c95-218">Enterprise Edition 풀 업데이트 SQL Backends 먼저 끝나고 각는 해당 FEs입니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="45c95-219">[SQL server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)이상/sql SERVER 2012 SP2 + CU16 이상/sql SERVER [2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)이상/sql server 2014 sp2</span><span class="sxs-lookup"><span data-stu-id="45c95-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="45c95-220">Sql server Native Client for SQL 서버 2012</span><span class="sxs-lookup"><span data-stu-id="45c95-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="45c95-221">[SQL Server 용 MICROSOFT ODBC Driver 11](https://www.microsoft.com/download/details.aspx?id=36434)이상</span><span class="sxs-lookup"><span data-stu-id="45c95-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="45c95-222">SQL Server 2014 SP2 용 공유 관리 개체</span><span class="sxs-lookup"><span data-stu-id="45c95-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="45c95-223">SQL server 2014 SP2에 대 한 SQLSysClrTypes</span><span class="sxs-lookup"><span data-stu-id="45c95-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="45c95-224">권장 순서 대로 사전 필수 구성 요소를 설치 하는 기본 단계</span><span class="sxs-lookup"><span data-stu-id="45c95-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="45c95-225">모든 서버에 비즈니스용 Skype 서버 CU9 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="45c95-226">업데이트 프로그램을 사용 하 여 구성 요소에 update를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="45c95-227">문서화 된 절차에 따라 데이터베이스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="45c95-228">비즈니스용 Skype 서버 2015에 대 한 자세한 내용은 [kb(3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45c95-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="45c95-229">다른 변경 내용으로 이동 하기 전에 배포에서 제품 기능의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="45c95-230">.NET 4.7 오프 라인 설치 관리자를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="45c95-231">참고할[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="45c95-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="45c95-232">프런트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중지 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="45c95-233">참고할[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="45c95-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="45c95-234">Ex (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="45c95-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="45c95-235">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="45c95-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="45c95-236">설치 관리자 패키지를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-236">Run the installer package.</span></span>
    7. <span data-ttu-id="45c95-237">서버를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-237">Reboot the server.</span></span>
3. <span data-ttu-id="45c95-238">모든 서버에서 SQL Express 2014를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="45c95-239">참고할[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="45c95-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="45c95-240">SQL 2014 SP2 다운로드</span><span class="sxs-lookup"><span data-stu-id="45c95-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="45c95-241">참고할[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="45c95-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="45c95-242">설치 미디어를 서버의 폴더에 복사 합니다 (예: C:\ 01_2014SqlSp2).</span><span class="sxs-lookup"><span data-stu-id="45c95-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="45c95-243">프런트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중지 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="45c95-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="45c95-244">Ex (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="45c95-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="45c95-245">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="45c95-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="45c95-246">관리 명령 프롬프트를 열고 설치 된 모든 구성 요소와 인스턴스를 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="45c95-247">예: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="45c95-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="45c95-248">SQL Native Client를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="45c95-249">참조: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="45c95-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="45c95-250">에서 다운로드[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="45c95-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="45c95-251">비즈니스용 Skype 서버 2015 서비스가 프런트 엔드 서버에서 중지 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="45c95-252">Ex (Standard Edition):```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="45c95-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="45c95-253">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="45c95-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="45c95-254">설치 중인 SQL 인스턴스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="45c95-255">Ex```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="45c95-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="45c95-256">Ex```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="45c95-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="45c95-257">Ex (Standard Edition에만 해당):```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="45c95-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="45c95-258">업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-258">Install the update.</span></span>
5. <span data-ttu-id="45c95-259">TLS 1.2 ( [kb(3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server))에 대 한 지원을 포함 하도록 ODBC Driver 11 For SQL Server를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="45c95-260">[ODBC Driver 11 FOR SQL Server-Windows를](https://www.microsoft.com/download/confirmation.aspx?id=36434)다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="45c95-261">프런트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중지 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="45c95-262">예 (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="45c95-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="45c95-263">예 (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="45c95-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="45c95-264">업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-264">Install the update.</span></span>
6. <span data-ttu-id="45c95-265">필수 구성 요소 레지스트리 키를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="45c95-266">필수 구성 요소 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="45c95-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="45c95-267">다음 테스트를 메모장에 복사/붙여 넣고 TLSPreReq 이름 또는 선택한 이름을 바꾼 다음 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="45c95-268">Enterprise Edition 풀에 대 한 SQL 백 엔드의 경우 필수 구성 요소 및 TLS 사용 안 함은 SQL 또는 OS 업데이트로 처리 됩니다. 다음을 참조 하세요.[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="45c95-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="45c95-269">필수 구성 요소 응용 프로그램과 TLS를 사용 하지 않도록 설정 하는 단계를 모두 결합할 수 있지만 운영 체제 수준에서 TLS 1.0 및 1.1을 사용 하지 않도록 설정 하기 전에 모든 필수 구성 요소를 적용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="45c95-270">모범 사례 방법은 모든 필수 구성 요소를 배포 하 고 해당 작업을 모든 작업이 올바르게 정상적으로 진행 하는지 확인 한 다음 나중에 TLS 1.0/1.1을 사용 하지 않도록 설정 하 여 환경을 준비 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="45c95-271">레지스트리 가져오기를 통해 TLS 1.0 및 1.1 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="45c95-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="45c95-272">다음 단계를 진행 하기 전에 *모든 필수 구성 요소를 완료 하 고 비즈니스용 Skype 서버를 업데이트 했는지 확인*합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="45c95-273">다음 텍스트를 메모장 파일에 복사 하 고 이름을 **Tlsdisable .reg**로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="45c95-274">TLS 1.0 및 1.1을 사용 하지 않도록 설정할 각 서버에서 .reg 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="45c95-275">서버를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-275">Reboot the server.</span></span> <span data-ttu-id="45c95-276">서비스가 다시 온라인 상태가 되 면 다음 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="45c95-277">Enterprise Edition 풀에 대 한 접근 방식은 OS 업데이트에 대해 수행 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="45c95-278">여기에서 TLS 1.0 및 1.1을 사용 하지 않는 것 보다 더 많은 작업을 수행 하 고 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="45c95-279">여기에는 위의 예제와 같이 암호 제품군 다시 정렬 및 일부 이전 weak 암호를 사용 하지 않도록 설정 하는 기능이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="45c95-280">이는 비즈니스용 Skype 서버에서 SCHANNEL 및 Crypto API에 대 한 이러한 변경 사항을 공식적으로 지원 하며, 이러한 변경 사항만 현재 지원 되 고 테스트를 거친 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="45c95-281">향후에는 추가 구성을 고려할 수도 있지만, 지금은 구현에서 레지스트리 가져오기 파일을 수정 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="45c95-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="45c95-282">작업 부하가 예상 대로 작동 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="45c95-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="45c95-283">사용자 환경에서 TLS 1.0 및 1.1가 사용 하지 않도록 설정 된 경우 IM & 현재 상태, P2P 통화, Enterprise Voice 등의 모든 주요 작업을 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="45c95-284">**유효성 검사 TLS 1.2만 사용 되 고 있는지 확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="45c95-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="45c95-285">보안 팀에서 비즈니스용 Skype 트래픽에 대 한 새로운 감사를 수행 하 여 이전 프로토콜이 TLS 1.0 및 1.1를 더 이상 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="45c95-286">또는 TLS 1.0 및 TLS 1.1가 사용 하지 않도록 설정 된 후 Internet Explorer를 사용 하 여 비즈니스용 Skype 서버 2015의 웹 서비스에 대 한 TLS 연결을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="45c95-287">Internet Explorer를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="45c95-288">**도구** > **인터넷 옵션**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="45c95-289">**고급** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="45c95-290">**설정**아래에서 아래쪽으로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="45c95-291">TLS 1.0, TLS 1.1 및 TLS 1.2가 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="45c95-292">SfB 2015 풀의 내부 웹 서비스 URL (정상적으로 연결 되어야 함)을 찾아봅니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="45c95-293">Internet Explorer로 돌아간 후 **TLS 1.2만 사용** 하도록 옵션을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="45c95-294">SfB 2015 풀의 내부 웹 서비스 URL을 다시 찾아봅니다 (연결 하지 않아야 함).</span><span class="sxs-lookup"><span data-stu-id="45c95-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![인터넷 옵션](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="45c95-296">고급 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="45c95-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="45c95-297">일부 종속성 필수 구성 요소는 비즈니스용 Skype Ser 2015에서 TLS 1.2을 지원 하기 위해 필요 하기 때문에, RTM 미디어에서 설치 하는 데는 TLS 1.0 및 1.1이 사용 하지 않도록 설정 된 시스템에서 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="45c95-298">**사용자 환경에서 TLS 1.0 및 1.1가 사용 하지 않도록 설정 된 경우 새 Standard Edition 서버 또는 Enterprise Edition 풀을 배포 합니다.**</span><span class="sxs-lookup"><span data-stu-id="45c95-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="45c95-299">**옵션 1:** [Smartsetup](../../deploy/install/install-skype-for-business-server.md)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="45c95-300">향후 CU에서 업데이트 된 SQL 바이너리를 수용할 수 있도록 SmartSetup을 업데이트 하 고 나중에이 문서를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="45c95-301">**옵션 2:** 로컬 SQL 인스턴스 사전 설치 (RTCLOCAL 및 LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="45c95-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="45c95-302">SQL Express 2014 SP2 (SQLEXPR_x64 .exe)를 다운로드 하 고 FE의 로컬 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="45c95-303">폴더 경로 <SQL_FOLDER_PATH>를 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="45c95-304">PowerShell 또는 명령 프롬프트를 시작 하 고 <SQL_FOLDER_PATH> 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="45c95-305">아래 명령을 실행 하 여 RTCLOCAL SQL 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="45c95-306">다음 단계를 마칠 때까지 기다렸다가 SQLEXPR_x64 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="45c95-307">SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = Install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/UPDATEENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/PSQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automati</span><span class="sxs-lookup"><span data-stu-id="45c95-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="45c95-308">아래 명령을 실행 하 여 LYNCLOCAL SQL 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="45c95-309">다음 단계를 진행 하기 전에 SQLEXPR_x64가 완료 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="45c95-310">SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = Install/FEATURES = SQLEngine, Tools/INSTANCENAME = L/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="45c95-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="45c95-311">비즈니스용 Skype 서버 2015 RTM 설치 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="45c95-312">위의 필수 구성 요소 섹션에서 남은 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="45c95-313">**옵션 3:** 로컬 설치 미디어 디렉터리에서 이진 파일을 다음과 같이 수동으로 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="45c95-314">비즈니스용 Skype 서버에 대 한 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="45c95-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="45c95-315">.NET 4.7 설치:</span><span class="sxs-lookup"><span data-stu-id="45c95-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="45c95-316">**참고:** Microsoft는 먼저 비즈니스용 Skype 서버 2015 CU5 (6.0.9319.281)에서 .NET 4.7에 대 한 지원을 도입 했습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="45c95-317">따라서 아래의 이후 단계에서는 주 설치 전에 핵심 구성 요소를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="45c95-318">다운로드: https://www.microsoft.com/download/details.aspx?id=55167</span><span class="sxs-lookup"><span data-stu-id="45c95-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="45c95-319">참조: [비즈니스용 Skype 서버 2015 배포 전에 설치 해야 하는 소프트웨어](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="45c95-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="45c95-320">ISO 파일/폴더 복사:</span><span class="sxs-lookup"><span data-stu-id="45c95-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="45c95-321">비즈니스용 Skype 서버 2015 ISO를 연결 하 고 파일 탐색기에서 해당 드라이브가 연결 된 드라이브의 루트 디렉터리 (예: D:\) )를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="45c95-322">로컬 디스크의 폴더에 모든 폴더 및 파일을 복사 합니다 (예: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="45c95-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="45c95-323">**참고:** 구성 요소를 설치 하기 전에 일부 파일을 TLS 1.2 지원을 위해 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="45c95-324">MSI/EXE 패키지 교체:</span><span class="sxs-lookup"><span data-stu-id="45c95-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="45c95-325">로컬 컴퓨터에 있는 설치 미디어의/Psetup/amd64/폴더에 있는 기존 MSI 및 EXE 패키지를 교체 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="45c95-326">SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="45c95-326">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="45c95-327">로컬 컴퓨터에서 SQLEXPR_x64으로 이름을 바꾸고 설치 미디어의 설치/amd64/폴더에 있는 기존 파일을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="45c95-328">SQL Native Client:https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="45c95-328">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="45c95-329">**참고:** 필요한 경우이 항목의 이름을 sqlncli로 바꾼 다음 설치 미디어의 설치/amd64/폴더에 있는 기존 파일을 교체 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="45c95-330">SQL 관리 개체:https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="45c95-330">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="45c95-331">**참고:** 기능 팩에는 다운로드 가능한 항목이 많이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="45c95-332">SharedManagementObjects만 다운로드 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="45c95-333">**참고:** 설치 미디어의 설치/amd64/폴더에 있는 기존 파일을 교체 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="45c95-334">SQL CLR 유형:https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="45c95-334">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="45c95-335">**참고:** 기능 팩에는 다운로드 가능한 항목이 많이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="45c95-336">CQLSysClrTypes를 다운로드 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="45c95-337">**Note**: 설치 미디어의 설치/amd64/폴더에 있는 기존 파일을 교체 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="45c95-338">핵심 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-338">Install Core Components:</span></span> 
    - <span data-ttu-id="45c95-339">설치 미디어의 설치/amd64/폴더에서 setup.exe를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="45c95-340">지침에 따라 핵심 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="45c95-341">핵심 구성 요소를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-341">Close Core Components.</span></span>
6. <span data-ttu-id="45c95-342">핵심 구성 요소 업데이트:</span><span class="sxs-lookup"><span data-stu-id="45c95-342">Update Core Components:</span></span> 
    - <span data-ttu-id="45c95-343">비즈니스용 Skype 업데이트 설치 관리자를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="45c95-344">설치 관리자를 실행 하 여 핵심 구성 요소를 업데이트 하 고 성능 카운터를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="45c95-345">**참고:** CU6HF2 출시 시에도 자동 업데이트 기능은 현재 CU6 까지만 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="45c95-346">따라서 필수 구성 요소를 6.0.9319.516으로 업데이트 하려면 해당 업데이트를 별도로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="45c95-347">참고할https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="45c95-347">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="45c95-348">관리 도구 설치 (선택 사항):</span><span class="sxs-lookup"><span data-stu-id="45c95-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="45c95-349">업데이트 된 파일을 사용 하 여 Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) 및 Microsoft System CLR 유형이 SQL Server 2014 (x64)에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="45c95-350">또한 로컬 컴퓨터에서 비즈니스용 Skype 서버 2015 토폴로지 작성기와 제어판을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="45c95-351">로컬 구성 저장소 설치 (1 단계):</span><span class="sxs-lookup"><span data-stu-id="45c95-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="45c95-352">배포 마법사를 열고 비즈니스용 Skype 서버 시스템 설치 또는 업데이트를 클릭 한 다음 1 단계: 로컬 구성 저장소 설치에서 **실행** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="45c95-353">**로컬 구성 저장소 설치** 대화 상자에서 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="45c95-354">![로컬 구성 저장소 설치 대화 상자](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="45c95-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="45c95-355">결과를 검토 하 고 작업 상태가 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="45c95-356">**로그 보기**를 클릭 하 여 결과 로그 파일을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="45c95-357">![완료 된 것으로 표시 되는 작업 상태](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="45c95-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="45c95-358">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-358">Click **Finish**.</span></span>
9. <span data-ttu-id="45c95-359">비즈니스용 Skype 서버 구성 요소를 설정 하거나 제거 합니다 (2 단계).</span><span class="sxs-lookup"><span data-stu-id="45c95-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="45c95-360">배포 마법사를 열고 **비즈니스용 Skype 서버 시스템 설치 또는 업데이트**를 클릭 한 다음 2 단계: 비즈니스용 Skype 서버 구성 요소 설정 또는 제거에서 **실행** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="45c95-361">비즈니스용 Skype 서버 구성 요소 설정 대화 상자에서 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="45c95-362">![비즈니스용 Skype 서버 구성 요소 설정 창](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="45c95-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="45c95-363">보기 로그를 사용 하 여 로그를 검토 하 고 문제가 발생 하지 않고 설치가 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="45c95-364">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45c95-364">Click **Finish**.</span></span>
10. <span data-ttu-id="45c95-365">필요에 따라 추가 설치 및 구성을 진행 합니다 (이 시점에서 일반 설치 절차를 다시 시작할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="45c95-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
