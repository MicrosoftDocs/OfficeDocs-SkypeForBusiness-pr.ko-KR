---
title: 먼저 Microsoft Teams 롤아웃
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: 이 지침을 사용하여 Microsoft Teams 워크로드를 Microsoft 365 Office 365 합니다.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119357"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="ddb0f-103">먼저 Microsoft Teams 롤아웃</span><span class="sxs-lookup"><span data-stu-id="ddb0f-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="ddb0f-104">Microsoft Teams 직원들이 서로 연결되고 공동 작업할 수 있도록 지원할 수 있습니다. 특히 전 세계의 직원들이 원격 작업의 현실이 되는 전례 없는 현재의 경우.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="ddb0f-105">채팅을 할 수 있으며, 비디오 모임을 진행하고, Office 문서에서 공동 작업할 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="ddb0f-106">중소기업이든 비영리 조직이든 대규모 조직이든 다른 Teams 또는 서비스를 배포하기 전에 Microsoft 365 Office 365 첫 번째 워크로드로 시작할 Office 앱 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="ddb0f-107">이 문서에서는 "Teams 방법"을 통해 고려해야 하는 사항을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddb0f-108">Teams 첫 번째 클라우드 배포 워크로드일 수 있는 반면, Teams 배포는 전체 클라우드 배포 전략의 일부가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="ddb0f-109">다른 Microsoft 365 Office 365 서비스 및 Teams 롤아웃할 다음 워크로드인 경우 를 [롤아웃하는 방법을 Teams.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="ddb0f-110">여기에서 시작</span><span class="sxs-lookup"><span data-stu-id="ddb0f-110">Start here</span></span>

<span data-ttu-id="ddb0f-111">첫 번째 배포를 Teams 시작하려면 최소한 몇 가지 전제 요건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="ddb0f-112">다음 목록은 조직에서 사용하도록 설정하기 전에 조직에 필요한 Teams 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="ddb0f-113">도메인 이름으로 Microsoft 365 Office 365 조직 또는 조직</span><span class="sxs-lookup"><span data-stu-id="ddb0f-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="ddb0f-114">Azure Active Directory(AAD 연결) 또는 유사한 클라우드 ID 동기화 솔루션(모든 필수 특성이 테넌트와 동기화된 경우)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="ddb0f-115">AAD 동기화와 동기화된 특성을 이해하기 위해 Azure AD 커넥트 [동기화:](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) 동기화된 특성 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ddb0f-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="ddb0f-116">사용자에게 할당된 적절한 사용자 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="ddb0f-117">라이선스를 Teams 이해하기 위해 Microsoft Teams [설명 을 참조하세요.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="ddb0f-118">준비된 조직의 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="ddb0f-119">네트워크 준비를 이해하기 위해 조직의 네트워크 준비를 [Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="ddb0f-120">에서 Exchange, Sharepoint 및 비즈니스용 OneDrive Microsoft 365 Office 365 URL 및 IP 주소 범위에 Office 365 [허용합니다.](/office365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="ddb0f-121">2019년 9월 1일 이후에 만든 테넌트는 Teams 모드로 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="ddb0f-122">배포된 비즈니스용 Skype 서버 테넌트가 2019년 9월 1일 이후에 프로비전된 경우 지원 팀에 문의하여 Teams.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="ddb0f-123">사용자에게 라이선스를 할당하기 전에 '조직 전체 업그레이드 <span class="underline"></span> 정책'을 '섬 모드'로 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="ddb0f-124">마이그레이션 시작 지점</span><span class="sxs-lookup"><span data-stu-id="ddb0f-124">Migration Starting points</span></span>

