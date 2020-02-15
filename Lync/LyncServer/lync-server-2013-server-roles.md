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
ms.openlocfilehash: 093161cec5a13ac12840776dec731773782966c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Lync Server 2013의 서버 역할

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

Lync Server를 실행 하는 각 서버는 하나 이상의 *서버 역할*을 실행 합니다. 서버 역할은 해당 서버가 제공 하는, 정의 된 Lync Server 기능 집합입니다. 네트워크에서 사용 가능한 모든 서버 역할을 배포할 필요는 없습니다. 필요한 기능이 포함된 서버 역할만 설치하면 됩니다.

Lync Server의 서버 역할에 대해 잘 모르는 경우에도 계획 도구를 사용 하 여 원하는 기능에 따라 배포 해야 하는 서버에 가장 적합 한 솔루션을 안내할 수 있습니다. 이 섹션에서는 서버 역할 및 서버 역할에서 제공하는 일반적인 기능에 대해 간략하게 살펴봅니다.

  - Standard Edition 서버

  - 프런트 엔드 서버 및 백 엔드 서버

  - 에지 서버

  - 중재 서버

  - 영화

  - 영구 채팅 프런트 엔드 서버

  - 영구 채팅 저장소(영구 채팅 백 엔드 서버)

  - 영구 채팅 준수 저장소(영구 채팅 준수 백 엔드 서버)

대부분의 서버 역할은 확장성 및 고가용성을 위해 모두 같은 서버 역할을 실행하는 여러 서버 *풀*을 배포할 수 있습니다. 풀의 각 서버는 동일한 서버 역할을 실행해야 합니다. Lync Server에서는 대부분의 풀 유형에 대해 부하 분산 장치를 배포 하 여 풀의 여러 서버 간에 트래픽을 분산 해야 합니다. Lync Server는 DNS (Domain Name System) 부하 분산 및 하드웨어 부하 분산 장치를 모두 지원 합니다.

<div>

## <a name="standard-edition-server"></a>Standard Edition 서버

Standard Edition 서버는 대규모 조직의 파일럿 프로젝트 또는 소규모 조직용으로 설계되었습니다. 이를 통해 단일 서버에서 실행 되는 필수 데이터베이스를 비롯 한 여러 Lync Server 기능을 사용할 수 있습니다. 이를 통해 저렴 한 비용으로 Lync Server 기능을 사용할 수 있지만, 진정한 고가용성 솔루션은 제공 되지 않습니다.

Standard Edition server에서는 IM (인스턴트 메시징), 현재 상태, 회의 및 Enterprise Voice를 한 서버에서 모두 실행 하는 기능을 사용할 수 있습니다.

고가용성 솔루션의 경우 Lync Server Enterprise Edition을 사용 합니다.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>프런트 엔드 서버 및 백 엔드 서버

Lync Server Enterprise Edition에서 프런트 엔드 서버는 핵심 서버 역할이 며 다양 한 기본 Lync Server 기능을 실행 합니다. 프런트 엔드 서버와 백 엔드 서버를 함께 사용 하는 것이 Lync Server Enterprise Edition 배포에 필요한 유일한 서버 역할입니다.

*프런트 엔드 풀*은 동일하게 구성된 프런트 엔드 서버 집합으로서, 이러한 서버가 함께 일반 사용자 그룹에 대한 서비스를 제공합니다. 동일 역할을 실행하는 여러 서버로 구성된 풀은 확장성 및 장애 조치(Failover) 기능을 제공합니다.

