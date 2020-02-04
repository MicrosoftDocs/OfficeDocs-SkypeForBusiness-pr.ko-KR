---
title: 'Lync Server 2013: 주소록 관리를 위한 테스트-CsAddressBookWebQuery'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c50497979e8439a60799864376d1f93d36646cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013의 주소록 관리를 위한 테스트-CsAddressBookWebQuery

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

이 cmdlet을 실행할 수 있는 사용자: 기본적으로 다음 그룹의 구성원은 테스트-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins을 실행할 권한이 있습니다. 이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

테스트-CsAddressBookService 가상 트랜잭션과 유사 하 게, 테스트-CsAddressBookWebQuery는 주소록 웹 쿼리에 대 한 쿼리를 수행 하 여 제대로 작동 하는지 확인 합니다. Cmdlet이 웹 티켓 인증에 연결 하 고 – UserCredential에 지정 된 자격 증명을 표시 합니다. 인증 된 경우 cmdlet은 – TargetSipAddress 정보를 표시 합니다. 연락처에 대 한 정보를 검색할 수 있는 경우에는 cmdlet에서 성공을 보고 해야 합니다.

예를 들면 다음과 같습니다.

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a>참고 항목


[Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