<span data-ttu-id="ddb0f-125">시작 Microsoft 365 Office 365 또는 Lync 서버의 Teams 및 온-프레미스의 존재에 따라 비즈니스용 Skype 및 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="ddb0f-126">다음 섹션에서는 위의 전제 사항 외에도 기본 기능 및 구성 옵션을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="ddb0f-127">시작 지점 시나리오를 다음 항목으로 세분화했습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="ddb0f-128">**테넌트 Teams** 구성 : 테넌트 및 사용자 모드는 받는 사람의 동작을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="ddb0f-129">이러한 설정은 테넌트 수준 또는 조직의 사용자 수준에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="ddb0f-130">자세한 내용은 와 공존을 [비즈니스용 Skype.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="ddb0f-131">**채팅/외부** Teams : 채팅 서비스는 피어 투 피어 투 피어 또는 그룹 채팅 대화를 조직 내 또는 외부로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="ddb0f-132">외부 통신을 페더리화라고도 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="ddb0f-133">**모임 만들기** 및 Teams: 사용자는 항상 추가 기능을 통해 온라인 모임을 만들 수 Outlook Teams 모든 시나리오에서 PSTN 전화 접속을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="ddb0f-134">Teams 비즈니스용 Skype 사서함에 일정 정보를 저장하고 Exchange 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="ddb0f-135">프레미스 Exchange 클라이언트가 사용자의 사서함과 상호 작용할 수 Exchange Server 2016 CU3 이상을 Teams 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="ddb0f-136">사서함이 Exchange 일정 아이콘에 Teams 나타나지 않으면 사용자가 해당 클라이언트에서 모임을 보거나, 만들거나 수정할 수 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="ddb0f-137">**통화 기능 VoIP/PSTN을** Teams : 통화는 IP(VoIP) 또는 PSTN(공용 전환 전화 네트워크)을 통해 음성이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="ddb0f-138">VoIP 연결은 Teams 클라이언트 간에 기본적으로 발생하고, PSTN 연결은 사용자가 외부 전화 번호에 전화를 걸 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="ddb0f-139">Teams 두 가지 유형의 PSTN 연결을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="ddb0f-140">Microsoft 통화 계획은 Microsoft에서 사용자의 전화 번호 또는 직접 라우팅 구성을 포함한 전화 통신 인프라를 제공하는 경우 고객이 해당 사용자에 대한 세션 경계 컨트롤러(SBC)를 통해 전화 통신 연결을 Teams.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="ddb0f-141">자세한 내용은 어떤 통화 계획이 [적합한가요?](calling-plan-landing-page.md) 및 직접 라우팅을 전화 시스템 [를 읽어보세요.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="ddb0f-142">**Teams** 및 채널 공동 작업의 Teams : Teams 팀이 작업, 프로젝트 또는 공통 관심사에 대해 함께 모이는 사용자 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="ddb0f-143">Teams 채널로 만들어 졌다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-143">Teams are made up of channels.</span></span> <span data-ttu-id="ddb0f-144">각 채널은 "팀 이벤트", 부서 이름 또는 재미를 위해 토픽을 중심으로 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="ddb0f-145">채널은 모임을 개최하고, 대화를 나누고, 파일을 함께 작업하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="ddb0f-146">공동 작업 중</span><span class="sxs-lookup"><span data-stu-id="ddb0f-146">During collaboration</span></span>

<span data-ttu-id="ddb0f-147">**비즈니스용 OneDrive(P2P** 파일 공유) Teams : Teams 및 채널 외부에서 사용자가 Citrix Files, DropBox Teams, Box 및 OneDrive 같은 비즈니스용 파일 또는 기타 P2P 공유 파일 프로그램을 사용하여 피어 투 피어를 Google 드라이브.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="ddb0f-148">비즈니스 OneDrive 사용자는 온라인 라이선스가 할당된 SharePoint 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="ddb0f-149">**애플리케이션 플랫폼:** 앱은 조직에서 더 많은 기능을 사용할 수 있도록 가장 잘 사용할 수 있는 도구를 Teams.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="ddb0f-150">이러한 앱은 타사 또는 조직의 개발자가 Microsoft에서 제공하는 탭, 메시징 확장, 커넥터 및 봇의 기능을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="ddb0f-151">보안 및 규정 준수 **기능:** Teams, DLP(데이터 손실 보호), eDiscovery 및 채널, 채팅 및 파일, 감사 로그 검색을 비롯한 규정 준수 영역을 지원하기 위한 광범위한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="ddb0f-152">자세한 내용은 에서 보안 및 규정 [준수를 Microsoft Teams.](security-compliance-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="ddb0f-153">사전 eDiscovery 기능에는 E5 라이선스가 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="ddb0f-154">[라이선스 옵션을 비교합니다.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="ddb0f-155">시나리오에서 [Exchange Microsoft Teams](exchange-teams-interact.md) 준수 기능을 알아보기 위해 상호 작용하는 방법을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="ddb0f-156">비즈니스용 Skype **<span class="underline"></span>** 또는 Lync Server가 없는 조직</span><span class="sxs-lookup"><span data-stu-id="ddb0f-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="ddb0f-157">이 시작점은 조직에서 현재 비즈니스용 Skype 또는 Lync Server를 활용하지 않는 것으로 가정하고 Teams 응용 프로그램이 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ddb0f-158">다음 표에서는 핵심 서비스에 대한 고급 구성 및 최종 사용자 Teams 자세히 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ddb0f-159">항목</span><span class="sxs-lookup"><span data-stu-id="ddb0f-159">Item</span></span></th>
<th><span data-ttu-id="ddb0f-160">참고</span><span class="sxs-lookup"><span data-stu-id="ddb0f-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ddb0f-161">테넌트 Teams 구성</span><span class="sxs-lookup"><span data-stu-id="ddb0f-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="ddb0f-162">Teams 모드만, 모든 채팅 및 통화 기능은 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ddb0f-163">채팅/외부 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="ddb0f-164">내부(Microsoft 365 또는 Office 365) 및 외부 채팅 통신이 Teams.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="ddb0f-165"><em>참고: 외부 액세스에 대해 DNS 항목을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="ddb0f-166">비즈니스용 Skype DNS 레코드는 온-프레미스 또는 비즈니스용 Skype Lync 및 Microsoft 365 또는 Office 365 환경과의 페더전을 허용하지 비즈니스용 Skype 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="ddb0f-167">
<a href="/office365/enterprise/external-domain-name-system-records">외부 도메인 이름 시스템 레코드</a></em></span><span class="sxs-lookup"><span data-stu-id="ddb0f-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ddb0f-168">모임 만들기 및 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="ddb0f-169">추가 기능을 통해 내부 및 외부 Outlook 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="ddb0f-170">PSTN 전화 접속 및 전화 접속 기능은 오디오 회의 라이선스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="ddb0f-171">Teams 액세스하려면 하이브리드 Exchange 하이브리드를 사용하여 배포된 2016 CU3+ Exchange 하이브리드 구성 마법사를 사용하여 하이브리드 배포를 만들어야 <a href="/exchange/hybrid-deployment/deploy-hybrid">합니다.</a> </span><span class="sxs-lookup"><span data-stu-id="ddb0f-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="ddb0f-172">하이브리드 구성 외에도 Exchange OAuth Exchange 인증: 조직과 조직 간에 <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth Exchange Exchange Online 설정합니다."</span><span class="sxs-lookup"><span data-stu-id="ddb0f-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ddb0f-173">호출 기능</span><span class="sxs-lookup"><span data-stu-id="ddb0f-173">Calling Features</span></span><br />
<span data-ttu-id="ddb0f-174">VoIP/PSTN에서 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="ddb0f-175">테넌트에 대한 내부 및 외부 VoIP를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="ddb0f-176">PSTN 서비스는 시스템 Microsoft 전화 Microsoft 통화 계획 또는 직접 라우팅을 추가하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ddb0f-177">Teams 및 채널 공동 작업에서 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="ddb0f-178">규정 준수 기능을 포함한 전체 환경을 SharePoint 온라인 라이선스를 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="ddb0f-179">기존 프레미스 SharePoint 마이그레이션할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ddb0f-180">비즈니스용 OneDrive(P2P 파일 공유)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="ddb0f-181">비즈니스용 OneDrive 사용자가 온라인 라이선스를 할당해야 SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="ddb0f-182">이 라이선스가 없는 경우 피어 투 피어 파일 공유는 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ddb0f-183">애플리케이션 플랫폼</span><span class="sxs-lookup"><span data-stu-id="ddb0f-183">Application platform</span></span></td>
<td><span data-ttu-id="ddb0f-184">사용자는 회사 정책에 따라 사용할 수 있도록 지정된 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="ddb0f-185">여기에서 자세히 알아보십시오. 다음의 앱에 <a href="/microsoftteams/admin-settings">대한 관리자 Teams</a></span><span class="sxs-lookup"><span data-stu-id="ddb0f-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ddb0f-186">보안 및 규정 준수 기능</span><span class="sxs-lookup"><span data-stu-id="ddb0f-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="ddb0f-187">보존 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="ddb0f-188">채널 메시지에 대한 준수에 대한 eDiscovery 및 법적 보류가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="ddb0f-189">DLP(데이터 손실 방지 정책)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="ddb0f-190">전체 기능 집합은 Exchange Online. Exchange 대부분의 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="ddb0f-191">전체 목록은 을 Exchange 및 Teams <a href="/MicrosoftTeams/exchange-teams-interact">참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="ddb0f-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="ddb0f-192">또는 Lync Server가 없는 조직에 비즈니스용 Skype 단계</span><span class="sxs-lookup"><span data-stu-id="ddb0f-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="ddb0f-193">위의 시작 섹션에서 자세히 설명한 전제 요건 충족</span><span class="sxs-lookup"><span data-stu-id="ddb0f-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="ddb0f-194">테넌트를 Teams 전용 모드로 전환합니다( 기존 테넌트에만 해당): 공존 및 업그레이드 설정 설정 [을 선택합니다.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="ddb0f-195">회사의 비즈니스/회사 정책에 따라 테넌트 [구성:](enable-features-office-365.md)조직의 Microsoft Teams 설정 관리</span><span class="sxs-lookup"><span data-stu-id="ddb0f-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="ddb0f-196">사용자에 Teams 클라이언트 배포: [클라이언트를](get-clients.md) Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="ddb0f-197">채택 프로그램 드라이브</span><span class="sxs-lookup"><span data-stu-id="ddb0f-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="ddb0f-198">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="ddb0f-199">Microsoft Teams 빠른 시작 검사 목록</span><span class="sxs-lookup"><span data-stu-id="ddb0f-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="ddb0f-200">다른 워크로드를 Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="ddb0f-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="ddb0f-201">비즈니스용 Skype **<span class="underline"></span>** 또는 Lync 서버가 있는 조직</span><span class="sxs-lookup"><span data-stu-id="ddb0f-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="ddb0f-202">이 시작점은 조직에서 2019 또는 2015+비즈니스용 Skype 또는 Lync 2013+ 온-프레미스 서버를 활용하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="ddb0f-203">이미 프레미스 서버에서 프레미스 서버로 마이그레이션하는 조직에 대한 광범위한 Teams 이러한 시나리오에 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="ddb0f-204">이 지침은 Teams 또는 Teams 첫 번째 애플리케이션인 시나리오에 Microsoft 365 Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ddb0f-205">다음 표에서는 핵심 서비스에 대한 고급 구성 및 최종 사용자 Teams 자세히 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ddb0f-206">항목</span><span class="sxs-lookup"><span data-stu-id="ddb0f-206">Item</span></span></th>
<th><span data-ttu-id="ddb0f-207">참고</span><span class="sxs-lookup"><span data-stu-id="ddb0f-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ddb0f-208">테넌트 Teams 구성</span><span class="sxs-lookup"><span data-stu-id="ddb0f-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="ddb0f-209">섬 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ddb0f-210">채팅/외부 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="ddb0f-211">자체 테넌트 내에서만 내부적으로 외부 통신(페더화)은 사용자 비즈니스용 Skype 또는 Lync 서버 배포를 통해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ddb0f-212">모임 만들기 및 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="ddb0f-213">추가 기능을 통해 내부 및 외부 Outlook 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="ddb0f-214">PSTN 전화 접속 및 전화 접속 기능은 오디오 회의 라이선스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="ddb0f-215">Teams 액세스하려면 Exchange 하이브리드가 Exchange 배포된 2016 CU3+ Exchange 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="ddb0f-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">하이브리드 구성 마법사를 사용하여 하이브리드 배포를 만들 수 있습니다.</a></span><span class="sxs-lookup"><span data-stu-id="ddb0f-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="ddb0f-217">관리자는 비즈니스용 Skype Outlook Teams 모임 정책의 PreferredMeetingProviderForIslandsMode 특성인<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy를</a>통해 추가 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="ddb0f-218">호출 기능</span><span class="sxs-lookup"><span data-stu-id="ddb0f-218">Calling Features</span></span><br />
<span data-ttu-id="ddb0f-219">VoIP/PSTN에서 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="ddb0f-220">테넌트에 내부적으로 VoIP를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="ddb0f-221">PSTN 또는 Calling Plan 서비스는 사용자가 사용자만 환경으로 이동될 때까지 Teams 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ddb0f-222">Teams 및 채널 공동 작업에서 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="ddb0f-223">규정 준수 기능을 포함한 전체 환경을 SharePoint 온라인 라이선스를 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="ddb0f-224">기존 프레미스 SharePoint 마이그레이션할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ddb0f-225">비즈니스용 OneDrive(P2P 파일 공유)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="ddb0f-226">비즈니스용 OneDrive 사용자가 온라인 라이선스를 할당해야 SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="ddb0f-227">이 라이선스가 없는 경우 피어 파일 공유는 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ddb0f-228">애플리케이션 플랫폼</span><span class="sxs-lookup"><span data-stu-id="ddb0f-228">Application platform</span></span></td>
<td><span data-ttu-id="ddb0f-229">사용자는 회사 정책에 따라 사용할 수 있도록 지정된 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="ddb0f-230">여기에서 자세히 알아보십시오. 다음의 앱에 <a href="/microsoftteams/admin-settings">대한 관리자 Teams</a></span><span class="sxs-lookup"><span data-stu-id="ddb0f-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ddb0f-231">보안 및 규정 준수 기능</span><span class="sxs-lookup"><span data-stu-id="ddb0f-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="ddb0f-232">보존 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="ddb0f-233">채널 메시지에 대한 준수에 대한 eDiscovery 및 법적 보류가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="ddb0f-234">DLP(데이터 손실 방지 정책)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="ddb0f-235">전체 기능 집합은 Exchange Online. Exchange 대부분의 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="ddb0f-236">전체 목록은 상호 작용하는 Exchange <a href="/MicrosoftTeams/exchange-teams-interact">Teams 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="ddb0f-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="ddb0f-237">조직에 대한 사용 비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="ddb0f-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="ddb0f-238">위의 시작 섹션에 자세히 설명된 전제 요건을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="ddb0f-239">테넌트 전환(2019년 9월 1일 이후 프로비전된 테넌트의 경우 지원에 문의하여 변경)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="ddb0f-240">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="ddb0f-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="ddb0f-241">회사의 비즈니스/회사 정책에 따라 테넌트 구성</span><span class="sxs-lookup"><span data-stu-id="ddb0f-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="ddb0f-242">조직에서 Microsoft Teams 설정 관리</span><span class="sxs-lookup"><span data-stu-id="ddb0f-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="ddb0f-243">클라이언트 Teams 배포</span><span class="sxs-lookup"><span data-stu-id="ddb0f-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="ddb0f-244">Teams용 클라이언트 가져오기</span><span class="sxs-lookup"><span data-stu-id="ddb0f-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="ddb0f-245">채택 프로그램 드라이브</span><span class="sxs-lookup"><span data-stu-id="ddb0f-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="ddb0f-246">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="ddb0f-247">Microsoft Teams 빠른 시작 검사 목록</span><span class="sxs-lookup"><span data-stu-id="ddb0f-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="ddb0f-248">다른 워크로드를 Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="ddb0f-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="ddb0f-249">비즈니스용 Skype 및 Lync 서버의 권장 업그레이드 경로를 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="ddb0f-250">비즈니스용 Skype 프레미스에서 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="ddb0f-251">닫기 문</span><span class="sxs-lookup"><span data-stu-id="ddb0f-251">Closing statement</span></span>

<span data-ttu-id="ddb0f-252">Microsoft Teams 모든 직원, 정보 근로자 및 Frontline 작업자를 단일 플랫폼에서 함께 사용할 수 있는 지원자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="ddb0f-253">오늘 [시작할 수](https://products.office.com/microsoft-teams/group-chat-software) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="ddb0f-254">여기에서 모든 최신 공지 및 월별 제품 업데이트를 계속 연락할 수 [있습니다.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="ddb0f-255">또한 전 세계 기업이 현재 COVID-19 상황을 관리하고 있는 동안 조직에서 최대의 영향력을 위해 Teams 일련의 콘텐츠를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="ddb0f-256">[COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/) 기간 동안 고객에 대한 약속</span><span class="sxs-lookup"><span data-stu-id="ddb0f-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="ddb0f-257">2주: 원격 작업에서 배운 사항</span><span class="sxs-lookup"><span data-stu-id="ddb0f-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="ddb0f-258">온라인 모임 및 이벤트 배달</span><span class="sxs-lookup"><span data-stu-id="ddb0f-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="ddb0f-259">중소 기업이 Teams와 원격으로 작업할 수 있도록 지원</span><span class="sxs-lookup"><span data-stu-id="ddb0f-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="ddb0f-260">라이브 이벤트의 디지털 변환: 최전선에서 Bob Bejan의 관찰</span><span class="sxs-lookup"><span data-stu-id="ddb0f-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="ddb0f-261">Microsoft IT가 직원들의 원격 작업을 가능하게하는 9가지 방법</span><span class="sxs-lookup"><span data-stu-id="ddb0f-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="ddb0f-262">원격으로 작업하고 보안을 유지하며 CISOS에 대한 팁</span><span class="sxs-lookup"><span data-stu-id="ddb0f-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="ddb0f-263">교사와 학생들이 원격 학습으로 전환할 수 있도록 지원</span><span class="sxs-lookup"><span data-stu-id="ddb0f-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="ddb0f-264">원격으로 작업하는 동안 생산성을 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="ddb0f-265">지원 서비스 참조</span><span class="sxs-lookup"><span data-stu-id="ddb0f-265">Support Services reference</span></span>

<span data-ttu-id="ddb0f-266">Teams, Exchange Online SharePoint, 비즈니스용 OneDrive 및 Microsoft 365 그룹에 의존하여 사용자에게 완전히 통합된 Microsoft 365 Office 365 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="ddb0f-267">위에서 설명한 Teams 제한된 기능을 통해 이러한 서비스를 전체 배포하지 않고도 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="ddb0f-268">여기에서 Teams 및 전제품에 대해 자세히 [Teams.](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="ddb0f-269">위에 나열된 각 서비스에 대한 자세한 설명은 아래 링크를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="ddb0f-270">Exchange Online 기능은 일정을 관리하고 피어 투 피어 메시지를 저장하는 데 Teams.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="ddb0f-271">자세한 내용은 상호 작용 방법 Exchange [Teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddb0f-272">Teams 및 Exchange 조직 간에 OAuth 인증 구성에 설명된 Exchange OAuth 인증 프로토콜을 Exchange Exchange Online [구성해야 합니다.](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="ddb0f-273">SharePoint /비즈니스용 OneDrive 1:1 또는 그룹 채팅에서 파일 공유에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="ddb0f-274">자세한 내용은 온라인 및 SharePoint 및 비즈니스용 OneDrive [를 Microsoft Teams.](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="ddb0f-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="ddb0f-275">[Microsoft 365 그룹은](office-365-groups.md) 팀 및 채널 만들기/관리에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddb0f-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ddb0f-276">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ddb0f-276">Related topics</span></span>

[<span data-ttu-id="ddb0f-277">Microsoft Teams IT 아키텍처 및 전화 통신 솔루션 포스터</span><span class="sxs-lookup"><span data-stu-id="ddb0f-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="ddb0f-278">비즈니스용 Skype 서버와 Office 365 간의 하이브리드 연결 플랜</span><span class="sxs-lookup"><span data-stu-id="ddb0f-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="ddb0f-279">원격 작업자를 사용하여 Teams</span><span class="sxs-lookup"><span data-stu-id="ddb0f-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="ddb0f-280">원격으로 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ddb0f-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)