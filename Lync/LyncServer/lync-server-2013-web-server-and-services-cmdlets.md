---
title: 'Lync Server 2013: 웹 서버 및 서비스 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web server and services cmdlets
ms:assetid: 07ce7fd4-4068-4957-9cb9-fd121b43858c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415631(v=OCS.15)
ms:contentKeyID: 48183326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 754e8a96c240b99de7238c150fd60b37772bbd07
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-server-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="4d92b-102">Lync Server 2013의 웹 서버 및 서비스 cmdlet</span><span class="sxs-lookup"><span data-stu-id="4d92b-102">Web server and services cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d92b-103">_**마지막으로 수정한 주제:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="4d92b-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="4d92b-104">대부분의 Microsoft Lync Server 2013 구성 요소는 웹 서비스 또는 웹 페이지를 사용 하 여 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d92b-104">Many Microsoft Lync Server 2013 components are web-based: these components either use Web Services or webpages to carry out their tasks.</span></span> <span data-ttu-id="4d92b-105">웹 서버와 웹 서비스 cmdlet을 사용 하면 웹 서버 설정을 구성 하 고 간단한 Url을 관리 하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d92b-105">The Web Server and Web services cmdlets enable you to do such things as configure Web Server settings and to manage simple URLs.</span></span> <span data-ttu-id="4d92b-106">간단한 Url을 통해 사용자가 모임과 회의에 더 쉽게 참가 하 고 관리자가 Lync Server 2013 제어판에 쉽게 로그온 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d92b-106">Simple URLs make it easier for users to join meetings and conferences, and make it easier for Administrators to log on to the Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="web-server-and-web-services-cmdlets"></a><span data-ttu-id="4d92b-107">웹 서버 및 웹 서비스 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4d92b-107">Web Server and Web Services Cmdlets</span></span>

<span data-ttu-id="4d92b-108">다음은 웹 서버와 웹 서비스를 관리 하는 것과 직접 관련 된 cmdlet의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4d92b-108">The following is a list of cmdlets that relate directly to managing Web Servers and Web Services:</span></span>

<span data-ttu-id="4d92b-109">**웹 서버 및 서비스**</span><span class="sxs-lookup"><span data-stu-id="4d92b-109">**Web Servers and Services**</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-110">[New-CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-110">[New-CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4d92b-111">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-111">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-112">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-112">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-113">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-113">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-114">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-114">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4d92b-115">[New-CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-115">[New-CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4d92b-116">[새 CsWebOrigin](https://technet.microsoft.com/en-us/library/JJ950236(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-116">[New-CsWebOrigin](https://technet.microsoft.com/en-us/library/JJ950236(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4d92b-117">[Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-117">[Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4d92b-118">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-118">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-119">[New-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-119">[New-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-120">[제거-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-120">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-121">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-121">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4d92b-122">[새로운 CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-122">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4d92b-123">[신규-C(c) Ercosaccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-123">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4d92b-124">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-124">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-125">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-125">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-126">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-126">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-127">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-127">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4d92b-128">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-128">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4d92b-129">[Set-c. Ercosaccountpassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-129">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4d92b-130">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-130">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="4d92b-131">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4d92b-131">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d92b-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d92b-132">See Also</span></span>


[<span data-ttu-id="4d92b-133">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="4d92b-133">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

