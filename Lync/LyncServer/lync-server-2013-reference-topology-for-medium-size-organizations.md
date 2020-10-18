---
title: 중간 규모 조직에 대 한 Lync Server 2013 참조 토폴로지
description: 중간 규모 조직에 대 한 Lync Server 2013 참조 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9e6ef467506865193dc26887e802198b16f42f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578614"
---
# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>중간 규모 조직의 Lync Server 2013에 대 한 참조 토폴로지

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

고가용성을 지원하고 단일 데이터 센터를 사용하는 참조 토폴로지는 하나의 중앙 사이트가 있는 중소 규모 조직용으로 설계되었습니다. 다음 다이어그램의 정확한 토폴로지는 2만 명의 사용자를 구성 하는 것입니다.

**중간 규모 조직에 대 한 참조 토폴로지**

![단일 데이터 센터 다이어그램에 대 한 참조 토폴로지](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "단일 데이터 센터 다이어그램에 대 한 참조 토폴로지")

  - **프런트 엔드 서버를 더 추가 하 여 더 많은 사용자를 수용할 수 있습니다.**     이 다이어그램의 정확한 토폴로지는 3 개의 프런트 엔드 서버를 포함 하 여 2만 사용자에 게 지원을 제공 합니다. 중앙 사이트와 사용자가 하나인 경우에는 풀에 프런트 엔드 서버를 더 추가할 수 있습니다. 풀 당 최대 사용자 수는 12 개의 프런트 엔드 서버가 있는 8만입니다.
    
    그러나 사이트에 다른 프런트 엔드 풀을 추가 하면 단일 사이트 토폴로지가 더 많은 사용자를 지원할 수 있습니다.

  - **재해 복구를 추가할 수 있습니다.**     이 조직에서 Lync Server 서비스에 대 한 고가용성은 필요한 기능 이지만 재해 복구는 그렇지 않습니다. 배포 된 프런트 엔드 서버의 풀에 고가용성이 제공 됩니다.
    
    재해 복구 기능을 추가 하려는 경우에는 다른 데이터 센터를 설정 하 고 다른 프런트 엔드 풀을 추가 하 고 현재 데이터 센터에서 프런트 엔드 풀과 연결 하는 것이 좋습니다. 그런 다음 주 풀에 영향을 주는 재해가 발생 한 경우 관리자는 사용자가 백업 풀로 장애 조치 (failover) 할 수 있습니다.

  - **백 엔드 서버가 미러링 됨**     기본 사용자 기능에 대 한 고가용성을 제공 하기 위해 조직은 각 프런트 엔드 풀에 대해 미러링된 백 엔드 서버 쌍을 배포 했습니다. 이는 Lync Server 2013의 새로운 토폴로지 옵션으로, 선택 사항입니다. 대신 단일 백 엔드 서버를 배포 하도록 선택할 수 있습니다.

  - **모니터링 서버 데이터베이스 옵션**     이 조직은 엔터프라이즈 음성 통화 및 A/V 회의의 품질을 보장 하기 위해 모니터링을 배포 했습니다. 모니터링은 모든 프런트 엔드 서버에 배포 되 고 모니터링 데이터베이스는 백 엔드 서버와 배치 된 됩니다. 또한 모니터링 데이터베이스가 별도의 서버에 있는 토폴로지를 지원 합니다.

  - 에 **지 서버 고가용성**     이 예제에서는 2만 명의 사용자를 포함 하는 조직의 경우에도 하나의에 지 서버 만으로도 충분 합니다. 그러나 고가용성을 제공 하기 위해 배포 된 두 개의에 지 서버에 대 한 풀이 있습니다.

  - **분기 사이트 배포 옵션입니다.**     이 토폴로지의 조직에는 음성 솔루션으로 배포 된 Enterprise Voice가 있습니다. 분기 사이트 1에는 중앙 사이트에 대 한 탄성 WAN (광역 네트워크) 링크가 없기 때문에 중앙 사이트에 대 한 WAN 링크가 다운 될 경우 여러 Lync Server 기능을 유지 관리 하기 위해 Sba (survivable Branch 기기를 배포 했습니다. 그러나 분기 사이트 2에는 탄력적 WAN 링크가 있으므로 공중 전화망 (PSTN) 게이트웨이만 필요 합니다. 여기에 배포 된 PSTN 게이트웨이는 미디어 바이패스를 지원 하므로 분기 사이트 2에서는 중재 서버가 필요 하지 않습니다. 분기 사이트에서 배포할 항목을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 분기 사이트 음성 복구 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 을 참조 하십시오.

  - **DNS 부하 분산**     프런트 엔드 풀 andEdge 서버 풀에는 SIP 트래픽에 대 한 DNS 부하 분산이 배포 되어 있습니다. 하드웨어 부하 분산 장치는 HTTP 트래픽에만 필요하기 때문입니다. DNS 부하 분산에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 dns 부하 분산](lync-server-2013-dns-load-balancing.md) 을 참조 하십시오.

  - **Exchange UM 배포** 이 참조 토폴로지에는 Lync Server가 아닌 Microsoft Exchange Server를 실행 하는 Exchange UM (통합 메시징) 서버가 포함 되어 있습니다.
    
    Exchange UM에 대 한 자세한 내용은 계획 설명서의 lync server 2013에서 Lync server 2013 및 [Hosted Exchange 통합 메시징 통합](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 의 [exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 을 참조 하세요.

  - **Office Web Apps 서버.** 웹 회의를 사용하는 모든 조직에서 Office Web Apps Server 또는 Office Web Apps Server 팜을 배포하는 것이 좋습니다. Office Web Apps 서버를 사용하면 웹 회의에서 Powerpoint 슬라이드를 제시할 수 있습니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

  - **에 지 서버를 권장 합니다.**     에 지 서버를 배포 하는 것은 필수는 아니지만 배포 규모에 관계 없이 배포할 것을 권장 합니다. 현재 조직의 방화벽 외부에 있는 사용자에 게 서비스를 제공 하기 위해에 지 서버를 배포 하 여 Lync Server 투자를 최대화할 수 있습니다. 이점은 다음과 같습니다.
    
      - 조직의 사용자가 Lync Server 기능을 사용할 수 있으며, 홈에서 작업 중이거나 여행 중에는 작동 하지 않습니다.
    
      - 사용자가 외부 사용자를 모임에 초대할 수 있습니다.
    
      - Lync Server도 사용 하는 파트너, 공급 업체 또는 고객 조직이 있는 경우 해당 조직과의 *페더레이션 관계* 를 설정할 수 있습니다. 그러면 Lync Server 배포에서 해당 페더레이션 조직의 사용자를 인식 하 고 보다 나은 공동 작업을 가능 하 게 됩니다.
    
      - 사용자는 Windows Live, AOL, Yahoo \! 및 Google 대화를 비롯 한 공용 IM 서비스 사용자와 인스턴트 메시지를 교환할 수 있습니다. 이러한 서비스와의 공용 IM 연결에는 별도의 라이선스가 필요할 수도 있습니다.
        
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

  - **디렉터를 추가할 수 있습니다.**     이 조직이 서비스 거부 공격에 대 한 보안을 강화 하려는 경우에는 디렉터 풀도 배포할 수 있습니다. 디렉터는 홈 사용자 계정이 아닌 Lync Server의 별도의 선택적 서버 역할 이거나, 현재 상태 또는 회의 서비스를 제공 합니다. 또한에 지 서버가 내부 서버로 향하는 인바운드 SIP 트래픽을 라우팅하는 내부 다음 홉 서버 역할을 합니다. 디렉터는 인바운드 요청을 미리 인증 하 고 사용자의 홈 풀이나 서버로 리디렉션합니다. 디렉터에서의 사전 인증을 통해 배포에 알려지지 않은 사용자 계정에서 오는 요청을 끊을 수 있습니다. 디렉터는 DoS (서비스 거부) 공격과 같은 악의적인 트래픽에 대 한 프런트 엔드 서버를 제거할 수 있도록 지원 합니다. 이러한 공격에 잘못 된 외부 트래픽이 발생 하는 네트워크의 경우에는 디렉터에서 트래픽이 종료 됩니다.

  - **System Center Operations Manager를 권장 합니다.**    최종 사용자의 서비스 가용성을 보장 하려면 Lync Server 배포의 상태를 모니터링 하는 것이 좋습니다. Microsoft에서 무료로 다운로드할 수 있는 Lync 용 System Center Operations Manager 관리 팩을 사용 하 여 Lync를 모니터링할 수 있습니다. Lync 관리 팩을 사용하면 문제가 발생할 때 실시간 알림을 받아 대처하고, 가상 트랜잭션을 실행하여 전체 Lync 기능을 테스트하고, 서비스 가용성에 대한 보고서를 받는 등 다양한 이점을 얻을 수 있습니다. 이를 통해 최종 사용자가 문제를 경험하기 전에 배포에 대한 문제를 미리 해결할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

