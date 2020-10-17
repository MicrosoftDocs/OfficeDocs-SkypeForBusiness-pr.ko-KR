---
title: Lync Server 2013 회의 부하 분산
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f7b2d759ec9370bbf7eeeb2844edd3511ba0f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499205"
---
# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Lync Server 2013의 회의 부하 분산

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

다른 전용 회의 솔루션과 달리 Lync Server 아키텍처는 공유 하드웨어 모델입니다. 즉, 각각 여러 가지 실시간 통신을 지원하는 여러 소프트웨어 구성 요소에서 동일한 하드웨어를 공유합니다. 각 유형의 실시간 통신은 서버에 특정 부하를 줍니다. 예를 들어 프런트 엔드 서버는 SIP (Session 착수 프로토콜) 라우팅 구성 요소, 웹 응용 프로그램 (예: 주소록 검색), 웹 회의 서비스, A/V 회의 서비스, Enterprise Voice 응용 프로그램 (예를 들어, 회의 전화 교환 응용 프로그램 및 응답 그룹 응용 프로그램) 및 중재 서버를 실행할 수 있습니다. 프런트 엔드 서버의 데이터베이스 집합은 사용자, 연락처, 현재 상태, 회의 및 음성 라우팅 데이터에 대 한 저장소 및 처리도 제공 합니다. 이러한 하드웨어 공유에서는 구성 요소, 서비스 및 프로세스가 CPU 및 메모리 리소스를 경합하므로 비회의 작업 부하는 서버 확장에 직접적인 영향을 주지 않습니다.

다른 하드웨어 포트 기반 회의 솔루션과 비교 하 여 Lync Server 회의 아키텍처는 예약 되지 않은 모델입니다. 사용자가 모임을 예약 하면 Lync Server에서 회의 데이터를 저장 하는 a meeting 데이터베이스에 레코드를 만들지만 예약 된 모임에 대 한 하드웨어 리소스를 미리 예약 하지 않습니다. 대신, Lync Server에는 프런트 엔드 서버에서 회의 리소스를 풀의 모든 프런트 엔드 서버에 동일 하 게 분산 되는 방식으로 동적으로 할당 하는 부하 분산 논리가 기본적으로 포함 되어 있습니다. 이러한 방식으로 하드웨어 리소스를 효율적으로 프로비전하고 활용할 수 있지만 특히 적합한 계획이 없을 경우 대규모 모임을 지원하는 데에는 어려움이 있습니다. 예를 들어 Lync Server 2013 풀이 최상위 용량에 근접 하 게 실행 되는 경우 각 프런트 엔드 서버는 약 125의 평균 크기 모임을 호스트할 수 있습니다. 다른 소규모 모임을 추가 하는 것은 문제가 되지 않지만, 1000 사용자에 게 모임을 추가 하는 것은 프런트 엔드 서버가 다른 125 모임과 동시에 이러한 대규모 모임을 지원 하지 못할 수 있기 때문에 문제가 될 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

