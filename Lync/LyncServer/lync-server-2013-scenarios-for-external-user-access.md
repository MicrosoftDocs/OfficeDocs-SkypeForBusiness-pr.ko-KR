---
title: 'Lync Server 2013: 외부 사용자 액세스에 대한 시나리오'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eab8323744615dc3f5d0b68f4325fbfb85bf911e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013의 외부 사용자 액세스에 대한 시나리오

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

Lync Server 2013에 대 한 외부 사용자 액세스를 제공 하려면 경계 네트워크에 하나 이상의 Edge 서버와 한 개의 역방향 프록시를 배포 해야 합니다. 필요에 따라 내부 네트워크에 디렉터 또는 디렉터 풀을 배포할 수 있습니다.

단일 Edge 서버에서 제공할 수 있는 용량 보다 용량이 더 필요 하거나 Edge 서버 배포에 높은 수준의 가용성이 필요한 경우 부하 분산을 구성 하 고 부하 분산 풀에 여러 Edge 서버를 배포할 수 있습니다. 조직에 데이터 센터가 여러 개 있는 경우에는 둘 이상의 위치에서 Edge 서버 또는 Edge 풀 배포를 가질 수 있습니다. 그러나 Edge 서버 배포 중 하나만 페더레이션 경로로 지정할 수 있습니다.

이 섹션에서는 Edge 서버 배포 시나리오를 정의 하 고 계획 섹션을 가능 시나리오에 매핑합니다. 예를 들어 배포에 고가용성이 필요한 경우 확장 가능한 메시징 및 현재 상태 (XMPP) 연락처와 Lync mobility을 사용 하는 페더레이션에서는 다음 표의 해당 요구 사항을 충족 하는 일치 하는 항목을 선택 하 고 다음 순서도에 나와 있는 것 처럼 배포를 정의 하기 위한 참조 계획 섹션입니다.

**Edge 서버 배포 시나리오 선택 프로세스**

![샘플 배포 순서도](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "샘플 배포 순서도")

이 프로세스를 사용 하 여 사용자를 위해 배포할 모든 잠재적 기능의 구성을 계획 하 고 문서화할 수 있습니다. 그러나 Edge 서버를 배포 하 고 다른 기능을 추가 하기 전에 올바른 작업을 확인 한 후에는 페더레이션 및 모바일 서비스를 추가할 수 있습니다. 기존 Edge 서버 배포에 기능을 추가 하는 프로세스는 배포 섹션에 설명 되어 있습니다. 배포에 대 한 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 초기 계획 프로세스 중 이러한 기능에 대 한 계획을 포함 하 여 추가 된 기능에 대 한 dns, 방화벽, 인증서 요구 사항을 준비 하 고, 인증서를 얻고 dns 및 포트/프로토콜 요구 사항을 미리 구성할 수 있습니다.

<div>


> [!TIP]  
> Edge 서버와 리버스 프록시를 설치한 다음 나중에 (예: 페더레이션 및 이동성) 기능을 추가 하려는 경우 배포 후에 모든 서비스에 필요한 인증서를 결정 합니다. 모든 기능에 대 한 인증서를 미리 계획 하 고 초기에 배포 하거나 사용할 수 없는 경우 페더레이션 요구 사항 (즉, Edge 서버) 또는 리버스 프록시 (즉, 이동성에 대 한)를 충족 하기 위해 새 인증서를 주문할 필요가 없습니다. 서비스).



</div>

<div>


