---
title: 'Lync Server 2013: 외부 사용자 액세스에 대 한 시나리오'
description: 'Lync Server 2013: 외부 사용자 액세스에 대 한 시나리오'
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
ms.openlocfilehash: 6b212d371d5a87470fc3d849f185bb5c8659ce05
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547644"
---
# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-08_

Lync Server 2013에 대 한 외부 사용자 액세스를 제공 하려면 경계 네트워크에 하나 이상의에 지 서버와 하나의 역방향 프록시를 배포 해야 합니다. 필요한 경우 내부 네트워크에 디렉터 또는 디렉터 풀을 배포할 수 있습니다.

단일에 지 서버에서 제공할 수 있는 것 보다 많은 용량이 필요 하거나,에 지 서버 배포에 대 한 고가용성이 필요한 경우 부하 분산을 구성 하 고 부하 분산 된 풀에 여러 개의에 지 서버를 배포할 수 있습니다. 조직에 데이터 센터가 여러 개 있는 경우에는 둘 이상의 위치에에 지 서버 또는에 지 풀 배포가 있을 수 있습니다. 그러나에 지 서버 배포 중 하나만 페더레이션 경로로 지정할 수 있습니다.

이 섹션에서는에 지 서버 배포 시나리오를 정의 하 고 계획 섹션을 가능한 시나리오로 매핑합니다. 예를 들어 배포에 고가용성, 확장 가능한 메시징 및 현재 상태 (XMPP) 연락처 및 Lync mobility가 포함 된 페더레이션이 필요한 경우 다음 표에서 이러한 요구 사항을 충족 하는 일치 항목을 선택 하 고 참조 된 계획 섹션을 사용 하 여 다음 순서도와 같이 배포를 정의 합니다.

**에 지 서버 배포 시나리오 선택 프로세스**

![샘플 배포 순서도](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "샘플 배포 순서도")

이 프로세스를 사용 하 여 사용자를 위해 배포할 모든 잠재적 기능의 구성을 계획 하 고 문서화할 수 있습니다. 그러나에 지 서버를 배포 하 고 다른 기능을 추가 하기 전에 올바른 작업을 확인 한 후에는 페더레이션 및 모바일 서비스를 추가할 수 있습니다. 기존에 지 서버 배포에 기능을 추가 하는 프로세스는 배포 섹션에 설명 되어 있습니다. 배포에 대 한 자세한 내용은 초기 계획 프로세스를 진행 하는 동안 이러한 기능에 대 한 계획을 포함 하 여 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하세요. 그러면 추가 된 기능에 대 한 dns, 방화벽 및 인증서 요구 사항을 준비 하 여 인증서를 얻고 dns 및 포트/프로토콜 요구 사항을 구성 하는 데 사용할 수 있습니다.

<div>


> [!TIP]  
> 에 지 서버 및 역방향 프록시를 설치한 다음 나중에 (예: 페더레이션 및 모바일) 기능을 추가 하려는 경우 배포 후 모든 서비스에 필요한 인증서를 결정 해야 합니다. 사전에 모든 기능에 대 한 인증서를 계획 하 고 획득 하는 경우 처음에 배포 하거나 그렇지 않은 경우에는 페더레이션 요구 사항 (즉,에 지 서버) 또는 역방향 프록시 (즉, 모바일 서비스)를 충족 하기 위해 새 인증서를 주문할 필요가 없습니다.



</div>

<div>


