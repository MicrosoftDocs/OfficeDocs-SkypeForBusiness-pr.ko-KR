---
title: 'Lync Server 2013: 토폴로지 선택'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9f59648d845f37c7cf6d92c471b81a29415753
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지 선택

</div>

<div id="mainSection">

<div id="mainBody">

_**마지막으로 수정한 주제:** 2013-02-21_

토폴로지를 선택 하면 다음과 같은 지원 되는 토폴로지 옵션 중 하나를 사용할 수 있습니다.

<div>


> [!NOTE]
> 다른 언급이 없는 한, Microsoft Lync Server 2010에 대 한 경험이 있는 경우 여기에 나와 있는 지침이 대부분 변경 되지 않습니다.



</div>

  - [Lync Server 2013의 개인 IP 주소 및 NAT 사용 단일 통합 에지](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Lync Server 2013의 공용 IP 주소의 단일 통합 에지](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013의 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013의 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013의 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> 내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.



</div>

다음 표에서는 지원 되는 Microsoft Lync Server 2013 토폴로지에서 사용할 수 있는 기능을 요약 하 여 설명 합니다. 열 머리글은 해당 Edge 구성 옵션에 대해 사용할 수 있는 기능을 나타냅니다. 크기가 조정 된 가장자리 (DNS 부하 분산) 옵션을 사용 하는 경우 높은 가용성을 지원할 수 있으며, 외부 인터페이스에 지정 된 라우팅 불가능 한 개인 IP 주소 또는 라우팅 가능한 공용 IP 주소를 사용 하 여 비용을 줄일 수 있습니다. 하드웨어 로드 균형 조정기는 필요 하지 않습니다.

DNS 부하 분산에서 지원 되는 Edge 장애 조치 시나리오는 Lync에서 Lync를 사용 하는 지점간 세션, Lync 회의 세션, Lync-PSTN 세션 및 Office 365입니다. DNS 부하 분산에 도움이 되지 않는 Edge 장애 조치 시나리오는 원격 사용자의 Exchange UM (통합 메시징), Exchange 2010 SP1 이전 버전, 공용 인스턴트 메시징 (IM) 연결, Office Communications을 실행 하는 서버와의 페더레이션 등의 장애 조치입니다. Server.

### <a name="summary-of-edge-server-topology-options"></a>Edge 서버 토폴로지 옵션 요약

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>토폴로지</th>
<th>고가용성</th>
<th>Edge 풀의 외부에 지 서버에 필요한 추가 DNS 레코드</th>
<th>Lync에서 Lync 용 세션에 대 한 Edge 장애 조치</th>
<th>Lync to Lync EUM/PIC/OCS 페더레이션 세션에 대 한 Edge 장애 조치</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NAT를 사용 하 여 단일 쪽</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>공용 IP를 사용 하는 단일 쪽</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>NAT를 사용 하 여 크기가 조정 된 Edge (DNS 부하 분산)</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>공용 IP를 사용 하 여 크기가 조정 된 Edge (DNS 부하 분산)</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>확장 된 Edge 하드웨어 부하 분산)</p></td>
<td><p>예</p></td>
<td><p>없음 (VIP 당 하나의 DNS A 레코드)</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
</tbody>
</table>


**\*** DNS 부하 분산에서는 공용 IM (인스턴트 메시징) 연결에 대 한 장애 조치 및 Office Communications Server를 실행 하는 서버와의 페더레이션을 사용할 수 없습니다. DNS 부하 분산을 사용 하는 exchange UM (원격 사용자) 장애 조치 (failover)에는 Exchange Server 2010 SP1 이상 버전이 필요 합니다.



> [!NOTE]
> 단일 모서리 및 배율 조정 된 모서리 (DNS 부하 분산) 토폴로지에서 다음을 사용할 수 있습니다.
> <ul><li><p>라우팅할 수 있는 공용 IP 주소</p></li>
> <li><p>대칭적 NAT (network address translation)를 사용 하는 경우 라우팅할 수 없는 개인 IP 주소</p></li>
>
> <ul><li> NAT에서 공용 IP 주소 또는 개인 IP 주소를 사용 하는 경우에도 토폴로지 작성기의 구성 선택에 따라 동일한 수의 IP 주소를 사용 하 게 됩니다. 각 서비스에 대 한 고유 포트를 사용 하 여 단일 IP 주소를 사용 하거나, 서비스 별로 고유한 IP 주소를 사용 하 되, 동일한 포트 (기본적으로 TCP 443)를 사용 하도록 Edge 서버를 구성할 수 있습니다.</li></ul>>
> NAT에서 라우팅할 수 없는 개인 IP 주소를 사용 하기로 결정 한 경우:
> <ul><li><p>세 개의 외부 인터페이스 모두에서 라우팅할 수 있는 개인 IP 주소를 사용 해야 합니다.</p></li>
> <li><p>들어오고 나가는 트래픽에 대해 대칭 NAT를 구성 해야 합니다.</p></li></ul>>
> 크기가 조정 된 Edge (하드웨어 부하 분산) 토폴로지에서는 공용 IP 주소를 사용 해야 합니다.



Lync Server 2013는 단일 및 배율 통합 된 Edge 서버 토폴로지에 대해 NAT (network address translation)를 수행 하는 라우터 또는 방화벽 뒤에 Access, 웹 회의 및 A/V 경계 외부 인터페이스를 지원 합니다.

