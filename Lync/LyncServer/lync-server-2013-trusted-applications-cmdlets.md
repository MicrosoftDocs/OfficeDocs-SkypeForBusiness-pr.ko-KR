---
title: 'Lync Server 2013: 신뢰할 수 있는 응용 프로그램 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Trusted applications cmdlets
ms:assetid: 4d6ae0dc-e3e0-4519-8b74-9e941dea21e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415652(v=OCS.15)
ms:contentKeyID: 48184071
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8738855f7784e5586659eb80a4a42e5de43adf00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="trusted-applications-cmdlets-in-lync-server-2013"></a><span data-ttu-id="98382-102">Lync Server 2013의 신뢰할 수 있는 응용 프로그램 cmdlet</span><span class="sxs-lookup"><span data-stu-id="98382-102">Trusted applications cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98382-103">_**마지막으로 수정한 주제:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="98382-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="98382-104">신뢰할 수 있는 응용 프로그램은 Microsoft Lync Server 2013의 일부로 실행할 신뢰할 수 있는 상태를 제공 하는 제 3 자에 의해 개발 된 응용 프로그램이 며, 제품의 기본 제공 부분이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="98382-104">A trusted application is an application developed by a third party that is given trusted status to run as part of Microsoft Lync Server 2013 but that is not a built-in part of the product.</span></span> <span data-ttu-id="98382-105">Lync Server 2013는 신뢰할 수 있는 응용 프로그램을 구성 하 고 관리 하는 데 사용 되는 cmdlet을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98382-105">Lync Server 2013 provides cmdlets that can be used to configure and managed trusted applications.</span></span>

<div>

## <a name="trusted-applications-cmdlets"></a><span data-ttu-id="98382-106">신뢰할 수 있는 응용 프로그램 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="98382-106">Trusted Applications Cmdlets</span></span>

<span data-ttu-id="98382-107">다음 cmdlet을 사용 하 여 신뢰할 수 있는 응용 프로그램을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="98382-107">Use the following cmdlets to manage trusted applications.</span></span>

<span data-ttu-id="98382-108">**신뢰할 수 있는 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="98382-108">**Trusted Applications**</span></span>

  - <span></span>  
    <span data-ttu-id="98382-109">[Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-109">[Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-110">[새로운 CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-110">[New-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-111">[제거-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-111">[Remove-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-112">[Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-112">[Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="98382-113">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-113">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-114">[새로운 CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-114">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-115">[제거-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-115">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="98382-116">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-116">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-117">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-117">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-118">[제거-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-118">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-119">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-119">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="98382-120">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-120">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-121">[새로운 CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-121">[New-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-122">[제거-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-122">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="98382-123">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="98382-123">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98382-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98382-124">See Also</span></span>


[<span data-ttu-id="98382-125">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="98382-125">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

