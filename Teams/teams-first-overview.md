---
title: Microsoft 팀 먼저 롤아웃
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
description: 이 지침을 사용 하 여 Microsoft 팀을 첫 번째 Microsoft 365 또는 Office 365 작업 부하로 롤아웃할 수 있습니다.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84408fdb6d58e755d0eb4c775d1954f22791264c
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691004"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="cd4dc-103">Microsoft 팀 먼저 롤아웃</span><span class="sxs-lookup"><span data-stu-id="cd4dc-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="cd4dc-104">Microsoft 팀은 직원 들이 전세계에 있는 직원의 실제 근무 시간에 따라 서로 연결 하 고 공동 작업 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="cd4dc-105">팀 내에서 채팅, 영상 모임, Office 문서 공동 작업을 할 수 있습니다. 회사가 생산성을 유지 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="cd4dc-106">소규모 기업, 비 손익 또는 대규모 조직에 관계 없이 다른 Office 앱 이나 서비스를 배포 하기 전에 Microsoft 365 또는 Office 365 제품군의 첫 번째 작업 부하로 팀을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="cd4dc-107">이 문서에서는 "팀 먼저" 접근 방법으로 수행 해야 하는 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd4dc-108">팀은 조직의 첫 번째 클라우드가 배포할 수 있지만 전체 클라우드 배포 전략의 일부로 팀을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="cd4dc-109">다른 Microsoft 365 또는 Office 365 서비스와 팀이 배포 되는 경우 (첫 번째 단계 대신) 다음 작업 부하로 인해 [팀을 롤아웃 하는 방법](How-to-roll-out-teams.md)부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="cd4dc-110">여기에서 시작</span><span class="sxs-lookup"><span data-stu-id="cd4dc-110">Start here</span></span>

