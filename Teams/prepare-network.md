---
title: Teams에 대한 조직의 네트워크 준비
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 네트워크 요구 사항, 네트워크 최적화, 대역폭 요구 사항을 포함하여 Microsoft Teams를 사용하기 위해 조직의 네트워크를 준비하는 방법을 자세히 알아봅니다.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: ff6959319a55183f33c8998adc4a4a46c640bca4
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768387"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="92216-103">Microsoft Teams를 사용하기 위한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="92216-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="92216-104">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="92216-104">Network requirements</span></span>

<span data-ttu-id="92216-105">[Microsoft 365 또는 Office 365에 대한 네트워크를 이미 최적화했다면](/Office365/Enterprise/assessing-network-connectivity) Microsoft Teams를 사용할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92216-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="92216-106">어떤 경우든, 특히 **원격 작업자** 를 지원하기 위해 첫 Microsoft 365 또는 Office 365 워크로드로서 Teams를 빠르게 배포하는 경우, Teams 배포를 시작하기 전에 다음을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="92216-107">모든 위치에서 인터넷에 액세스할 수 있나요(Microsoft 365 또는 Office 365에 연결할 수 있도록)?</span><span class="sxs-lookup"><span data-stu-id="92216-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="92216-108">최소한 일반 웹 트래픽 외에도 모든 위치에서 Teams의 미디어에 대해 다음을 열었는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="92216-109">포트</span><span class="sxs-lookup"><span data-stu-id="92216-109">Ports</span></span>     |<span data-ttu-id="92216-110">UDP 포트 <strong>3478</strong>~<strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="92216-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="92216-111">IP 주소</span><span class="sxs-lookup"><span data-stu-id="92216-111">IP addresses</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="92216-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, <strong>52.120.0.0/14</strong></span><span class="sxs-lookup"><span data-stu-id="92216-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

    > [!IMPORTANT]
    > <span data-ttu-id="92216-113">온-프레미스 또는 온라인에서 비즈니스용 Skype와 페더레이션해야 하는 경우 몇 가지 추가 DNS 레코드를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure some additional DNS records.</span></span>
    >
    >|<span data-ttu-id="92216-114">CNAME 레코드/호스트 이름</span><span class="sxs-lookup"><span data-stu-id="92216-114">CNAME Records / Host name</span></span>  |<span data-ttu-id="92216-115">TTL</span><span class="sxs-lookup"><span data-stu-id="92216-115">TTL</span></span>  |<span data-ttu-id="92216-116">주소 또는 값을 가리킴</span><span class="sxs-lookup"><span data-stu-id="92216-116">Points to address or value</span></span>  |
    >|---------|---------|---------|
    >|<span data-ttu-id="92216-117">sip</span><span class="sxs-lookup"><span data-stu-id="92216-117">sip</span></span>     |    <span data-ttu-id="92216-118">3600</span><span class="sxs-lookup"><span data-stu-id="92216-118">3600</span></span>     |    <span data-ttu-id="92216-119">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="92216-119">sipdir.online.lync.com</span></span>     |
    >|<span data-ttu-id="92216-120">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="92216-120">lyncdiscover</span></span>     |   <span data-ttu-id="92216-121">3600</span><span class="sxs-lookup"><span data-stu-id="92216-121">3600</span></span>      |    <span data-ttu-id="92216-122">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="92216-122">webdir.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="92216-123">Microsoft 365 또는 Office 365에 대한 확인된 도메인이 있나요(예: contoso.com)?</span><span class="sxs-lookup"><span data-stu-id="92216-123">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="92216-124">조직에서 Microsoft 365 또는 Office 365를 배포하지 않은 경우 [시작](/microsoft-365/admin/admin-overview/get-started-with-office-365)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-124">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="92216-125">조직에서 Microsoft 365 또는 Office 365에 대해 확인된 도메인을 추가하거나 구성하지 않은 경우 [도메인 FAQ](/microsoft-365/admin/setup/domains-faq)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-125">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="92216-126">조직에서 Exchange Online 및 SharePoint Online을 배포했나요?</span><span class="sxs-lookup"><span data-stu-id="92216-126">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="92216-127">조직에 Exchange Online이 없는 경우 [Exchange와 Microsoft Teams의 상호 작용 방법](exchange-teams-interact.md)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="92216-127">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="92216-128">조직에 SharePoint Online이 없는 경우 [SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-128">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="92216-129">이러한 네트워크 요구 사항을 충족하는지 확인했다면 [Teams를 배포](./deploy-overview.md)할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92216-129">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="92216-130">대규모 다국적 기업이거나 네트워크 제한 사항이 있음을 알고 있는 경우 Teams를 사용하기 위해 네트워크를 평가하고 최적화하는 방법을 알아보도록 계속 읽으세요.</span><span class="sxs-lookup"><span data-stu-id="92216-130">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92216-131">**교육 기관**: 조직이 교육 기관이고 SIS(학생 정보 시스템)를 사용하는 경우 Teams를 배포하기 전에 [학교 데이터 동기화를 배포](/schooldatasync/)합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-131">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="92216-132">**온-프레미스 비즈니스용 Skype 서버 실행**: 조직에서 온-프레미스 비즈니스용 Skype 서버(또는 Lync Server)를 실행하는 경우 [Azure Active Directory Connect를 구성](/skypeforbusiness/hybrid/configure-azure-ad-connect)하여 온-프레미스 디렉터리를 Microsoft 365 또는 Office 365와 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-132">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="92216-133">모범 사례: CQD 및 통화 분석을 사용하여 네트워크 모니터링</span><span class="sxs-lookup"><span data-stu-id="92216-133">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="92216-134">[CQD(통화 품질 대시보드)](turning-on-and-using-call-quality-dashboard.md)를 사용하여 Teams의 통화 및 모임의 품질을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-134">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="92216-135">CQD를 사용하면 품질, 안정성 및 사용자 환경을 세밀하게 확인하여 네트워크를 최적화하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-135">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="92216-136">CQD는 전체 패턴이 명백해질 수 있는 전체 조직에 대한 집계 원격 분석을 살펴보아 문제를 식별하고 수정을 계획하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-136">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="92216-137">또한, CQD는 전체 품질, 안정성 및 사용자 환경을 파악할 수 있는 풍부한 메트릭 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-137">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="92216-138">[통화 분석](set-up-call-analytics.md)을 사용하여 개별 사용자의 통화 및 모임 문제를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-138">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="92216-139">네트워크 최적화</span><span class="sxs-lookup"><span data-stu-id="92216-139">Network optimization</span></span>

<span data-ttu-id="92216-140">다음 작업은 선택 사항이며 특히 중소기업이거나 Microsoft 365 또는 Office 365를 이미 배포한 경우 Teams를 배포하는 데 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-140">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="92216-141">네트워크 및 Teams 성능을 최적화하거나 네트워크 제한 사항이 있는 경우 이 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-141">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="92216-142">다음의 경우 추가 네트워크 최적화를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-142">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="92216-143">Teams가 느리게 실행됩니다(대역폭이 부족할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="92216-143">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="92216-144">통화가 계속 끊깁니다(방화벽 또는 프록시 차단 때문일 수 있음).</span><span class="sxs-lookup"><span data-stu-id="92216-144">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="92216-145">통화 중 잡음이 들리고 끊기거나 음성이 로봇처럼 들립니다(지터 또는 패킷 손실일 수 있음).</span><span class="sxs-lookup"><span data-stu-id="92216-145">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="92216-146">네트워크 장애를 식별하고 수정하기 위한 지침을 비롯한 네트워크 최적화에 대한 자세한 논의는 [Microsoft 365 및 Office 365 네트워크 연결 원칙](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-146">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="92216-147"><strong>네트워크 최적화 작업</strong></span><span class="sxs-lookup"><span data-stu-id="92216-147"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="92216-148"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="92216-148"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="92216-149">네트워크 플래너</span><span class="sxs-lookup"><span data-stu-id="92216-149">Network planner</span></span></td>
<td><p><span data-ttu-id="92216-150">조직의 물리적 위치에서 대역폭 계산 및 네트워크 요구 사항을 포함하여 네트워크를 평가하는 데 도움이 필요한 경우 <a href="https://admin.teams.microsoft.com">Teams 관리 센터</a>의 <a href="/microsoftteams/network-planner">네트워크 플래너</a> 도구를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-150">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="92216-151">네트워크 세부 정보 및 Teams 사용을 제공하는 경우 네트워크 플래너는 조직에서 실제 위치에 Teams와 Cloud Voice를 배포하는데 필요한 네트워크 요구 사항을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-151">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="92216-152">예제 시나리오는 <a href="/microsoftteams/tutorial-network-planner-example">네트워크 플래너 사용 - 예제 시나리오</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-152">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="92216-153">Teams용 어드바이저</span><span class="sxs-lookup"><span data-stu-id="92216-153">Advisor for Teams</span></span></td>
<td><span data-ttu-id="92216-154"><a href="/microsoftteams/use-advisor-teams-roll-out">Teams용 어드바이저</a>는 <a href="https://admin.teams.microsoft.com">Teams 관리 센터</a>의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="92216-154"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="92216-155">Advisor for Teams(미리 보기)는 Microsoft 365 또는 Office 365 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-155">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="92216-156">외부 이름 확인</span><span class="sxs-lookup"><span data-stu-id="92216-156">External Name Resolution</span></span></td>
<td><span data-ttu-id="92216-157">Teams 클라이언트를 실행하는 모든 컴퓨터가 외부 DNS 쿼리를 확인하여 Microsoft 365 또는 Office 365에서 제공하는 서비스를 검색할 수 있고 방화벽이 액세스를 차단하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-157">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="92216-158">방화벽 포트 구성에 대한 자세한 내용은 <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 및 Office 365 URL 및 IP 범위</a>로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-158">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="92216-159">세션 지속성 유지</span><span class="sxs-lookup"><span data-stu-id="92216-159">Maintain session persistence</span></span></td>
<td><span data-ttu-id="92216-160">방화벽에서 UDP에 대해 매핑된 NAT(Network Address Translation) 주소 또는 포트를 변경하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-160">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="92216-161">NAT 풀 크기 확인</span><span class="sxs-lookup"><span data-stu-id="92216-161">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="92216-162">사용자 연결에 필요한 NAT(network address translation) 풀 크기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-162">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="92216-163">여러 사용자와 장치가 <a href="/office365/enterprise/nat-support-with-office-365">NAT(Network Address Translation) 또는 PAT(Port Address Translation)</a>를 사용하여 Microsoft 365 또는 Office 365에 액세스하는 경우, 공개적으로 라우팅할 수 있는 각 IP 주소 뒤에 숨어 있는 장치가 지원되는 수를 초과하지 않는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-163">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="92216-164">포트 소진을 방지하도록 NAT 풀에 적절한 공용 IP 주소를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-164">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="92216-165">포트 소진은 내부 사용자와 장치가 Microsoft 365 또는 Office 365 서비스에 연결할 수 없게 합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-165">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="92216-166">Microsoft 데이터 센터로 라우팅</span><span class="sxs-lookup"><span data-stu-id="92216-166">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="92216-167"><a href="/office365/enterprise/client-connectivity">가장 효율적인 Microsoft 데이터 센터로의 라우팅을 구현합니다</a>.</span><span class="sxs-lookup"><span data-stu-id="92216-167"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="92216-168">로컬 또는 국가별 송신 지점을 사용하여 최대한 효율적으로 Microsoft 네트워크에 연결할 수 있는 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-168">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="92216-169">침입 탐지 및 예방 지침</span><span class="sxs-lookup"><span data-stu-id="92216-169">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="92216-170">아웃바운드 연결에 대한 추가 보안 계층을 위해 배포된 <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">침입 탐지</a> 또는 예방 시스템(IDS/IPS)이 있는 경우 모든 Microsoft 365 또는 Office 365 URL을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-170">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="92216-171">분할 터널 VPN 구성</span><span class="sxs-lookup"><span data-stu-id="92216-171">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="92216-172">일반적으로 <a href="/windows/security/identity-protection/vpn/vpn-routing">분할 터널 VPN</a>이라고 알려진 VPN(가상 사설망)을 우회하는 Teams 트래픽에 대한 대체 경로를 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-172">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="92216-173">분할 터널링은 Microsoft 365 또는 Office 365의 트래픽이 VPN을 통과하지 않고 대신 Microsoft 365 또는 Office 365로 직접 이동함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-173">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="92216-174">VPN을 우회하면 Teams 품질에 긍정적인 영향을 미치며 VPN 장치와 조직의 네트워크의 부하가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="92216-174">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="92216-175">분할 터널 VPN을 구현하기 위해 VPN 공급업체와 협력하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-175">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="92216-176">VPN 우회를 권장하는 다른 이유:</span><span class="sxs-lookup"><span data-stu-id="92216-176">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="92216-177">일반적으로 VPN은 실시간 미디어를 지원하도록 설계되거나 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-177">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="92216-178">일부 VPN은 UDP를 지원하지 않을 수도 있습니다(Teams에 필요함).</span><span class="sxs-lookup"><span data-stu-id="92216-178">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="92216-179">또한 VPN은 이미 암호화되어 있는 미디어 트래픽 위에 추가 암호화 계층을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="92216-180">VPN 장치를 통한 헤어핀 트래픽으로 인해 Teams에 대한 연결이 효율적이지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-180">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="92216-181">QoS 구현</span><span class="sxs-lookup"><span data-stu-id="92216-181">Implement QoS</span></span></td>
<td><span data-ttu-id="92216-182"><a href="/microsoftteams/qos-in-teams">QoS(서비스 품질)를 사용하여</a> 패킷 우선순위를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-182"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="92216-183">이렇게 하면 Teams의 통화 품질이 향상될 수 있으며 통화 품질을 모니터링하고 문제를 해결하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-183">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="92216-184">QoS는 관리 네트워크의 모든 세그먼트에 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-184">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="92216-185">네트워크가 대역폭에 적절하게 프로비전된 경우에도 QoS에서는 예상하지 않은 네트워크 이벤트가 발생하면 위험을 완화합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-185">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="92216-186">QoS를 사용하여 이러한 예상치 않은 이벤트가 품질에 부정적인 영향을 주지 있도록 음성 트래픽이 우선시됩니다.</span><span class="sxs-lookup"><span data-stu-id="92216-186">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="92216-187">WiFi 최적화</span><span class="sxs-lookup"><span data-stu-id="92216-187">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="92216-188">VPN과 마찬가지로 WiFi 네트워크는 실시간 미디어를 지원하도록 설계되거나 구성되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-188">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="92216-189">Teams를 지원하기 위해 WiFi 네트워크를 계획하거나 최적화하는 것은 고품질 배포를 하기 위한 중요한 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="92216-189">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="92216-190">다음 요인들을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-190">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="92216-191">QoS 또는 WMM(WiFi 멀티미디어)를 구현하여 미디어 트래픽이 WiFi 네트워크보다 적절하게 우선되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-191">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="92216-192">WiFi 대역과 액세스 지점 배치를 계획하고 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-192">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="92216-193">2.4GHz 범위는 액세스 지점 배치에 따라 적절한 환경을 제공할 수 있지만 액세스 지점은 종종 해당 범위에서 작동하는 다른 소비자 장치의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-193">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="92216-194">5GHz 범위는 조밀한 범위 때문에 실시간 미디어에 더 적합하지만, 충분한 범위를 확보하려면 액세스 지점이 더 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-194">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="92216-195">또한 엔드포인트는 해당 범위를 지원하고 그에 따라 해당 대역을 활용하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="92216-196">이중 대역 WiFi 네트워크를 사용 중이면 대역 조정을 구현하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-196">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="92216-197"><em>대역 조정</em>은 5GHz 범위를 사용하도록 이중 대역 클라이언트에 영향을 미치기 위해 WiFi 공급업체에서 구현한 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="92216-197"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="92216-198">같은 채널의 액세스 지점이 너무 가깝게 있는 경우 신호가 겹치거나 의도치 않게 경합하여 사용자에게 좋지 않은 환경이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-198">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="92216-199">옆에 있는 액세스 포인트가 서로 겹치지 않는 채널에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="92216-200">각 무선 공급업체에는 무선 솔루션을 배포하는 것에 대한 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="92216-201">자세한 지침은 Wi-Fi 공급업체에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="92216-201">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="92216-202">대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="92216-202">Bandwidth requirements</span></span>

<span data-ttu-id="92216-203">Teams는 네트워크 조건과 상관없이 최상의 오디오, 비디오, 콘텐츠 공유 환경을 제공하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="92216-203">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="92216-204">즉, 대역폭이 부족하면 Teams에서는 비디오 품질보다 오디오 품질을 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-204">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="92216-205">대역폭이 제한되지 *않은* 경우 Teams에서는 최대 1080p 비디오 해상도, 비디오의 경우 최대 30fps, 콘텐츠의 경우 15fps, 고음질 오디오를 포함하여 미디어 품질을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="92216-205">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="92216-206">관련 항목</span><span class="sxs-lookup"><span data-stu-id="92216-206">Related Topics</span></span>

[<span data-ttu-id="92216-207">Microsoft 365 및 Office 365 네트워크 연결 원칙</span><span class="sxs-lookup"><span data-stu-id="92216-207">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="92216-208">전 세계 엔드포인트: 비즈니스용 Skype Online 및 Teams</span><span class="sxs-lookup"><span data-stu-id="92216-208">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="92216-209">Teams용 프록시 서버</span><span class="sxs-lookup"><span data-stu-id="92216-209">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="92216-210">Teams의 미디어: 모임이 간단한 이유</span><span class="sxs-lookup"><span data-stu-id="92216-210">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="92216-211">Teams의 미디어: 미디어 흐름에 대한 심층 분석</span><span class="sxs-lookup"><span data-stu-id="92216-211">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="92216-212">Teams의 ID 모델 및 인증</span><span class="sxs-lookup"><span data-stu-id="92216-212">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="92216-213">Teams를 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="92216-213">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="92216-214">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="92216-214">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
