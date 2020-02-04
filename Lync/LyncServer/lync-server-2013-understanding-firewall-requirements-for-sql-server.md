---
title: 'Lync Server 2013: SQL Server에 대한 방화벽 요구 사항 이해'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dba3296ee01f997857660d2a3f328f663d32cf99
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Lync Server 2013의 SQL Server에 대한 방화벽 요구 사항 이해

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

스탠더드 버전 배포의 경우 방화벽 예외는 Lync Server 2013 설치 중에 자동으로 생성 됩니다. 그러나 Enterprise Edition 배포의 경우 SQL Server 백 엔드 서버에서 방화벽 예외를 수동으로 구성 해야 합니다. TCP/IP 프로토콜을 사용 하면 지정 된 IP 주소에 대해 주어진 포트를 한 번만 사용할 수 있습니다. 즉, SQL Server 기반 서버에서는 기본 TCP 포트 1433에 기본 데이터베이스 인스턴스를 할당할 수 있습니다. 다른 경우에는 SQL Server 구성 관리자를 사용 하 여 고유 하 고 사용 하지 않는 포트를 할당 해야 합니다. 이 항목에서는 다음에 대해 설명 합니다.

  - 기본 인스턴스를 사용 하는 경우 방화벽 예외에 대 한 요구 사항

  - SQL Server Browser 서비스의 방화벽 예외에 대 한 요구 사항

  - 명명 된 인스턴스를 사용 하는 경우 정적 수신 대기 포트에 대 한 요구 사항

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>기본 인스턴스를 사용 하는 경우 방화벽 예외에 대 한 요구 사항

Lync Server 2013을 배포할 때 데이터베이스에 대해 SQL Server 기본 인스턴스를 사용 하는 경우 다음 방화벽 규칙 요구 사항을 사용 하 여 프런트 엔드 풀에서 SQL Server 기본 인스턴스로 통신 하는 데 도움을 줍니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>프로토콜별</th>
<th>포트</th>
<th>지침</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NET.TCP</p></td>
<td><p>1433</p></td>
<td><p>SQL Server로의 인바운드</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>SQL Server Browser 서비스의 방화벽 예외에 대 한 요구 사항

SQL Server Browser 서비스는 데이터베이스 인스턴스를 찾고 인스턴스 (명명 된 또는 기본값)가 사용 하도록 구성 된 포트를 통신 합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>프로토콜별</th>
<th>포트</th>
<th>지침</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>Ipsec</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>명명 된 인스턴스를 사용 하는 경우 정적 수신 대기 포트에 대 한 요구 사항

Lync Server 2013을 지 원하는 데이터베이스용 SQL Server 구성에서 명명 된 인스턴스를 사용 하는 경우 SQL Server 구성 관리자를 사용 하 여 정적 포트를 구성 합니다. 명명 된 각 인스턴스에 정적 포트를 할당 한 후에는 방화벽의 각 정적 포트에 대 한 예외를 만듭니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>프로토콜별</th>
<th>포트</th>
<th>지침</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NET.TCP</p></td>
<td><p>정적으로 정의 됨</p></td>
<td><p>Ipsec</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>SQL Server 설명서

Microsoft SQL Server 2012 문서에서는 데이터베이스에 대 한 방화벽 액세스를 구성 하는 방법에 대 한 자세한 지침을 제공 합니다. Microsoft SQL Server 2012에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)"SQL Server 액세스를 허용 하도록 Windows 방화벽 구성"을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

