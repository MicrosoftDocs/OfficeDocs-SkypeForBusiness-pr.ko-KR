---
title: 'Lync Server 2013: 모바일 기능의 토폴로지 및 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 537eda14f2587e06bd8a1112f2a6a44299b0b78e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Lync Server 2013의 모바일 기능의 토폴로지 및 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

모바일 장치에서 Lync 모바일 응용 프로그램을 지원 하기 위해 Lync server 2013는 Lync Server 2013 Mcx Mobility Service, Lync Server 2013 자동 검색 서비스, Lync Server 2013 Push 알림 서비스 등의 세 가지 서비스를 제공 합니다. Lync Server 2013의 누적 업데이트: 2 월 2013에서는 Lync 2013 모바일 클라이언트에 대 한 고급 서비스, 즉 통합 커뮤니케이션 웹 API를 사용 하 여 이동성을 지 원하는 기능을 추가 합니다. 이 섹션에서는 이러한 구성 요소에 대해 간략하게 설명 하 고 모바일 기능을 지 원하는 Lync Server 2013 토폴로지를 식별 합니다.

<div>


> [!NOTE]  
> 하이브리드 배포 에서도 모바일 서비스를 사용할 수 있습니다. 사용자가 온라인 상태인 경우 이동성을 지원 하기 위해 서비스를 배포할 필요는 없습니다. 모바일 사용자가 온라인 id를 찾을 수 있도록 자동 검색 서비스에 대 한 설정을 정의 해야 합니다.



</div>

<div>


> [!IMPORTANT]  
> 외부 사용자 연결 (예: 페더레이션, 외부 사용자 액세스 또는 이동성 기능)을 계획 하는 경우에는 표준 버전 서버와 프런트 엔드 서버 또는 프런트 엔드 풀에 Edge 서버를 사용 해야 합니다. 스탠더드 버전 서버와 프런트 엔드 서버 또는 프런트 엔드 풀에는 외부 사용자가 내부 배포에 액세스 하거나 외부 사용자와 통신할 수 있도록 내부 배포에 대해 필요한 구성 요소가 없습니다. 외부 사용자에 게 공동 작업을 포함 하거나 모바일을 비롯 한 내부 사용자와 통신 하는 모든 시나리오의 경우에는 적어도 하나 이상의 Edge 서버와 한 개의 역방향 프록시를 배포 해야 합니다.<BR><EM>푸시 알림은</EM> 푸시 알림 클리어 링 하우스를 호스트 하는 Lync Online 서비스에 페더레이션 유형을 사용 합니다 (pnch). 푸시 알림은 모바일 장치가 비활성 상태일 때 응용 프로그램에서 Apple iPhone, iPad, Windows Phone으로 푸시된 사운드 알림, 화면 알림 (텍스트) 및 배지를 나타냅니다. PNCH는 Lync Server에서 푸시 알림을 받습니다. PNCH가 메시지 알림을 받으면, 메시지가 의도 한 모바일 클라이언트에 기반 하 여 Apple Push Notification Services 또는 Lync Server 2013 푸시 알림 서비스를 통해 모바일 클라이언트에 알림을 전달 합니다. PNCH는 이러한 모바일 클라이언트에 필요한 서비스입니다. Lync Online에 페더레이션 하려면 PNCH 및 인증서를 사용 하 여 기밀성 및 인증, 정책, 올바르게 구성 된 DNS (domain name system) 레코드를 확인 합니다. Nokia Symbian 및 Android 기반 Lync 모바일 클라이언트는 PNCH를 사용 하지 않습니다. Edge 서버를 계획 하 고 배포 하는 방법에 대 한 자세한 내용은 lync <A href="lync-server-2013-planning-for-external-user-access.md">server 2013에서 외부 사용자 액세스 계획</A> 및 <A href="lync-server-2013-deploying-external-user-access.md">lync server 2013에서 외부 사용자 액세스 배포</A>를 참고 하세요.<BR>Lync 2013 모바일 클라이언트에 대 한 lync 용 업데이트에 대 한 자세한 Apple Server 2013:2 월 2013이 더 이상 푸시 알림이나 푸시 알림 클리어 링 하우스 (PNCH)를 사용 하지 않습니다. Windows Phone의 Lync 2013 모바일 클라이언트는 계속 해 서 푸시 알림과 (PNCH)를 사용 합니다.



