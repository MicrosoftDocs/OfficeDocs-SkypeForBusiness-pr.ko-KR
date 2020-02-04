---
title: 'Lync Server 2013: 대용량 모임 지원 FAQ'
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
ms.openlocfilehash: 6f5a8d63fddf3b8633ebf31651d501458eaf4893
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Lync Server 2013에 대 한 대용량 모임 지원 FAQ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

다음 섹션에서는 대규모 모임 만들기 및 실행에 대 한 일반적인 질문에 대 한 답변을 제공 합니다.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>Q: 대용량 모임에 참가할 수 있는 사용자는 몇 명 인가요?

Lync Server 사용자 모델은 공유 풀의 250 사용자에 대 한 제한 사항을 지정 하거나 대규모 모임에 대 한 풀의 사용자를 1000 하며, 이러한 숫자는 테스트 한 사용자 수와 테스트에 사용한 특정 하드웨어 집합에 대해서만 표시 됩니다. 저희 테스트에 따라, 최대 크기에 대 한 제한을 사용 하는 것이 좋습니다. 그러나 Lync Server 관리 셸에서 Windows PowerShell cmdlet을 사용 하거나 Lync Server를 사용 하 여 구성 하는 하나 이상의 회의 정책을 구성 하 여 조직의 모임에서 허용 되는 실제 참가자 수를 제어할 수 있습니다. 제어판). 회의 정책에서 지정 하는 번호는 1에서 4294967295 사이의 모든 32 비트 정수를 사용할 수 있지만 권장 되는 크기는 2와 250 사이의 참가자 (포함) 사이입니다. 기본 값은 250입니다.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>Q: 대규모 모임 전용으로 풀에서 사용할 수 있는 모임 또는 기타 작업은 몇 개입니까?

최대 1000 참가자에 대 한 대규모 모임에서 최상의 사용자 환경을 유지 하기 위해 대규모 모임에 전담 되는 풀에서 한 번에 하나의 대규모 모임을 주최 하는 것이 좋습니다. 또한 대규모 모임이 진행 중일 때 해당 풀에서 다른 작업을 실행 하도록 허용 하지 않는 것이 좋습니다.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>Q: 대규모 모임의 이끌이를 전용 풀에서 사용할 수 있나요?

아니요. 전용 풀에서 대규모 모임의 일정을 관리 하는 전용 직원 이외의 사용자는 안내 하지 않는 것이 좋습니다. 이렇게 하면 다른 실시간 통신 트래픽이 풀에 호스팅되는 대규모 모임에서 문제를 일으킬 수 없습니다. 대규모 모임 예약 직원의 사용자 계정을 사용 하 여 전용 풀에서 대규모 모임을 예약 해야 합니다. 대규모 모임에 대 한 발표자로 모임 이끌이의 사용자 계정 (대규모 모임을 요청한 사용자)을 추가 해야 합니다.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>Q: 대용량 모임에서 사용할 수 있는 미디어 형식을 무엇 인가요?

최대 1000 사용자와의 대규모 모임에는 오디오, 비디오, PowerPoint 공유, 화이트 보드 및 현재 상태 폴링이 포함 될 수 있습니다.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>Q: 대규모 모임에서 그룹 인스턴트 메시지 (IM)를 사용할 수 있나요?

예. 그러나 많은 수의 모임 참가자가 보내는 경우 특히 인스턴트 메시지의 수가 많으면 메신저 대화 창의 빠른 텍스트 스크롤 문제로 인해 사용자 환경에 영향을 줄 수 있습니다. 최대 1000 사용자에 게 많은 양의 인스턴트 메시지를 제공 하는 것도 성능에 영향을 줄 수 있는 서버 로드를 크게 유발할 수 있습니다. 일반적으로 질문 및 답변에만 IM이 필요 합니다 (\&Q As).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>사용자가 휴대폰에서 전화를 걸어 대용량 모임에 참가할 수 있나요?

예. Lync Server 2013 풀을 제대로 배포 하 고 전화 접속 회의를 사용 하도록 설정한 경우 사용자는에서 전화를 걸어 대규모 모임에 참가할 수 있습니다. 저희 테스트에는 최대 15%의 1000 사용자가 10 분 동안 대규모 모임에 참가할 수 있다는 것이 표시 되었습니다.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>Q: 가상 토폴로지에서 대규모 모임을 호스트할 수 있나요?

가상 토폴로지에서 대규모 모임을 테스트 하지 않았으므로 대규모 모임에 대해 전용 풀을 호스팅하기 위해 가상 컴퓨터를 사용 하는 것은 지원 되지 않습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

