---
title: 'Lync Server 2013: 주소록 관리 New-CsClientPolicy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a253fb46dfdfe63957efa97ffa68d97ead65ed87
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508825"
---
# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="c15f9-102">Lync Server 2013의 주소록 관리 New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c15f9-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c15f9-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c15f9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c15f9-104">이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalServerAdmins 그룹의 구성원은 New-CsClientPolicy cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15f9-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="c15f9-105">사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f9-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="c15f9-106">Cmdlet New-CsClientPolicy는 Lync Server 2013에서 사용할 수 있는 기능에 대 한 클라이언트 프로 비전을 위한 다 수의 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15f9-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="c15f9-107">주소록 서비스의 경우 AddressBookAvailability 매개 변수가 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15f9-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="c15f9-108">클라이언트에서 사용할 수 있는 옵션에 직접 영향을 주는 이 매개 변수에는 다음과 같은 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15f9-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="c15f9-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="c15f9-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="c15f9-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="c15f9-110">WebSearchOnly</span></span>

  - <span data-ttu-id="c15f9-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="c15f9-111">FileDownloadOnly</span></span>

<span data-ttu-id="c15f9-p103">이 매개 변수가 정의된 경우 클라이언트에서 주소록에 액세스하는 방법이 결정됩니다. 이 매개 변수를 정의할 경우 옵션 중 하나를 정의해야 합니다. 이 설정을 수정하지 않으면 기본 WebSearchAndFileDownload가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15f9-p103">When defined, it determines how the Address Book is accessed by clients. If you define this parameter, you must define one of the options. If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="c15f9-115">예:</span><span class="sxs-lookup"><span data-stu-id="c15f9-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="c15f9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c15f9-116">See Also</span></span>


[<span data-ttu-id="c15f9-117">신규-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c15f9-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

