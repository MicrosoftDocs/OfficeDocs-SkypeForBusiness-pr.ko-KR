---
title: 'Lync Server 2013: 중앙 로깅 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Centralized Logging cmdlets
ms:assetid: 8ba5bcae-8b99-489c-9355-6e77d4ad9100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205064(v=OCS.15)
ms:contentKeyID: 48184743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05bdedc57fca4c51351bcee351c7774c471cc821
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="centralized-logging-cmdlets-in-lync-server-2013"></a><span data-ttu-id="92989-102">Lync Server 2013의 중앙 집중화 된 로깅 cmdlet</span><span class="sxs-lookup"><span data-stu-id="92989-102">Centralized Logging cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92989-103">_**마지막으로 수정한 주제:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="92989-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="92989-104">중앙 로깅 cmdlet은 관리자가 Microsoft Lync Server 2013에서 도입 된 중앙 집중식 로깅 기능을 관리 하 고 구성할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92989-104">The centralized logging cmdlets provide a way for administrators to manage and configure the centralized logging capabilities introduced in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="92989-105">중앙 집중화 된 로깅을 통해 관리자는 여러 컴퓨터에서 이벤트 추적을 동시에 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92989-105">Centralized logging allows administrators to simultaneously enable or disable event tracing on multiple computers.</span></span>

<div>

## <a name="centralized-logging-cmdlets"></a><span data-ttu-id="92989-106">중앙 로깅 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="92989-106">Centralized Logging Cmdlets</span></span>

<span data-ttu-id="92989-107">중앙 로깅 cmdlet을 사용 하 여 Lync Server 2013에 도입 된 중앙 집중화 된 로깅 서비스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92989-107">The centralized logging cmdlets enable you to manage the centralized logging service introduced in Lync Server 2013:</span></span>

<span data-ttu-id="92989-108">**중앙 로깅 Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="92989-108">**Centralized Logging Cmdlets**</span></span>

  - <span data-ttu-id="92989-109">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-109">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-110">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-110">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-111">[-CsClsConfiguration 제거](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-111">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-112">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-112">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="92989-113">[Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-113">[Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-114">[표시-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-114">[Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-115">[시작-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-115">[Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-116">[중지-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-116">[Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-117">[Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-117">[Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-118">[업데이트-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-118">[Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="92989-119">[새-CsClsProvider](https://technet.microsoft.com/en-us/library/JJ619187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-119">[New-CsClsProvider](https://technet.microsoft.com/en-us/library/JJ619187(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="92989-120">[Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-120">[Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-121">[새-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-121">[New-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-122">[-CsClsRegion 제거](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-122">[Remove-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-123">[Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-123">[Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="92989-124">[Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-124">[Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-125">[신규-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-125">[New-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-126">[-CsClsScenario 제거](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-126">[Remove-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-127">[Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-127">[Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="92989-128">[Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-128">[Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-129">[Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-129">[Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="92989-130">[Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-130">[Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-131">[새-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-131">[New-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-132">[-CsClsSecurityGroup 제거](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-132">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="92989-133">[Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="92989-133">[Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

