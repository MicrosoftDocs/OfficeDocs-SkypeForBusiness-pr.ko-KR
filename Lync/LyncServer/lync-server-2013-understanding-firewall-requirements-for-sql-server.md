---
title: 'Lync Server 2013: SQL Server에 대 한 방화벽 요구 사항 이해'
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
ms.openlocfilehash: ba04284106bcd1b0cbf17d214d8ad0b1a1ff9024
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Lync Server 2013을 사용 하 여 SQL Server에 대 한 방화벽 요구 사항 이해

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

Standard Edition 배포의 경우 Lync Server 2013 설치 중에 방화벽 예외가 자동으로 만들어집니다. 그러나 Enterprise Edition 배포의 경우 SQL Server 백 엔드 서버에서 방화벽 예외를 수동으로 구성 해야 합니다. TCP/IP 프로토콜을 사용하는 경우 지정된 IP 주소에 대해 지정된 포트를 한 번 사용할 수 있습니다. 즉, SQL Server 기반 서버의 경우 기본 데이터베이스 인스턴스에 기본 TCP 포트 1433을 할당할 수 있습니다. 기타 모든 인스턴스의 경우에는 SQL Server 구성 관리자를 사용하여 고유한 미사용 포트를 할당해야 합니다. 이 항목에서는 다음에 대해 다룹니다.

  - 기본 인스턴스를 사용하는 경우의 방화벽 예외 요구 사항

  - SQL Server Browser 서비스를 사용하는 경우의 방화벽 예외 요구 사항

  - 명명된 인스턴스를 사용하는 경우의 정적 수신 대기 포트 요구 사항

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>기본 인스턴스를 사용하는 경우의 방화벽 예외 요구 사항

Lync Server 2013를 배포할 때 모든 데이터베이스에 대해 SQL Server 기본 인스턴스를 사용 하는 경우에는 다음 방화벽 규칙 요구 사항을 사용 하 여 프런트 엔드 풀에서 SQL Server 기본 인스턴스에 대 한 통신을 수행 하는 데 도움이 됩니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>프로토콜로</th>
<th>포트</th>
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>SQL Server로 인바운드</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>SQL Server Browser 서비스를 사용하는 경우의 방화벽 예외 요구 사항

SQL Server Browser 서비스는 데이터베이스 인스턴스를 찾아 해당 인스턴스(명명된 인스턴스 또는 기본 인스턴스)가 사용하도록 구성된 포트와 통신합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>프로토콜로</th>
<th>포트</th>
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>P</p></td>
<td><p>1434</p></td>
<td><p>인바운드</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>명명된 인스턴스를 사용하는 경우의 정적 수신 대기 포트 요구 사항

Lync Server 2013을 지 원하는 데이터베이스에 대 한 SQL Server 구성에서 명명 된 인스턴스를 사용 하는 경우 SQL Server Configuration Manager를 사용 하 여 정적 포트를 구성 합니다. 정적 포트를 각 명명된 인스턴스에 할당한 후에는 방화벽의 각 정적 포트에 대한 예외를 만듭니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>프로토콜로</th>
<th>포트</th>
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>정적으로 정의됨</p></td>
<td><p>인바운드</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>SQL Server 설명서

Microsoft SQL Server 2012 문서에서는 데이터베이스에 대 한 방화벽 액세스를 구성 하는 방법에 대 한 자세한 지침을 제공 합니다. Microsoft SQL Server 2012에 대 한 자세한 내용은의 "SQL Server 액세스를 허용 하도록 Windows 방화벽 구성" [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

