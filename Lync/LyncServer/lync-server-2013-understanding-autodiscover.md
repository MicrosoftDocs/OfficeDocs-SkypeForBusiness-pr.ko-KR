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
ms.openlocfilehash: f57dd0158f4a9b6c798d1b968353e5f84b55d46e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Lync Server 2013의 자동 검색 이해

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-06-03_

Lync Server 2013 자동 검색 서비스는 Lync Server 2010:11 월 2011에 대 한 누적 업데이트의 일부로, 원래 Microsoft Lync Server 2010에 도입 된 기능입니다. 수정 사항 외에도이 누적 업데이트는 Lync Mobile 및 Lync 2013 클라이언트에 대 한 지원을 제공 합니다.

Lync Server 2013에서 자동 검색 서비스는 외부 및 내부 모바일 클라이언트 작업의 필수 부분이 며, Windows 8 용으로 최근에 도입 된 Lync Windows 스토어 앱과 같은 새 클라이언트로도 자동 검색을 확장 합니다. 자동 검색은 Lync 2013 데스크톱 클라이언트 에서도 사용 됩니다. 입력은 필요한 DNS (domain name system) record **lyncdiscover를 통해 Lync Server에서 인식 됩니다\< . 도메인\> ** 및 **lyncdiscoverinternal.\< 도메인\>** 또한 최신 버전의 Lync 2010 및 Lync 2013 데스크톱 클라이언트는 DNS (domain name system) SRV 레코드에 대 한 자동 검색을 우선적으로 사용 합니다 (lyncdiscover 인 경우에만 DNS SRV 레코드). \<도메인\> 또는 lyncdiscoverinternal \<도메인이\> 응답 하지 않거나 확인 하지 않습니다. Windows 8 및 Lync Mobile 용 Lync Windows 스토어 앱은 자동 검색을 단독으로 사용 하며 기존 DNS SRV 레코드를 참조 하지 않습니다.

Lync Server 2013에서는 클라이언트에서 사용할 수 있는 요소, 기능 및 통신 방법을 클라이언트에 알리기 위해 자동 검색 기능이 확장 되었습니다. 이 정보는 클라이언트에서 전송 되는 요청을 통해 전달 되며, Lync Server 웹 서비스는 클라이언트에 게 제공 되는 이름을 명확 하 게 정의 된 응답과 함께 응답 하 고 해당 기능에 문의 하 여 자동 검색 형식으로 연락 하는 방법을 설명 합니다. 응답 문서

웹 서비스가이 문서를 통해 클라이언트에 기능을 전달 하는 방법을 비롯 하 여 자동 검색 응답 문서를 이해 하는 가장 좋은 방법은 Lync web service 자동 검색 응답 문서의 일반적인 응답에서 각 줄을 dissect 하 고 정의 하는 것입니다.

<div class="">


> [!NOTE]  
> 팔 로우 하는 세부 정보에서는 인증 요청에 응답 하 여 사용자가 이미 홈 서버에 인증 되었습니다.



</div>

<div class="">


> [!NOTE]  
> Lync 자동 검색 웹 서비스는 MSDN ( <STRONG>Microsoft Developer Network</STRONG> ) 라이브러리의 <STRONG>공개 사양</STRONG> 섹션에 있는 <STRONG>microsoft Office 프로토콜</STRONG> 에 정의 되어 있습니다. 자세한 내용은의 "Lync 자동 검색 웹 서비스 프로토콜" <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>전체 사양 문서를 참조 하십시오. 인증에 대 한 자세한 내용은의 <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>"OC 인증 웹 서비스 프로토콜"을 참조 하세요.



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Lync Server 웹 서비스 자동 검색 응답

자동 검색 요청이 전송 될 때 반환 되는 응답은 내부 또는 외부 클라이언트에서 동일 합니다. 위치를 확인 하는 일부 매개 변수는 변경 될 수 있습니다. 클라이언트 요청을 받았지만 실제 풀이 연결 된 것과 다른 경우에는 해당 사용자에 대해 사용자의 홈 풀이 설정 됩니다. 사용자 계정이 다른 풀에 있지만 같은 사무실의 로그인 인 동료는 약간 다른 응답을 받게 됩니다. 응답은 해당 사용자에 대 한 올바른 프런트 엔드 서버 또는 프런트 엔드 풀을 나타냅니다.

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

