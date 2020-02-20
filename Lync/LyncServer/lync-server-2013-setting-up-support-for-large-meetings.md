---
title: 'Lync Server 2013: 대규모 모임에 대 한 지원 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 589bb15213e6ec895121d81e60852d183801cee9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Lync Server 2013에서 대규모 모임에 대 한 지원 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-12_

사용자 수 최대 1000명의 대규모 모임을 지원하기 위해서는 적절한 토폴로지, 모임 하드웨어 및 소프트웨어 필수 구성 요소를 만들고 환경을 적절하게 구성해야 합니다.

<div>

## <a name="topology-requirements"></a>토폴로지 요구 사항

단일 대규모 모임에는 하나 이상의 프런트 엔드 서버와 1 개의 백 엔드 서버가 필요 합니다. 그러나 고가용성을 제공 하려면 미러링된 백 엔드 서버를 사용 하는 프런트 엔드 서버가 두 개 있는 것이 좋습니다.

대규모 모임을 호스팅하는 사용자는 해당 사용자 계정이 이 풀에 있어야 합니다. 하지만 이 풀에서 다른 사용자 계정은 호스팅하지 않는 것이 좋습니다. 대신 대규모 모임에 대해서만 사용하십시오. 최선의 방법은 대규모 모임을 호스팅하는 데에만 사용되도록 이 풀에 특별한 사용자 계정을 만드는 것입니다. 대규모 모임 설정은 성능에 최적화 되므로 일반 사용자로 사용 하는 경우 PSTN 끝점이 포함 된 경우 P2P 세션을 모임에 승격 하지 못하는 등의 문제가 발생할 수 있습니다.

정확히 두 개의 프런트 엔드 서버를 포함하는 풀을 관리하기 위해서는 특별한 고려 사항이 필요합니다. 자세한 내용은 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)를 참조 하세요.

또한 대규모 모임에 사용 되는 풀에 대 한 재해 복구 백업 및 장애 조치 (failover)를 선택적으로 제공 하려는 경우에는 다른 데이터 센터에 비슷한 설정 전용 풀을 사용 하 여 연결할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하십시오.

![대규모 모임 풀 구성](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "대규모 모임 풀 구성")

토폴로지에 대한 추가 정보에는 다음이 포함됩니다.

  - 파일 공유는 보관 파일을 저장 하기 위해 모임 콘텐츠를 저장 하 고 보관 서버를 배포 하 고 사용 하는 경우에 필요 합니다. 파일 공유는 풀 전용이거나 풀이 배포된 사이트에서 다른 풀에 사용되는 것과 동일한 파일 공유일 수 있습니다. 파일 공유를 구성 하는 방법에 대 한 자세한 내용은 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)을 참조 하십시오.

  - Office Web Apps 서버는 대규모 모임에서 PowerPoint 프레젠테이션 기능을 사용 하도록 설정 하는 데 필요 합니다. Office Web Apps 서버는 대규모 모임 풀 전용 이거나 전용 풀이 배포 되는 사이트의 다른 풀에서 사용 하는 것과 동일한 Office Web Apps 서버 일 수 있습니다.

  - 프런트 엔드 서버의 부하 분산에는 HTTP 트래픽 (예: 모임 콘텐츠 다운로드)에 대 한 하드웨어 부하 분산이 필요 합니다. SIP 트래픽에는 DNS 부하 분산이 권장됩니다. 자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항을](lync-server-2013-load-balancing-requirements.md)참조 하세요.

  - 전용 대규모 모임 풀에 대해 모니터링 서버를 사용 하려면 Lync Server 배포의 모든 프런트 엔드 서버 풀에서 공유 되는 모니터링 서버 및 해당 데이터베이스를 사용 하는 것이 좋습니다.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>하드웨어 및 소프트웨어 요구 사항

전용 대규모 모임 풀의 서버에 대 한 하드웨어 요구 사항은 다른 Lync Server 2013 서버와 동일 합니다. 하드웨어 요구 사항에 대 한 자세한 내용은 "[Lync server 용 서버 하드웨어 플랫폼 2013](lync-server-2013-server-hardware-platforms.md)"을 참조 하십시오.

전용 대규모 모임 풀의 서버는 모든 Lync Server 2013 소프트웨어 요구 사항을 충족 해야 합니다. 소프트웨어 요구 사항에 대한 자세한 내용은 다음 설명서를 참조하십시오.

  - [Lync Server 2013의 서버 및 도구 운영 체제 지원](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013의 데이터베이스 소프트웨어 지원](lync-server-2013-database-software-support.md)

  - [Lync Server 2013의 추가 소프트웨어 요구 사항](lync-server-2013-additional-software-requirements.md)

또한 Lync Server 2013와 모든 Lync Server 2013 클라이언트에는 최신 업데이트가 있어야 합니다.

