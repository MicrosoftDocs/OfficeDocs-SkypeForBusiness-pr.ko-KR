---
title: 'Lync Server 2013: 인증서 요약-자동 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 196b3dacec792097a4760ef134ead91f267a53d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499315"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Lync Server 2013의 인증서 요약-자동 검색

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-14_

Lync Server 2013 자동 검색 서비스는 디렉터 및 프런트 엔드 풀 서버에서 실행 되며, DNS에 게시 될 때 Lync 클라이언트에서 서버 및 사용자 서비스를 찾는 데 사용할 수 있습니다. Lync Server 2010에서 업그레이드 하는 중 이며, 모바일을 배포 하지 않은 경우 클라이언트가 자동 검색을 사용할 수 있도록 하려면 모든 디렉터 및 자동 검색 서비스를 실행 하는 프런트 엔드 서버에서 인증서 주체 대체 이름 목록을 수정 해야 합니다. 또한 역방향 프록시에 대한 외부 웹 서비스 게시 규칙에 사용되는 인증서에서도 주체 대체 이름 목록을 수정해야 할 수 있습니다.

역방향 프록시에서 주체 대체 이름 목록을 사용할지 여부에 대 한 결정은 포트 80 또는 포트 443에 자동 검색 서비스를 게시할지 여부에 따라 달라 집니다.

  - **포트 80**     에 게시 됨 포트 80을 통해 자동 검색 서비스에 대 한 초기 쿼리를 수행 하는 경우에는 인증서를 변경할 필요가 없습니다. Lync를 실행 하는 모바일 장치는 외부에서 포트 80의 역방향 프록시에 액세스 한 다음 내부적으로 포트 8080의 디렉터 또는 프런트 엔드 서버에 브리지 되기 때문입니다. 자세한 내용은 [Lync Server 2013에서 모바일 기능에 대 한](lync-server-2013-technical-requirements-for-mobility.md)"포트 80을 사용 하 여 초기 자동 검색 프로세스" 섹션을 참조 하십시오.

  - **포트 443**     에 게시 됨 외부 웹 서비스 게시 규칙에서 사용 하는 인증서의 주체 대체 이름 목록에는 *lyncdiscover \<sipdomain\> * 가 포함 되어야 합니다. 조직 내의 각 SIP 도메인에 대 한 항목입니다.
    
    <div>
    

    > [!IMPORTANT]  
    > HTTPS over HTTP를 사용 하는 것이 좋습니다. HTTPS는 인증서를 사용 하 여 트래픽을 암호화 합니다. HTTP는 암호화를 제공 하지 않으며 전송 되는 데이터는 일반 텍스트로 나타납니다.

    
    </div>

내부 인증 기관을 사용 하 여 인증서를 재발급 하는 것은 일반적으로 간단한 프로세스입니다. 그러나 웹 서비스 게시 규칙에 사용 되는 공용 인증서의 경우 여러 주체 대체 이름 항목을 추가 하는 데 많은 비용이 소요 될 수 있습니다. 이 문제를 해결 하려면 포트 80을 통한 초기 자동 검색 연결을 지원 하며, 그러면 디렉터 또는 프런트 엔드 서버의 포트 8080로 리디렉션됩니다.

<div>


> [!NOTE]  
> Lync Server 2013 인프라에서 내부 CA (인증 기관)에서 발급 된 내부 인증서를 사용 하 고 무선으로 연결 되는 모바일 장치를 지원 하려는 경우에는 내부 CA의 루트 인증서 체인을 모바일 장치에 설치 해야 하거나 Lync Server 2013 인프라의 공용 인증서로 변경 해야 합니다.



</div>

이 항목에서는 디렉터, 프런트 엔드 서버 및 역방향 프록시에 필요한 추가 주체 대체 이름에 대해 설명 합니다. 추가 된 SAN (주체 대체 이름)만 참조 됩니다. 인증서의 다른 항목에 대 한 지침은 계획 섹션을 참조 하십시오. 자세한 내용은 Lync server 2013, lync server [2013의 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)및 [lync server 2013의 역방향 프록시 시나리오](lync-server-2013-scenarios-for-reverse-proxy.md)에서 [디렉터에 대 한](lync-server-2013-scenarios-for-the-director.md)시나리오를 참조 하세요.

다음 표에서는 디렉터 풀, 프런트 엔드 풀 및 역방향 프록시에 대 한 자동 검색 SAN 항목을 정의 합니다.

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
<td><p>SAN = lyncdiscoverinternal. &lt; 내부 도메인 이름&gt;</p></td>
</tr>
<tr class="even">
<td><p>외부 자동 검색 서비스 URL</p></td>
<td><p>SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 새 SAN 항목을 사용 하 여 새로 업데이트 된 인증서를 기본 인증서에 할당 합니다. 또는 SAN = *를 사용할 수 있습니다. &lt; microsoft.rtc.management.xds.sipdomain object &gt;



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
<td><p>SAN = lyncdiscoverinternal. &lt; 내부 도메인 이름&gt;</p></td>
</tr>
<tr class="even">
<td><p>외부 자동 검색 서비스 URL</p></td>
<td><p>SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 새 SAN 항목을 사용 하 여 새로 업데이트 된 인증서를 기본 인증서에 할당 합니다. 또는 SAN = *를 사용할 수 있습니다. &lt; microsoft.rtc.management.xds.sipdomain object&gt;



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
> 새 SAN 항목을 사용 하 여 새로 업데이트 된 인증서를 역방향 프록시의 SSL 수신기에 할당 합니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

