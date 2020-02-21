---
title: 'Lync Server 2013: QoE 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 353e0941f443e2cb971f8ebd037413232e21b827
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a>Lync Server 2013의 QoE 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>QoE 요약/추세 보고서

QoE 요약/추세 보고서는 조직의 네트워크 리소스가 충분 한지 확인 하기 위해 하루 중 최고 사용 시간을 찾고 해당 시간 동안 미디어 품질을 확인 하는 데 유용 합니다. 조직에서는 보고서에서 사용할 수 있는 다양 한 필터를 사용 하 여 특정 위치, 클라이언트 및 장치 유형, 서버에 대 한 성능 번호를 격리할 수도 있습니다.

QoE 요약/추세 보고서는 다음으로 구성 됩니다.

  - UC-UC 요약/추세 보고서

  - PSTN 요약/추세 보고서

  - 전화 회의 요약/추세 보고서

</div>

<div>

## <a name="qoe-performance-reports"></a>QoE 성능 보고서

QoE 성능 보고서는 중재 서버, A/V 회의 서버 및 끝점 위치의 QoE 성능에 주력 하는 세 가지 보고서에 대 한 세부 정보를 제공 합니다.

</div>

<div>

## <a name="mediation-server-performance-report"></a>중재 서버 성능 보고서

중재 서버 성능 보고서에는 지정 된 기간 동안 하나 이상의 중재에 의해 달성 된 메트릭이 나열 됩니다. UC (통합 통신) 및 각 통화의 중재 서버 간 연결에 대 한 메트릭은 개별적으로 보고 됩니다. 이 보고서를 사용 하 여 조직의 다양 한 중재 서버에 대 한 볼륨 및 성능을 비교 합니다.

각 중재 서버 (and 각 통화 레그)에 대해 보고서에 다음이 표시 됩니다.

  - 통화 수

  - 패킷 손실

  - 라운드트립 시간

  - 지터

  - MOS (대화 평균 평가 점수)

  - MOS 보내기

  - 수신 대기 MOS

  - 네트워크 MOS

  - 네트워크 MOS 성능 저하

  - 에코 반환

  - 신호 수준

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>A/V 회의 서버 성능 보고서

A/V 회의 서버 성능 보고서는 지정 된 기간 동안 하나 이상의 A/V 회의 서버에서 얻은 메트릭 목록을 제공 합니다. 이 보고서는 조직의 다양 한 A/V 회의 서버의 볼륨과 성능을 비교 하는 데 사용할 수 있습니다. 조직에서는 Lync 클라이언트나 PSTN 클라이언트 같은 특정 클라이언트 유형에 대 한 환경만 표시 하도록 보고서를 격리할 수도 있습니다.

각 A/V 회의 서버에 대해 보고서에 다음이 표시 됩니다.

  - 회의 수

  - 패킷 손실

  - 라운드트립 시간

  - 지터

  - MOS (대화 평균 평가 점수)

  - MOS 보내기

  - 수신 대기 MOS

  - 네트워크 MOS

  - 네트워크 MOS 성능 저하

  - 에코 반환

  - 신호 수준

</div>

<div>

## <a name="location-based-performance-report"></a>위치 기반 성능 보고서

위치 기반 성능 보고서는 네트워크 위치 목록을 제공 하 고 각 위치에 대해 미리 결정 된 각 품질 범위의 통화 수를 표시 합니다. 이 보고서의 목표는 다양 한 위치에 대 한 조직의 전화 통화에 대 한 대량의 정보를 파악 하 여 제대로 수행 되지 않는 위치를 파악 하 고 조직의 다양 한 미디어 품질 등급을 볼 수 있도록 하는 것입니다. 다른 위치

보고서를 표시할 때 각 메트릭이 표시 되 면 조직에서 보고 하기로 결정 한 각 메트릭에 대 한 테이블이 하나씩 나타납니다. 이 보고서에 대해 다음 메트릭 중에서 선택할 수 있습니다.

  - MOS (대화 평균 평가 점수)

  - 네트워크 MOS

  - 네트워크 MOS 성능 저하

  - MOS 보내기

  - 수신 대기 MOS

  - 패킷 손실

  - 지터

  - 대기 시간

</div>

</div>

<span> </span>

</div>

</div>

</div>

