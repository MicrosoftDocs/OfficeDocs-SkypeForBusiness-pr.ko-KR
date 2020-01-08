---
title: Lync Server 2013 초기 계획 결정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dd1359e27f6869dab1ead38da3716135a2468ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Lync Server 2013에 대한 초기 계획 결정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

계획 프로세스의 첫 번째 단계는 조직에 대해 원하는 Lync Server 작업 부하와 주요 기능을 결정 하는 것입니다.

1.  **온-프레미스 또는 온라인 배포를 선택** 하 시겠습니까?    Lync Server는 두 가지 배포 시나리오를 모두 지원 합니다. 이 결정에 대 한 자세한 내용은이 섹션의 앞에 나오는 [Lync Server 2013을 배포 하는 방법 결정](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)을 참조 하세요.

2.  **물리적 또는 가상화 된 토폴로지가 필요 한가요?**    Lync Server는 모든 작업 부하와 서버 역할을 실제 및 가상화 된 토폴로지에서 모두 지원 합니다. 사용자 용량 및 확장성은 물리적 토폴로지와 가상 토폴로지로 서로 다를 수 있습니다. 자세한 내용은 [가상 서버에서 Lync Server 2013 실행](lync-server-2013-running-lync-server-on-virtual-servers.md)을 참조 하세요.

3.  **인스턴트 메시지 *(IM)* 및 *현재 상태* 는 항상 사용할 수 있습니다.**    Lync Server 배포에서는 인스턴트 메시지 (IM) 및 현재 상태 작업 부하가 기본적으로 설치 되 고 사용 하도록 설정 됩니다. IM을 사용 하면 사용자가 실시간 텍스트 메시지와 통신할 수 있으며 현재 상태를 통해 네트워크에 있는 다른 사용자의 상태를 볼 수 있습니다. 사용자의 현재 상태는 다른 사람이 사용자에 게 문의 해야 하는지 여부를 결정 하는 데 도움이 되는 정보와 그 의미를 제공 합니다. 자세한 내용은 계획 설명서의 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 계획](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) 을 참조 하세요.

4.  **회의 모드를 배포 하 고 싶으신가요?**    회의는 Lync Server의 또 다른 핵심 기능입니다. 회의의 몇 가지 모드는 지원 됩니다. 지원 되는 모든 유형의 회의 또는 그 중 일부를 배포 하도록 선택할 수 있습니다. *웹 회의* 를 통해 사용자는 Microsoft PowerPoint 프레젠테이션 그래픽 프로그램을 사용 하 여 만든 슬라이드 데크 등의 파일을 볼 수 있습니다. 사용자는 *응용 프로그램 공유* 를 통해 데스크톱의 전체 또는 일부를 실시간으로 서로 공유할 수 있습니다. *A/V 회의*를 통해 사용자는 자신의 컨퍼런스 및 피어 투 피어 통신에 오디오 및 비디오를 추가할 수 있습니다. *전화 접속 회의* 를 통해 사용자는 표준 PSTN 전화기를 사용 하 여 조직에서 호스트 하는 회의의 오디오 부분에 참가할 수 있습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 회의 계획](lync-server-2013-planning-for-conferencing.md) 을 참조 하세요.
    
    Lync Server 2013에서 웹 회의를 배포 하는 경우 Office Web Apps 서버와 통합 하 여 모임에서 Powerpoint를 공유 하 고 볼 수 있도록 계획 해야 합니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

5.  **A/V 회의를 배포 하는 경우에는 이러한 컨퍼런스의 오디오 음질도 모니터링 해야 합니다.**    대부분의 요소는 Lync Server A/V 회의의 오디오 및 비디오 품질에 영향을 줍니다. 모니터링을 사용 하 여 통화 및 컨퍼런스의 A/V 품질을 모니터링할 수 있습니다. 미디어 품질에 영향을 주는 문제를 감지 하 고 사용자에 게 최대한의 미디어 환경을 제공 하도록 할 수 있습니다. 자세한 내용은 [Lync Server 2013의 모니터링 계획](lync-server-2013-planning-for-monitoring.md)을 참조 하세요.

6.  **메신저 대화, 현재 상태, 회의 서버에 대 한 고가용성을 원하는 경우**    사이트에 IM, 현재 상태, 회의 기능을 제공 하는 서버가 하나뿐인 경우 해당 서버가 다운 되 면 사용자의 생산성이 크게 영향을 받게 됩니다. 이러한 기능에 대 한 최소 3 대의 서버에 Enterprise Edition *풀* 을 배포 하면 서버를 사용할 수 없는 경우에도 Lync Server가 모든 기능을 그대로 유지 하면서 계속 작동할 수 있습니다.
    
    5000 명 이하의 사용자가 있는 조직에 대해 다른 옵션을 사용 하 여 Lync Server Standard Edition을 실행 하는 두 서버를 배포 하 고 이러한 서버를 함께 연결 하는 방법을 사용할 수 있습니다. 자세한 내용은 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

