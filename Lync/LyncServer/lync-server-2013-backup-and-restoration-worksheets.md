---
title: 'Lync Server 2013: 백업 및 복원 워크시트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af90939e8034c8bf240ec04514a1a30044a14c94
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Lync Server 2013의 백업 및 복원 워크시트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-18_

조직에 대 한 백업 및 복원 계획에는 데이터 및 설정 백업 방법 및 시기에 대 한 세부 정보가 포함 되어야 합니다. 여기에 나와 있는 워크시트를 사용 하 여 특정 배포와 조직의 백업 및 복원 요구 사항에 대 한 정보를 문서화할 수 있습니다.

다음 워크시트를 사용 하 여 Lync Server 풀 또는 Standard Edition Server에 대 한 데이터베이스, 파일 저장소 및 설정 정보를 백업 및 복원 하는 데 필요한 정보를 기록 합니다. Lync Server를 복원 해야 하는 경우에도 쉽게 액세스할 수 있도록 이러한 워크시트의 복사본을 하나 이상 안전한 위치에 보관 합니다.

<div>


> [!NOTE]  
> 이 섹션의 워크시트에는 Lync Server 데이터베이스 및 서버의 데이터와 설정을 복원 하는 데 필요한 정보만 포함 되어 있습니다. 운영 체제 및 기타 소프트웨어를 다시 설치 하기 위한 정보와 같은 기타 복원 정보를 문서화 해야 하는 경우 조직의 배포 계획 및 백업 및 복원 계획을 사용 하 여 이러한 요구 사항을 해결 합니다.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>데이터베이스 백업 및 복원 워크시트

다음 표를 사용 하 여 Lync Server 데이터베이스를 백업 및 복원 하는 데 필요한 정보를 기록 합니다.

### <a name="database-information-for-backup-and-restoration"></a>백업 및 복원에 대 한 데이터베이스 정보

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>데이터베이스</th>
<th>서버 이름 (FQDN)</th>
<th>백업 일정</th>
<th>데이터베이스 백업 도구</th>
<th>백업 집합</th>
<th>백업 대상</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>사용자 데이터에 대 한 백 엔드 서버의 Rtc 데이터베이스</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData</strong> cmdlet</p></td>
<td><p>Name</p>
<p>행사</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>보관 데이터베이스 서버의 LcsLog (기본 이름) 데이터베이스</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 관리 도구</p></td>
<td><p>Name</p>
<p>행사</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>CDRs (통화 정보 레코드)에 대 한 모니터링 데이터베이스 서버의 LcsCdr 데이터베이스</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 관리 도구</p></td>
<td><p>Name</p>
<p>행사</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>QoE (QoEMetrics Quality) 데이터에 대 한 모니터링 데이터베이스 서버의 데이터베이스</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 관리 도구</p></td>
<td><p>Name</p>
<p>행사</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>영구 채팅 데이터베이스</p></td>
<td></td>
<td></td>
<td><p>SQL Server 관리 도구 또는 <strong>export-cspersistentchatdata</strong> cmdlet</p></td>
<td><p>Name</p>
<p>행사</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


다음 데이터베이스에는 백업 또는 복원이 필요 하지 않습니다.

  - Rtcdyn. 이 데이터베이스의 일시적 사용자 데이터는 서비스 복원에 필요 하지 않습니다.

  - Rtcab. 주소록 데이터베이스는 Active Directory 도메인 서비스의 GAL (전체 주소 목록)에서 자동으로 다시 만들어집니다.

  - Rgsdyn.mdf. 이 데이터베이스의 임시 응답 그룹 서비스 데이터는 서비스 복원에 필요 하지 않습니다.

  - Cpsdyn.mdf. 서비스를 복원 하는 데는 통화 대기 응용 프로그램에 대 한 동적 정보가 필요 하지 않습니다.

  - MgcComp. 서비스를 복원 하는 데에는 영구적 채팅에 대 한 준수 데이터베이스를 사용할 필요가 없습니다.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>파일 저장소 백업 및 복원 워크시트

다음 표를 사용 하 여 파일 저장소를 백업 및 복원 하는 데 필요한 정보를 기록 합니다. 파일 저장소에는 모임 콘텐츠 메타 데이터, 모임 준수 로그, 장치 업데이트의 업데이트 로그, 응답 그룹, 통화 대기 및 알림 응용 프로그램에 대 한 오디오 파일 등의 데이터가 포함 됩니다.

### <a name="file-store-information-for-backup-and-restoration"></a>백업 및 복원에 대 한 파일 저장소 정보

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>콘텐츠</th>
<th>서버 이름 (FQDN)</th>
<th>백업 일정</th>
<th>파일 시스템 백업 도구</th>
<th>백업할 파일 공유 *</th>
<th>백업 대상</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 파일 저장소</p></td>
<td></td>
<td></td>
<td><p>표준 백업 도구 (예: Robocopy)</p></td>
<td><p>Enterprise Edition 용 파일 서버 Standard edition 배포의 경우 기본적으로 스탠더드 버전을 기반으로 합니다. 일반적으로 사이트별로 하나씩 있습니다.</p></td>
<td></td>
<td><p>이름이 <strong>Meeting.Active</strong>인 파일은 백업해서는 안됩니다. 이 파일은 사용 중 이며 모임이 진행 되는 동안 잠깁니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>설정 백업 및 복원 워크시트

다음 표를 사용 하 여 설정을 백업 및 복원 하는 데 필요한 정보를 기록 합니다.

### <a name="settings-information-for-backup-and-restoration"></a>백업 및 복원에 대 한 설정 정보

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>데이터베이스</th>
<th>서버 이름 (FQDN)</th>
<th>백업 일정</th>
<th>백업 도구</th>
<th>구성 파일 (.xml) 이름</th>
<th>백업 위치</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>토폴로지 구성에 대 한 중앙 관리 저장소의 Xds 데이터베이스 (전역)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration</strong> cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>E9-1-1 위치 정보에 대 한 중앙 관리 저장소의 Lis 데이터베이스 (전역)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-cslisconfiguration</strong> cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>응답 그룹 구성 (풀)을 위해 백 엔드 서버의 RgsConfig 데이터베이스</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-csrgsconfiguration</strong> cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

