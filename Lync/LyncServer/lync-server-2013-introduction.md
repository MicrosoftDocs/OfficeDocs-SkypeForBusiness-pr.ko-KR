---
title: Lync Server 2013 소개
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8879bd2f3638df17215b7b8f0ee4a12c751277f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a><span data-ttu-id="ac0d0-102">Lync Server 2013 소개</span><span class="sxs-lookup"><span data-stu-id="ac0d0-102">Introduction to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac0d0-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="ac0d0-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="ac0d0-104">Lync Server 2013 및 해당 클라이언트 소프트웨어 (예: Lync 2013)는 사용자가 실제 위치에 관계 없이 새로운 방법으로 연결 하 고 연결을 유지할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-104">Lync Server 2013 and its client software, such as Lync 2013, enable your users to connect in new ways and to stay connected, regardless of their physical location.</span></span> <span data-ttu-id="ac0d0-105">Lync와 Lync 서버는 사용자가 단일 클라이언트 인터페이스에서 통신 하는 다양 한 방법, 그리고 통합 플랫폼으로 배포 되며 단일 관리 인프라를 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-105">Lync and Lync Server bring together the different ways that people communicate in a single client interface, are deployed as a unified platform, and are administered through a single management infrastructure.</span></span>

<span data-ttu-id="ac0d0-106">이 표 및 다음 섹션에서는 사용자에 게 제공 되는 Lync Server의 주요 기능 집합 또는 *작업 부하*에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-106">This table and the following sections illustrate the major feature sets, or *workloads*, that Lync Server provides for your users.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac0d0-107">튜닝</span><span class="sxs-lookup"><span data-stu-id="ac0d0-107">Workload</span></span></th>
<th><span data-ttu-id="ac0d0-108">설명</span><span class="sxs-lookup"><span data-stu-id="ac0d0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac0d0-109">메신저 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="ac0d0-109">IM and presence</span></span></p></td>
<td><p><span data-ttu-id="ac0d0-110">인스턴트 메시지 (IM) 및 현재 상태를 통해 사용자 들이 쉽고 효과적으로 서로를 찾고 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-110">Instant messaging (IM) and presence help your users find and communicate with one another efficiently and effectively.</span></span></p>
<p><span data-ttu-id="ac0d0-111">IM은 대화 기록과 인스턴트 메시징 플랫폼을 제공 하며, MSN/Windows Live, Yahoo!, AOL, Google 대화 등의 공용 IM 네트워크 사용자와 공용 IM 연결을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-111">IM provides an instant messaging platform with conversation history, and supports public IM connectivity with users of public IM networks such as MSN/Windows Live, Yahoo!, AOL, and Google Talk.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="ac0d0-112">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-112">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="ac0d0-113">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-113">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="ac0d0-114">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-114">Messenger until the service shut down date.</span></span> <span data-ttu-id="ac0d0-115">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="ac0d0-115">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ac0d0-116">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-116">has been announced.</span></span> <span data-ttu-id="ac0d0-117">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-117">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="ac0d0-118">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-118">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="ac0d0-119">받으려면.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-119">Messenger.</span></span> <span data-ttu-id="ac0d0-120">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-120">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="ac0d0-121">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-121">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="ac0d0-122">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-122">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="ac0d0-123">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-123">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div>
<p><span data-ttu-id="ac0d0-124">현재 상태는 <strong>사용</strong> 가능 여부와 같은 일반적인 <strong>상태를 사용</strong>하 여 통신 하는 사용자의 개인 사용 가능 시간 및 willingness를 설정 하 고, <strong>오른쪽 뒤로</strong> , <strong>방해</strong>금지 등의 자세한 상태를 함께 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-124">Presence establishes and displays a user’s personal availability and willingness to communicate through the use of common states such as <strong>Available</strong> or <strong>Busy</strong>, as well as more detailed states such as <strong>Be Right Back</strong> and <strong>Do Not Disturb</strong>.</span></span> <span data-ttu-id="ac0d0-125">이 풍부한 현재 상태 정보를 통해 다른 사용자가 즉시 효과적인 의사 소통을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-125">This rich presence information enables other users to immediately make effective communication choices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac0d0-126">회의</span><span class="sxs-lookup"><span data-stu-id="ac0d0-126">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="ac0d0-127">Lync Server에는 예정 된 모임 및 임시 모임의 두 가지에 대 한 IM 회의, 오디오 회의, 웹 회의, 영상 회의, 응용 프로그램 공유에 대 한 지원이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-127">Lync Server includes support for IM conferencing, audio conferencing, web conferencing, video conferencing, and application sharing, for both scheduled and impromptu meetings.</span></span> <span data-ttu-id="ac0d0-128">이러한 모든 모임 유형은 단일 클라이언트에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-128">All these meeting types are supported with a single client.</span></span> <span data-ttu-id="ac0d0-129">Lync 서버는 또한 전화 접속 회의를 지원 하므로, PSTN (공개 통신 네트워크) 전화의 사용자가 회의의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-129">Lync Server also supports dial-in conferencing so that users of public switched telephone network (PSTN) phones can participate in the audio portion of conferences.</span></span></p>
<p><span data-ttu-id="ac0d0-130">회의가 실시간으로 변경 및 확대 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-130">Conferences can seamlessly change and grow in real time.</span></span> <span data-ttu-id="ac0d0-131">예를 들어 단일 회의는 몇 명의 사용자 사이에서 인스턴트 메시지로 시작 하 고, 데스크톱 공유를 사용 하 여 음성 회의를 하 고, 쉽고 빠르게 대화 흐름을 방해 하지 않고 더 많은 청중에 게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-131">For example, a single conference can start as just instant messages between a few users, and escalate to an audio conference with desktop sharing and a larger audience instantly, easily, and without interrupting the conversation flow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac0d0-132">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ac0d0-132">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="ac0d0-133"><em>Enterprise Voice</em> 는 Lync Server의 Voip (Voice Over 인터넷 프로토콜)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-133"><em>Enterprise Voice</em> is the Voice over Internet Protocol (VoIP) offering in Lync Server.</span></span> <span data-ttu-id="ac0d0-134">기존 PBX (개인 브랜치 교환) 시스템을 개선 하거나 대체 하는 음성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-134">It delivers a voice option to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="ac0d0-135">IP PBX의 완벽 한 전화 통신 기능 외에도 엔터프라이즈 음성은 다양 한 현재 상태, 메신저 대화, 공동 작업, 모임에 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-135">In addition to the complete telephony capabilities of an IP PBX, Enterprise Voice is integrated with rich presence, IM, collaboration, and meetings.</span></span> <span data-ttu-id="ac0d0-136">통화 응답, 보류, 이력서, 이전, 앞으로, 접속해 등의 기능을 직접 지원 하 고, 개인 설정 된 스피드 다이얼 키가 연락처 목록으로 바뀌고 자동 인터 컴 메신저 대화로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-136">Features such as call answer, hold, resume, transfer, forward and divert are supported directly, while personalized speed dialing keys are replaced by Contacts lists, and automatic intercom is replaced with IM.</span></span></p>
<p><span data-ttu-id="ac0d0-137">Enterprise Voice는 호출 허용 제어 (CAC), 지사 survivability, 데이터 탄력성을 위한 확장 옵션을 통해 고가용성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-137">Enterprise Voice supports high availability through call admission control (CAC), branch office survivability, and extended options for data resiliency.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac0d0-138">원격 사용자를 위한 지원</span><span class="sxs-lookup"><span data-stu-id="ac0d0-138">Support for remote users</span></span></p></td>
<td><p><span data-ttu-id="ac0d0-139">이러한 원격 사용자에 대 한 연결을 제공 하기 위해 <em>Edge 서버</em> 라고 하는 서버를 배포 하 여 현재 조직의 방화벽 외부에 있는 사용자에 대해 전체 Lync Server 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-139">You can provide full Lync Server functionality for users who are currently outside your organization’s firewalls by deploying servers called <em>Edge Servers</em> to provide a connection for these remote users.</span></span> <span data-ttu-id="ac0d0-140">이러한 원격 사용자는 Lync 2013이 설치 된 개인 컴퓨터, 휴대폰 또는 웹 인터페이스를 사용 하 여 회의에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-140">These remote users can connect to conferences by using a personal computer with Lync 2013 installed, the phone, or a web interface.</span></span></p>
<p><span data-ttu-id="ac0d0-141">Edge 서버를 배포 하는 경우에도 파트너 또는 공급 업체 조직과 <em>페더레이션</em> 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-141">Deploying Edge Servers also enables you to <em>federate</em> with partner or vendor organizations.</span></span> <span data-ttu-id="ac0d0-142">페더레이션 관계를 통해 사용자는 페더레이션 사용자를 대화 상대 목록에 배치할 수 있고, 현재 상태 정보 및 인스턴트 메시지를 이러한 사용자와 연결 하 고, 음성 통화, 영상 통화, 회의에 초대 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-142">A federated relationship enables your users to put federated users on their Contacts lists, exchange presence information and instant messages with these users, and invite them to audio calls, video calls, and conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac0d0-143">모바일 클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="ac0d0-143">Mobile client support</span></span></p></td>
<td><p><span data-ttu-id="ac0d0-144">또한 Lync Server mobility services를 통해 사용자는 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 Lync 기능에 액세스 하 고 인스턴트 메시지 보내기 및 받기, 연락처 보기 등의 작업을 수행할 수 있습니다. 현재 상태 보기</span><span class="sxs-lookup"><span data-stu-id="ac0d0-144">Additionally, with Lync Server mobility services, your users can access Lync functionality when using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices and perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="ac0d0-145">또한 모바일 장치는 클릭 하 여 회의에 참가 하 고, 회사, 단일 전화 접속, 음성 메일 및 부재 중 통화를 통해 전화를 걸 수 있는 몇 가지 엔터프라이즈 음성 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-145">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="ac0d0-146">푸시 알림은 백그라운드에서 실행 되는 응용 프로그램을 지원 하지 않는 모바일 장치 에서도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-146">Push notifications are also supported for mobile devices that do not support applications running in the background.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac0d0-147">다른 제품과 통합</span><span class="sxs-lookup"><span data-stu-id="ac0d0-147">Integration with other products</span></span></p></td>
<td><p><span data-ttu-id="ac0d0-148">Lync Server는 다른 여러 제품과 통합 되어 사용자와 관리자에 게 추가 혜택을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-148">Lync Server integrates with several other products to provide additional benefits to your users and administrators.</span></span></p>
<p><span data-ttu-id="ac0d0-149">모임 도구는 주최자가 모임을 예약 하거나 한 번의 클릭으로 즉석 회의를 시작할 수 있도록 Outlook에 통합 되어 참석자 들이 쉽게 참가할 수 있도록 해 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-149">Meeting tools are integrated into Outlook to enable organizers to schedule a meeting or start an impromptu conference with a single click and make it just as easy for attendees to join.</span></span></p>
<p><span data-ttu-id="ac0d0-150">현재 상태 정보는 Outlook과 SharePoint에 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-150">Presence information is integrated into Outlook and SharePoint.</span></span></p>
<p><span data-ttu-id="ac0d0-151">Exchange UM (통합 메시징)는 여러 가지 통합 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-151">Exchange Unified Messaging (UM) provides several integration features.</span></span> <span data-ttu-id="ac0d0-152">사용자는 Lync Server 내에서 새로운 음성 메일을 사용 하 고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-152">Users can see if they have new voice mail within Lync Server.</span></span> <span data-ttu-id="ac0d0-153">Outlook 메시지에서 재생 단추를 클릭 하 여 오디오 음성 메일을 듣거나 알림 메시지에서 음성 사서함의 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-153">They can click a play button in the Outlook message to hear the audio voice mail, or view a transcription of the voice mail in the notification message.</span></span></p>
<p><span data-ttu-id="ac0d0-154">또한 Exchange 2013를 사용 하 여 Lync Server 2013를 실행 하면 두 제품의 클라이언트에서 액세스할 수 있는 통일 된 연락처 저장소와 같은 몇 가지 새로운 기능과 Exchange 2013 데이터베이스에 저장 된 연락처의 고해상도 사진이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-154">Additionally, running Lync Server 2013 with Exchange 2013 enables several new features such as a unified contact store which can be accessed by clients of both products, as well as high-resolution photos for contacts which are stored in the Exchange 2013 database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac0d0-155">간단한 배포</span><span class="sxs-lookup"><span data-stu-id="ac0d0-155">Simple deployment</span></span></p></td>
<td><p><span data-ttu-id="ac0d0-156">서버 및 클라이언트를 계획 하 고 배포 하는 데 도움이 되도록 Lync Server는 토폴로지 작성기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-156">To help you plan and deploy your servers and clients, Lync Server provides the Topology Builder.</span></span></p>
<p><span data-ttu-id="ac0d0-157">토폴로지 작성기는 Lync Server의 설치 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-157">Topology Builder is an installation component of Lync Server.</span></span> <span data-ttu-id="ac0d0-158">토폴로지 작성기를 사용 하 여 계획 된 토폴로지를 만들고, 조정 하 고, 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-158">You use Topology Builder to create, adjust and publish your planned topology.</span></span> <span data-ttu-id="ac0d0-159">또한 서버 설치를 시작 하기 전에 토폴로지의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-159">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="ac0d0-160">개별 서버에 Lync Server를 설치 하는 경우 설치 프로그램은 토폴로지에서 지시한 대로 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-160">When you install Lync Server on individual servers, the installation program deploys the server as directed in the topology.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac0d0-161">간단한 관리</span><span class="sxs-lookup"><span data-stu-id="ac0d0-161">Simple management</span></span></p></td>
<td><p><span data-ttu-id="ac0d0-162">Lync Server를 배포한 후 다음과 같은 강력 하 고 능률적인 관리 도구가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-162">After you deploy Lync Server, it offers the following powerful and streamlined management tools:</span></span></p>
<ul>
<li><p><span data-ttu-id="ac0d0-163">중앙 구성 관리-변경 내용을 중앙에서 관리 하 고 전체 배포에 신속 하 게 복제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-163">Central configuration management, which enables you to manage changes centrally and have them replicated quickly to the entire deployment.</span></span></p></li>
<li><p><span data-ttu-id="ac0d0-164">관리자를 위한 웹 기반 그래픽 사용자 인터페이스인 Lync 서버 컨트롤 패널</span><span class="sxs-lookup"><span data-stu-id="ac0d0-164">Lync Server Control Panel, a web-based graphical user interface for administrators.</span></span> <span data-ttu-id="ac0d0-165">이 웹 기반 UI를 사용 하 여 Lync Server 관리자는 컴퓨터에 특별 한 관리 소프트웨어를 설치 하지 않고도 회사 네트워크의 어디에서 나 시스템을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-165">With this web-based UI, Lync Server administrators can manage their systems from anywhere on the corporate network, without needing specialized management software installed on their computers.</span></span></p></li>
<li><p><span data-ttu-id="ac0d0-166">Windows PowerShell 명령줄 인터페이스를 기반으로 하는 Lync Server 관리 셸 명령줄 관리 도구</span><span class="sxs-lookup"><span data-stu-id="ac0d0-166">Lync Server Management Shell command-line management tool, which is based on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="ac0d0-167">제품의 모든 측면을 관리 하기 위한 풍부한 명령 집합을 제공 하 고 Lync Server 관리자가 익숙한 도구를 사용 하 여 반복적인 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-167">It provides a rich command set for administration of all aspects of the product, and enables Lync Server administrators to automate repetitive tasks using a familiar tool.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ac0d0-168">메신저 대화 및 현재 상태 기능은 모든 Lync Server 배포에 자동으로 설치 되지만, 조직의 요구 사항에 맞게 배포를 조정 하기 위해 회의, Enterprise Voice, 원격 사용자 액세스를 배포할지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d0-168">While the IM and presence features are automatically installed in every Lync Server deployment, you can choose whether to deploy conferencing, Enterprise Voice, and remote user access, to tailor your deployment to your organization’s needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ac0d0-169">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ac0d0-169">In This Section</span></span>

  - [<span data-ttu-id="ac0d0-170">Lync Server 2013의 메신저 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="ac0d0-170">IM and presence in Lync Server 2013</span></span>](lync-server-2013-im-and-presence.md)

  - [<span data-ttu-id="ac0d0-171">Lync Server 2013의 회의</span><span class="sxs-lookup"><span data-stu-id="ac0d0-171">Conferencing in Lync Server 2013</span></span>](lync-server-2013-conferencing.md)

  - [<span data-ttu-id="ac0d0-172">Lync Server 2013의 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ac0d0-172">Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice.md)

  - [<span data-ttu-id="ac0d0-173">Lync Server 2013의 확장성</span><span class="sxs-lookup"><span data-stu-id="ac0d0-173">Scalability with Lync Server 2013</span></span>](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

