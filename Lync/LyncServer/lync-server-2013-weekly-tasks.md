---
title: 'Lync Server 2013: 주간 작업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87d3f87b37b8c0fe29c4dee76467a9e07931551a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a>Lync Server 2013의 주간 작업

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-08-17_

주간 작업은 일반적으로 로그 및 보고서를 수집 하 고 분석 하는 것과 관련 됩니다.

<div>

## <a name="archive-event-logs"></a>이벤트 로그 보관

필요에 따라 이벤트를 덮어쓰도록 이벤트 로그를 구성하지 않을 경우 이벤트 로그를 정기적으로 보관 및 삭제해야 합니다. 이 작업은 시도된 보안 침해를 조사하는 경우 필요할 수 있는 보안 로그에서 특히 중요합니다.

조직에서는 로그 보관에 대 한 정책 및 절차를 정의 해야 합니다.

</div>

<div>

## <a name="create-reports"></a>보고서 만들기

용량 계획, SLA 검토 및 성능 분석에 도움이 되는 상황 보고서를 만듭니다. 이벤트 로그 및 시스템 모니터의 매일 데이터를 사용 하 여 디스크, 메모리 및 CPU 사용량에 대 한 보고서를 만듭니다. System Center Operations Manager를 사용 하 여 가동 시간 및 가용성 보고서를 생성 합니다.

조직에서는 상황 보고서에 대 한 정책 및 절차를 정의 해야 합니다.

</div>

<div>

## <a name="incident-reports"></a>사고 보고서

Lync Server와 관련 된 조직의 문제 보고서에 대 한 주간 감사를 수행 합니다. 이 감사에는 다음이 포함 되어야 합니다.

  - 맨 위에 생성 된, 해결 됨 및 보류 중인 인시던트

  - 해결 되지 않은 문제에 대 한 해결 방법

  - 새 문제 티켓을 포함 하도록 보고서 업데이트

  - 문서 리포지토리를 업데이트 하 여 가이드 문제를 해결 하 고 중단에 대 한 사후를 게시 합니다.

조직의 인시던트 추적 시스템은 Lync Server에 관계 없이 선택 되어 있으므로 특정 지침이 나 포인터를 사용할 수 없습니다. 조직에서 선택한 시스템에 대 한 설명서를 참조 하세요.

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>IIS 로그 및 성능 확인

