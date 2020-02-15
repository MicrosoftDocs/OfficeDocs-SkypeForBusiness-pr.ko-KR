---
title: 'Lync Server 2013: 모바일 기능에 대 한 토폴로지 및 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac03d6b98b0b209a50f08e660fe6665b975d2ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Lync Server 2013의 모바일 기능에 대 한 토폴로지 및 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013에서는 모바일 장치에서 Lync 모바일 응용 프로그램을 지원 하기 위해 lync server 2013 Mcx Mobility Service, Lync Server 2013 자동 검색 서비스 및 Lync Server 2013 Push Notification Service의 세 가지 서비스를 제공 합니다. Lync Server 2013에 대 한 누적 업데이트: 2 월 2013에는 통합 커뮤니케이션 웹 API를 사용 하 여 이동성을 지원 하는 무료 및 고급 서비스인 Lync 2013 모바일 클라이언트를 추가 합니다. 이 섹션에서는 이러한 구성 요소에 대해 간략하게 설명 하 고 모바일 기능을 지 원하는 Lync Server 2013 토폴로지를 식별 합니다.

<div>


> [!NOTE]  
> Mobility Service는 하이브리드 배포에서도 사용할 수 있습니다. 사용자가 온라인에 배치된 경우 모바일 기능을 지원하기 위해 서비스를 배포할 필요가 없습니다. 모바일 사용자가 온라인 id를 찾을 수 있도록 자동 검색 서비스에 대 한 설정을 정의 해야 합니다.



</div>

<div>


> [!IMPORTANT]  
> 외부 사용자 연결 (예: 페더레이션, 외부 사용자 액세스 또는 모바일 기능)을 계획 하는 경우 Standard Edition server 및 프런트 엔드 서버 또는 프런트 엔드 풀과 함께에 지 서버를 사용 해야 합니다. Standard Edition 서버와 프런트 엔드 서버 또는 프런트 엔드 풀에는 외부 사용자가 내부 배포에 액세스 하거나 내부 배포가 외부 사용자와 통신 하도록 하기 위한 필수 구성 요소가 없습니다. 외부 사용자가 공동 작업을 하거나 내부 사용자와 통신 하는 경우 (모바일 기능 포함), 하나 이상의에 지 서버와 하나의 역방향 프록시를 배포 해야 합니다.<BR><EM>푸시 알림</EM> 에서는 pnch (푸시 알림 클리어 링 하우스)를 호스트 하는 Lync Online 서비스에 대 한 페더레이션 유형을 사용 합니다. 푸시 알림은 모바일 장치가 비활성 상태일 때 응용 프로그램에서 Apple iPhone, iPad 및 Windows Phone으로 푸시된 소리 알림, 화면 알림 (텍스트) 및 배지를 참조 합니다. PNCH는 Lync Server에서 푸시 알림을 받습니다. PNCH가 메시지 알림을 받으면, PNCH는 메시지를 받는 모바일 클라이언트에 따라 Apple Push Notification Services 또는 Lync Server 2013 Push Notification Service를 통해 모바일 클라이언트에 알림을 전달 합니다. PNCH는 이러한 모바일 클라이언트에서 필수적인 서비스입니다. Lync Online에 페더레이션 하기 위해 PNCH는에 지 서버 및 인증서를 사용 하 여 기밀성 및 인증, 정책 및 올바르게 구성 된 DNS (domain name system) 레코드를 확인 합니다. Nokia Symbian 및 Android 기반 Lync 모바일 클라이언트는 PNCH를 사용 하지 않습니다. 에 지 서버를 계획 하 고 배포 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-planning-for-external-user-access.md">Lync server 2013의 외부 사용자 액세스 계획</A> 및 <A href="lync-server-2013-deploying-external-user-access.md">lync server 2013의 외부 사용자 액세스 배포</A>를 참조 하세요.<BR>Lync Server 2013에 대 한 Lync 2013 모바일 클라이언트에서는 더 이상 푸시 알림 또는 PNCH (푸시 알림 클리어 링 하우스)를 사용 하지 않습니다 2013. Lync 2013 Windows Phone의 모바일 클라이언트는 여전히 푸시 알림과 (PNCH)를 사용 합니다.