</div>

<div>

## <a name="configuration-requirements"></a>구성 요구 사항

대규모 모임에 대해 특별한 새로운 회의 정책을 만들고 해당 전용 대규모 모임 풀에 있는 사용자에게 해당 회의 정책을 지정하는 것이 좋습니다. 다음 설정을 사용하여 회의 정책을 구성합니다.

  - **MaxMeetingSize** 옵션을 **1000**으로 설정합니다(기본값 **250**).

  - **AllowLargeMeetings** 옵션을 **True**로 설정합니다.

  - **EnableAppDesktopSharing** 옵션을 **None**으로 설정합니다.

  - **AllowUserToScheduleMeetingsWithAppSharing** 옵션을 **False**로 설정합니다.

  - **AllowSharedNotes** 옵션을 **False**로 설정합니다.

  - **AllowAnnotations** 옵션을 **False**로 설정합니다.

  - **DisablePowerPointAnnotations** 옵션을 **True**로 설정합니다.

  - **AllowMultiview** 옵션을 **False**로 설정합니다.

  - **EnableMultiviewJoin** 옵션을 **False**로 설정합니다.

<div>


> [!NOTE]  
> Lync Server 2013의 1000 사용자 대규모 모임에 대 한 지원에는 모임 스케줄러에 대 한 회의 정책의 <STRONG>AllowLargeMeetings</STRONG> 설정이 true로 설정 되어 있어야 합니다. 이 설정을 true로 설정 하면 사용자가 모임에 참가 하는 경우 Lync 환경이 추가 대규모 모임에 최적화 됩니다. 특히 대규모 모임에서는 Lync에서 전체 모임 참가자 목록의 초기 또는 업데이트를 표시 하지 않으므로 클라이언트 및 Lync Server 2013에 대 한 성능 병목 현상이 발생 하 게 됩니다. 대신 Lync에서는 사용자 및 모임의 발표자 목록에 대 한 정보만 표시 합니다. Lync에서는 여전히 대규모 모임에서 사용할 수 있는 총 참가자 수를 올바르게 표시 합니다.



</div>

**최대 모임 크기** 설정을 제외하고 여기에 지정되는 다른 모든 모임 정책 설정은 대규모 모임에 필요하지 않은 회의 기능을 사용하지 않도록 설정하기 위해 필요합니다.

또한 풀에 있고 모임 일정 관리를 담당 하는 각 Lync Server 2013 사용자에 게 적절 한 사용 권한이 있도록 전용 대규모 모임 풀을 구성 해야 합니다. 이렇게 하려면 다음을 수행합니다.

  - **발표자로 지정** 옵션을 **없음**으로 설정합니다. 일반적으로 대규모 모임의 모든 참가자 중 일부 소수만 발표자가 됩니다. 대규모 모임에서 참가자를 자동으로 발표자로 허용해서는 안됩니다. 대신 모임 예약 시에 발표자를 명시적으로 지정하거나 대규모 모임 중에 명시적으로 승격해야 합니다.

  - **기본적으로 배정 된 회의 유형** 확인란이 선택 되지 않았는지 확인 합니다. 이 설정은 Lync 2013에 대 한 온라인 모임 추가 기능이 이끌이의 지정 된 전화 회의를 사용 하 여 항상 회의를 예약할 지, 즉 예약 된 모임에 같은 참가 URL 및 오디오 정보가 있음을 의미 합니다. 소규모 그룹 공동 작업 시나리오에서는 모든 사용자에 게 고유한 회의가 있고, 상수 조인 URL 및 오디오 정보를 사용 하면 모임에 더 빠르게 참가할 수 있으므로 이러한 지정 된 회의 유형이 제대로 작동 합니다. 그러나 대규모 모임 시나리오에서는 대규모 모임 지원 담당자가 단일 사용자 자격 증명 집합을 사용 하 여 대규모 모임을 예약 하 고 모임 요청자에 게 참가 Url 및 오디오 정보를 제공 합니다. 이 경우에는 각 모임에 서로 다른 URL을 사용 하 여 작업 하는 것이 좋습니다.

  - 필요한 경우가 아니면 **기본적으로 익명 사용자 허용** 확인란의 선택이 취소되었는지 확인합니다. 이 설정은 지정 된 회의를 사용 하지 않을 때 Lync 2013에 대 한 온라인 모임 추가 기능에 의해 예약 된 기본 모임 액세스 유형에 영향을 줍니다. 이 설정에 적합한 옵션은 조직의 요구 사항에 따라 달라집니다. 조직에서 수행되는 대규모 모임 중 대부분이 내부 모임인 경우에는 이 옵션을 선택하지 마십시오. 대부분의 대규모 모임에 외부 사용자가 참가할 수 있어야 하는 경우 이 옵션을 선택합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

