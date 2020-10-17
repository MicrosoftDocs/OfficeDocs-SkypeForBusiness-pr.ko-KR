---
title: 'Lync Server 2013: Active Directory cmdlet'
description: 'Lync Server 2013: Active Directory cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory cmdlets
ms:assetid: 313d73cb-f3db-4bc4-8708-de4da1d719c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415640(v=OCS.15)
ms:contentKeyID: 48183769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c5e87cda24d5517b9c4501523fd06804ea20020
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571084"
---
# <a name="active-directory-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2bab0-103">Lync Server 2013의 Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="2bab0-103">Active Directory cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bab0-104">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="2bab0-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="2bab0-105">Active Directory cmdlet는 일반적으로 설치 프로그램에서 사용되며, 관리자가 직접 호출하는 경우는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2bab0-105">The Active Directory cmdlets are typically used by Setup, and will rarely be called directly by an administrator.</span></span> <span data-ttu-id="2bab0-106">그러나 관리자는 이러한 cmdlet을 사용 하 여 Microsoft Lync Server 2013의 도메인 또는 포리스트를 준비 (또는 unprepare) 하 고 필요한 Active Directory 스키마 파일을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bab0-106">However, administrators can use these cmdlets to prepare (or unprepare) a domain or forest for Microsoft Lync Server 2013, and to install the required Active Directory schema files.</span></span>

<div>

## <a name="active-directory-cmdlets"></a><span data-ttu-id="2bab0-107">Active Directory Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2bab0-107">Active Directory Cmdlets</span></span>

<span data-ttu-id="2bab0-108">다음은 Lync Server 2013 Active Directory 설정 관리와 직접 관련 된 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2bab0-108">The following is a list of cmdlets that relate directly to managing Lync Server 2013 Active Directory settings:</span></span>

<span data-ttu-id="2bab0-109">**Active Directory**</span><span class="sxs-lookup"><span data-stu-id="2bab0-109">**Active Directory**</span></span>

  - <span></span>  
    <span data-ttu-id="2bab0-110">[사용 안 함-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2bab0-110">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2bab0-111">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2bab0-111">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2bab0-112">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2bab0-112">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2bab0-113">[사용 안 함-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2bab0-113">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2bab0-114">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2bab0-114">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2bab0-115">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2bab0-115">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2bab0-116">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2bab0-116">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2bab0-117">[설치-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2bab0-117">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2bab0-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bab0-118">See Also</span></span>


[<span data-ttu-id="2bab0-119">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="2bab0-119">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