</div>

<div>

## <a name="mobility-components"></a>모바일 구성 요소

이동성을 지 원하는 서비스는 다음과 같습니다.

  - **Lync server 2013 통합 커뮤니케이션 웹 API (c)**   는 lync server 2013의 모바일 및 웹 클라이언트와의 실시간 통신을 위한 서비스를 제공 합니다. Lync Server 2013 2013에 대 한 누적 업데이트를 배포 하는 경우 프런트 엔드 서버 및 디렉터에 대 한이 설치에는 내부 및 외부 웹 서비스 (인천 wa)에 가상 디렉터리가 만들어집니다. 웹 구성 요소는 함께 사용할 수 있는 가상 디렉터리의 일부입니다. 클라이언트 앱은 현재 상태, 연락처, 인스턴트 메시지, VoIP, 영상 회의, 공동 작업을 위해 REST 인터페이스를 통해 통신 합니다. (A) P-GET 기반 채널을 사용 하 여 수신 전화, 들어오는 인스턴트 메시지 또는 클라이언트 앱에 대 한 메시지 등의 이벤트를 보냅니다.
    
    <div>
    

    > [!NOTE]  
    > <EM>REST</EM> 또는 representational 상태 전송은 다양 한 양식에서 널리 채택 되었으며 일반적으로 웹 서비스 요구 사항에 가장 적합 한 분산 시스템에 대 한 소프트웨어 아키텍처 스타일입니다.

    
    </div>

  - **Lync Server 2013 Mobility services (mcx)**   이 서비스는 모바일 장치에서 메신저 대화 (IM), 현재 상태, 대화 상대 등의 Lync 기능을 지원 합니다. 모바일 장치에서 Lync 기능을 지 원하는 각 풀의 모든 프런트 엔드 서버에 모바일 서비스가 설치 되어 있습니다. Lync Server 2013을 설치할 때 내부 웹 사이트와 프런트 엔드 서버의 외부 웹 사이트 모두에 새 가상 디렉터리 (Mcx)가 만들어집니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync server 2013에 대 한 누적 업데이트가 포함 된 lync 서버 2013:2 월 2013은 Lync Server 2011 2010의 누적 업데이트에 도입 된 이동성 서비스 (일반적으로 Mcx로 알려진, 즉, e-)를 지원 합니다. 이러한 두 가지 이동성 서비스의 조합으로 lync 2010 모바일 및 lync 2013 모바일 2013 클라이언트를 사용할 수 있는 사용자의 상호 운용성 및 사용을 제공 합니다.

    
    </div>

  - **Lync server 2013 자동 검색 서비스**   이 서비스는 사용자의 위치를 식별 하 고 모바일 장치 및 다른 Lync 클라이언트가 lync Server 2013 웹 서비스의 내부 및 외부 url과 네트워크 위치에 관계 없이 mcx 또는 xwa의 URL을 찾을 수 있도록 합니다. 자동 검색은 하드 코드 된 호스트 이름 (네트워크 내부의 사용자에 게 lyncdiscoverinternal, 네트워크 외부 사용자를 위한 lyncdiscover) 및 사용자의 SIP 도메인을 사용 합니다. HTTP 또는 HTTPS 중 하나를 사용 하는 클라이언트 연결을 지원 합니다.
    
    자동 검색 서비스는 모바일 장치에서 Lync 기능을 지 원하는 모든 프런트 엔드 서버와 각 풀의 모든 디렉터에 설치 됩니다. 자동 검색 서비스를 설치 하는 경우 프런트 엔드 서버와 디렉터 모두에서 내부 웹 사이트와 외부 웹사이트 모두에서 새 자동 검색 (virtual directory)이 만들어집니다.
    
    <div>
    

    > [!NOTE]  
    > 자동 검색 서비스는 모바일 클라이언트 서비스를 제공할 때 중요 한 구성 요소로 남아 있기 때문에 여기에 나열 되어 있습니다. Lync Server 2013의 자동 검색 역할이 모든 클라이언트에 대 한 서비스를 제공 하도록 확장 되었습니다. 자동 검색 서비스 계획에 대 한 자세한 내용은 <A href="lync-server-2013-planning-for-autodiscover.md">Lync Server 2013에서 자동 검색 계획</A>을 참조 하세요.

    
    </div>

  - **푸시 알림 서비스**   이 서비스는 Lync Online 데이터 센터에 있는 클라우드 기반 서비스입니다. 지원 되는 Apple iOS 장치 또는 Windows Phone에서 Lync 모바일 응용 프로그램을 사용할 수 없는 경우 새로운 이벤트 (예: 메신저 대화) 초대, 부재 중 메신저 대화, 부재 중 통화, 음성 메일 등 해당 장치에서 지원 되지 않기 때문에이에 응답할 수가 없습니다. 백그라운드에서 실행 되는 모바일 응용 프로그램 이러한 경우 *푸시 알림*이라는 새 이벤트에 대 한 알림이 모바일 장치로 전송 됩니다. 모바일 서비스는 클라우드 기반 푸시 알림 서비스에 알림을 보내고,이는 APNS (Apple 푸시 알림 서비스) (지원 Apple iOS 장치용) 또는 Microsoft 푸시 알림 서비스 (MPNS)에 알림을 보냅니다. ) (Windows Phone의 경우)로 이동 하 여 모바일 장치에 보냅니다. 그러면 사용자가 모바일 장치에서 알림에 응답 하 여 응용 프로그램을 활성화할 수 있습니다.
    
    Apple 및 Windows Phone 장치에서 Lync 2010 Mobile은 푸시 알림을 사용 합니다. Lync 2013 모바일 클라이언트에 대 한 lync 용 업데이트에 대 한 자세한 Apple Server 2013:2 월 2013은 더 이상 푸시 알림이나 푸시 알림 클리어 하우스 (PNCH)를 사용 하지 않습니다.

