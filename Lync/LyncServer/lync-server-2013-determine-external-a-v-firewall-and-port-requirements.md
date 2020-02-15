---
title: 'Lync Server 2013: 외부 A/V 방화벽 및 포트 요구 사항 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f44e23cdc60251df4ea3f4071805d9367eef84
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

A/V (오디오/비디오) 통신은 복잡할 수 있습니다. A/V에서 사용 되는 프로토콜의 특성 및 클라이언트와 서버에서 프로토콜을 사용 하는 방법 때문에 클라이언트와 서버 버전 간의 차이점을 설명 하기 위해 특수 섹션을 사용할 수 있습니다.

다음 A/V 방화벽과 Port 테이블을 사용 하 여 방화벽 요구 사항 및 열 포트를 확인 합니다. 그런 다음 NAT (network address translation) 용어를 다양 한 방식으로 구현할 수 있으므로이를 검토 합니다. 방화벽 포트 설정에 대 한 자세한 예는 [Lync Server 2013의 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)의 참조 아키텍처를 참조 하십시오.

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>UDP 및 TCP의 일반 프로토콜 사용량 (오디오/비디오 및 미디어 트래픽)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>오디오/비디오 전송</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>P</p></td>
<td><p>오디오 및 비디오에 대 한 기본 설정 전송 계층 프로토콜</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>오디오 및 비디오용 대체 전송 계층 프로토콜</p>
<p>Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013에 대 한 응용 프로그램 공유를 위한 필수 전송 계층 프로토콜</p>
<p>Lync Server 2010 및 Lync Server 2013에 파일을 전송 하기 위한 필수 전송 계층 프로토콜</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>외부 사용자 액세스를 위한 외부 A/V 방화벽 포트 요구 사항

외부 (및 내부) SIP 및 회의 인터페이스에 대 한 방화벽 포트 요구 사항은 클라이언트 버전 또는 페더레이션 파트너의 버전에 관계 없이 일관성을 유지 하는 것입니다.

오디오/비디오에 지 외부 인터페이스의 경우에도 마찬가지입니다. Office Communications Server 2007의 페더레이션에서는 A/V에 지 서비스를 통해 5만에서 59999 포트 범위에 RTP/TCP 및 RTP/UDP 트래픽이 양방향으로 전달 되도록 하는 외부 방화벽 규칙을 사용 해야 합니다. 위 표에서는 Lync Server 2013이 기본 페더레이션 파트너가 고 나열 된 다른 페더레이션 파트너 유형 중 하 나와 통신 하도록 구성 되는 것으로 가정 합니다.

50000-59999의 오디오/비디오 포트 범위를 구성 하는 것은 포트 범위에 페더레이션 파트너와의 통신을 위한 원본 포트가 포함 되어야 한다는 것을 고려해 야 합니다. 자세한 내용은 페더레이션 파트너에서 통신을 시작 하는 것을 고려해 야 합니다. 59999 범위의 A/V에 지 서비스 포트에서 전달 되는 통신은 파트너의 A/V에 지 서비스에 대해 예상 되는 포트 TCP 443에 연결 됩니다. 반대로 A/V에 지 서비스 포트 TCP 443에 대 한 인바운드 트래픽은 50000-59999 범위의 원본 포트를 갖게 됩니다.

방화벽 관리를 위한 방화벽과 정책에 따라 대상 규칙만 구성 해야 할 수도 있고, 구성 해야 하는 원본 및 대상이 둘 다 필요할 수도 있습니다. 대상 포트에 한 해 요구 사항이 있는 경우 오디오/비디오 요구 사항은 다음과 같습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>원본 IP</th>
<th>대상 IP</th>
<th>대상 포트</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V에 지 서비스 인터페이스</p></td>
<td><p>모두</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V에 지 서비스 인터페이스</p></td>
<td><p>모두</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>모두</p></td>
<td><p>A/V에 지 서비스 인터페이스</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>모두</p></td>
<td><p>A/V에 지 서비스 인터페이스</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


