---
title: 'Lync Server 2013: 이동성을 위한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc11c79c291f7db7ad9e9e3228644ee27d42e555
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Lync Server 2013을 사용 하 여 이동성을 위한 DNS 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-13_

Lync Server 2013 모바일 기능을 배포 하는 경우 Microsoft Lync Server 2013 자동 검색 서비스에서 사용할 수 있는 새 Url을 사용 하거나 기존 웹 서비스 Url을 사용할 수 있습니다. 기존 Url을 사용 하는 경우 사용자는 모바일 장치 설정에 Url을 수동으로 입력 해야 합니다. 이 옵션은 일반적으로 문제 해결에 사용 됩니다. 새 Url을 사용 하는 경우 모바일 클라이언트는 Lync Server 2013 리소스를 자동으로 검색할 수 있습니다. 자동 검색을 지 원하는 경우 새 DNS (Domain Name System) 레코드를 추가 해야 합니다. 이 섹션에서는 자동 검색에 필요한 DNS 레코드에 대해 설명 합니다.

자동 검색을 지원 하려면 각 SIP 도메인에 대해 다음 DNS 레코드를 만들어야 합니다.

  - 조직의 네트워크 내에서 연결 하는 모바일 사용자를 지 원하는 내부 DNS 레코드

  - 인터넷에서 연결 하는 모바일 사용자를 지 원하는 외부 또는 공용 DNS 레코드

내부 자동 검색 URL은 네트워크 외부에서 주소를 지정할 수 없습니다. 외부 자동 검색 URL은 네트워크 내에서 주소를 지정할 수 없습니다. 그러나 외부 URL에 대해 이러한 요구 사항을 충족 하지 못하는 경우에는 모바일 클라이언트의 기능에 영향을 주지 않습니다.

DNS 레코드는 CNAME 레코드 이거나 (호스트) 레코드가 될 수 있습니다.

**내부 DNS 레코드**

다음 내부 DNS 레코드 중 하나를 만들어야 합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>레코드 종류</th>
<th>호스트 이름 또는 SRV 정의</th>
<th>(으)로 확인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>디렉터 풀에 대 한 내부 웹 서비스 FQDN (정규화 된 도메인 이름) 또는 디렉터가 없는 경우 프런트 엔드 풀에 대해 사용</p></td>
</tr>
<tr class="even">
<td><p>A (호스트)</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>디렉터 풀에 대 한 내부 웹 서비스 IP 주소 (부하 분산 장치를 사용 하는 경우 VIP (가상 IP) 주소) (사용자에 게 디렉터가 없는 경우) 또는 프런트 엔드 풀을 보유 하 고 있는 경우</p></td>
</tr>
</tbody>
</table>


**외부 DNS 레코드**

다음 외부 DNS 레코드 중 하나를 만들어야 합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>레코드 종류</th>
<th>호스트 이름</th>
<th>(으)로 확인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>디렉터 풀에 대 한 외부 웹 서비스 FQDN (있는 경우) 또는 사용자에 게 디렉터가 없는 경우 프런트 엔드 풀의 경우</p></td>
</tr>
<tr class="even">
<td><p>A (호스트)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>역방향 프록시의 외부 또는 공용 IP 주소 (부하 분산 장치를 사용 하는 경우 VIP 주소)</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_tcp _sipfederationtls. &lt;sipdomain&gt;</p>
<p>액세스에 지 서비스에 대 한 host (A 또는 AAAA) 레코드로 확인 됩니다.</p></td>
<td><p>푸시 알림 서비스 및 Apple 푸시 알림 서비스를 지원 하려면 Microsoft Lync 모바일 클라이언트가 있는 각 SIP 도메인에 대해 하나의 SRV 레코드를 만듭니다.</p>
<div>

> [!IMPORTANT]  
> 이 요구 사항은 Apple 또는 Microsoft 기반 모바일 장치에서 Microsoft Lync Mobile 클라이언트에만 적용 됩니다. Andriod 및 Nokia Symbian 장치는 푸시 알림을 사용 하지 않습니다.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 자동 검색이 라고도 하는 lyncdiscover는 트래픽이 역방향 프록시를 거칩니다. SRV 레코드는 액세스에 지 서비스를 통해 확인 되는 레코드를 가리킵니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

