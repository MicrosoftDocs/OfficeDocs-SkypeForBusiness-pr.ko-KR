---
title: 'Lync Server 2013: 대규모 모임 지원 FAQ'
description: 'Lync Server 2013: 대규모 모임 지원 FAQ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8d206400b46fc32a3af7b21ad7d50663e85d069
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557554"
---
# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Lync Server 2013에 대 한 대규모 모임 지원 FAQ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

다음 섹션에서는 대규모 모임 만들기 및 실행에 대한 일반적인 사항을 설명합니다.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>대규모 모임에 참가할 수 있는 사용자의 수

Lync Server 사용자 모델은 공유 풀에 있는 250 명의 사용자에 대 한 제한 또는 대규모 모임 전용 풀의 1000 사용자를 지정 하지만 이러한 수치는 테스트를 거친 사용자 수 뿐 아니라 테스트에 사용한 특정 하드웨어 집합에만 표시 됩니다. 이 테스트를 기준으로 하여 최대 크기에 대한 권장 제한이 제공됩니다. 그러나 Lync Server 관리 셸에서 Windows PowerShell cmdlet을 사용 하거나 Lync Server 제어판을 사용 하 여 구성 하는 하나 이상의 회의 정책을 구성 하 여 조직의 모임에서 허용 되는 실제 참가자 수를 제어할 수 있습니다. 회의 정책에서 지정하는 값은 1에서 4,294,967,295 사이의 32비트 정수일 수 있지만, 권장 크기는 참가자 2~250명(두 끝값 포함)이며 기본값은 250입니다.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>대규모 모임 전용 풀에 포함할 수 있는 모임 또는 기타 작업의 수

참가자 수가 최대 1,000명인 대규모 모임에서 최적의 사용자 환경을 유지하려면 대규모 모임 전용 풀에서 한 번에 하나의 대규모 모임만 호스팅하는 것이 좋습니다. 또한 대규모 모임이 진행 중일 때는 해당 풀에서 다른 작업 실행을 허용하지 않는 것이 좋습니다.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>대규모 모임의 이끌이가 전용 풀에 있어야 하는지 여부

대규모 모임 예약을 관리하는 전담 직원 이외의 사용자는 전용 풀에 배치하지 않는 것이 좋습니다. 이렇게 하면 다른 실시간 통신 트래픽으로 인해 풀에서 호스팅되는 대규모 모임에서 문제가 발생하지 않습니다. 대규모 모임 예약 직원의 사용자 계정을 사용하여 전용 풀에서 대규모 모임을 예약해야 합니다. 모임 이끌이(대규모 모임을 요청하는 사용자)의 사용자 계정을 대규모 모임 발표자로 추가해야 합니다.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>대규모 모임에서 사용할 수 있는 미디어 형식

사용자가 최대 1,000명인 대규모 모임에는 오디오, 비디오, PowerPoint 공유, 화이트보드 및 현재 상태 폴링을 포함할 수 있습니다.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>대규모 모임의 그룹 IM(인스턴트 메시징) 사용 가능 여부

예. 그러나 인스턴트 메시지의 수가 많은 경우(특히 많은 모임 참가자가 인스턴트 메시지를 보내는 경우) IM 창에서 텍스트를 빠르게 스크롤하면서 발생하는 문제로 인해 사용자 환경이 영향을 받을 수 있습니다. 또한 최대 1,000명의 사용자에게 많은 양의 인스턴트 메시지를 배달하는 경우 서버 부하가 매우 많아져 성능에도 영향을 줄 수 있습니다. 일반적으로 IM은 질문과 대답에만 필요 합니다 (Q \& As).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>전화기에서 전화를 걸어 대규모 모임에 참가할 수 있는지 여부

예. Lync Server 2013 풀이 제대로 배포 되 고 전화 접속 회의를 사용 하도록 설정 된 경우 사용자는 전화를 걸어 대규모 모임에 참가할 수 있습니다. 테스트 결과에 따르면 1,000명의 사용자 중 최대 15%가 10분 동안 대규모 모임에 참가할 수 있는 것으로 확인되었습니다.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>가상 토폴로지에서 대규모 모임 호스팅 가능 여부

가상 토폴로지에서 대규모 모임을 테스트하지는 않았으므로 가상 컴퓨터를 사용하여 대규모 모임 전용 풀을 호스팅하는 방법은 지원되지 않습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

