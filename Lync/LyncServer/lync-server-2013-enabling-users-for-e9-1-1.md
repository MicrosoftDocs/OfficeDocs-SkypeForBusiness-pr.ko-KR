---
title: 'Lync Server 2013: E9에서 사용자 사용-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62d811d78695cbc04fa8def76da1843beddb586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013에서 E9에 대해 사용자 설정-1-1

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-06_

클라이언트 등록 중에 Lync Server는 위치 정책을 사용 하 여 Enterprise Voice 사용이 가능한 사용자의 E9-1-1 속성을 구성 합니다. 이 정책에는 E9-1-1이 구현 되는 방법을 정의 하는 설정이 포함 되어 있습니다. 예를 들어 위치 정책에는 긴급 전화 접속 문자열, 위치 정보 서비스에서 자동으로 위치를 제공 하지 않는 경우 사용자가 수동으로 위치를 입력 해야 하는지 여부 등의 정보가 포함 됩니다. 위치 정책에 대 한 전체 정의는 [Lync Server 2013의 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)를 참조 하세요.

Lync Server는 위치 정책을 서브넷에 기반 하 여 클라이언트에 게 할당 하거나, 전역, 사이트별 또는 사용자 단위 정책을 기반으로 하는 사용자에 게 할당할 수 있습니다. 사용자를 설정 하는 방법을 결정 하려면 먼저 다음 질문에 대답 해야 합니다.

  - **모든 사용자를 설정 하거나 엔터프라이즈의 특정 지리적 영역에 대 한 지원을 제한할 계획 입니까?**  
    전역 위치 정책을 사용 하 여 엔터프라이즈의 모든 사용자에 게 위치를 할당할 수 있습니다. 그러나 위치 정책을 Lync Server 네트워크 사이트에 할당 한 다음 사이트에 서브넷을 추가 하 여 E9-1-1 지원을 엔터프라이즈 내에서 선택 된 위치로 제한 하 고 각 사이트 별로 E9-1 라우팅 동작을 지정할 수 있습니다.

<!-- end list -->

  - **사용자 정책을 통해 개별 사용자를 사용할 계획 입니까?**  
    E9-1-1 지원을 사용자 지정 하려는 경우 특정 사용자 또는 공용 지역 전화 연락처 개체에 위치 정책을 직접 할당할 수 있습니다.

<!-- end list -->

  - **클라이언트가 네트워크 외부에서 로밍 하거나 정의 되지 않은 서브넷에서 연결 하는 경우 E9-1-1에 대해 클라이언트를 계속 사용할 수 있게 하려면**  
    사용자에 게 전역, 사이트 또는 사용자 단위 위치 정책을 할당 한 경우에는 클라이언트가 정의 된 서브넷 내에 없거나 위치 정보 서비스에 위치를 찾을 수 없는 경우 수동으로 클라이언트에 위치를 입력 해야 합니다. 자세한 내용은 [Lync Server 2013에서 수동으로 위치를 가져오기 위한 사용자 환경 정의](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

