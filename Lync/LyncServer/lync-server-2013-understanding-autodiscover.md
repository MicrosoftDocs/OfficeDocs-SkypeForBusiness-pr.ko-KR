---
title: 'Lync Server 2013: 자동 검색 이해'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae8a4965674952cfa5822c24e887ed4d5a02b798
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Lync Server 2013의 자동 검색 이해

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-06-03_

Lync Server 2013 자동 검색 서비스는 Lync Server 2010:11 월 2011에 대 한 누적 업데이트의 일부로 Microsoft Lync Server 2010에서 원래 도입 된 기능입니다. 이 누적 업데이트는 픽스 외에도 Lync Mobile 및 Lync 2013 클라이언트에 대 한 지원을 제공 합니다.

Lync Server 2013에서 자동 검색 서비스는 외부 및 내부 모바일 클라이언트 작업의 핵심 부분이 며 Windows 8 용 Lync Windows 스토어 앱과 같은 새 클라이언트에도 자동 검색을 확장 합니다. 자동 검색은 Lync 2013 데스크톱 클라이언트 에서도 사용 됩니다. 입력 하는 DNS (domain name system) 레코드는 Lync Server에서 알 수 **있습니다.\< 도메인\> ** 및 **lyncdiscoverinternal.\< 도메인\>**. 또한 Lync 2010 및 Lync 2013 데스크톱 클라이언트의 최신 버전은 DNS (domain name system) SRV 레코드에 대 한 자동 검색을 사용 하 고, lyncdiscover 인 경우에만 DNS SRV 레코드를 사용할 수도 있습니다. \<도메인\> 또는 lyncdiscoverinternal. \<도메인이\> 응답 하지 않거나 확인 되지 않습니다. Windows 8 및 Lync Mobile 용 Lync Windows 스토어 앱은 자동 검색을 독점적으로 사용 하므로 기존 DNS SRV 레코드를 참조 하지 않습니다.

Lync Server 2013에서는 클라이언트가 사용할 수 있는 요소, 기능 및 통신 방법을 클라이언트와 통신 하기 위해 자동 검색을 확장 합니다. 이 정보는 클라이언트에서 전송 되는 요청을 통해 전달 되며, Lync Server 웹 서비스는 클라이언트에 게 제공 되는 응답을 명확 하 게 정의 하 여 응답 하 고 해당 기능에 대 한 자동 검색 형식으로 연락 하는 방법을 설명 합니다. 응답 문서.

웹 서비스에서이 문서를 통해 클라이언트에 기능을 전달 하는 방법을 비롯 하 여 자동 검색 응답 문서를 이해 하는 가장 좋은 방법은 Lync 웹 서비스 자동 검색 응답 문서의 일반적인 응답에서 각 줄을 dissect 하 고 정의 하는 것입니다.

<div class="">


> [!NOTE]  
> 팔 로우 하는 세부 정보에서 사용자는 인증 요청에 응답 하 여 이미 홈 서버에 대 한 인증을 받은 것입니다.



</div>

<div class="">


> [!NOTE]  
> Lync 자동 검색 웹 서비스는 microsoft <STRONG>Office 프로토콜</STRONG> 에서 MSDN ( <STRONG>microsoft Developer Network</STRONG> ) 라이브러리의 <STRONG>열기 사양</STRONG> 섹션에 정의 되어 있습니다. 자세한 내용은의 전체 사양 문서 "Lync 자동 검색 웹 서비스 프로토콜"을 참조 하세요 <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>. 인증에 대 한 자세한 내용은의 <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>"OC 인증 웹 서비스 프로토콜"을 참조 하세요.



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Lync Server 웹 서비스 자동 검색 응답

자동 검색 요청이 전송 될 때 반환 되는 응답은 내부 또는 외부 클라이언트에 대해 동일 합니다. 위치 인식의 일부 매개 변수는 변경 될 수 있습니다. 클라이언트 요청이 수신 되지만 실제 풀이 연결 된 것과 다른 경우 해당 사용자에 대해 사용자의 홈 풀이 설정 됩니다. 해당 사용자 계정이 다른 풀에 있지만 같은 사무실에서 로그인 하는 동료는 약간 다른 응답을 받을 수 있습니다. 응답은 해당 사용자의 올바른 프런트 엔드 서버 또는 프런트 엔드 풀을 나타냅니다.

