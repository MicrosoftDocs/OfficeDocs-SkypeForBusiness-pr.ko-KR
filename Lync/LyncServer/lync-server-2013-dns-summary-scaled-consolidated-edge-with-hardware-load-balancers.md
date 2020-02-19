---
title: DNS 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c45802282c57ebcf80fbc55b030c985fe7d977cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013의 DNS 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-27_

Lync Server 2013에 대 한 원격 액세스에 대 한 DNS 레코드 요구 사항은 인증서 및 포트의 경우와 비교 하는 것이 아주 간단 합니다. 또한 대부분의 레코드는 Lync 2013를 실행 하는 클라이언트를 구성 하는 방법과 페더레이션을 사용 하는지 여부에 따라 선택적입니다.

Lync 2013 DNS 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)을 참조 하십시오.

분할로 인 한 DNS가 구성 되지 않은 경우 Lync 2013 클라이언트의 자동 구성을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)의 "자동 구성 (분할 되지 않은 dns)" 섹션을 참조 하십시오.

다음 표에는 확장된 통합 에지 토폴로지(하드웨어 부하 분산) 그림을 지원하는 데 필요한 DNS 레코드에 대한 요약이 포함되어 있습니다. 특정 DNS 레코드는 Lync 클라이언트에 대 한 자동 구성에만 필요 합니다. Gpo (그룹 정책 개체)를 사용 하 여 Lync 클라이언트를 구성 하려는 경우에는 관련 레코드가 필요 하지 않습니다.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>중요:에 지 서버 네트워크 어댑터 요구 사항

라우팅 문제를 방지 하려면에 지 서버에 네트워크 어댑터가 두 개 이상 있는지, 그리고 외부 인터페이스와 연결 된 네트워크 어댑터에만 기본 게이트웨이가 설정 되었는지 확인 합니다. 예를 들어, [Lync Server 2013의 하드웨어 부하 분산 장치를 사용 하 여 확장 된 통합](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)에 지에 따라 확장 된 통합에 지 시나리오 그림에 나와 있는 것 처럼 기본 게이트웨이는 외부 방화벽을 가리킵니다.

다음과 같이 각에 지 서버에 두 개의 네트워크 어댑터를 구성할 수 있습니다.

  - **네트워크 어댑터 1(내부 인터페이스)**
    
    172.25.33.10이 지정된 내부 인터페이스입니다.
    
    기본 게이트웨이는 없습니다.
    
    에 지 서버 내부 인터페이스를 포함 하는 네트워크에서 lync server를 실행 하는 네트워크 (예: 172.25.33.0에서 192.168.10.0로)에 대 한 경로가 있는지 확인 합니다.

  - **네트워크 어댑터 2(외부 인터페이스)**
    
    이 네트워크 어댑터에는 세 개의 공용 IP 주소가 할당 됩니다 (예: 액세스에 지 서비스의 경우 131.107.155.10, 131.107.155.20에 대 한 웹 회의에 지 서비스의 경우 131.107.155.30 for A/V에 지 서비스의 경우).
    
    <div>
    

    > [!NOTE]
    > 에 지 서버의 실제 외부 네트워크 인터페이스에 할당 되는 IP 주소는 선택한 하드웨어 부하 분산 장치에 따라 달라질 수 있습니다. 실제 IP 주소 요구 사항을 이해 하려면 하드웨어 부하 분산 장치 설명서를 참조 하세요.<BR>권장되지는 않지만 세 개의 모든 에지 서비스 인터페이스에 대해 단일 IP 주소를 사용할 수도 있습니다. 이렇게 해서 IP 주소를 절약할 수는 있지만 각 서비스에 대해 서로 다른 포트 번호가 필요합니다. 기본 포트 번호는 대부분의 원격 방화벽에서 트래픽을 허용하도록 보장하는 443/TCP입니다. 포트 값을 다음으로 변경 (예: 액세스에 지 서비스의 경우), A/V에 지 서비스의 경우 444/tcp를 사용 하는 경우 원격 사용자에 게 문제가 발생할 수 있는데,이 경우 해당 방화벽에서 들어오는 방화벽이 5061/tcp 및 444/tcp를 통해 트래픽을 허용 하지 않습니다. 또한 세 개의 고유 IP 주소를 사용하면 IP 주소로 필터링할 수 있기 때문에 문제 해결에도 더 유리합니다.

    
    </div>
    
    액세스에 지 서비스 IP 주소는 기본 게이트웨이가 인터넷 연결 라우터 (131.107.155.1)로 설정 되어 있습니다.
    
    웹 회의에 지 서비스 및 A/V에 지 서비스 IP 주소 보조입니다.

<div>


> [!TIP]
> 두 개의 네트워크 어댑터를 사용 하 여에 지 서버를 구성 하는 방법은 두 가지 옵션 중 하나입니다. 또 다른 옵션은에 지 서버의 외부에 세 개의 네트워크 어댑터와 내부 측면에 대해 하나의 네트워크 어댑터를 사용 하는 것입니다. 이 옵션의 주요 이점은 각에 지 서버 서비스에 대 한 고유한 네트워크 어댑터 이며, 문제 해결이 필요한 경우 데이터 수집이 더 간결 해질 수 있습니다.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>확장된 통합 에지, 하드웨어 부하 분산에 필요한 DNS 레코드(예제)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Location/TYPE/Port</th>
<th>FQDN/DNS 레코드</th>
<th>IP 주소/FQDN</th>
<th>매핑 대상/설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>액세스에 지 서비스 외부 인터페이스 (Contoso) Lync를 사용하도록 설정된 사용자가 포함된 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>웹 회의에 지 서비스 외부 인터페이스</p></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V에 지 서비스 외부 인터페이스</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/SRV/443</p></td>
<td><p>_sip _tls. contoso.</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>액세스에 지 서비스 외부 인터페이스 Lync 2013 및 Lync 2010 클라이언트가 외부적으로 작동 하도록 자동으로 구성 하는 데 필요 합니다. Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</p></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp. contoso.</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 액세스에 지 서비스 외부 인터페이스 페더레이션 파트너의 자동 DNS 검색에 필요한 "허용 된 SIP 도메인" (이전 릴리스의 향상 된 페더레이션 이라고 함)입니다. Lync를 사용할 수 있는 모든 SIP 도메인 및 푸시 알림 서비스 또는 Apple 푸시 알림 서비스를 사용 하는 Microsoft Lync 모바일 클라이언트에 대해 필요에 따라 반복</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10이 지정</p></td>
<td><p>통합 에지 내부 인터페이스</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

