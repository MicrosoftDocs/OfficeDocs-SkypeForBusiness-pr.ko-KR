---
title: 'Lync Server 2013: 통합 연락처 저장소로 사용자 마이그레이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ec64192f1aa83eb9c076976c20a9e87ab9115
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Lync Server 2013에서 통합 연락처 저장소로 사용자 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-15_

사용자의 연락처가 다음과 같이 자동으로 Exchange 2013 서버로 마이그레이션됩니다.

  - (으)로 지정 된 사용자 서비스 정책에 대 한 모든 권한이 True로 설정 되었습니다.

  - 이 (가) Exchange 2013 사서함으로 프로 비전 되었으며 사서함에 한 번 이상 로그인 되어 있습니다.

  - Lync 2013 리치 클라이언트를 사용 하 여 로그인 합니다.

사용자가 Lync 2010 또는 이전 클라이언트를 사용 하 여 로그인 하거나 사용자가 Exchange 2013 서버에 연결 되어 있지 않은 경우 사용자 서비스 정책이 무시 되 고 사용자의 연락처가 Lync Server에 남아 있습니다.

다음 방법 중 하나를 사용 하 여 사용자의 연락처가 마이그레이션 되었는지 여부를 확인할 수 있습니다.

  - 클라이언트 컴퓨터에서 다음 레지스트리 키를 확인 합니다.
    
    HKEY\_현재\_사용자\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS
    
    사용자의 연락처가 Exchange 2013에 저장 되어 있는 경우이 키에는 2165 값을 사용 하 여 InUCSMode 값이 포함 됩니다.

  - **테스트 CsUnifiedContactStore** cmdlet을 실행 합니다. Lync Server 관리 셸 명령줄에 다음을 입력 합니다.
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    **테스트-CsUnifiedContactStore** 성공 하면 사용자의 연락처가 통일 된 대화 상대 저장소로 마이그레이션됩니다.

</div>

<span> </span>

</div>

</div>

</div>

