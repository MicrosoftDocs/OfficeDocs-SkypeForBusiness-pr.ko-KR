---
title: 'Lync Server 2013: 작업 종속성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ef9959f48c085ad4f5f28f182b86442ebec8c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Lync Server 2013의 운영 의존 관계

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-05-15_

이 문서에서 설명 하는 참조 아키텍처는 조직의 요구 사항에 맞게 크기를 조정 하는 것이 아니라 Microsoft의 모범 사례에 따라 설계 되는 Lync Server 2013 배포를 유지 하는 데 도움이 됩니다. Lync Server 2013 구현이 동적인 서비스 이며 엔터프라이즈의 다른 서비스와 마찬가지로 비즈니스에 높은 수준의 서비스 사용 및 서비스 품질을 유지 하기 위해서는 계속 모니터링 및 사전 관리가 필요 합니다.

조직의 일상 비즈니스에서 Lync Server 2013을 깊이 있게 사용할 수 있으므로 정확한 서비스 수준 관리를 통해 서비스를 관리 하는 것이 중요 합니다. Lync 시스템 아키텍처는 복잡 하 고 매우 통합 될 수 있으며, 효과적인 서비스 수준 관리를 유지 관리 하 고 Lync Server 2013에 대 한 Sla를 설정 하려면 다른 플랫폼 및 서버에 대 한 시스템 종속성을 이해 하는 것이 중요 합니다. 중요 한 것은 음성 및 UC 통합 응용 프로그램과 같은 비즈니스 서비스가 Lync에 의존 하는 것을 확인 하는 것입니다.

모든 해당 종속성에 대해 설명 하는 Lync Server 2013을 설정 해야 합니다. 서비스 맵을 사용 하 여 Lync와 해당 종속 서비스 간의 SLA를 공식화 하 고 SLA 협상이 시작 되는 위치를 제공할 수 있습니다.

다음 표에서는 Lync 인프라에 대 한 일반적인 종속성 서비스를 보여 줍니다. 이러한 각 기술에는 자체적인 사전 모니터링이 필요 합니다.

### <a name="typical-dependency-services"></a>일반적인 종속성 서비스

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>종속성 서비스</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>운영 체제</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>서버 하드웨어</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Active Directory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>공개 키 인프라</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>도메인 이름 지정 서비스</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>데이터베이스 서비스</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>저장소 서비스</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>시스템 관리 – 모니터링 및 배포</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>보안 서비스-바이러스 백신</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>네트워크 인프라-인터넷</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>네트워크 인프라 – 내부용 (LAN/WAN)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>전화 통신 인프라 – IP PBX 및 게이트웨이</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>클라우드 서비스</p></td>
<td></td>
</tr>
</tbody>
</table>


이는 MOF에 규정 된 변경, 사고, 릴리스 관리 등의 기본 서비스 수준 관리 기능을 operationally 하는 것으로 가정 합니다. Lync 솔루션은 이러한 기능을 통해 채택 하 고 동일한 운영 관리 프로세스를 따릅니다.

위의 정보를 작성 하면 이제 기업에서 Lync 서비스에 영향을 미칠 수 있는 사항에 대 한 이해가 더욱 향상 되었습니다. Lync Server 2013 서비스 가용성 및 품질을 보장 하기 위해 다음 모니터링 도구는 참조 아키텍처 배포와 함께 제공 되어야 합니다.

