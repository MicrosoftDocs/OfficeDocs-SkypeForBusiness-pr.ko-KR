---
title: 'Lync Server 2013: 백업 및 복원 요구 사항: 도구 및 사용 권한'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5e4ce57e61be50bfd1e2a78529830b4a40e3ed
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Lync Server 2013의 백업 및 복원 요구 사항: 도구 및 사용 권한

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-17_

이 항목에서는 Lync Server 2013을 백업 하 고 복원 하는 데 사용할 수 있는 도구, 필요한 사용 권한, 명령을 원격으로 실행할 수 있는지 아니면 로컬로 실행할지에 대해 설명 합니다. 이 항목에서는 백업 및 복원을 위해 Lync Server와 함께 제공 되는 도구에 중점을 둔 것입니다.

<div>

## <a name="backups"></a>해결할

Lync Server를 백업 하려면 다음 표에서 확인 된 도구를 사용 합니다. Lync Server를 백업 하는 데 필요한 모든 명령을 스크립팅할 수 있으며 원격으로 실행할 수 있습니다.

### <a name="tools-for-backing-up-lync-server"></a>Lync Server 백업 도구

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>백업 하려면 다음을 실행 합니다.</th>
<th>이 도구 또는 cmdlet 사용:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>토폴로지 구성 데이터 (Xds)</p></td>
<td><p>수출-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>위치 정보 서비스 (E9-1-1) 데이터 (Lis .mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>응답 그룹 구성 데이터 (RgsConfig)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>영구 사용자 데이터 (Rtcxds 데이터베이스)</p>
<p>컨퍼런스 Id</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>보관 데이터베이스 (LcsLog. .mdf)</p></li>
<li><p>통화 정보 기록 데이터베이스 (LcsCDR) 모니터링</p></li>
<li><p>체감 품질 데이터베이스 모니터링 (QoEMetrics)</p></li>
</ul></td>
<td><p>Sql Server Management Studio와 같은 SQL Server 데이터베이스 도구</p></td>
</tr>
<tr class="even">
<td><p>Mgc .mdf (영구 채팅 데이터베이스)</p></td>
<td><p>SQL Server 백업 절차 또는 내보내기-CsPersistentChatData. Export-CsPersistentChatData는 영구 채팅 데이터를 파일로 내보냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>모든 파일 저장소: Lync Server 파일 저장소, 보관 파일 저장소</p>
<div>

> [!NOTE]  
> 이름이 <STRONG>Meeting</STRONG> 인 파일은 백업 하지 않아야 합니다. 모임이 진행 되는 동안 이러한 파일은 사용 중이거나 잠겨 있습니다.


</div></td>
<td><p>표준 파일 시스템 관리 도구 (예: Robocopy)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>복원이

Lync Server를 복원 하려면 다음 표의 도구를 사용 합니다. Lync Server를 복원 하는 데 필요한 모든 명령을 스크립팅할 수 있습니다. 일부는 원격으로 실행할 수 있지만, 다음 표에 지정 된 대로 로컬에서 실행 해야 합니다.

### <a name="tools-for-restoring-lync-server"></a>Lync Server 복원 도구

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>실행할 작업:</th>
<th>이 도구 또는 cmdlet 사용:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>신규 또는 깨끗 한 컴퓨터 빌드</p></td>
<td><ul>
<li><p>Windows 운영 체제 설치 소프트웨어</p></li>
<li><p>SQL Server 설치 소프트웨어</p></li>
<li><p>인증서를 내보낼 수 있는 개인 키를 사용 하 여 복원 하는 경우 MMC (Microsoft Management Console) 스냅인</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>파일 저장소 데이터 복원</p></td>
<td><p>표준 파일 시스템 관리 도구 (예: Robocopy)</p></td>
</tr>
<tr class="odd">
<td><p>빈 데이터베이스를 다시 만들고 다음에 대 한 사용 권한을 설정 합니다.</p>
<ul>
<li><p>중앙 관리 저장소</p></li>
<li><p>백 엔드 서버</p></li>
<li><p>모니터링 데이터베이스</p></li>
<li><p>보관 데이터베이스</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 도메인 서비스 포인터를 중앙 관리 저장소에 복원</p>
<div>

> [!NOTE]  
> 언제 든 지 서비스 연결 지점을 잃어버린 경우이 cmdlet을 다시 실행할 수 있습니다.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>토폴로지, 정책 및 구성 설정을 중앙 관리 저장소 (Xds)로 가져오기</p></td>
<td><p>가져오기-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>토폴로지 게시 및 설정</p></td>
<td><p>토폴로지 작성기</p>
<p>또는</p>
<p>게시-CsTopology 및 Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>마지막으로 게시 된 토폴로지 사용</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 구성 요소 다시 설치</p></td>
<td><p>Lync Server 설정</p>
<div>

> [!NOTE]  
> Lync Server 설치 폴더 또는 \setup\amd64\Setup.exe. 미디어에 위치


</div></td>
</tr>
<tr class="odd">
<td><p>위치 정보 (E9-1-1) 데이터 (Lis .mdf) 복원</p></td>
<td><p>가져오기-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>영구 사용자 데이터 (Rtcxds) 복원</p></td>
<td><p>가져오기-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>응답 그룹 구성 데이터 (RgsConfig) 복원</p></td>
<td><p>가져오기-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> 데이터베이스에 응답 그룹 데이터가 없는 새로 배포 된 풀에서 구성을 복원 하는 경우 – OverwriteOwner 옵션을 사용 해야 합니다. 복원 하려는 데이터가 FQDN (정규화 된 도메인 이름)을 가진 풀에 있는 경우에도이 옵션을 사용 합니다. 그렇지 않으면 Active Directory에 이미 존재 하는 응답 그룹에 대 한 contact 개체 때문에 가져오기가 성공 하지 못합니다.


</div></td>
</tr>
<tr class="even">
<td><p>다음 데이터베이스를 복원 합니다.</p>
<ul>
<li><p>보관 데이터베이스 (LcsLog. .mdf)</p></li>
<li><p>데이터베이스 모니터링: 통화 세부 레코드 데이터베이스 (LcsCDR) 및 체감 품질 database (QoEMetrics)</p></li>
</ul></td>
<td><p>SQL Server 데이터베이스 관리 도구</p></td>
</tr>
<tr class="odd">
<td><p>Mgs mdf (영구 채팅 데이터베이스)</p></td>
<td><p>SQL Server 복원 절차 또는 가져오기-CsPersistentChatData. Export-CsPersistentChatData를 사용 하 여 만든 파일과 함께 CsPersistentChatData를 사용할 수 있으며, 데이터를 영구 채팅 데이터베이스로 가져옵니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>필요한 권한

이 항목에 설명 된 모든 명령을 수행 하려면 사용자가 **RTCUniversalServerAdmins** 그룹의 구성원 이어야 합니다. 대부분의 백업 및 복원 명령은 역할 기반 액세스 제어 (RBAC)를 지원 하지 않습니다. 두 가지 예외는 CsPersistentChatAdministrator 그룹의 구성원 인 사용자가 실행 해야 하는 영구 채팅 cmdlet 내보내기-CsPersistentChatData 및 가져오기-CsPersistentChatData입니다. Lync Server 배포 마법사를 실행 하려면 사용자도 로컬 관리자 그룹의 구성원 이어야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

