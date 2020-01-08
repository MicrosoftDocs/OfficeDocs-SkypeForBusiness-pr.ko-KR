---
title: 'Lync Server 2013: 미디어를 사용 하지 않도록 네트워크 사이트와 서브넷 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c0f2d6461264ff8b54609e280c59986e1a923c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>네트워크 사이트와 서브넷을 연결 하 여 Lync Server 2013에서 미디어 무시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-12_

<div>


> [!NOTE]  
> 이 항목에서는 미디어를 구성 했다고 가정 하 고 미디어 바이패스를 위해 네트워크 지역 및 네트워크 사이트를 구성한 것으로 가정 합니다.



</div>

네트워크의 모든 서브넷은 특정 네트워크 사이트에 연결 되어 있어야 합니다. 이는 끝점이 위치한 네트워크 사이트를 확인 하는 데 서브넷 정보를 사용 하기 때문입니다. 한 세션에서 두 파티의 위치를 알고 있는 경우 미디어 바이패스는 처리를 위해 미디어를 보낼 위치를 결정할 수 있습니다.

미디어 바이패스에는 네트워크 사이트와 서브넷을 연결 하기 위한 특별 한 요구 사항이 없습니다. 토폴로지의 서브넷과 네트워크 사이트 간에 연결을 만들려면 [Lync Server 2013에서 서브넷을 네트워크 사이트와 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)의 절차를 따릅니다.

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>다음 단계: 대역폭 정책 프로필 만들기

서브넷을 미디어 바이패스에 대 한 네트워크 사이트와 연결한 후에는 미디어를 우회 하기 위해 서브넷을 양호한 연결을 통해 분할 하는 하나 이상의 대역폭 정책 프로필을 만들고 없는 경우 필요 합니다. 네트워크 영역 내에서 대역폭 제약 조건이 없는 네트워크 사이트의 모든 서브넷에 대 한 연결이 양호한 데, 따라서 해당 서브넷에서 미디어 바이패스를 사용할 수 있습니다.

대역폭 정책 프로필을 구성 하는 절차는 [Lync Server 2013에서 대역폭 정책 프로필 만들기](lync-server-2013-create-bandwidth-policy-profiles.md)를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

