---
title: 'Lync Server 2013: 주소록 관리용으로 설정 된 CsAddressBookConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set-CsAddressBookConfiguration for Address Book management
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429700(v=OCS.15)
ms:contentKeyID: 48183913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edafd6b51da15b3302a9c3f454400325527fa631
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="302f8-102">Lync Server 2013의 주소록 관리에 대 한 집합-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="302f8-102">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="302f8-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="302f8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="302f8-104">이 cmdlet을 실행할 수 있는 사용자: 기본적으로 다음 그룹의 구성원에 게 Set CsAddressBookConfiguration cmdlet을 로컬로 실행할 권한이 부여 됩니다. RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="302f8-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="302f8-105">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="302f8-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

<span data-ttu-id="302f8-106">Set-CsAddressBookConfiguration은 기존 구성을 수정 하는 데 사용 된다는 점을 제외 하 고 새 CsAddressBookConfiguration cmdlet과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="302f8-106">Set-CsAddressBookConfiguration is similar to the New-CsAddressBookConfiguration cmdlet, except it is used to modify an existing configuration.</span></span>

<span data-ttu-id="302f8-107">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="302f8-107">For example:</span></span>

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

<div>

## <a name="see-also"></a><span data-ttu-id="302f8-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="302f8-108">See Also</span></span>


[<span data-ttu-id="302f8-109">Set-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="302f8-109">Set-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

