---
title: 'Lync Server 2013: 인증서 요약-역방향 프록시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5691b20031d9998877a64f34f6578b654494a99
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>인증서 요약-Lync Server 2013의 역방향 프록시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-14_

역방향 프록시에 대 한 인증서 요구 사항은에 지 서버에 비해 훨씬 단순 합니다. 제공 된 순서도에는 필요한 요구 사항이 표시 됩니다. 함께 제공 되는 표에는에 지 서버 토론에서 검토 한 시나리오와 관련 하 여 일반적인 인증서 주체 이름 및 주체 대체 이름이 나와 있습니다. 에 지 서버 시나리오에 대 한 자세한 내용은 [Lync server 2013에서 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.

**역방향 프록시에 대 한 인증서 순서도**

![에 지 서버에 대 한 인증서 순서도](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "에 지 서버에 대 한 인증서 순서도")

### <a name="reverse-proxy-external-interface"></a>역방향 프록시: 외부 인터페이스

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>구성 요소</th>
<th>주체 이름</th>
<th>SAN (주체 대체 이름)/Order</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>역방향 프록시</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(선택 사항):* contoso.com</p></td>
<td><p>인증서는 공용 CA 및 서버 EKU를 사용 하 여 발급 해야 합니다. 서비스에는 주소록 서비스, 회의를 위한 메일 그룹 확장 Office Web Apps 및 Lync IP 장치 게시 규칙이 포함 되어 있습니다. 주체 대체 이름에는 다음이 포함됩니다.</p>
<ul>
<li><p>프런트 엔드 서버 또는 프런트 엔드 풀에 대 한 외부 웹 서비스 FQDN</p></li>
<li><p>디렉터 또는 디렉터 풀에 대 한 외부 웹 서비스 FQDN</p></li>
<li><p>전화 접속 회의</p></li>
<li><p>온라인 모임 게시 규칙</p></li>
<li><p>회의를 위한 Office Web Apps</p></li>
<li><p>Lyncdiscover (자동 검색)</p></li>
</ul>
<p>선택적 와일드 카드는 모임 및 전화 접속 SAN을 모두 대체 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

