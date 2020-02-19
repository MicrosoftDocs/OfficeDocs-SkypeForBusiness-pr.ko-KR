---
title: 'Lync Server 2013: 신뢰할 수 있는 응용 프로그램 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Trusted applications cmdlets
ms:assetid: 4d6ae0dc-e3e0-4519-8b74-9e941dea21e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415652(v=OCS.15)
ms:contentKeyID: 48184071
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 037af965f87c0ec156bc4f3d41fd298cb61b113f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="trusted-applications-cmdlets-in-lync-server-2013"></a><span data-ttu-id="d2c44-102">Lync Server 2013의 신뢰할 수 있는 응용 프로그램 cmdlet</span><span class="sxs-lookup"><span data-stu-id="d2c44-102">Trusted applications cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2c44-103">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="d2c44-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="d2c44-104">신뢰할 수 있는 응용 프로그램 이란 타사에서 개발한 응용 프로그램으로, Microsoft Lync Server 2013의 일부로 실행 되며 제품의 기본 제공 부분은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d2c44-104">A trusted application is an application developed by a third party that is given trusted status to run as part of Microsoft Lync Server 2013 but that is not a built-in part of the product.</span></span> <span data-ttu-id="d2c44-105">Lync Server 2013에서는 신뢰할 수 있는 응용 프로그램을 구성 하 고 관리 하는 데 사용 되는 cmdlet을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c44-105">Lync Server 2013 provides cmdlets that can be used to configure and managed trusted applications.</span></span>

<div>

## <a name="trusted-applications-cmdlets"></a><span data-ttu-id="d2c44-106">신뢰할 수 있는 응용 프로그램 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d2c44-106">Trusted Applications Cmdlets</span></span>

<span data-ttu-id="d2c44-107">다음 cmdlet를 사용하여 신뢰할 수 있는 응용 프로그램을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c44-107">Use the following cmdlets to manage trusted applications.</span></span>

<span data-ttu-id="d2c44-108">**신뢰할 수 있는 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="d2c44-108">**Trusted Applications**</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-109">[New-cstrustedapplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-109">[Get-CsTrustedApplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-110">[New-cstrustedapplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-110">[New-CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-111">[New-cstrustedapplication을 제거 합니다.](https://technet.microsoft.com/library/Gg398176(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-111">[Remove-CsTrustedApplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-112">[New-cstrustedapplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-112">[Set-CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d2c44-113">[CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-113">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-114">[CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-114">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-115">[CsTrustedApplicationComputer을 제거 합니다.](https://technet.microsoft.com/library/Gg398838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-115">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d2c44-116">[CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-116">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-117">[CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-117">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-118">[CsTrustedApplicationEndpoint을 제거 합니다.](https://technet.microsoft.com/library/Gg398837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-118">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-119">[CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-119">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d2c44-120">[New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-120">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-121">[New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-121">[New-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-122">[New-cstrustedapplicationpool을 제거 합니다.](https://technet.microsoft.com/library/Gg398750(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-122">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2c44-123">[New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2c44-123">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2c44-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2c44-124">See Also</span></span>


[<span data-ttu-id="d2c44-125">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="d2c44-125">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

