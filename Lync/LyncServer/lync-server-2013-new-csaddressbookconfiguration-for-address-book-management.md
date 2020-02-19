---
title: 'Lync Server 2013: 주소록 관리를 위한 신규-CsAddressBookConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb0e7a605d7859cf9eb53e72ad0bdf7273b0d8c7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="53870-102">Lync Server 2013의 주소록 관리를 위한 신규-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="53870-102">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53870-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="53870-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="53870-p101">이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalServerAdmins 그룹에 속한 구성원은 New-CsAddressBookConfiguration cmdlet을 로컬로 실행할 수 있습니다. 사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 가져오려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="53870-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

<span data-ttu-id="53870-p102">New-CsAddressBookConfiguration cmdlet은 새 구성을 만들어 주소록의 동작을 관리합니다. 이 cmdlet은 주소록 서비스에서 클라이언트 다운로드 파일을 만들지 여부, 정규화 규칙 사용 여부, 델타 및 컴팩트 델타 파일 보존 기간, 전체 새 파일 만들기를 통합하기 전 델타 파일 크기, 전체 파일 주소록이 만들어지는 시기 및 사용자 데이터베이스에서 정보 동기화를 위한 내부 상태 등을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="53870-p102">The New-CsAddressBookConfiguration cmdlet creates a new configuration to manage the behavior of the Address book. Specific to this cmdlet is the ability to define if the Address Book Service creates the client download files, how and if normalization rules are used, how long to retain delta and compact delta files, delta file size before incorporating a new full file creation, what time of day the full file Address Book is created, and what the internal should be for synchronization of information in the User database.</span></span>

<span data-ttu-id="53870-108">예:</span><span class="sxs-lookup"><span data-stu-id="53870-108">For example:</span></span>

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a><span data-ttu-id="53870-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53870-109">See Also</span></span>


[<span data-ttu-id="53870-110">새-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="53870-110">New-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

