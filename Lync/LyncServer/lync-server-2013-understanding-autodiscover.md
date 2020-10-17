---
title: 'Lync Server 2013: 자동 검색 이해'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63e29608dd8c3a0187b17c03e6ba9373b31f08f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527765"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="90e18-102">Lync Server 2013의 자동 검색 이해</span><span class="sxs-lookup"><span data-stu-id="90e18-102">Understanding Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90e18-103">_**마지막으로 수정 된 항목:** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="90e18-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="90e18-104">Lync Server 2013 자동 검색 서비스는 Lync Server 2010:11 월 2011에 대 한 누적 업데이트의 일부로, 원래 Microsoft Lync Server 2010에 도입 된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="90e18-105">수정 사항 외에도이 누적 업데이트는 Lync Mobile 및 Lync 2013 클라이언트에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="90e18-106">Lync Server 2013에서 자동 검색 서비스는 외부 및 내부 모바일 클라이언트 작업의 필수 부분이 며, Windows 8 용으로 최근에 도입 된 Lync Windows 스토어 앱과 같은 새 클라이언트로도 자동 검색을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="90e18-107">자동 검색은 Lync 2013 데스크톱 클라이언트 에서도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="90e18-108">입력은 필요한 DNS (domain name system) record \*\*lyncdiscover \<domain\> \*\* 를 통해 Lync Server에서 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>**</span></span> <span data-ttu-id="90e18-109">및 \*\*lyncdiscoverinternal \<domain\> \*\*</span><span class="sxs-lookup"><span data-stu-id="90e18-109">and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="90e18-110">또한 최신 버전의 Lync 2010 및 Lync 2013 데스크톱 클라이언트는 DNS (domain name system) SRV 레코드에 대 한 자동 검색을 우선적으로 사용 합니다 (lyncdiscover 인 경우에만 DNS SRV 레코드).\<domain\></span><span class="sxs-lookup"><span data-stu-id="90e18-110">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\></span></span> <span data-ttu-id="90e18-111">또는 lyncdiscoverinternal입니다.\<domain\></span><span class="sxs-lookup"><span data-stu-id="90e18-111">or lyncdiscoverinternal.\<domain\></span></span> <span data-ttu-id="90e18-112">응답 하지 않거나 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-112">does not respond or does not resolve.</span></span> <span data-ttu-id="90e18-113">Windows 8 및 Lync Mobile 용 Lync Windows 스토어 앱은 자동 검색을 단독으로 사용 하며 기존 DNS SRV 레코드를 참조 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-113">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="90e18-114">Lync Server 2013에서는 클라이언트에서 사용할 수 있는 요소, 기능 및 통신 방법을 클라이언트에 알리기 위해 자동 검색 기능이 확장 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-114">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="90e18-115">정보는 클라이언트에서 전송 되는 요청을 통해 전달 되며, Lync Server 웹 서비스는 클라이언트에 게 제공 되는 이름을 명확 하 게 정의 된 응답으로 응답 하 고 자동 검색 응답 문서 형식으로 이러한 기능에 연락 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-115">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="90e18-116">웹 서비스가이 문서를 통해 클라이언트에 기능을 전달 하는 방법을 비롯 하 여 자동 검색 응답 문서를 이해 하는 가장 좋은 방법은 Lync web service 자동 검색 응답 문서의 일반적인 응답에서 각 줄을 dissect 하 고 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-116">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="90e18-117">팔 로우 하는 세부 정보에서는 인증 요청에 응답 하 여 사용자가 이미 홈 서버에 인증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-117">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="90e18-118">Lync 자동 검색 웹 서비스는 MSDN ( <STRONG>Microsoft Developer Network</STRONG> ) 라이브러리의 <STRONG>공개 사양</STRONG> 섹션에 있는 <STRONG>microsoft Office 프로토콜</STRONG> 에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-118">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="90e18-119">자세한 내용은의 "Lync 자동 검색 웹 서비스 프로토콜" 전체 사양 문서를 참조 <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> 하십시오.</span><span class="sxs-lookup"><span data-stu-id="90e18-119">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="90e18-120">인증에 대 한 자세한 내용은의 "OC 인증 웹 서비스 프로토콜"을 참조 <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> 하세요.</span><span class="sxs-lookup"><span data-stu-id="90e18-120">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="90e18-121">Lync Server 웹 서비스 자동 검색 응답</span><span class="sxs-lookup"><span data-stu-id="90e18-121">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="90e18-122">자동 검색 요청이 전송 될 때 반환 되는 응답은 내부 또는 외부 클라이언트에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-122">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="90e18-123">위치를 확인 하는 일부 매개 변수는 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-123">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="90e18-124">클라이언트 요청을 받았지만 실제 풀이 연결 된 것과 다른 경우에는 해당 사용자에 대해 사용자의 홈 풀이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-124">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="90e18-125">사용자 계정이 다른 풀에 있지만 같은 사무실의 로그인 인 동료는 약간 다른 응답을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-125">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="90e18-126">응답은 해당 사용자에 대 한 올바른 프런트 엔드 서버 또는 프런트 엔드 풀을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-126">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="90e18-127">자동 검색 응답 문서의 예:</span><span class="sxs-lookup"><span data-stu-id="90e18-127">An example of an Autodiscover Response document:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="90e18-128">자동 검색 응답 문서 세부 정보</span><span class="sxs-lookup"><span data-stu-id="90e18-128">Autodiscover Response Document Details</span></span>

