---
title: 'Lync Server 2013: 분기 사이트 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edacf70cf4a8b899857864c400fa92f78bb0d94b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>Lync Server 2013에서 분기 사이트 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

분기 사이트 사용자는 분기 사이트가 연결 된 중앙 사이트의 서버에서 Lync Server 2013 기능 대부분을 가져옵니다. 각 분기 사이트는 정확히 하나의 중앙 사이트에 연결됩니다. 공중 전화망(PSTN)과의 통화 기능을 제공하기 위해 분기 사이트는 다음 항목을 포함할 수 있습니다.

  - PSTN 게이트웨이 및 중재 서버

  - SIP 트렁크

  - PBX(Private Branch Exchange)와의 기존 음성 인프라

  - Sba (survivable 분기 어플라이언스

  - Sba (survivable 분기 서버

Sba (survivable Branch 어플라이언스 또는 Sba (survivable 분기 서버를 사용 하는 분기 사이트는 이러한 솔루션 중 하나를 제외 하 고 분기 사이트에 비해 광역 네트워크 또는 중앙 사이트에서 오류가 발생 하는 시점 보다 탄력적입니다. 예를 들어 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버가 배포 된 사이트에서 사용자는 분기 사이트를 중앙 사이트에 연결 하는 네트워크가 다운 되는 경우 계속 해 서 PSTN 전화를 걸고 받을 수 있습니다. 분기 사이트 복구를 수행 하는 또 다른 방법은 지점 사이트에서 전체 수평 Lync Server 배포를 사용 하 여 PSTN 게이트웨이나 SIP 트렁크를 통해 수행 하는 것입니다.

필수 구성 요소 및 기타 계획 고려 사항을 비롯 하 여 조직에 적합 한 분기 사이트 배포에 대 한 자세한 내용은 계획 설명서에서 lync server 2013의 [PSTN 2013 연결 계획](lync-server-2013-planning-for-pstn-connectivity.md) 및 [분기 사이트 음성 복구 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 을 참조 하십시오.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 분기 사이트에서 PSTN 연결 제공](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Lync Server 2013을 사용 하 여 Sba (survivable 분기 어플라이언스 또는 서버 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

