---
title: 'Lync Server 2013: 주소록 관리 Remove-CsWebServiceConfiguration'
description: 'Lync Server 2013: 주소록 관리 Remove-CsWebServiceConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsWebServiceConfiguration for Address Book management
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48184848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 145cb1cb98bcb4c988a8fdaea74a4eae86d5fc4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553514"
---
# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="c38eb-103">Lync Server 2013의 주소록 관리 Remove-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="c38eb-103">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c38eb-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c38eb-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c38eb-p101">이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalServerAdmins 그룹의 구성원은 Remove-CsWebServiceConfiguration cmdlet을 로컬로 실행할 수 있습니다. 사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 가져오려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c38eb-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

<span data-ttu-id="c38eb-107">관리자는 이전에 만든 웹 서비스 구성을 Remove-CsWebServiceConfiguration cmdlet로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c38eb-107">The Remove-CsWebServiceConfiguration cmdlet allows an administrator to remove a previously created Web Services configuration.</span></span> <span data-ttu-id="c38eb-108">이 cmdlet은 전역 웹 서비스 구성을 제거하지는 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c38eb-108">The cmdlet cannot remove the global Web Services configuration.</span></span>

<span data-ttu-id="c38eb-109">예:</span><span class="sxs-lookup"><span data-stu-id="c38eb-109">For example:</span></span>

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="c38eb-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c38eb-110">See Also</span></span>


[<span data-ttu-id="c38eb-111">Set-cswebserviceconfiguration을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c38eb-111">Remove-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

