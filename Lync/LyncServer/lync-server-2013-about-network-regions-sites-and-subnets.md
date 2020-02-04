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
ms.openlocfilehash: 1f85d392f7d5f987bf14197fd5027c6568965ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>Lync Server 2013의 네트워크 지역, 사이트 및 서브넷 정보

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-24_

이 섹션에 설명 된 고급 엔터프라이즈 음성 기능은 네트워크 지역, 네트워크 사이트 및 서브넷에 대 한 특정 구성 요구 사항을 공유 합니다. 예를 들어 세 가지 고급 기능을 사용 하려면 토폴로지의 각 서브넷을 특정 *네트워크 사이트*와 연결 하 고 각 네트워크 사이트는 *네트워크 지역과*연결 되어 있어야 합니다.

<div>


> [!IMPORTANT]  
> 통화 허용 제어, E9-1-1 또는 미디어 바이패스에 대 한 네트워크 구성을 시작 하기 전에 계획 설명서의 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 항목에서 고급 Enterprise Voice 기능에 대 한 네트워크</A> 설정의 네트워크 설정에 대 한 추가 정보를 검토 했는지 확인 합니다. 전화 허용 제어에 대 한 기본 네트워크 구성에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 정의</A> 를 참조 하세요.



</div>

통화 허용 제어 및 E9-1-1에는 네트워크 사이트에 대 한 추가 구성 요구 사항이 있습니다.

  - 호출 허용 제어는 WAN 대역폭 제한에 의해 제한 된 각 사이트에 대해 *대역폭 정책 프로필* 을 지정 해야 합니다. 통화 허용 제어를 배포 하려는 경우에는 네트워크 사이트를 구성 하기 전에 [Lync Server 2013에서 대역폭 정책 프로필을 만들어야](lync-server-2013-create-bandwidth-policy-profiles.md) 합니다.

  - E9-1-1은 각 사이트에 대해 *위치 정책을* 지정 해야 합니다. E9-1-1을 배포 하려는 경우 네트워크 사이트를 구성 하기 전에 [Lync Server 2013에서 위치 정책을 만들어야](lync-server-2013-create-location-policies.md) 합니다.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>네트워크 지역, 네트워크 사이트 및 서브넷 만들기 또는 수정

다음 항목에서는 네트워크 지역 및 네트워크 사이트를 만들거나 수정 하 고 서브넷을 네트워크 사이트와 연결 하는 단계를 제공 합니다. 이러한 항목은 특정 고급 엔터프라이즈 음성 기능에 국한 되지 않습니다.

  - [Lync Server 2013에서 네트워크 영역 만들기 또는 수정](lync-server-2013-create-or-modify-a-network-region.md)

  - [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정](lync-server-2013-create-or-modify-a-network-site.md)

  - [Lync Server 2013 에서 네트워크 사이트에 서브넷 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

