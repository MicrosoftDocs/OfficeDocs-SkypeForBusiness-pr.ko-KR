---
title: 'Lync Server 2013: 잠긴 Active Directory 도메인 서비스 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 482c5a59c6dc53fc712db7e77430367dd9c37af5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>Lync Server 2013에서 잠긴 Active Directory 도메인 서비스 준비

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-05-14_

조직에서 보안 위험을 줄일 수 있도록 Active Directory 도메인 서비스를 잠그는 경우가 많습니다. 그러나 잠겨 있는 Active Directory 환경은 Lync Server 2013에 필요한 권한을 제한할 수 있습니다. Lync Server 2013의 잠겨진 Active Directory 환경을 올바르게 준비 하려면 몇 가지 추가 고려 사항 및 단계가 필요 합니다.

잠겨 있는 Active Directory 환경에서 사용 권한이 제한 되는 두 가지 일반적인 방법은 다음과 같습니다.

  - 인증 된 Ace (사용자 액세스 제어 항목)가 컨테이너에서 제거 됩니다.

  - 사용자, 연락처, InetOrgPerson 또는 컴퓨터 개체의 컨테이너에서 사용 권한 상속을 사용 하지 않도록 설정 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 인증된 사용자 권한이 제거됨](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Lync Server 2013의 Computer, User 또는 InetOrgPerson 컨테이너에서 권한 상속이 비활성화됨](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

