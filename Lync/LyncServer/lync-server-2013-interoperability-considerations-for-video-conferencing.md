---
title: 'Lync Server 2013: 비디오 회의에 대 한 상호 운용성 고려 사항'
description: 'Lync Server 2013: 비디오 회의에 대 한 상호 운용성 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89675954ea4c4f188f50aab8fb2cb49494bcc247
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543934"
---
# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 비디오 회의에 대 한 상호 운용성 고려 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

이 섹션에서는 레거시 클라이언트와 Lync Server 2013 풀 또는 Lync Server 2013 클라이언트와 레거시 풀 간의 상호 운용성이 있을 때 마이그레이션 동시 사용 단계 중 사용자 환경에 대해 설명 합니다.

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013 풀

Lync Server 2013 풀에서 레거시 클라이언트를 사용 하는 경우 사용자에 게 다음과 같은 동작이 발생 합니다.

  - 두 사용자 간의 통화에서는 비디오 해상도가 레거시 풀과 동일하게 설정됩니다.

  - 단체 전화 회의에서는 비디오 해상도 및 비디오 회의 기능이 레거시 풀과 동일하게 설정됩니다. 갤러리 보기 및 고해상도는 사용할 수 없습니다.

</div>

<div>

## <a name="legacy-pools"></a>레거시 풀

레거시 풀에서 Lync Server 2013 클라이언트를 사용 하면 사용자에 게 다음과 같은 동작이 발생 합니다.

  - 두 사용자 간의 통화에서 Lync Server 2013 클라이언트는 다음과 같은 새 기능을 사용할 수 있습니다.
    
      - 두 참가자가 모두 Lync Server 2013 클라이언트를 사용 하는 경우에는 .h를 사용할 수 있습니다.
    
      - 레거시 서버가 대역내 프로 비전을 사용 하 여이 정보를 보내지 않으므로 Lync Server 2013 클라이언트는 TotalReceiveVideoBitRateKb의 기본값을 사용 합니다.

  - 단체 전화 회의에서는 비디오 해상도 및 비디오 회의 기능이 레거시 풀의 레거시 클라이언트에 사용되는 것과 동일하게 설정됩니다.

<div>


> [!NOTE]  
> 레거시 서버가 Lync Server 2013 클라이언트를 호스트 하는 경우에는 해당 풀의 모든 사용자가 저해상도 비디오만 수신 하 고 고해상도 동영상을 보낼 수 있도록 비디오 회의 대역폭을 구성할 수도 있습니다. 미디어 구성에서는 MaxVideoRateAllowed를 CIF-250K로 설정하고 회의 정책에서는 VideoBitRateKb를 2000kbps로 설정하는 경우를 한 가지 예로 들 수 있습니다. 이러한 상황에서는 풀의 사용자에 대해 고해상도를 사용할 수 없게 됩니다.<BR>Lync Server 2013 클라이언트에는 더 이상 MaxVideoRateAllowed가 사용 되지 않으므로 Lync Server 2013 클라이언트에서 고해상도 비디오를 요청 하는 것을 방지할 수 없습니다. 대신 풀의 모든 사용자에 대해 회의 정책의 VideoBitRateKb를 MaxVideoRateAllowed와 같은 값으로 설정하십시오(CIF를 250kbps로 설정하거나, VGA를 600kbps로 설정하거나, HD를 1500kbps로 설정함).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

