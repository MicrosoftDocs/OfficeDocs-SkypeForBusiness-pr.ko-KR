---
title: 기능 개요 (계획 도구)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: 계획 도구를 사용하여 Lync Server 2013의 토폴로지 디자인
ms.openlocfilehash: 81b674f55098f22f2bbff2db65219226c195e0f2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685461"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="39a5b-103">기능 개요 (계획 도구)</span><span class="sxs-lookup"><span data-stu-id="39a5b-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="39a5b-104">계획 도구를 사용하여 Lync Server 2013의 토폴로지 디자인</span><span class="sxs-lookup"><span data-stu-id="39a5b-104">Skype for Business Server 2015 Planning Tool</span></span>
  
<span data-ttu-id="39a5b-105">계획 도구의 **중앙 사이트** 페이지를 사용 하 여 비즈니스용 Skype 서버 배포를 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="39a5b-106">중앙 집중화 또는 분산 배포 두 개를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="39a5b-107">중앙 집중화 된 배포에는 조직의 모든 비즈니스용 Skype 사용자를 홈으로 하는 하나의 중앙 사이트만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="39a5b-108">분산 배포에는 두 개 이상의 중앙 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="39a5b-109">여러 중앙 사이트에 비즈니스용 Skype 서버를 배포 하는 경우 계획 도구에서 각 중앙 사이트에 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="39a5b-110">중앙 사이트의 정의를 완료 하려면 먼저 다음 정보를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="39a5b-111">**사이트 이름** 중앙 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="39a5b-112">**사용자 수** 중앙 사이트에 속한 지점 사이트의 사용자를 포함 하 여 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="39a5b-113">**클라우드 홈 사용자** 비즈니스용 Skype Online에서 중앙 사이트에 속한 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="39a5b-114">UI 요소</span><span class="sxs-lookup"><span data-stu-id="39a5b-114">UI Elements</span></span>

<span data-ttu-id="39a5b-115">나머지 요소는 **시작** 마법사에 표시 된 질문에 대 한 답변으로 채워지고, 마법사를 건너뛴 경우 계획 도구에 의해 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="39a5b-116">온라인 공동 작업</span><span class="sxs-lookup"><span data-stu-id="39a5b-116">Online Collaboration</span></span>

 <span data-ttu-id="39a5b-117">**온라인 공동 작업** 에는 다음 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="39a5b-118">**메신저 대화 및 현재 상태**</span><span class="sxs-lookup"><span data-stu-id="39a5b-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="39a5b-119">인스턴트 메시지 (IM)를 사용 하면 사용자가 텍스트 기반 메시지를 사용 하 여 컴퓨터에서 실시간으로 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="39a5b-120">2-파티 및 단체 IM 세션이 모두 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="39a5b-121">현재 상태는 네트워크에 있는 다른 사용자의 상태에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="39a5b-122">사용자의 현재 상태는 다른 사용자가 온라인 상태 인지 여부를 확인 하는 데 도움이 되는 정보와 사용자에 게 가장 적합 한 방법 등을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="39a5b-123">예를 들어 모임에 참가 중인 사용자는 전자 메일을 통해 가장 잘 연락을 드릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="39a5b-124">**오디오 및 비디오 회의**</span><span class="sxs-lookup"><span data-stu-id="39a5b-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="39a5b-125">오디오/비디오 (A/V) 회의를 통해 실시간 오디오 및 비디오 회의를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="39a5b-126">**전화 접속 회의**</span><span class="sxs-lookup"><span data-stu-id="39a5b-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="39a5b-127">전화 접속 회의를 통해 사용자는 PSTN의 전화기에서 A/V에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-127">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN.</span></span> <span data-ttu-id="39a5b-128">전화 접속 회의를 하려면 회의 수행자와 회의 알림 서비스 응용 프로그램을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-128">Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="39a5b-129">**웹 회의**</span><span class="sxs-lookup"><span data-stu-id="39a5b-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="39a5b-130">웹 회의를 통해 방화벽 내부 및 외부의 엔터프라이즈 사용자가 내부 서버에 호스팅되는 실시간 회의를 만들고 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="39a5b-131">**영구 채팅**</span><span class="sxs-lookup"><span data-stu-id="39a5b-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="39a5b-132">영구 채팅을 통해 여러 사용자가 텍스트, 링크, 파일을 비롯 한 특정 항목에 대 한 콘텐츠를 게시 하 고 액세스 하는 대화에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-132">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="39a5b-133">사용자가 세션 중에 실시간으로 통신할 수 있지만, 각 세션의 콘텐츠는 영구적 이므로 세션이 종료 된 후에도 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-133">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>
    
