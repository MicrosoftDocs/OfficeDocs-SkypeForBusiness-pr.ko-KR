---
title: 'Lync Server 2013: 주소록 관리 Test-CsAddressBookWebQuery'
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
ms.openlocfilehash: 8c4112f34eb35bcf45991e6744327487afe9a2a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519245"
---
# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013의 주소록 관리 Test-CsAddressBookWebQuery

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalServerAdmins 그룹의 구성원은 Test-CsAddressBookWebQuery cmdlet을 실행할 수 있습니다. 사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 가져오려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Test-CsAddressBookService 가상 트랜잭션과 마찬가지로 Test-CsAddressBookWebQuery는 주소록 웹 쿼리에 대해 쿼리를 수행하여 제대로 작동하고 있는지 확인합니다. 이 cmdlet은 웹 티켓 인증에 연결되어 –UserCredential에 지정되어 있는 자격 증명을 제시합니다. 인증된 경우 이 cmdlet은 –TargetSipAddress 정보를 제시합니다. 이 cmdlet은 연락처에 대한 정보를 검색할 수 있었는 경우 성공을 보고합니다.

예:

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a>참고 항목


[테스트-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

