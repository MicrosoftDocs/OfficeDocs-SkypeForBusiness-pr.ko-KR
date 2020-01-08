---
title: Lync Server 2013 하드웨어 부하 분산 장치 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d5b10a91f469bf4688de06e836e0bdeffae1112
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Lync Server 2013에 대한 하드웨어 부하 분산 장치 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-05-11_

Lync Server 2013 배율 조정 된 통합에 지 토폴로지는 기본적으로 Lync Server를 사용 하 여 다른 조직에 페더레이션 하는 새 배포에 대 한 DNS 부하 분산에 최적화 되었습니다. 다음 시나리오에 대해 높은 가용성을 요구 하는 경우에는 다음과 같은 경우에 대 한 하드웨어 부하 분산 장치를 Edge 서버 풀에 사용 해야 합니다.

  - Office Communications Server 2007 R2 또는 Office Communications Server 2007를 사용 하는 조직과의 페더레이션

  - Exchange 2010 SP1 이전에 exchange UM을 사용 하는 원격 사용자 용 exchange UM

  - 공용 IM 사용자에 대 한 연결

<div>


> [!IMPORTANT]  
> 한 인터페이스에서 DNS 부하 분산을 사용 하는 것은 불가능 하지만, 하드웨어 부하 분산이 지원 되지 않습니다. 둘 다에 대해 인터페이스 또는 DNS 부하 분산에 대해 하드웨어 부하 분산을 사용 해야 합니다.



</div>

<div>


> [!NOTE]  
> 하드웨어 부하 분산 장치를 사용 하는 경우에는 내부 네트워크와의 연결에 대해 배포 된 부하 분산 장치를 구성 하 여 액세스에 지 서비스를 실행 하는 서버와 A/V에 대 한 서비스 소통량만 로드 해야 합니다. 내부 웹 회의 Edge 서비스 또는 내부 XMPP 프록시 서비스에 대 한 트래픽의 부하 균형을 조정할 수 없습니다.



</div>

<div>


> [!NOTE]  
> DSR (direct server return) NAT는 Lync Server 2013에서 지원 되지 않습니다.



</div>

하드웨어 부하 분산 장치가 Lync Server 2013에서 요구 하는 필수 기능을 지원 하는지 여부를 확인 하려면에서 [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)"Lync Server 2010 부하 분산 장치 파트너"를 참조 하세요.

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>A/V Edge 서비스를 실행 하는 Edge 서버의 하드웨어 부하 분산 장치 요구 사항

다음은 A/V Edge 서비스를 실행 하는 Edge 서버의 하드웨어 부하 분산 장치 요구 사항입니다.

  - 내부 및 외부 포트 443에 대해 TCP nagling를 해제 합니다. Nagling는 여러 개의 작은 패킷을 하나의 대형 패킷으로 결합 하 여 효율적인 전송을 위해 하는 프로세스입니다.

  - 외부 포트 범위 5만-59999에 대해 TCP nagling을 끄십시오.

  - 내부 또는 외부 방화벽에서 NAT를 사용 하지 마세요.

  - Edge 내부 인터페이스는 Edge 서버 외부 인터페이스와 다른 네트워크에 있어야 하 고 그 사이의 라우팅은 비활성화 되어야 합니다.

  - A/V Edge 서비스를 실행 하는 Edge 서버의 외부 인터페이스는 공용 라우팅할 수 있는 IP 주소를 사용 해야 하며, 모든 Edge 외부 IP 주소에서 NAT 또는 포트 번역이 없어야 합니다.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>하드웨어 부하 분산 장치 요구 사항

웹 서비스의 Lync Server 2013에서 쿠키 기반 선호도 요구 사항이 크게 줄어들었습니다. Lync Server 2013을 배포 하 고 Lync Server 2010 프런트 엔드 서버 또는 프런트 엔드 풀을 유지 하지 않는 경우에는 쿠키 기반 지 속성이 필요 하지 않습니다. 그러나 Lync Server 2010 프런트 엔드 서버 또는 프런트 엔드 풀을 일시적으로 또는 영구적으로 유지 하는 경우에는 Lync Server 2010에 대해 배포 하 고 구성 하는 동안에도 쿠키 기반 유지를 사용 합니다.

<div>


> [!NOTE]  
> <STRONG>배포에 필요 하지 않은 쿠키 기반 선호도를 사용 하기로 결정 한 경우</STRONG>, 이렇게 해도 부정적인 영향을 주지 않습니다.



</div>

쿠키 기반 선호도를 **사용 하지** 않는 배포에는 다음을 수행 합니다.

  - 포트 4443에 대 한 역방향 프록시 게시 규칙에서 **정방향 호스트 헤더** 를 True로 설정 합니다. 이렇게 하면 원래 URL이 전달 됩니다.

