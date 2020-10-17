---
title: 'Lync Server 2013: 미디어 바이패스 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d9687069e82cde803f7a01873db482ea2afa2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521995"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013의 미디어 바이패스 계획

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

미디어 바이패스는 신호가 중재 서버를 트래버스하는 통화에 대해 가능할 때마다 미디어 경로에서 중재 서버를 제거하는 것을 가리킵니다.

미디어 바이패스는 대기 시간, 불필요한 변환, 패킷 손실 가능성 및 잠재적 오류 지점 수를 줄여 음성 품질을 향상시킬 수 있습니다. 바이패스된 통화에 대한 미디어 처리가 없으므로 중재 서버에 대한 부하가 줄어 들어 확장성이 향상될 수 있습니다. 이러한 부하가 줄어들면 중재 서버가 여러 게이트웨이를 제어 하는 기능이 보완 됩니다.

중재 서버가 없는 분기 사이트가 제한 된 대역폭을 사용 하는 하나 이상의 WAN 링크를 통해 중앙 사이트에 연결 되어 있는 경우 미디어 바이패스는 먼저 WAN 링크에서 중앙 사이트의 중재 서버로 흐를 필요 없이 분기 사이트에 있는 클라이언트의 미디어가 로컬 게이트웨이로 직접 흐르도록 하 여 대역폭 요구 사항을 줄입니다.

미디어 바이패스를 통해 중재 서버를 fea-mediation-server-role-plural 하 여 엔터프라이즈 음성 인프라에 필요한 중재 서버 수를 줄일 수도 있습니다.

다음 그림에서는 미디어 바이패스가 있는 경우와 없는 경우의 토폴로지의 기본 미디어 및 신호 경로를 보여 줍니다.

**미디어 바이패스가 있는 경우와 없는 경우의 미디어 및 신호 경로**

![음성 CAC 미디어 바이패스 연결 적용](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "음성 CAC 미디어 바이패스 연결 적용")

일반적으로 가능한 모든 곳에 미디어 바이패스를 사용합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 미디어 바이패스 개요](lync-server-2013-overview-of-media-bypass.md)

  - [Lync Server 2013의 미디어 바이패스 모드](lync-server-2013-media-bypass-modes.md)

  - [Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>관련 섹션

[Lync Server 2013에서 고급 Enterprise Voice 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 미디어 바이패스로 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Lync Server 2013의 글로벌 미디어 바이패스 옵션](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

