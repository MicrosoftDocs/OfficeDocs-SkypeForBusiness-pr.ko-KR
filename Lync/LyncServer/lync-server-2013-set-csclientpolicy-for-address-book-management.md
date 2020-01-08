---
title: 'Lync Server 2013: 설정-주소록 관리를 위한 CsClientPolicy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set-CsClientPolicy for Address Book management
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429723(v=OCS.15)
ms:contentKeyID: 48185726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248a04692327d93293e5bc5d37e650322b415ccb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="45ab7-102">Lync Server 2013의 주소록 관리에 대 한 Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="45ab7-102">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45ab7-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="45ab7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="45ab7-104">이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원은 Set CsClientPolicy cmdlet을 로컬로 실행할 권한이 있습니다. RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="45ab7-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsClientPolicy cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="45ab7-105">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ab7-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

<span data-ttu-id="45ab7-106">새 CsClientPolicy와 유사 하 게, 집합-CsClientPolicy cmdlet을 사용 하 여 이미 현재 있는 클라이언트 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ab7-106">Similar to New-CsClientPolicy, the Set-CsClientPolicy cmdlet allows you to modify client settings that are already in place.</span></span>

<span data-ttu-id="45ab7-107">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="45ab7-107">For example:</span></span>

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

<div>

## <a name="see-also"></a><span data-ttu-id="45ab7-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45ab7-108">See Also</span></span>


[<span data-ttu-id="45ab7-109">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="45ab7-109">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

