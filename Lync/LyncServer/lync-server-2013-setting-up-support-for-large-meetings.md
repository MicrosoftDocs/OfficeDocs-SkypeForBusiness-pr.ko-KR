---
title: 'Lync Server 2013: 대규모 모임에 대 한 지원 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03196c705253320e31e2483cc89b2aca386ff1af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Lync Server 2013에서 대규모 모임에 대 한 지원 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-12_

최대 1000 명의 사용자에 대 한 대규모 모임을 지원 하려면 적절 한 토폴로지, 모임 하드웨어 및 소프트웨어 필수 구성 요소를 만들고 적절 하 게 환경을 구성 해야 합니다.

<div>

## <a name="topology-requirements"></a>토폴로지 요구 사항

단일 대규모 모임에는 하나 이상의 프런트 엔드 서버와 1 백 엔드 서버가 필요 합니다. 그러나 고가용성을 제공 하려면 미러 백 엔드 서버가 있는 2 개의 프런트 엔드 서버 풀을 사용 하는 것이 좋습니다.

대규모 모임을 호스트 하는 사용자는이 풀에 속한 사용자 계정이 있어야 합니다. 그러나이 풀에는 다른 사용자 계정을 호스트 하지 않는 것이 좋습니다. 그 대신 대규모 모임에만 사용 합니다. 이 풀에는 대규모 모임을 호스트 하는 데만 사용 될 특수 사용자 계정을 만드는 것이 가장 좋습니다. 대규모 모임 설정은 성능에 최적화 되어 있으므로 일반 사용자로 사용 하면 PSTN 끝점을 사용할 때 P2P 세션을 모임으로 승격할 수 없는 등의 문제가 발생할 수도 있습니다.

정확히 두 개의 프런트 엔드 서버를 사용 하 여 풀을 관리 하려면 몇 가지 특별 고려 사항이 필요 합니다. 자세한 내용은 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)를 참조 하세요.

또한 대규모 모임에 사용 되는 풀에 대해 필요에 따라 재해 복구 백업 및 장애 조치를 제공 하려는 경우에는 다른 데이터 센터에 비슷한 설정 전용 풀을 사용 하 여 연결할 수 있습니다. 자세한 내용은 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

![대규모 모임 풀 구성](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "대규모 모임 풀 구성")

토폴로지에 대 한 추가 정보는 다음과 같습니다.

  - 파일 공유는 모임 콘텐츠를 저장 하는 데 필요 하며 보관 서버를 배포 하 여 사용 하는 경우 보관 파일을 저장 하기 위한 것입니다. 파일 공유는 풀 전용 이거나 풀이 배포 된 사이트의 다른 풀에서 사용 하는 것과 동일한 파일 공유 일 수 있습니다. 파일 공유를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 파일 저장소 구성을](lync-server-2013-configure-dfs-file-storage.md)참조 하세요.

  - Office Web Apps 서버는 대규모 모임에서 PowerPoint 프레젠테이션 기능을 사용 하도록 설정 하는 데 필요 합니다. Office Web Apps 서버는 대규모 모임 풀 전용 이거나 전용 풀이 배포 된 사이트의 다른 풀에서 사용 하는 동일한 Office Web Apps 서버 일 수 있습니다.

  - 프런트 엔드 서버의 부하 분산에는 HTTP 트래픽에 대 한 하드웨어 로드 밸런싱 (예: 모임 콘텐츠 다운로드)이 필요 합니다. DNS 부하 분산은 SIP 트래픽에 적합 합니다. 자세한 내용은 [Lync Server 2013에 대 한 부하 분산 요구 사항을](lync-server-2013-load-balancing-requirements.md)참조 하세요.

  - 전용 대용량 모임 풀에 모니터링 서버를 사용 하려는 경우에는 Lync Server 배포의 모든 프런트 엔드 서버 풀에서 공유 되는 모니터링 서버와 해당 데이터베이스를 사용 하는 것이 좋습니다.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>하드웨어 및 소프트웨어 요구 사항

전용 대용량 모임 풀의 서버에 대 한 하드웨어 요구 사항은 다른 Lync Server 2013 서버와 동일 합니다. 하드웨어 요구 사항에 대 한 자세한 내용은 "[Lync server 용 서버 하드웨어 플랫폼 2013](lync-server-2013-server-hardware-platforms.md)을 참조 하세요.

전용 대용량 모임 풀의 서버는 모든 Lync Server 2013 소프트웨어 요구 사항을 충족 해야 합니다. 소프트웨어 요구 사항에 대 한 자세한 내용은 다음 문서를 참조 하세요.

  - [Lync Server 2013의 서버 및 도구 운영 체제 지원](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013의 데이터베이스 소프트웨어 지원](lync-server-2013-database-software-support.md)

  - [Lync Server 2013에 대한 추가 소프트웨어 요구 사항](lync-server-2013-additional-software-requirements.md)

