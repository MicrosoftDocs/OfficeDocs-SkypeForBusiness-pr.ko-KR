---
title: 'Lync Server 2013: PSTN 연결 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa82336ed96c61315da4c25a0152ba75d15d7b6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531745"
---
# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Lync Server 2013의 PSTN 연결 구성 요소

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-04_

엔터프라이즈급 VoIP 솔루션은 QoS (서비스 품질)를 제외 하 고는 PSTN (공중 전화망)에 대 한 통화를 제공 해야 합니다. 또한 사용자는 전화를 걸고 받을 때 기본 기술을 모르고 서는 안 됩니다. 사용자의 관점에서 보면 엔터프라이즈 음성 인프라와 PSTN 간의 통화는 다른 SIP 세션 처럼 보일 수 있습니다.

PSTN 연결의 경우 SIP 트렁크 또는 PSTN 게이트웨이 (PBX, 직접 SIP 링크 라고도 함 또는 PBX가 없는 경우)를 배포할 수 있습니다.

<div>

## <a name="sip-trunking"></a>SIP 트렁크

PSTN 게이트웨이를 사용 하는 대신 SIP 트렁크를 사용 하 여 Enterprise Voice 솔루션을 PSTN에 연결할 수 있습니다. SIP 트렁크에서는 다음과 같은 시나리오를 사용할 수 있습니다.

  - 회사 방화벽 내부 또는 외부의 엔터프라이즈 사용자는 해당 서비스 공급자의 서비스로 PSTN에서 종료 되는 전자 164 규격 번호로 지정 된 시내 또는 시외 전화를 걸 수 있습니다.

  - 모든 PSTN 구독자는 해당 엔터프라이즈 사용자와 연결 된 직접 안쪽 전화 걸기 (온) 번호에 전화를 걸어 회사 방화벽 내부 또는 외부의 엔터프라이즈 사용자에 게 연락할 수 있습니다.

이 배포 솔루션을 사용 하려면 SIP 트렁크 서비스 공급자가 필요 합니다.

</div>

<div>

## <a name="pstn-gateways"></a>PSTN 게이트웨이

PSTN 게이트웨이는 엔터프라이즈 음성 인프라와 PSTN 또는 PBX 간에 신호 및 미디어를 변환 하는 타사 장치입니다. PSTN 게이트웨이는 중재 서버와 함께 엔터프라이즈 음성 클라이언트에 PSTN 또는 PBX 통화를 제공 하는 작업을 수행 합니다. 중재 서버는 PSTN 또는 PBX로 라우팅하기 위해 Enterprise Voice 클라이언트에서 PSTN 게이트웨이로의 통화도 제공 합니다. Microsoft와 협력 하 여 Lync Server에서 작동 하는 장치를 제공 하는 파트너 목록은의 Microsoft 통합 커뮤니케이션 파트너 웹 사이트를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .

</div>

<div>

## <a name="private-branch-exchanges"></a>Private Branch 교환

PBX (private branch exchange)를 사용 하는 기존 음성 인프라가 있는 경우 Lync Server Enterprise Voice를 사용 하 여 PBX를 사용할 수 있습니다.

지원 되는 Enterprise Voice PBX 통합 시나리오는 다음과 같습니다.

  - 중재 서버를 사용 하 여 미디어 바이패스를 지 원하는 ip-pbx

  - 독립 실행형 PSTN 게이트웨이가 필요한 ip-pbx

  - 독립 실행형 PSTN 게이트웨이를 사용 하는 TDM (시간 구분 멀티플렉싱) PBX

<div>


> [!NOTE]  
> 미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다. Microsoft는 인증 된 파트너와의 PSTN 게이트웨이 및 국내 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 몇 가지 테스트를 수행 했습니다. 미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램-Lync Server에 나열 된 제품 및 버전 에서만 지원 됩니다 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .



</div>

Enterprise Voice 솔루션을 제공 하는 파트너에 대 한 자세한 내용은의 Microsoft 통합 커뮤니케이션 파트너 웹 사이트를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .

PSTN 게이트웨이를 포함 하 여 Enterprise Voice 하드웨어 솔루션을 제공 하는 파트너에 대 한 자세한 내용은 Microsoft 통합 커뮤니케이션 파트너 웹 사이트를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

