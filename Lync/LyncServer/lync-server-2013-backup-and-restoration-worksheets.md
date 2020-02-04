---
title: 'Lync Server 2013: 워크시트 백업 및 복원'
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
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Lync Server 2013의 워크시트 백업 및 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-18_

조직의 백업 및 복원 계획에는 데이터 및 설정 백업 방법 및 시기에 대 한 세부 정보가 포함 되어야 합니다. 여기에 표시 된 워크시트를 사용 하 여 특정 배포에 대 한 정보를 문서화 하 고 조직의 백업 및 복원 요구 사항을 확인할 수 있습니다.

다음 워크시트를 사용 하 여 Lync Server 풀 또는 Standard Edition Server의 데이터베이스, 파일 저장소 및 설정 정보를 백업 하 고 복원 하는 데 필요한 정보를 기록 합니다. 이러한 워크시트의 복사본 하나 이상을 안전한 위치에 보관 하 여 Lync Server를 복원 해야 하는 경우 쉽게 액세스할 수 있도록 합니다.

<div>


> [!NOTE]  
> 이 섹션의 워크시트는 Lync Server 데이터베이스 및 서버의 데이터 및 설정을 복원 하는 데 필요한 정보만 다룹니다. 운영 체제 및 기타 소프트웨어를 다시 설치 하기 위한 정보와 같은 다른 복원 정보를 문서화 해야 하는 경우 조직의 배포 계획 및 백업 및 복원 계획을 사용 하 여 이러한 요구 사항을 해결 합니다.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>데이터베이스 백업 및 복원 워크시트

다음 표를 사용 하 여 Lync Server 데이터베이스를 백업 하 고 복원 하는 데 필요한 정보를 기록 합니다.

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
<th>데이터</th>
<th>서버 이름 (FQDN)</th>
<th>백업 일정</th>
<th>데이터베이스 백업 도구</th>
<th>백업 집합</th>
<th>백업 대상</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>백 엔드 서버의 사용자 데이터에 대 한 Rtc 데이터베이스</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData</strong> cmdlet</p></td>
<td><p>성을</p>
<p>기간이</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>보관 데이터베이스 서버의 LcsLog (기본 이름) 데이터베이스</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 관리 도구</p></td>
<td><p>성을</p>
<p>기간이</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>CDRs (호출 정보 레코드)에 대 한 모니터링 데이터베이스 서버의 LcsCdr 데이터베이스</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 관리 도구</p></td>
<td><p>성을</p>
<p>기간이</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>환경 품질 (체감 품질) 데이터를 모니터링 하는 데이터베이스 서버의 QoEMetrics 데이터베이스</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 관리 도구</p></td>
<td><p>성을</p>
<p>기간이</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>영구 채팅 데이터베이스</p></td>
<td></td>
<td></td>
<td><p>SQL Server 관리 도구 또는 <strong>Export-CsPersistentChatData</strong> cmdlet</p></td>
<td><p>성을</p>
<p>기간이</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


백업 또는 복원에는 다음 데이터베이스가 필요 하지 않습니다.

  - Rtcdyn. 이 데이터베이스의 임시 사용자 데이터는 서비스 복원에 필요 하지 않습니다.

  - Rtcab. 주소록 데이터베이스는 Active Directory 도메인 서비스의 GAL (전체 주소 목록)에서 자동으로 다시 만들어집니다.

  - Rgsdyn. 이 데이터베이스의 임시 응답 그룹 서비스 데이터는 서비스 복원에 필요 하지 않습니다.

  - Cpsdyn. 통화 공원 응용 프로그램에 대 한 동적 정보는 서비스 복원에 필요 하지 않습니다.

  - MgcComp. 서비스 복원에는 영구 채팅에 대 한 규정 준수 데이터베이스가 필요 하지 않습니다.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>파일 저장소 백업 및 복원 워크시트

다음 표를 사용 하 여 파일 저장소를 백업 하 고 복원 하는 데 필요한 정보를 기록 합니다. 파일 저장소에는 모임 콘텐츠 메타 데이터, 모임 준수 로그, 장치 업데이트에 대 한 업데이트 로그, 응답 그룹, 통화 공원, 알림 응용 프로그램에 대 한 오디오 파일 등의 데이터가 포함 됩니다.

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
<th>콘텐트가</th>
<th>서버 이름 (FQDN)</th>
<th>백업 일정</th>
<th>파일 시스템 백업 도구</th>
<th>백업할 파일 공유 *</th>
<th>백업 대상</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 파일 저장소</p></td>
<td></td>
<td></td>
<td><p>Robocopy와 같은 표준 백업 도구</p></td>
<td><p>Enterprise Edition 용 파일 서버. 스탠더드 버전 배포의 경우 Standard Edition에서 기본적으로 설정 되어 있습니다. 일반적으로 사이트당 하나입니다.</p></td>
<td></td>
<td><p>이름이 <strong>Meeting</strong> 인 파일은 백업 하지 않아야 합니다. 이러한 파일은 사용 중 이며 모임이 진행 되는 동안 잠깁니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>설정 백업 및 복원 워크시트

다음 표를 사용 하 여 설정을 백업 하 고 복원 하는 데 필요한 정보를 기록 합니다.

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
<th>데이터</th>
<th>서버 이름 (FQDN)</th>
<th>백업 일정</th>
<th>백업 도구</th>
<th>구성 파일 (.xml) 이름</th>
<th>백업 위치</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>토폴로지 구성 (전역) 용 중앙 관리 저장소의 Xds 데이터베이스</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration</strong> cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>E9 용 중앙 관리 저장소의 Lis 데이터베이스-1-1 위치 정보 (전역)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsLisConfiguration</strong> cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>RgsConfig에서 응답 그룹 구성 (풀)에 대 한 백 엔드 서버의 데이터베이스</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsRgsConfiguration</strong> cmdlet</p></td>
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

