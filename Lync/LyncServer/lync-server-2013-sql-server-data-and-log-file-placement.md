---
title: 'Lync Server 2013: SQL Server 데이터 및 로그 파일 배치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a528ba7a348ebb5c8f865a795f8b1f1c1bc30cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Lync Server 2013에 대한 SQL Server 데이터 및 로그 파일 배치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

Lync Server 2013 프런트 엔드 풀에 대 한 Microsoft SQL Server 2012 또는 Microsoft SQL Server 2008 R2 SP1을 계획 하 고 배포 하는 동안 성능에 대 한 데이터 및 로그 파일을 실제 하드 디스크에 배치 하는 것이 중요 한 고려 사항입니다. 권장 되는 디스크 구성은 6 개 스핀 들을 사용 하 여 1 + 0 RAID 집합을 구현 하는 것입니다. Lync Server를 사용 하 여 RAID 드라이브 집합에 대 한 프런트 엔드 풀 및 연결 된 서버 역할 및 서비스 (즉, 보관 및 모니터링 서버, Lync Server 응답 그룹 서비스, Lync Server 통화 공원 서비스)에 사용 되는 모든 데이터베이스 및 로그 파일을 배치할 수 있습니다. 배포 마법사는 좋은 성능을 위해 테스트 된 구성을 생성 합니다. 데이터베이스 파일과 이러한 파일의 역할은 다음 표에 자세히 설명 되어 있습니다.

<div>


> [!NOTE]  
> 정책 및 SQL Server 구성에 더 특별 한 설치가 필요한 경우 Lync Server Management Shell을 사용 하 여 데이터베이스 및 로그 파일을 미리 정의 된 위치에 설치할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Lync server 2013에서 Lync Server Management Shell을 사용 하 여 데이터베이스 설치</A> 를 참조 하세요.



</div>

### <a name="data-and-log-files-for-central-management-store"></a>중앙 관리 저장소에 대 한 데이터 및 로그 파일

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>중앙 관리 저장소 데이터베이스 파일</th>
<th>데이터 파일 또는 로그 용도</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds</p></td>
<td><p>중앙 관리 저장소의 트랜잭션 로그 파일</p></td>
</tr>
<tr class="even">
<td><p>Xds .mdf</p></td>
<td><p>토폴로지 작성기에서 정의 하 고 게시 한 현재 Lync Server 2013 토폴로지의 구성을 유지 관리 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>Lis. .mdf</p></td>
<td><p>위치 정보 서비스 데이터 파일</p></td>
</tr>
<tr class="even">
<td><p>Lis</p></td>
<td><p>위치 정보 서비스 데이터 파일에 대 한 트랜잭션 로그</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>사용자, 회의 및 주소록에 대 한 데이터 및 로그 파일

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>핵심 Lync Server 2013 데이터베이스 파일</th>
<th>데이터 파일 또는 로그 용도</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc</p></td>
<td><p>영구 사용자 데이터 (예: Acl (액세스 제어 목록), 연락처, 예약 된 회의)</p></td>
</tr>
<tr class="even">
<td><p>Rtc</p></td>
<td><p>Rtc 데이터에 대 한 트랜잭션 로그</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn</p></td>
<td><p>임시 사용자 데이터 (현재 상태 런타임 데이터)를 유지 합니다.</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn</p></td>
<td><p>Rtcdyn 데이터에 대 한 트랜잭션 로그</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab .mdf</p></td>
<td><p>RTC (실시간 통신) 주소록 데이터베이스는 주소록 서비스 정보가 저장 되는 SQL Server 리포지토리입니다.</p></td>
</tr>
<tr class="even">
<td><p>Rtcab. i a .ldf</p></td>
<td><p>주소록 서비스에 대 한 트랜잭션 로그</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal</p></td>
<td><p>회의 디렉터리를 호스팅합니다.</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds</p></td>
<td><p>사용자 데이터에 대 한 백업 유지 관리</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds</p></td>
<td><p>Rtcxds 데이터에 대 한 트랜잭션 로그</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>통화 공원 및 응답 그룹에 대 한 데이터 및 로그 파일

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>응용 프로그램 데이터베이스</th>
<th>데이터 파일 또는 로그 용도</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn</p></td>
<td><p>통화 공원 응용 프로그램에 대 한 동적 정보 데이터베이스</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn</p></td>
<td><p>통화 공원 응용 프로그램 데이터 파일에 대 한 트랜잭션 로그</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig</p></td>
<td><p>서비스 구성에 대 한 Lync Server 응답 그룹 서비스 데이터 파일</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig</p></td>
<td><p>응답 그룹 응용 프로그램 구성에 대 한 트랜잭션 로그 파일</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn</p></td>
<td><p>런타임 작업에 대 한 응답 그룹 서비스 데이터 파일</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn</p></td>
<td><p>응답 그룹 서비스 런타임 데이터 파일에 대 한 트랜잭션 로그</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>보관 및 모니터링 서버에 대 한 데이터 및 로그 파일

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>데이터베이스 파일 보관 및 모니터링</th>
<th>데이터 파일 또는 로그 용도</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr</p></td>
<td><p>모니터링 서버의 CDR (통화 정보 기록) 프로세스에 대 한 데이터 저장소</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr</p></td>
<td><p>CDR (통화 정보 기록) 데이터에 대 한 트랜잭션 로그</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics</p></td>
<td><p>모니터링 서버에서 저장 된 환경 데이터 파일의 품질</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics</p></td>
<td><p>데이터 모니터링에 대 한 트랜잭션 로그</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog .mdf</p></td>
<td><p>보관 서버에서 인스턴트 메시지 및 회의 데이터 보존을 위한 데이터 파일</p></td>
</tr>
<tr class="even">
<td><p>Lcslog. .ldf</p></td>
<td><p>데이터 보관을 위한 트랜잭션 로그</p></td>
</tr>
</tbody>
</table>


이 항목에서는 디스크와 RAID 집합에 대 한 참조를 생성 합니다. SQL Server 리소스의 구성에서 디스크를 참조 하는 것은 단일 하드웨어 장치를 의미 한다는 점에 유의 하세요. 두 개의 파티션, 그리고 데이터 파일을 보유 하 고 있는 다른 파티션이 포함 된 하드 디스크 드라이브는 두 개의 디스크와 동일 하지 않으며, 각각 로그 또는 데이터 파일에 대 한 전용 복사본입니다.

RAID 집합에 대 한 참조에는 다양 한 공급 업체의 여러 가지 RAID 기술이 있습니다. 그리고 SAN (storage area networks)의 확산으로 단일 시스템 전용 RAID 집합은 rarer입니다. Lync Server 2013를 사용 하 여 SQL Server 성능을 구성할 때 디스크 레이아웃에 적합 한 구성을 확인 하려면 RAID 또는 SAN 공급 업체에 문의 해야 합니다.

또한 모든 디스크 드라이브가 동등 하 게 만들어지지 않은 것을 참고 하십시오. 일부는 다른 방법 보다 성능이 더 좋습니다. 동일한 제조업체의 드라이브 조차도 회전 속도, 하드웨어 캐시 크기 및 기타 요인 때문에 성능이 다를 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

