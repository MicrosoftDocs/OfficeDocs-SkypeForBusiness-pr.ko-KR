---
title: 'Lync Server 2013: 주소록 관리용 테스트-CsAddressBookService'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test-CsAddressBookService for Address Book management
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48185206
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120a61ff03957a25cb7e6e0d09b8d3bccb11343c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="6abf0-102">Lync Server 2013의 주소록 관리를 위한 테스트-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="6abf0-102">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6abf0-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6abf0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6abf0-104">이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원은 테스트-CsAddressBookService cmdlet: RTCUniversalServerAdmins를 실행할 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abf0-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookService cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="6abf0-105">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abf0-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="6abf0-106">Lync Server 2013에는 특정 함수 또는 기능이 제대로 작동 하 고 있는지 확인 하기 위해 합성 명령을 시작 하는 많은 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abf0-106">Lync Server 2013 contains a number of cmdlets that initiate synthetic commands to confirm that a specific function or feature is working properly.</span></span> <span data-ttu-id="6abf0-107">테스트-CsAddressBookService는 정의 된 사용자가 주소록 웹 서비스에서 로컬 파일을 연결 하 고 요청할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abf0-107">Test-CsAddressBookService confirms that a defined user can connect and request the local files from the Address Book Web service.</span></span>

<span data-ttu-id="6abf0-108">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6abf0-108">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="6abf0-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6abf0-109">See Also</span></span>


[<span data-ttu-id="6abf0-110">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="6abf0-110">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

