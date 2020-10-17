---
title: 'Lync Server 2013: 백업 및 복원 요구 사항: 도구 및 사용 권한'
description: 'Lync Server 2013: 백업 및 복원 요구 사항: 도구 및 사용 권한'
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
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553474"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Lync Server 2013의 백업 및 복원 요구 사항: 도구 및 사용 권한

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-17_

이 항목에서는 Lync Server 2013을 백업 및 복원 하는 데 사용할 수 있는 도구, 필요한 권한, 원격 또는 로컬로 명령을 실행할 수 있는지 여부에 대해 설명 합니다. 특히이 항목에서는 백업 및 복원을 위해 Lync Server와 함께 제공 되는 도구에 대해 중점적으로 설명 합니다.

<div>

## <a name="backups"></a>백업

Lync Server를 백업 하려면 다음 표에서 확인 된 도구를 사용 합니다. Lync Server를 백업 하는 데 필요한 모든 명령을 스크립트로 작성 하 고 원격으로 실행할 수 있습니다.

### <a name="tools-for-backing-up-lync-server"></a>Lync Server 백업 도구

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>백업할 항목:</th>
<th>사용할 도구 또는 cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>토폴로지 구성 데이터(Xds.mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>위치 정보 서비스(E9-1-1) 데이터(Lis.mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>응답 그룹 구성 데이터(RgsConfig.mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>영구 사용자 데이터 (Rtcxds 데이터베이스)</p>
<p>전화 회의 ID</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>보관 데이터베이스(LcsLog.mdf)</p></li>
<li><p>통화 정보 기록 모니터링 데이터베이스(LcsCDR.mdf)</p></li>
<li><p>QoE 모니터링 데이터베이스(QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>SQL Server 데이터베이스 도구(예: SQL Server Management Studio)</p></td>
</tr>
<tr class="even">
<td><p>영구 채팅 데이터베이스 (Mgc .mdf)</p></td>
<td><p>SQL Server 백업 절차 또는 내보내기-Export-cspersistentchatdata. Export-CsPersistentChatData 영구 채팅 데이터를 파일로 내보냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>모든 파일 저장소: Lync Server 파일 저장소, 보관 파일 저장소</p>
<div>

> [!NOTE]  
> 이름이 <STRONG>Meeting.Active</STRONG>인 파일은 백업해서는 안됩니다. 이러한 파일은 사용 중이며 모임이 수행되는 동안 잠깁니다.


</div></td>
<td><p>표준 파일 시스템 관리 도구 (예: Robocopy)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>복구할

Lync Server를 복원 하려면 다음 표의 도구를 사용 합니다. Lync Server를 복원 하는 데 필요한 모든 명령을 스크립팅할 수 있습니다. 일부는 원격으로 실행할 수 있지만 다음 표에 지정 된 대로 로컬로 실행 해야 합니다.

### <a name="tools-for-restoring-lync-server"></a>Lync Server 복원 도구

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>수행할 작업:</th>
<th>사용할 도구 또는 cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>신규 또는 깨끗한 컴퓨터 구축</p></td>
<td><ul>
<li><p>Windows 운영 체제 설치 소프트웨어</p></li>
<li><p>SQL Server 설치 소프트웨어</p></li>
<li><p>내보낼 수 있는 개인 키를 사용하여 인증서를 복원할 경우 MMC(Microsoft Management Console) 스냅인 인증</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>파일 저장소 데이터 복원</p></td>
<td><p>표준 파일 시스템 관리 도구(예: Robocopy)</p></td>
</tr>
<tr class="odd">
<td><p>빈 데이터베이스를 다시 만들고 다음에 대한 권한을 설정합니다.</p>
<ul>
<li><p>Central Management store</p></li>
<li><p>백 엔드 서버</p></li>
<li><p>모니터링 데이터베이스</p></li>
<li><p>보관 데이터베이스</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 도메인 서비스 포인터를 중앙 관리 저장소로 복원</p>
<div>

> [!NOTE]  
> 언제라도 서비스 연결 지점이 손실될 경우 이 cmdlet을 다시 실행할 수 있습니다.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>토폴로지, 정책 및 구성 설정을 중앙 관리 저장소 (Xds)로 가져오기</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>토폴로지 게시 및 사용</p></td>
<td><p>토폴로지 작성기</p>
<p>또는</p>
<p>Publish-CsTopology 및 Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>마지막으로 게시된 토폴로지 사용</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 구성 요소 다시 설치</p></td>
<td><p>Lync Server 설치</p>
<div>

> [!NOTE]  
> Lync Server 설치 폴더 또는 \setup\amd64\Setup.exe 미디어에 있습니다.


</div></td>
</tr>
<tr class="odd">
<td><p>위치 정보(E9-1-1) 데이터(Lis.mdf) 복원</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>영구 사용자 데이터 복원 (Rtcxds)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>응답 그룹 구성 데이터 복원(RgsConfig.mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> 데이터베이스에 응답 그룹 데이터가 없는 새로 배포 된 풀에서 구성을 복원 하는 경우 – OverwriteOwner 옵션을 사용 해야 합니다. 복원 중인 데이터가 FQDN (정규화 된 도메인 이름)을 가진 풀에 있더라도이 옵션을 사용 합니다. 그렇지 않으면 연락처 개체가 Active Directory에 이미 있는 응답 그룹으로 인해 가져오기가 완료 되지 않습니다.


</div></td>
</tr>
<tr class="even">
<td><p>다음 데이터베이스 복원:</p>
<ul>
<li><p>보관 데이터베이스(LcsLog.mdf)</p></li>
<li><p>모니터링 데이터베이스: 통화 정보 기록 데이터베이스(LcsCDR.mdf) 및 QoE 데이터베이스(QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>SQL Server 데이터베이스 관리 도구</p></td>
</tr>
<tr class="odd">
<td><p>영구 채팅 데이터베이스 (Mgs .mdf)</p></td>
<td><p>SQL Server 복원 절차 또는 가져오기-Export-cspersistentchatdata. Export-cspersistentchatdata에서 만든 파일을 사용 하 여 Import-CsPersistentChatData를 사용할 수 있으며 데이터를 영구 채팅 데이터베이스로 가져오게 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>필요한 사용 권한

이 항목에서 설명 하는 모든 명령을 수행 하려면 사용자가 **RTCUniversalServerAdmins** 그룹의 구성원 이어야 합니다. 대부분의 백업 및 복원 명령은 RBAC (역할 기반 액세스 제어)를 지원 하지 않습니다. 두 가지 예외는 CsPersistentChatAdministrator 그룹의 구성원 인 사용자가 실행 해야 하는 영구 채팅 cmdlet Export-CsPersistentChatData 및 Export-cspersistentchatdata입니다. Lync Server 배포 마법사를 실행 하려면 사용자가 로컬 관리자 그룹의 구성원 이기도 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