### <a name="monitoring-tools"></a>모니터링 도구

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>요소가</th>
<th>설명</th>
<th>해당 사이트</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 모니터링 서버</p></td>
<td><p>중앙 사이트별로 하나 이상의 Lync Server 2013 모니터링 서버 역할을 배포 하 고 환경 품질 (체감 품질) 보고 팩을 구성 합니다.</p>
<p>자세한 내용은 Lync Server 2013 배포 설명서를 참조 하세요.</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Lync Server 2013에서 모니터링 배포</a></p></td>
<td><p>중앙 사이트</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>각 풀을 모니터링 서버 역할의 가장 가까운 인스턴스로 합니다.</p></td>
<td><p>중앙 사이트</p>
<p>지점 사이트</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>Microsoft Lync Server 2013 관리 팩 (MP)이 있는 System Center Operations Manager 2012.</p>
<p>관리 팩은 기존 이벤트 로그 및 성능 카운터 기반 계측을 구현 하는 것은 물론 Lync Server 2013에서 새로 사용할 수 있는 계측 기능을 사용 하도록 설정 합니다.</p></td>
<td><p>중앙 사이트</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>모니터링 해야 하는 역할 및 구성 요소 검색에 대 한 중앙 검색이 중앙 관리 데이터베이스에 게시 된 토폴로지 문서를 읽는 중앙 검색 스크립트를 기반으로 자동으로 완료 되는지 확인 합니다.</p></td>
<td><p>중앙 사이트</p>
<p>지점 사이트</p>
<p>Edge 사이트</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Lync Server를 실행 하는 모든 배포 서버에 시스템 센터 Operations Manager 2007 에이전트를 배포 합니다.</p></td>
<td><p>중앙 사이트</p>
<p>지점 사이트</p>
<p>Edge 사이트</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>알림을 위해 우선 순위가 지정 된 경고가 구성 되어 있는지 확인 합니다.</p>
<p>우선 순위가 높은 알림</p>
<p>보통 우선 순위 알림</p>
<p>다른 알림.</p></td>
<td><p>중앙 사이트</p>
<p>지점 사이트</p>
<p>Edge 사이트</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>배포에 대 한 포트 모니터링을 구성 합니다.</p></td>
<td><p>중앙 사이트</p>
<p>지점 사이트</p>
<p>Edge 사이트</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>배포에 대 한 URL 모니터링 구성</p></td>
<td><p>중앙 사이트</p></td>
</tr>
<tr class="odd">
<td><p>Lync 및 System Center Operations Manager 통합</p></td>
<td><p>통화 안정성 및 미디어 품질 MonitoringCall 안정성 및 미디어 품질 모니터링 모니터링 서버 컴퓨터를 감시자 노드로 사용 하 여 Lync Server의 통화 안정성 및 미디어 품질을 모니터링 합니다. 이러한 두 가지 기능은 모두 모니터링 서버 데이터베이스를 쿼리하여 분석을 수행 합니다.</p></td>
<td><p>중앙 사이트</p>
<p>지점 사이트</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>미디어 품질 경고 임계값이 정확 하 게 구성 되어 있는지 확인 합니다. 다음 표에는 코덱의 최대 네트워크 의미 성적 점수가 표시 되어 있습니다. 프로덕션에서 이러한 점수는 설정 된 기간 동안 모니터링 되어야 하며, 허용 되는 임계값은 조직별 NMOS 성적을 기준으로 설정 해야 합니다.</p></td>
<td><p>중앙 사이트</p>
<p>지점 사이트</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 가상 트랜잭션 감시자</p></td>
<td><p>가상 트랜잭션 감시자가 되도록 전용 Lync 서버를 배포 합니다.</p>
<p>종합 트랜잭션은 미리 정의 된 간격으로 관리 팩에 의해 자동으로 트리거되는 Lync Server 2013 Windows PowerShell cmdlet입니다. 이는 각 풀에 대 한 STs의 검색 및 실행을 담당 하는 관리자 지정 서버인 가상 트랜잭션 감시자 노드에서 실행 됩니다.</p>
<p>기존 Microsoft Lync Server 2013 서버를 가상 트랜잭션 감시자 노드로 사용 하지 않는 것이 좋습니다. STs 실행에 대 한 CPU/메모리 사용량 요구 사항 때문입니다. 가상 트랜잭션 감시자 노드에 새 서버 컴퓨터 (또는 가상 서버)를 사용 합니다.</p></td>
<td><p>중앙 사이트</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>종합 트랜잭션 감시자 노드 배포</p>
<p>문서의 MonitoringCS_withSCOM .docx 문서 연결 문서 탭을 참조 하세요.</p></td>
<td><p>중앙 사이트</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>코덱 당 최대 네트워크 SPECIALIST 점수

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>시나리오</th>
<th>코덱이나</th>
<th>Max NMOS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC-UC 통화</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4.10</p></td>
</tr>
<tr class="even">
<td><p>UC-UC 통화</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2.95</p></td>
</tr>
<tr class="odd">
<td><p>컨퍼런스 통화</p></td>
<td><p>사이렌</p></td>
<td><p>3.72</p></td>
</tr>
<tr class="even">
<td><p>UC-PSTN 통화</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2.95</p></td>
</tr>
<tr class="odd">
<td><p>UC-PSTN 통화</p></td>
<td><p>G-711</p></td>
<td><p>3.61</p></td>
</tr>
</tbody>
</table>


이전 pro 활성 모니터링 작업을 진행 하는 동안에는 Lync RA 작업 가이드에 정의 된 대로 매일, 매주, 매월의 중앙, 주 및 지사 사이트에 대 한 유지 관리 작업을 실행 해야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