자동 검색 응답 문서의 예:

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

## <a name="autodiscover-response-document-details"></a>자동 검색 응답 문서 세부 정보

자동 검색 응답 문서는 두 가지 형식 중 하나가 될 수 있습니다. 기본 형식은 JSON (JavaScript 개체 표기법)입니다. 다른 형식은 XML (extensible markup language) 문서입니다. XML이이 예제에 사용 됩니다. 문서에 형식을 결정 하는 정의 된 스키마가 있기 때문에 요청 및 응답은 예측 가능 합니다. 사용 된 스키마를 설명 하는 문서의 줄은 요청 또는 응답의 첫 번째 줄입니다.

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

**Accesslocation = "External"** 의 정의는 외부 사용자가 요청 했음을 나타냅니다.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess 및 SipServerExternalAccess는 현재 사용 되지 않습니다. 이러한 항목은 나중에 사용할 수 있도록 예약 되어 있습니다.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess 및 SipClientExternalAccess는 내부 또는 외부 클라이언트에서 정의 된 SIP 서버에 액세스 하는 데 사용 하는 정규화 된 도메인 이름 및 포트를 설명 합니다. Lync 데스크톱 클라이언트와 Lync Windows 스토어 앱은 해당 위치 (내부 또는 외부)에 따라 디렉터 또는 프런트 엔드 서버를 찾을 때 이러한 항목을 사용 합니다.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

참조 `Autodiscover` 에는 자동 검색 서비스에 대 한 서비스 진입점이 포함 되어 있습니다. Token 특성은 서비스의 이름을 포함 하 고 href는 서비스를 찾을 수 있는 클라이언트에 대해 정의 하는 URL입니다. 외부 네트워크의 클라이언트는를 `External/Autodiscover`사용 합니다. 자동 검색 서비스는 배포 프로세스의 일부로 설치 됩니다. `Internal/Autodiscover`는 현재 사용 되지 않으며 나중에 사용할 수 있도록 예약 되어 있습니다.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

참조 `AuthBroker` 에는 내부 및 외부 인증 브로커 서비스에 대 한 서비스 진입점 (이 경우에는 sip.)이 포함 됩니다. Token 특성은 서비스의 이름을 포함 하 고 href는 서비스를 찾을 수 있는 클라이언트에 대해 정의 하는 URL입니다. 사용 `Internal/AuthBroker`하는 내부 네트워크의 클라이언트 외부 네트워크의 클라이언트는를 `External/AuthBroker`사용 합니다. AuthBroker 서비스는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

이 `WebScheduler` 토큰은 Lync 서버 컨퍼런스에 대 한 웹 기반 예약에 대 한 클라이언트 액세스 url을 참조 합니다. 현재만 사용 `External/WebScheduler` 됩니다. WebScheduler는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx``External/Mcx` Lync Server 2010의 누적 업데이트에서 도입 된 모바일 서비스의 위치는 11 월 2011입니다. 이러한 참조는 지원 되는 모든 장치에서 Lync 2010 Mobile에서 계속 사용할 수 있습니다. Mcx 서비스는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**내부/** 일부, **외부/** c u c e **, c** u r a r a c c e a c c e c a r a r a e a u a e a e a e a e a e a c e a c c `Internal/Ucwa`그리고 `External/Ucwa` 가상 디렉터리는 향후 기능 향상을 위해 예약 된 액세스 포인트 이며 사용 되지 않습니다. 가상 `Ucwa` 디렉터리는 지원 되는 모든 장치에서 Microsoft lync Mobile (Lync Server 2013에서 도입 됨)에 사용 됩니다. 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/XFrame** 및 **XFrame** 는 wa 기반 서버 응용 프로그램에 대 한 액세스를 제공 합니다. XFrame는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

토큰 `Self` 은 요청을 보내는 클라이언트 (사용자 응답 형식)에 대 한 정보를 나타냅니다. 이 요청을 만든 클라이언트는 외부이 고,이 자동 검색 참조는 자동 검색 서비스의 사용자 부분에 해당 합니다.

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 외부 사용자 액세스 구성 요소에 대한 시스템 요구 사항](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Lync Server 2013의 자동 검색 계획](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