정책에 따라 인바운드 및 아웃 바운드 방화벽 규칙 정의가 모두 필요한 경우 오디오/비디오 요구 사항은 다음과 같습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>원본 IP</th>
<th>대상 IP</th>
<th>원본 포트</th>
<th>대상 포트</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V에 지 서비스 인터페이스</p></td>
<td><p>모두</p></td>
<td><p>TCP 50000-59999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V에 지 서비스 인터페이스</p></td>
<td><p>모두</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>모두</p></td>
<td><p>A/V에 지 서비스 인터페이스</p></td>
<td><p>모두</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>모두</p></td>
<td><p>A/V에 지 서비스 인터페이스</p></td>
<td><p>모두</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007에는 약간 다른 구성이 필요 합니다. 50000-59999의 TCP 및 UDP 포트 범위는 inbound 및 outbound를 열어야 합니다. 이 요구 사항은 Office Communicator 2007에만 해당 됩니다. Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013에만 TCP 범위 50000-59999 open outbound가 필요 합니다.



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>에 지 서비스에 대 한 NAT 요구 사항

에 지 서비스에 대해 라우팅할 수 없는 개인 IP 주소를 구성 하도록 선택한 경우 다음 NAT 요구 사항이 적용 됩니다.

  - NAT는 DNS 부하 분산에만 사용할 수 있습니다. NAT는 HLB (하드웨어 부하 분산)에 지 토폴로지에서 지원 되지 않습니다.

  - NAT는 외부에 지 인터페이스 에서만 사용할 수 있습니다. NAT는 내부에 지 인터페이스에서 지원 되지 않습니다.

  - 들어오는 트래픽과 나가는 트래픽에 대해 NAT가 대칭적 이어야 합니다.
    
  - 인터넷 트래픽의 경우 NAT는 A/V에 지 서비스의 NAT 사용 가능 공용 IP 주소에서 외부 IP 주소로 대상 IP 주소를 변경 해야 합니다. A/V에 지 서비스가 최적의 미디어 경로를 찾을 수 있도록 원본 IP 주소는 그대로 유지 되어야 합니다.
  
  예를 들어 아래 그림의 인바운드 방향에서 공용 IP 주소 131.107.155.30은 외부 (개인) IP 주소 10.45.16.10로 변경 되었습니다. 원본 IP 주소가 변경 되지 않은 상태로 유지 되었습니다.
  
  - A/V에 지 서비스에서 인터넷으로 전송 하는 경우 NAT는 A/V에 지 서비스의 외부 IP 주소에서 NAT 사용 공용 IP 주소로의 원본 IP 주소를 변경 해야 합니다.

예를 들어 아래 그림의 아웃 바운드 방향에서 외부 (개인) IP 주소 10.45.16.10 공용 IP 주소 131.107.155.30로 변경 되었습니다.

**아래 그림은 NAT에서 인바운드 트래픽에 대 한 대상 IP 주소와 아웃 바운드 트래픽의 원본 IP 주소를 변경 하는 방법을 보여줍니다.**

![대상/원본 IP 주소 변경](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "대상/원본 IP 주소 변경")

핵심 사항은 다음과 같습니다.

  - A/V에 지 서비스를 실행 하는 서버에 인바운드 되는 트래픽 원본 IP 주소는 변경 되지 않지만 대상 IP 주소는 131.107.155.30에서 10.45.16.10의 변환 된 IP 주소로 변경 됩니다.

  - A/V에 지 서비스를 실행 하는 서버에서 워크스테이션으로 다시 아웃 바운드 되는 트래픽은 원본 IP 주소가 서버의 공용 IP 주소에서 A/V에 지 서비스를 실행 하는 서버의 공용 IP 주소로 변경 됩니다. 대상 IP는 워크스테이션의 공용 IP 주소를 유지 합니다. 패킷이 첫 번째 NAT 장치 아웃 바운드로 나간 후에 NAT 장치의 규칙은 A/V에 지 서비스 외부 인터페이스 IP 주소 (10.45.16.10)를 실행 하는 서버의 원본 IP 주소를 해당 공용 IP 주소 (131.107.155.30)로 변경 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

