---
title: 'Lync Server 2013: PSTN 연결 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecda38b4164a70cd4dbb21271ff6efedb08cd498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Lync Server 2013의 PSTN 연결 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-04_

엔터프라이즈급 VoIP 솔루션은 서비스 품질 (QoS)에 동의 하지 않고 PSTN (공공 교환 전화 네트워크)에 대 한 통화를 제공 해야 합니다. 또한 사용자는 전화를 걸거나 받을 때 기본 기술을 인식 하지 못할 수 있습니다. 사용자의 관점에서 보면 엔터프라이즈 음성 인프라와 PSTN 간의 통화는 다른 SIP 세션 처럼 보일 것입니다.

PSTN 연결의 경우 SIP 트렁크 또는 PSTN 게이트웨이 (PBX는 직접 SIP 링크 라고도 함) 또는 PBX 없이 구축할 수 있습니다.

<div>

## <a name="sip-trunking"></a>SIP 트렁크

PSTN 게이트웨이를 사용 하는 대신 SIP 트렁크를 사용 하 여 엔터프라이즈 음성 솔루션을 PSTN에 연결할 수 있습니다. SIP 트렁크는 다음과 같은 시나리오를 사용할 수 있습니다.

  - 회사 방화벽 내부나 외부의 enterprise 사용자는 해당 서비스 공급자의 서비스로 PSTN에서 종료 되는 E-164 규격 번호로 지정 된 지역 또는 장거리 통화를 할 수 있습니다.

  - 모든 PSTN 구독자는 해당 엔터프라이즈 사용자와 연결 된 직접적인 안쪽 전화 걸기 (시작) 번호를 사용 하 여 회사 방화벽 내부나 외부의 엔터프라이즈 사용자에 게 연락할 수 있습니다.

이 배포 솔루션을 사용 하려면 SIP 트렁크 서비스 공급자가 필요 합니다.

</div>

<div>

## <a name="pstn-gateways"></a>PSTN 게이트웨이

PSTN 게이트웨이는 엔터프라이즈 음성 인프라와 PSTN 또는 PBX 간에 신호 및 미디어를 변환 하는 타사 장치입니다. PSTN 게이트웨이는 중재 서버를 사용 하 여 PSTN 또는 PBX 통화를 엔터프라이즈 음성 클라이언트로 제공 합니다. 또한 중재 서버는 PSTN 또는 PBX로 라우팅하기 위해 엔터프라이즈 음성 클라이언트에서 PSTN 게이트웨이로의 통화를 제공 합니다. Lync Server와 작동 하는 장치를 제공 하기 위해 Microsoft와 함께 작업 하는 파트너 목록은의 Microsoft 통합 커뮤니케이션 파트너 웹 사이트 [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)를 참조 하세요.

</div>

<div>

## <a name="private-branch-exchanges"></a>개인 분기 교환

PBX (개인 브랜치 교환)를 사용 하는 기존 음성 인프라가 있는 경우 Lync Server Enterprise Voice에서 PBX를 사용할 수 있습니다.

지원 되는 엔터프라이즈 음성 PBX 통합 시나리오는 다음과 같습니다.

  - 중재 서버를 사용 하 여 미디어 바이패스를 지 원하는 IP-PBX

  - 독립 실행형 PSTN 게이트웨이를 필요로 하는 IP-PBX.

  - 독립 실행형 PSTN 게이트웨이를 사용 하는 TDM (시간 구분 멀티플렉싱) PBX.

<div>


> [!NOTE]  
> 미디어 바이패스는 모든 PSTN 게이트웨이, IP PBX, SBC와 상호 작용 하지 않습니다. Microsoft는 인증 된 파트너와 함께 PSTN 게이트웨이 및 SBCs 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 테스트를 완료 했습니다. 미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램 –의 Lync Server에 나열 된 제품 및 버전 에서만 <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>지원 됩니다.



</div>

엔터프라이즈 음성 솔루션을 제공 하는 파트너에 대 한 자세한 내용은의 [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)Microsoft 통합 커뮤니케이션 파트너 웹 사이트를 참조 하세요.

PSTN 게이트웨이를 포함 하 여 엔터프라이즈 음성 하드웨어 솔루션을 제공 하는 파트너에 대 한 자세한 내용은 Microsoft 통합 [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)커뮤니케이션 파트너 웹 사이트를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

