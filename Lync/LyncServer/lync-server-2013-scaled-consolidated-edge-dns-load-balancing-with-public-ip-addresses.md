---
title: 확장 된 통합에 지, 공용 IP 주소의 DNS 부하 분산
description: 확장 된 통합에 지, 공용 IP 주소의 DNS 부하 분산
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: 2b854f6d-3d3f-4961-a5f8-a03f47740df0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204761(v=OCS.15)
ms:contentKeyID: 48183698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d382fe7d25b4fae8c91073451d7d8b4f3f113b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547674"
---
# <a name="scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013의 확장 된 통합에 지, 공용 IP 주소의 DNS 부하 분산

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-08_

에지 서버 풀 토폴로지에서는 둘 이상의 에지 서버가 데이터 센터의 경계 네트워크에 부하 분산 풀로 배포됩니다. 외부 및 내부 에지 인터페이스로의 트래픽에는 모두 DNS(도메인 이름 시스템) 부하 분산이 사용됩니다.

조직에서 15000 개 이상의 액세스에 지 서비스 클라이언트 연결, 1000 액티브 Lync Server 웹 회의 서비스 클라이언트 연결 또는 500 동시 A/V에 지 세션에 대 한 지원이 필요한 경우이 토폴로지는 확장성 및 장애 조치 (failover) 지원의 이점을 제공 합니다.

이 그림에는에 지 서버와 프런트 엔드 풀 또는 서버 간에 내부 네트워크에 배포 된 선택적 서버 역할인 디렉터는 표시 되지 않습니다. 디렉터 토폴로지에 대 한 자세한 내용은 [Lync Server 2013의 디렉터에 필요한 구성 요소](lync-server-2013-components-required-for-the-director.md)를 참조 하세요. 그림은 단일 역방향 프록시를 나타냅니다.

<div>


> [!NOTE]
> 그림에는 방향과 IP 주소 예가 표시되어 있지만 올바른 수신/발신 트래픽의 실제 통신 흐름을 나타낼 목적으로 제작되지는 않았습니다. 이 그림은 발생 가능한 트래픽을 대략적으로 보여줍니다. 수신 포트로의 수신 및 대상 서버/클라이언트로의 발신과 관련된 트래픽 흐름에 대한 세부 정보는 각 시나리오의 포트 요약 다이어그램에 나타납니다. 예를 들어 실제로 TCP 443은 에지 또는 역방향 프록시로의 인바운드만 수행하지만 TCP 프로토콜 관점에서는 양방향 흐름입니다. 또한 그림은 NAT(Network Address Translation)가 발생하는 경우, 즉 대상 주소가 인바운드에서 변경되거나 원본 주소가 아웃바운드에서 변경된 경우 변경되는 트래픽의 특성도 보여줍니다. 외부 및 내부 방화벽 예와 서버 인터페이스는 참조 목적으로만 표시되어 있습니다. 마지막으로 적용 가능한 경우 기본 게이트웨이 및 경로 관계 예가 표시되었습니다. 또한 다이어그램은 <EM>.Com</EM> dns 영역을 사용 하 여 역방향 프록시와에 지 서버 둘 다에 대해 외부 dns 영역을 나타내지만, <EM>.net</EM> dns 영역은 내부 dns 영역을 참조 한다는 점에 유의 하십시오.



</div>

Microsoft Lync Server 2013의 새로운 기능에서는 IPv6 주소 지정을 지원 합니다. IPv4 주소와 거의 마찬가지로 IPv6 주소를 할당할 때 할당된 IPv6 주소 공간에 포함되어야 합니다. 이 문서에 사용된 주소는 오직 예입니다. 배포 환경에서 작동하고 올바른 범위를 제공하며 내/외부 주소와 통합되는 IPv6 주소를 보유해야 합니다. Windows Server에서는 IPv6 작업을 전환 하는 중요 한 기능과 *이중 스택*이라고 하는 ipv6 통신에 대 한 IPv4를 제공 합니다. 이중 스택은 IPv4 및 IPv6 각각에 대한 별도의 네트워크 스택입니다. 이중 스택을 사용하면 IPv4 및 IPv6의 주소를 동시에 할당할 수 있을 뿐 아니라 서버가 각 요구 사항에 기반하여 다른 호스트 및 클라이언트와 통신할 수 있습니다.

IPv6 주소 지정에 사용할 일반적인 주소 유형은 IPv6 글로벌 주소 (공용 IPv4 주소와 유사함), ipv6 고유 로컬 주소 (개인 IPv4 주소 범위와 비슷함) 및 IPv6 링크 로컬 주소 (Windows Server의 IPv4의 경우 자동 개인 IP 주소와 유사함)가 됩니다.

NAT IPv6에서 IPv4로의 변환(주로 NAT64라고 함) 및 NAT IPv6에서 IPv6로의 변환(주로 NAT66라고 함)을 허용하는 IPv6의 NAT(네트워크 주소 변환) 기술이 존재합니다. NAT 기술이 있다는 것은 Lync Server에 지 서버에 대해 제공 되는 5 가지 시나리오가 여전히 유효한 것임을 의미 합니다.

<div>


> [!WARNING]
> IPv6은 복잡 한 주제 이며, Windows server 수준 및 Lync Server 2013 수준에서 할당 하는 주소가 예상 대로 작동 하는지 확인 하기 위해 네트워킹 팀 및 인터넷 공급자와의 신중한 계획이 필요 합니다. IPv6 주소 지정 및 계획에 대한 추가 리소스는 이 항목의 끝에 있는 링크를 참조하십시오.



</div>

![7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537](images/JJ204761.7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537(OCS.15).jpg "7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537")

<div>


> [!IMPORTANT]
> CAC (통화 허용 제어)를 사용 하는 경우에도에 지 서버 내부 인터페이스에 IPv4 주소를 할당 해야 합니다. CAC는 IPv4 주소를 사용하며, 작동을 위해 이를 사용할 수 있어야 합니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [인증서 요약-조정 된 통합에 지, Lync Server 2013의 공용 IP 주소를 사용한 DNS 부하 분산](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [포트 요약-조정 된 통합에 지, Lync Server 2013의 공용 IP 주소를 사용한 DNS 부하 분산](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [DNS 요약-조정 된 통합에 지, Lync Server 2013의 공용 IP 주소를 사용한 DNS 부하 분산](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[IP 버전 6 주소 지정 아키텍처](https://tools.ietf.org/html/rfc4291)  
[IPv6 글로벌 유니캐스트 주소 형식](https://tools.ietf.org/html/rfc3587)  
[고유한 로컬 IPv6 유니캐스트 주소](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

