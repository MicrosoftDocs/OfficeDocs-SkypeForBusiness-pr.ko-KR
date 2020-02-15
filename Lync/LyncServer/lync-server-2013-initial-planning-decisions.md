---
title: Lync Server 2013 초기 계획 결정 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec4d9d90c56f44b14c19d7f4cc387f4e0aaf58f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Lync Server 2013에 대 한 초기 계획 결정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

계획 프로세스의 첫 부분은 조직에 사용할 Lync Server 작업 및 주요 기능을 결정 하는 것입니다.

1.  **온-프레미스 또는 온라인 배포를 원하십니까?**    Lync Server에서는 두 가지 배포 시나리오를 모두 지원 합니다. 이 결정을 내리는 방법에 대 한 자세한 내용은이 섹션 앞부분에 나오는 [Lync Server 2013를 배포 하는 방법 결정](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)을 참조 하십시오.

2.  **물리적 또는 가상화 된 토폴로지를 원하십니까?**    Lync Server는 실제 및 가상화 된 토폴로지에서 모두에 대해 모든 작업 및 서버 역할을 지원 합니다. 사용자 용량 및 확장성은 실제 토폴로지와 가상화 토폴로지 간에 차이가 납니다. 자세한 내용은 [virtual servers에서 Lync Server 2013 실행](lync-server-2013-running-lync-server-on-virtual-servers.md)을 참조 하십시오.

3.  ***IM (* 인스턴트 메시징) 및 *현재 상태* 는 항상 사용 하도록 설정 되어 있습니다.**    Lync Server 배포에서는 IM (인스턴트 메시징) 및 현재 상태 작업 부하가 기본적으로 설치 및 사용 하도록 설정 되어 있습니다. 메신저는 사용자들이 실시간 텍스트 메시지를 사용하여 커뮤니케이션하는 데 사용되며, 현재 상태는 네트워크에 있는 다른 사용자들의 상태를 보는 데 사용됩니다. 사용자의 현재 상태는 다른 사람들이 사용자에게 연락할지 여부와 연락 방법을 결정하는 데 도움이 되는 정보를 제공합니다. 자세한 내용은 계획 설명서에서 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 계획](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) 을 참조 하십시오.

4.  **회의 모드를 배포** 하 시겠습니까?    회의는 Lync Server의 또 다른 주요 기능입니다. 몇 가지 회의 모드가 지원됩니다. 지원되는 모든 회의 유형을 배포하거나 일부만 배포하도록 선택할 수 있습니다. *웹 회의*는 사용자가 Microsoft PowerPoint 프레젠테이션 그래픽 프로그램으로 만든 슬라이드 카드와 같이 프레젠테이션할 파일을 보는 데 사용됩니다. *응용 프로그램 공유*는 사용자들이 실시간으로 서로 데스크톱의 일부 또는 전부를 공유하는 데 사용됩니다. 사용자들은 *A/V 회의*를 사용하여 회의 및 피어 투 피어 통신에 오디오(및 비디오)를 추가할 수 있습니다. *전화 접속 회의*는 사용자가 표준 PSTN 전화를 사용하여 조직에서 호스팅되는 회의의 오디오 부분에 참가하는 데 사용됩니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 회의 계획](lync-server-2013-planning-for-conferencing.md) 을 참조 하십시오.
    
    Lync Server 2013에서 웹 회의를 배포 하는 경우 Office Web Apps 서버와의 통합도 계획 하 여 회의에서 Powerpoint 공유 및 보기를 사용 하도록 설정 해야 합니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

5.  **A/V 회의를 배포 하는 경우에는 이러한 전화 회의의 오디오 품질도 모니터링 해야 합니다.**    대부분의 요인은 Lync Server A/V 회의의 오디오 및 비디오 품질에 영향을 줍니다. 모니터링을 사용 하 여 통화 및 전화 회의의 A/V 품질을 모니터링할 수 있습니다. 미디어 품질에 영향을 주는 문제를 감지 하 고 사용자가 최상의 미디어 환경을 사용할 수 있도록 합니다. 자세한 내용은 [Lync Server 2013의 모니터링 계획](lync-server-2013-planning-for-monitoring.md)을 참조 하십시오.

6.  **IM, 현재 상태 및 회의 서버에 대 한 고가용성을 원하십니까?**    IM, 현재 상태 및 회의 기능을 제공 하는 사이트에 서버가 하나만 있는 경우 해당 서버가 다운 되 면 사용자의 생산성도 크게 영향을 받게 됩니다. 이러한 기능을 위해 3 대 이상의 서버에 Enterprise Edition *풀* 을 배포 하면 서버를 사용할 수 없는 경우에도 Lync Server에서 이러한 모든 기능을 그대로 유지 하면서 계속 작업할 수 있습니다.
    
    또한 고가용성을 원하는 사용자가 5000 이상인 조직에서는 Lync Server Standard Edition을 실행 하는 두 서버를 배포 하 고 이러한 서버를 함께 연결 하는 것이 좋습니다. 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

