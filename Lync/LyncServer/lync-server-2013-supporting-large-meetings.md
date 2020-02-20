---
title: 'Lync Server 2013: 대규모 모임 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d1ba298ea35c177eb51191c230ea51a50d6c3e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>Lync Server 2013를 사용 하 여 대규모 모임 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

대규모 모임은 다음과 같은 특성을 갖기 때문에 이전 섹션에서 설명한 테스트 모델을 따르지 않습니다.

  - 모임 형식이 일대다 프레젠테이션입니다.

  - 한 명 또는 소수의 사용자가 발표자이고 그외 모든 사람은 참석자로만 모임에 참가합니다.

  - PowerPoint 프레젠테이션 공유가 기본 데이터 공동 작업 활동입니다.

  - 오디오가 필요하고 비디오를 사용할 수도 있습니다.

  - 모임 이끌이 또는 이끌이의 보조 등 전담 사용자가 미리 모임을 설정합니다.

  - 전담 직원(발표자가 아님)이 온라인 모임에 연결하고, 오디오, 비디오 및 슬라이드 공유가 작동하는지 확인하고, 대기실 및 사용자 역할을 관리하고, 참가자를 음소거하거나 음소거를 해제하고, 질문을 받고, 기록을 관리하는 등 모임을 적절하게 운영합니다.

최대 1000명의 사용자를 포함하는 대규모 모임을 지원하기 위해서는 공유 하드웨어 모델 및 비예약 모델 모두와 관련된 문제를 해결해야 합니다.

최대 1000 명의 모임에 대 한 충분 한 CPU 및 메모리 리소스를 확보 하려면 호스팅 프런트 엔드 서버에서 다른 IM (인스턴트 메시징) 및 현재 상태 또는 Enterprise Voice 작업을 호스트 해서는 안 됩니다. 또한 다른 모임의 크기에 관계없이 다른 모임을 호스팅해서도 안됩니다. 즉, 최대 1000 명의 사용자에 게 모임을 호스트 하려면 최대 1000 명의 사용자에 대 한 대규모 회의 호스팅 전용의 별도 Lync Server 풀을 설정 해야 합니다.

대규모 모임 호스팅 전용 Lync Server 풀은 최대 1000 명의 모임 회의를 동시에 호스트 해야 하므로, 프런트 엔드 Serv에서 전용 지원을 위해 대역 외 예약 프로세스를 통해 모임 시간을 미리 예약 해야 합니다. 사람이. 동시에 두 개 이상의 대규모 모임을 지원 하려면 여러 전용 대규모 모임 풀을 설정 하는 것이 좋습니다.

대규모 모임의 온라인 부분은 전담 사용자가 실행하고 모니터링하는 것이 좋습니다. 이 사용자는 조직의 상황에 따라 이끌이거나 이끌이 또는 발표자의 대리인 또는 전담 대규모 모임 지원 팀의 구성원일 수 있습니다.

다음 섹션에서는 Lync Server 2013을 사용 하 여 대규모 모임 시나리오를 지원 하기 위한 모범 사례를 포함 하 여 대규모 모임에 대 한 전용 풀을 구현 하는 방법을 설명 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 대규모 모임에 대 한 지원 설정](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Lync Server 2013에서 대규모 모임 관리](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

