---
title: 소규모 조직에 대 한 Lync Server 2013 참조 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f4c9d99e95dea0edd0b5990b0bb198dfe59dc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>소규모 조직의 Lync Server 2013에 대 한 참조 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

소규모 조직의 참조 토폴로지는 Lync Server를 실행 하는 서버 3 대만 배포 하 여 강력 하 고 가용성이 높은 솔루션을 배포 하는 방법을 보여 줍니다.

**소규모 조직에 대 한 참조 토폴로지**

![3 개의 서버를 배포 하는 참조 토폴로지 다이어그램](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "3 개의 서버를 배포 하는 참조 토폴로지 다이어그램")

  - ****    이 조직에 배포 된 Standard Edition Servers 쌍의 중앙 사이트에는 4000 명의 사용자가 있습니다. 조직은 두 개의 Standard Edition 서버를 배포 하 고이를 하나로 연결 하 여 고가용성 및 재해 복구를 사용 하도록 설정 합니다. 각 서버 홈 2000 사용자는 아니지만, 모든 사용자에 대 한 정보는 두 서버 간에 동기화 됩니다. 그 중 하나가 다운 되 면 관리자가 다른 서버에서 해당 사용자를 처리 하는 데 장애가 발생 하 여 사용자의 업무 중단을 최소화할 수 있습니다. Lync Server 2013의 고가용성 및 재해 복구 기능에 대 한 자세한 내용은 [Lync server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하십시오.

  - **에 지 서버 배포를 권장 합니다.**    내부 IM, 현재 상태 및 회의에에 지 서버를 배포 하는 것은 필요 하지 않지만 소규모 배포의 경우에도 마찬가지입니다. 현재 조직의 방화벽 외부에 있는 사용자에 게 서비스를 제공 하기 위해에 지 서버를 배포 하 여 Lync Server 투자를 최대화할 수 있습니다. 이점은 다음과 같습니다.
    
      - 조직의 사용자가 Lync Server 기능을 사용할 수 있으며, 홈에서 작업 중이거나 여행 중에는 작동 하지 않습니다.
    
      - 사용자가 외부 사용자를 모임에 초대할 수 있습니다.
    
      - Lync Server도 사용 하는 파트너, 공급 업체 또는 고객 조직이 있는 경우 해당 조직과의 *페더레이션 관계* 를 설정할 수 있습니다. 그러면 Lync Server 배포에서 해당 페더레이션 조직의 사용자를 인식 하 고 보다 나은 공동 작업을 가능 하 게 됩니다.
    
      - 사용자는 Windows Live, AOL, Yahoo\!및 Google 대화를 비롯 한 공용 IM 서비스 사용자와 인스턴트 메시지를 교환할 수 있습니다. 이러한 서비스와의 공용 IM 연결에는 별도의 라이선스가 필요할 수도 있습니다.
        
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

  - **지 속성 분기 사이트**    이 조직은 Lync Server의 Enterprise Voice 기능 파일럿 프로그램을 실행 하 고 있습니다. 일부 사용자는 Lync Server를 유일한 음성 솔루션으로 사용 하 고 있습니다. 이러한 음성 파일럿 사용자 중 일부는 분기 사이트에 있습니다. 분기 사이트에 중앙 사이트에 대 한 신뢰할 수 있는 WAN (광역 네트워크) 링크가 없기 때문에 Sba (survivable Branch 기기가 배포 됩니다. 이 배포를 통해 WAN 링크가 다운 될 경우 분기 사이트의 사용자는 계속 해 서 통화를 받고 수신할 수 있으며 (두 통화를 모두 수행 하 여 조직 및 PSTN 통화 내) 음성 메일 기능을 사용 하 고 두 명의 타사 IM (인스턴트 메시징)과 통신 합니다. 또한 WAN 링크를 사용할 수 없는 경우에도 사용자가 인증을 받을 수 있습니다.

  - **Exchange UM 배포** 이 참조 토폴로지에는 Lync Server가 아닌 Microsoft Exchange Server를 실행 하는 Exchange UM (통합 메시징) 서버가 포함 되어 있습니다.
    
    Exchange UM에 대 한 자세한 내용은 계획 설명서의 lync server 2013에서 Lync server 2013 및 [Hosted Exchange 통합 메시징 통합](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 의 [exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 을 참조 하세요.

  - **Office Web Apps 서버.** 웹 회의를 사용하는 모든 조직에서 Office Web Apps Server 또는 Office Web Apps Server 팜을 배포하는 것이 좋습니다. Office Web Apps 서버를 사용 하면 PowerPoint 슬라이드를 웹 회의에 표시할 수 있습니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