### <a name="users"></a><span data-ttu-id="39a5b-134">사용자</span><span class="sxs-lookup"><span data-stu-id="39a5b-134">Users</span></span>

 <span data-ttu-id="39a5b-135">**사용자에 게** 는 다음 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-135">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="39a5b-136">**내부 조직**</span><span class="sxs-lookup"><span data-stu-id="39a5b-136">**Internal organization**</span></span>
    
- <span data-ttu-id="39a5b-137">**다른 조직과의 페더레이션**</span><span class="sxs-lookup"><span data-stu-id="39a5b-137">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="39a5b-138">**이전 버전과의 페더레이션**</span><span class="sxs-lookup"><span data-stu-id="39a5b-138">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="39a5b-139">**공용 IM 서비스 공급자와의 페더레이션** 조직의 사용자가 MSN, Yahoo!, AOL 등의 공공 메신저 서비스 공급자와 통신을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-139">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL.</span></span> <span data-ttu-id="39a5b-140">공용 인스턴트 메시징 네트워크 페더레이션 설정에는 별도의 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-140">A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="39a5b-141">**XMPP 기반 서비스 공급자와의 페더레이션**</span><span class="sxs-lookup"><span data-stu-id="39a5b-141">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="39a5b-142">비즈니스용 Skype 서버 2015에는 전체 통합 XMPP 프록시 (Edge 서버에 배포 됨)와 프런트 엔드 서버에 배포 된 XMPP 게이트웨이가 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-142">Skype for Business Server 2015 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="39a5b-143">XMPP 프록시와 XMPP 게이트웨이를 추가 하 고 구성 하 여 사용 하면 Skype for Business Server 2015 사용자가 XMPP 기반 파트너에서 인스턴트 메시지 (IM) 및 현재 상태에 대 한 연락처를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-143">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server 2015 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="39a5b-144">**이동성**</span><span class="sxs-lookup"><span data-stu-id="39a5b-144">**Mobility**</span></span>
    
    <span data-ttu-id="39a5b-145">비즈니스용 Skype Server 2015 모바일 서비스를 배포 하는 경우 사용자는 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 인스턴트 메시지 보내기 및 받기, 연락처 보기, 현재 상태 보기 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-145">When you deploy the Skype for Business Server 2015 Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="39a5b-146">**W15 Exchange 사서함**</span><span class="sxs-lookup"><span data-stu-id="39a5b-146">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="39a5b-147">비즈니스용 Skype 서버 2015를 사용 하면 UM (통합 메시징)에 저장 된 보이스 메일 메시지를 받을 수 있습니다. 그러면 해당 보이스 메일 메시지가 사용자의 받은 편지함에 전자 메일 메시지로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-147">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>
    
