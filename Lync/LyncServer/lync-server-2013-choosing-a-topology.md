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
ms.openlocfilehash: dc30881da768d8dad9f952df37bdf1accdf091b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지 선택

</div>

<div id="mainSection">

<div id="mainBody">

_**마지막으로 수정 된 항목:** 2013-02-21_

토폴로지를 선택 하는 경우 다음과 같은 지원 되는 토폴로지 옵션 중 하나를 사용할 수 있습니다.

<div>


> [!NOTE]
> 다른 설명이 없는 한 Microsoft Lync Server 2010에 대 한 경험이 있는 경우 여기에 나와 있는 지침이 대부분 변경 되지 않습니다.



</div>

  - [Lync Server 2013의 개인 IP 주소 및 NAT를 포함 하는 단일 통합에 지](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Lync Server 2013의 공용 IP 주소를 포함 하는 단일 통합에 지](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013의 확장 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013의 확장 된 통합에 지, 공용 IP 주소의 DNS 부하 분산](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013의 하드웨어 부하 분산 장치로 확장 된 통합에 지](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> 내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.



</div>

다음 표에는 지원 되는 Microsoft Lync Server 2013 토폴로지에서 사용할 수 있는 기능이 요약 되어 있습니다. 열 머리글은 지정 된에 지 구성 옵션에 사용할 수 있는 기능을 나타냅니다. 예를 들어 배율이 지정 된에 지 (DNS 부하 분산 됨) 옵션을 사용 하는 경우 높은 가용성을 지원 하 고, NAT를 통해 라우팅할 수 없는 개인 IP 주소를 사용 하거나,에 지 외부 인터페이스에 할당 된 라우팅 가능 공용 IP 주소를 이용 하 여 비용을 절감 하는 것을 확인할 수 있습니다. 하드웨어 부하 분산 장치는 필요 하지 않습니다.

DNS 부하 분산에서 지원 되는 Edge 장애 조치 (failover) 시나리오는 Lync-Lync의 지점간 세션, Lync 회의 세션, Lync-PSTN 세션 및 Office 365입니다. DNS 부하 분산에 도움이 되지 않는 Edge 장애 조치 (failover) 시나리오는 원격 사용자 UM (통합 메시징) (Exchange 2010 SP1 이전), 공용 IM (인스턴트 메시징) 연결 및 Office Communications을 실행 하는 서버와의 페더레이션에 대 한 장애 조치 (failover) 서버.

### <a name="summary-of-edge-server-topology-options"></a>에 지 서버 토폴로지 옵션 요약

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
<th>에 지 풀의 외부에 지 서버에 필요한 추가 DNS A 레코드</th>
<th>Lync-Lync 세션에 대 한에 지 장애 조치 (Failover)</th>
<th>Lync to Lync EUM/PIC/OCS 페더레이션 세션에 대 한에 지 장애 조치 (Failover)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NAT를 사용 하는 단일에 지</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>공용 IP를 사용 하는 단일에 지</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>NAT를 사용한 확장 된에 지 (DNS 부하 분산 됨)</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>공용 IP를 사용 하는 확장 된에 지 (DNS 부하 분산 됨)</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>확장 된에 지 하드웨어 부하 분산 됨)</p></td>
<td><p>예</p></td>
<td><p>아니요 (VIP 당 DNS A 레코드 하나)</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
</tbody>
</table>


**\*** 공용 IM (인스턴트 메시징) 연결을 위한 장애 조치 (Failover) 및 Office Communications Server를 실행 하는 서버와의 페더레이션은 DNS 부하 분산에서 사용할 수 없습니다. DNS 부하 분산을 사용 하는 exchange UM (원격 사용자) 장애 조치 (failover)는 Exchange Server 2010 SP1 이상이 필요 합니다.



