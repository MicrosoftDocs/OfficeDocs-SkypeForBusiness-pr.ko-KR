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
ms.openlocfilehash: 97b28559ea58439d370042d54ab7ef58943bc594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013의 미디어 바이패스 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

미디어 바이패스는 신호 조정 서버를 통과 하는 호출에 대해 가능 하면 미디어 경로에서 중재 서버를 제거 하는 것을 의미 합니다.

미디어 바이패스는 대기 시간, 불필요 한 번역, 패킷 손실 가능성 및 잠재적 실패 지점의 수를 줄여 음성 품질을 향상 시킬 수 있습니다. 우회 된 통화에 대 한 미디어 처리를 제거 하면 조정 서버의 로드가 줄어들기 때문에 확장성이 향상 될 수 있습니다. 이러한 로드 감소는 중재 서버에서 여러 게이트웨이를 제어 하는 기능을 보완 합니다.

중재 서버가 없는 지점 사이트는 제한 된 대역폭의 하나 이상의 WAN 링크로 중앙 사이트에 연결 되며, 미디어 바이패스는 지점 사이트의 클라이언트에서 미디어를 통해 로컬 게이트웨이로 바로 이동 하도록 허용 하 여 대역폭 요구 사항을 줄입니다. 중앙 사이트의 중재 서버에 대 한 WAN 링크를 통해 먼저 이동 해야 합니다.

미디어 처리에서 중재 서버를 relieving 하 여 엔터프라이즈 음성 인프라에 필요한 중재 서버 수를 줄일 수도 있습니다.

다음 그림은 미디어 바이패스를 사용 하는 것과 없는 토폴로지의 기본 미디어 및 신호 경로를 보여 줍니다.

**미디어를 우회 하거나 사용 하지 않고 미디어 및 신호 경로**

![음성 CAC 미디어 바이패스 연결 적용](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "음성 CAC 미디어 바이패스 연결 적용")

일반적으로 가능한 모든 곳에서 미디어를 우회 하도록 설정 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 미디어 바이패스 개요](lync-server-2013-overview-of-media-bypass.md)

  - [Lync Server 2013의 미디어 바이패스 모드](lync-server-2013-media-bypass-modes.md)

  - [Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Lync Server 2013의 미디어 바이패스에 대한 기술 요구 사항](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>관련 단원

[Lync Server 2013에서 고급 엔터프라이즈 음성 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Lync Server 2013의 글로벌 미디어 우회 옵션](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