</div>

<div>

## <a name="mobility-components"></a>모바일 기능 구성 요소

모바일 기능을 지원하는 서비스는 다음과 같습니다.

  - **Lync server 2013 통합 커뮤니케이션 웹 API (c)**   는 lync server 2013의 모바일 및 웹 클라이언트와의 실시간 통신을 위한 서비스를 제공 합니다. Lync Server 2013 2013에 대 한 누적 업데이트를 배포 하는 경우에는 프런트 엔드 서버 및 디렉터에 대 한 가상 디렉터리가 설치 됩니다 (내부 및 외부 웹 서비스). C u c 가상 디렉터리의 일부인 웹 구성 요소는가 중 WA-사용 가능 클라이언트의 통화를 수락 합니다. 클라이언트 응용 프로그램은 현재 상태, 연락처, 인스턴트 메시징, VoIP, 비디오 회의 및 공동 작업을 위해 REST 인터페이스를 통해 통신 합니다. (C)는 P 가져오기 기반 채널을 사용 하 여 들어오는 통화, 들어오는 인스턴트 메시지 또는 클라이언트 응용 프로그램에 대 한 메시지와 같은 이벤트를 보냅니다.
    
    <div>
    

    > [!NOTE]  
    > <EM>REST</EM> 또는 representational 상태 전송은 대부분의 양식에서 널리 채택 되 고 일반적인 웹 서비스 요구 사항에 적합 한 분산 시스템에 대 한 소프트웨어 아키텍처 스타일입니다.

    
    </div>

  - **Lync Server 2013 모바일 서비스 (mcx)**   이 서비스는 모바일 장치에서 IM (인스턴트 메시징), 현재 상태 및 연락처와 같은 Lync 기능을 지원 합니다. 모바일 서비스는 각 풀의 모든 프런트 엔드 서버에 설치 됩니다. Lync Server 2013을 설치할 때 내부 웹 사이트와 프런트 엔드 서버의 외부 웹 사이트 모두에 새 가상 디렉터리 (Mcx)가 만들어집니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync server 2013에 대 한 누적 업데이트: 2 월 12 일 2013은 Lync Server 2010:11 월 2011, 일반적으로 Mcx 및 c 지 웹 구성 요소에 도입 된 모바일 서비스를 모두 지원 합니다. 2013 이러한 두 mobility services의 조합은 lync Server 2013에서 Lync 2010 모바일 및 Lync 2013 모바일 클라이언트를 사용 하는 사용자의 상호 운용성 및 사용을 제공 합니다.

    
    </div>

  - **Lync server 2013 자동 검색 서비스**   이 서비스는 사용자의 위치를 식별 하 고 모바일 장치 및 기타 Lync 클라이언트에서 lync Server 2013 웹 서비스의 내부 및 외부 url, 네트워크 위치에 관계 없이 mcx 또는 인천 wa의 url과 같은 리소스를 찾을 수 있도록 합니다. 자동 검색에서는 하드 코드 된 호스트 이름 (네트워크 내부의 사용자에 게는 lyncdiscoverinternal) 및 사용자의 SIP 도메인을 사용 합니다. HTTP 또는 HTTPS 중 하나를 사용 하는 클라이언트 연결을 지원 합니다.
    
    자동 검색 서비스는 모바일 장치에서 Lync 기능을 지원 하기 위해 모든 프런트 엔드 서버 및 각 풀의 모든 디렉터에 설치 됩니다. 자동 검색 서비스를 설치 하면 프런트 엔드 서버와 디렉터 모두에 내부 웹 사이트와 외부 웹 사이트의 새 자동 검색 (가상 디렉터리)이 만들어집니다.
    
    <div>
    

    > [!NOTE]  
    > 자동 검색 서비스는 모바일 클라이언트 서비스를 제공할 때 중요 한 구성 요소로 남아 있으므로 여기에 나열 됩니다. Lync Server 2013의 자동 검색 역할이 모든 클라이언트에 대 한 서비스를 제공 하도록 확장 되었습니다. 자동 검색 서비스를 계획 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-planning-for-autodiscover.md">Lync Server 2013에서 자동 검색 계획</A>을 참조 하십시오.

    
    </div>

  - **푸시 알림 서비스**   이 서비스는 Lync Online 데이터 센터에 있는 클라우드 기반 서비스입니다. 지원 되는 Apple iOS 장치 또는 Windows Phone에서 Lync 모바일 응용 프로그램을 사용할 수 없는 경우에는 이러한 장치에서 지원 하지 않으므로 새 이벤트 (IM) 초대, 부재 중 메신저 대화, 부재 중 전화 또는 음성 메일 같은 응답을 받지 못합니다. 백그라운드에서 실행 되는 모바일 응용 프로그램 이러한 경우 새 이벤트에 대 한 알림 ( *푸시 알림*이라고 함)이 모바일 장치로 전송 됩니다. 모바일 서비스가 클라우드 기반 푸시 알림 서비스에 알림을 보낸 다음 APNS (Apple Push Notification Service) (지원 되는 Apple iOS 장치용) 또는 Microsoft 푸시 알림 서비스 (MPNS)에 알림을 보냅니다. ) (Windows Phone)의 경우 모바일 장치로 보냅니다. 그러면 사용자가 모바일 장치의 알림에 응답 하 여 응용 프로그램을 활성화할 수 있습니다.
    
    Apple 및 Windows Phone 장치에서 Lync 2010 Mobile은 푸시 알림을 사용 합니다. Lync Server 2013에 대 한 Lync 2013 모바일 클라이언트에서는 더 이상 푸시 알림 또는 PNCH (푸시 알림 클리어 링 하우스)를 사용 하지 않습니다 2013.