자동 검색 응답 문서는 두 가지 형식 중 하나일 수 있습니다. 기본 형식은 JSON (JavaScript Object Notation)입니다. 다른 형식은 XML (extensible markup language) 문서입니다. 이 예제에서는 XML이 사용 됩니다. 문서에 형식을 결정 하는 정의 된 스키마가 있기 때문에 요청 및 응답은 예측 가능 합니다. 사용 된 스키마를 설명 하는 문서의 줄은 요청 또는 응답의 첫 번째 줄입니다.

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

**Accesslocation = "External"** 정의는 외부 사용자 로부터 요청이 수행 되었음을 나타냅니다.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess 및 SipServerExternalAccess는 현재 사용 되지 않습니다. 이러한 항목은 나중에 사용할 수 있도록 예약 되어 있습니다.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess 및 SipClientExternalAccess에서는 내부 또는 외부 클라이언트가 정의 된 SIP 서버에 액세스 하는 데 사용 하는 정규화 된 도메인 이름 및 포트를 설명 합니다. Lync 데스크톱 클라이언트 및 Lync Windows 스토어 앱은 위치 (내부 또는 외부)를 기반으로 하 여 디렉터 또는 프런트 엔드 서버를 찾는 이러한 항목을 사용 합니다.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

참조 `Autodiscover` 에 자동 검색 서비스에 대 한 서비스 진입점이 포함 됩니다. Token 특성은 서비스 이름을 포함 하며, href는 서비스를 찾을 수 있는 클라이언트에 대해 정의 되는 URL입니다. 외부 네트워크의 클라이언트는를 `External/Autodiscover`사용 합니다. 자동 검색 서비스는 배포 프로세스의 일부로 설치 됩니다. `Internal/Autodiscover`는 현재 사용 되지 않으며 나중에 사용 하도록 예약 되어 있습니다.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

참조 `AuthBroker` 에는 내부 및 외부 인증 브로커 서비스에 대 한 서비스 진입점 (이 경우에는 sip.)이 포함 됩니다. Token 특성은 서비스 이름을 포함 하며, href는 서비스를 찾을 수 있는 클라이언트에 대해 정의 되는 URL입니다. 사용 `Internal/AuthBroker`하는 내부 네트워크의 클라이언트 외부 네트워크의 클라이언트는를 `External/AuthBroker`사용 합니다. AuthBroker 서비스는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

이 `WebScheduler` 토큰은 Lync Server 회의에 대 한 웹 기반 예약에 대 한 클라이언트 액세스 url을 참조 합니다. 현재만 사용 `External/WebScheduler` 됩니다. WebScheduler는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`또한 `External/Mcx` 모바일 서비스의 위치는 Lync Server 2010 용 누적 업데이트에서 도입 되었으며 11 월 2011입니다. 이러한 참조는 지원 되는 모든 장치에서 Lync 2010 Mobile에 계속 사용 됩니다. Mcx 서비스는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**내부/** 일부 wa, **외부/** c u c e c e c e c e c s e c e c e c e c e c e c e c e c e c/c e c e **c/c** e c l i `Internal/Ucwa`또한 `External/Ucwa` 가상 디렉터리는 미래 기능 개선을 위해 예약 된 액세스 포인트 이며 사용 되지 않습니다. 지원 `Ucwa` 되는 모든 장치에서 Microsoft lync Mobile (lync Server 2013에 도입 됨)에 가상 디렉터리를 사용 합니다. 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일환으로 지원 됩니다.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/XFrame** 및 **XFRAME** 는 다중 wa 기반 서버 응용 프로그램에 대 한 액세스를 제공 합니다. XFrame는 내부 Lync Server 2013 배포 웹 서비스 배포 프로세스의 일부로 설치 됩니다.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

이 `Self` 토큰은 요청을 수행 하는 클라이언트 (사용자 응답 형식) 관련 정보를 참조 합니다. 이 요청을 수행한 클라이언트는 외부에서 자동 검색 서비스의 사용자 부분으로 참조 됩니다.

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 외부 사용자 액세스 구성 요소에 대 한 시스템 요구 사항](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Lync Server 2013의 자동 검색 계획](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

