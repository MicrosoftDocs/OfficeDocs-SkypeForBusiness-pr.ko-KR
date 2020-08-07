---
title: Teams에 대한 조직의 네트워크 준비
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 네트워크 요구 사항, 네트워크 최적화, 대역폭 요구 사항을 비롯 한 조직의 네트워크를 준비 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: d0ce589ef972639928e4c8696f3ed23146126086
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583895"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="aa679-103">Microsoft Teams에 대한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="aa679-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="aa679-104">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa679-104">Network requirements</span></span>

<span data-ttu-id="aa679-105">[Microsoft 365 또는 Office 365 용 네트워크](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)를 이미 최적화 한 경우 microsoft 팀에 대 한 준비가 되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-105">If you've already [optimized your network for Microsoft 365 or Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="aa679-106">어떤 경우 든 특히, **원격 작업자** 를 지원 하기 위해 첫 번째 Microsoft 365 또는 Office 365 작업 부하로 팀을 신속 하 게 배포 하는 경우 팀 롤아웃을 시작 하기 전에 다음을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="aa679-107">모든 위치에서 인터넷에 액세스할 수 있도록 하 되, Microsoft 365 또는 Office 365에 연결 되도록 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="aa679-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="aa679-108">최소한 일반 웹 소통량 외에도 팀에서 미디어의 모든 위치에 대해 다음을 열었는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="aa679-109">139</span><span class="sxs-lookup"><span data-stu-id="aa679-109">Ports</span></span>     |<span data-ttu-id="aa679-110">UDP 포트 <strong>3478</strong> ~ <strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="aa679-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="aa679-111">IP 주소</span><span class="sxs-lookup"><span data-stu-id="aa679-111">IP addresses</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="aa679-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, <strong>52.120.0.0/14</strong></span><span class="sxs-lookup"><span data-stu-id="aa679-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="aa679-113">온-프레미스 또는 온라인으로 비즈니스용 Skype에 페더레이션 해야 하는 경우 몇 가지 추가 DNS 레코드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure some additional DNS records.</span></span>
>
>|<span data-ttu-id="aa679-114">CNAME 레코드/호스트 이름</span><span class="sxs-lookup"><span data-stu-id="aa679-114">CNAME Records / Host name</span></span>  |<span data-ttu-id="aa679-115">TTL</span><span class="sxs-lookup"><span data-stu-id="aa679-115">TTL</span></span>  |<span data-ttu-id="aa679-116">주소 또는 값 가리키기</span><span class="sxs-lookup"><span data-stu-id="aa679-116">Points to address or value</span></span>  |
>|---------|---------|---------|
>|<span data-ttu-id="aa679-117">sip</span><span class="sxs-lookup"><span data-stu-id="aa679-117">sip</span></span>     |    <span data-ttu-id="aa679-118">3600</span><span class="sxs-lookup"><span data-stu-id="aa679-118">3600</span></span>     |    <span data-ttu-id="aa679-119">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="aa679-119">sipdir.online.lync.com</span></span>     |
>|<span data-ttu-id="aa679-120">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="aa679-120">lyncdiscover</span></span>     |   <span data-ttu-id="aa679-121">3600</span><span class="sxs-lookup"><span data-stu-id="aa679-121">3600</span></span>      |    <span data-ttu-id="aa679-122">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="aa679-122">webdir.online.lync.com</span></span>     |
>


    
2.  <span data-ttu-id="aa679-123">Microsoft 365 또는 Office 365에 대해 확인 된 도메인이 있습니까 (예: contoso.com)?</span><span class="sxs-lookup"><span data-stu-id="aa679-123">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
      - <span data-ttu-id="aa679-124">조직에서 Microsoft 365 또는 Office 365을 롤백하지 않은 경우 [시작](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-124">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
      - <span data-ttu-id="aa679-125">조직에서 Microsoft 365 또는 Office 365에 대해 확인 된 도메인을 추가 하거나 구성 하지 않은 경우에는 [도메인 FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-125">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="aa679-126">조직에서 Exchange Online 및 SharePoint Online을 배포 했습니까?</span><span class="sxs-lookup"><span data-stu-id="aa679-126">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
      - <span data-ttu-id="aa679-127">조직에 Exchange Online이 없는 경우 [exchange 및 Microsoft 팀의 상호 작용 방법 이해](exchange-teams-interact.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-127">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
      - <span data-ttu-id="aa679-128">조직에 SharePoint Online이 없는 경우 [Sharepoint online 및 비즈니스용 OneDrive For Business가 Microsoft 팀과 어떻게 상호 작용 하는지 이해](sharepoint-onedrive-interact.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-128">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="aa679-129">이러한 네트워크 요구 사항을 충족 하는 것으로 확인 되 면 [팀을 롤아웃할](How-to-roll-out-teams.md)준비가 되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-129">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="aa679-130">다국적 대기업 이거나 몇 가지 네트워크 제한 사항이 있는 경우에는 팀을 위해 네트워크를 평가 하 고 최적화 하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-130">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa679-131">**교육 기관**: 조직이 교육 기관 이거나 SIS (학생 정보 시스템)를 사용 하는 경우 팀을 롤아웃하기 전에 [School Data Sync를 배포](https://docs.microsoft.com/schooldatasync/) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-131">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="aa679-132">온 **-프레미스 비즈니스용 Skype server**: 조직이 온-프레미스 비즈니스용 skype server (또는 Lync Server)를 실행 하는 경우 [Azure AD Connect를 구성](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) 하 여 온-프레미스 디렉터리를 Microsoft 365 또는 Office 365와 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-132">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="aa679-133">모범 사례: CQD 및 call analytics을 사용 하 여 네트워크 모니터링</span><span class="sxs-lookup"><span data-stu-id="aa679-133">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="aa679-134">[CQD (통화 품질 대시보드)](turning-on-and-using-call-quality-dashboard.md) 를 사용 하 여 팀에서 통화 및 모임 품질에 대 한 통찰력을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-134">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="aa679-135">CQD는 품질, 안정성 및 사용자 경험을 가까이 유지 하 여 네트워크를 최적화 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-135">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="aa679-136">CQD는 전체적인 패턴이 명확 하 게 표시 될 수 있는 전체 조직에 대 한 집계 원격 분석을 살펴보고 문제를 식별 하 고 업데이트를 계획 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-136">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="aa679-137">또한 CQD는 전반적인 품질, 안정성 및 사용자 환경에 대 한 통찰력을 제공 하는 풍부한 메트릭 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-137">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="aa679-138">[통화 분석](set-up-call-analytics.md) 을 사용 하 여 개별 사용자의 통화 및 모임 문제를 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-138">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="aa679-139">네트워크 최적화</span><span class="sxs-lookup"><span data-stu-id="aa679-139">Network optimization</span></span>

<span data-ttu-id="aa679-140">다음 작업은 선택 사항이 며 팀 롤아웃에 필요 하지 않으며 특히, 소규모 기업과 이미 Microsoft 365 또는 Office 365을 출시 했습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-140">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="aa679-141">이 지침을 사용 하 여 네트워크 및 팀 성능을 최적화 하거나 네트워크 제한 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-141">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="aa679-142">다음과 같은 경우 추가 네트워크 최적화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-142">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="aa679-143">팀이 느리게 실행 됨 (대역폭이 부족할 수도 있음)</span><span class="sxs-lookup"><span data-stu-id="aa679-143">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="aa679-144">통화 보관 (방화벽 또는 프록시 차단 때문일 수 있음)</span><span class="sxs-lookup"><span data-stu-id="aa679-144">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="aa679-145">통화에는 정적, 오려내기 또는 로봇 등의 음성 사운드가 있습니다 (지터 또는 패킷 손실이 있을 수 있음).</span><span class="sxs-lookup"><span data-stu-id="aa679-145">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="aa679-146">네트워크 장애를 식별 하 고 해결 하는 지침을 비롯 한 네트워크 최적화에 대 한 자세한 내용은 [Microsoft 365 및 Office 365 네트워크 연결 원칙](https://aka.ms/pnc)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-146">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](https://aka.ms/pnc).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="aa679-147"><strong>네트워크 최적화 작업</strong></span><span class="sxs-lookup"><span data-stu-id="aa679-147"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="aa679-148"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="aa679-148"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="aa679-149">네트워크 planner</span><span class="sxs-lookup"><span data-stu-id="aa679-149">Network planner</span></span></td>
<td><p><span data-ttu-id="aa679-150">조직의 실제 위치에서 대역폭 계산과 네트워크 요구 사항을 비롯 한 네트워크를 평가 하는 데 도움이 필요한 경우 <a href="https://admin.teams.microsoft.com">팀 관리 센터</a>에서 <a href="https://docs.microsoft.com/microsoftteams/network-planner">네트워크 Planner</a> 도구를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-150">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="aa679-151">네트워크 세부 정보 및 팀 사용량을 제공 하는 경우 네트워크 계획자는 조직의 실제 위치에서 팀 및 클라우드 음성을 배포 하기 위한 네트워크 요구 사항을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-151">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="aa679-152">예제 시나리오는 <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">네트워크 Planner 사용-예제 시나리오</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-152">For an example scenario, see <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aa679-153">팀 관리자</span><span class="sxs-lookup"><span data-stu-id="aa679-153">Advisor for Teams</span></span></td>
<td><span data-ttu-id="aa679-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">팀</a> 관리자는 <a href="https://admin.teams.microsoft.com">팀 관리 센터</a>의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="aa679-155">Advisor for Teams(미리 보기)는 Microsoft 365 또는 Office 365 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-155">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aa679-156">외부 이름 확인</span><span class="sxs-lookup"><span data-stu-id="aa679-156">External Name Resolution</span></span></td>
<td><span data-ttu-id="aa679-157">팀 클라이언트를 실행 하는 모든 컴퓨터에서 Microsoft 365 또는 Office 365에서 제공 하는 서비스를 검색할 수 있도록 외부 DNS 쿼리를 확인 하 고 방화벽이 액세스를 차단 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-157">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="aa679-158">방화벽 포트를 구성 하는 방법에 대 한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 및 Office 365 url 및 IP 범위로</a>이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-158">For information about configuring firewall ports, go to <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aa679-159">세션 유지 관리</span><span class="sxs-lookup"><span data-stu-id="aa679-159">Maintain session persistence</span></span></td>
<td><span data-ttu-id="aa679-160">방화벽이 UDP에 대 한 매핑된 NAT (Network Address Translation) 주소 또는 포트를 변경 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-160">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="aa679-161">NAT 풀 크기 확인</span><span class="sxs-lookup"><span data-stu-id="aa679-161">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="aa679-162">사용자 연결에 필요한 NAT (network address translation) 풀 크기의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-162">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="aa679-163">여러 사용자와 장치가 <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">NAT (Network Address translation) 또는 PAT (Port Address translation)</a>를 사용 하 여 Microsoft 365 또는 Office 365에 액세스 하는 경우, 각 공용 라우팅 가능 IP 주소 뒤에 숨겨진 장치가 지원 되는 번호를 초과 하지 않는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-163">When multiple users and devices access Microsoft 365 or Office 365 using <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="aa679-164">포트 소모를 방지 하기 위해 적절 한 공용 IP 주소가 NAT 풀에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-164">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="aa679-165">포트 소모는 내부 사용자와 장치가 Microsoft 365 또는 Office 365 서비스에 연결할 수 없는 경우에 기여 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-165">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aa679-166">Microsoft 데이터 센터로 라우팅</span><span class="sxs-lookup"><span data-stu-id="aa679-166">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="aa679-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Microsoft 데이터 센터에 가장 효율적인 라우팅을 구현</a>합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="aa679-168">로컬 또는 지역 송신 지점을 사용 하 여 가능한 한 효율적으로 Microsoft 네트워크에 연결할 수 있는 위치를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-168">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aa679-169">침입 감지 및 예방 지침</span><span class="sxs-lookup"><span data-stu-id="aa679-169">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="aa679-170">아웃 바운드 연결에 대 한 추가 보안 계층에 대 한 <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">침입 감지</a> 또는 방지 시스템 (ID/i p)이 환경에 있는 경우 모든 Microsoft 365 또는 Office 365 url을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-170">If your environment has an <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aa679-171">분할 터널 VPN 구성</span><span class="sxs-lookup"><span data-stu-id="aa679-171">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="aa679-172">일반적으로 [분할 터널 VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing)이라고 하는 vpn (가상 사설망)을 우회 하는 팀 트래픽에 대 한 대체 경로를 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-172">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as [split-tunnel VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing).</span></span> <span data-ttu-id="aa679-173">분할 터널링은 Microsoft 365 또는 Office 365에 대 한 트래픽이 VPN을 거치지 않고 대신 Microsoft 365 또는 Office 365로 바로 이동 한다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-173">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="aa679-174">VPN을 건너뛰면 팀 품질에 긍정적인 영향을 미칠 수 있으며, VPN 장치 및 조직의 네트워크에서의 로드를 줄여줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-174">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="aa679-175">분할 터널 VPN을 구현 하려면 VPN 공급 업체와 협력 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-175">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="aa679-176">VPN을 우회 하는 것이 권장 되는 다른 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-176">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="aa679-177">Vpn은 일반적으로 실시간 미디어를 지원 하도록 설계 또는 구성 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-177">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="aa679-178">일부 Vpn은 UDP (팀에 필요 함)를 지원 하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-178">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="aa679-179">Vpn은 이미 암호화 된 미디어 트래픽 위에 추가 암호화 계층을 도입 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="aa679-180">VPN 장치를 통해 헤어 고정 트래픽 때문에 팀에 대 한 연결이 효율적이 지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-180">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aa679-181">QoS 구현</span><span class="sxs-lookup"><span data-stu-id="aa679-181">Implement QoS</span></span></td>
<td><span data-ttu-id="aa679-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">QoS (서비스 품질)를 사용</a> 하 여 패킷 우선 순위를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="aa679-183">이렇게 하면 팀에서 통화 품질을 개선 하 고 통화 품질을 모니터링 하 고 문제를 해결 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-183">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="aa679-184">QoS는 관리 되는 네트워크의 모든 세그먼트에서 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-184">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="aa679-185">네트워크가 대역폭에 적절 하 게 프로 비전 된 경우에도 QoS는 예기치 않은 네트워크 이벤트가 발생할 경우 위험 경감을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-185">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="aa679-186">QoS를 사용 하면 이러한 예기치 않은 이벤트가 품질에 부정적인 영향을 주지 않도록 음성 트래픽이 우선 순위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-186">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aa679-187">WiFi 최적화</span><span class="sxs-lookup"><span data-stu-id="aa679-187">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="aa679-188">VPN과 유사 하 게, WiFi 네트워크는 실시간 미디어를 지원 하도록 설계 또는 구성 되어 있지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-188">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="aa679-189">팀을 지원 하기 위해 WiFi 네트워크를 계획 하거나 최적화 하는 것은 고품질 배포를 위한 중요 한 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-189">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="aa679-190">다음과 같은 요인을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-190">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa679-191">WiFi 네트워크를 통해 미디어 트래픽이 적절 하 게 우선 순위를 유지 하도록 QoS 또는 WMM (WiFi 멀티미디어)를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-191">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="aa679-192">WiFi 밴드 및 액세스 지점의 위치를 계획 하 고 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-192">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="aa679-193">2.4 GHz 범위는 액세스 지점 배치에 따라 적절 한 환경을 제공할 수 있지만 액세스 지점은 해당 범위에서 작동 하는 다른 소비자 장치에 영향을 받는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-193">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="aa679-194">5ghz 범위는 조밀 범위 때문에 실시간 미디어에 더 적합 하지만, 충분 한 서비스를 얻으려면 더 많은 액세스 포인트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-194">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="aa679-195">또한 끝점은 해당 범위를 지원 하 고 그에 따라 이러한 대역을 활용 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="aa679-196">이중 대역 WiFi 네트워크를 사용 하는 경우에는 밴드 조절을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-196">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="aa679-197"><em>밴드 조종</em> 은 듀얼 밴드 클라이언트에 게 5ghz 범위를 사용 하는 데 영향을 주는 WiFi 공급 업체에서 구현한 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-197"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="aa679-198">같은 채널의 액세스 지점이 너무 가까이 있으면 신호가 겹치고 그에 따른 경합으로 인해 사용자에 게 좋지 않은 환경이 제공 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-198">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="aa679-199">서로 인접 한 연결점이 겹치지 않는 채널에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="aa679-200">각 무선 공급 업체에는 해당 무선 솔루션을 배포 하기 위한 고유한 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="aa679-201">WiFi 공급 업체에 문의 하 여 특정 지침을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa679-201">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="aa679-202">대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa679-202">Bandwidth requirements</span></span>

<span data-ttu-id="aa679-203">팀은 네트워크 상태에 관계 없이 최상의 오디오, 비디오, 콘텐츠 공유 환경을 제공 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-203">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="aa679-204">대역폭을 충분히 사용할 수 없는 경우에는 팀이 비디오 품질 보다 오디오 품질에 우선 순위를 둘 것 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-204">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="aa679-205">대역폭이 제한 *되지* 않는 경우, 팀은 최대 1080p 비디오 해상도, 최대 30fps, 콘텐츠의 경우 15fps, 고화질 오디오를 비롯 한 미디어 품질을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa679-205">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="aa679-206">관련 항목</span><span class="sxs-lookup"><span data-stu-id="aa679-206">Related Topics</span></span>

[<span data-ttu-id="aa679-207">Microsoft 365 및 Office 365 네트워크 연결 원칙</span><span class="sxs-lookup"><span data-stu-id="aa679-207">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="aa679-208">전세계 끝점: 비즈니스용 Skype Online 및 팀</span><span class="sxs-lookup"><span data-stu-id="aa679-208">Worldwide endpoints: Skype for Business Online and Teams</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="aa679-209">팀의 프록시 서버</span><span class="sxs-lookup"><span data-stu-id="aa679-209">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="aa679-210">팀의 미디어: 모임이 간단한 이유</span><span class="sxs-lookup"><span data-stu-id="aa679-210">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="aa679-211">팀의 미디어: 전체 미디어 흐름에 대해 자세히 알아보고</span><span class="sxs-lookup"><span data-stu-id="aa679-211">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="aa679-212">Teams의 ID 모델 및 인증</span><span class="sxs-lookup"><span data-stu-id="aa679-212">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="aa679-213">Teams를 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="aa679-213">How to roll out Teams</span></span>](How-to-roll-out-teams.md)

[<span data-ttu-id="aa679-214">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="aa679-214">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
