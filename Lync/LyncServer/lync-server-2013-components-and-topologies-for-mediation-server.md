---
title: 'Lync Server 2013: 중재 서버에 대 한 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1337e7ecdc1ee1467bcb78f0b89ea1410445f59c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013의 중재 서버에 대 한 구성 요소 및 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

이 항목에서는 중재 서버가 종속 된 구성 요소 및 중재 서버를 배포할 수 있는 토폴로지에 대해 설명 합니다.

<div>

## <a name="dependencies"></a>의존

중재 서버에는 다음과 같은 종속성이 있습니다.

  - **등록자.** 필수 특성입니다. 등록자는 Lync Server 2013 네트워크와의 중재 서버 상호 작용에서 신호를 보내는 다음 홉입니다. 중재 서버는 배치 된과 함께 프런트 엔드 서버에는 중재 서버로만 구성 된 독립 실행형 풀에 설치 되어 있을 수 있습니다. 등록자는 Sba (survivable 분기 기기에 중재 서버 및 PSTN 게이트웨이를 사용 하 여 배치 된 됩니다.

  - **모니터링 서버.** 선택 항목이지만 사용하는 것이 좋습니다. 모니터링 서버를 사용 하면 중재 서버가 해당 미디어 세션과 관련 된 품질 메트릭을 기록할 수 있습니다.

  - **에지 서버.** 외부 사용자 지원에 필요합니다. 에 지 서버를 사용 하면 NAT 또는 방화벽 뒤에 있는 사용자와 중재 서버가 상호 작용할 수 있습니다.

</div>

<div>

## <a name="topologies"></a>기술

Lync Server 2013, 중재 서버는 기본적으로 Standard Edition Server, 프런트 엔드 풀 또는 Sba (survivable 분기 기기의 등록자 인스턴스를 사용 하 여 배치 된 됩니다. 프런트 엔드 풀의 모든 중재 서버는 동일 하 게 구성 해야 합니다.

성능에 문제가 있는 경우 전용 독립 실행형 풀에 하나 이상의 중재 서버를 배포 하는 것이 좋을 수 있습니다. 또는 SIP 트렁크를 배포 하는 경우 독립 실행형 중재 서버 풀을 배포 하는 것이 좋습니다.

미디어 바이패스 및 DNS 부하 분산을 지원하는 적격한 PSTN 게이트웨이에 직접 SIP 연결을 배포한 경우 독립 실행형 중재 서버 풀이 필요하지 않습니다. 정규 게이트웨이는 중재 서버 풀에 대 한 DNS 부하 분산을 가능 하 게 하 고 풀의 중재 서버에서 트래픽을 수신할 수 있으므로 독립 실행형 중재 서버 풀은 필요 하지 않습니다.

또한 다음 조건 중 하나라도 충족 되 면 IP-Pbx를 배포 하거나 인터넷 전화 통신 서버 공급자의 세션 경계 컨트롤러 (SBC)에 연결 하는 경우에도 프런트 엔드 풀에 중재 서버를 함께 배치할 것을 권장 합니다.

  - IP-PBX 또는 SBC가 풀의 중재 서버에서 트래픽을 수신하도록 구성되었고 풀의 모든 중재 서버에 트래픽을 단일 방식으로 라우팅할 수 있습니다.

  - IP-PBX는 미디어 바이패스를 지원 하지 않지만 중재 서버를 호스트 하는 프런트 엔드 풀은 미디어 바이패스가 적용 되지 않는 통화에 대 한 음성 트랜스 변환을 처리할 수 있습니다.

Microsoft Lync Server 2013, 계획 도구를 사용 하 여 중재 서버를 함께 배치할 프런트 엔드 풀에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다. 사용자 환경에서 이러한 요구 사항을 충족할 수 없는 경우 독립 실행형 중재 서버 풀을 배포해야 합니다.

배포할 토폴로지에 대 한 자세한 내용은 [Lync server 2013의 중재 서버에 대 한 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md)을 참조 하세요.

다음 그림에서는 WAN 링크로 연결된 두 사이트로 구성된 단순한 토폴로지를 보여 줍니다. 중재 서버는 배치 된이 사이트 1의 프런트 엔드 풀에 있는 등록자와 함께 사용 됩니다. 사이트 1의 중재 서버는 사이트 1의 PSTN 게이트웨이와 사이트 2의 게이트웨이를 모두 제어 합니다. 이 토폴로지에서는 사이트 및 지역 정보를 사용하도록 미디어 바이패스가 전역적으로 설정되어 있으며 각 PSTN 게이트웨이의 트렁크(GW1 및 GW2)에 바이패스가 사용되도록 설정되었습니다.

**사이트 1의 중재 서버 및 사이트 2의 PSTN 게이트웨이를 사용하여 WAN 링크로 연결된 사이트의 예**

![중재 서버 WAN 게이트웨이를 사용 하는 음성 토폴로지](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "중재 서버 WAN 게이트웨이를 사용 하는 음성 토폴로지")

다음 그림에서는 중재 서버가 사이트 1의 프런트 엔드 풀에 있는 등록자와 배치 된 하 고 사이트 1의 IP-PBX에 직접 SIP 연결 되는 간단한 토폴로지를 보여 줍니다. 이 그림에서 중재 서버는 사이트 2의 PSTN 게이트웨이도 제어 합니다. 사이트 1과 2에 모두 Lync 사용자가 있다고 가정 합니다. 또한 ip-pbx가 IP-PBX에서 제어 하는 미디어 끝점에 전송 되기 전에 Lync 끝점에서 시작 되는 모든 미디어에서 통과 해야 하는 관련 미디어 프로세서가 있다고 가정 합니다. 이 토폴로지에는 사이트 및 지역 정보를 사용하도록 미디어 바이패스가 전역적으로 설정되어 있으며 PBX 및 PSTN 게이트웨이의 트렁크에 바이패스가 사용되도록 설정되어 있습니다.

**사이트 1의 중재 서버 및 사이트 2의 PBX를 사용하여 WAN 링크로 연결된 사이트의 예**

![음성 토폴로지 중재 서버 WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "음성 토폴로지 중재 서버 WAN PBX")

PBX 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 [lync server 2013의 중재 서버에 대 한 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md) 및 [lync Server 2013의 Direct SIP 배포 옵션](lync-server-2013-direct-sip-deployment-options.md)을 참조 하십시오.

이 항목의 마지막 그림에서는 중재 서버가 인터넷 전화 통신 서비스 공급자의 SBC에 연결 되는 토폴로지를 보여 줍니다. SIP 트렁크 토폴로지에 대 한 자세한 내용은 [sip 트렁크 In Lync Server 2013](lync-server-2013-sip-trunking.md)을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

