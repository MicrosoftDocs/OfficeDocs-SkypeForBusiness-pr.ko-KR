---
title: Lync Server 2013 서버 역할
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b22115bf137c388fd6cd15103ac882056affa4f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Lync Server 2013의 서버 역할

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-07_

Lync Server를 실행 하는 각 서버는 하나 이상의 *서버 역할*을 실행 합니다. 서버 역할은 해당 서버에서 제공 하는 Lync Server 기능을 정의한 집합입니다. 네트워크에서 사용 가능한 모든 서버 역할을 배포할 필요는 없습니다. 원하는 기능이 포함 된 서버 역할만 설치 합니다.

Lync Server의 서버 역할에 익숙하지 않은 경우에도 계획 도구를 사용 하 여 원하는 기능에 따라 배포 해야 하는 서버에 대 한 최상의 솔루션을 안내할 수 있습니다. 이 섹션에서는 서버 역할 및 제공 하는 일반 기능에 대 한 간략 한 개요를 제공 합니다.

  - Standard Edition 서버

  - 프런트 엔드 서버 및 백 엔드 서버

  - Edge 서버

  - 중재 서버

  - Director

  - 영구 채팅 프런트 엔드 서버

  - 영구 채팅 저장소 (영구 채팅 백 엔드 서버)

  - 영구 채팅 준수 스토어 (영구 채팅 준수 백 엔드 서버)

대부분의 서버 역할에서 확장성 및 고가용성을 위해 동일한 서버 역할을 실행 하는 여러 서버의 *풀* 을 배포할 수 있습니다. 풀의 각 서버는 동일한 서버 역할 또는 역할을 실행 해야 합니다. Lync Server의 대부분의 풀 유형에 대해 부하 분산 장치를 배포 하 여 풀의 다양 한 서버 간에 트래픽을 분산 해야 합니다. Lync Server는 DNS (Domain Name System) 부하 분산 및 하드웨어 부하 분산 장치를 모두 지원 합니다.

<div>

## <a name="standard-edition-server"></a>Standard Edition 서버

스탠더드 버전 서버는 소규모 조직을 위해 디자인 되었으며 대규모 조직의 경우 파일럿 프로젝트에 적합 합니다. 이를 통해 단일 서버에서 실행 하는 데 필요한 데이터베이스를 비롯 한 다양 한 Lync Server 기능을 사용할 수 있습니다. 이렇게 하면 저렴 한 비용으로 Lync Server 기능을 사용할 수 있지만, 진정한 고가용성 솔루션은 제공 되지 않습니다.

Standard Edition server를 사용 하면 인스턴트 메시지 (IM), 현재 상태, 회의 및 엔터프라이즈 음성을 모두 하나의 서버에서 실행할 수 있습니다.

고가용성 솔루션의 경우 Lync Server Enterprise Edition을 사용 합니다.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>프런트 엔드 서버 및 백 엔드 서버

Lync Server Enterprise Edition에서 프런트 엔드 서버는 핵심 서버 역할을 하 고 다양 한 기본 Lync Server 함수를 실행 합니다. 프런트 엔드 서버는 백 엔드 서버와 함께 Lync Server Enterprise Edition 배포에 있어야 하는 유일한 서버 역할입니다.

*프런트 엔드 풀* 은 동일 하 게 구성 된 프런트 엔드 서버 집합으로, 공통 사용자 그룹에 대 한 서비스를 제공 하기 위해 함께 작동 합니다. 동일한 역할을 실행 하는 여러 서버의 풀은 확장성 및 장애 조치 기능을 제공 합니다.