다음 다이어그램에서는 e u c e 및 Lync 2013 모바일 클라이언트를 사용 하는 Lync Server 2013 토폴로지 내에 푸시 알림 서비스가 어떻게 맞는지 보여 줍니다.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Lync Server 용 누적 업데이트에서 도입 되었습니다 2011.2010: Mcx 서비스는 Lync 2010 Mobile 클라이언트에 서비스를 제공 합니다. 다음 다이어그램에서는 Mcx 및 Lync 2010 모바일 클라이언트를 사용 하는 토폴로지에 적용 되는 푸시 알림 서비스를 보여 줍니다.

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>지원되는 토폴로지

Lync Server에 대 한 누적 업데이트 적용 2013:2 월 2013에는 다음과 같은 토폴로지의 Lync 2013 모바일 클라이언트 기능에 대 한 이동성을 지원 하기 위한 웹 구성 요소를 추가 합니다.

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

에 지 서버는 Lync Server 2010에 지 서버로 사용할 수 있습니다.

Lync server 2013에 대 한 누적 업데이트가 없는 Lync 서버 2013 배포: 2 월 2013은 Mcx Mobility Service를 사용 하며 Lync 2010 Mobile에만 서비스를 제공할 수 있습니다.

<div>


> [!IMPORTANT]  
> 모바일 서비스는 두 개의 네트워크 인터페이스를 사용 하는 중재 서버 역할을 가진 배치 된 프런트 엔드 서버에서 지원 되지만 적절 한 단계를 수행 하 여 인터페이스를 구성 해야 합니다. 중재 서버로 통신할 특정 인터페이스에 IP 주소를 할당 하 고 프런트 엔드 서버로 통신할 네트워크 인터페이스 IP를 지정 해야 합니다. <STRONG>구성 된 모든 IP 주소</STRONG>를 사용 하는 대신 각 서비스에 대 한 올바른 IP 주소를 선택 하 여 토폴로지 작성기에서이 작업을 수행할 수 있습니다.



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

