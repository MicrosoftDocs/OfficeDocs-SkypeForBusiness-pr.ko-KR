---
title: Lync Server 2013 중간 규모 조직을 위한 참조 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41a003bd87e4dc8b85e78946a5ce870f3f6dd045
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>중간 규모 조직의 Lync Server 2013에 대한 참조 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-07_

고가용성 및 단일 데이터 센터의 참조 토폴로지는 중앙 사이트 하나가 있는 중소 규모의 조직에 맞게 설계 되었습니다. 다음 다이어그램의 정확한 토폴로지는 2만 사용자의 조직에 대 한 것입니다.

**중간 규모 조직의 참조 토폴로지**

(images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "단일 데이터 센터 다이어그램에 대 한") ![단일 데이터 센터 다이어그램 참조 토폴로지의 참조 토폴로지]

  - **프런트 엔드 서버를 더 추가 하 여 더 많은 사용자를 수용할 수 있습니다.**    이 다이어그램의 정확한 토폴로지에는 2만 사용자에 게 지원을 제공 하는 프런트 엔드 서버가 세 개 있습니다. 중앙 사이트 한 대와 사용자가 많을 경우 프런트 엔드 서버를 풀에 추가 하면 됩니다. 풀 당 최대 사용자 수는 12 대의 프런트 엔드 서버를 사용 하는 8만입니다.
    
    그러나 단일 사이트 토폴로지는 사이트에 다른 프런트 엔드 풀을 추가 하 여 더 많은 사용자를 지원할 수 있습니다.

  - **재해 복구를 추가할 수 있습니다.**    이 조직의 경우 Lync Server 서비스에 대 한 고가용성은 필수 기능 이지만 재해 복구는 그렇지 않습니다. 배포 된 프런트 엔드 서버의 풀이 높은 가용성을 제공 합니다.
    
    재해 복구 기능을 추가 하려는 경우 다른 데이터 센터를 설정 하 고 다른 프런트 엔드 풀을 해당 위치에 추가 하 고 현재 데이터 센터의 프런트 엔드 풀과 연결 하는 것이 좋습니다. 그런 다음 주 풀에 영향을 주는 재해가 발생 한 경우 관리자가 사용자를 백업 풀로 장애 조치할 수 있습니다.

  - **백 엔드 서버**   는 기본 사용자 기능에 대 한 높은 가용성을 제공 하기 위해 미러링 되며, 조직은 각 프런트 엔드 풀에 대 한 미러 쌍의 백 엔드 서버를 배포 했습니다. 이는 Lync Server 2013의 새로운 토폴로지 옵션이 며 선택 사항입니다. 대신 단일 백 엔드 서버를 배포 하도록 선택할 수 있습니다.

  - **모니터링 서버 데이터베이스 옵션**    이 조직은 엔터프라이즈 음성 통화와 A/V 회의의 품질을 보장 하기 위해 모니터링을 배포 했습니다. 모니터링은 모든 프런트 엔드 서버에 배포 되 고 모니터링 데이터베이스는 백 엔드 서버와 collocated 됩니다. 또한 모니터링 데이터베이스가 별도의 서버에 있는 토폴로지를 지원 합니다.

  - **Edge 서버의 높은 가용성**    2만 사용자가 있는이 조직의 경우 하나의 Edge 서버에만 성능이 충분 합니다. 그러나 고가용성을 제공 하기 위해 배포 된 두 개의 Edge 서버 풀이 있습니다.

  - **지점 사이트 배포 옵션**    이 토폴로지의 조직에는 음성 솔루션으로 배포 되는 Enterprise Voice가 있습니다. 지점 사이트 1에 중앙 사이트에 대 한 탄성 광역 네트워크 (WAN) 링크가 없으므로 중앙 사이트에 대 한 WAN 연결이 다운 되는 경우 여러 Lync Server 기능을 유지 하기 위해 배포 된 Survivable Branch 기기를 보유 하 고 있습니다. 그러나 지점 사이트 2에는 탄성 WAN 링크가 있으므로, PSTN (공개 통신 네트워크) 게이트웨이만 필요 합니다. PSTN 게이트웨이가 미디어 바이패스를 지원 하기 때문에 지점 사이트 2에서 중재 서버는 필요 하지 않습니다. 지점 사이트에서 배포할 항목을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 지점 사이트 음성 복구 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 을 참조 하세요.

  - **DNS 로드 균형 조정.**    프런트 엔드 풀 andEdge 서버 풀에는 SIP 트래픽에 대 한 DNS 부하 분산이 배포 되어 있습니다. 이렇게 하면 경계 서버에 대 한 하드웨어 부하 분산 장치가 필요 하지 않으며 하드웨어 로드 균형 조정기는 HTTP 트래픽에만 필요 하므로 다른 풀의 하드웨어 부하 분산 장치 설정 및 유지 관리를 크게 줄일 수 있습니다. DNS 부하 분산에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 dns 부하 분산](lync-server-2013-dns-load-balancing.md) 을 참조 하세요.

  - **Exchange UM 배포** 이 참조 토폴로지에는 Lync Server가 아닌 Microsoft Exchange Server를 실행 하는 UM (Exchange 통합 메시징) 서버가 포함 되어 있습니다.
    
    Exchange UM에 대 한 자세한 내용은 계획 설명서의 lync server 2013에서 lync Server 2013 및 [호스트 된 Exchange 통합 메시징 통합](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 의 [exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 을 참조 하세요.

  - **Office Web Apps 서버.** 웹 회의를 사용 하는 모든 조직에서 Office Web Apps 서버 또는 Office Web Apps 서버 팜을 배포 하는 것이 좋습니다. Office Web Apps Server를 통해 Powerpoint 슬라이드를 웹 회의에 표시할 수 있습니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

  - **Edge 서버를 권장 합니다.**    Edge 서버를 배포 하는 것이 필요 하지는 않지만 모든 배포 크기에 권장 됩니다. 현재 조직의 방화벽 외부에 있는 사용자에 게 서비스를 제공 하는 Edge 서버를 배포 하 여 Lync 서버 투자를 최대화할 수 있습니다. 이러한 혜택에는 다음이 포함 됩니다.
    
      - 조직의 자체 사용자가 집에서 작업 중이거나 여행 중일 때 Lync Server 기능을 사용할 수 있습니다.
    
      - 사용자는 외부 사용자를 초대 하 여 모임에 참가할 수 있습니다.
    
      - Lync Server도 함께 사용 하는 파트너, 공급 업체 또는 고객 조직이 있는 경우 해당 조직과 *페더레이션 관계* 를 구성할 수 있습니다. 그러면 Lync Server 배포에서 해당 페더레이션된 조직의 사용자를 인식 하 여 더 나은 공동 작업을 할 수 있습니다.
    
      - 사용자는 Windows Live, AOL, Yahoo\!, Google 대화 등의 일부 또는 전부를 포함 하 여 공용 IM 서비스 사용자와 인스턴트 메시지를 교환할 수 있습니다. 이러한 서비스를 사용 하는 공용 IM 연결에는 별도의 라이선스가 필요할 수 있습니다.
        
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

  - **감독을 추가할 수 있습니다.**    이 조직이 서비스 거부 공격에 대 한 보안을 강화 하는 데 도움이 필요한 경우 디렉터 풀을 배포할 수도 있습니다. 디렉터는 사용자 계정이 가정용이 아니거나 현재 상태 또는 회의 서비스를 제공 하는 Lync Server의 개별 선택적 서버 역할입니다. 이 서비스는 Edge 서버가 내부 서버를 대상으로 하는 인바운드 SIP 트래픽을 라우팅하는 내부 다음 홉 서버로 작동 합니다. 디렉터는 인바운드 요청을 사전 인증 하 고 사용자의 홈 풀이나 서버로 리디렉션합니다. 디렉터에서 사전 인증을 통해 배포에 알려지지 않은 사용자 계정의 요청을 삭제할 수 있습니다. 디렉터는 DoS (서비스 거부) 공격과 같은 악의적인 트래픽에 대 한 프런트 엔드 서버를 방지 하는 데 도움이 됩니다. 이러한 공격에서 유효 하지 않은 외부 트래픽으로 네트워크에 장애가 발생 하는 경우에는 해당 트래픽이 디렉터에서 끝납니다.

  - **System Center Operations Manager를 권장 합니다.**   최종 사용자에 대 한 서비스 가용성을 보장 하기 위해 Lync Server 배포의 상태를 모니터링 하는 것이 좋습니다. Microsoft에서 무료로 다운로드할 수 있는 Lync 용 System Center Operations Manager 관리 팩을 사용 하 여 Lync를 모니터링할 수 있습니다. Lync 관리 팩을 사용 하면 문제가 발생할 경우 실시간 알림을 받을 수 있으며, 종합 트랜잭션을 실행 하 여 엔드 투 엔드 Lync 기능을 테스트 하 고, 서비스 가용성을 위한 보고서를 얻을 수도 있습니다. 이렇게 하면 최종 사용자가 작업을 수행 하기 전에 배포 문제에 대 한 사전 대처를 경험할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

