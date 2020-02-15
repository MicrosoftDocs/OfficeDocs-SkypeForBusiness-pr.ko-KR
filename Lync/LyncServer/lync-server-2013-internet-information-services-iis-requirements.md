---
title: 'Lync Server 2013: IIS (인터넷 정보 서비스) 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a086713c4c4c1ea5752c7e1b46ce46e48a0ea42
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Lync Server 2013의 IIS (인터넷 정보 서비스) 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-19_

여러 Lync Server 2013 구성 요소에는 IIS (인터넷 정보 서비스)가 필요 합니다. 이 항목에서는 Lync Server를 지 원하는 데 필요한 특정 IIS 기능에 대해 설명 합니다. 이 섹션의 항목에서는 IIS의 특정 구성 요소에 대한 요구 사항을 설명합니다.

Windows Server 2008에서 웹 서버(IIS) 역할이 사용하도록 설정되어 있으면 다양한 역할 서비스가 기본적으로 설치됩니다. 다음 표에서는 Windows Server 2008에서 웹 서버(IIS) 역할이 사용하도록 설정되어 있을 때 설치해야 하는 추가 역할 서비스에 대해 설명합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>역할 서비스</th>
<th>기능</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>일반 HTTP 기능</p></td>
<td><p>HTTP 리디렉션</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 개발</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 개발</p></td>
<td><p>.NET 확장성</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 개발</p></td>
<td><p>ISAPI 확장</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 개발</p></td>
<td><p>ISAPI 필터</p></td>
</tr>
<tr class="even">
<td><p>상태 및 진단</p></td>
<td><p>로깅 도구</p></td>
</tr>
<tr class="odd">
<td><p>상태 및 진단</p></td>
<td><p>추적은</p></td>
</tr>
<tr class="even">
<td><p>보안</p></td>
<td><p>기본 인증</p></td>
</tr>
<tr class="odd">
<td><p>보안</p></td>
<td><p>Windows 인증</p></td>
</tr>
<tr class="even">
<td><p>관리 도구</p></td>
<td><p>IIS 관리 스크립트 및 도구</p></td>
</tr>
<tr class="odd">
<td><p>관리 도구</p></td>
<td><p>IIS 6 관리 호환성</p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" />보안 메모:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Windows Server 2008 운영 체제에서 IIS 7.0을 사용 하는 경우 Lync Server 설치 프로그램에서 커널 모드 인증을 사용 하지 않도록 설정 합니다.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 프런트 엔드 풀 및 Standard Edition 서버에 대 한 IIS 요구 사항](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

