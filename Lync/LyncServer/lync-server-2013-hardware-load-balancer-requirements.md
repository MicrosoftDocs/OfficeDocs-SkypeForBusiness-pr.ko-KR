---
title: Lync Server 2013 하드웨어 부하 분산 장치 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bb8c3ff97930411cb8d679054015ffc18ab3ce2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Lync Server 2013에 대 한 하드웨어 부하 분산 장치 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-05-11_

Lync Server 2013 확장 통합에 지 토폴로지는 기본적으로 Lync Server를 사용 하는 다른 조직과 함께 새 배포에 대 한 DNS 부하 분산에 최적화 되어 있습니다. 다음과 같은 시나리오에 고가용성이 필요한 경우에는 에지 서버 풀에서 다음에 대해 하드웨어 부하 분산 장치를 사용해야 합니다.

  - Office Communications Server 2007 R2 또는 Office Communications Server 2007을 사용 하는 조직과의 페더레이션

  - Exchange 2010 SP1 이전 버전에서 exchange UM을 사용 하는 원격 사용자를 위한 exchange UM

  - 공용 IM 사용자 연결

<div>


> [!IMPORTANT]  
> DNS 부하 분산과 하드웨어 부하 분산을 서로 다른 인터페이스에서 사용할 수 없습니다. 두 인터페이스에서 모두 하드웨어 부하 분산 또는 DNS 부하 분산을 사용해야 합니다.



</div>

<div>


> [!NOTE]  
> 하드웨어 부하 분산 장치를 사용하는 경우, 내부 네트워크와의 연결을 위해 배포된 부하 분산 장치는 액세스 에지 서비스와 A/V 에지 서비스를 실행 중인 서버의 트래픽 부하만 분산하도록 구성해야 합니다. 즉, 이 부하 분산 장치를 사용하여 내부 웹 회의 에지 서비스 또는 내부 XMPP 프록시 서비스에 대한 트래픽 부하 분산을 수행할 수는 없습니다.



</div>

<div>


> [!NOTE]  
> DSR (direct server return) NAT는 Lync Server 2013에서 지원 되지 않습니다.



</div>

하드웨어 부하 분산 장치에서 Lync Server 2013에 필요한 필요한 기능을 지원 하는지 여부를 확인 하려면 "Lync Server 2010 부하 분산 장치 파트너 [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452)"를 참조 하십시오.

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>A/V 에지 서비스를 실행하는 에지 서버에 대한 하드웨어 부하 분산 장치 요구 사항

다음은 A/V에 지 서비스를 실행 하는에 지 서버에 대 한 하드웨어 부하 분산 장치 요구 사항입니다.

  - 내부 및 외부 포트 443에 대해 TCP Nagling을 해제합니다. Nagling은 보다 효율적인 전송을 위해 여러 개의 작은 패킷을 하나의 큰 패킷으로 결합하는 프로세스입니다.

  - 외부 포트 범위 50,000~59,999에 대해 TCP Nagling을 해제합니다.

  - 내부 또는 외부 방화벽에 NAT를 사용하지 않습니다.

  - 에지 내부 인터페이스는 에지 서버 외부 인터페이스와 다른 네트워크에 있어야 하며 두 인터페이스 간의 라우팅은 사용할 수 없도록 설정되어야 합니다.

  - A/V에 지 서비스를 실행 하는에 지 서버의 외부 인터페이스는 공용으로 라우팅할 수 있는 IP 주소를 사용 해야 하며,에 지 외부 IP 주소에 NAT 또는 포트 변환이 없어야 합니다.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>하드웨어 부하 분산 장치 요구 사항

웹 서비스의 경우 Lync Server 2013에서 쿠키 기반 선호도 요구 사항이 크게 감소 합니다. Lync Server 2013을 배포 하 고 Lync Server 2010 프런트 엔드 서버 또는 프런트 엔드 풀을 유지 하지 않을 경우에는 쿠키 기반 지 속성을 사용할 필요가 없습니다. 그러나 Lync server 2010 프런트 엔드 서버 또는 프런트 엔드 풀을 일시적으로 나 영구적으로 유지 하려는 경우에도 Lync Server 2010에 대해 배포 되 고 구성 될 때 쿠키 기반 지 속성을 사용 합니다.

<div>


> [!NOTE]  
> <STRONG>배포에서 필요하지 않은 경우에도 쿠키 기반 선호도를 사용하려는 경우</STRONG> 부정적인 영향은 없습니다.



</div>

쿠키 기반 선호도를 **사용하지 않는** 배포에는 다음이 적용됩니다.

  - 포트 4443에 대한 역방향 프록시 게시 규칙에 대해 **호스트 헤더 전달**을 True로 설정합니다. 그러면 원래 URL이 전달됩니다.

쿠키 기반 선호도를 **사용하는** 배포에는 다음이 적용됩니다.

  - 포트 4443에 대한 역방향 프록시 게시 규칙에 대해 **호스트 헤더 전달**을 True로 설정합니다. 그러면 원래 URL이 전달됩니다.

  - 하드웨어 부하 분산 장치 쿠키는 httpOnly로 표시해서는 안 됩니다.

  - 하드웨어 부하 분산 장치 쿠키에 만료 시간이 있어서는 안 됩니다.

  - 하드웨어 부하 분산 장치 쿠키 이름은 **MS-WSMAN**(웹 서비스에 필요한 값이며 변경할 수 없음)으로 지정해야 합니다.

  - 동일한 TCP 연결의 이전 HTTP 응답에서 이미 쿠키를 가져왔는지 여부에 관계없이, 들어오는 HTTP 요청에 쿠키가 없었던 모든 HTTP 응답에서 하드웨어 부하 분산 장치 쿠키를 설정해야 합니다. 부하 분산 장치에서 TCP 연결당 한 번만 쿠키 삽입이 수행되도록 최적화하는 경우에는 해당 최적화를 사용하면 안 됩니다.