다음 다이어그램에서는이 지 각 및 Lync 2013 모바일 클라이언트를 사용 하는 Lync Server 2013 토폴로지 내에 적용 되는 푸시 알림 서비스를 보여 줍니다.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Lync x 서비스가 lync의 누적 업데이트에서 도입 되었습니다. 2010 2011 년 11 월에는 Mcx 서비스에서 Lync 2010 모바일 클라이언트에 대 한 서비스를 제공 합니다. 다음 다이어그램은 Mcx 및 Lync 2010 모바일 클라이언트를 사용 하 여 토폴로지에 적용 되는 푸시 알림 서비스를 보여 줍니다.

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>지원 되는 토폴로지

Lync Server에 대 한 누적 업데이트 적용 2013:2 월 2013에서는 다음 토폴로지의 Lync 2013 모바일 클라이언트 기능에 대 한 이동성을 지원 하기 위해 웹 구성 요소를 추가 합니다.

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

Edge 서버는 Lync Server 2010 Edge 서버 일 수 있습니다.

Lync server 2013에 대 한 누적 업데이트 없이 Lync 서버 2013 배포: 2 월 2013은 Mcx Mobility Service를 사용 하며 Lync 2010 Mobile에만 서비스를 제공할 수 있습니다.

<div>


> [!IMPORTANT]  
> 모바일 서비스는 두 개의 네트워크 인터페이스를 사용 하는 중재 서버 역할을 collocated 하는 프런트 엔드 서버에서 지원 되지만 인터페이스를 구성 하는 적절 한 단계를 수행 해야 합니다. 중재 서버로 통신 하는 특정 인터페이스에 IP 주소를 할당 하 고 프런트 엔드 서버로 통신 하는 네트워크 인터페이스 IP를 지정 해야 합니다. <STRONG>구성 된 모든 IP 주소</STRONG>를 사용 하는 대신 각 서비스에 대 한 올바른 IP 주소를 선택 하 여 토폴로지 작성기에서이 작업을 수행할 수 있습니다.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md)  
[Lync Server 2013의 자동 검색 계획](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

