---
title: 'Lync Server 2013: 주소록 관리용 가져오기-CsAddressBookConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30a9f29ee4842b11c503e913d1e80e97e2dab274
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="ff7f3-102">Lync Server 2013의 주소록 관리를 위한 가져오기-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="ff7f3-102">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff7f3-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ff7f3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ff7f3-104">이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원은 Get-CsAddressBookConfiguration cmdlet을 로컬로 실행할 권한이 있습니다. RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ff7f3-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="ff7f3-105">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7f3-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

<span data-ttu-id="ff7f3-106">Cmdlet Get CsAddressBookConfiguration은 이미 존재 하는 구성에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7f3-106">The cmdlet Get-CsAddressBookConfiguration returns information about a configuration that already exists.</span></span>

<span data-ttu-id="ff7f3-107">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7f3-107">For example:</span></span>

    Get-CsAddressBookConfiguration -Identity site:Redmond

<span data-ttu-id="ff7f3-108">Get-CsAddressBookConfiguration 및 Set CsAddressBookConfiguration 기능을 결합 하면 관리자가 수정할 구성을 정의한 다음 수정 내용을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7f3-108">Combining the functionality of Get-CsAddressBookConfiguration and Set-CsAddressBookConfiguration allows the administrator to define which configurations to modify and then apply the modifications.</span></span> <span data-ttu-id="ff7f3-109">예를 들어 다음과 같이 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff7f3-109">For example, this combined:</span></span>

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

<span data-ttu-id="ff7f3-110">모든 사이트의 모든 구성을 반환 하 고 구성에 23:00 시간을 기준으로 RunTimeOfDay를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7f3-110">Returns all configurations in all sites and applies the RunTimeOfDay of 23:00 hours to the configurations.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ff7f3-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff7f3-111">See Also</span></span>


[<span data-ttu-id="ff7f3-112">Get-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="ff7f3-112">Get-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