7.  **재해 복구 옵션을 보 시겠습니까?**    데이터 센터 두 개를 사용 하는 경우 사용자가 한 datacenter의 모든 서버 또는 모든 서버가 아래로 이동할 때 작업을 계속할 수 있는 재해 복구 옵션을 원할 경우 재해 복구를 고려 하 여 서버를 배포 하면 됩니다. 이 배포의 경우 한 데이터 센터의 서버 풀을 다른 데이터 센터의 해당 풀에 연결 합니다. 한 데이터 센터가 다운 되 면 해당 쌍의 다른 풀에서 서비스의 최소 중단으로 두 풀의 사용자에 게 서비스를 할 수 있습니다. 자세한 내용은 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

8.  **사용자가 외부 사용자와 통신 하 고 공동 작업할 수 있도록 설정** 하 시겠습니까?    외부 사용자와 통신 및 공동 작업을 사용 하도록 설정 하면 Lync Server의 투자 수익을 높일 수 있습니다. 이렇게 하면 조직의 방화벽 밖에 서 작업 하는 경우에도 조직 고유의 사용자가 Lync Server 기능을 활용할 수 있습니다. Lync Server를 실행 하는 파트너 또는 고객 조직과 페더레이션 할 수도 있습니다. 이렇게 하면 사용자와 페더레이션 파트너 사용자가 쉽게 메신저 대화 메시지를 보내고 받을 수 있으며 서로를 초대 하 여 다른 사람에 게 현재 상태를 볼 수도 있습니다. 또한 사용자는 전자 메일 메시지를 사용 하 여 외부 사용자 들이 자신이 구성한 회의에 초대할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스 계획 수립](lync-server-2013-planning-for-external-user-access.md)을 참조 하세요.

9.  **엔터프라이즈 음성을 배포 하 고 싶으신가요?**     *Enterprise Voice* 는 Lync Server에서 제공 하는 voip (VOICE over IP) 솔루션입니다. 기존 PBX 기반 전화 통신에 대 한 매력적인 대안을 제공 합니다. Enterprise Voice를 통해 사용자는 Outlook 또는 Lync Server에서 연락처를 클릭 하 여 컴퓨터 또는 VoIP 전화기에서 전화를 걸 수 있습니다. IP 네트워크를 통해 컴퓨터에서 컴퓨터, 컴퓨터에서 전화기로 또는 전화를 컴퓨터에 연결할 수 있습니다. 사용자는 모든 통신 옵션 (음성, 전자 메일, 메신저, 회의)을 컴퓨터에 통합 하 여 사용 하는 데 도움이 됩니다. 자세한 내용은 계획 설명서의 [Lync Server 2013의 Enterprise Voice 계획](lync-server-2013-planning-for-enterprise-voice.md) 을 참조 하세요.

10. **엔터프라이즈 음성을 배포 하는 경우에는 이러한 통화의 음질도 모니터링 해야 합니다.**    엔터프라이즈 음성을 배포 하는 경우 모니터링을 사용 하 여 엔터프라이즈 음성 통화의 오디오 품질을 확인 하는 것이 좋습니다. 자세한 내용은 [Lync Server 2013의 모니터링 계획](lync-server-2013-planning-for-monitoring.md)을 참조 하세요.

11. **규정 준수를 위해 IM 콘텐츠 또는 모임 콘텐츠를 보관 해야 하나요?**    조직이 준수를 위해 IM 콘텐츠 또는 모임 콘텐츠를 보관 해야 하는 경우 보관을 배포할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md)을 참조 하세요.

12. **영구 채팅을 배포** 하 시겠습니까?    사용자가 시간에 따라 유지 될 수 있는 실시간 대화를 사용 하도록 설정 하려는 경우 영구 채팅을 배포할 수 있습니다. 자세한 내용은 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)을 참조 하세요.

13. **Microsoft Exchange를 배포 했습니까?**    조직에서 전자 메일 서비스에 Microsoft exchange server를 사용 하는 경우 Lync Server와 Microsoft exchange server의 유용성을 향상 시키는 여러 기능을 사용 하도록 설정할 수 있습니다. UM (통합 메시징) 라는 이러한 기능 중 일부는 사용자가 Outlook 또는 Outlook Web Access에서 음성 메일을 청취 하 고 전화를 사용 하 여 Microsoft Exchange 사서함에 액세스 하 고 팩스를 받을 수 있도록 하는 것을 포함 합니다. Microsoft Exchange 사서함. 또한 Exchange 2013을 배포한 경우 두 시스템 간에 사용자를 위한 연락처 저장소를 통합 하 고, Exchange를 사용 하 여 고해상도 연락처 사진을 저장 하 고, 전자 메일과 인스턴트 메시지 보관을 통합할 수 있습니다. 자세한 내용은 [Lync server 2013에서 Exchange Server 통합 계획 수립](lync-server-2013-planning-for-exchange-server-integration.md)을 참조 하세요.

14. **조직에 지사가 있나요?**    조직에 지사가 있는 경우 Lync Server는 다양 한 방법으로 지원 하며 음성 및 기타 기능에 대 한 탄력성을 보장 합니다. 특히 데이터 센터에 대 한 탄성 WAN 링크가 없는 지점에서 Survivable Branch 기기 또는 Survivable Branch 서버를 설치 하 여 WAN (광역 네트워크) 링크가 작동 하지 않는 경우 엔터프라이즈 음성 지원을 유지할 수 있습니다. 자세한 내용은 [Lync Server 2013의 지점 사이트 음성 복원 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md)을 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

