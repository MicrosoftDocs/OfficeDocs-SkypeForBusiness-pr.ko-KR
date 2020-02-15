---
title: 'Lync Server 2013: (선택 사항) 전화 접속 회의 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 133d0bccb919e537998878306b3bbf85d77bd0cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a>반드시 Lync Server 2013에서 전화 접속 회의 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2011-01-21_

전화 접속 회의 설정 웹 페이지와 전화 접속 액세스 번호가 올바르게 작동하는지 확인하려면 다음을 수행해야 합니다.

  - 단순 URL에 로그인하여 전화 접속 회의 설정 웹 페이지를 테스트합니다.

  - 이 항목 뒷부분에 나와 있는 스크립트를 실행하여 특정 풀에 대해 액세스 번호가 올바르게 작동하는지 테스트합니다. 이 스크립트는 액세스 번호에 대한 호출을 시뮬레이트합니다. 이 스크립트를 사용하려면 특정 풀에서 호스팅되는 단일 UC(통합 통신) 클라이언트의 SIP 주소 및 자격 증명이 필요합니다.

이 단계는 선택 사항입니다.

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a>특정 풀에 대한 액세스 번호를 테스트하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령 프롬프트에서 다음을 실행합니다.
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    결과 보고서에는 성공 또는 실패와 특정 진단 정보가 표시됩니다. –Verbose 플래그는 발견된 액세스 번호의 수와 각 번호의 세부 사항에 대해 더욱 자세한 정보를 제공합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

