---
title: MSPL(Microsoft SIP Processing Language) 서버 응용 프로그램 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2a8aea4b412d2d744c42d659d2414a93c8435e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="b4e5a-102">Lync Server 2013에서 MSPL(Microsoft SIP Processing Language) 서버 응용 프로그램 보기</span><span class="sxs-lookup"><span data-stu-id="b4e5a-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4e5a-103">_**마지막으로 수정한 주제:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="b4e5a-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="b4e5a-104">MSPL (Microsoft SIP 처리 언어) 서버 응용 프로그램은 Microsoft Lync 2010 API 대신 스크립팅 언어를 사용 하는 스크립트 전용 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="b4e5a-105">MSPL는 트랜잭션 기반 SIP 응용 프로그램에 특정 메시지를 발송 하기 위한 기능 외에도 필터링 및 프록시 동작에 대 한 세밀 한 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="b4e5a-106">MSPL는 특별히 SIP 메시지를 필터링 하 고 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="b4e5a-107">MSPL 응용 프로그램은 UserServices 모듈과 같은 프로세스에서 실행 되지만 Lync 2010 API를 기반으로 하는 프로그램은 별도의 프로세스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="b4e5a-108">Lync Server 제어판의 **토폴로지** 그룹에 있는 **서버 응용 프로그램** 페이지를 사용 하 여 Lync Server 2013 환경의 프런트 엔드 서버에서 실행 되는 MSPL 서버 응용 프로그램 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="b4e5a-109">목록에는 각 풀에 대해 사용할 수 있는 스크립트와 해당 스크립트가 활성화 되었는지 여부와 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="b4e5a-110">스크립트는 나열 된 순서 대로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="b4e5a-111">이러한 스크립트에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-111">These scripts include the following:</span></span>

  - <span data-ttu-id="b4e5a-112">ClientVersionFilter는 관리자에 게 풀에서 지원 되는 클라이언트 버전을 지정 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-112">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="b4e5a-113">클라이언트 버전 필터는 클라이언트 버전을 확인 하 고 클라이언트의 로그온을 방지 하거나 지원 되지 않는 클라이언트를 사용 중임을 나타내는 메시지를 사용자에 게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-113">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="b4e5a-114">클라이언트 버전 필터는 다운로드 가능한 최신 버전의 클라이언트에 대 한 URL이 포함 된 메시지를 사용자에 게 표시 하도록 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-114">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="b4e5a-115">TranslationService은 관리자가 정의한 정규화 규칙에 따라 사용자가 전자로 거는 번호를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="b4e5a-116">자세한 내용은 [Lync Server 2013의 번역 규칙](lync-server-2013-translation-rules.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="b4e5a-117">IncomingFederation는 외부 배포에서 테 넌 트 간 및 받는 메시지에 대해 테 넌 트 수준 페더레이션 유효성 검사를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="b4e5a-118">UserServices는 프런트 엔드 서버의 SIP 등록자, 현재 상태, 회의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-118">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="b4e5a-119">SIP 프록시를 기반으로 하는 긴밀 하 게 통합 된 메신저 대화, 현재 상태, 회의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-119">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="b4e5a-120">InterClusterRouting는 피호출자의 기본 등록자 풀로 호출을 라우팅하는 역할을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="b4e5a-121">자세한 내용은 [Lync server 2013의 프런트 엔드 서버 VoIP 구성 요소](lync-server-2013-front-end-server-voip-components.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="b4e5a-122">IIMFilter (지능형 IM 필터)는 클릭 가능한 Url을 포함 하거나 파일 전송을 시작 하려고 하는 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="b4e5a-123">또한 IIMFilter는 서버를 대신 하 여 클라이언트 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="b4e5a-124">IIMFilter는 Lync Server 또는 Communicator를 사용 하 여 시작한 파일 전송에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="b4e5a-125">기본적으로 클릭 가능한 링크는 링크의 첫 번째 문자 앞에 밑줄 문자를 추가 하 여 사용할 수 없도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="b4e5a-126">관리자는이 동작을 변경 하 여 링크가 차단 되도록 할 수 있으며,이 경우 클릭 가능한 Url을 포함 하거나 파일 전송을 시작 하려는 메시지가 의도 한 대상에 도달 하지 못하도록 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="b4e5a-127">IIMFilter는 프록시 서버와 보관 서버를 제외한 Lync Server를 실행 하는 모든 서버에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="b4e5a-128">UserPinService는 전화 접속 회의에 대 한 사용자의 Pin (개인 식별 번호)을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="b4e5a-129">DefaultRouting는 Lync Server를 실행 하는 서버에 대 한 기본 라우팅 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="b4e5a-130">이 기능은 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-130">It is enabled by default.</span></span> <span data-ttu-id="b4e5a-131">라우팅 응용 프로그램이 모든 스탠더드 버전 및 Enterprise Edition 서버에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="b4e5a-132">ExumRouting는 Exchange UM (통합 메시징)로 전화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-132">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="b4e5a-133">ExumRouting은 새 음성 메일 메시지가 있을 때 통화를 라우팅하기 위해 해당 Exchange UM 서버를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-133">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="b4e5a-134">ExumRouting는 자동 전화 교환 및 구독자 액세스에 대 한 라우팅을 포함 하 여 일부 다른 Exchange UM 통합 측면도 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-134">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="b4e5a-135">OutboundRouting는 전화를 건 번호와 사용자의 전화 접속 인증을 착신 지에 따라 연결 되는 게이트웨이를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-135">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="b4e5a-136">또한 OutboundRouting는 게이트웨이에서 호출을 처리할 수 없는 경우 호출의 경로를 다시 라우팅하도록 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-136">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="b4e5a-137">QoEAgent는 끝점에서 SIP 서비스 요청을 통해 체감 품질 (환경 품질) 데이터 보고서를 수신 하 고 모니터링 서버의 대상 큐 또는 HTTP POST를 사용 하 여 타사 소비자에 게 데이터를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="b4e5a-138">자세한 내용은 [Lync Server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="b4e5a-139">OutgoingFederation는 대상 외부 배포로 보내는 메시지에 대해 테 넌 트 수준 페더레이션 유효성 검사를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="b4e5a-140">AcpRouting 프록시는 오디오 회의 공급자를 대상으로 하는 요청을 오디오 회의 공급자 게이트웨이로 초대 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="b4e5a-141">Edge 서버에서 실행 되는 스크립트에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="b4e5a-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="b4e5a-142">IIMFilter</span></span>

  - <span data-ttu-id="b4e5a-143">OptionsHandler는 요청이 현재 서버로 향하는 경우 **200 OK** 로 들어오는 옵션 요청에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="b4e5a-144">토폴로지 유효성 검사에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e5a-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b4e5a-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4e5a-145">See Also</span></span>


[<span data-ttu-id="b4e5a-146">Lync Server 2013에서 Microsoft SIP 처리 언어 (MSPL) 서버 응용 프로그램 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b4e5a-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="b4e5a-147">Lync Server 2013에서 Microsoft MSPL (SIP 처리 언어) 응용 프로그램을 중요 하거나 중요 하지 않음으로 표시</span><span class="sxs-lookup"><span data-stu-id="b4e5a-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

