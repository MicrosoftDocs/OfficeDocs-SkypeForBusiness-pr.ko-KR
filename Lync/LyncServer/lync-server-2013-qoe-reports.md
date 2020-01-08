---
title: 'Lync Server 2013: 체감 품질 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04960c43dc8e29c6e5af44a1d3109e40dd578479
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a>Lync Server 2013의 체감 품질 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>체감 품질 요약/추세 보고서

체감 품질 요약/추세 보고서는 조직의 네트워크 리소스가 충분 한지 확인 하는 데 도움이 되도록 하루 중 피크 사용 시간을 찾고 해당 시간 동안 미디어 품질을 검사 하는 데 유용 합니다. 조직에서는 보고서에 사용 가능한 여러 필터를 사용 하 여 특정 위치, 클라이언트 및 장치 유형 및 서버의 성과 번호를 격리할 수도 있습니다.

체감 품질 요약/추세 보고서는 다음과 같이 구성 됩니다.

  - UC-UC 요약/추세 보고서

  - PSTN 요약/추세 보고서

  - 회의 요약/추세 보고서

</div>

<div>

## <a name="qoe-performance-reports"></a>체감 품질 성과 보고서

체감 품질 성능 보고서는 중재 서버, A/V 회의 서버, 끝점 위치의 체감 품질 성능에 집중 하는 세 가지 보고서에 대 한 세부 정보를 제공 합니다.

</div>

<div>

## <a name="mediation-server-performance-report"></a>중재 서버 성능 보고서

중재 서버 성능 보고서에는 지정 된 기간 동안 하나 이상의 중재로 얻은 메트릭이 나열 됩니다. 통합 커뮤니케이션 (UC) 조정 서버 레그에 대 한 메트릭과 각 통화에 대 한 중재 서버에서 게이트웨이 다리를 개별적으로 보고 합니다. 이 보고서를 사용 하 여 조직의 다양 한 조정 서버에 대 한 볼륨과 성능을 비교할 수 있습니다.

각 중재 서버 (및 각 통화 레그)에 대해 보고서에 다음이 표시 됩니다.

  - 통화 수

  - 패킷 손실

  - 왕복 시간

  - 지터

  - SPECIALIST (대화 평균 견해 점수)

  - SPECIALIST 보내기

  - SPECIALIST 듣기

  - 네트워크 SPECIALIST

  - 네트워크 SPECIALIST 성능 저하

  - 에코 반환

  - 신호 수준

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>A/V 회의 서버 성능 보고서

A/V 회의 서버 성능 보고서는 지정 된 기간 동안 하나 이상의 A/V 회의 서버에서 달성 한 메트릭의 목록을 제공 합니다. 이 보고서를 사용 하 여 조직의 다양 한 A/V 회의 서버의 볼륨과 성능을 비교할 수 있습니다. 조직에서 보고서를 격리 하 여 Lync 클라이언트나 PSTN 클라이언트 같은 특정 클라이언트 유형에 대 한 환경만 표시 하도록 할 수도 있습니다.

각 A/V 회의 서버에 대해 보고서에 다음이 표시 됩니다.

  - 컨퍼런스 수

  - 패킷 손실

  - 왕복 시간

  - 지터

  - SPECIALIST (대화 평균 견해 점수)

  - SPECIALIST 보내기

  - SPECIALIST 듣기

  - 네트워크 SPECIALIST

  - 네트워크 SPECIALIST 성능 저하

  - 에코 반환

  - 신호 수준

</div>

<div>

## <a name="location-based-performance-report"></a>위치 기반 성능 보고서

위치 기반 성능 보고서는 네트워크 위치 목록을 제공 하 고 각 위치에 대해 미리 결정 된 각 품질 범위의 통화 수를 보여 줍니다. 이 보고서의 목표는 다양 한 위치에 대 한 조직의 전화 통화 중 대규모의 미디어 품질에 대 한 통찰력을 제공 하 여 성능이 좋지 않은 위치를 식별 하 고 조직의 미디어 품질에 대 한 다양 한 점수를 볼 수 있도록 하는 것입니다. 다른 위치

보고서를 표시할 때 조직에서 보고 하도록 결정 하는 각 메트릭에 대해 각 테이블에 대 한 여러 메트릭이 표시 됩니다. 이 보고서에 대해 다음 메트릭 중에서 선택할 수 있습니다.

  - SPECIALIST (대화 평균 견해 점수)

  - 네트워크 SPECIALIST

  - 네트워크 SPECIALIST 성능 저하

  - SPECIALIST 보내기

  - SPECIALIST 듣기

  - 패킷 손실

  - 지터

  - 긴

</div>

</div>

<span> </span>

</div>

</div>

</div>