7.  **재해 복구 옵션을 원하십니까?**    두 데이터 센터가 있는 경우 한 데이터 센터의 모든 서버 또는 다 수의 서버가 다운 될 경우 사용자가 계속 작업할 수 있도록 재해 복구 옵션을 사용 하려면 재해 복구를 염두에 두고 서버를 배포 하면 됩니다. 이러한 배포에서는 한 데이터 센터의 서버 풀을 다른 데이터 센터의 상대 풀과 쌍으로 연결할 수 있습니다. 한 데이터 센터의 가동이 중단되는 경우 쌍으로 연결된 다른 풀이 최소한의 서비스 중단만으로 두 풀의 사용자 모두에게 서비스를 제공할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

8.  **사용자가 외부 사용자와 통신 하 고 공동으로 작업할 수 있도록 설정 하 고 싶으십니까?**    외부 사용자와의 통신 및 공동 작업을 사용 하도록 설정 하면 Lync Server에 대 한 투자 수익률을 높일 수 있습니다. 이렇게 하면 조직의 방화벽 외부에서 작업 하는 경우에도 조직 자체 사용자가 Lync Server 기능을 활용할 수 있습니다. Lync Server를 실행 하는 파트너 또는 고객 조직과 페더레이션 할 수도 있습니다. 이렇게 하면 사용자 및 페더레이션된 파트너 사용자가 쉽게 메신저 메시지를 주고받고, 서로 모임에 초대하고, 상대방의 현재 상태를 볼 수 있습니다. 또한 사용자는 전자 메일 메시지를 사용하여 자신이 이끄는 회의에 특정 외부 사용자를 초대할 수 있습니다. 자세한 내용은 [Lync Server 2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md)을 참조 하십시오.

9.  **Enterprise Voice를 배포** 하 시겠습니까?     *Enterprise Voice* 는 Lync Server에서 제공 하는 VoIP (VOICE over IP) 솔루션입니다. 기존의 PBX 기반 전화 통신에 대한 매력적인 대안을 제공합니다. Enterprise Voice를 사용 하면 사용자가 Outlook 또는 Lync Server의 대화 상대를 클릭 하 여 컴퓨터 또는 VoIP 전화에서 전화를 걸 수 있습니다. IP 네트워크를 통해 컴퓨터 간, 컴퓨터에서 전화로 또는 전화에서 컴퓨터로 통화를 할 수 있습니다. 사용자가 자신의 컴퓨터에서 통합하고 사용할 수 있는 모든 통신 옵션(음성, 전자 메일, 메신저 및 회의)을 모두 활용할 수 있습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 Enterprise Voice 계획](lync-server-2013-planning-for-enterprise-voice.md) 을 참조 하십시오.

10. **Enterprise Voice를 배포 하는 경우 이러한 통화의 오디오 품질도 모니터링 해야 합니다.**    Enterprise voice를 배포 하는 경우 모니터링을 사용 하 여 enterprise voice 통화의 오디오 품질을 확인 하는 것이 좋습니다. 자세한 내용은 [Lync Server 2013의 모니터링 계획](lync-server-2013-planning-for-monitoring.md)을 참조 하십시오.

11. **규정 준수를 위해 IM 콘텐츠 또는 모임 콘텐츠를 보관 해야 하나요?**    조직에서 규정 준수를 위해 IM 콘텐츠 또는 모임 콘텐츠를 보관 해야 하는 경우에는 보관을 배포할 수 있습니다. 자세한 내용은 [Lync Server 2013의 보관 계획](lync-server-2013-planning-for-archiving.md)을 참조 하세요.

12. **영구 채팅을 배포** 하 시겠습니까?    시간에 따라 지속 될 수 있는 실시간 대화를 사용자에 게 사용 하도록 설정 하려는 경우 영구 채팅을 배포할 수 있습니다. 자세한 내용은 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)을 참조 하십시오.

13. **Microsoft Exchange를 배포 했습니까?**    조직에서 전자 메일 서비스에 Microsoft Exchange server를 사용 하는 경우 Lync Server와 Microsoft Exchange server의 유용성을 향상 시키는 다양 한 기능을 사용 하도록 설정할 수 있습니다. Exchange UM (통합 메시징) 이라고 하는 이러한 기능 중 일부는 사용자가 음성 메일 알림을 받고 Outlook 또는 Outlook Web Access에서 음성 메일을 듣고 전화를 사용 하 여 Microsoft Exchange 사서함에 액세스 하 고 팩스를 받을 수 있도록 하는 것을 포함 합니다. Microsoft Exchange 사서함 또한 Exchange 2013이 배포 된 경우 두 시스템 간에 사용자에 대 한 연락처 저장소를 통합 하 고 Exchange를 사용 하 여 고해상도 연락처 사진을 저장 하 고 전자 메일 및 인스턴트 메시지의 보관 기능을 통합할 수 있습니다. 자세한 내용은 [Lync server 2013과의 Exchange Server 통합 계획](lync-server-2013-planning-for-exchange-server-integration.md)을 참조 하세요.

14. **조직에 지사가 있습니까?**    조직에 지사가 있는 경우 Lync Server에서 지원 되는 다양 한 방법을 지원 하 고 음성 및 기타 기능에 대 한 복원성을 보장 합니다. 특히 데이터 센터에 대 한 복구 가능한 WAN 링크가 없는 지점에서는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버를 설치 하 여 WAN (광역 네트워크) 링크가 작동 하지 않는 경우 Enterprise Voice 지원을 유지할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 분기 사이트 음성 복구 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md)을 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

