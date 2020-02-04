---
title: 'Lync Server 2013: 등록자 및 디렉터 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registrar and Director cmdlets
ms:assetid: 327c08ab-7e1e-47c0-b280-a001722c116f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415641(v=OCS.15)
ms:contentKeyID: 48183813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5512b80d5860c94d379c5c5d43e51cdb8ac5177
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registrar-and-director-cmdlets-in-lync-server-2013"></a><span data-ttu-id="3e5c2-102">Lync Server 2013의 등록자 및 디렉터 cmdlet</span><span class="sxs-lookup"><span data-stu-id="3e5c2-102">Registrar and Director cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e5c2-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="3e5c2-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="3e5c2-104">등록 기관 및 디렉터는 로그온 요청을 인증 하 고 사용자 상태 및 사용 가능성에 대 한 정보를 유지 관리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e5c2-104">Registrars and Directors are used to authenticate logon requests and to maintain information about user status and availability.</span></span> <span data-ttu-id="3e5c2-105">레지스트라 및 디렉터 cmdlet을 사용 하 여 이러한 서버의 구성 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5c2-105">The Registrar and Director cmdlets enable you to manage configuration settings for these servers.</span></span>

<div>

## <a name="registrar-and-director-cmdlets"></a><span data-ttu-id="3e5c2-106">등록자 및 디렉터 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3e5c2-106">Registrar and Director Cmdlets</span></span>

<span data-ttu-id="3e5c2-107">다음은 등록 기관 및 디렉터 관리와 직접 관련 된 cmdlet의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3e5c2-107">The following is a list of cmdlets that relate directly to managing Registrars and Directors:</span></span>

<span data-ttu-id="3e5c2-108">**등록 기관 및 감독**</span><span class="sxs-lookup"><span data-stu-id="3e5c2-108">**Registrars and Directors**</span></span>

  - <span></span>  
    <span data-ttu-id="3e5c2-109">[집합-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3e5c2-109">[Set-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3e5c2-110">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/en-us/library/JJ619172(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3e5c2-110">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/en-us/library/JJ619172(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3e5c2-111">[CsRegistrar 설정](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3e5c2-111">[Set-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3e5c2-112">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3e5c2-112">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3e5c2-113">[새로운 CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3e5c2-113">[New-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3e5c2-114">[제거-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3e5c2-114">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3e5c2-115">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3e5c2-115">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3e5c2-116">[Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3e5c2-116">[Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e5c2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e5c2-117">See Also</span></span>


[<span data-ttu-id="3e5c2-118">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="3e5c2-118">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

