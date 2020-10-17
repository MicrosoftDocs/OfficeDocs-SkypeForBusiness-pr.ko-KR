---
title: 'Lync Server 2013: 웹 서버 및 서비스 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web server and services cmdlets
ms:assetid: 07ce7fd4-4068-4957-9cb9-fd121b43858c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415631(v=OCS.15)
ms:contentKeyID: 48183326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c43092e9b0f97bc669c8f1e57be888b6b7af3c0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518245"
---
# <a name="web-server-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ff086-102">Lync Server 2013의 웹 서버 및 서비스 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff086-102">Web server and services cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff086-103">_**마지막으로 수정 된 항목:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="ff086-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="ff086-104">대부분의 Microsoft Lync Server 2013 구성 요소는 웹 서비스 또는 웹 페이지를 사용 하 여 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff086-104">Many Microsoft Lync Server 2013 components are web-based: these components either use Web Services or webpages to carry out their tasks.</span></span> <span data-ttu-id="ff086-105">웹 서버 및 웹 서비스 cmdlet을 사용 하면 웹 서버 설정을 구성 하 고 단순 Url을 관리 하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff086-105">The Web Server and Web services cmdlets enable you to do such things as configure Web Server settings and to manage simple URLs.</span></span> <span data-ttu-id="ff086-106">간단한 Url을 통해 사용자가 모임 및 전화 회의에 보다 쉽게 참가할 수 있으며 관리자가 Lync Server 2013 제어판에 쉽게 로그온 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff086-106">Simple URLs make it easier for users to join meetings and conferences, and make it easier for Administrators to log on to the Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="web-server-and-web-services-cmdlets"></a><span data-ttu-id="ff086-107">웹 서버 및 웹 서비스 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff086-107">Web Server and Web Services Cmdlets</span></span>

<span data-ttu-id="ff086-108">다음은 웹 서버 및 웹 서비스 관리와 직접적으로 관련된 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ff086-108">The following is a list of cmdlets that relate directly to managing Web Servers and Web Services:</span></span>

<span data-ttu-id="ff086-109">**웹 서버 및 서비스**</span><span class="sxs-lookup"><span data-stu-id="ff086-109">**Web Servers and Services**</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-110">[New-cssimpleurl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-110">[New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ff086-111">[Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-111">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-112">[Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-112">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-113">[Get-cssimpleurlconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-113">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-114">[Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-114">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ff086-115">[New-cssimpleurlentry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-115">[New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ff086-116">[새-CsWebOrigin](https://technet.microsoft.com/library/JJ950236(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-116">[New-CsWebOrigin](https://technet.microsoft.com/library/JJ950236(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ff086-117">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-117">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ff086-118">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-118">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-119">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-119">[New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-120">[Set-cswebserviceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-120">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-121">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-121">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ff086-122">[New-cswebtrustedcacertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-122">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ff086-123">[새-C고 Ercosaccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-123">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ff086-124">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-124">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-125">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-125">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-126">[Get-cskerberosaccountassignment을 제거 합니다.](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-126">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-127">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-127">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ff086-128">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-128">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ff086-129">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-129">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ff086-130">[Test-cswebapp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-130">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="ff086-131">[Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ff086-131">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff086-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff086-132">See Also</span></span>


[<span data-ttu-id="ff086-133">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="ff086-133">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

