---
title: 'Lync Server 2013: 통합 연락처 저장소로 사용자 마이그레이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ab00e89c41b075e47d7764ce1c9c4cd3c471b8c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513635"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Lync Server 2013에서 통합 연락처 저장소로 사용자 마이그레이션

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-15_

사용자의 연락처가 다음과 같은 경우 Exchange 2013 서버로 자동으로 마이그레이션됩니다.

  - UcsAllowed가 True로 설정된 사용자 서비스 정책을 할당한 경우

  - Exchange 2013 사서함으로 프로 비전 되었으며 사서함에 한 번 이상 로그인 되어 있습니다.

  - Lync 2013 리치 클라이언트를 사용 하 여 로그인 합니다.

사용자가 Lync 2010 또는 이전 클라이언트를 사용 하 여 로그인 하거나 사용자가 Exchange 2013 서버에 연결 되어 있지 않은 경우에는 사용자 서비스 정책이 무시 되 고 사용자의 연락처가 Lync Server에 남아 있습니다.

다음 방법 중 하나를 사용하여 사용자 연락처가 마이그레이션되었는지 확인할 수 있습니다.

  - 클라이언트 컴퓨터에서 다음 레지스트리 키를 확인합니다.
    
    HKEY \_ 현재 \_ 사용자 \\ 소프트웨어 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ \<SIP URL\> \\ UCS
    
    사용자의 연락처가 Exchange 2013에 저장 되어 있는 경우이 키에는 값이 2165 인 InUCSMode 값이 포함 됩니다.

  - **Test-CsUnifiedContactStore** cmdlet을 실행합니다. Lync Server 관리 셸 명령줄에 다음을 입력 합니다.
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    **Test-CsUnifiedContactStore**가 정상적으로 실행되면 사용자 연락처가 통합 연락처 저장소로 마이그레이션된 것입니다.

</div>

<span> </span>

</div>

</div>

</div>

