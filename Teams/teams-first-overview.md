---
title: 먼저 Microsoft Teams 출시
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
description: 이 지침을 사용하여 Microsoft Teams를 첫 번째 Microsoft 365 또는 Office 365 워크로드로 롤아웃합니다.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a30d5bed9443df3077ab7384cd8266d2f049148d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909482"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="bb3e5-103">먼저 Microsoft Teams 출시</span><span class="sxs-lookup"><span data-stu-id="bb3e5-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="bb3e5-104">Microsoft Teams는 직원들이 서로 연결되고 공동 작업할 수 있도록 지원할 수 있습니다. 특히 원격 업무가 전 세계 직원의 현실인 현재 전례 없는 시간에서 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="bb3e5-105">Teams 내에서 채팅하고, 비디오 모임을 진행하고, Office 문서에 대해 공동 작업할 수 있게 하여 회사 생산성을 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="bb3e5-106">중소기업, 비영리 또는 대규모 조직이든, 다른 Office 앱 또는 서비스를 배포하기 전에 Microsoft 365 또는 Office 365 제품군 내에서 첫 번째 워크로드로 Teams를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="bb3e5-107">이 문서에서는 "Teams First" 접근 방식을 통해 해야 하는 고려 사항을 자세히 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb3e5-108">Teams는 조직의 첫 번째 클라우드 배포 워크로드가 될 수 있는 반면 Teams 배포는 전체 클라우드 배포 전략의 일부가 됐습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="bb3e5-109">다른 Microsoft 365 또는 Office 365 서비스를 이미 롤아웃한 경우 Teams가 첫 번째 대신 롤아웃할 다음 워크로드인 경우 Teams를 롤아웃하는 방법을 [시작하세요.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="bb3e5-110">여기에서 시작</span><span class="sxs-lookup"><span data-stu-id="bb3e5-110">Start here</span></span>

