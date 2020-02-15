---
title: MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d0572ad17d5359cf082c6bd06ab722d8322180e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="b9489-102">Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램 보기</span><span class="sxs-lookup"><span data-stu-id="b9489-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9489-103">_**마지막으로 수정 된 항목:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="b9489-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="b9489-104">MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램은 Microsoft Lync 2010 API 대신 스크립트 언어를 사용 하는 스크립트 전용 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="b9489-105">MSPL에서는 트랜잭션 기반 SIP 응용 프로그램에 대 한 특정 메시지를 발송 하기 위한 기능 외에도 필터링 및 프록시 동작을 보다 세부적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="b9489-106">MSPL는 SIP 메시지를 필터링 하 고 라우팅하는 데 특별히 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="b9489-107">MSPL 응용 프로그램은 UserServices 모듈과 동일한 프로세스에서 실행 되지만 Lync 2010 API를 기반으로 하는 프로그램은 별도의 프로세스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="b9489-108">Lync server 제어판의 **토폴로지** 그룹에 있는 **서버 응용** 프로그램 페이지를 사용 하 여 Lync Server 2013 환경의 프런트 엔드 서버에서 실행 되는 MSPL 서버 응용 프로그램의 목록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="b9489-109">이 목록에는 각 풀에 사용할 수 있는 스크립트가 나와 있으며, 스크립트가 사용하도록 설정되었는지, 중요 스크립트로 지정되었는지 여부도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="b9489-110">스크립트는 나열된 순서대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="b9489-111">이러한 스크립트에 포함되는 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-111">These scripts include the following:</span></span>

  - <span data-ttu-id="b9489-p103">ClientVersionFilter - 관리자에게 풀에서 지원하는 클라이언트 버전을 지정하는 방법을 제공합니다. 클라이언트 버전 필터는 클라이언트 버전을 확인한 다음, 결과에 따라 클라이언트 로깅을 차단할 수도 있고, 현재 사용 중인 클라이언트가 지원되지 않는다는 메시지를 표시할 수도 있습니다. 또한 다운로드 가능한 최신 클라이언트 버전의 URL이 포함된 메시지를 사용자에게 표시하도록 구성될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-p103">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool. The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported. The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="b9489-115">TranslationService - 관리자가 정의한 정규화 규칙에 따라 사용자가 전화를 거는 번호를 E.164 번호로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="b9489-116">자세한 내용은 [Lync Server 2013의 변환 규칙](lync-server-2013-translation-rules.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9489-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="b9489-117">IncomingFederation은 내부 테넌트 및 외부 배포에서 수신되는 메시지에 대한 테넌트 수준의 페더레이션 유효성 검사를 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="b9489-p105">UserServices - 프런트 엔드 서버의 SIP 등록자, 현재 상태 및 회의 구성 요소이며, SIP 프록시의 위쪽에 구축된 통합형 IM 현재 상태 및 회의 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-p105">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server. It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="b9489-120">InterClusterRouting - 통화를 수신자의 기본 등록자 풀로 라우팅하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="b9489-121">자세한 내용은 [Lync server 2013의 프런트 엔드 서버 VoIP 구성 요소](lync-server-2013-front-end-server-voip-components.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9489-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="b9489-122">IIMFilter(지능형 IM 필터) - 클릭 가능한 URL이 들어 있거나 파일 전송을 시작하려고 하는 메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="b9489-123">또한 서버 대신 클라이언트 버전도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="b9489-124">IIMFilter는 Lync Server 또는 Communicator를 사용 하 여 시작한 파일 전송에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="b9489-125">기본적으로 클릭 가능한 링크는 링크의 첫 문자 앞에 밑줄을 추가하면 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="b9489-126">관리자는 링크가 차단되도록 이 동작을 변경할 수 있으며, 이 경우 클릭 가능한 URL이 들어 있거나 파일 전송을 시작하려고 하는 메시지가 의도한 대상에 접근할 수 없도록 서버에서 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="b9489-127">프록시 서버 및 보관 서버를 제외 하 고 Lync Server를 실행 하는 모든 서버에 IIMFilter가 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="b9489-128">UserPinService - 전화 접속 회의 시 사용자의 PIN(개인 식별 번호)을 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="b9489-129">DefaultRouting은 Lync Server를 실행 하는 서버의 기본 라우팅 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="b9489-130">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-130">It is enabled by default.</span></span> <span data-ttu-id="b9489-131">라우팅 응용 프로그램은 모든 Standard Edition 및 Enterprise Edition 서버에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="b9489-p109">ExumRouting - 통화를 Exchange Server UM(통합 메시징)으로 라우팅하며, 새 음성 메시지를 보관해야 할 경우 통화를 라우팅할 적절한 Exchange UM 서버를 결정합니다. 또한 ExumRouting은 구독자 액세스 기능 및 자동 전화 교환으로 라우팅을 비롯한 다른 몇 가지 Exchange UM 통합 부분을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-p109">ExumRouting routes calls to Exchange Server Unified Messaging (UM). ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit. ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="b9489-p110">OutboundRouting - 전화 건 번호와 사용자의 전화 걸기 권한 부여에 따라 통화를 전화 번호로 라우팅하는 게이트웨이를 결정하며, 게이트웨이에서 통화를 처리할 수 없는 경우 통화 재라우팅을 처리하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-p110">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization. OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="b9489-137">QoEAgent - SIP SERVICE 요청을 통해 끝점에서 QoE(체감 품질) 데이터 보고서를 수신하며 HTTP POST를 사용하여 타사 소비자나 모니터링 서버의 대상 큐에 이 데이터를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="b9489-138">자세한 내용은 [Lync Server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9489-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="b9489-139">OutgoingFederation은 대상 외부 배포로 이동하는 메시지에 대해 테넌트 수준의 페더레이션 유효성 검사를 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="b9489-140">AcpRouting은 오디오 회의 공급자에 대해 지정된 INVITE 요청을 오디오 회의 공급자 게이트웨이로 프록시합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="b9489-141">에지 서버에서 실행되는 스크립트에 포함되는 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="b9489-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="b9489-142">IIMFilter</span></span>

  - <span data-ttu-id="b9489-143">OptionsHandler는 요청이 현재 서버에 대해 지정된 경우 수신되는 OPTIONS 요청에 **200 OK**로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="b9489-144">이 항목은 토폴로지 유효성 검사에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9489-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b9489-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9489-145">See Also</span></span>


[<span data-ttu-id="b9489-146">Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="b9489-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="b9489-147">Lync Server 2013에서 Microsoft MSPL (SIP 처리 언어) 응용 프로그램을 중요 또는 중요 하지 않음으로 표시</span><span class="sxs-lookup"><span data-stu-id="b9489-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

