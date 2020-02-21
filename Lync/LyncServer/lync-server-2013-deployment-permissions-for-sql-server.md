---
title: 'Lync Server 2013: SQL Server에 대 한 배포 권한'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d24a60c089efef55718dd71d889caade8f24949a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Lync Server 2013의 SQL Server에 대 한 배포 권한

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

Microsoft SQL Server 2012에는 Lync Server 2013을 설치 및 배포할 때 특정 요구 사항이 적용 됩니다. Windows 및 SQL Server에서는 보안을 다르게 정의 하기 때문에 Active Directory 도메인의 관리자로 로그인 하면 SQL Server에 대 한 사용 권한을 암시적으로 부여 하지 않습니다. 즉, 구성 중인 SQL Server 기반 서버에서 sysadmin 엔터티의 구성원이어야 합니다.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>데이터베이스 및 Lync Server 설치에 필요한 사용 권한

다음 옵션은 Lync Server 2013 파일과 SQL Server 데이터베이스 설치에 대 한 세 가지 권한 및 그룹 구성원 연결에 대해 자세히 설명 합니다. 조직의 요구 사항에 가장 적합한 시나리오를 선택하십시오.

### <a name="permissions-and-group-membership-associations"></a>사용 권한 및 그룹 구성원 연결

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>SQL Server 또는 Lync Server 2013 역할</th>
<th>역할의 일반적인 SQL Server 사용 권한 및 그룹 구성원</th>
<th>역할-일반적인 Lync Server 2013 사용 권한 및 그룹 구성원 자격</th>
<th>사용 권한의 결과</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 관리자</p></td>
<td><p>SQL Server 로컬 Administrators 그룹 구성원 및 sysadmins SQL Server 보안 그룹 구성원 자격이 부여되어야 합니다.</p></td>
<td><p>RTCUniversalServerAdmins 그룹 구성원이어야 합니다.</p></td>
<td><p>Lync Server 2013 관리자에 게 Lync Server 2013 및 SQL Server 데이터베이스를 모두 설치할 수 있는 적절 한 권한이 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>SQL Server 관리자</p></td>
<td><p>SQL Server sysadmin 그룹 구성원이거나 그와 동등한 권한을 가져야 하며, SQL Server 로컬 Administrators 그룹 구성원이어야 합니다.</p></td>
<td><p>RTCUniversalServerReadOnly 그룹 구성원이어야 합니다.</p></td>
<td><p>SQL Server 관리자에 게 Lync Server 2013 및 SQL Server 데이터베이스를 모두 설치할 수 있는 적절 한 권한이 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>설치 작업을 공유하는 두 관리자 모두</p></td>
<td><p>SQL Server 관리자가 sysadmins 그룹 구성원이거나 그와 동등한 권한을 가져야 하며, SQL Server 로컬 Administrators 그룹 구성원이어야 합니다.</p></td>
<td><p>Lync Server 2013 관리자가 RTCUniversalServerAdmins의 구성원 이어야 합니다.</p></td>
<td><p>Lync Server 2013 관리자는 Lync Server 2013를 설치할 수 있지만 데이터베이스를 설치할 수는 없습니다. SQL Server 관리자는 lync server 2013 관리자가 제공 하는 Lync 서버 관리 셸 및 Windows PowerShell cmdlet을 사용 하 여 데이터베이스를 설치 합니다. SQL Server 관리자가 사용 하는 Lync Server 2013 관리 셸이 프런트 엔드 서버에 설치 되어 있어야 합니다. 이를 통해 SQL Server 기반 서버에 Lync Server 2013 관리 도구를 설치할 필요가 없습니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

