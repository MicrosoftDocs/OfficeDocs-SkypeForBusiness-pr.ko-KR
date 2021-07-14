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
ms.openlocfilehash: db911db3631caebb0e767401f80c36bdac6c9c1b
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420833"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="7d2e9-103">Microsoft Teams를 사용하기 위한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="7d2e9-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="7d2e9-104">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d2e9-104">Network requirements</span></span>

<span data-ttu-id="7d2e9-105">[Microsoft 365 또는 Office 365에 대한 네트워크를 이미 최적화했다면](/Office365/Enterprise/assessing-network-connectivity) Microsoft Teams를 사용할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="7d2e9-106">어떤 경우든, 특히 **원격 작업자** 를 지원하기 위해 첫 Microsoft 365 또는 Office 365 워크로드로서 Teams를 빠르게 배포하는 경우, Teams 배포를 시작하기 전에 다음을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="7d2e9-107">모든 위치에서 인터넷에 액세스할 수 있나요(Microsoft 365 또는 Office 365에 연결할 수 있도록)?</span><span class="sxs-lookup"><span data-stu-id="7d2e9-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="7d2e9-108">일반적인 웹 트래픽 외에도 [Office 365 URL 및 IP 주소 범위](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)에 있는 Teams에 대해 나열된 TCP 포트와 IP 주소를 열었는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-108">In addition to normal web traffic, make sure you've opened the TCP ports and IP addresses listed for Teams in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7d2e9-109">온-프레미스 또는 온라인에서 비즈니스용 Skype와 페더레이션해야 하는 경우 추가 DNS 레코드를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-109">If you need to federate with Skype for Business, either on-premises or online, you will need to configure an additional DNS record.</span></span>
    >
    >|<span data-ttu-id="7d2e9-110">DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="7d2e9-110">DNS record</span></span>  |<span data-ttu-id="7d2e9-111">서비스</span><span class="sxs-lookup"><span data-stu-id="7d2e9-111">Service</span></span>  |<span data-ttu-id="7d2e9-112">프로토콜</span><span class="sxs-lookup"><span data-stu-id="7d2e9-112">Protocol</span></span>  |<span data-ttu-id="7d2e9-113">우선 순위</span><span class="sxs-lookup"><span data-stu-id="7d2e9-113">Priority</span></span>  |<span data-ttu-id="7d2e9-114">가중치</span><span class="sxs-lookup"><span data-stu-id="7d2e9-114">Weight</span></span>  |<span data-ttu-id="7d2e9-115">포트</span><span class="sxs-lookup"><span data-stu-id="7d2e9-115">Port</span></span>  |<span data-ttu-id="7d2e9-116">대상</span><span class="sxs-lookup"><span data-stu-id="7d2e9-116">Target</span></span>  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|<span data-ttu-id="7d2e9-117">SRV</span><span class="sxs-lookup"><span data-stu-id="7d2e9-117">SRV</span></span>     |<span data-ttu-id="7d2e9-118">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7d2e9-118">sipfederationtls</span></span>     |<span data-ttu-id="7d2e9-119">TCP</span><span class="sxs-lookup"><span data-stu-id="7d2e9-119">TCP</span></span>     |<span data-ttu-id="7d2e9-120">100</span><span class="sxs-lookup"><span data-stu-id="7d2e9-120">100</span></span>     |<span data-ttu-id="7d2e9-121">1</span><span class="sxs-lookup"><span data-stu-id="7d2e9-121">1</span></span>     |<span data-ttu-id="7d2e9-122">5061</span><span class="sxs-lookup"><span data-stu-id="7d2e9-122">5061</span></span>     |<span data-ttu-id="7d2e9-123">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7d2e9-123">sipfed.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="7d2e9-124">Microsoft 365 또는 Office 365에 대한 확인된 도메인이 있나요(예: contoso.com)?</span><span class="sxs-lookup"><span data-stu-id="7d2e9-124">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="7d2e9-125">조직에서 Microsoft 365 또는 Office 365를 배포하지 않은 경우 [시작](/microsoft-365/admin/admin-overview/get-started-with-office-365)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-125">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="7d2e9-126">조직에서 Microsoft 365 또는 Office 365에 대해 확인된 도메인을 추가하거나 구성하지 않은 경우 [도메인 FAQ](/microsoft-365/admin/setup/domains-faq)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-126">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="7d2e9-127">조직에서 Exchange Online 및 SharePoint Online을 배포했나요?</span><span class="sxs-lookup"><span data-stu-id="7d2e9-127">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="7d2e9-128">조직에 Exchange Online이 없는 경우 [Exchange와 Microsoft Teams의 상호 작용 방법](exchange-teams-interact.md)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="7d2e9-128">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="7d2e9-129">조직에 SharePoint Online이 없는 경우 [SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-129">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="7d2e9-130">이러한 네트워크 요구 사항을 충족하는지 확인했다면 [Teams를 배포](./deploy-overview.md)할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-130">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="7d2e9-131">대규모 다국적 기업이거나 네트워크 제한 사항이 있음을 알고 있는 경우 Teams를 사용하기 위해 네트워크를 평가하고 최적화하는 방법을 알아보도록 계속 읽으세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-131">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d2e9-132">**교육 기관**: 조직이 교육 기관이고 SIS(학생 정보 시스템)를 사용하는 경우 Teams를 배포하기 전에 [학교 데이터 동기화를 배포](/schooldatasync/)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-132">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="7d2e9-133">**온-프레미스 비즈니스용 Skype 서버 실행**: 조직에서 온-프레미스 비즈니스용 Skype 서버(또는 Lync Server)를 실행하는 경우 [Azure Active Directory Connect를 구성](/skypeforbusiness/hybrid/configure-azure-ad-connect)하여 온-프레미스 디렉터리를 Microsoft 365 또는 Office 365와 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-133">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="7d2e9-134">모범 사례: CQD 및 통화 분석을 사용하여 네트워크 모니터링</span><span class="sxs-lookup"><span data-stu-id="7d2e9-134">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="7d2e9-135">[CQD(통화 품질 대시보드)](turning-on-and-using-call-quality-dashboard.md)를 사용하여 Teams의 통화 및 모임의 품질을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-135">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="7d2e9-136">CQD를 사용하면 품질, 안정성 및 사용자 환경을 세밀하게 확인하여 네트워크를 최적화하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-136">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="7d2e9-137">CQD는 전체 패턴이 명백해질 수 있는 전체 조직에 대한 집계 원격 분석을 살펴보아 문제를 식별하고 수정을 계획하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-137">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="7d2e9-138">또한, CQD는 전체 품질, 안정성 및 사용자 환경을 파악할 수 있는 풍부한 메트릭 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-138">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="7d2e9-139">[통화 분석](set-up-call-analytics.md)을 사용하여 개별 사용자의 통화 및 모임 문제를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-139">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="7d2e9-140">네트워크 최적화</span><span class="sxs-lookup"><span data-stu-id="7d2e9-140">Network optimization</span></span>

<span data-ttu-id="7d2e9-141">다음 작업은 선택 사항이며 특히 중소기업이거나 Microsoft 365 또는 Office 365를 이미 배포한 경우 Teams를 배포하는 데 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-141">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7d2e9-142">네트워크 및 Teams 성능을 최적화하거나 네트워크 제한 사항이 있는 경우 이 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-142">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="7d2e9-143">다음의 경우 추가 네트워크 최적화를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-143">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="7d2e9-144">Teams가 느리게 실행됩니다(대역폭이 부족할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="7d2e9-144">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="7d2e9-145">통화가 계속 끊깁니다(방화벽 또는 프록시 차단 때문일 수 있음).</span><span class="sxs-lookup"><span data-stu-id="7d2e9-145">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="7d2e9-146">통화 중 잡음이 들리고 끊기거나 음성이 로봇처럼 들립니다(지터 또는 패킷 손실일 수 있음).</span><span class="sxs-lookup"><span data-stu-id="7d2e9-146">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="7d2e9-147">네트워크 장애를 식별하고 수정하기 위한 지침을 비롯한 네트워크 최적화에 대한 자세한 논의는 [Microsoft 365 및 Office 365 네트워크 연결 원칙](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-147">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="7d2e9-148">네트워크 최적화 작업</span><span class="sxs-lookup"><span data-stu-id="7d2e9-148">Network optimization task</span></span></th>
<th><span data-ttu-id="7d2e9-149">세부 정보</span><span class="sxs-lookup"><span data-stu-id="7d2e9-149">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7d2e9-150">네트워크 플래너</span><span class="sxs-lookup"><span data-stu-id="7d2e9-150">Network planner</span></span></td>
<td><p><span data-ttu-id="7d2e9-151">조직의 물리적 위치에서 대역폭 계산 및 네트워크 요구 사항을 포함하여 네트워크를 평가하는 데 도움이 필요한 경우 <a href="https://admin.teams.microsoft.com">Teams 관리 센터</a>의 <a href="/microsoftteams/network-planner">네트워크 플래너</a> 도구를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-151">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="7d2e9-152">네트워크 세부 정보 및 Teams 사용을 제공하는 경우 네트워크 플래너는 조직에서 실제 위치에 Teams와 Cloud Voice를 배포하는데 필요한 네트워크 요구 사항을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-152">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="7d2e9-153">예제 시나리오는 <a href="/microsoftteams/tutorial-network-planner-example">네트워크 플래너 사용 - 예제 시나리오</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-153">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7d2e9-154">Teams용 어드바이저</span><span class="sxs-lookup"><span data-stu-id="7d2e9-154">Advisor for Teams</span></span></td>
<td><span data-ttu-id="7d2e9-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Teams용 어드바이저</a>는 <a href="https://admin.teams.microsoft.com">Teams 관리 센터</a>의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="7d2e9-156">Advisor for Teams(미리 보기)는 Microsoft 365 또는 Office 365 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-156">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7d2e9-157">외부 이름 확인</span><span class="sxs-lookup"><span data-stu-id="7d2e9-157">External Name Resolution</span></span></td>
<td><span data-ttu-id="7d2e9-158">Teams 클라이언트를 실행하는 모든 컴퓨터가 외부 DNS 쿼리를 확인하여 Microsoft 365 또는 Office 365에서 제공하는 서비스를 검색할 수 있고 방화벽이 액세스를 차단하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-158">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="7d2e9-159">방화벽 포트 구성에 대한 자세한 내용은 <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 및 Office 365 URL 및 IP 범위</a>로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-159">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7d2e9-160">세션 지속성 유지</span><span class="sxs-lookup"><span data-stu-id="7d2e9-160">Maintain session persistence</span></span></td>
<td><span data-ttu-id="7d2e9-161">방화벽에서 UDP에 대해 매핑된 NAT(Network Address Translation) 주소 또는 포트를 변경하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-161">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="7d2e9-162">NAT 풀 크기 확인</span><span class="sxs-lookup"><span data-stu-id="7d2e9-162">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="7d2e9-163">사용자 연결에 필요한 NAT(network address translation) 풀 크기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-163">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="7d2e9-164">여러 사용자와 장치가 <a href="/office365/enterprise/nat-support-with-office-365">NAT(Network Address Translation) 또는 PAT(Port Address Translation)</a>를 사용하여 Microsoft 365 또는 Office 365에 액세스하는 경우, 공개적으로 라우팅할 수 있는 각 IP 주소 뒤에 숨어 있는 장치가 지원되는 수를 초과하지 않는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-164">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="7d2e9-165">포트 소진을 방지하도록 NAT 풀에 적절한 공용 IP 주소를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-165">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="7d2e9-166">포트 소진은 내부 사용자와 장치가 Microsoft 365 또는 Office 365 서비스에 연결할 수 없게 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-166">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7d2e9-167">Microsoft 데이터 센터로 라우팅</span><span class="sxs-lookup"><span data-stu-id="7d2e9-167">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="7d2e9-168"><a href="/office365/enterprise/client-connectivity">가장 효율적인 Microsoft 데이터 센터로의 라우팅을 구현합니다</a>.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-168"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="7d2e9-169">로컬 또는 국가별 송신 지점을 사용하여 최대한 효율적으로 Microsoft 네트워크에 연결할 수 있는 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-169">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7d2e9-170">침입 탐지 및 예방 지침</span><span class="sxs-lookup"><span data-stu-id="7d2e9-170">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="7d2e9-171">아웃바운드 연결에 대한 추가 보안 계층을 위해 배포된 <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">침입 탐지</a> 또는 예방 시스템(IDS/IPS)이 있는 경우 모든 Microsoft 365 또는 Office 365 URL을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-171">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7d2e9-172">분할 터널 VPN 구성</span><span class="sxs-lookup"><span data-stu-id="7d2e9-172">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="7d2e9-173">일반적으로 <a href="/windows/security/identity-protection/vpn/vpn-routing">분할 터널 VPN</a>이라고 알려진 VPN(가상 사설망)을 우회하는 Teams 트래픽에 대한 대체 경로를 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-173">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="7d2e9-174">분할 터널링은 Microsoft 365 또는 Office 365의 트래픽이 VPN을 통과하지 않고 대신 Microsoft 365 또는 Office 365로 직접 이동함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-174">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7d2e9-175">VPN을 우회하면 Teams 품질에 긍정적인 영향을 미치며 VPN 장치와 조직의 네트워크의 부하가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-175">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="7d2e9-176">분할 터널 VPN을 구현하기 위해 VPN 공급업체와 협력하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-176">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="7d2e9-177">VPN 우회를 권장하는 다른 이유:</span><span class="sxs-lookup"><span data-stu-id="7d2e9-177">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="7d2e9-178">일반적으로 VPN은 실시간 미디어를 지원하도록 설계되거나 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-178">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="7d2e9-179">일부 VPN은 UDP를 지원하지 않을 수도 있습니다(Teams에 필요함).</span><span class="sxs-lookup"><span data-stu-id="7d2e9-179">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="7d2e9-180">또한 VPN은 이미 암호화되어 있는 미디어 트래픽 위에 추가 암호화 계층을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-180">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="7d2e9-181">VPN 장치를 통한 헤어핀 트래픽으로 인해 Teams에 대한 연결이 효율적이지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-181">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7d2e9-182">QoS 구현</span><span class="sxs-lookup"><span data-stu-id="7d2e9-182">Implement QoS</span></span></td>
<td><span data-ttu-id="7d2e9-183"><a href="/microsoftteams/qos-in-teams">QoS(서비스 품질)를 사용하여</a> 패킷 우선순위를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-183"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="7d2e9-184">이렇게 하면 Teams의 통화 품질이 향상될 수 있으며 통화 품질을 모니터링하고 문제를 해결하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-184">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="7d2e9-185">QoS는 관리 네트워크의 모든 세그먼트에 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-185">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="7d2e9-186">네트워크가 대역폭에 적절하게 프로비전된 경우에도 QoS에서는 예상하지 않은 네트워크 이벤트가 발생하면 위험을 완화합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-186">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="7d2e9-187">QoS를 사용하여 이러한 예상치 않은 이벤트가 품질에 부정적인 영향을 주지 있도록 음성 트래픽이 우선시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-187">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7d2e9-188">WiFi 최적화</span><span class="sxs-lookup"><span data-stu-id="7d2e9-188">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="7d2e9-189">VPN과 마찬가지로 WiFi 네트워크는 실시간 미디어를 지원하도록 설계되거나 구성되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-189">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="7d2e9-190">Teams를 지원하기 위해 WiFi 네트워크를 계획하거나 최적화하는 것은 고품질 배포를 하기 위한 중요한 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-190">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="7d2e9-191">다음 요인들을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-191">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d2e9-192">QoS 또는 WMM(WiFi 멀티미디어)를 구현하여 미디어 트래픽이 WiFi 네트워크보다 적절하게 우선되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-192">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="7d2e9-193">WiFi 대역과 액세스 지점 배치를 계획하고 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-193">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="7d2e9-194">2.4GHz 범위는 액세스 지점 배치에 따라 적절한 환경을 제공할 수 있지만 액세스 지점은 종종 해당 범위에서 작동하는 다른 소비자 장치의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-194">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="7d2e9-195">5GHz 범위는 조밀한 범위 때문에 실시간 미디어에 더 적합하지만, 충분한 범위를 확보하려면 액세스 지점이 더 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-195">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="7d2e9-196">또한 엔드포인트는 해당 범위를 지원하고 그에 따라 해당 대역을 활용하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-196">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="7d2e9-197">이중 대역 WiFi 네트워크를 사용 중이면 대역 조정을 구현하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-197">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="7d2e9-198"><em>대역 조정</em>은 5GHz 범위를 사용하도록 이중 대역 클라이언트에 영향을 미치기 위해 WiFi 공급업체에서 구현한 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-198"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="7d2e9-199">같은 채널의 액세스 지점이 너무 가깝게 있는 경우 신호가 겹치거나 의도치 않게 경합하여 사용자에게 좋지 않은 환경이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-199">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="7d2e9-200">옆에 있는 액세스 포인트가 서로 겹치지 않는 채널에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-200">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="7d2e9-201">각 무선 공급업체에는 무선 솔루션을 배포하는 것에 대한 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-201">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="7d2e9-202">자세한 지침은 Wi-Fi 공급업체에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-202">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="7d2e9-203">대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d2e9-203">Bandwidth requirements</span></span>

<span data-ttu-id="7d2e9-204">Teams는 네트워크 조건과 상관없이 최상의 오디오, 비디오, 콘텐츠 공유 환경을 제공하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-204">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="7d2e9-205">즉, 대역폭이 부족하면 Teams에서는 비디오 품질보다 오디오 품질을 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-205">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="7d2e9-206">대역폭이 제한되지 않는 경우, Teams에서는 고해상도 오디오, 최대 1080p 비디오 해상도, 최대 30fps(초당 프레임 수)의 비디오 및 컨텐츠를 포함한 미디어 품질을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-206">Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30fps (frames per second) for video and content.</span></span>

<span data-ttu-id="7d2e9-207">이 표는 Teams에서 대역폭을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-207">This table describes how Teams uses bandwidth.</span></span> <span data-ttu-id="7d2e9-208">Teams는 항상 대역폭 사용에 대해 보수적이며 1.5Mbps 미만에서 HD 비디오 품질을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-208">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.5Mbps.</span></span> <span data-ttu-id="7d2e9-209">각 오디오/비디오 통화 또는 모임에서 실제 대역폭 소비량은 비디오 레이아웃, 비디오 해상도, 비디오 프레임 등 여러 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-209">The actual bandwidth consumption in each audio/video call or meeting will vary based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="7d2e9-210">더 많은 대역폭을 사용할 수 있게 되면 최상의 환경을 제공하기 위해 품질이 향상되고 사용량이 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-210">When more bandwidth is available, quality and usage will increase to deliver the best experience.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="7d2e9-211">**형식**</span><span class="sxs-lookup"><span data-stu-id="7d2e9-211">**Modality**</span></span>
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="7d2e9-212">**대역폭 요구 사항(비트 전송률 KB/ 업/다운)**</span><span class="sxs-lookup"><span data-stu-id="7d2e9-212">**Bandwidth requirements (bitrate KB/s up/down)**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="7d2e9-213">**최소**</span><span class="sxs-lookup"><span data-stu-id="7d2e9-213">**Minimum**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="7d2e9-214">**권장**</span><span class="sxs-lookup"><span data-stu-id="7d2e9-214">**Recommended**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="7d2e9-215">**최고의 성능**</span><span class="sxs-lookup"><span data-stu-id="7d2e9-215">**Best performance**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="7d2e9-216">**오디오**</span><span class="sxs-lookup"><span data-stu-id="7d2e9-216">**Audio**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="7d2e9-217">일대일</span><span class="sxs-lookup"><span data-stu-id="7d2e9-217">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-218">10/10</span><span class="sxs-lookup"><span data-stu-id="7d2e9-218">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-219">58/58</span><span class="sxs-lookup"><span data-stu-id="7d2e9-219">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-220">76/76</span><span class="sxs-lookup"><span data-stu-id="7d2e9-220">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="7d2e9-221">모임</span><span class="sxs-lookup"><span data-stu-id="7d2e9-221">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-222">10/10</span><span class="sxs-lookup"><span data-stu-id="7d2e9-222">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-223">58/58</span><span class="sxs-lookup"><span data-stu-id="7d2e9-223">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-224">76/76</span><span class="sxs-lookup"><span data-stu-id="7d2e9-224">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="7d2e9-225">**비디오**</span><span class="sxs-lookup"><span data-stu-id="7d2e9-225">**Video**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="7d2e9-226">일대일</span><span class="sxs-lookup"><span data-stu-id="7d2e9-226">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-227">150/150</span><span class="sxs-lookup"><span data-stu-id="7d2e9-227">150/150</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-228">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="7d2e9-228">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-229">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="7d2e9-229">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="7d2e9-230">모임</span><span class="sxs-lookup"><span data-stu-id="7d2e9-230">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-231">150/200</span><span class="sxs-lookup"><span data-stu-id="7d2e9-231">150/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-232">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="7d2e9-232">2,500/4,000</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-233">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="7d2e9-233">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="7d2e9-234">**화면 공유.**</span><span class="sxs-lookup"><span data-stu-id="7d2e9-234">**Screen sharing**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="7d2e9-235">일대일</span><span class="sxs-lookup"><span data-stu-id="7d2e9-235">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-236">200/200</span><span class="sxs-lookup"><span data-stu-id="7d2e9-236">200/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-237">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="7d2e9-237">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-238">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="7d2e9-238">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="7d2e9-239">모임</span><span class="sxs-lookup"><span data-stu-id="7d2e9-239">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-240">250/250</span><span class="sxs-lookup"><span data-stu-id="7d2e9-240">250/250</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-241">2,500/2,500</span><span class="sxs-lookup"><span data-stu-id="7d2e9-241">2,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-242">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="7d2e9-242">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="7d2e9-243">**함께 모드**</span><span class="sxs-lookup"><span data-stu-id="7d2e9-243">**Together Mode**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="7d2e9-244">일대일</span><span class="sxs-lookup"><span data-stu-id="7d2e9-244">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-245">해당 없음</span><span class="sxs-lookup"><span data-stu-id="7d2e9-245">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-246">해당 없음</span><span class="sxs-lookup"><span data-stu-id="7d2e9-246">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-247">해당 없음</span><span class="sxs-lookup"><span data-stu-id="7d2e9-247">N/A</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="7d2e9-248">모임</span><span class="sxs-lookup"><span data-stu-id="7d2e9-248">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-249">1,000/1,500</span><span class="sxs-lookup"><span data-stu-id="7d2e9-249">1,000/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-250">1,500/2,500</span><span class="sxs-lookup"><span data-stu-id="7d2e9-250">1,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="7d2e9-251">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="7d2e9-251">2,500/4,000</span></span>
   :::column-end:::
:::row-end:::

<span data-ttu-id="7d2e9-252">**최소**, **권장** 및 **최고의 성능** 대역폭 요구 사항은 엔드포인트별 사용량을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-252">**Minimum**, **Recommended**, and **Best performance** bandwidth requirements are based on per-endpoint usage.</span></span> <span data-ttu-id="7d2e9-253">일반적으로 사용자당 하나의 엔드포인트가 있습니다(예: 컴퓨터 또는 모바일 장치).</span><span class="sxs-lookup"><span data-stu-id="7d2e9-253">Typically, there's one endpoint per user, such as a computer or mobile device.</span></span> <span data-ttu-id="7d2e9-254">그러나 사용자가 시스템 *과* 모바일 장치 *모두* 에서 Teams 모임에 참여하는 경우 두 개의 엔드포인트가 해당 사용자와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-254">However, if a user joins a Teams meeting on *both* a computer *and* a mobile device, two endpoints are associated with that user.</span></span>

- <span data-ttu-id="7d2e9-255">비디오 호출에 필요한 **최소** 대역폭 요구 사항은 최대 240p 해상도, 화면 공유 컨텐츠 프레임률이 적응형 1.875~7.5fps, 함께 모드/대형 갤러리 비디오 해상도가 최대 540p입니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-255">**Minimum** Bandwidth requirements for video calls are up to 240p resolution, screen sharing content frame rates adaptive 1.875 to 7.5fps, and Together Mode/Large Gallery video up to 540p resolution.</span></span>  

- <span data-ttu-id="7d2e9-256">비디오 호출에 **권장되는** 대역폭 요구 사항은 최대 1080p 해상도<sup>\*</sup>, 화면 공유 컨텐츠 프레임률 적응형 7.5~30fps 및 함께 모드/대형 갤러리 비디오 해상도 최대 1080p입니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7d2e9-256">**Recommended** Bandwidth requirements for video calls are up to 1080p resolution<sup>\*</sup>, screen sharing content frame rates adaptive 7.5 to 30fps, and Together Mode/Large Gallery video up to 1080p resolution<sup>\*</sup>.</span></span>  

- <span data-ttu-id="7d2e9-257">**최고의 성능** 지침은 15~30fps의 화면 공유 콘텐츠 프레임률을 통해 대규모 참석자 모임, 고손실 환경 및 고 모션 콘텐츠를 보다 충실하게 저장할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-257">**Best Performance** Guidance allows higher fidelity video for larger attendee meetings, high loss environments, and higher motion content with screen sharing content frame rates adaptive 15 to 30fps.</span></span>

<span data-ttu-id="7d2e9-258"><sup>\*</sup>최대 1080p의 화질을 기대하지만 네트워크 상태에 따라 비디오 해상도와 화질이 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2e9-258"><sup>\*</sup>Expect up to 1080p quality but depending on your network conditions, video resolution and quality will be optimized accordingly.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="7d2e9-259">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7d2e9-259">Related Topics</span></span>

[<span data-ttu-id="7d2e9-260">Microsoft 365 및 Office 365 네트워크 연결 원칙</span><span class="sxs-lookup"><span data-stu-id="7d2e9-260">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="7d2e9-261">전 세계 엔드포인트: 비즈니스용 Skype Online 및 Teams</span><span class="sxs-lookup"><span data-stu-id="7d2e9-261">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="7d2e9-262">Teams용 프록시 서버</span><span class="sxs-lookup"><span data-stu-id="7d2e9-262">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="7d2e9-263">Teams의 미디어: 모임이 간단한 이유</span><span class="sxs-lookup"><span data-stu-id="7d2e9-263">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="7d2e9-264">Teams의 미디어: 미디어 흐름에 대한 심층 분석</span><span class="sxs-lookup"><span data-stu-id="7d2e9-264">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="7d2e9-265">Teams의 ID 모델 및 인증</span><span class="sxs-lookup"><span data-stu-id="7d2e9-265">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="7d2e9-266">Teams를 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="7d2e9-266">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="7d2e9-267">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7d2e9-267">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
