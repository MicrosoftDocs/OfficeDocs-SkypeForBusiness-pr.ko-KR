---
title: Lync Server 2013 회의 로드 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd78b6dcedc66f5a2235b45066be7faf70d4379b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Lync Server 2013의 회의 로드 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

일부 다른 전용 회의 솔루션과 달리 Lync Server 아키텍처는 공유 하드웨어 모델입니다. 이는 각각 서로 다른 실시간 통신을 지 원하는 여러 소프트웨어 구성 요소에서 동일한 하드웨어를 공유 한다는 의미입니다. 각 실시간 통신 유형은 서버에 특정 로드를 배치 합니다. 예를 들어 프런트 엔드 서버는 SIP (세션 시작 프로토콜) 라우팅 구성 요소, 웹 응용 프로그램 (예: 주소록 검색), 웹 회의 서비스, A/V 회의 서비스, Enterprise Voice 응용 프로그램 (예: 회의 수행자 응용 프로그램 및 응답 그룹 응용 프로그램) 및 중재 서버를 실행할 수 있습니다. 프런트 엔드 서버의 데이터베이스 집합은 사용자, 연락처, 현재 상태, 회의 및 음성 라우팅 데이터에 대 한 저장 및 처리도 제공 합니다. 이 하드웨어 공유를 사용 하 여 구성 요소, 서비스, 프로세스가 CPU 및 메모리 리소스에 대해 경합 하므로, 비 회의 작업 부하는 서버 크기 조정에 직접적인 영향을 줍니다.

다른 하드웨어 포트 기반 회의 솔루션과 비교 하 여 Lync Server 회의 아키텍처는 비 예약 모델입니다. 사용자가 모임을 예약 하면 Lync Server가 회의 데이터베이스에 레코드를 만들며,이는 회의 데이터를 저장 하지만 예약 된 모임의 하드웨어 리소스를 미리 예약 하지는 않습니다. 대신 Lync Server에는 풀의 모든 프런트 엔드 서버에서 균등 하 게 배포 되는 방식으로 프런트 엔드 서버에서 회의 리소스를 동적으로 할당 하는 부하 분산 논리가 기본적으로 포함 되어 있습니다. 이렇게 하면 하드웨어 리소스가 효과적으로 제공 되 고 사용 되지만 매우 큰 모임 (특히 적절 한 계획 없이)을 지원 하기 어렵습니다. 예를 들어 Lync Server 2013 풀이 최고 용량 보다 가까이 실행 되는 경우 각 프런트 엔드 서버는 약 125 평균 크기의 모임을 호스트할 수 있습니다. 다른 작은 모임을 추가 하는 것은 문제가 되지 않지만, 프런트 엔드 서버는 다른 125 모임과 동시에 이러한 대규모 모임을 지원할 수 없기 때문에 1000 사용자에 대 한 모임을 추가 하는 것이 문제가 될 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

