---
title: 'Lync Server 2013: 네트워크 지역, 사이트 및 서브넷 정보'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 142b8a13f8cf0600709fc1c43285e58ff182d19e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>Lync Server 2013의 네트워크 지역, 사이트 및 서브넷 정보

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-24_

이 섹션에서 설명하는 고급 Enterprise Voice 기능은 네트워크 지역, 네트워크 사이트 및 서브넷에 대해 특정 구성 요구 사항을 공유합니다. 예를 들어, 이 세 고급 기능을 사용하려면 토폴로지의 각 서브넷이 특정 *네트워크 사이트*에 연결되어 있어야 하며, 각 네트워크 사이트는 *네트워크 지역*에 연결되어 있어야 합니다.

<div>


> [!IMPORTANT]  
> 통화 허용 제어, E9-1-1 또는 미디어 바이패스에 대 한 네트워크 구성을 시작 하기 전에 계획 설명서의 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 항목에서 고급 Enterprise Voice 기능에 대 한 네트워크 설정</A> 의 네트워크 설정에 대 한 추가 정보를 검토 했는지 확인 합니다. 통화 허용 제어에 대 한 네트워크 구성에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 정의</A> 도 참조 하십시오.



</div>

통화 허용 제어 및 E9-1-1의 경우 네트워크 사이트에 대한 추가 구성 요구 사항이 있습니다.

  - 통화 허용 제어의 경우 WAN 대역폭 제한을 통해 제약되는 각 사이트에 대해 *대역폭 정책 프로필*을 지정해야 합니다. 통화 허용 제어를 배포 하려는 경우에는 네트워크 사이트를 구성 하기 전에 [Lync Server 2013에서 대역폭 정책 프로필을 만들어야](lync-server-2013-create-bandwidth-policy-profiles.md) 합니다.

  - E9-1-1의 경우 각 사이트에 대해 *위치 정책*을 지정해야 합니다. E9-1-1을 배포 하려는 경우 네트워크 사이트를 구성 하기 전에 [Lync Server 2013에서 위치 정책을 만들어야](lync-server-2013-create-location-policies.md) 합니다.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>네트워크 지역, 네트워크 사이트 및 서브넷 만들기 또는 수정

다음 항목에서는 네트워크 지역과 네트워크 사이트를 만들거나 수정하고, 서브넷을 네트워크 사이트와 연결하는 단계를 제공합니다. 이러한 항목의 내용은 특정 고급 Enterprise Voice 기능에만 해당되는 것이 아닙니다.

  - [Lync Server 2013에서 네트워크 지역 만들기 또는 수정](lync-server-2013-create-or-modify-a-network-region.md)

  - [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정](lync-server-2013-create-or-modify-a-network-site.md)

  - [Lync Server 2013에서 서브넷을 네트워크 사이트에 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