또한 Lync Server 2013와 모든 Lync Server 2013 클라이언트에는 최신 업데이트가 설치 되어 있어야 합니다.

</div>

<div>

## <a name="configuration-requirements"></a>구성 요구 사항

대규모 모임에 대 한 새로운 회의 정책을 만든 다음 전용 대용량 모임 풀에 속한 사용자에 게 회의 정책을 할당 하는 것이 좋습니다. 다음 설정을 사용 하 여 회의 정책을 구성 합니다.

  - **MaxMeetingSize** 옵션을 **1000**로 설정 합니다. (기본값은 **250**입니다.)

  - **AllowLargeMeetings** 옵션을 **True**로 설정 합니다.

  - **Enableappdesktopsharing** 옵션을 **없음**으로 설정 합니다.

  - **AllowUserToScheduleMeetingsWithAppSharing** 옵션을 **False**로 설정 합니다.

  - **Allowsharednotes** 옵션을 **False**로 설정 합니다.

  - **Allowannotations** 옵션을 **False**로 설정 합니다.

  - **DisablePowerPointAnnotations** 옵션을 **True**로 설정 합니다.

  - **AllowMultiview** 옵션을 **False**로 설정 합니다.

  - **EnableMultiviewJoin** 옵션을 **False**로 설정 합니다.

<div>


> [!NOTE]  
> Lync Server 2013의 1000 사용자 대규모 모임에 대 한 지원에는 모임 스케줄러에 대 한 회의 정책의 <STRONG>AllowLargeMeetings</STRONG> 설정이 true로 설정 되어 있어야 합니다. 이 설정을 true로 설정 하면 사용자가 모임에 참가할 때 추가 대규모 모임에 대해 Lync 환경이 최적화 됩니다. 특히 대규모 모임에서 Lync는 전체 모임 참가자 목록의 초기 또는 업데이트를 표시 하지 않으며,이는 클라이언트와 Lync 서버 2013 모두에 대 한 성능 병목 상태입니다. 대신 Lync에는 사용자 및 모임의 발표자 목록에 대 한 정보만 표시 됩니다. Lync는 대규모 모임에서 사용할 수 있는 참가자의 총 수를 계속 올바르게 표시 합니다.



</div>

**최대 모임 크기** 설정을 제외한, 대규모 모임에서 필요 하지 않은 회의 기능을 사용 하지 않도록 설정 하려면 여기에 지정 된 다른 모든 회의 정책 설정이 필요 합니다.

또한 풀에 있고 모임 일정 관리를 담당 하는 각 Lync Server 2013 사용자에 게 적절 한 사용 권한이 있도록 전용 대용량 모임 풀을 구성 해야 합니다. 이 작업을 수행 하려면 다음을 실행 합니다.

  - **발표자로 지정** 옵션을 **없음**으로 설정 합니다. 일반적으로 대규모 모임의 모든 참가자에 대 한 한 명 이상의 사용자가 발표자 인 경우에는 참가자가 발표자로 서 대규모 모임에 자동으로 참여 하지 않아야 합니다. 대신 발표자는 모임 예약 시간에 명시적으로 지정 되거나 대규모 모임 중에 명시적으로 승격 되어야 합니다.

  - **지정 된 컨퍼런스 회의 종류가 기본적으로** 선택 되어 있는지 확인 합니다. 이 설정은 모임의 온라인 모임 추가 2013 기능이 이끌이의 지정 된 회의를 사용 하 여 언제 든 지 회의를 예약할 지 여부를 제어 하며,이는 예약 된 모임에 동일한 참가 URL 및 오디오 정보가 있음을 의미 합니다. 소규모 그룹 공동 작업 시나리오에서는 모든 사용자에 게 고유한 회의가 있고, 상수 조인 URL 및 오디오 정보로 인해 모임 참가에 더 빠르게 참가할 수 있으므로 이러한 지정 된 회의 종류가 제대로 작동 합니다. 그러나 대규모 모임 시나리오에서는 대규모 모임 지원 직원이 단일 사용자 자격 증명 집합을 사용 하 여 대규모 모임을 예약 하 고 모임 요청자에 게 참가 Url 및 오디오 정보를 제공 합니다. 이 경우에는 다른 URL을 사용 하 여 각 모임에 참가 하는 것이 좋습니다.

  - 필요 하지 않은 경우 **익명 사용자의 기본값으로** 허용 확인란이 선택 되어 있지 않은지 확인 합니다. 이 설정은 지정 된 회의를 사용 하지 않을 때 Lync 2013의 온라인 모임 추가 기능에서 예약한 기본 모임 액세스 형식에 영향을 줍니다. 이 설정에 적합 한 옵션은 조직의 요구 사항에 따라 달라 집니다. 조직에 대 한 대부분의 대규모 모임이 내부 모임이 면이 옵션을 선택 하지 마세요. 대부분의 대규모 모임에서 외부 사용자가 참가할 수 있어야 하는 경우이 옵션을 선택 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