프런트 엔드 서버에는 다음이 포함 됩니다.

  - 사용자 인증 및 등록

  - 현재 상태 정보 및 대화 상대 카드 교환

  - 주소록 서비스 및 메일 그룹 확장

  - 메신저 대화 회의를 비롯 한 IM 기능

  - 웹 회의, PSTN 전화 접속 회의 및 A/V 회의 (배포 된 경우)

  - Lync Server에 포함 된 응용 프로그램 (예: 회의 수행자 및 응답 그룹 응용 프로그램) 및 타사 응용 프로그램 호스팅

  - 선택적으로 모니터링을 통해 CDRs (호출 정보 레코드)와 Cer (통화 오류 레코드) 형식으로 사용 정보를 수집할 수 있습니다. 이 정보는 엔터프라이즈 음성 통화와 A/V 회의에 대 한 네트워크를 통과 하는 미디어 (오디오 및 비디오)의 품질에 대 한 메트릭을 제공 합니다.

  - 웹 구성 요소를 사용 하 여 web scheduler 및 join 시작 관리자와 같은 지원 되는 웹 기반 작업을 수행 합니다.

  - 필요에 따라 보관할 수 있으며, 규정 준수를 위해 IM 통신 및 모임 콘텐츠를 보관 합니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하세요.
    
    Lync Server 2010 및 이전 버전에서 모니터링 및 보관은 프런트 엔드 서버에서 collocated 아닌 별도의 서버 역할 이었습니다.

  - 선택적으로 영구 채팅을 사용 하는 경우, 파일 업로드/다운로드에 대 한 채팅방 관리 및 영구 채팅 웹 서비스에 대 한 지속적인 채팅 웹 서비스.

프런트 엔드 풀은 사용자 및 컨퍼런스 데이터에 대 한 기본 저장소 이기도 합니다. 각 사용자에 대 한 정보는 풀의 세 프런트 엔드 서버 간에 복제 되 고 백 엔드 서버에서 백업 됩니다.

또한 배포의 프런트 엔드 풀 하나는 Lync Server를 실행 하는 모든 서버에 대 한 기본 구성 데이터를 관리 하 고 배포 하는 *중앙 관리 서버*도 실행 합니다. 중앙 관리 서버는 또한 Lync Server 관리 셸 및 파일 전송 기능을 제공 합니다.

백 엔드 서버는 프런트 엔드 풀에 대 한 데이터베이스 서비스를 제공 하는 Microsoft SQL Server를 실행 하는 데이터베이스 서버입니다. 백 엔드 서버는 풀의 사용자 및 회의 데이터에 대 한 백업 저장소 역할을 하며 응답 그룹 데이터베이스와 같은 다른 데이터베이스의 주요 저장소입니다. 단일 백 엔드 서버를 사용할 수 있지만, SQL Server 미러링을 사용 하는 솔루션에는 장애 조치에 권장 됩니다. 백 엔드 서버는 Lync Server 소프트웨어를 실행 하지 않습니다.

<div>


> [!IMPORTANT]  
> 다른 데이터베이스에서 Lync Server 데이터베이스를 collocating 하지 않는 것이 좋습니다. 이렇게 하면 가용성과 성능이 영향을 받을 수 있습니다.



</div>

백 엔드 서버 데이터베이스에 저장 되는 정보에는 현재 상태 정보, 사용자의 연락처 목록, 회의 데이터 (모든 최신 컨퍼런스 상태에 대 한 영구 데이터 포함), 컨퍼런스 일정 데이터 등이 포함 됩니다.

</div>

<div>

## <a name="edge-server"></a>Edge 서버

Edge Server를 통해 사용자는 조직의 방화벽 외부의 사용자와 통신 하 고 공동 작업할 수 있습니다. 이러한 외부 사용자는 현재 오프 사이트를 사용 중인 조직의 고유한 사용자, 페더레이션 파트너 조직의 사용자, Lync Server 배포에 호스팅되는 회의에 참여 하도록 초대 받은 외부 사용자를 포함할 수 있습니다. 또한 Edge 서버는 Windows Live, AOL, Yahoo\!, Google 대화를 포함 하 여 공용 IM 연결 서비스에 대 한 연결을 가능 하 게 합니다.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜가 될 때까지 메신저를 종료 합니다. AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다. 받으려면. 이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</P></LI></UL>



</div>

