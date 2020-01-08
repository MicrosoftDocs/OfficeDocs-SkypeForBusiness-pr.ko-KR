---
title: 'Lync Server 2013: Active Directory cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory cmdlets
ms:assetid: 313d73cb-f3db-4bc4-8708-de4da1d719c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415640(v=OCS.15)
ms:contentKeyID: 48183769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 727d2020b733d1956097e294891cf67b1fe333f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e4992-102">Lync Server 2013의 Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="e4992-102">Active Directory cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4992-103">_**마지막으로 수정한 주제:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="e4992-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="e4992-104">Active Directory cmdlet은 일반적으로 설치에 사용 되며, 관리자가 직접 호출 하는 경우에는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4992-104">The Active Directory cmdlets are typically used by Setup, and will rarely be called directly by an administrator.</span></span> <span data-ttu-id="e4992-105">그러나 관리자는 이러한 cmdlet을 사용 하 여 Microsoft Lync Server 2013에 대 한 도메인 또는 포리스트를 준비 (또는 unprepare) 하 고 필요한 Active Directory 스키마 파일을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4992-105">However, administrators can use these cmdlets to prepare (or unprepare) a domain or forest for Microsoft Lync Server 2013, and to install the required Active Directory schema files.</span></span>

<div>

## <a name="active-directory-cmdlets"></a><span data-ttu-id="e4992-106">Active Directory Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e4992-106">Active Directory Cmdlets</span></span>

<span data-ttu-id="e4992-107">다음은 Lync Server 2013 Active Directory 설정 관리와 직접 관련 된 cmdlet의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="e4992-107">The following is a list of cmdlets that relate directly to managing Lync Server 2013 Active Directory settings:</span></span>

<span data-ttu-id="e4992-108">**Active Directory**</span><span class="sxs-lookup"><span data-stu-id="e4992-108">**Active Directory**</span></span>

  - <span></span>  
    <span data-ttu-id="e4992-109">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4992-109">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4992-110">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4992-110">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4992-111">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4992-111">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4992-112">[사용 안 함-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4992-112">[Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4992-113">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4992-113">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4992-114">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4992-114">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4992-115">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4992-115">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4992-116">[Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4992-116">[Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4992-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4992-117">See Also</span></span>


[<span data-ttu-id="e4992-118">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="e4992-118">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