### <a name="voice"></a><span data-ttu-id="39a5b-148">음성</span><span class="sxs-lookup"><span data-stu-id="39a5b-148">Voice</span></span>

 <span data-ttu-id="39a5b-149">**음성** 에는 다음 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-149">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="39a5b-150">**Enterprise Voice**</span><span class="sxs-lookup"><span data-stu-id="39a5b-150">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="39a5b-151">엔터프라이즈 음성은 마이크로 Sft의 소프트웨어 구동 VoIP 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-151">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="39a5b-152">기업 음성으로 사용자는 비즈니스용 Skype를 사용 하 여 컴퓨터에서 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-152">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="39a5b-153">**Exchange 통합 메시징**</span><span class="sxs-lookup"><span data-stu-id="39a5b-153">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="39a5b-154">Exchange UM (통합 메시징)는 음성 메일 및 전자 메일을 단일 메시징 인프라로 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-154">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="39a5b-155">비즈니스용 Skype 서버 2015는 Exchange UM을 사용 하 여 통화 응답, 구독자 액세스, 통화 알림, 자동 전화 교환 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-155">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="39a5b-156">이러한 서비스를 사용 하는 경우에는 공유 Active Directory 토폴로지에서 Exchange UM 및 비즈니스용 Skype 서버를 통합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-156">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="39a5b-157">추가 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="39a5b-157">Additional Deployment Options</span></span>

 <span data-ttu-id="39a5b-158">**추가 배포 옵션** 에는 다음 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-158">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="39a5b-159">**고가용성**</span><span class="sxs-lookup"><span data-stu-id="39a5b-159">**High Availability**</span></span>
    
    <span data-ttu-id="39a5b-160">고가용성을 통해 장애 조치 지원에 대기 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-160">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="39a5b-161">**재해 복구**</span><span class="sxs-lookup"><span data-stu-id="39a5b-161">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="39a5b-162">재해 복구 측정값을 사용 하면 두 데이터 센터에 있는 프런트 엔드 풀을 쌍으로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-162">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="39a5b-163">**모니터링**</span><span class="sxs-lookup"><span data-stu-id="39a5b-163">**Monitoring**</span></span>
    
    <span data-ttu-id="39a5b-164">모니터링은 통신 세션과 관련 된 통화 정보 레코드를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-164">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="39a5b-165">또한 참가자 끝점에서 오디오 및 비디오 세션의 메트릭을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-165">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="39a5b-166">모니터링 서버는 사용 통계, 추세 및 미디어 품질 통계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-166">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="39a5b-167">**보관**</span><span class="sxs-lookup"><span data-stu-id="39a5b-167">**Archiving**</span></span>
    
    <span data-ttu-id="39a5b-168">보관은 인스턴트 메시지 대화 및 회의를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-168">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="39a5b-169">**Exchange 보관 통합**</span><span class="sxs-lookup"><span data-stu-id="39a5b-169">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="39a5b-170">Exchange 2013에 속한 사용자와 사서함이 원본 위치 유지에 저장 되어 있는 경우 비즈니스용 Skype Server 2015 저장소를 Exchange 저장소와 통합 하는 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-170">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server 2015 storage with Exchange storage.</span></span>
    
