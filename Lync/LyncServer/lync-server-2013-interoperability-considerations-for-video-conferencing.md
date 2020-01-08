---
title: 'Lync Server 2013: 비디오 회의를 위한 상호 운용성 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 880b2e41a1ea92b3d6da9cd29153695b474e88f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 비디오 회의에 대 한 상호 운용성 고려 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

이 섹션에서는 레거시 클라이언트와 Lync Server 2013 풀 또는 Lync Server 2013 클라이언트와 레거시 풀 간의 상호 운영성이 있는 경우 마이그레이션 작업 단계 중 사용자 환경에 대해 설명 합니다.

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013 풀

사용자는 레거시 클라이언트가 Lync Server 2013 풀에서 사용 될 때 다음과 같은 동작을 경험할 수 있습니다.

  - 2-타사 통화의 경우 비디오 해상도가 레거시 풀의 경우와 동일 합니다.

  - 단체 컨퍼런스의 경우 비디오 해상도 및 비디오 회의 기능은 레거시 풀의 경우와 동일 합니다. 갤러리 보기 및 고해상도를 사용할 수 없습니다.

</div>

<div>

## <a name="legacy-pools"></a>레거시 풀

사용자는 Lync Server 2013 클라이언트를 레거시 풀에서 사용할 때 다음과 같은 동작이 발생 합니다.

  - 2-타사 통화의 경우 Lync Server 2013 클라이언트는 다음과 같이 새로운 기능을 사용할 수 있습니다.
    
      - 두 참가자가 모두 Lync Server 2013 클라이언트를 사용 하는 경우에는 H. a 264를 사용할 수 있습니다.
    
      - Lync Server 2013 클라이언트는 레거시 서버가 대역내 프로비저닝으로이 정보를 보내지 않으므로 TotalReceiveVideoBitRateKb에 대 한 기본값을 사용 합니다.

  - 단체 컨퍼런스의 경우 비디오 해상도 및 비디오 회의 기능은 레거시 풀의 레거시 클라이언트에서 경험 하는 것과 동일 합니다.

<div>


> [!NOTE]  
> 레거시 서버에서 Lync Server 2013 클라이언트를 호스트 하는 경우에는 풀의 모든 사용자가 저해상도 비디오만 받도록 비디오 회의 대역폭을 구성할 수 있지만 고해상도 비디오를 보낼 수도 있습니다. 예를 들어 미디어 구성에서 MaxVideoRateAllowed가 CIF-250K로 설정 되 고 VideoBitRateKb가 회의 정책에서 2000 kbps로 설정 됩니다. 이 경우에는 풀의 사용자에 게 높은 해상도를 사용할 수 없기 때문에 발생 하는 순 효과입니다.<BR>MaxVideoRateAllowed는 Lync Server 2013 클라이언트에 더 이상 사용 되지 않으므로 Lync Server 2013 클라이언트가 고해상도 비디오를 요청 하는 것을 막을 수 없습니다. 대신 풀의 모든 사용자에 대 한 회의 정책의 VideoBitRateKb을 MaxVideoRateAllowed와 같은 값으로 설정 하거나 (즉, CIF를 250 kbps로 설정 하거나 VGA를 600 kbps로 설정 하거나 HD를 1500 kbps로 설정 합니다.)



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

