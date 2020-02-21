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
ms.openlocfilehash: bd649cea823ce13460de924ffc49741b3ca5c6d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Lync Server 2013의 IPsec 예외

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-27_

IPsec (인터넷 프로토콜 보안) (IETF RFC 4301-4309 참조)이 배포 된 엔터프라이즈 네트워크의 경우에는 오디오, 비디오 및 파노라마 비디오를 배달 하는 데 사용 되는 포트 범위에서 IPsec을 사용 하지 않도록 설정 해야 합니다. 권장 사항은 IPsec 협상으로 인 한 미디어 포트 할당의 지연을 방지 해야 하는 경우에의 동기입니다.

다음 표에서는 권장 되는 IPsec 예외 설정에 대해 설명 합니다.

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
<th>프로토콜로</th>
<th>원본 포트</th>
<th>대상 포트</th>
<th>인증 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V에 지 서버 내부 인바운드</p></td>
<td><p>모두</p></td>
<td><p>A/V에 지 서버 내부</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>A/V에 지 서버 외부 인바운드</p></td>
<td><p>모두</p></td>
<td><p>A/V에 지 서버 외부</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>A/V에 지 서버 내부 아웃 바운드</p></td>
<td><p>A/V에 지 서버 내부</p></td>
<td><p>모두</p></td>
<td><p>UDP &amp; TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>A/V에 지 서버 외부 아웃 바운드</p></td>
<td><p>A/V에 지 서버 외부</p></td>
<td><p>모두</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>중재 서버 인바운드</p></td>
<td><p>모두</p></td>
<td><p>중재</p>
<p>서버 (s)</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>중재 서버 아웃 바운드</p></td>
<td><p>중재</p>
<p>서버 (s)</p></td>
<td><p>모두</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>회의 전화 교환 인바운드</p></td>
<td><p>모두</p></td>
<td><p>회의 전화 교환을 실행 하는 프런트 엔드 서버</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>회의 전화 교환 아웃 바운드</p></td>
<td><p>회의 전화 교환을 실행 하는 프런트 엔드 서버</p></td>
<td><p>모두</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>A/V 회의 인바운드</p></td>
<td><p>모두</p></td>
<td><p>프런트 엔드 서버</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>A/V 회의 아웃 바운드</p></td>
<td><p>프런트 엔드 서버</p></td>
<td><p>모두</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 인바운드</p></td>
<td><p>모두</p></td>
<td><p>Exchange 통합 메시징</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 공유 서버 인바운드</p></td>
<td><p>모두</p></td>
<td><p>응용 프로그램 공유 서버</p></td>
<td><p>TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 공유 서버 아웃 바운드</p></td>
<td><p>응용 프로그램 공유 서버</p></td>
<td><p>모두</p></td>
<td><p>TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="even">
<td><p>Exchange 아웃 바운드</p></td>
<td><p>Exchange 통합 메시징</p></td>
<td><p>모두</p></td>
<td><p>UDP 및 TCP</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
<tr class="odd">
<td><p>클라이언트</p></td>
<td><p>모두</p></td>
<td><p>모두</p></td>
<td><p>P</p></td>
<td><p>지정 된 미디어 포트 범위</p></td>
<td><p>모두</p></td>
<td><p>인증 안 함</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