<span data-ttu-id="90e18-129">자동 검색 응답 문서는 두 가지 형식 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-129">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="90e18-130">기본 형식은 JSON (JavaScript Object Notation)입니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-130">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="90e18-131">다른 형식은 XML (extensible markup language) 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-131">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="90e18-132">이 예제에서는 XML이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-132">The XML is used for this example.</span></span> <span data-ttu-id="90e18-133">문서에 형식을 결정 하는 정의 된 스키마가 있기 때문에 요청 및 응답은 예측 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-133">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="90e18-134">사용 된 스키마를 설명 하는 문서의 줄은 요청 또는 응답의 첫 번째 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-134">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="90e18-135">**Accesslocation = "External"** 정의는 외부 사용자 로부터 요청이 수행 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-135">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="90e18-136">SipServerInternalAccess 및 SipServerExternalAccess는 현재 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-136">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="90e18-137">이러한 항목은 나중에 사용할 수 있도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-137">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="90e18-138">SipClientInternalAccess 및 SipClientExternalAccess에서는 내부 또는 외부 클라이언트가 정의 된 SIP 서버에 액세스 하는 데 사용 하는 정규화 된 도메인 이름 및 포트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-138">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="90e18-139">Lync 데스크톱 클라이언트 및 Lync Windows 스토어 앱은 위치 (내부 또는 외부)를 기반으로 하 여 디렉터 또는 프런트 엔드 서버를 찾는 이러한 항목을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-139">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="90e18-140">`Autodiscover`참조에 자동 검색 서비스에 대 한 서비스 진입점이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-140">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="90e18-141">Token 특성은 서비스 이름을 포함 하며, href는 서비스를 찾을 수 있는 클라이언트에 대해 정의 되는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-141">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="90e18-142">외부 네트워크의 클라이언트는를 사용 `External/Autodiscover` 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-142">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="90e18-143">자동 검색 서비스는 배포 프로세스의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-143">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="90e18-144">`Internal/Autodiscover` 는 현재 사용 되지 않으며 나중에 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-144">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="90e18-145">참조에는 `AuthBroker` 내부 및 외부 인증 브로커 서비스에 대 한 서비스 진입점 (이 경우에는 sip.)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-145">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="90e18-146">Token 특성은 서비스 이름을 포함 하며, href는 서비스를 찾을 수 있는 클라이언트에 대해 정의 되는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-146">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="90e18-147">사용 하는 내부 네트워크의 클라이언트 `Internal/AuthBroker`</span><span class="sxs-lookup"><span data-stu-id="90e18-147">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="90e18-148">외부 네트워크의 클라이언트는를 사용 `External/AuthBroker` 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-148">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="90e18-149">AuthBroker 서비스는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-149">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="90e18-150">이 `WebScheduler` 토큰은 Lync Server 회의에 대 한 웹 기반 예약에 대 한 클라이언트 액세스 url을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-150">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="90e18-151">현재만 `External/WebScheduler` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-151">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="90e18-152">WebScheduler는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-152">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="90e18-153">`Internal/Mcx` 또한 `External/Mcx` 모바일 서비스의 위치는 Lync Server 2010 용 누적 업데이트에서 도입 되었으며 11 월 2011입니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-153">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="90e18-154">이러한 참조는 지원 되는 모든 장치에서 Lync 2010 Mobile에 계속 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-154">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="90e18-155">Mcx 서비스는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-155">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="90e18-156">**내부/** 일부 wa, **외부/** c u c e c e c e c e c s e c e c e c e c e c e c e c e c e c/c e c e **c/c** e c l i</span><span class="sxs-lookup"><span data-stu-id="90e18-156">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="90e18-157">`Internal/Ucwa` 또한 `External/Ucwa` 가상 디렉터리는 미래 기능 개선을 위해 예약 된 액세스 포인트 이며 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-157">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="90e18-158">`Ucwa`지원 되는 모든 장치에서 Microsoft Lync Mobile (Lync Server 2013에 도입 됨)에 가상 디렉터리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-158">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="90e18-159">내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일환으로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-159">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="90e18-160">`Internal/XFrame`, **External/XFrame** 및 **XFRAME** 는 다중 wa 기반 서버 응용 프로그램에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-160">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="90e18-161">XFrame는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-161">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="90e18-162">`Self`이 토큰은 요청을 수행 하는 클라이언트 (사용자 응답 형식) 관련 정보를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-162">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="90e18-163">이 요청을 수행한 클라이언트는 외부에서 자동 검색 서비스의 사용자 부분으로 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e18-163">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90e18-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90e18-164">See Also</span></span>


[<span data-ttu-id="90e18-165">Lync Server 2013의 외부 사용자 액세스 구성 요소에 대 한 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="90e18-165">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="90e18-166">Lync Server 2013의 자동 검색 계획</span><span class="sxs-lookup"><span data-stu-id="90e18-166">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

