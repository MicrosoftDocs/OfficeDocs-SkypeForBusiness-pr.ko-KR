---
title: 'Lync Server 2013: 잠겨진 Active Directory 도메인 서비스 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae8ea746ba8ea2ddea8d696d42865324da60ecbc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>Lync Server 2013에서 잠긴 Active Directory 도메인 서비스 준비

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-05-14_

조직은 보안 위험을 완화할 수 있도록 Active Directory 도메인 서비스를 잠그는 경우가 많습니다. 그러나 잠겨 있는 Active Directory 환경은 Lync Server 2013에 필요한 권한을 제한할 수 있습니다. Lync Server 2013에 대해 잠긴 Active Directory 환경을 적절 하 게 준비 하려면 몇 가지 추가 고려 사항과 단계가 필요 합니다.

잠겨 있는 Active Directory 환경에서 사용 권한이 제한 되는 일반적인 두 가지 방법은 다음과 같습니다.

  - 인증 된 사용자 Ace (액세스 제어 항목)가 컨테이너에서 제거 됩니다.

  - User, Contact, InetOrgPerson 또는 Computer 개체의 컨테이너에서 사용 권한 상속이 사용 되지 않도록 설정 됩니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 인증 된 사용자 권한이 제거 됨](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Lync Server 2013의 컴퓨터, 사용자 또는 InetOrgPerson 컨테이너에서 사용 권한 상속이 비활성화 됨](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

