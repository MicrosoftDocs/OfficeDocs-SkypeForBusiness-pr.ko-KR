---
title: 'Lync Server 2013: 데이터베이스 및 관리 서버 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database and Management Server cmdlets
ms:assetid: b323bd59-8f71-4f03-af94-f3afb8620f4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415671(v=OCS.15)
ms:contentKeyID: 48185174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 770107bb4f7fafc4b1d43db8a5bdfcd3efef63e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-and-management-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="1ffbd-102">Lync Server 2013의 데이터베이스 및 관리 서버 cmdlet</span><span class="sxs-lookup"><span data-stu-id="1ffbd-102">Database and Management Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ffbd-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="1ffbd-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="1ffbd-104">데이터베이스 및 관리 서버 cmdlet은 Microsoft Lync Server 2013 백 엔드 데이터베이스와 프런트 엔드 관리 서비스를 모두 관리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ffbd-104">The database and Management Server cmdlets are used to manage both your Microsoft Lync Server 2013 back-end databases and your front-end management services.</span></span> <span data-ttu-id="1ffbd-105">이러한 cmdlet을 사용 하 여 Lync Server 2013에서 사용 되는 데이터베이스를 설치 또는 제거 하 고 중앙 관리 저장소에 대 한 Active Directory 서비스 제어 지점을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ffbd-105">You can use these cmdlets to install or uninstall any of the databases used by Lync Server 2013, in addition to configuring the Active Directory service control point for the Central Management store.</span></span>

<div>

## <a name="database-and-management-server-cmdlets"></a><span data-ttu-id="1ffbd-106">데이터베이스 및 관리 서버 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1ffbd-106">Database and Management Server Cmdlets</span></span>

<span data-ttu-id="1ffbd-107">다음은 데이터베이스 관리 및 관리 서버와 직접 관련 된 cmdlet의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1ffbd-107">The following is a list of cmdlets that relate directly to managing databases and the Management Server:</span></span>

<span data-ttu-id="1ffbd-108">**데이터베이스 및 관리 서버**</span><span class="sxs-lookup"><span data-stu-id="1ffbd-108">**Databases and Management Server**</span></span>

  - <span></span>  
    <span data-ttu-id="1ffbd-109">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-109">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1ffbd-110">[제거-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-110">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1ffbd-111">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-111">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1ffbd-112">[Install-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-112">[Install-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1ffbd-113">[Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-113">[Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1ffbd-114">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-114">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="1ffbd-115">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-115">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="1ffbd-116">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-116">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="1ffbd-117">[Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-117">[Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="1ffbd-118">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-118">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1ffbd-119">[Get-Csuserdatabasedatabasestate](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-119">[Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1ffbd-120">[Set-Csuserdatabasedatabasestate](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-120">[Set-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1ffbd-121">[업데이트-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-121">[Update-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1ffbd-122">[이동-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-122">[Move-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1ffbd-123">[Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-123">[Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="1ffbd-124">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ffbd-124">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ffbd-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ffbd-125">See Also</span></span>


[<span data-ttu-id="1ffbd-126">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="1ffbd-126">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