> [!NOTE]  
> 모든 edge 서비스가 각 Edge 서버에서 실행 됩니다. 두 개의 서로 다른 Edge 서버 간에 서비스를 분할할 수 없습니다. 확장성을 위해 Edge 풀을 배포 하는 경우 모든 edge 서비스가 풀의 각에 지 서버에 배포 됩니다. XMPP 페더레이션, Office Communications Server 및 Lync Server federation, 공용 IM 연결 및 클라이언트 이동성은 첫 번째 Edge 서버 또는 Edge 풀을 배포한 후 배포할 수 있는 추가 서비스입니다. 모바일 서비스는 리버스 프록시를 사용 하는 기능입니다. 모바일 서비스를 설치 하면 Edge 서버에 기능이 추가 되는 것이 아니라 리버스 프록시를 재구성 해야 합니다. 이러한 기능을 나열 하는 <STRONG>설치 목표</STRONG> 열은 edge 서버를 설치 하 고 구성할 때 배포할 이러한 기능을 동시에 계획 하는 데 사용할 수 있는 <STRONG>edge Server 계획 섹션 또는 섹션</STRONG> 의 관련 열에 있는 계획 지침을 제공 합니다.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>배포 목표 식별 및 매핑


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>설치 목표</th>
<th>Edge 서버 계획 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>단일 서버가 인프라의 Edge 서비스에 충분 한지 결정 했습니다. 또한 NAT를 사용 하 여 인터넷에 대 한 Edge 서버 외부 인터페이스에 대해 개인 IP 주소를 사용 하려고 합니다.</p>
<p>경계에 단일에 지 서버를 배포 하는 경우이 계획 섹션을 사용 합니다. Edge 서버에 할당 된 개인 IP 주소를 사용 하 여 Edge 서버를 배포 하 고 NAT를 사용 하 여 인터넷의 외부 사용자에 대 한 공용 IP 주소를 제공 하 게 됩니다.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013의 개인 IP 주소 및 NAT 사용 단일 통합 에지</a></p></td>
</tr>
<tr class="even">
<td><p>단일 서버가 인프라의 Edge 서비스에 충분 한지 결정 했습니다. 또한 인터넷에 대 한 Edge 서버 외부 인터페이스에 공용 IP 주소를 사용 하려고 합니다.</p>
<p>경계에 단일에 지 서버를 배포 하는 경우이 계획 섹션을 사용 합니다. Edge 서버에 할당 된 공용 IP 주소를 사용 하 여 Edge 서버를 배포 합니다. NAT 대신이 시나리오에서 라우팅을 사용 합니다. Edge 서버의 실제 공용 IP 주소는 외부 사용자 연결에 대해 사용할 수 있습니다.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013의 공용 IP 주소의 단일 통합 에지</a></p></td>
</tr>
<tr class="odd">
<td><p>Edge 서비스의 고가용성을 사용자에 게 중요 하 게 결정 했으며,이 풀에 두 개 이상의 Edge 서버를 배포 하 게 됩니다. 또한 NAT를 사용 하 여 인터넷에 대 한 Edge 서버 외부 인터페이스에 대해 개인 IP 주소를 사용 하려고 합니다.</p>
<p>경계에 Edge 서버 풀을 배포 하는 경우이 계획 섹션을 사용 합니다. Edge 서버에 연결 된 개인 IP 주소를 사용 하 여 Edge 서버를 배포 하 고 DNS 부하 분산을 통해 풀을 통해 통신을 배포 합니다. NAT를 사용 하 여 인터넷의 외부 사용자에 게 공용 IP 주소를 제공 합니다.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013의 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산</a></p></td>
</tr>
<tr class="even">
<td><p>Edge 서비스의 고가용성을 사용자에 게 중요 하 게 결정 했으며,이 풀에 두 개 이상의 Edge 서버를 배포 하 게 됩니다. 또한 인터넷에 대 한 Edge 서버 외부 인터페이스에 공용 IP 주소를 사용 하려고 합니다.</p>
<p>경계에 Edge 서버 풀을 배포 하는 경우이 계획 섹션을 사용 합니다. Edge 서버에 연결 된 공용 IP 주소를 사용 하 여 Edge 서버를 배포 하 고 DNS 부하 분산을 사용 하 여 풀 전체의 통신을 배포 합니다. NAT 대신 라우팅을 사용 하 여 인터넷의 외부 사용자에 게 공용 IP 주소를 제공 합니다.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013의 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산</a></p></td>
</tr>
<tr class="odd">
<td><p>Edge 서비스의 고가용성을 사용자에 게 중요 한 것으로 판단 하 고 하드웨어 로드 균형 조정기를 사용 하 여이 풀에 두 개 이상의 Edge 서버를 배포 합니다.</p>
<p>경계에 Edge 서버 풀을 배포 하는 경우이 계획 섹션을 사용 합니다. Edge 서버에 연결 된 공용 IP 주소를 사용 하 여 Edge 서버를 배포 하 고 하드웨어 로드 균형 조정기를 사용 하 여 풀을 통해 통신을 배포 합니다. NAT 대신 라우팅을 사용 하 여 인터넷의 외부 사용자에 게 공용 IP 주소를 제공 합니다.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013의 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지</a></p></td>
</tr>
<tr class="even">
<td><p>페더레이션 시나리오에서는 사용자가 통신할 수 있는 파트너 유형을 확장 하는 기능에 대 한 계획을 수립할 수 있습니다.</p>
<ul>
<li><p>Lync Server federation</p></li>
<li><p>Office Communications Server federation</p></li>
<li><p>공용 메신저 연결</p></li>
<li><p>XMPP 페더레이션</p></li>
</ul></td>
<td><p>페더레이션 시나리오 계획</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Lync Server 2013 및 Office Communications Server federation에 대 한 계획</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Lync Server 2013에서 공용 인스턴트 메시징 연결 계획</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Lync Server 2013에서 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 페더레이션 계획</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>모바일 서비스는 리버스 프록시를 통해 제공 됩니다. 외부 사용자에 대해 이동성을 사용 하도록 설정 하는 서비스는 프런트 엔드 서버 또는 프런트 엔드 풀에 배포 됩니다. 외부 사용자를 위해 모바일 서비스를 사용 하도록 설정 하려면 리버스 프록시에서 기존 게시 규칙을 만들거나 수정 합니다.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013의 모바일 기능 계획</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> 다음 시나리오에서 섹션은 참조 아키텍처, 예제 DNS, 포트/프로토콜 정의, 인증서 요구 사항입니다. DNS, 포트/프로토콜 정의 및 인증서 요구에 대 한 다이어그램도 포함 되어 있습니다. 다이어그램은 다른 팀 (예: 조직의 네트워크 팀, 공개 키 인프라 팀, 서버 배포 팀)에 입력 하 고 배포 하는 데 사용할 수 있는 서식 파일을 제공 합니다. 다이어그램의 목표는 통신을 개선 하 고 필요한 Edge 서버 구성 요소를 실제 구성 작업을 수행 하는 사용자에 게 전달할 때 성공 하도록 하는 것입니다. 다이어그램 및 관련 참조 아키텍처를 사용 하 여 배포를 계획 하는 것이 좋습니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