프런트 엔드 서버에는 다음과 같은 항목이 포함됩니다.

  - 사용자 인증 및 등록

  - 현재 상태 정보 및 대화 상대 카드 교환

  - 주소록 서비스 및 메일 그룹 확장

  - IM 기능(단체 IM 전화 회의 포함)

  - 웹 회의, PSTN 전화 접속 회의 및 A/V 회의(배포된 경우)

  - Lync Server에 포함 된 응용 프로그램 (예: 회의 전화 교환 및 응답 그룹 응용 프로그램) 및 타사 응용 프로그램에 대 한 응용 프로그램 호스팅

  - CDR(통화 정보 기록) 및 CER(통화 오류 기록)의 형식으로 사용 정보를 수집하는 모니터링(선택 사항). 이 정보는 엔터프라이즈 음성 통화 및 A/V 회의에 대해 네트워크를 통과 하는 미디어 (오디오 및 비디오)의 품질에 대 한 메트릭을 제공 합니다.

  - 웹 스케줄러 및 참가 시작 관리자와 같은 지원되는 웹 기반 작업에 대한 웹 구성 요소

  - 준수 목적의 IM 통신 및 모임 콘텐츠에 대한 보관(선택 사항). 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하십시오.
    
    Lync Server 2010 및 이전 버전에서 모니터링 및 보관은 프런트 엔드 서버에서 배치 된가 아니라 별도의 서버 역할 이었습니다.

  - 영구 채팅이 사용하도록 설정된 경우 채팅방 관리를 위한 영구 채팅 웹 서비스 및 파일 업로드/다운로드를 위한 영구 채팅 웹 서비스(선택 사항)

프런트 엔드 풀은 사용자 및 회의 데이터의 기본 저장소로도 사용됩니다. 각 사용자에 대한 정보는 풀에 있는 3개의 프런트 엔드 서버 간에 복제되고 백 엔드 서버에서 백업됩니다.

또한 배포의 프런트 엔드 풀 하나는 기본 구성 데이터를 관리 하 고 Lync Server를 실행 하는 모든 서버에 배포 하는 *중앙 관리 서버*도 실행 합니다. 중앙 관리 서버 에서도 Lync Server 관리 셸 및 파일 전송 기능을 제공 합니다.

백 엔드 서버는 프런트 엔드 풀에 대 한 데이터베이스 서비스를 제공 하는 Microsoft SQL Server를 실행 하는 데이터베이스 서버입니다. 백 엔드 서버는 풀의 사용자 및 회의 데이터에 대한 백업 저장소로 사용되며, 응답 그룹 데이터베이스와 같은 다른 데이터베이스의 기본 저장소로도 사용됩니다. 하나의 백 엔드 서버를 사용할 수 있지만 장애 조치 (failover)를 위해 SQL Server 미러링을 사용 하는 솔루션은 권장 됩니다. 백 엔드 서버는 Lync Server 소프트웨어를 실행 하지 않습니다.

<div>


> [!IMPORTANT]  
> Lync Server 데이터베이스를 다른 데이터베이스와 배치 않는 것이 좋습니다. 그렇지 않으면 가용성 및 성능에 영향을 줄 수 있습니다.



</div>

백 엔드 서버 데이터베이스에 저장되는 정보에는 현재 상태 정보, 사용자의 대화 상대 목록, 모든 현재 전화 회의의 상태에 대한 영구 데이터를 비롯한 회의 데이터 및 전화 회의 일정 데이터가 포함됩니다.

</div>

<div>

## <a name="edge-server"></a>에지 서버

에 지 서버를 사용 하면 조직의 방화벽 외부에서 사용자와 정보를 교환 하 고 공동으로 작업할 수 있습니다. 이러한 외부 사용자는 현재 오프 사이트를 사용 하 고 있는 조직 사용자, 페더레이션 파트너 조직의 사용자, Lync Server 배포에서 호스트 되는 회의에 참가 하도록 초대 된 외부 사용자 등을 포함할 수 있습니다. 또한에 지 서버는 Windows Live, AOL, Yahoo\!및 Google 대화를 비롯 한 공용 IM 연결 서비스에 대 한 연결을 사용 하도록 설정 합니다.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>



</div>

