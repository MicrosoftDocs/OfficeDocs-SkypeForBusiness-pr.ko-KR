---
title: 'Lync Server 2013: 중재 서버 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f3476f8b4e99b2abccb67f1d75446a126df03d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Lync Server 2013의 중재 서버 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

엔터프라이즈 음성 작업 부하를 배포 하는 경우 Lync Server 2013, 중재 서버를 배포 해야 합니다. 이 섹션에서는 기본 기능, 종속성, 기본 토폴로지 및 계획 지침에 대해 설명 합니다.

중재 서버는 신호 및 일부 구성의 경우 내부 Lync Server 2013, 엔터프라이즈 음성 인프라, PSTN (세션 초기화 프로토콜) 게이트웨이 또는 SIP (세션 초기 통신 네트워크)의 사용자 간 미디어를 변환 합니다. Lync Server 2013 측면에서 중재 서버는 단일 상호 TLS (MTLS) 전송 주소를 수신 대기 합니다. 게이트웨이 쪽에서 중재 서버는 토폴로지 문서에 정의 된 trunks와 연결 된 모든 연결 된 수신 대기 포트를 수신 대기 합니다. 모든 정식 게이트웨이는 TLS를 지원 해야 하지만 TCP도 사용할 수 있습니다. TLS를 지원 하지 않는 게이트웨이에 대해 TCP가 지원 됩니다.

환경에 기존 PBX (공용 분기 교환)도 있는 경우 중재 서버는 엔터프라이즈 음성 사용자와 PBX 간의 통화를 처리 합니다. PBX가 ip-pbx 인 경우 PBX와 중재 서버 간에 직접 SIP 연결을 만들 수 있습니다. PBX가 시간 나눗셈 Multiplex (TDM) PBX 인 경우 중재 서버와 PBX 간에 PSTN 게이트웨이를 배포 해야 합니다.

중재 서버는 기본적으로 프런트 엔드 서버와 collocated 됩니다. 조정 서버는 성능상의 이유 때문에 독립 실행형 풀에 배포 되거나 SIP 트렁크를 배포 하는 경우에도 독립 실행형 풀을 강력히 권장 합니다.

미디어 우회 및 DNS 부하 분산을 지 원하는 정식 PSTN 게이트웨이에 직접 SIP 연결을 배포 하는 경우 독립 실행형 중재 서버 풀은 필요 하지 않습니다. 자격 있는 게이트웨이는 중재 서버 풀에 DNS 부하 분산을 사용할 수 있고 풀의 모든 중재 서버에서 트래픽을 수신할 수 있으므로 독립 실행형 중재 서버 풀은 필요 하지 않습니다.

또한 다음 조건 중 하나가 충족 되는 경우 IP Pbx를 배포 하거나 인터넷 전화 통신 서버 공급자의 SBC (세션 경계 컨트롤러)에 연결 된 경우에는 프런트 엔드 풀에 중재 서버를 collocate 하는 것이 좋습니다.

  - IP-PBX 또는 SBC는 풀의 중재 서버에서 트래픽을 수신 하도록 구성 되며 풀의 모든 중재 서버에 일관 된 트래픽을 라우팅할 수 있습니다.

  - IP-PBX는 미디어 바이패스를 지원 하지 않지만 중재 서버를 호스트 하는 프런트 엔드 풀은 미디어 bypass이 적용 되지 않는 호출에 대 한 음성 코드 변환을 처리할 수 있습니다.

Microsoft Lync Server 2013, 계획 도구를 사용 하 여 중재 서버를 collocate 프런트 엔드 풀에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다. 환경이 이러한 요구 사항을 충족 하지 못하는 경우에는 독립 실행형 중재 서버 풀을 배포 해야 합니다.

중재 서버의 주요 기능은 다음과 같습니다.

  - Lync Server 쪽에서 SRTP 암호화 및 암호 해독

  - TCP를 통해 SIP (TLS를 지원 하지 않는 게이트웨이의 경우)를 상호 TLS를 통해 SIP에 변환

  - Lync Server와 중재 서버의 게이트웨이 피어 간에 미디어 스트림 번역

  - 네트워크 외부의 클라이언트를 내부 ICE 구성 요소에 연결 하 여 NAT 및 방화벽의 미디어 탐색을 사용 하도록 설정

  - 게이트웨이에서 지원 하지 않는 통화 흐름에 대 한 중개 역할을 하는 방법 (예: 엔터프라이즈 음성 클라이언트의 원격 작업자 전화)

  - SIP 트렁크를 포함 하는 배포에서 PSTN 지원을 제공 하기 위해 SIP 트렁크 서비스 공급자와 협력 하 여 PSTN 게이트웨이 필요를 제거 합니다.

다음 그림은 기본 PSTN 게이트웨이와 엔터프라이즈 음성 인프라와 통신할 때 중재 서버에서 사용 하는 신호 및 미디어 프로토콜을 보여 줍니다.

**중재 서버에서 사용 하는 신호 및 미디어 프로토콜**

![중재 서버 프로토콜 다이어그램]조정(images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "서버 프로토콜 다이어그램")

<div>


> [!NOTE]  
> PSTN 게이트웨이와 중재 서버 간의 네트워크에서 TCP 또는 RTP/RTCP (SRTP 또는 SRTCP 대신)를 사용 하는 경우 네트워크의 보안 및 개인 정보 보호를 위해 조치를 취할 것을 권장 합니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [M:N-Lync Server 2013의 트렁크](lync-server-2013-m-n-trunk.md)

  - [Lync Server 2013의 통화 허용 제어 서비스 및 중재 서버](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Lync Server 2013의 E9-1-1(고급 9-1-1) 및 중재 서버](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Lync Server 2013의 미디어 바이패스 및 중재 서버](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Lync Server 2013의 중재 서버의 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Lync Server 2013의 중재 서버 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