매주 IIS (인터넷 정보 서비스) 로그 및 성능에 대 한 검토를 수행 합니다. IIS 로그 및 성능을 모니터링 하는 방법에 대 한 자세한 내용은 [Windows Server 2003 IIS (인터넷 정보 서비스) 이벤트 로깅 개요](http://go.microsoft.com/fwlink/?linkid=36077)를 참조 하세요. 검토에는 다음이 포함 되어야 합니다.

  - WWW 서비스 캐시를 모니터링 하는 웹 서비스 캐시 카운터입니다.

  - Asp (Active Server Pages) 카운터-Asp로 실행 되는 응용 프로그램을 모니터링 합니다.

</div>

<div>

## <a name="generate-database-reports"></a>데이터베이스 보고서 생성

**SQL 데이터베이스에 대 한 보고서를 생성 하려면**

1.  Lync Server 2013를 엽니다.

2.  콘솔 트리에서 포리스트 노드, **엔터프라이즈 풀**을 차례로 확장 한 다음 데이터베이스 보고서를 생성할 풀을 클릭 합니다.

3.  세부 정보 창에서 **데이터베이스** 탭을 클릭 합니다.

4.  **데이터베이스** 탭에서 다음을 수행 합니다.
    
    1.  데이터베이스의 이름을 보려면 **일반 설정을**확장 하 고 데이터베이스 이름을 확인 합니다.
    
    2.  풀에 대 한 현재 사용자 요약 통계를 검색 하려면 **사용자 요약 보고서**를 확장 하 고 **이동을**클릭 한 다음 결과를 확인 합니다.
    
    3.  풀의 단일 사용자에 대 한 현재 사용자별 데이터를 검색 하려면 사용자별 **보고서**를 확장 하 고 사용자의 SIP URI를 입력 한 다음 **이동을**클릭 하 고 결과를 확인 합니다.

풀에 대 한 현재 전화 회의 요약 통계를 검색 하려면 **전화 회의 요약 보고서**를 확장 하 고 **이동을**클릭 한 다음 결과를 확인 합니다.

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>보안 및 Lync Server 업데이트 확인

새 서비스 팩, 핫픽스 또는 업데이트를 확인합니다. 해당 하는 경우 테스트 랩에서 테스트를 실시 하 고 변경 제어 절차를 사용 하 여 프로덕션 서버에 대 한 배포를 정렬 합니다. 또한 이제 Lync Server 구성 요소 업데이트를 Windows update의 일부로 사용할 수 있습니다. 모든 Lync Server 구성 요소 업데이트는 업데이트를 적용할 수 있는 Lync Server를 실행 하는 모든 서버에서 동시에 업데이트 해야 합니다.

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>Lync Server 2013 모범 사례 분석기 실행

Lync Server 2013 모범 사례 분석기 도구는 구성 정보를 수집 하 고 구성이 Microsoft 모범 사례에 따라 설정 되는지 여부를 확인 하는 진단 도구입니다. 이 도구에 대 한 설명서는 [Lync Server 2013 모범 사례 분석기](lync-server-2013-lync-server-best-practices-analyzer.md)에 있습니다.

이 도구는 배포의 구성 데이터를 Lync Server의 미리 정의 된 규칙 집합과 비교 하 고 잠재적 문제를 보고 합니다. 보고 된 모든 문제에 대해이 도구는 Lync Server 환경 및 권장 구성에서 현재 구성을 제공 합니다.

올바른 네트워크 액세스를 사용 하 여이 도구는 Lync Server 2013을 실행 하는 AD DS 및 서버를 검사 하 여 다음을 수행할 수 있습니다.

  - 권장 되는 모범 사례에 따라 구성이 설정 되어 있는지 확인 하는 상태 검사를 사전에 수행

  - 최적이 지 않은 구성 설정 또는 권장 되지 않는 옵션 등의 문제 목록을 생성 합니다.

  - 시스템의 일반적인 상태를 판단 합니다.

  - 특정 문제 해결 지원

  - 사용할 수 있는 경우 업데이트를 다운로드 하 라는 메시지 표시

  - 보고 된 문제에 대 한 온라인 및 로컬 설명서를 제공 하 고 문제 해결 팁을 포함 합니다.

  - 나중에 검토 하기 위해 캡처할 수 있는 구성 정보 생성

모든 Lync Server 2013 서버에 RTCBPA이 설치 되어 있는지 확인 하 고 주간 상태 검사 보고서를 생성 합니다. 필요한 경우 결과를 기록해 두고 올바르게 기록 합니다.

</div>

<div>

## <a name="review-sla-performance-figures"></a>SLA 성과 수치 검토

이전 한 주 동안의 주요 성능 데이터를 점검합니다. SLA 요구 사항에 대비 하 여 성능을 검토 합니다. 목표를 달성하지 못한 경향 및 항목을 식별합니다.

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>System Center Operations Manager 관리 팩 및 경력 보고서 검토

Lync Server 2013 관리 팩 및 경험 치 보고서를 구해서 검토 합니다.

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>Enterprise 풀에 대 한 데이터베이스 보고서 생성 및 보기

**풀 보고서를 생성 하려면**

1.  Lync Server 2013를 엽니다.

2.  콘솔 트리에서 포리스트 노드, **엔터프라이즈 풀**을 차례로 확장 한 다음 데이터베이스 보고서를 생성할 풀을 클릭 합니다.

3.  세부 정보 창에서 **데이터베이스** 탭을 클릭 합니다.

4.  **데이터베이스** 탭에서 다음을 수행 합니다.
    
    1.  데이터베이스의 이름을 보려면 **일반 설정을**확장 하 고 데이터베이스 이름을 확인 합니다.
    
    2.  풀에 대 한 현재 사용자 요약 통계를 검색 하려면 **사용자 요약 보고서**를 확장 하 고 **이동을**클릭 한 다음 결과를 확인 합니다.
    
    3.  풀의 단일 사용자에 대 한 현재 사용자별 데이터를 검색 하려면 사용자별 **보고서**를 확장 하 고 사용자의 SIP URI를 입력 한 다음 **이동을**클릭 하 고 결과를 확인 합니다.

풀에 대 한 현재 전화 회의 요약 통계를 검색 하려면 **전화 회의 요약 보고서**를 확장 하 고 **이동을**클릭 한 다음 결과를 확인 합니다.

각 엔터프라이즈 풀에 대해 **관리자는 데이터베이스 탭을** 사용 하 여 데이터베이스 이름을 확인 하 고 데이터베이스에서 보고서를 검색 하 고 볼 수 있습니다.

### <a name="database-reports-and-descriptions"></a>데이터베이스 보고서 및 설명

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>단면</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>사용자 요약 보고서</p></td>
<td><p>Dbanalyze/v/preport: diag [/psqlserver: value]</p>
<p>이 섹션에는 사용 하도록 설정 된 사용자 수, 사용자 당 평균 대화 상대 수 및 특정 기능에 대 한 사용자 수와 같은 풀의 사용자에 대 한 집계 정보가 표시 됩니다.</p>
<p>이러한 보고서를 사용할 때 다음과 같은 정보가 도움이 될 수 있습니다.</p>
<ul>
<li><p>사용 하도록 설정 된 사용자는 Active Directory 사용자 및 컴퓨터 스냅인을 사용 하 여 Lync Server 2013을 사용할 수 있는 사용자입니다.</p></li>
<li><p>활성 사용자는 로그온 하거나 등록 한 사용자입니다.</p></li>
<li><p>요약 보고서에는 연락처에 대 한 통계 정보 집합도 제공 됩니다. 이러한 통계는 적어도 한 번 로그온 한 사용자와 적어도 한 명의 대화 상대에 대해서만 유효 합니다. 따라서 일반적으로 최소 개수의 연락처가 0으로 표시 되지는 않습니다. 이 동작으로 인해 사용자에 게 대화 상대가 없지만 (활성 상태이 고 사용자가 등록 한 경우), 일부 통계 필드의 경우 &lt;비어&gt; 있을 수 있습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>사용자별 보고서</p></td>
<td><p>Dbanalyze/v/preport: disk [/psqlserver: value]</p>
<p>사용자 인구를 초과 하 여 계산 되는 요약 보고서와는 달리, 다음은 특정 사용자에 대 한 보고서입니다.</p></td>
</tr>
<tr class="odd">
<td><p>전화 회의 요약 보고서</p></td>
<td><p>Dbanalyze/v/preport: 회의 [/psqlserver: value]</p>
<p>이 섹션에는 활성 회의 수 및 총 참가자 수와 같은 풀에 대 한 전화 회의 요약 통계에 대 한 집계 정보가 표시 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>대역폭 사용률 분석기 실행

대역폭 사용률 분석기는 엔터프라이즈 네트워크의 WAN 링크에서 UC 끝점에 의해 다양 한 대역폭 소비 보기에 대 한 보고서를 작성 하는 도구입니다. 이러한 보고서를 사용 하 여 현재 대역폭 소비 패턴을 이해 하 고 대역폭 용량 계획에 도움을 받을 수 있습니다. 또한 다양 한 링크에 할당 된 대역폭 용량을 반복 합니다.

이 도구는 다음을 수행 합니다.

  - 네트워크를 통한 오디오 사용에 대 한 특정 보고서 생성

  - 다양 한 링크에 할당 된 대역폭 용량에 대 한 보다 효율적인 용량 계획 및 반복을 지원 합니다.

대역폭 사용률 분석기는 대역폭 용량 및 사용 현황 보고서의 그래픽 플롯을 생성할 수 있습니다. 이러한 작업은 다음과 같습니다.

  - 엔터프라이즈 네트워크의 모든 WAN 링크

  - 선택한 WAN 링크로 필터링 됨

  - 연결 용량을 초과한 WAN 링크로 필터링 됨

  - 프로 비전 된 대역폭을 사용 중 이었던 WAN 링크로 필터링 됨

  - 중요 한 수준에 도달한 WAN 링크로 필터링 (WAN 링크의 대역폭 용량을 90% 초과 하는 대역폭 사용량)

  - WAN 링크 유형 (네트워크-사이트 링크, 인터 지역별 링크 및 사이트 내부의 링크)을 기준으로 필터링 됨

  - 네트워크 지역별로 필터링 됨

이 도구에 대 한 설명서는 [Lync Server 2013 Resource Kit Tools 설명서](http://go.microsoft.com/fwlink/?linkid=623245)에서 제공 됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[주간 작업 검사 목록](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

