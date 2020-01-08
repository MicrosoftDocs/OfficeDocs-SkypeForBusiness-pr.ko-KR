---
title: 소규모 조직을 위한 Lync Server 2013 참조 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c06a3585a342ecc7fa7c41ff2b2b2682d2b8a0c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>소규모 조직의 Lync Server 2013에 대 한 참조 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-07_

소규모 조직의 참조 토폴로지에는 Lync Server를 실행 하는 서버 3 대만 배포 하 여 강력 하 고 사용 가능한 솔루션을 배포 하는 방법이 나와 있습니다.

**소규모 조직을 위한 참조 토폴로지**

![참조 토폴로지 3 대의 서버 배포 다이어그램](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "참조 토폴로지 3 대의 서버 배포 다이어그램")

  - ****    이 조직에 배포 된 Standard Edition server 쌍의 중앙 사이트에서 4000 사용자가 있습니다. 조직은 두 개의 표준 버전 서버를 배포 하 고 함께 사용 하 여 고가용성 및 재해 복구를 가능 하 게 합니다. 각 서버 홈에는 2000 사용자가 있지만, 모든 사용자에 대 한 정보는 두 서버 간에 동기화 됩니다. 그 중 하나가 발생 하는 경우 관리자는 다른 서버에서 해당 사용자에 게 서비스를 제공할 수 있으므로 사용자에 게 최소한의 장애가 있습니다. Lync Server 2013의 고가용성 및 재해 복구 기능에 대 한 자세한 내용은 [Lync server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

  - **Edge 서버 배포를 권장 합니다.**    내부 인스턴트 메시지, 현재 상태, 회의에는 Edge 서버를 배포 하는 것이 필요 하지 않지만, 소규모 배포의 경우에도이 방법을 권장 합니다. 현재 조직의 방화벽 외부에 있는 사용자에 게 서비스를 제공 하는 Edge 서버를 배포 하 여 Lync 서버 투자를 최대화할 수 있습니다. 이러한 혜택에는 다음이 포함 됩니다.
    
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

  - **지점 사이트 survivability.**    이 조직은 Lync Server의 엔터프라이즈 음성 기능 파일럿 프로그램을 실행 하 고 있습니다. 일부 사용자는 Lync Server를 유일한 음성 솔루션으로 사용 하 고 있습니다. 이러한 음성 파일럿 사용자 중 일부는 지점 사이트에 있습니다. 지점 사이트에 중앙 사이트에 대 한 안정적인 WAN (광역 네트워크) 링크가 없으므로 Survivable Branch 기기를 배포 합니다. 이 배포를 통해 WAN 링크가 다운 되는 경우 지사 사이트의 사용자가 계속 해 서 전화를 걸고 받을 수 있습니다 (둘 다 조직 및 PSTN 통화 내에서 전화를 걸고), 음성 메일 기능을 사용 하 고, 2 개의 메신저 대화 (IM)와 통신 합니다. 또한 WAN 링크를 사용할 수 없는 경우에도 사용자가 인증할 수 있습니다.

  - **Exchange UM 배포** 이 참조 토폴로지에는 Lync Server가 아닌 Microsoft Exchange Server를 실행 하는 UM (Exchange 통합 메시징) 서버가 포함 되어 있습니다.
    
    Exchange UM에 대 한 자세한 내용은 계획 설명서의 lync server 2013에서 lync Server 2013 및 [호스트 된 Exchange 통합 메시징 통합](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 의 [exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 을 참조 하세요.

  - **Office Web Apps 서버.** 웹 회의를 사용 하는 모든 조직에서 Office Web Apps 서버 또는 Office Web Apps 서버 팜을 배포 하는 것이 좋습니다. Office Web Apps Server를 통해 PowerPoint 슬라이드를 웹 회의에 표시할 수 있습니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