쿠키 기반 선호도를 **사용** 하는 배포의 경우:

  - 포트 4443에 대 한 역방향 프록시 게시 규칙에서 **정방향 호스트 헤더** 를 True로 설정 합니다. 이렇게 하면 원래 URL이 전달 됩니다.

  - 하드웨어 부하 분산 장치 쿠키는 httpOnly로 표시 되지 않아야 합니다.

  - 하드웨어 부하 분산 장치 쿠키에는 만료 시간이 없어야 합니다.

  - 하드웨어 부하 분산 장치 쿠키는 **MS-WSMAN** (웹 서비스에서 예상 하는 값 이며 변경할 수 없음)로 명명 되어야 합니다.

  - 동일한 TCP 연결에 대 한 이전 HTTP 응답에서 쿠키를 이미 가져왔는지 여부에 관계 없이 들어오는 HTTP 요청에 쿠키가 없는 모든 HTTP 응답에서 하드웨어 부하 분산 장치 쿠키를 설정 해야 합니다. 부하 분산 장치가 TCP 연결 당 쿠키 삽입이 발생 하도록 최적화 하면 해당 최적화를 사용 하지 않아야 합니다.

<div>


> [!NOTE]  
> 일반적인 하드웨어 부하 분산 장치 구성에서는 클라이언트 사용 및/또는 응용 프로그램 조작을 통해 세션 상태가 유지 관리 되므로 Lync Server 및 Lync 2013 클라이언트에 적합 한 원본 주소 선호도 및 20 분 TCP 세션 수명을 사용 합니다.



</div>

모바일 장치를 배포 하는 경우 하드웨어 로드 균형 조정기는 TCP 세션 내에서 개별 요청에 대 한 부하 분산을 수행할 수 있어야 합니다 (즉, 대상 IP 주소를 기반으로 개별 요청의 부하를 분산할 수 있어야 함).

<div>


> [!WARNING]  
> F5 하드웨어 부하 분산 장치에는 TCP 연결 내의 각 요청이 개별적으로 부하 분산 됨을 확인 하는 OneConnect 이라는 기능이 있습니다. 모바일 장치를 배포 하는 경우 하드웨어 부하 분산 장치 공급 업체에서 동일한 기능을 지원 하는지 확인 합니다. 최신 Apple iOS 모바일 앱에는 TLS (전송 계층 보안) 버전 1.2이 필요 합니다. F5 키를 눌러이에 대 한 특정 설정을 제공 합니다.<BR>타사 하드웨어 부하 분산 장치에 대 한 자세한 내용은 다음을 참조 하세요.<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

다음은 디렉터 및 프런트 엔드 풀 웹 서비스에 대 한 하드웨어 부하 분산 장치 요구 사항입니다.

  - 내부 웹 서비스 Vip의 경우 하드웨어 부하\_분산 장치에서 원본 주소 지 속성 (내부 포트 80, 443)을 설정 합니다. Lync Server 2013의 경우 원본\_주소 유지를 통해 단일 IP 주소에서 들어오는 여러 연결이 항상 하나의 서버로 전송 되어 세션 상태를 유지 합니다.

  - TCP 유휴 시간 제한 (1800 초)을 사용 합니다.

  - 리버스 프록시와 다음 홉 풀의 하드웨어 부하 분산 장치 사이에 있는 방화벽에서 https: 포트 4443에서 트래픽을 허용 하는 규칙을 만듭니다 (역방향 프록시에서 하드웨어 로드 균형 조정기). 포트 80, 443 및 4443에서 수신 하도록 하드웨어 로드 균형 조정기를 구성 해야 합니다.

<div>


> [!IMPORTANT]  
> 하드웨어 부하 분산 장치 구성에 대 한 자세한 내용은 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">포트 요약-확장 된 통합 모서리와 Lync Server 2013의 하드웨어 부하 분산 장치</A>를 참조 하세요.



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
<p>모바일 장치 (내부 및 외부 사용자)</p></td>
<td><p>선호도 없음</p></td>
<td><p>원본 주소 선호도</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (외부 사용자만 해당)</p>
<p>모바일 장치 (내부 및 외부 사용자)</p></td>
<td><p>선호도 없음</p></td>
<td><p>원본 주소 선호도</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (내부 사용자만 해당)</p>
<p>모바일 장치 (배포 되지 않음)</p></td>
<td><p>선호도 없음</p></td>
<td><p>원본 주소 선호도</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>하드웨어 부하 분산 장치에 대 한 포트 모니터링

하드웨어 부하 분산 장치에서 포트 모니터링을 정의 하 여 하드웨어 또는 통신 오류로 인해 특정 서비스를 더 이상 사용할 수 없는 경우를 결정 합니다. 예를 들어 프런트 엔드 서버 또는 프런트 엔드 풀에 오류가 발생 하 여 프런트 엔드 서버 서비스 (RTCSRV)가 중지 되는 경우 HLB 모니터링에서 웹 서비스의 트래픽 수신도 중지 해야 합니다. HLB에서 포트 모니터링을 구현 하 여 다음을 모니터링 합니다.

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>프런트 엔드 서버 사용자 풀 – HLB 내부 인터페이스

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
<th>지 속성 프로필</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;웹-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>프론트 엔드</p>
<p>5061</p></td>
<td><p>Source</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;웹-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>프론트 엔드</p>
<p>5061</p></td>
<td><p>Source</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>프런트 엔드 서버 사용자 풀-HLB 외부 인터페이스

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
<th>지 속성 프로필</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;풀&gt;web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>프론트 엔드</p>
<p>5061</p></td>
<td><p>없음</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;풀&gt;web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>프론트 엔드</p>
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

