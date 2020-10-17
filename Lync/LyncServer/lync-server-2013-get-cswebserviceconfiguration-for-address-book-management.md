---
title: 'Lync Server 2013: 주소록 관리 Get-CsWebServiceConfiguration'
description: 'Lync Server 2013: 주소록 관리 Get-CsWebServiceConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb22d7607f9ac18cda9c8653374ae86839b033e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554644"
---
# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="f3799-103">Lync Server 2013의 주소록 관리 Get-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="f3799-103">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3799-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f3799-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f3799-p101">이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalUserAdmins 및 RTCUniversalServerAdmins 그룹의 구성원은 Get-CsWebServiceConfiguration cmdlet을 로컬로 실행할 수 있습니다. 사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 가져오려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3799-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsWebServiceConfiguration cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

<span data-ttu-id="f3799-p102">Get-CsWebServiceConfiguration은 현재 조직에서 사용 중인 웹 서비스 구성 정보를 반환합니다. 메일 그룹 확장 기능의 상태는 주소록 서비스와 관련이 있습니다. EnableGroupExpansion 특성이 True이면 조직에서 현재 그룹 확장을 허용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f3799-p102">Get-CsWebServiceConfiguration returns information of the Web Services configuration currently in use in your organization. Of interest to the Address Book Services is the status of Distribution List Expansion function. If the attribute EnableGroupExpansion is True, your organization currently allows group expansion.</span></span>

<span data-ttu-id="f3799-110">예:</span><span class="sxs-lookup"><span data-stu-id="f3799-110">For example:</span></span>

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="f3799-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3799-111">See Also</span></span>


[<span data-ttu-id="f3799-112">Set-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="f3799-112">Get-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