- <span data-ttu-id="39a5b-171">**(Ipv4**</span><span class="sxs-lookup"><span data-stu-id="39a5b-171">**IPv4**</span></span>
    
    <span data-ttu-id="39a5b-172">IPv4 주소는 컴퓨터에서 인터넷을 통해 통신할 수 있도록 하는 32 비트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-172">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="39a5b-173">전세계 장치 수가 증가 함에 따라 사용 가능한 IPv4 주소가 초과 되었습니다. 이 때문에 많은 새 장치가 IPv6 주소를 사용 하도록 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-173">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="39a5b-174">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="39a5b-174">**IPv6**</span></span>
    
    <span data-ttu-id="39a5b-175">IPv6 주소는 IPv4 주소와 동일한 기능을 수행 하지만 (일부 추가 기능 포함), 32 비트만 사용 하는 대신 128 비트를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-175">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="39a5b-176">이렇게 하면 새 주소 집합 뿐만 아니라 훨씬 더 많은 수가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-176">This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="39a5b-177">**장치 업데이트 웹 서비스**</span><span class="sxs-lookup"><span data-stu-id="39a5b-177">**Device Update Web service**</span></span>
    
    <span data-ttu-id="39a5b-178">장치 업데이트 웹 서비스는 조직 외부에 배포 되는 Windows Phone 용 비즈니스용 Skype 등의 모든 장치를 자동으로 업데이트 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-178">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="39a5b-179">서버 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="39a5b-179">Server Applications</span></span>

 <span data-ttu-id="39a5b-180">**서버 응용 프로그램** 에는 다음 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-180">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="39a5b-181">**응답 그룹**</span><span class="sxs-lookup"><span data-stu-id="39a5b-181">**Response Group**</span></span>
    
    <span data-ttu-id="39a5b-182">응답 그룹 응용 프로그램이 자동으로 응답 하 고 통화를 사용 가능한 헬프 데스크 상담원에 게 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-182">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="39a5b-183">**발표**</span><span class="sxs-lookup"><span data-stu-id="39a5b-183">**Announcement**</span></span>
    
    <span data-ttu-id="39a5b-184">엔터프라이즈 음성을 배포 하려는 경우 전화 건 번호가 유효 하지만 사용자 공통 영역에 할당 되지 않은 경우에는 휴대폰 통화가 처리 되는 방식을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-184">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="39a5b-185">관리자는 이러한 호출이 미리 지정 된 대상 (전화 번호 또는 SIP URI)으로 전송 되거나 오디오 알림 또는 두 가지 모두를 재생 하도록 알림 서비스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-185">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="39a5b-186">알림 서비스를 사용 하면 발신자가 통화를 잘못 걸기 하 고 수신 중이거나 SIP 클라이언트에 오류 메시지가 나타나는 상황을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-186">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="39a5b-187">알림 서비스 기능은 일반적인 PBX 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-187">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="39a5b-188">**통화 파킹**</span><span class="sxs-lookup"><span data-stu-id="39a5b-188">**Call Park**</span></span>
    
    <span data-ttu-id="39a5b-189">통화 대기 응용 프로그램을 통해 엔터프라이즈 음성 사용자는 전화를 걸 수 있습니다. 그런 다음 통화를 받은 전화기에 리소스를 연결 하지 않고 다른 전화로 전화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-189">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="39a5b-190">통화 대기 응용 프로그램은 사용자가 통화를 전송 해야 하지만 특정 수신자는 알 수 없는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-190">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="39a5b-191">**컨퍼런스 전화 교환**</span><span class="sxs-lookup"><span data-stu-id="39a5b-191">**Conference Attendant**</span></span>
    
    <span data-ttu-id="39a5b-192">회의 전화 교환 응용 프로그램은 타사 오디오 회의 공급자의 서비스 없이도 전화 사용자에 게 오디오 회의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-192">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="39a5b-193">**회의 알림**</span><span class="sxs-lookup"><span data-stu-id="39a5b-193">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="39a5b-194">회의 알림 응용 프로그램을 통해 사용자가 회의를 시작 하거나 탈퇴할 때 신호를 보내거나, 음소거 또는 음소거 됨 때 전화 사용자에 게 알림을 보내는 신호음이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-194">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="39a5b-195">**통화 허용 컨트롤**</span><span class="sxs-lookup"><span data-stu-id="39a5b-195">**Call Admission Control**</span></span>
    
    <span data-ttu-id="39a5b-196">호출 허용 제어 (CAC)는 WAN 대역폭 관리 라고도 하며, 사용 가능한 대역폭, 새 실시간 통신 세션을 허용할지 여부를 결정 하 여 혼잡 한 네트워크의 사용자에 대 한 경험 치를 방지 하는 데 도움이 됩니다. 했.</span><span class="sxs-lookup"><span data-stu-id="39a5b-196">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="39a5b-197">CAC는 실시간 트래픽만 제어 하 고 데이터 트래픽에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-197">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="39a5b-198">새 음성 또는 비디오 세션이 WAN에 할당 한 대역폭 제한을 초과할 경우 해당 세션은 차단 되거나 (전화 통화 전용) PSTN으로 다시 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="39a5b-198">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

