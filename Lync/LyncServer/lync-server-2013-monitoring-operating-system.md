---
title: 'Lync Server 2013: 운영 체제 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5bd837bab2ca4323dd0fb2f4d29b31d653d37c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a>Lync Server 2013의 운영 체제 모니터링

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-01-26_

Lync Server 2013의 모든 서버 및 구성 요소에 대 한 성능을 모니터링 해야 합니다. 가장 중요 한 구성 요소 중 하나는 운영 체제 자체에 해당 합니다. Lync Server 2013는 다음과 같은 x64 버전을 지원 합니다.

  - Windows Server 2008 R2

  - Windows Server 2012 R2 및 Windows Server 2012

운영 체제를 모니터링 하는 가장 투명 한 방법은 Windows Server 운영 체제 관리 팩을 사용 하는 것입니다. Windows Server 2012, Windows Server 2012 R2 및 Windows Server 2008 r 2를 실행 하는 컴퓨터의 성능, 상태 및 가용성과 같은 기본적인 모니터링 기본 사항을 제공 합니다.

이러한 관리 팩은 중요 한 이벤트 및 성능 지표에 대 한 검색, 경고 및 자동 응답을 통해 문제 해결 시간을 줄이고 Windows Server를 실행 하는 시스템의 전반적인 가용성과 성능을 향상 시킵니다. 운영 체제

System Center Operations Manager 용 관련 Windows Server 관리 팩과 별도로, 다음 시스템 도구 및 리소스를 사용 하 여 운영 체제의 상태를 모니터링할 수 있습니다 (운영 체제 버전에 따라 다름).

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 r 2에는 관리자가 기본 운영 체제 모니터링 및 관리를 지원 하기 위한 다음과 같은 추가 기능 및 도구가 포함 되어 있습니다.

  - **Windows 리소스 모니터** 는 프로세스 및 서비스에서 시스템 리소스를 사용 하는 방법을 이해 하는 강력한 도구입니다. 리소스 사용 현황을 실시간으로 모니터링 하는 것 외에도 자원 모니터를 통해 응답 하지 않은 프로세스를 분석 하 고, 파일을 사용 중인 응용 프로그램을 식별 하 고, 프로세스 및 서비스를 제어할 수 있습니다.

  - **안정성 분석 구성 요소** 는 시스템 사용 및 안정성에 대 한 자세한 경험 정보를 제공 하는 실시간 에이전트입니다. 이 정보는 휴대용 판독기 시스템에서 사용할 수 있도록 WMI 인터페이스를 통해 노출 됩니다. 개발자는 WMI 인터페이스를 통해 안정성 분석 구성 요소를 공개 하 여 응용 프로그램을 모니터링 및 분석 하 고 안정성과 성능을 향상 시킬 수 있습니다.

  - **Windows Server 2008 R2** 는 기본 제공 안정성 분석 구성 요소를 사용 하 여 전체 시스템 사용량 및 시간에 따른 안정성에 대 한 정보를 제공 하는 안정성 인덱스를 계산 합니다. 또한 안정성 분석 구성 요소는 Windows 업데이트 및 응용 프로그램 설치와 같은 안정성에 영향을 줄 수 있는 중요 한 시스템 변경 내용을 추적 합니다.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Windows Server 2008 Windows 안정성 및 성능 모니터

Windows 안정성 및 성능 모니터는 성능 로그 및 경고, 서버 성능 관리자 및 시스템 모니터를 포함 하 여 이전 독립 실행형 도구의 기능을 결합 한 MMC 스냅인입니다. 성능 데이터 수집 및 이벤트 추적 세션을 사용자 지정 하기 위한 그래픽 인터페이스를 제공 합니다.

또한 안정성 모니터, 즉 시스템 변경 내용을 추적 하 고 시스템 안정성과 비교 하 여 해당 관계를 그래픽으로 보여 주는 MMC 스냅인이 포함 되어 있습니다.

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Windows 안정성 및 성능 모니터

Windows 안정성 및 성능 모니터는 성능 로그 및 경고, 시스템 모니터 및 서버 성능 관리자와 같은 이전의 독립 실행형 도구를 함께 사용 하는 경우에도 Windows Server 2008에 대 한 몇 가지 새로운 기능을 제공 합니다. 다음과 같은 Windows Server 2008 R2

  - 데이터 수집기 집합

  - 자원 보기

  - 안정성 모니터

  - 로그를 만들기 위한 마법사 및 서식 파일

**데이터 수집기 집합** 은 다양 한 성능 모니터링 시나리오에서 사용할 수 있도록 데이터 수집기를 다시 사용할 수 있는 요소로 그룹화 합니다. 데이터 수집기 그룹을 데이터 수집기 집합으로 저장 한 후에는 단일 속성 변경을 통해 일정 작업과 같은 작업을 전체 집합에 적용할 수 있습니다. Windows 안정성 및 성능 모니터에는 시스템 관리자가 서버 역할 또는 모니터링 시나리오와 관련 된 성능 데이터를 즉시 수집 하기 시작할 수 있도록 하는 기본 데이터 수집기 집합 템플릿이 포함 되어 있습니다.

Windows 안정성 및 성능 모니터의 홈 페이지는 CPU, 디스크, 네트워크 및 메모리 사용에 대 한 실시간 그래픽 개요를 제공 하는 새로운 **리소스 보기** 화면입니다. 시스템 관리자는 이러한 각 모니터링 되는 요소를 확장 하 여 어떤 프로세스에서 어떤 리소스를 사용 하 고 있는지 확인할 수 있습니다. 이전 버전의 Windows에서는이 실시간 프로세스 관련 데이터를 작업 관리자의 제한 된 형식 으로만 사용할 수 있었습니다.

**안정성 모니터** 는 예기치 않은 문제로 인해 시스템의 안정성이 저하 되었는지 여부를 나타내는 시스템 안정성 인덱스를 계산 합니다. 시간에 따른 안정성 인덱스 그래프는 문제가 발생 하기 시작 하는 날짜를 빠르게 식별 합니다. 함께 제공 되는 시스템 안정성 보고서는 안정성을 줄이는 문제를 해결 하는 데 도움이 되는 세부 정보입니다. 오류 (응용 프로그램 오류, 운영 체제 손상 또는 하드웨어 오류)와 함께 시스템 변경 (응용 프로그램 설치 또는 제거, 운영 체제에 대 한 업데이트 또는 드라이버 추가 또는 수정)을 확인 한 후에는 다음에 대 한 전략을 검토 합니다. 문제를 해결 하는 것이 빠르게 개발 될 수 있습니다.

이제 **마법사 인터페이스**를 통해 로그 파일에 카운터를 추가 하 고 해당 시작, 중지 및 지속 시간을 예약할 수 있습니다. 또한이 구성을 템플릿으로 저장 하면 시스템 관리자가 데이터 수집기 선택 및 예약 프로세스를 반복 하지 않고 다른 컴퓨터에서 동일한 로그를 수집할 수 있습니다. 성능 로그 및 경고 기능은 모든 데이터 수집기 집합에서 사용할 Windows 안정성 및 성능 모니터에 통합 되었습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

