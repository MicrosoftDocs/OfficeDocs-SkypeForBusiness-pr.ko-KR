---
title: Lync Server 2013 서버 하드웨어 플랫폼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95c8b0e9b1e13d845672cff07d30b7f2ac1a5b22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Lync Server 2013의 서버 하드웨어 플랫폼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-07-28_

Lync server 2013 서버 역할 및 Lync Server 관리 도구를 실행 하는 컴퓨터에는 64 비트 하드웨어가 필요 합니다.

Lync Server 2013 배포에 사용 되는 특정 하드웨어는 크기 및 사용 요구 사항에 따라 다를 수 있습니다. 이 섹션에서는 권장 하드웨어에 대해 설명 합니다. 이는 권장 사항은 아니지만 이러한 권장 사항을 충족 하지 않는 하드웨어를 사용 하는 경우 중대 한 성능 문제 및 기타 문제가 발생할 수 있습니다.

<div>

## <a name="recommended-hardware-platform"></a>권장 하드웨어 플랫폼

최상의 성능을 위해서는 다음 표의 요구 사항에 맞는 하드웨어를 사용 하 여 서버에서 Lync Server를 실행 하는 것이 좋습니다. 덜 강력한 하드웨어를 사용 하는 경우 기능에 문제가 있거나 성능이 저하 될 수 있습니다. 이러한 하드웨어 요구 사항은 주로 Lync Server 2013, 모든 프런트 엔드 서버에서 SQL Server를 실행 하기 때문에 이전 버전의 Lync Server 보다 더 높습니다.

<div>


> [!NOTE]  
> NIC 팀은 지원 되며 Lync Server에 투명 해야 합니다. 자세한 내용은 <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">통신 서버 또는 Lync 서버 및 네트워크 어댑터 팀 구성을</A>참조 하세요.



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>프론트 엔드 서버용 권장 하드웨어, 백 엔드 서버, 스탠더드 버전 서버, 영구 채팅 서버, 영구 채팅 및 영구 채팅 준수 저장소 (영구 채팅 서버용 백 엔드 서버 역할)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>하드웨어 구성 요소</th>
<th>권장</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>%</p></td>
<td><p>64 비트 듀얼 프로세서, 16 진수 코어, 2.26 ghz 이상.</p>
<p>인텔 아이테니엄 프로세서는 Lync Server 서버 역할에 지원 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Memory</p></td>
<td><p>32 기가바이트 (GB).</p></td>
</tr>
<tr class="odd">
<td><p>공간</p></td>
<td><ul>
<li><p>최소 72 GB의 사용 가능한 디스크 공간을 갖춘 8 개 이상의 1만 RPM 하드 디스크 드라이브.</p>
<p>두 개의 디스크에서 RAID 1을 사용 하 고 6 개는 RAID 10을 사용 해야 합니다.</p>
<p>-또는</p></li>
<li><p>8 1만-RPM 기계 디스크 드라이브와 유사한 성능을 제공 하는 Ssd (고체 스테이트 드라이브).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>네트워크</p></td>
<td><ul>
<li><p>1 개의 듀얼 포트 네트워크 어댑터, 1Gbps 이상 (2 권장, 단일 MAC 주소 및 단일 IP 주소를 사용 하는 팀이 필요 함)</p>
<div>

> [!NOTE]  
> 프런트 엔드 서버, 백 엔드 서버, Standard Edition 서버 및 영구 채팅 서버에서는 듀얼 또는 멀티홈 구성이 지원 되지 않습니다.<BR>ILO/DRAC/기타. 운영 체제에 표시 되지 않고 서버 하드웨어를 모니터링 하 고 관리 하는 데 사용 되는 연결은 멀티홈 서버를 구성 하지 않으므로 지원 됩니다.


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>Edge 서버, 독립 실행형 중재 서버 및 디렉터에 권장 되는 하드웨어

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>하드웨어 구성 요소</th>
<th>권장</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>%</p></td>
<td><ul>
<li><p>64 비트 듀얼 프로세서, 쿼드 코어, 2.0 ghz 이상</p>
<p>-또는</p></li>
<li><p>64 비트 4 방향 프로세서, 듀얼 코어, 2.0 GHz 이상.</p></li>
</ul>
<p>인텔 아이테니엄 프로세서는 Lync Server 서버 역할에 지원 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Memory</p></td>
<td><p>16gb (GB).</p></td>
</tr>
<tr class="odd">
<td><p>공간</p></td>
<td><ul>
<li><p>최소 72 GB의 사용 가능한 디스크 공간을 제공 하는 4 개 이상의 1만 RPM 하드 디스크 드라이브.</p>
<p>디스크는 2 배로 RAID 1에 구성 되어 있어야 합니다.</p>
<p>-또는</p></li>
<li><p>4 1만-RPM 기계 디스크 드라이브와 유사한 성능을 제공 하는 Ssd (고체 스테이트 드라이브).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>네트워크</p></td>
<td><ul>
<li><p>1 개의 듀얼 포트 네트워크 어댑터, 1Gbps 이상 (2 권장, 단일 MAC 주소 및 단일 IP 주소를 사용 하는 팀이 필요 함) 2 네트워크 인터페이스는 Edge 서버에 필요 하며 독립 실행형 중재 서버에서 지원 됩니다.</p></li>
</ul>
<div>

> [!NOTE]  
> 이중 또는 멀티홈 구성은 디렉터에서 지원 되지 않습니다.<BR>ILO/DRAC/기타. 운영 체제에 표시 되지 않고 서버 하드웨어를 모니터링 하 고 관리 하는 데 사용 되는 연결은 멀티홈 서버를 구성 하지 않으므로 지원 됩니다.


</div>
<p>Edge 서버에는 이중 포트 네트워크 어댑터용 1 Gbps 이상 (또는 두 개의 연결 된 네트워크 어댑터와 총 4 개, 단일 MAC 주소와 단일 IP 주소로 그룹화 된 각 쌍 중 총 2 쌍) 인 2 개의 네트워크 인터페이스가 필요 합니다.</p>
<p>독립 실행형 중재 서버에서 특정 PSTN IP 주소 구성을 허용 하는 추가 Nic (네트워크 인터페이스 카드)를 설치 하는 것이 지원 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