> [!NOTE]  
> 모든에 지 서비스가 각에 지 서버에서 실행 됩니다. 서로 다른 두에 지 서버 간에는 서비스를 분할할 수 없습니다. 확장성을 위해에 지 풀을 배포 하는 경우 모든에 지 서비스가 풀의 각에 지 서버에 배포 됩니다. XMPP 페더레이션, Office Communications Server 및 Lync Server 페더레이션, 공용 IM 연결 및 클라이언트 이동성은 첫 번째에 지 서버 또는에 지 풀을 배포한 후에 배포할 수 있는 추가 서비스입니다. 모바일 서비스는 역방향 프록시를 사용 하는 기능입니다. 모바일 서비스 설치는 기능을에 지 서버에 추가 하지는 않지만, 역방향 프록시를 다시 구성 해야 합니다. 이러한 기능을 나열 하는 <STRONG>설치 목표</STRONG> 열에서는 edge 서버를 설치 및 구성할 때 이러한 기능을 배포할 수 있도록 동시에 계획 하기 위한 <STRONG>섹션 이나에 지 서버 계획 섹션</STRONG> 의 관련 열에 있는 계획 지침을 제공 합니다.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>배포 목표 파악 및 매핑


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>설치 목표</th>
<th>에 지 서버 계획 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>인프라의에 지 서비스에 대해 단일 서버를 충분히 결정 해야 합니다. 또한 NAT를 사용 하 여 인터넷에 대 한에 지 서버 외부 인터페이스에 대해 개인 IP 주소를 사용 하려고 합니다.</p>
<p>경계에 단일에 지 서버를 배포 하는 경우이 계획 섹션을 사용 합니다. 에 지 서버에 대 한 전용 IP 주소를 할당 하는 Edge Server를 배포 하 고 NAT를 사용 하 여 인터넷의 외부 사용자에 대 한 공용 IP 주소를 제공 합니다.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013의 개인 IP 주소 및 NAT를 포함 하는 단일 통합에 지</a></p></td>
</tr>
<tr class="even">
<td><p>인프라의에 지 서비스에 대해 단일 서버를 충분히 결정 해야 합니다. 또한에 지 서버 외부 인터페이스에 대 한 공용 IP 주소를 인터넷에 사용 하려고 합니다.</p>
<p>경계에 단일에 지 서버를 배포 하는 경우이 계획 섹션을 사용 합니다. 에 지 서버에 할당 된 공용 IP 주소를 사용 하 여에 지 서버를 배포 합니다. NAT 대신이 시나리오에서 라우팅을 사용 하 게 됩니다. 외부 사용자 연결에 대 한에 지 서버의 실제 공용 IP 주소를 사용할 수 있습니다.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013의 공용 IP 주소를 포함 하는 단일 통합에 지</a></p></td>
</tr>
<tr class="odd">
<td><p>에 지 서비스의 고가용성은 사용자에 게 중요 하며이 풀에는 두 개 이상의에 지 서버를 배포 하도록 결정 해야 합니다. 또한 NAT를 사용 하 여 인터넷에 대 한에 지 서버 외부 인터페이스에 대해 개인 IP 주소를 사용 하려고 합니다.</p>
<p>경계에에 지 서버 풀을 배포 하는 경우이 계획 섹션을 사용 합니다. DNS 부하 분산을 사용 하 여 풀 전체에 통신을 분산 시켜에 지 서버에 할당 된 개인 IP 주소를 사용 하 여에 지 서버를 배포 합니다. NAT를 사용 하 여 인터넷의 외부 사용자에 대 한 공용 IP 주소를 제공 합니다.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013의 확장 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산</a></p></td>
</tr>
<tr class="even">
<td><p>에 지 서비스의 고가용성은 사용자에 게 중요 하며이 풀에는 두 개 이상의에 지 서버를 배포 하도록 결정 해야 합니다. 또한에 지 서버 외부 인터페이스에 대 한 공용 IP 주소를 인터넷에 사용 하려고 합니다.</p>
<p>경계에에 지 서버 풀을 배포 하는 경우이 계획 섹션을 사용 합니다. DNS 부하 분산을 사용 하 여 풀 전체에 통신을 분산 시켜에 지 서버에 할당 된 공용 IP 주소를 사용 하 여에 지 서버를 배포 합니다. NAT 대신 라우팅을 사용 하 여 인터넷의 외부 사용자에 대 한 공용 IP 주소를 제공 합니다.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013의 확장 된 통합에 지, 공용 IP 주소의 DNS 부하 분산</a></p></td>
</tr>
<tr class="odd">
<td><p>에 지 서비스의 고가용성은 사용자에 게 중요 하며, 하드웨어 부하 분산 장치를 사용 하 여이 풀에 두 개 이상의에 지 서버를 배포 하도록 결정 해야 합니다.</p>
<p>경계에에 지 서버 풀을 배포 하는 경우이 계획 섹션을 사용 합니다. 하드웨어 부하 분산 장치를 사용 하 여 풀 전체에 통신을 분산 시켜에 지 서버에 할당 된 공용 IP 주소를 사용 하 여에 지 서버를 배포 합니다. NAT 대신 라우팅을 사용 하 여 인터넷의 외부 사용자에 대 한 공용 IP 주소를 제공 합니다.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013의 하드웨어 부하 분산 장치로 확장 된 통합에 지</a></p></td>
</tr>
<tr class="even">
<td><p>페더레이션 시나리오를 사용 하면 사용자가 통신할 수 있는 파트너 유형을 확장 하는 기능을 계획 하는 데 도움이 됩니다.</p>
<ul>
<li><p>Lync Server 페더레이션</p></li>
<li><p>Office Communications Server 페더레이션</p></li>
<li><p>공용 IM 연결</p></li>
<li><p>XMPP 페더레이션</p></li>
</ul></td>
<td><p>페더레이션 시나리오 계획</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Lync Server 2013 및 Office Communications Server federation 계획</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Lync Server 2013의 공용 인스턴트 메시징 연결 계획</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Lync Server 2013의 XMPP (extensible messaging and 거점 protocol) 페더레이션 계획</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>모바일 서비스는 역방향 프록시를 통해 제공 됩니다. 외부 사용자에 대해 모바일 기능을 사용 하도록 설정 하는 서비스는 프런트 엔드 서버 또는 프런트 엔드 풀에 배포 됩니다. 외부 사용자에 대해 모바일 서비스를 사용 하도록 설정 하기 위해 역방향 프록시에서 기존 게시 규칙을 만들거나 수정 합니다.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013의 모바일 기능 계획</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> 다음 시나리오에서는 참조 아키텍처, 예제 DNS, 포트/프로토콜 정의 및 인증서 요구 사항에 대해 설명 합니다. 또한 DNS, 포트/프로토콜 정의 및 인증서 요구 사항에 대 한 다이어그램도 포함 되어 있습니다. 다이어그램은 다른 팀 (예: 조직의 네트워크 팀, 공개 키 인프라 팀 및 서버 배포 팀)에 입력 하 고 배포할 수 있는 서식 파일을 제공 합니다. 다이어그램의 목표는 통신을 향상 시키고 필수에 지 서버 구성 요소를 실제 구성 작업을 수행 하는 사용자에 게 전달할 때 성공 여부를 확인 하는 것입니다. 다이어그램 및 관련 참조 아키텍처를 사용 하 여 배포를 계획 하는 것이 좋습니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