> [!NOTE]
> 단일에 지 및 확장 된에 지 (DNS 부하 분산 됨) 토폴로지에서 다음을 사용할 수 있습니다.
> <ul><li><p>라우팅 가능한 공용 IP 주소</p></li>
> <li><p>대칭적 NAT (network address translation)를 사용 하는 경우 라우팅할 수 없는 개인 IP 주소</p></li>
>
> <ul><li> NAT와 함께 공용 IP 주소 또는 개인 IP 주소를 사용 하는 경우에도 토폴로지 작성기의 구성 선택에 따라 동일한 개수의 IP 주소를 사용 합니다. 서비스 마다 고유한 포트가 포함 된 단일 IP 주소를 사용 하거나, 서비스 당 고유한 IP 주소를 사용 하 고, 동일한 포트 (기본적으로 TCP 443)를 사용 하도록에 지 서버를 구성할 수 있습니다.</li></ul>>
> NAT와 함께 라우팅할 수 없는 개인 IP 주소를 사용 하기로 결정 한 경우:
> <ul><li><p>세 개의 외부 인터페이스 모두에 대해 라우팅 가능한 개인 IP 주소를 사용 해야 합니다.</p></li>
> <li><p>들어오는 트래픽과 나가는 트래픽에 대해 대칭 NAT를 구성 해야 합니다.</p></li></ul>>
> 확장 된에 지 (하드웨어 부하 분산 됨) 토폴로지는 공용 IP 주소를 사용 해야 합니다.



Lync Server 2013에서는 단일 및 확장 된 통합에 지 서버 토폴로지에 대해 NAT (network address translation)를 수행 하는 라우터나 방화벽 뒤에 있는 액세스, 웹 회의 및 A/V에 지 외부 인터페이스를 사용할 지를 지원 합니다.

모든 에지 외부 인터페이스에 대해 NAT를 사용하려면 DNS 부하 분산을 사용해야 합니다. 하드웨어 부하 분산 장치를 사용 하는 것과 비교할 때 NAT 없이 DNS 부하 분산을 사용 하면 다음 목록에 나와 있는 것 처럼에 지 풀에 있는 대 중 서버당 공용 IP 주소 수를 줄일 수 있습니다.

  - Lync Server 2013 확장 통합에 지 (DNS 부하 분산 됨)에는에 지 풀의 각에 지 서버에 대해 세 개의 공용 IP 주소가 필요 합니다.

  - Lync Server 2013 확장 통합에 지 (하드웨어 부하 분산 됨)에는 부하 분산 장치 가상 IP 주소에 대 한 세 가지 공용 IP 주소 (풀에 더 많은에 지 서버를 추가 하는 데 사용할 수 있는 한 가지 공용 IP 주소)가 필요 합니다. 풀의에 지 서버

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>확장 통합에 지에 대 한 IP 주소 요구 사항 (역할별 IP 주소)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>풀당 에지 서버 수</th>
<th>필요한 IP 주소 수 Lync Server 2013 (DNS 부하 분산 됨)</th>
<th>필요한 IP 주소 수 Lync Server 2013 (하드웨어 부하 분산 됨)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>6 </p></td>
<td><p>3개(VIP당 1개) + 6개</p></td>
</tr>
<tr class="even">
<td><p>3(sp3)</p></td>
<td><p>9 </p></td>
<td><p>3개(VIP당 1개) + 9개</p></td>
</tr>
<tr class="odd">
<td><p>1-4</p></td>
<td><p>12</p></td>
<td><p>3개(VIP당 1개) + 12개</p></td>
</tr>
<tr class="even">
<td><p>2-5</p></td>
<td><p>15 </p></td>
<td><p>3개(VIP당 1개) + 15개</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>확장 통합에 지에 대 한 IP 주소 요구 사항 (모든 역할에 대 한 단일 IP 주소)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>풀당 에지 서버 수</th>
<th>필요한 IP 주소 수 Lync Server 2013 (DNS 부하 분산 됨)</th>
<th>필요한 IP 주소 수 Lync Server 2013 (하드웨어 부하 분산 됨)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>2</p></td>
<td><p>1 개 (VIP 당 1 개) + 2 개</p></td>
</tr>
<tr class="even">
<td><p>3(sp3)</p></td>
<td><p>3(sp3)</p></td>
<td><p>1 (VIP 당 1 개) + 3 개</p></td>
</tr>
<tr class="odd">
<td><p>1-4</p></td>
<td><p>1-4</p></td>
<td><p>1 (VIP 당 1 개) + 4 개</p></td>
</tr>
<tr class="even">
<td><p>2-5</p></td>
<td><p>2-5</p></td>
<td><p>1 개 (VIP 당 1 개) + 5 개</p></td>
</tr>
</tbody>
</table>