에지 서버를 배포하면 모바일 장치에서 Lync 기능을 지원하는 모바일 서비스도 사용하도록 설정됩니다. 사용자는 지원된느 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용해서 인스턴트 메시지 전송 및 수신, 연락처 보기 및 현재 상태 보기와 같은 활동을 수행할 수 있습니다. 또한 모바일 장치에서는 클릭하여 회의 참가, 회사번호로 전화, 단일 번호 연결, 음성 메일, 부재 중 통화 등의 일부 Enterprise Voice 기능도 지원됩니다. 모바일 기능에는 또한 백그라운드에서 실행 중인 응용 프로그램을 지원하지 않는 모바일 장치를 위한 *푸시 알림*도 지원됩니다. 푸시 알림은 해당 모바일 응용 프로그램이 비활성 상태일 때 발생한 이벤트에 대해 모바일 장치에 전송되는 알림입니다.

에지 서버에는 또한 프런트 엔드 서버에 포함된 XMPP 게이트웨이를 포함하는 완전히 통합된 XMPP(Extensible Messaging and Presence Protocol) 프록시가 포함됩니다. 이러한 XMPP 구성 요소를 구성 하 여 Lync Server 2013 사용자가 XMPP 기반 파트너 (예: Google 대화)에서 인스턴트 메시징 및 현재 상태에 대 한 연락처를 추가할 수 있습니다.

자세한 내용은 계획 설명서에서 [Lync Server 2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 을 참조 하십시오.

</div>

<div>

## <a name="mediation-server"></a>중재 서버

중재 서버는 Enterprise Voice 및 전화 접속 회의를 구현 하는 데 필요한 필수 구성 요소입니다. 중재 서버는 신호를 번역 하며, 일부 구성에서는 내부 Lync Server 인프라와 PSTN (공중 전화망) 게이트웨이, IP-PBX 또는 SIP (Session 착수 프로토콜) 트렁크 간의 미디어를 변환 합니다. 중재 서버는 프런트 엔드 서버와 동일한 서버에 함께 배치하여 실행하거나 독립 실행형 중재 서버 풀에 별도로 배치한 상태로 실행할 수 있습니다.

자세한 내용은 계획 설명서의 [Lync server 2013에서 중재 서버 구성 요소](lync-server-2013-mediation-server-component.md) 를 참조 하십시오.

</div>

<div>

## <a name="director"></a>영화

디렉터는 Lync Server 사용자 요청을 인증할 수 있지만, 사용자 계정이 나 현재 상태 또는 회의 서비스는 제공 하지 않습니다. 디렉터는 외부 사용자 액세스를 지원하는 배포에서 보안을 효과적으로 향상시켜줍니다. 디렉터는 요청을 내부 서버로 전송하기 전에 요청에 대한 인증을 수행할 수 있습니다. 서비스 거부 공격이 있더라도 공격이 디렉터에서 끝나고 프런트 엔드 서버에 도달하지 못합니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하십시오.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>영구 채팅 서버 역할

영구 채팅을 통해 사용자는 장기간 지속되는 주제 기반의 단체 대화에 참가할 수 있습니다. 영구 채팅 프런트 엔드 서버는 영구 채팅 서비스를 실행합니다. 영구 채팅 백 엔드 서버는 채팅 기록 데이터와 범주 및 채팅방에 대한 정보를 저장합니다. 영구 채팅 준수 백 엔드 서버(선택 사항)는 준수 목적으로 채팅 콘텐츠 및 준수 이벤트를 저장할 수 있습니다.

Lync Server Standard Edition을 실행 하는 서버 에서도 동일한 서버에서 영구 채팅 배치 된 실행할 수 있습니다. 영구 채팅 프런트 엔드 서버를 Enterprise Edition 프런트 엔드 서버에 함께 배치할 수는 없습니다.

자세한 내용은 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 중재 서버 구성 요소](lync-server-2013-mediation-server-component.md)  


[Lync Server 2013의 보관 계획](lync-server-2013-planning-for-archiving.md)  
[Lync Server 2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013의 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md)  
[Lync Server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