모든 Edge 외부 인터페이스에 NAT를 사용 하려면 DNS 부하 분산을 사용 해야 합니다. 하드웨어 부하 분산 장치를 사용 하는 것과 비교해 볼 때 NAT 없이 DNS 부하 분산을 사용 하면 다음 목록에 나와 있는 것 처럼 Edge 풀에 있는 Edge 당 공용 IP 주소 수를 줄일 수 있습니다.

  - Lync Server 2013 배율 조정 된 통합 된 Edge (DNS 부하 분산)에는 edge 풀의 각 Edge 서버에 대 한 세 가지 공용 IP 주소가 필요 합니다.

  - Lync Server 2013 배율 통합 된 가장자리 (하드웨어 부하 분산)에는 부하 분산 장치 가상 IP 주소에 대 한 세 가지 공용 IP 주소 (더 많은 Edge 서버를 풀에 추가 하는 데 사용 되지 않는 한 가지) 및 다음 당 세 개의 공용 IP 주소가 필요 합니다. 풀의 Edge 서버.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>확장 통합 된 가장자리에 대 한 IP 주소 요구 사항 (역할별 IP 주소)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>풀 당 Edge 서버 수</th>
<th>필요한 IP 주소 수 Lync Server 2013 (DNS 부하 분산)</th>
<th>필요한 IP 주소 수 Lync Server 2013 (하드웨어 부하 분산)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>26</p></td>
<td><p>3 (VIP 당 1 개) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>되었는지</p></td>
<td><p>3 (VIP 당 1 개) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4(tcp/ipv4)</p></td>
<td><p>까지</p></td>
<td><p>3 (VIP 당 1 개) + 12</p></td>
</tr>
<tr class="even">
<td><p>5mb</p></td>
<td><p>~</p></td>
<td><p>3 (VIP 당 1) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>확장 통합 된 가장자리에 대 한 IP 주소 요구 사항 (모든 역할의 단일 IP 주소)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>풀 당 Edge 서버 수</th>
<th>필요한 IP 주소 수 Lync Server 2013 (DNS 부하 분산)</th>
<th>필요한 IP 주소 수 Lync Server 2013 (하드웨어 부하 분산)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>2</p></td>
<td><p>1 (VIP 당 1 개) + 2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>1 (VIP 당 1 개) + 3</p></td>
</tr>
<tr class="odd">
<td><p>4(tcp/ipv4)</p></td>
<td><p>4(tcp/ipv4)</p></td>
<td><p>1 (VIP 당 1 개) + 4</p></td>
</tr>
<tr class="even">
<td><p>5mb</p></td>
<td><p>5mb</p></td>
<td><p>1 (VIP 당 1 개) + 5</p></td>
</tr>
</tbody>
</table>


토폴로지 선택에 대 한 기본 결정 사항은 고가용성 및 부하 분산입니다. 고가용성을 위한 요구 사항은 부하 분산 결정에 영향을 미칠 수 있습니다.

  - **고가용성**   높은 가용성을 필요로 하는 경우 풀에 Edge 서버를 두 개 이상 배포 합니다. 단일 Edge 풀은 최대 12 대의 Edge 서버를 지원 합니다. 용량이 더 필요한 경우 여러 Edge 풀을 배포할 수 있습니다. 일반적으로 지정 된 사용자 기반의 10%는 외부 액세스가 필요 합니다.
    
    <div>
    

    > [!IMPORTANT]
    > 토폴로지 작성기를 사용 하면 단일 Edge 풀에서 최대 20 개의 Edge 서버를 구성할 수 있습니다. 풀에서 테스트 되 고 지원 되는 최대 Edge 서버 수는 12 개 보다 더 많은 수를 허용 하는 토폴로지 작성기는 단일 Edge 풀에 있는 12 개 이상의 Edge 서버에 대해 암시적인 지원으로 construed 수 없습니다.

    
    </div>

  - **하드웨어 부하 분산**   경계 외부 인터페이스에 대해 공개적으로 라우팅할 수 있는 IP 주소를 사용 하는 경우 Lync Server 2013 Edge 서버의 부하 분산에 대해 하드웨어 부하 분산이 지원 됩니다. 예를 들어 다음 응용 프로그램에 대해 장애 조치가 필요한 경우에이 방법을 사용 합니다.
    
      - 공용 메신저 연결
    
      - Microsoft Office Communications Server 2007 또는 Microsoft Office Communications Server 2007 R2를 실행 하는 회사와의 페더레이션
    
      - Exchange 2007 UM (통합 메시징) 또는 Exchange 2010 UM에 대 한 외부 액세스
        
        <div>
        

        > [!IMPORTANT]
        > Exchange 2010 SP1 이상에 대 한 DNS 부하 분산이 Exchange UM에 대해 지원 됩니다.

        
        </div>
    
    이러한 세 가지 응용 프로그램은 계속 작동 하지만 DNS 부하 분산을 인식 하지 않으며 풀의 첫 번째 Edge 서버에만 연결 됩니다. 해당 서버를 사용할 수 없는 경우에는 연결에 실패 하 게 됩니다. 예를 들어 페더레이션 트래픽 로드를 처리 하기 위해 풀에 여러 Edge 서버가 배포 되는 경우 한 액세스 프록시는 다른 사용자가 유휴 상태에 있는 동안 실제로 트래픽을 받습니다.

<div>


> [!IMPORTANT]
> Lync Server 2010 및 Microsoft Office 365를 사용 하 여 회사와 페더레이션 하는 경우 DNS 부하 분산을 사용 하는 것이 좋습니다. 대부분의 페더레이션 파트너가 Office Communications Server 2007 또는 Office Communications Server 2007 R2를 사용 하는 경우 성능이 크게 저하 된다는 점에 주의 하세요.



</div>

</div>

<span> </span>

</div>

</div>

</div>

