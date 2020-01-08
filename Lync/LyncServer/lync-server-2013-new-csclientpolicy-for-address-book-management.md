---
title: 'Lync Server 2013: 주소록 관리용 새-CsClientPolicy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf1f7ebe085fc11d23381db9d1c474c79403d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="35aa5-102">Lync Server 2013의 주소록 관리에 대 한 새 CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="35aa5-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35aa5-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="35aa5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="35aa5-104">이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원은 새 CsClientPolicy cmdlet: RTCUniversalServerAdmins을 실행할 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35aa5-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="35aa5-105">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="35aa5-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="35aa5-106">Cmdlet 새 CsClientPolicy는 Lync Server 2013에서 사용할 수 있는 기능에 대 한 클라이언트 프로 비전에 대 한 여러 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="35aa5-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="35aa5-107">주소록 서비스의 경우 매개 변수 AddressBookAvailability이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="35aa5-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="35aa5-108">클라이언트가 사용할 수 있는 옵션에 직접적인 영향을 주는이 매개 변수는 세 가지 가능한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="35aa5-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="35aa5-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="35aa5-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="35aa5-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="35aa5-110">WebSearchOnly</span></span>

  - <span data-ttu-id="35aa5-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="35aa5-111">FileDownloadOnly</span></span>

<span data-ttu-id="35aa5-112">정의 되 면 클라이언트가 주소록에 액세스 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35aa5-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="35aa5-113">이 매개 변수를 정의 하는 경우 옵션 중 하나를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35aa5-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="35aa5-114">이 설정을 수정 하지 않으면 기본 WebSearchAndFileDownload가 계속 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35aa5-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="35aa5-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35aa5-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="35aa5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35aa5-116">See Also</span></span>


[<span data-ttu-id="35aa5-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="35aa5-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

