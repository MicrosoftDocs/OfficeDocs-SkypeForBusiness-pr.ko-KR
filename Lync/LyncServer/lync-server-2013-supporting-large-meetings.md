---
title: 'Lync Server 2013: 대용량 모임 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e8c37c5498702e893da803497177c086a39a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>Lync Server 2013를 사용 하 여 대용량 모임 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

대규모 회의는 다음 특성을 가지 므로 이전 섹션에서 설명한 테스트 모델을 따르지 않습니다.

  - 모임 형식은 일대다 프레젠테이션입니다.

  - 한 명 또는 소수의 사용자가 발표자이 고 모든 사람이 참석자로 참가 합니다.

  - PowerPoint 프레젠테이션 공유는 기본 데이터 공동 작업 작업입니다.

  - 오디오는 필수 이며 비디오만 사용할 수도 있습니다.

  - 일반적으로 모임 이끌이 또는 이끌이를 위한 보조자 등의 전담 사용자가 모임을 미리 설정 합니다.

  - 전용 스태프 (발표자가 아님)는 온라인 모임 연결, 오디오, 비디오 및 슬라이드 공유 작업 확인, 로비와 사용자 역할, 음소거 및 음소거 해제, 질문 하기, 녹음/녹화 관리 등의 모임을 실행 합니다. 알맞은.

최대 1000 명의 사용자에 대 한 대규모 모임을 지원 하려면 공유 하드웨어 모델과 비 예약 모델에 관련 된 문제를 해결 해야 합니다.

1000 사용자의 모임에 충분 한 CPU 및 메모리 리소스를 확보 하기 위해 호스팅 프런트 엔드 서버는 다른 인스턴트 메시징 (IM) 및 현재 상태 또는 엔터프라이즈 음성 작업 부하를 호스팅하지 않아야 합니다. 또한 다른 모임의 크기에 관계 없이 다른 모임을 호스팅하지 않아야 합니다. 즉, 최대 1000 사용자에 게 모임을 호스팅 하려면 최대 1000 사용자에 대 한 대규모 모임 호스팅 전용 별도의 Lync Server 풀을 설정 해야 합니다.

대규모 모임을 호스팅 전용으로 사용할 수 있는 Lync 서버 풀은 동시에 최대 1000 사용자에 대 한 하나의 모임만 호스팅하고 있으므로, 프런트 엔드 Serv의 전용 지원을 위해 모임 시간을 대역 외 예약 프로세스를 통해 미리 예약 해야 합니다. 사람이. 동시에 여러 개의 대용량 모임을 지원 하려면 하나의 전용 대량 모임 풀을 설정 하는 것이 좋습니다.

전용 사용자는 대규모 모임의 온라인 부분을 실행 하 고 모니터링 하는 것이 좋습니다. 조직의 기본 설정에 따라이 사람이 이끌이, 이끌이 또는 발표자의 대리인 또는 전용 대규모 모임 지원 팀의 구성원 일 수 있습니다.

다음 섹션에서는 대규모 모임 시나리오를 지원 하기 위해 Lync Server 2013를 사용 하는 모범 사례를 포함 하 여 대규모 모임에 대 한 전용 풀을 구현 하는 방법을 설명 합니다.

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

