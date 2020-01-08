---
title: 'Lync Server 2013: Set-주소록 관리를 위한 CsWebServiceConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set-CsWebServiceConfiguration for Address Book management
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48184572
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cb1fa5d6474a792442510181a5c13b17e074c61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="1479d-102">Set-Lync Server 2013의 주소록 관리에 대 한 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="1479d-102">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1479d-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1479d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1479d-104">이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원은 Set-CsWebServiceConfiguration cmdlet을 로컬로 실행할 권한이 있습니다. RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1479d-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="1479d-105">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1479d-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

<span data-ttu-id="1479d-106">CsWebServiceConfiguration cmdlet을 사용 하면 관리자가 웹 서비스의 구성에서 기존 특성을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1479d-106">The Set-CsWebServiceConfiguration cmdlet allows the administrator to redefine an existing attribute in the configuration of the Web Services.</span></span>

<span data-ttu-id="1479d-107">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1479d-107">For example:</span></span>

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

<div>

## <a name="see-also"></a><span data-ttu-id="1479d-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1479d-108">See Also</span></span>


[<span data-ttu-id="1479d-109">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="1479d-109">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