<span data-ttu-id="bb3e5-111">Teams First 배포를 시작하려면 최소한 몇 가지 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="bb3e5-112">Teams를 사용하도록 설정하기 전에 조직에 대해 설정해야 하는 항목은 다음 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="bb3e5-113">도메인 이름으로 구성된 Microsoft 365 또는 Office 365 조직</span><span class="sxs-lookup"><span data-stu-id="bb3e5-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="bb3e5-114">테넌트와 동기화된 모든 필수 특성이 있는 AAD 연결(AAD 연결) 또는 유사한 클라우드 ID 동기화 솔루션</span><span class="sxs-lookup"><span data-stu-id="bb3e5-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="bb3e5-115">AAD 동기화와 동기화된 특성을 이해하기 위해 [Azure AD Connect 동기화: Azure Active Directory에](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) 동기화된 특성 읽기</span><span class="sxs-lookup"><span data-stu-id="bb3e5-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="bb3e5-116">Teams에 할당된 적절한 사용자 라이선스</span><span class="sxs-lookup"><span data-stu-id="bb3e5-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="bb3e5-117">Teams 라이선스를 이해하기 위해 Microsoft Teams 서비스 [설명을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="bb3e5-118">Teams에 대해 준비된 조직의 네트워크</span><span class="sxs-lookup"><span data-stu-id="bb3e5-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="bb3e5-119">네트워크 준비를 이해하기 위해 [Teams에 대한 조직의 네트워크 준비를 읽어보아야 합니다.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="bb3e5-120">Microsoft 365 또는 Office 365: [Office 365 URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)및 IP 주소 범위에서 Exchange, Sharepoint 및 비즈니스용 OneDrive에 대한 네트워크 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e5-121">2019년 9월 1일 이후에 만든 테넌트는 Teams 전용 모드로 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="bb3e5-122">비즈니스용 Skype Server를 배포하고 2019년 9월 1일 이후에 테넌트가 프로비전된 경우 지원에 문의하여 Teams의 공존 기능을 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="bb3e5-123">사용자에게 Teams 라이선스를 할당하기 전에 '조직 전체 <span class="underline"></span> 업그레이드 정책'을 '섬 모드'로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="bb3e5-124">마이그레이션 시작 지점</span><span class="sxs-lookup"><span data-stu-id="bb3e5-124">Migration Starting points</span></span>

<span data-ttu-id="bb3e5-125">시작 지점 및 온-프레미스 비즈니스용 Skype 또는 Lync 서버의 존재 여부에 따라 Microsoft 365 또는 Office 365 및 Teams에서 사용할 수 있는 기능에 대한 여정입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="bb3e5-126">다음 섹션에서는 위의 전제 구성 구성 외에도 기본 기능 및 구성 옵션에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="bb3e5-127">시작 지점 시나리오를 다음 항목으로 세분화했습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="bb3e5-128">**테넌트 Teams 구성:** 테넌트 및 사용자 모드는 받는 사람의 동작을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="bb3e5-129">이러한 설정은 테넌트 수준 또는 조직의 사용자 수준에서 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="bb3e5-130">자세한 내용은 비즈니스용 [Skype와의 공존을 읽어보아야 합니다.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="bb3e5-131">**Teams의 채팅/외부 통신: 채팅** 서비스는 피어 투 피어 또는 그룹 채팅 대화를 조직 내부 및 조직 내부 또는 외부에서 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="bb3e5-132">외부 통신을 비즈니스용 Skype에서 페더러리라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="bb3e5-133">**Teams에서** 모임 만들기 및 보기: 사용자는 항상 Outlook Teams 추가 기능을 통해 온라인 모임을 만들 수 있으며, 사용자가 라이선스가 부여된 후 모든 시나리오에서 PSTN 전화 접속을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="bb3e5-134">Teams 및 비즈니스용 Skype는 사용자의 Exchange 사서함에 일정 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="bb3e5-135">Teams 클라이언트가 사용자의 사서함과 상호 작용할 수 있도록 Exchange Server 2016 CU3 이상을 위한 프레미스 Exchange 서버가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="bb3e5-136">Exchange 사서함에 액세스하지 않으면 Teams의 일정 아이콘이 나타나지 않고 사용자가 Teams 클라이언트에서 모임을 보거나 만들거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="bb3e5-137">**Teams의 VoIP/PSTN** 통화 기능: 통화는 VoIP(Voice over IP) 또는 PSTN(Public Switched Telephone Network)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="bb3e5-138">VoIP 연결은 Teams 클라이언트 간에 기본적으로 발생하고, PSTN 연결은 사용자가 외부 전화 번호로 전화를 걸 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="bb3e5-139">Teams는 두 가지 유형의 PSTN 연결을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="bb3e5-140">Microsoft 통화 요금제는 Microsoft에서 사용자의 전화 번호를 포함한 전화 통신 인프라 또는 직접 라우팅 구성을 제공하는 경우 고객이 Teams 사용자의 SBC(세션 테두리 컨트롤러)를 통해 전화 통신 연결을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="bb3e5-141">자세한 내용은 어떤 통화 [요금제가 적합한가요?](calling-plan-landing-page.md) 및 전화 시스템 직접 라우팅을 [읽어보세요.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="bb3e5-142">**Teams의 팀** 및 채널 공동 작업: Teams에서 팀은 작업, 프로젝트 또는 일반적인 관심사에 대해 함께 모인 사용자 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="bb3e5-143">팀은 채널로만 이월됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-143">Teams are made up of channels.</span></span> <span data-ttu-id="bb3e5-144">각 채널은 "팀 이벤트", 부서 이름 또는 재미를 위해 주제를 중심으로 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="bb3e5-145">채널은 모임을 열고, 대화를 나누고, 파일을 함께 작업하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="bb3e5-146">공동 작업 중</span><span class="sxs-lookup"><span data-stu-id="bb3e5-146">During collaboration</span></span>

<span data-ttu-id="bb3e5-147">**Teams의 비즈니스용 OneDrive(P2P** 파일 공유) : Teams 및 채널 외부에서 Teams 사용자는 비즈니스용 OneDrive 또는 Citrix Files, DropBox, Box 및 Google Drive와 같은 다른 P2P 공유 파일 프로그램을 사용하여 파일 피어 투 피어를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="bb3e5-148">비즈니스용 OneDrive의 경우 사용자에게 SharePoint Online 라이선스가 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="bb3e5-149">**애플리케이션 플랫폼:** 앱은 조직에서 Teams를 더 많이 활용하는 데 사용할 수 있는 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="bb3e5-150">이러한 앱은 타사 또는 조직의 개발자가 Microsoft에서 제공하는 탭, 메시징 확장, 커넥터 및 봇의 기능을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="bb3e5-151">**보안 및 규정 준수 기능:** Teams에는 보존 정책, DLP(데이터 손실 방지), eDiscovery 및 채널, 채팅 및 파일, 감사 로그 검색에 대한 법적 보존을 포함하여 규정 준수 영역을 지원하기 위한 다양한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="bb3e5-152">자세한 내용은 Microsoft Teams에서 보안 [및 규정 준수를 읽어보아야 합니다.](security-compliance-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="bb3e5-153">EDiscovery 기능의 경우 E5 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="bb3e5-154">[라이선스 옵션을 비교합니다.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="bb3e5-155">[Exchange 및 Microsoft Teams가 상호](exchange-teams-interact.md) 작용하여 시나리오에서 사용할 수 있는 규정 준수 기능을 알아보는 방법을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="bb3e5-156">**<span class="underline">비즈니스용</span>** Skype 또는 Lync Server가 없는 조직</span><span class="sxs-lookup"><span data-stu-id="bb3e5-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="bb3e5-157">이 시작점에서는 조직에서 현재 비즈니스용 Skype 또는 Lync Server를 활용하지 않는 경우 Teams가 Microsoft 365 또는 Office 365의 첫 번째 응용 프로그램이 될 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="bb3e5-158">다음 표에서는 핵심 서비스에 대한 Teams에 대한 고급 구성 및 최종 사용자 기능에 대해 자세히 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="bb3e5-159">항목</span><span class="sxs-lookup"><span data-stu-id="bb3e5-159">Item</span></span></th>
<th><span data-ttu-id="bb3e5-160">참고</span><span class="sxs-lookup"><span data-stu-id="bb3e5-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bb3e5-161">테넌트 Teams 구성</span><span class="sxs-lookup"><span data-stu-id="bb3e5-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="bb3e5-162">Teams 전용 모드, 모든 채팅 및 통화 기능은 Teams에만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb3e5-163">Teams의 채팅/외부 통신</span><span class="sxs-lookup"><span data-stu-id="bb3e5-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="bb3e5-164">Teams에서 내부(Microsoft 365 또는 Office 365 조직 내부) 및 외부 채팅 통신을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="bb3e5-165"><em>참고: 외부 액세스를 위해 DNS 항목을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="bb3e5-166">비즈니스용 Skype DNS 레코드는 비즈니스용 Skype 온-프레미스 또는 Microsoft 365 또는 Office 365에 없는 경우에도 Lync 및 비즈니스용 Skype 환경과의 페더맹을 허용하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="bb3e5-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">외부 도메인 이름 시스템 레코드</a></em></span><span class="sxs-lookup"><span data-stu-id="bb3e5-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb3e5-168">Teams에서 모임 만들기 및 보기</span><span class="sxs-lookup"><span data-stu-id="bb3e5-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="bb3e5-169">Outlook 추가 기능을 통해 내부 및 외부 모임을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="bb3e5-170">오디오 회의 라이선스에서 PSTN 다이얼 인 및 전화 걸기 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="bb3e5-171">Teams 일정 액세스에는 Exchange 하이브리드를 사용하여 배포된 Exchange 2016 CU3+ On-프레미스가 <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">필요합니다. 하이브리드</a> 구성 마법사를 사용하여 하이브리드 배포 만들기 </span><span class="sxs-lookup"><span data-stu-id="bb3e5-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="bb3e5-172">Exchange 하이브리드 구성 외에도 Exchange OAuth 인증을 설정: Exchange와 Exchange Online 조직 간에 <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth 인증 구성"을 수립합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb3e5-173">통화 기능</span><span class="sxs-lookup"><span data-stu-id="bb3e5-173">Calling Features</span></span><br />
<span data-ttu-id="bb3e5-174">Teams의 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="bb3e5-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="bb3e5-175">테넌트 내부 및 외부에서 VoIP를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="bb3e5-176">Microsoft Phone System을 통해 PSTN 서비스를 구성하고 Microsoft 통화 요금제 또는 직접 라우팅을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb3e5-177">Teams의 팀 및 채널 공동 작업</span><span class="sxs-lookup"><span data-stu-id="bb3e5-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="bb3e5-178">규정 준수 기능을 포함한 전체 환경을 위해 사용자에게 SharePoint Online 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="bb3e5-179">기존 On-프레미스 SharePoint 사이트를 마이그레이션할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb3e5-180">비즈니스용 OneDrive(P2P 파일 공유)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="bb3e5-181">비즈니스용 OneDrive를 사용하려면 사용자가 SharePoint Online 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="bb3e5-182">이 라이선스가 없는 경우 피어 투 피어 파일 공유는 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb3e5-183">애플리케이션 플랫폼</span><span class="sxs-lookup"><span data-stu-id="bb3e5-183">Application platform</span></span></td>
<td><span data-ttu-id="bb3e5-184">사용자는 회사 정책에 따라 사용할 수 있도록 지정된 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="bb3e5-185">자세한 정보: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Teams의 앱에 대한 관리자 설정</a></span><span class="sxs-lookup"><span data-stu-id="bb3e5-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb3e5-186">보안 및 규정 준수 기능</span><span class="sxs-lookup"><span data-stu-id="bb3e5-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="bb3e5-187">보존 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="bb3e5-188">채널 메시지에 대한 규정 준수를 위한 eDiscovery 및 법적 보류가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="bb3e5-189">DLP(데이터 손실 방지 정책)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="bb3e5-190">Exchange Online에서 사용할 수 있는 전체 기능 집합 Exchange-프레미스에서는 이러한 기능 대부분을 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="bb3e5-191">전체 목록은 Exchange 및 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Teams가 상호 작용하는 방법을 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="bb3e5-191">For a full list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="bb3e5-192">비즈니스용 Skype 또는 Lync Server가 없는 조직에 대한 사용 단계</span><span class="sxs-lookup"><span data-stu-id="bb3e5-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="bb3e5-193">위의 시작 섹션에 자세히 설명된 전제 요건 충족</span><span class="sxs-lookup"><span data-stu-id="bb3e5-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="bb3e5-194">테넌트가 Teams 전용 모드로 전환(기존 테넌트에만 해당): 공존 및 업그레이드 설정 [설정](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="bb3e5-195">회사의 비즈니스/회사 정책에 따라 테넌트 구성: [조직의 Microsoft Teams](enable-features-office-365.md)설정 관리</span><span class="sxs-lookup"><span data-stu-id="bb3e5-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="bb3e5-196">사용자에게 Teams 클라이언트 배포: [Teams용 클라이언트를 얻습니다.](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="bb3e5-197">채택 프로그램 구동</span><span class="sxs-lookup"><span data-stu-id="bb3e5-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="bb3e5-198">Microsoft Teams 채택</span><span class="sxs-lookup"><span data-stu-id="bb3e5-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="bb3e5-199">Microsoft Teams 채택 빠른 시작 검사 목록</span><span class="sxs-lookup"><span data-stu-id="bb3e5-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="bb3e5-200">다른 워크로드를 Microsoft 365 또는 Office 365로 이동 계획 시작</span><span class="sxs-lookup"><span data-stu-id="bb3e5-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="bb3e5-201">**<span class="underline">비즈니스용</span>** Skype 또는 Lync 서버가 있는 조직</span><span class="sxs-lookup"><span data-stu-id="bb3e5-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="bb3e5-202">이 시작점에서는 조직이 온-프레미스에서 비즈니스용 Skype 2019 또는 2015+ 또는 Lync 2013+ 서버를 활용하고 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="bb3e5-203">이미 프레미스 서버에서 Teams로 마이그레이션하는 조직에 대한 광범위한 지침이 있으며 이러한 시나리오에 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="bb3e5-204">이 지침은 Teams가 Microsoft 365 또는 Office 365에서 가장 먼저 활용하는 응용 프로그램인 시나리오와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="bb3e5-205">다음 표에서는 핵심 서비스에 대한 Teams에 대한 고급 구성 및 최종 사용자 기능에 대해 자세히 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="bb3e5-206">항목</span><span class="sxs-lookup"><span data-stu-id="bb3e5-206">Item</span></span></th>
<th><span data-ttu-id="bb3e5-207">참고</span><span class="sxs-lookup"><span data-stu-id="bb3e5-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bb3e5-208">테넌트 Teams 구성</span><span class="sxs-lookup"><span data-stu-id="bb3e5-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="bb3e5-209">제도 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb3e5-210">Teams의 채팅/외부 통신</span><span class="sxs-lookup"><span data-stu-id="bb3e5-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="bb3e5-211">자체 테넌트 내에서만 내부적으로 외부 통신(페더십)은 비즈니스용 Skype 또는 Lync 서버 배포를 통해 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb3e5-212">Teams에서 모임 만들기 및 보기</span><span class="sxs-lookup"><span data-stu-id="bb3e5-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="bb3e5-213">Outlook 추가 기능을 통해 내부 및 외부 모임을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="bb3e5-214">오디오 회의 라이선스에서 PSTN 다이얼 인 및 전화 걸기 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="bb3e5-215">Teams 일정 액세스에는 Exchange 하이브리드를 설정하여 배포된 Exchange 2016 CU3+ On-프레미스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="bb3e5-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">하이브리드 구성 마법사를 사용하여 하이브리드 배포를 만들 수 있습니다.</a></span><span class="sxs-lookup"><span data-stu-id="bb3e5-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="bb3e5-217">관리자는 Teams 모임 정책의 PreferredMeetingProviderForIslandsMode 특성인<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy를</a>통해 비즈니스용 Skype Outlook 추가 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb3e5-218">통화 기능</span><span class="sxs-lookup"><span data-stu-id="bb3e5-218">Calling Features</span></span><br />
<span data-ttu-id="bb3e5-219">Teams의 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="bb3e5-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="bb3e5-220">테넌트에 내부적으로 VoIP를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="bb3e5-221">사용자가 Teams 전용 환경으로 이동될 때까지 PSTN 또는 통화 요금제 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb3e5-222">Teams의 팀 및 채널 공동 작업</span><span class="sxs-lookup"><span data-stu-id="bb3e5-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="bb3e5-223">규정 준수 기능을 포함한 전체 환경을 위해 사용자에게 SharePoint Online 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="bb3e5-224">기존 On-프레미스 SharePoint 사이트를 마이그레이션할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb3e5-225">비즈니스용 OneDrive(P2P 파일 공유)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="bb3e5-226">비즈니스용 OneDrive를 사용하려면 사용자가 SharePoint Online 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="bb3e5-227">이 라이선스가 없는 경우 피어 파일 공유가 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb3e5-228">애플리케이션 플랫폼</span><span class="sxs-lookup"><span data-stu-id="bb3e5-228">Application platform</span></span></td>
<td><span data-ttu-id="bb3e5-229">사용자는 회사 정책에 따라 사용할 수 있도록 지정된 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="bb3e5-230">자세한 정보: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Teams의 앱에 대한 관리자 설정</a></span><span class="sxs-lookup"><span data-stu-id="bb3e5-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb3e5-231">보안 및 규정 준수 기능</span><span class="sxs-lookup"><span data-stu-id="bb3e5-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="bb3e5-232">보존 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="bb3e5-233">채널 메시지에 대한 규정 준수를 위한 eDiscovery 및 법적 보류가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="bb3e5-234">DLP(데이터 손실 방지 정책)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="bb3e5-235">Exchange Online에서 사용할 수 있는 전체 기능 집합 Exchange-프레미스에서는 이러한 기능 대부분을 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="bb3e5-236">전체 목록은 Exchange 및 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Teams가 상호 작용하는 방법을 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="bb3e5-236">For a complete list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="bb3e5-237">비즈니스용 Skype Server를 사용하여 조직에 대한 사용 단계</span><span class="sxs-lookup"><span data-stu-id="bb3e5-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="bb3e5-238">위의 시작 섹션에 자세히 설명된 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="bb3e5-239">테넌트가 제도 모드로 전환(2019년 9월 1일 이후에 프로비전된 테넌트의 경우 이 변경을 위해 고객 지원에 문의)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="bb3e5-240">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="bb3e5-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="bb3e5-241">회사의 비즈니스/회사 정책에 따라 테넌트 구성</span><span class="sxs-lookup"><span data-stu-id="bb3e5-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="bb3e5-242">조직에서 Microsoft Teams 설정 관리</span><span class="sxs-lookup"><span data-stu-id="bb3e5-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="bb3e5-243">Teams 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="bb3e5-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="bb3e5-244">Teams용 클라이언트 가져오기</span><span class="sxs-lookup"><span data-stu-id="bb3e5-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="bb3e5-245">채택 프로그램 구동</span><span class="sxs-lookup"><span data-stu-id="bb3e5-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="bb3e5-246">Microsoft Teams 채택</span><span class="sxs-lookup"><span data-stu-id="bb3e5-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="bb3e5-247">Microsoft Teams 채택 빠른 시작 검사 목록</span><span class="sxs-lookup"><span data-stu-id="bb3e5-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="bb3e5-248">다른 워크로드를 Microsoft 365 또는 Office 365로 이동 계획 시작</span><span class="sxs-lookup"><span data-stu-id="bb3e5-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="bb3e5-249">비즈니스용 Skype 하이브리드를 설정하고 비즈니스용 Skype 및 Lync 서버에 대한 권장 업그레이드 경로를 따르기</span><span class="sxs-lookup"><span data-stu-id="bb3e5-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="bb3e5-250">비즈니스용 Skype-프레미스에서 Teams로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="bb3e5-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="bb3e5-251">닫기 문</span><span class="sxs-lookup"><span data-stu-id="bb3e5-251">Closing statement</span></span>

<span data-ttu-id="bb3e5-252">Microsoft Teams는 조직에서 모든 직원, 정보 근로자 및 일선 직원을 단일 플랫폼으로 모을 수 있도록 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="bb3e5-253">지금 시작할 [수](https://products.office.com/microsoft-teams/group-chat-software) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="bb3e5-254">여기에서 최신 공지 및 월별 제품 업데이트를 계속 연락할 수 [있습니다.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="bb3e5-255">또한 전 세계 회사가 현재 COVID-19 상황을 관리하고 있는 동안 Teams를 조직에서 최대의 영향력으로 활용하는 데 도움이 되는 일련의 콘텐츠를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="bb3e5-256">[COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/) 기간 동안 고객에게 약속</span><span class="sxs-lookup"><span data-stu-id="bb3e5-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="bb3e5-257">2주: 원격 작업에서 배운 사항</span><span class="sxs-lookup"><span data-stu-id="bb3e5-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="bb3e5-258">온라인 모임 및 이벤트 제공</span><span class="sxs-lookup"><span data-stu-id="bb3e5-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="bb3e5-259">중소 기업이 Teams와 원격으로 작업할 수 있도록 지원</span><span class="sxs-lookup"><span data-stu-id="bb3e5-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="bb3e5-260">라이브 이벤트의 디지털 변환: 최전선에서 Bob Bejan의 관찰</span><span class="sxs-lookup"><span data-stu-id="bb3e5-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="bb3e5-261">Microsoft IT가 직원들의 원격 작업을 가능하게하는 9가지 방법</span><span class="sxs-lookup"><span data-stu-id="bb3e5-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="bb3e5-262">원격으로 작업하고 보안을 유지하며 CIS에 대한 팁</span><span class="sxs-lookup"><span data-stu-id="bb3e5-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="bb3e5-263">교사와 학생이 원격 학습으로 전환할 수 있도록 지원</span><span class="sxs-lookup"><span data-stu-id="bb3e5-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="bb3e5-264">Microsoft Teams를 사용하여 원격으로 작업하면서 생산성 유지</span><span class="sxs-lookup"><span data-stu-id="bb3e5-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="bb3e5-265">지원 서비스 참조</span><span class="sxs-lookup"><span data-stu-id="bb3e5-265">Support Services reference</span></span>

<span data-ttu-id="bb3e5-266">Teams는 Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 365 그룹을 통해 사용자에게 완전히 통합된 Microsoft 365 또는 Office 365 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="bb3e5-267">위에서 설명한 대로 Teams는 제한된 기능으로 이러한 서비스를 전체 배포하지 않고도 작동할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="bb3e5-268">Teams 및 해당 전제에 대한 자세한 내용은 Teams에 오신 것을 [환영합니다.](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="bb3e5-269">위에 나열된 각 서비스에 대한 구체적인 설명은 아래 링크를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="bb3e5-270">Exchange Online은 Teams에서 일정 기능 및 피어 투 피어 메시지 저장에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="bb3e5-271">자세한 내용은 Exchange 및 [Teams가 상호 작용하는 방법을 읽어보아야 합니다.](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb3e5-272">Exchange와 Exchange Online 조직 간의 OAuth 인증 구성에 설명된 새 Exchange [OAuth](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)인증 프로토콜을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="bb3e5-273">SharePoint는 채널에서 파일 공유에 사용되는 반면 비즈니스용 OneDrive는 1:1 또는 그룹 채팅에서 파일 공유에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="bb3e5-274">자세한 내용은 SharePoint Online 및 [비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법을 읽어보아야 합니다.](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="bb3e5-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="bb3e5-275">[Microsoft 365 그룹은](office-365-groups.md) 팀 및 채널 만들기/관리에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="bb3e5-276">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bb3e5-276">Related topics</span></span>

[<span data-ttu-id="bb3e5-277">Microsoft Teams IT 아키텍처 및 전화 통신 솔루션 포스터</span><span class="sxs-lookup"><span data-stu-id="bb3e5-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="bb3e5-278">비즈니스용 Skype 서버와 Office 365 간의 하이브리드 연결 플랜</span><span class="sxs-lookup"><span data-stu-id="bb3e5-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="bb3e5-279">Teams를 사용하여 원격 작업자 지원</span><span class="sxs-lookup"><span data-stu-id="bb3e5-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="bb3e5-280">Microsoft 365를 사용하여 원격으로 작업</span><span class="sxs-lookup"><span data-stu-id="bb3e5-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)
