---
title: 'Lync Server 2013: SIP 트렁크에 대한 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1b80078f942f3f70957a7af6b27b7dd9210046
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Lync Server 2013의 SIP 트렁크에 대한 구성 요소 및 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

다음 그림은 Lync Server의 SIP 트렁크 토폴로지를 보여 줍니다.

**SIP 트렁크 토폴로지**

![Sip 트렁크 토폴로지](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "sip 트렁크 토폴로지")

다이어그램에 표시 된 대로 IP 가상 개인 네트워크 (VPN)는 엔터프라이즈 네트워크와 PSTN (공개 통신 네트워크) 서비스 공급자 간의 연결에 사용 됩니다. 이 개인 네트워크의 용도는 IP 연결을 제공 하 고 보안을 강화 하며 서비스 품질 (옵션) 보장을 받을 수 있도록 하는 것입니다. VPN의 특성상 SIP 신호 소통량에는 TLS (전송 계층 보안)를 사용 하거나 미디어 트래픽에 대 한 보안 실시간 전송 프로토콜 (SRTP)을 사용할 필요가 없습니다. 따라서 엔터프라이즈와 서비스 공급자 간의 연결은 IP VPN을 통해 터널링 된 미디어에 대 한 UDP를 통해 SIP 및 일반 실시간 전송 프로토콜 (터널)에 대 한 일반 TCP 연결로 구성 됩니다. Vpn 라우터 간의 모든 방화벽이 VPN 라우터 통신을 허용 하도록 포트가 열려 있는지 확인 하 고 VPN 라우터의 외부 경계에 있는 IP 주소를 공개적으로 라우팅할 수 있도록 합니다.

<div>


> [!IMPORTANT]  
> 서비스 공급자에 게 문의 하 여 장애 조치를 포함 하 여 고가용성에 대 한 지원을 제공 하는지 확인 합니다. 이 경우 설정 절차를 결정 해야 합니다. 예를 들어 각 중재 서버에서 하나의 IP 주소와 하나의 SIP 트렁크만 구성 해야 하나요, 아니면 각 중재 서버에서 여러 SIP trunks를 구성 해야 합니까?<BR>중앙 사이트가 여러 개 있는 경우 서비스 공급자에 게 다른 중앙 사이트와의 연결을 설정 하는 기능이 있는지를 확인 합니다.



</div>

<div>


> [!NOTE]  
> SIP 트렁크의 경우 독립 실행형 중재 서버를 배포 하는 것이 좋습니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync Server 2013에서 중재 서버 배포 및 피어 정의</A> 를 참조 하세요.



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>SIP 트렁크 중재 서버 보안 유지

보안을 위해서는 두 VPN 라우터 간의 각 연결에 대해 VLAN (가상 LAN)을 설정 해야 합니다. VLAN을 설정 하는 실제 프로세스는 라우터 제조업체 마다 다릅니다. 자세한 내용은 라우터 공급 업체에 문의 하세요.

다음 지침을 따르는 것이 좋습니다.

  - 중재 서버와 경계 네트워크 (DMZ, 완충 영역 및 스크린 된 서브넷이 라고도 함)의 VPN 라우터 사이에 VLAN (가상 LAN)을 설정 합니다.

  - 브로드캐스트 또는 멀티 캐스트 패킷을 라우터에서 VLAN으로 전송 하는 것을 허용 하지 않습니다.

  - 라우터에서 중재 서버를 제외한 아무 곳에 나 트래픽을 라우팅하는 라우팅 규칙을 차단 합니다.

VPN 서버를 사용 하는 경우 다음 지침을 따르는 것이 좋습니다.

  - VPN 서버와 중재 서버 간에 VLAN을 설정 합니다.

  - 브로드캐스트 또는 멀티 캐스트 패킷을 VPN 서버에서 VLAN으로 전송 하도록 허용 하지 않습니다.

  - 중재 서버를 제외한 아무 곳으로도 VPN 서버 트래픽을 라우팅하는 라우팅 규칙을 차단 합니다.

  - GRE (generic routing 캡슐화)를 사용 하 여 VPN의 데이터를 암호화 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