<div>


> [!NOTE]  
> 일반적인 하드웨어 부하 분산 장치 구성에서는 클라이언트 사용 및/또는 응용 프로그램 상호 작용을 통해 세션 상태를 유지 관리 하므로 Lync Server 및 Lync 2013 클라이언트에 적합 한 원본 주소 선호도 및 20 분 TCP 세션 수명을 사용 합니다.



</div>

모바일 장치를 배포하는 경우 하드웨어 부하 분산 장치는 TCP 세션 내의 개별 요청 부하를 분산할 수 있어야 합니다(대상 IP 주소를 기준으로 개별 요청 부하를 분산할 수 있어야 함).

<div>


> [!WARNING]  
> F5 하드웨어 부하 분산 장치에는 TCP 연결 내의 각 요청이 개별적으로 부하 분산되도록 하는 OneConnect라는 기능이 있습니다. 모바일 장치를 배포하는 경우 하드웨어 부하 분산 장치 공급업체에서 이와 동일한 기능을 지원하는지 확인하십시오. 최신 Apple iOS 모바일 앱의 경우 TLS(전송 계층 보안) 버전 1.2가 필요합니다. F5는 이 버전을 위한 특정 설정을 제공합니다.<BR>타사 하드웨어 부하 분산 장치에 대 한 자세한 내용은<A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

다음은 디렉터 및 프런트 엔드 풀 웹 서비스에 대한 하드웨어 부하 분산 장치 요구 사항입니다.

  - 내부 웹 서비스 Vip의 경우 하드웨어 부하\_분산 장치에서 원본 주소 지 속성 (내부 포트 80, 443)을 설정 합니다. Lync Server 2013의 경우 원본\_주소 지 속성은 단일 IP 주소에서 들어오는 여러 연결이 세션 상태를 유지 하기 위해 항상 하나의 서버로 전송 되는 것을 의미 합니다.

  - 1800초의 TCP 유휴 시간 제한을 사용합니다.

  - 역방향 프록시와 다음 홉 풀의 하드웨어 부하 분산 장치 사이에 있는 방화벽에 역방향 프록시에서 하드웨어 부하 분산 장치로 전송되는 https: 트래픽(포트 4443)을 허용하는 규칙을 만듭니다. 하드웨어 부하 분산 장치는 포트 80, 443 및 4443에서 수신 대기하도록 구성되어야 합니다.

<div>


> [!IMPORTANT]  
> 하드웨어 부하 분산 장치의 구성에 대 한 자세한 내용을 보려면 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013에서 포트 요약-확장 된 통합에 지를 하드웨어 부하 분산 장치</A>를 참조 하세요.



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>하드웨어 부하 분산 장치 선호도 요구 사항 요약


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트/사용자 위치</th>
<th>외부 웹 서비스 FQDN 선호도 요구 사항</th>
<th>내부 웹 서비스 FQDN 선호도 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App (내부 및 외부 사용자)</p>
<p>모바일 장치(내부 및 외부 사용자)</p></td>
<td><p>선호도 없음</p></td>
<td><p>원본 주소 선호도</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (외부 사용자만 해당)</p>
<p>모바일 장치(내부 및 외부 사용자)</p></td>
<td><p>선호도 없음</p></td>
<td><p>원본 주소 선호도</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (내부 사용자만 해당)</p>
<p>모바일 장치(배포되지 않음)</p></td>
<td><p>선호도 없음</p></td>
<td><p>원본 주소 선호도</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>하드웨어 부하 분산 장치용 포트 모니터링

하드웨어 부하 분산 장치에 대해 포트 모니터링을 정의하여 하드웨어 또는 통신 오류로 인해 특정 서비스를 더 이상 사용할 수 없는 시기를 확인합니다. 예를 들어 프런트 엔드 서버 또는 프런트 엔드 풀에 오류가 발생 하 여 프런트 엔드 서버 서비스 (RTCSRV)가 중지 되는 경우 HLB 모니터링에서는 웹 서비스의 트래픽 수신도 중지 해야 합니다. HLB에 대해 포트 모니터링을 구현하여 다음 항목을 모니터링합니다.

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>프런트 엔드 서버 사용자 풀-HLB 내부 인터페이스

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
<th>가상 IP/포트</th>
<th>노드 포트</th>
<th>노드 컴퓨터/모니터</th>
<th>지속성 프로필</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;풀&gt;웹-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>프런트 엔드</p>
<p>5061</p></td>
<td><p>원본</p></td>
<td><p>H</p></td>
</tr>
<tr class="even">
<td><p>&lt;풀&gt;웹-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>프런트 엔드</p>
<p>5061</p></td>
<td><p>원본</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>프런트 엔드 서버 사용자 풀-HLB External Interface

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
<th>가상 IP/포트</th>
<th>노드 포트</th>
<th>노드 컴퓨터/모니터</th>
<th>지속성 프로필</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;풀&gt;web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>프런트 엔드</p>
<p>5061</p></td>
<td><p>없음</p></td>
<td><p>H</p></td>
</tr>
<tr class="even">
<td><p>&lt;풀&gt;web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>프런트 엔드</p>
<p>5061</p></td>
<td><p>없음</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