Edge Server를 배포 하면 모바일 장치에서 Lync 기능을 지 원하는 이동성 서비스도 사용할 수 있습니다. 사용자는 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 인스턴트 메시지 보내기 및 받기, 연락처 보기, 현재 상태 보기 등의 작업을 수행할 수 있습니다. 또한 모바일 장치는 클릭 하 여 회의에 참가 하 고, 회사, 단일 전화 접속, 음성 메일 및 부재 중 통화를 통해 전화를 걸 수 있는 몇 가지 엔터프라이즈 음성 기능을 지원 합니다. 또한 모바일 기능은 백그라운드에서 실행 되는 응용 프로그램을 지원 하지 않는 모바일 장치에 대 한 *푸시 알림을* 지원 합니다. 푸시 알림은 모바일 응용 프로그램이 비활성 상태일 때 발생 하는 이벤트에 대 한 모바일 장치에 전송 되는 알림입니다.

또한 Edge 서버에는 프런트 엔드 서버에 XMPP 게이트웨이를 포함 하는 완전 통합 된 확장 가능 메시지 및 현재 상태 프로토콜 (XMPP) 프록시가 포함 되어 있습니다. 이 XMPP 구성 요소를 구성 하 여 Lync Server 2013 사용자가 XMPP 기반 파트너 (예: Google 대화 가능)에서 인스턴트 메시지 및 현재 상태에 대 한 연락처를 추가할 수 있습니다.

자세한 내용은 계획 설명서의 [Lync Server 2013에서 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 을 참조 하세요.

</div>

<div>

## <a name="mediation-server"></a>중재 서버

중재 서버는 엔터프라이즈 음성 및 전화 접속 회의를 구현 하는 데 필요한 구성 요소입니다. 중재 서버는 신호를 번역 하 고, 일부 구성에서는 내부 Lync Server 인프라와 PSTN (공개 교환 통신 네트워크) 게이트웨이, IP-PBX 또는 SIP (세션 시작 프로토콜) 트렁크 간의 미디어를 변환 합니다. 프런트 엔드 서버와 동일한 서버에서 중재 서버 collocated을 실행 하거나 독립 실행형 중재 서버 풀로 분리할 수 있습니다.

자세한 내용은 계획 설명서의 [Lync server 2013에서 중재 서버 구성 요소](lync-server-2013-mediation-server-component.md) 를 참조 하세요.

</div>

<div>

## <a name="director"></a>Director

디렉터는 Lync Server 사용자 요청을 인증할 수 있지만, 사용자 계정이 나 현재 상태 또는 회의 서비스는 제공 하지 않습니다. 디렉터는 외부 사용자 액세스를 가능 하 게 하는 배포의 보안을 강화 하는 데 매우 유용 합니다. 디렉터는 내부 서버에 보내기 전에 요청을 인증할 수 있습니다. 서비스 거부 공격을 하는 경우 공격이 디렉터로 종료 되 고 프런트 엔드 서버에 도달 하지 않습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하세요.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>영구 채팅 서버 역할

영구 채팅을 통해 사용자는 시간에 따라 유지 되는 단체의 주제 기반 대화에 참여할 수 있습니다. 영구 채팅 프런트 엔드 서버는 영구 채팅 서비스를 실행 합니다. 영구 채팅 백 엔드 서버에는 채팅 기록 데이터와 범주 및 채팅방에 대 한 정보가 저장 됩니다. 선택적 영구 채팅 준수 백 엔드 서버는 준수 목적에 대 한 채팅 콘텐츠 및 준수 이벤트를 저장할 수 있습니다.

Lync Server Standard Edition을 실행 하는 서버는 동일한 서버에서 영구 채팅 collocated 실행할 수도 있습니다. Enterprise Edition 프런트 엔드 서버를 사용 하는 경우 영구 채팅 프론트엔드 서버를 collocate 수 없습니다.

자세한 내용은 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 중재 서버 구성 요소](lync-server-2013-mediation-server-component.md)  


[Lync Server 2013의 보관 계획](lync-server-2013-planning-for-archiving.md)  
[Lync Server 2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013의 디렉터 시나리오](lync-server-2013-scenarios-for-the-director.md)  
[Lync Server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

