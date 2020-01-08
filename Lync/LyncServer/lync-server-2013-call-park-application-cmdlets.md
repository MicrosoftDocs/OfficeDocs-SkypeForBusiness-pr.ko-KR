---
title: 'Lync Server 2013: 통화 공원 응용 프로그램 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park application cmdlets
ms:assetid: 30cc001f-b29e-4d44-bad7-65e1133e67b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415639(v=OCS.15)
ms:contentKeyID: 48183764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0530cdd5f9c9fdb7997b6c3576ca0f1280436458
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-application-cmdlets-in-lync-server-2013"></a><span data-ttu-id="aef69-102">Lync Server 2013의 통화 공원 응용 프로그램 cmdlet</span><span class="sxs-lookup"><span data-stu-id="aef69-102">Call Park application cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aef69-103">_**마지막으로 수정한 주제:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="aef69-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="aef69-104">통화 대기 응용 프로그램을 사용 하면 사용자가 전화를 걸고 다른 전화기에서 해당 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef69-104">Call Park application allows a user to place a call on hold, then retrieve that call from a different phone.</span></span> <span data-ttu-id="aef69-105">이러한 cmdlet을 사용 하 여 통화 공원 orbits 및 통화 공원 응용 프로그램에 대 한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef69-105">Use these cmdlets to configure settings for call park orbits and the Call Park application.</span></span>

<div>

## <a name="call-park-application-cmdlets"></a><span data-ttu-id="aef69-106">통화 공원 응용 프로그램 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="aef69-106">Call Park Application Cmdlets</span></span>

<span data-ttu-id="aef69-107">다음 cmdlet을 사용 하 여 통화 공원 응용 프로그램을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef69-107">The following cmdlets can be used to manage Call Park application.</span></span>

<span data-ttu-id="aef69-108">**통화 공원 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="aef69-108">**Call Park Application**</span></span>

  - <span></span>  
    <span data-ttu-id="aef69-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="aef69-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="aef69-110">[새로운 CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="aef69-110">[New-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="aef69-111">[제거-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="aef69-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="aef69-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="aef69-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="aef69-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="aef69-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="aef69-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="aef69-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="aef69-115">[새로운 CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="aef69-115">[New-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="aef69-116">[제거-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="aef69-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="aef69-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="aef69-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aef69-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aef69-118">See Also</span></span>


[<span data-ttu-id="aef69-119">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="aef69-119">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