<span data-ttu-id="cd4dc-111">먼저 팀을 배포 하려면 최소한 몇 가지 사전 요구 사항이 충족 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="cd4dc-112">다음 목록에는 팀을 사용 하도록 설정 하기 전에 조직에 대해 필요한 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="cd4dc-113">도메인 이름으로 구성 된 Microsoft 365 또는 Office 365 조직</span><span class="sxs-lookup"><span data-stu-id="cd4dc-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="cd4dc-114">필수 특성이 모두 테 넌 트에서 동기화 되는 Azure Active Directory 연결 (AAD connect) 또는 유사한 클라우드 id 동기화 솔루션</span><span class="sxs-lookup"><span data-stu-id="cd4dc-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="cd4dc-115">AAD 동기화와 동기화 된 특성을 이해 하려면 [AZURE AD Connect 동기화 읽기: 특성을 Azure Active Directory와 동기화](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) 됨</span><span class="sxs-lookup"><span data-stu-id="cd4dc-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="cd4dc-116">팀에 할당 된 적절 한 사용자 라이선스</span><span class="sxs-lookup"><span data-stu-id="cd4dc-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="cd4dc-117">팀 라이선스를 이해 하려면 [Microsoft 팀 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="cd4dc-118">조직에서 팀에 대해 준비한 네트워크</span><span class="sxs-lookup"><span data-stu-id="cd4dc-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="cd4dc-119">네트워크 준비를 이해 하려면 [팀에 대 한 조직의 네트워크 준비](prepare-network.md)를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="cd4dc-120">Microsoft 365 또는 Office 365에서 Exchange, Sharepoint, 비즈니스용 OneDrive에 대 한 네트워크 액세스를 허용 합니다. [office 365 url 및 IP 주소 범위](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="cd4dc-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="cd4dc-121">2019 년 9 월 1 일 이후에 만든 테 넌 트를 팀 전용 모드로 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="cd4dc-122">비즈니스용 Skype 서버를 배포 하 고 테 넌 트가 2019 년 9 월 1 일 이후에 프로 비전 된 경우 고객 지원에 문의 하 여 팀에 공존 기능을 사용 하도록 설정 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="cd4dc-123">사용자에 게 팀 라이선스를 할당 <span class="underline">하기 전에</span> ' 조직 전체 업그레이드 정책 '이 ' 섬 모드 '로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="cd4dc-124">마이그레이션 시작 지점</span><span class="sxs-lookup"><span data-stu-id="cd4dc-124">Migration Starting points</span></span>

<span data-ttu-id="cd4dc-125">Microsoft 365 또는 Office 365에 대 한 여행, 시작 지점 및 온-프레미스 비즈니스용 Skype 또는 Lync server에 따라 팀에서 사용할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="cd4dc-126">다음 섹션에서는 위의 사전 요구 사항 외에도 기본적인 기능과 구성 옵션에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="cd4dc-127">이 출발점 시나리오를 다음 항목으로 세분 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="cd4dc-128">**테 넌 트 팀 구성**: 테 넌 트 및 사용자 모드는 받는 사람의 동작을 제어 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="cd4dc-129">이러한 설정은 테 넌 트 수준이 나 조직의 사용자 수준에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="cd4dc-130">자세한 내용은 [비즈니스용 Skype를 사용 하 여](coexistence-chat-calls-presence.md)함께 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="cd4dc-131">**팀의 채팅/외부 통신**: 채팅 서비스는 및 조직 내에서 또는 조직 외부의 피어 투 피어 또는 그룹 채팅 대화를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="cd4dc-132">외부 통신은 비즈니스용 Skype의 페더레이션이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="cd4dc-133">**팀에서 모임 만들기 및 보기**: 사용자가 언제 든 지 Outlook 팀 추가 기능을 통해 온라인 모임을 만들 수 있으며, 사용자가 사용이 허가 되 면 모든 시나리오에서 PSTN 전화 접속을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="cd4dc-134">사용자의 Exchange 사서함에 있는 비즈니스용 Skype 스토어 일정 정보</span><span class="sxs-lookup"><span data-stu-id="cd4dc-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="cd4dc-135">온-프레미스 Exchange server는 팀 클라이언트가 사용자의 사서함과 상호 작용할 수 있으려면 Exchange Server 2016 CU3 이상 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="cd4dc-136">Exchange 사서함 액세스 권한이 없는 경우 팀의 일정 아이콘은 표시 되지 않으며 사용자는 팀 클라이언트에서 모임을 보거나 만들거나 수정할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="cd4dc-137">**팀에서 기능 voip/PSTN 통화**: 통화는 Voip (VOICE over IP) 또는 Pstn (공공 교환 전화 네트워크) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="cd4dc-138">VoIP 연결은 팀 클라이언트 간에 기본적으로 발생 하는 반면, 사용자가 외부 전화 번호로 전화를 걸 때 PSTN 연결이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="cd4dc-139">팀은 두 가지 유형의 PSTN 연결을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="cd4dc-140">Microsoft는 microsoft가 사용자의 전화 번호를 포함 하는 전화 통신 인프라를 제공 하는 경우 또는 팀 사용자를 위해 SBC (세션 경계 컨트롤러)를 통해 고객이 전화 접속 연결을 제공 하는 직접 라우팅 구성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="cd4dc-141">자세한 내용은 [사용자에 게 적합 한 통화 요금제](calling-plan-landing-page.md) 와 [전화 시스템 직접 라우팅을](direct-routing-landing-page.md)참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="cd4dc-142">팀 **에서 팀과 채널 공동 작업**: 팀에서 팀은 작업, 프로젝트 또는 일반적인 관심사에 대해 함께 제공 되는 사용자 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="cd4dc-143">팀은 채널으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-143">Teams are made up of channels.</span></span> <span data-ttu-id="cd4dc-144">각 채널은 "팀 이벤트", 부서 이름 등의 주제를 중심으로 작성 되거나 재미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="cd4dc-145">채널은 모임을 개최 하 고 대화를 하며 파일 작업을 함께 수행 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="cd4dc-146">공동 작업 중</span><span class="sxs-lookup"><span data-stu-id="cd4dc-146">During collaboration</span></span>

<span data-ttu-id="cd4dc-147">**비즈니스용 onedrive (P2P 파일 공유) 팀의**경우 팀 사용자는 비즈니스용 Onedrive 또는 Citrix 파일, DropBox, Box, Google Drive와 같은 기타 P2P 공유 파일 프로그램을 사용 하 여 파일을 피어 투 피어에 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="cd4dc-148">비즈니스용 OneDrive의 경우 사용자에 게 SharePoint Online 라이선스가 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="cd4dc-149">**응용 프로그램 플랫폼**: 앱은 조직의 다양 한 도구를 제공 하 여 팀을 최대한 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="cd4dc-150">이러한 앱은 Microsoft에서 제공 하는 제 3 자, 메시징 확장, 커넥터, 인공 지능 기능을 기반으로 하거나 조직의 개발자가 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="cd4dc-151">**보안 및 규정 준수 기능:** 팀에는 보존 정책, DLP (데이터 손실 방지), eDiscovery 및 채널에 대 한 법적 고 지 사항, 채팅 및 파일, 감사 로그 검색을 비롯 하 여 규정 준수 영역에 도움이 되는 다양 한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="cd4dc-152">자세한 내용은 [Microsoft 팀의 보안 및 규정 준수](security-compliance-overview.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="cd4dc-153">이동 eDiscovery 기능에는 E5 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="cd4dc-154">[라이선스 옵션을 비교](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="cd4dc-155">[Exchange 및 Microsoft 팀이 어떻게 상호 작용](exchange-teams-interact.md) 하 여 시나리오에서 사용할 수 있는 규정 준수 기능에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="cd4dc-156">비즈니스용 Skype 또는 Lync server가 **<span class="underline">없는</span>** 조직</span><span class="sxs-lookup"><span data-stu-id="cd4dc-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="cd4dc-157">이 시작 단계에서는 조직이 비즈니스용 Skype 또는 Lync server를 사용 하지 않는 것으로 가정 하 고, 현재 팀이 Microsoft 365 또는 Office 365의 첫 번째 응용 프로그램이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-157">This starting point assumes that your organization does not utilize Skype for Business or Lync server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="cd4dc-158">다음 표에서는 핵심 서비스에 대 한 팀의 상위 수준 구성과 최종 사용자 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cd4dc-159">항목</span><span class="sxs-lookup"><span data-stu-id="cd4dc-159">Item</span></span></th>
<th><span data-ttu-id="cd4dc-160">상속자</span><span class="sxs-lookup"><span data-stu-id="cd4dc-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cd4dc-161">테 넌 트 팀 구성</span><span class="sxs-lookup"><span data-stu-id="cd4dc-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="cd4dc-162">팀 전용 모드, 모든 채팅 및 통화 기능은 팀 에서만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-162">Teams Only mode, all chat and calling features are in Teams Only</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd4dc-163">팀에서 채팅/외부 통신</span><span class="sxs-lookup"><span data-stu-id="cd4dc-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="cd4dc-164">내부 (Microsoft 365 또는 Office 365 조직 내) 및 팀에서 가능 하 게 하는 외부 채팅 통신</span><span class="sxs-lookup"><span data-stu-id="cd4dc-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams</span></span></p>
<p><span data-ttu-id="cd4dc-165"><em>참고: DNS 항목은 외부 액세스용으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="cd4dc-166">비즈니스용 skype for 구내 또는 Microsoft 365 또는 Office 365을 사용 하지 않는 경우에도 Lync 및 비즈니스용 skype 환경과의 페더레이션을 허용 하는 skype for Business DNS 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments.</span></span><br /><span data-ttu-id="cd4dc-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">외부 도메인 이름 시스템 레코드</a></em></span><span class="sxs-lookup"><span data-stu-id="cd4dc-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd4dc-168"><em>팀에서 모임 만들기 및 보기</em></span><span class="sxs-lookup"><span data-stu-id="cd4dc-168"><em>Create and view Meetings in Teams</em></span></span></td>
<td><p><span data-ttu-id="cd4dc-169"><em>Outlook 추가 기능을 통해 모임을 만들 수 있습니다.</em></span><span class="sxs-lookup"><span data-stu-id="cd4dc-169"><em>Able to create meetings via Outlook add-in</em></span></span></p>
<p><span data-ttu-id="cd4dc-170"><em>PSTN 전화 접속 및 전화 접속 기능은 오디오 회의 라이선스를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-170"><em>PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="cd4dc-171">참고: 팀 일정 액세스에는 Exchange 하이브리드이 설정 된 Exchange 2016 CU3 이상 + 온-프레미스를 배포 해야 합니다. 하이브리드 <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">구성 마법사를 사용 하 여 하이브리드 배포 만들기</a></span><span class="sxs-lookup"><span data-stu-id="cd4dc-171">Note: Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span><br />
<span data-ttu-id="cd4dc-172">Exchange 하이브리드 구성 외에 Exchange OAuth 인증 설정: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">exchange 및 Exchange Online 조 직 간의 oauth 인증 구성</a></em></span><span class="sxs-lookup"><span data-stu-id="cd4dc-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations</a></em></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd4dc-173">통화 기능</span><span class="sxs-lookup"><span data-stu-id="cd4dc-173">Calling Features</span></span><br />
<span data-ttu-id="cd4dc-174">팀의 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="cd4dc-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="cd4dc-175">테 넌 트를 내부 및 외부적으로 VoIP를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-175">VoIP internally and externally to the tenant is available</span></span></p>
<p><span data-ttu-id="cd4dc-176">Microsoft 전화 시스템을 통해 PSTN 서비스를 구성 하 고 Microsoft 호출 계획 또는 직접 라우팅을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd4dc-177">팀에서 팀 및 채널 공동 작업</span><span class="sxs-lookup"><span data-stu-id="cd4dc-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="cd4dc-178">규정 준수 기능을 비롯 한 모든 환경을 위해 사용자에 게 SharePoint Online 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="cd4dc-179">기존 온-프레미스 SharePoint 사이트의 마이그레이션은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd4dc-180">비즈니스용 OneDrive (P2P 파일 공유)</span><span class="sxs-lookup"><span data-stu-id="cd4dc-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="cd4dc-181">비즈니스용 OneDrive에는 사용자가 SharePoint Online 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="cd4dc-182">이 라이선스 없이 피어 투 피어 파일 공유를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd4dc-183">응용 프로그램 플랫폼</span><span class="sxs-lookup"><span data-stu-id="cd4dc-183">Application platform</span></span></td>
<td><span data-ttu-id="cd4dc-184">사용자는 회사 정책에 따라 사용할 수 있도록 지정 된 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="cd4dc-185">자세한 정보: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">팀의 앱에 대 한 관리자 설정</a></span><span class="sxs-lookup"><span data-stu-id="cd4dc-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd4dc-186">보안 및 규정 준수 기능</span><span class="sxs-lookup"><span data-stu-id="cd4dc-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="cd4dc-187">보존 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-187">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="cd4dc-188">채널 메시지의 정책 준수에 대 한 eDiscovery 및 법률 보류가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-188">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="cd4dc-189">데이터 손실 방지 정책 (DLP)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-189">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="cd4dc-190">Exchange Online과 함께 사용할 수 있는 모든 기능 집합 Exchange 온-프레미스에서는 이러한 기능 대부분을 지원 하며 Exchange와 팀이 전체 목록에 대해 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">상호 작용 하는 방법</a> 에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-190">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a> for full list.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="cd4dc-191">비즈니스용 Skype 또는 Lync Server를 사용 하지 않는 조직의 사용 단계</span><span class="sxs-lookup"><span data-stu-id="cd4dc-191">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="cd4dc-192">위의 시작 위치 섹션에 자세히 설명 된 필수 조건을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-192">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="cd4dc-193">테 넌 트만 팀 전용 모드로 전환 (기존 테 넌 트에만 해당): [공존 및 업그레이드 설정을 설정](setting-your-coexistence-and-upgrade-settings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-193">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="cd4dc-194">회사의 비즈니스/회사 정책에 따라 테 넌 트를 구성 합니다. [조직에 대 한 Microsoft 팀 설정을 관리](enable-features-office-365.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-194">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="cd4dc-195">팀 클라이언트를 사용자에 게 배포: [팀 용 클라이언트 가져오기](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="cd4dc-195">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="cd4dc-196">채택을 프로그램 구동</span><span class="sxs-lookup"><span data-stu-id="cd4dc-196">Drive your adoption program</span></span>  
    [<span data-ttu-id="cd4dc-197">Microsoft 팀 채택</span><span class="sxs-lookup"><span data-stu-id="cd4dc-197">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="cd4dc-198">Microsoft 팀 채택 빠른 시작 검사 목록</span><span class="sxs-lookup"><span data-stu-id="cd4dc-198">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="cd4dc-199">다른 작업을 Microsoft 365 또는 Office 365로 이동 하기 위해 계획 시작</span><span class="sxs-lookup"><span data-stu-id="cd4dc-199">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="cd4dc-200">비즈니스용 Skype 또는 Lync server **<span class="underline">를 사용 하는</span>** 조직</span><span class="sxs-lookup"><span data-stu-id="cd4dc-200">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="cd4dc-201">이 시작 단계에서는 조직에서 비즈니스용 Skype 2019 또는 2015 + 또는 Lync 2013 + server 온-프레미스를 이용 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-201">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="cd4dc-202">지금까지 온-프레미스 서버에서 팀으로 마이그레이션하는 조직에 대 한 광범위 한 지침이 있으며, 이러한 시나리오를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-202">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="cd4dc-203">이 지침은 팀이 Microsoft 365 또는 Office 365에서 사용 하는 첫 번째 응용 프로그램에 해당 하는 시나리오와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-203">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="cd4dc-204">다음 표에서는 핵심 서비스에 대 한 팀의 상위 수준 구성과 최종 사용자 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-204">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cd4dc-205">항목</span><span class="sxs-lookup"><span data-stu-id="cd4dc-205">Item</span></span></th>
<th><span data-ttu-id="cd4dc-206">상속자</span><span class="sxs-lookup"><span data-stu-id="cd4dc-206">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cd4dc-207">테 넌 트 팀 구성</span><span class="sxs-lookup"><span data-stu-id="cd4dc-207">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="cd4dc-208">아일랜드 모드</span><span class="sxs-lookup"><span data-stu-id="cd4dc-208">Islands mode</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd4dc-209">팀에서 채팅/외부 통신</span><span class="sxs-lookup"><span data-stu-id="cd4dc-209">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="cd4dc-210">내부 테 넌 트에만 해당 됩니다. 비즈니스용 Skype 또는 Lync server 배포를 통해 외부 통신 (페더레이션)이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-210">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd4dc-211">팀에서 모임 만들기 및 보기</span><span class="sxs-lookup"><span data-stu-id="cd4dc-211">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="cd4dc-212">Outlook 추가 기능을 통해 모임을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-212">Able to create meetings via Outlook add-in</span></span></p>
<p><span data-ttu-id="cd4dc-213">PSTN 전화 접속 및 전화 접속 기능은 오디오 회의 라이선스를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-213">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="cd4dc-214">팀 일정 액세스에는 Exchange 하이브리드이 설정 된 Exchange 2016 CU3 이상 + 온-프레미스를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-214">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="cd4dc-215">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">하이브리드 구성 마법사를 사용 하 여 하이브리드 배포 만들기</a></span><span class="sxs-lookup"><span data-stu-id="cd4dc-215">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd4dc-216">통화 기능</span><span class="sxs-lookup"><span data-stu-id="cd4dc-216">Calling Features</span></span><br />
<span data-ttu-id="cd4dc-217">팀의 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="cd4dc-217">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="cd4dc-218">테 넌 트에 대 한 VoIP는 내부적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-218">VoIP internally to the tenant is available</span></span></p>
<p><span data-ttu-id="cd4dc-219">사용자가 팀 전용 환경으로 이동할 때까지 PSTN 또는 통화 계획 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-219">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd4dc-220">팀에서 팀 및 채널 공동 작업</span><span class="sxs-lookup"><span data-stu-id="cd4dc-220">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="cd4dc-221">규정 준수 기능을 비롯 한 모든 환경을 위해 사용자에 게 SharePoint Online 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-221">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="cd4dc-222">기존 온-프레미스 SharePoint 사이트의 마이그레이션은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-222">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd4dc-223">비즈니스용 OneDrive (P2P 파일 공유)</span><span class="sxs-lookup"><span data-stu-id="cd4dc-223">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="cd4dc-224">비즈니스용 OneDrive에는 사용자가 SharePoint Online 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-224">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="cd4dc-225">이 사용권을 사용 하지 않는 경우에는 피어 별 파일 공유를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-225">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd4dc-226">응용 프로그램 플랫폼</span><span class="sxs-lookup"><span data-stu-id="cd4dc-226">Application platform</span></span></td>
<td><span data-ttu-id="cd4dc-227">사용자는 회사 정책에 따라 사용할 수 있도록 지정 된 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-227">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="cd4dc-228">자세한 정보: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">팀의 앱에 대 한 관리자 설정</a></span><span class="sxs-lookup"><span data-stu-id="cd4dc-228">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd4dc-229">보안 및 규정 준수 기능</span><span class="sxs-lookup"><span data-stu-id="cd4dc-229">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="cd4dc-230">보존 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-230">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="cd4dc-231">채널 메시지의 정책 준수에 대 한 eDiscovery 및 법률 보류가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-231">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="cd4dc-232">데이터 손실 방지 정책 (DLP)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-232">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="cd4dc-233">Exchange Online에서 사용할 수 있는 전체 기능 집합 Exchange 온-프레미스에서는 이러한 기능을 대부분 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-233">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="cd4dc-234"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange와 Teams의 상호 작용 방법</a></span><span class="sxs-lookup"><span data-stu-id="cd4dc-234"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<ul>
<li><p><span data-ttu-id="cd4dc-235">전체 목록</span><span class="sxs-lookup"><span data-stu-id="cd4dc-235">for full list</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="cd4dc-236">비즈니스용 Skype 서버를 사용 하는 조직에 대 한 사용 단계</span><span class="sxs-lookup"><span data-stu-id="cd4dc-236">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="cd4dc-237">위의 시작 위치 섹션에 설명 된 필수 조건을 충족 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-237">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="cd4dc-238">테 넌 트를 아일랜드 모드로 전환 (9/1/2019 후에 테 넌 트를 프로비저닝된 경우 지원 팀에 문의 하 여이 변경 사항 수행)</span><span class="sxs-lookup"><span data-stu-id="cd4dc-238">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="cd4dc-239">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="cd4dc-239">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="cd4dc-240">회사의 비즈니스/회사 정책에 따라 테 넌 트 구성</span><span class="sxs-lookup"><span data-stu-id="cd4dc-240">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="cd4dc-241">조직에서 Microsoft Teams 설정 관리</span><span class="sxs-lookup"><span data-stu-id="cd4dc-241">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="cd4dc-242">팀 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="cd4dc-242">Deploy the Teams client</span></span>  
    [<span data-ttu-id="cd4dc-243">Teams용 클라이언트 가져오기</span><span class="sxs-lookup"><span data-stu-id="cd4dc-243">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="cd4dc-244">채택을 프로그램 구동</span><span class="sxs-lookup"><span data-stu-id="cd4dc-244">Drive your adoption program</span></span>  
    [<span data-ttu-id="cd4dc-245">Microsoft 팀 채택</span><span class="sxs-lookup"><span data-stu-id="cd4dc-245">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="cd4dc-246">Microsoft 팀 채택 빠른 시작 검사 목록</span><span class="sxs-lookup"><span data-stu-id="cd4dc-246">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="cd4dc-247">다른 작업을 Microsoft 365 또는 Office 365로 이동 하기 위해 계획 시작</span><span class="sxs-lookup"><span data-stu-id="cd4dc-247">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="cd4dc-248">비즈니스용 Skype 하이브리드 설정 및 비즈니스용 Skype 및 Lync server의 권장 업그레이드 경로 팔 로우</span><span class="sxs-lookup"><span data-stu-id="cd4dc-248">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="cd4dc-249">비즈니스용 Skype 온-프레미스에서 팀으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="cd4dc-249">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="cd4dc-250">닫는 문</span><span class="sxs-lookup"><span data-stu-id="cd4dc-250">Closing statement</span></span>

<span data-ttu-id="cd4dc-251">Microsoft 팀은 조직의 모든 직원, 정보 근로자 및 Firstline worker를 단일 플랫폼에 함께 가져오는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-251">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="cd4dc-252">지금 바로 [시작할](https://products.office.com/microsoft-teams/group-chat-software) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-252">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="cd4dc-253">[여기](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)에 있는 모든 최신 공지 사항 및 월간 제품 업데이트를 계속 해 서 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-253">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="cd4dc-254">또한 전세계의 회사가 현재 COVID-19 상황을 관리 하는 경우 팀을 활용 하는 데 도움이 되는 일련의 콘텐츠를 만들어 조직의 조직에서 최대한의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-254">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="cd4dc-255">[COVID-19 중 고객의 약정](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="cd4dc-255">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="cd4dc-256">2 주 후: 원격 작업에 대해 배운 내용</span><span class="sxs-lookup"><span data-stu-id="cd4dc-256">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="cd4dc-257">온라인 모임 및 이벤트 제공</span><span class="sxs-lookup"><span data-stu-id="cd4dc-257">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="cd4dc-258">중소 기업이 Teams와 원격으로 작업할 수 있도록 지원</span><span class="sxs-lookup"><span data-stu-id="cd4dc-258">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="cd4dc-259">라이브 이벤트의 디지털 변환: 일선에서 Bob의 1 월 관측값</span><span class="sxs-lookup"><span data-stu-id="cd4dc-259">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="cd4dc-260">Microsoft IT가 직원들의 원격 작업을 가능하게하는 9가지 방법</span><span class="sxs-lookup"><span data-stu-id="cd4dc-260">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="cd4dc-261">원격 작업, 보안 유지 — CISOs에 대 한 팁</span><span class="sxs-lookup"><span data-stu-id="cd4dc-261">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="cd4dc-262">교사와 학생이 원격 학습으로 전환 하도록 도와주는 경우</span><span class="sxs-lookup"><span data-stu-id="cd4dc-262">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="cd4dc-263">Microsoft 팀으로 원격 작업 하는 동안 생산성 유지</span><span class="sxs-lookup"><span data-stu-id="cd4dc-263">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="cd4dc-264">지원 서비스 참조</span><span class="sxs-lookup"><span data-stu-id="cd4dc-264">Support Services reference</span></span>

<span data-ttu-id="cd4dc-265">팀은 Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 365 그룹에 의존 하 여 사용자에 게 완전 통합 Microsoft 365 또는 Office 365 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-265">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="cd4dc-266">위에서 언급 한 것 처럼 팀은 제한 된 기능으로 이러한 서비스를 완전 하 게 배포 하지 않고 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-266">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="cd4dc-267">팀에 대 한 자세한 내용과 해당 필수 구성 요소를 읽어 보세요. [팀에 오신 것을 환영](teams-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-267">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="cd4dc-268">위에 나열 된 각 서비스에 대 한 자세한 내용은 아래 링크를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-268">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="cd4dc-269">Exchange Online은 일정 기능에 사용 되며 팀에 피어 투 피어 메시지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-269">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="cd4dc-270">자세한 내용은 [Exchange 및 팀의 상호 작용 방법](exchange-teams-interact.md) 읽기를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-270">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd4dc-271">Exchange 온-프레미스와 팀 interop를 사용 하는 경우 [exchange 및 Exchange Online 조 직 간의 OAuth 인증 구성](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)에 설명 된 대로 새 Exchange OAuth 인증 프로토콜을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-271">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="cd4dc-272">SharePoint는 채널에서 파일을 공유 하는 데 사용 되는 반면, OneDrive for Business는 1:1 또는 그룹 채팅에서 파일을 공유 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-272">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="cd4dc-273">자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive에서 Microsoft 팀과 상호 작용 하는 방법을](sharepoint-onedrive-interact.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-273">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="cd4dc-274">[Microsoft 365 그룹](office-365-groups.md) 은 팀 및 채널 생성/관리에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4dc-274">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="cd4dc-275">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cd4dc-275">Related topics</span></span>

[<span data-ttu-id="cd4dc-276">Microsoft Teams IT 아키텍처 및 전화 통신 솔루션 포스터</span><span class="sxs-lookup"><span data-stu-id="cd4dc-276">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="cd4dc-277">비즈니스용 Skype 서버와 Office 365 간의 하이브리드 연결 플랜</span><span class="sxs-lookup"><span data-stu-id="cd4dc-277">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="cd4dc-278">팀을 사용 하 여 원격 작업자 지원</span><span class="sxs-lookup"><span data-stu-id="cd4dc-278">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="cd4dc-279">Microsoft 365를 사용 하 여 원격으로 작업</span><span class="sxs-lookup"><span data-stu-id="cd4dc-279">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)
