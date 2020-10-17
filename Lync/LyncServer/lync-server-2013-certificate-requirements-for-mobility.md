---
title: 'Lync Server 2013: 모바일 기능에 대 한 인증서 요구 사항'
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
ms.openlocfilehash: 87657340205722a721485f213029220641885075
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533395"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013의 모바일 기능에 대 한 인증서 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-24_

모바일 기능을 배포하고 모바일 클라이언트에 대해 자동 검색을 지원하는 경우에는 모바일 클라이언트로부터의 보안 연결을 지원하기 위해 인증서에 특정 주체 대체 이름 항목을 포함해야 합니다.

자동 검색용 주체 대체 이름 항목을 포함해야 하는 인증서는 다음과 같습니다.

  - 디렉터 풀

  - 프런트 엔드 풀

  - 역방향 프록시

이 섹션에서는 자동 검색을 위해 인증서에 필요한 주체 대체 이름 항목에 대해 설명합니다.

<div>


> [!NOTE]  
> 내부 인증 기관을 통해 인증서를 다시 발급하는 과정은 일반적으로는 간단하지만, 역방향 프록시에서 사용되는 공용 인증서에 여러 주체 대체 이름 항목을 추가하려면 비용이 많이 들 수 있습니다. SIP 도메인이 여러 개인 경우 주체 대체 이름 추가 비용이 매우 크므로, 초기 자동 검색 서비스 요청에 대해 HTTPS(기본 구성) 대신 HTTP를 사용하도록 역방향 프록시를 구성할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 기술 요구 사항을</A>참조 하세요.



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
<td><p>SAN = lyncdiscoverinternal. &lt; microsoft.rtc.management.xds.sipdomain object&gt;</p></td>
</tr>
<tr class="even">
<td><p>외부 자동 검색 서비스 URL</p></td>
<td><p>SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 또는 SAN = *를 사용할 수 있습니다. &lt; microsoft.rtc.management.xds.sipdomain object&gt;



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
<td><p>SAN = lyncdiscoverinternal. &lt; microsoft.rtc.management.xds.sipdomain object&gt;</p></td>
</tr>
<tr class="even">
<td><p>외부 자동 검색 서비스 URL</p></td>
<td><p>SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 또는 SAN = *를 사용할 수 있습니다. &lt; microsoft.rtc.management.xds.sipdomain object&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>역방향 프록시(공용 CA) 인증서 요구 사항

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
<td><p>SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 역방향 프록시의 SSL 수신기에 할당된 인증서에 이 SAN을 할당합니다.



</div>

<div>


> [!NOTE]  
> 역방향 프록시 수신기에는 외부 웹 서비스 URL에 대 한 주체 대체 이름 (예: SAN = lyncwebextpool01.contoso.com, 그리고 선택적 디렉터를 배포한 경우 dirwebexternal.contoso.com)이 있습니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

