---
title: Lync Server 2013 IPsec 예외
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Lync Server 2013의 IPsec 예외

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-27_

IPsec (인터넷 프로토콜 보안) (IETF RFC 4301-4309 참조)이 배포 된 엔터프라이즈 네트워크의 경우 오디오, 비디오, 파노라마 비디오를 제공 하는 데 사용 되는 포트 범위에 대해 IPsec을 사용 하지 않도록 설정 해야 합니다. 권장 사항은 IPsec 협상으로 인해 미디어 포트를 할당할 때 지연 되지 않도록 하는 데 필요 합니다.

다음 표에서는 권장 IPsec 예외 설정에 대해 설명 합니다.

### <a name="recommended-ipsec-exceptions"></a>권장 IPsec 예외

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>규칙 이름</th>
<th>원본 IP</th>
<th>대상 IP</th>
<th>프로토콜별</th>
<th>원본 포트</th>
<th>대상 포트</th>
<th>인증 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V Edge 서버 내부 인바운드</p></td>
<td><p>이상</p></td>
<td><p>A/V에 지 서버 내부</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge 서버 외부 인바운드</p></td>
<td><p>이상</p></td>
<td><p>A/V에 지 서버 외부</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>A/V Edge 서버 내부 아웃 바운드</p></td>
<td><p>A/V에 지 서버 내부</p></td>
<td><p>이상</p></td>
<td><p>UDP &amp; TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge 서버 외부 아웃 바운드</p></td>
<td><p>A/V에 지 서버 외부</p></td>
<td><p>이상</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>중재 서버 인바운드</p></td>
<td><p>이상</p></td>
<td><p>중재</p>
<p>서버 (s)</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>중재 서버 아웃 바운드</p></td>
<td><p>중재</p>
<p>서버 (s)</p></td>
<td><p>이상</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>회의 전화 교환 인바운드</p></td>
<td><p>이상</p></td>
<td><p>회의 수행자를 실행 하는 프런트 엔드 서버</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>회의 전화 교환 아웃 바운드</p></td>
<td><p>회의 수행자를 실행 하는 프런트 엔드 서버</p></td>
<td><p>이상</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>A/V 회의 인바운드</p></td>
<td><p>이상</p></td>
<td><p>프런트 엔드 서버</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>A/V 회의 아웃 바운드</p></td>
<td><p>프런트 엔드 서버</p></td>
<td><p>이상</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 인바운드</p></td>
<td><p>이상</p></td>
<td><p>Exchange 통합 메시징</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 공유 서버 인바운드</p></td>
<td><p>이상</p></td>
<td><p>응용 프로그램 공유 서버</p></td>
<td><p>NET.TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 공유 서버 아웃 바운드</p></td>
<td><p>응용 프로그램 공유 서버</p></td>
<td><p>이상</p></td>
<td><p>NET.TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>Exchange 아웃 바운드</p></td>
<td><p>Exchange 통합 메시징</p></td>
<td><p>이상</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>클라이언트</p></td>
<td><p>이상</p></td>
<td><p>이상</p></td>
<td><p>UDP</p></td>
<td><p>지정 된 미디어 포트 범위</p></td>
<td><p>이상</p></td>
<td><p>인증 안 함</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