토폴로지 선택에 대 한 기본 결정 사항은 고가용성 및 부하 분산입니다. 고가용성에 대 한 요구 사항은 부하 분산 결정에 영향을 줄 수 있습니다.

  - **고가용성**   고가용성이 필요한 경우 풀에 적어도 두 개의에 지 서버를 배포 합니다. 단일에 지 풀은 최대 12 개의에 지 서버를 지원 합니다. 용량이 더 필요한 경우에는 여러 개의에 지 풀을 배포할 수 있습니다. 일반적으로 지정 된 사용자 기준의 10%에는 외부 액세스가 필요 합니다.
    
    <div>
    

    > [!IMPORTANT]
    > 토폴로지 작성기를 사용 하면 단일에 지 풀에서 최대 20 개의에 지 서버를 구성할 수 있습니다. 풀에서 테스트 및 지원 되는 최대 Edge 서버 수는 12이 고 12 보다 큰 수를 허용 하는 토폴로지 작성기는 단일에 지 풀에 있는 12 개 이상의에 지 서버에 대 한 묵시적 지원으로 무한대 간주 수 없습니다.

    
    </div>

  - **하드웨어 부하 분산**   에 지 외부 인터페이스에 대해 공용으로 라우팅할 수 있는 IP 주소를 사용 하면 Lync Server 2013에 지 서버에 대 한 부하 분산을 위해 하드웨어 부하 분산이 지원 됩니다. 예를 들어 다음 응용 프로그램에 대해 장애 조치 (failover)가 필요한 상황에서이 방법을 사용할 수 있습니다.
    
      - 공용 IM 연결
    
      - Microsoft Office Communications Server 2007 또는 Microsoft Office Communications Server 2007 R2를 실행 하는 회사와의 페더레이션
    
      - Exchange 2007 UM (통합 메시징) 또는 Exchange 2010 UM에 대 한 외부 액세스
        
        <div>
        

        > [!IMPORTANT]
        > Exchange UM에 대해 Exchange 2010 SP1 및 최신 버전에 대 한 DNS 부하 분산은 지원 됩니다.

        
        </div>
    
    이러한 세 응용 프로그램은 계속 작동 하지만 DNS 부하 분산을 고려 하지 않으며 풀의 첫 번째에 지 서버에만 연결 됩니다. 해당 서버를 사용할 수 없으면 연결이 실패 합니다. 예를 들어 페더레이션 트래픽 부하를 처리 하기 위해 풀에 여러 개의에 지 서버가 배포 되는 경우 한 액세스 프록시는 실제로 트래픽을 하나만 수신 하 고 나머지는 유휴 상태를 유지 합니다.

<div>


> [!IMPORTANT]
> Lync Server 2010 및 Microsoft Office 365을 사용 하 여 회사와 페더레이션 하는 경우 DNS 부하 분산을 사용 하는 것이 좋습니다. 대부분의 페더레이션 파트너가 Office Communications Server 2007 또는 Office Communications Server 2007 r 2를 사용 하는 경우에는 성능이 크게 저하 된다는 점을 염두에 두어야 합니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

