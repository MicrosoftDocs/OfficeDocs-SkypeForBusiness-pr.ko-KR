---
title: 'Lync Server 2013: 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa5a395c8509961937af23c12763a5bf55cc326
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013의 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-21_

Edge 풀 토폴로지에서는 두 개 이상의 Edge 서버가 데이터 센터의 경계 네트워크에 부하 분산 풀로 배포 됩니다. 하드웨어 부하 분산은 외부 및 내부 Edge 서버 인터페이스에 대 한 트래픽 소통에 사용 됩니다.

조직에서 15000 이상의 Edge 서비스 클라이언트 연결에 대 한 지원이 필요한 경우, 1000 활성 웹 컨퍼런스 Edge 서비스 클라이언트 연결 또는 500 동시 A/V Edge 서비스 세션을 사용 하 고, Edge 서버의 가용성이 매우 중요 한 경우이 토폴로지에서는 확장성 및 장애 조치 지원의 이점을 제공 합니다.

이 그림에는 Edge 서버와 프런트 엔드 풀 또는 서버 간의 내부 네트워크에 배포 된 선택적 서버 역할인 디렉터가 표시 되지 않습니다. . 디렉터 토폴로지에 대 한 자세한 내용은 [Lync Server 2013의 디렉터에 필요한 구성 요소](lync-server-2013-components-required-for-the-director.md)를 참조 하세요.

<div>


> [!NOTE]  
> 표시 되는 그림은 IP 주소 지정 방향과 예에 대 한 것 이지만 올바른 들어오고 나가는 트래픽에 대 한 실제 통신 흐름을 나타내지는 않습니다. 이 그림은 가능 소통량에 대 한 높은 수준의 보기를 나타냅니다. 수신 (수신 대기 포트)에 관련 된 트래픽 흐름에 대 한 세부 정보 및 보내는 (대상 서버 또는 클라이언트에 게)는 각 시나리오의 포트 요약 다이어그램에 표시 됩니다. 예를 들어, TCP 443는 실제로 인바운드 (Edge 서버 또는 리버스 프록시)에만 사용할 수 있으며, 프로토콜 (TCP) 관점에서 양방향 으로만 전달 됩니다. 또한이 그림에는 NAT (네트워크 주소 변환)가 발생할 때 변경 되는 트래픽 특성 (대상 주소는 인바운드에서 변경 되 고 원본 주소는 아웃 바운드로 변경 됨)이 표시 됩니다. 외부 및 내부 방화벽 예제와 서버 인터페이스가 참조용 으로만 표시 됩니다. 마지막으로, 해당 하는 경우 기본 게이트웨이 및 경로 관계 예를 표시 합니다. 또한 다이어그램은 <EM>.Com</EM> dns 영역을 사용 하 여 역방향 프록시와 경계 서버 모두에 대해 외부 dns 영역을 표시 하 고, <EM>.net</EM> dns 영역은 내부 DNS 영역을 참조 한다는 점에 유의 하세요.



</div>

Microsoft Lync Server 2013에 대 한 새로운 기능은 IPv6 주소 지정을 지원 합니다. IPv4 주소 지정과 매우 유사 하 게 IPv6 주소는 지정 된 IPv6 주소 공간의 일부인 방식으로 할당 되어야 합니다. 이 항목의 주소는 예를 보여 줍니다. 배포에서 작동 하는 IPv6 주소를 확보 하 고 올바른 범위를 제공 하 고 내부 및 외부 주소 지정과 상호 운용 되도록 해야 합니다. Windows Server는 IPv6 작업을 전환 하는 데 중요 한 기능과 *이중 스택*이라는 ipv6 통신에 IPv4를 제공 합니다. 이중 스택은 IPv4 및 IPv6에 대 한 별도의 개별 네트워크 스택입니다. 이중 스택은 IPv4 및 IPv6에 대 한 주소 지정을 동시에 할당할 수 있도록 허용 하 고 서버가 요구 사항에 따라 다른 호스트 및 클라이언트와 통신할 수 있도록 합니다.

Ipv6 주소 지정에 사용 하는 일반적인 주소 유형은 IPv6 전역 주소 (공용 IPv4 주소와 유사), IPv6 고유 로컬 주소 (개인 IPv4 주소 범위와 유사) 및 IPv6 링크 로컬 주소 (자동 개인 IP와 유사)가 됩니다. IPv4 용 Windows Server의 주소)

IPv6에 대 한 nat (Network address translation) (네트워크 주소 변환 기술)는 NAT IPv6에서 IPv4 (일반적으로 NAT64로 지칭 됨)로, 그리고 IPv6에 대 한 NAT IPv6의 경우 (일반적으로 NAT66 이라고 함)에 사용 됩니다. NAT 기술이 있으면 Lync Server Edge 서버에 대해 제공 되는 5 가지 시나리오가 여전히 유효 하다는 것을 의미 합니다.

<div>


> [!WARNING]  
> IPv6은 복잡 한 항목이 며, 네트워크 팀과 인터넷 공급자를 사용 하 여 Windows server 수준 및 Lync Server 2013 수준에서 할당 하는 주소가 예상 대로 작동 하는지 확인 하는 데 세심 한 계획이 필요 합니다. IPv6 주소 지정 및 계획에 대 한 추가 리소스는이 항목의 끝부분에 있는 링크를 참조 하세요.



</div>

**하드웨어 부하 분산 장치 구성**

자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 필요한 구성 요소의](lync-server-2013-components-required-for-external-user-access.md)"A/V Edge 용 하드웨어 부하 분산 장치 요구 사항" 섹션을 참조 하세요.

**크기가 조정 된 통합 된 가장자리 토폴로지 (하드웨어 부하 분산)**

![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")

<div>


> [!IMPORTANT]  
> CAC (Call 허용 제어)를 사용 하는 경우에도 Edge Server 내부 인터페이스에 IPv4 주소를 할당 해야 합니다. CAC는 IPv4 주소를 사용 하며 작동 하는 데 사용할 수 있어야 합니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 인증서 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Lync Server 2013의 포트 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Lync Server 2013의 DNS 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[IP 버전 6 주소 지정 아키텍처](http://tools.ietf.org/html/rfc4291)  
[IPv6 글로벌 유니캐스트 주소 형식](http://tools.ietf.org/html/rfc3587)  
[고유한 로컬 IPv6 유니캐스트 주소](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

