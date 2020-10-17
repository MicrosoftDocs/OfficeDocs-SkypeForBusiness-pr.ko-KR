---
title: 'Lync Server 2013: 성능에 대 한 모바일 기능 모니터링'
description: 'Lync Server 2013: 성능을 위해 모바일 기능을 모니터링 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6c366542e88406df043ba1a782ee12cd64bd804
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562904"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Lync Server 2013의 성능에 대 한 모바일 기능 모니터링

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-14_

Lync Server Mobility Service (Mcx) 및 통합 커뮤니케이션 웹 API (FWA)는 프런트 엔드 서버 및 프런트 엔드 풀에 대 한 부하를 증가 시킵니다. Lync 2013 Mobile을 실행 하는 android 및 Apple 장치와 2010 같이 모바일 응용 프로그램을 최소화 한 경우에도 서버에 대 한 연결을 유지 하는 모바일 장치는 모바일 응용 프로그램을 최소화할 때 서버에 대 한 연결을 종료 하는 장치 보다 부하가 더 많이 부과 됩니다. 이동성 사용량이 증가 함에 따라 모바일 기능 성능을 모니터링 하 여 용량을 늘려야 하는 시기를 결정 해야 합니다.

다음과 같은 다양한 제한이 모바일 성능에 영향을 줍니다.

  - 사용 가능한 메모리

  - 요청 큐 제한

  - 동시 연결 수

  - IIS 큐 길이

이동성 성능에 영향을 줄 수 있는 서버의 다른 제한은 최대 12 개의 동시 로그인, 인증, 세션 갱신 및 종료입니다. 대부분의 배포에서는 이러한 최대값을 수정할 필요가 없습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 서버 메모리 용량 제한 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Lync Server 2013에서 모바일 서비스 및 c u에 대 한 모니터링 사용](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Lync Server 2013에서 고성능을 위한 모바일 서비스 구성](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Lync Server 2013에서 IIS 요청 추적 로그 파일 모니터링](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Lync Server 2013의 모바일 기능 성능 카운터](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

