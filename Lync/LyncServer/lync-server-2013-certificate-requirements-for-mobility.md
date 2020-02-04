---
title: 'Lync Server 2013: 모바일 기능에 대한 인증서 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 680eaf205959b67d8fef93ff56d379ae8cd293bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013의 모바일 기능에 대한 인증서 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-24_

이동성 기능을 배포 하 고 모바일 클라이언트에 대 한 자동 검색을 지 원하는 경우 모바일 클라이언트의 보안 연결을 지원 하기 위해 인증서에 특정 주체 대체 이름 항목을 포함 해야 합니다.

자동 검색에 대 한 주체 대체 이름 항목을 다음 인증서에 포함 해야 합니다.

  - 디렉터 풀

  - 프런트 엔드 풀

  - 역방향 프록시

이 섹션에서는 자동 검색을 위해 인증서에 필요한 주체 대체 이름 항목에 대해 설명 합니다.

<div>


> [!NOTE]  
> 내부 인증 기관을 사용 하 여 인증서를 재발급 하는 것은 일반적으로 간단한 프로세스 이지만, 역방향 프록시에 사용 되는 공개 인증서에 여러 주체 대체 이름 항목을 추가 하는 것은 부담이 큰 일입니다. 많은 SIP 도메인이 있고, 주체 대체 이름을 추가 하는 것이 매우 많은 경우 HTTPS (기본 구성)를 사용 하는 대신 초기 자동 검색 서비스 요청에 대해 HTTP를 사용 하도록 역방향 프록시를 구성할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013의 모바일 기능에 대 한 기술 요구 사항을</A>참조 하세요.



</div>

### <a name="director-pool-certificate-requirements"></a>디렉터 풀 인증서 요구 사항

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>설명</th>
<th>주체 대체 이름 항목</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>내부 자동 검색 서비스 URL</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>외부 자동 검색 서비스 URL</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 또는 SAN = *를 사용할 수 있습니다. &lt;sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>프런트 엔드 풀 인증서 요구 사항

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>설명</th>
<th>주체 대체 이름 항목</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>내부 자동 검색 서비스 URL</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>외부 자동 검색 서비스 URL</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 또는 SAN = *를 사용할 수 있습니다. &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>역방향 프록시 (공개 CA) 인증서 요구 사항

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>설명</th>
<th>주체 대체 이름 항목</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 자동 검색 서비스 URL</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 이 SAN을 리버스 프록시의 SSL 수신기에 할당 된 인증서에 할당 합니다.



</div>

<div>


> [!NOTE]  
> 역방향 프록시 수신기에는 외부 웹 서비스 URL (예: SAN = lyncwebextpool01)에 대 한 주체의 대체 이름과 선택적 디렉터를 배포한 경우 dirwebexternal.contoso.com.



</div>

</div>

<span> </span>

</div>

</div>

</div>

