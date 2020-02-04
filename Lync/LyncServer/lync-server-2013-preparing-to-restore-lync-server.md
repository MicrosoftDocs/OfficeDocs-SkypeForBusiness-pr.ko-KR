---
title: 'Lync Server 2013: Lync Server 복원 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2e6516ee1162c02f2bebc8c385c2f41e87d7781
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Lync Server 2013 복원 준비

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

오류가 발생 한 후에 서버와 데이터베이스 복원을 시작 하기 전에 다음 사항을 확인 해야 합니다.

  - 복원 해야 할 사항.

  - 복원에 필요한 하드웨어, 소프트웨어, 데이터, 도구입니다.

<div>

## <a name="determining-what-to-restore"></a>복원할 항목 결정

이 항목에서는 서버, 풀 또는 중앙 관리 저장소 수준에서 발생 하는 Lync Server 중단을 복원 하는 방법에 대해 설명 합니다. 중앙 관리 저장소에 오류가 발생 하는 경우 Lync Server 배포는 계속 작동 하지만 구성을 변경할 수는 없습니다. 백 엔드 서버 또는 Standard Edition 서버에 오류가 발생 하면 사용자 풀이 작동을 중지 합니다. 다른 서버에 오류가 발생 한 경우 서버의 실행 되는 서버 역할 및 서버에서 하나 이상의 데이터베이스를 호스트 하는지 여부에 따라 오류가 발생 합니다.

### <a name="what-to-restore"></a>복원할 항목

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>실패 한 경우</th>
<th>이 섹션을 참조 하세요.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>스탠더드 버전 서버</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Lync Server 2013에서 Standard Edition 서버 복원</a></p></td>
</tr>
<tr class="even">
<td><p>중앙 관리 저장소</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Lync Server 2013에서 중앙 관리 저장소를 호스팅하는 서버 복원</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition 백 엔드</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync Server 2013에서 Enterprise Edition 백 엔드 서버 복원</a></p></td>
</tr>
<tr class="even">
<td><p>엔터프라이즈 버전의 미러된 백 엔드 기본 서버</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-기본</a></p></td>
</tr>
<tr class="odd">
<td><p>엔터프라이즈 버전의 미러된 백 엔드 보조 서버</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-미러</a></p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버, Edge 서버, 중재 서버, 또는 영구 채팅 서버와 같이 서버 역할을 실행 하는 모든 Enterprise Edition 서버</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync Server 2013에서 Enterprise Edition 구성원 서버 복원</a></p></td>
</tr>
<tr class="odd">
<td><p>전체 Lync Server 풀</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Lync Server 2013에서 Lync Server 풀 복원</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition 파일 저장소</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Lync Server 2013에서 파일 저장소 복원</a></p></td>
</tr>
<tr class="odd">
<td><p>독립 실행형 모니터링 데이터베이스 또는 보관 데이터베이스</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Lync Server 2013에서 모니터링 또는 데이터 보관 복원</a></p></td>
</tr>
<tr class="even">
<td><p>독립형 영구 채팅 데이터베이스</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Lync Server 2013에서 영구 채팅 데이터 복원</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>하드웨어, 소프트웨어 및 도구 수집

서버를 복원 하는 경우 새 컴퓨터 또는 깨끗 한 컴퓨터로 시작 해야 합니다. 또한 다음 하드웨어 및 소프트웨어를 사용할 수 있어야 합니다.

  - 실패 한 서버와 FQDN (정규화 된 도메인 이름)이 동일한 클린 또는 새 서버입니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 운영 체제를 설치할 때 Active Directory 도메인 서비스에서 컴퓨터 계정을 삭제 하지 말고 계정에 대 한 그룹 권한이 유지 되는지 확인 합니다.

    
    </div>

  - 운영 체제의 설치 소프트웨어입니다. 운영 체제를 설치 하려면 조직에서 설정한 서버 배포 절차와 구성을 사용 합니다. 이러한 절차와 구성 요구 사항은 서비스를 복원할 때 사용할 수 있어야 합니다.

  - SQL Server 2012 또는 SQL Server 2008 R2 용 설치 소프트웨어 데이터베이스 서버를 설치 하려면 해당 버전의 SQL Server와 조직에서 설정한 데이터베이스 서버 배포 절차 및 구성을 사용 합니다. 이러한 절차와 구성 요구 사항은 서비스를 복원할 때 사용할 수 있어야 합니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 배포 마법사에서는 sql server 2012 또는 SQL Server 2008 R2가 설치 되어 있지 않은 경우 각 스탠더드 버전 서버와 다른 Lync Server 서버에 로컬 구성 저장소를 설치한 경우 자동으로 SQL Server 2012 Express를 설치 합니다. 서버.

    
    </div>

  - 시스템 이미지를 만드는 소프트웨어입니다.
    
    <div>
    

    > [!TIP]  
    > 운영 체제 및 SQL Server를 설치한 후 복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하 여 복원 중 문제가 발생 하는 경우 롤백 시점으로이 이미지를 사용할 수 있도록 하는 것이 좋습니다.

    
    </div>

  - Lync Server 2013 설치 소프트웨어 Lync Server 배포 마법사는 Lync Server 설치 폴더 또는 \\설치\\amd64\\setup.exe의 미디어에 있습니다.

복원 하는 동안 다음 도구를 사용 합니다.

  - Lync Server 관리 셸 cmdlet

  - 가져오기-CsUserData

  - Windows 폴더 복원 도구

  - 토폴로지 작성기

  - Sql Server Management Studio와 같은 SQL Server 데이터베이스 유틸리티

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>서버 복원 준비

서버를 복원 하기 전에 다음 단계를 수행 해야 합니다.

1.  운영 체제를 설치 합니다.

2.  서버가 백 엔드 서버인 경우 SQL Server 2012 또는 SQL Server 2008 R2를 설치 합니다.

3.  인증서를 복원 하거나 reenroll. 인증서에 대 한 자세한 내용은 [Lync Server 2013: data의 백업 및 복원 요구 사항](lync-server-2013-backup-and-restoration-requirements-data.md)에서 "추가 백업 요구 사항"을 참조 하세요.

4.  복원 중 문제가 발생 하는 경우 롤백 시점으로 사용할 복원을 시작 하기 전에 시스템 이미지를 찍습니다.

<div>


> [!NOTE]  
> 이 항목의 절차에 설명 된 Lync Server 배포 마법사 및 cmdlet은 필요한 모든 Acl (액세스 제어 목록)을 설정 합니다.



</div>

복원을 시작 하기 전에 복원 하려는 구성 요소에 필요한 하드웨어 및 소프트웨어를 사용할 수 있는지 확인 합니다. 운영 체제 및 SQL Server를 설치한 후에는 다음 복원 절차의 대부분의 단계를 원격으로 실행할 수 있습니다. 예외는 절차에 명시 되어 있습니다.

또한 복원을 시작 하기 전에 조직의 백업 및 복원 계획 및이 문서의 워크시트에 있는 정보 (예: [Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)참조) 등의 마지막 백업 정보도 있어야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

