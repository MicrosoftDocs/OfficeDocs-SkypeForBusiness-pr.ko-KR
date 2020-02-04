---
title: 'Lync Server 2013: 영구 채팅 서버의 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b97d3238c64173cb5f9bfcfc12dce40f987da123
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버에 대 한 DNS 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-28_

이 섹션에서는 영구 채팅 서버를 배포 하는 데 필요한 DNS (Domain Name System) 레코드에 대해 설명 합니다.

<div>

## <a name="dns-records-for-persistent-chat-servers"></a>영구 채팅 서버용 DNS 레코드

다음 표에서는 영구 채팅 서버 배포에 대 한 DNS 요구 사항을 지정 합니다.

### <a name="dns-requirements-for-a-persistent-chat-server"></a>영구 채팅 서버의 DNS 요구 사항

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>배포 시나리오</th>
<th>DNS 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>영구 채팅 서버 1 개</p></td>
<td><p>서버의 FQDN (정규화 된 도메인 이름)을 IP 주소로 확인 하는 내부 A 레코드입니다.</p></td>
</tr>
<tr class="even">
<td><p>영구 채팅 풀</p></td>
<td><p>서버의 FQDN (정규화 된 도메인 이름)을 IP 주소로 확인 하는 내부 A 레코드입니다.</p>
<p><strong>예</strong></p>
<p>PersistentChatServer01.contoso.com 10.10.10.1</p>
<p>PersistentChatServer02.contoso.com 10.10.10.2</p>
<p>서버의 FQDN (정규화 된 도메인 이름)을 IP 주소로 확인 하는 내부 A 레코드입니다.</p>
<p><strong>예</strong></p>
<p>PersistentChatPool.contoso.com 10.10.10.1</p>
<p>PersistentChatPool.contoso.com 10.10.10.2</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

