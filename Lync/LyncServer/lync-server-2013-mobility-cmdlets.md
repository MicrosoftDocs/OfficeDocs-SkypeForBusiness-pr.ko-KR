---
title: 'Lync Server 2013: 모바일 기능 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility cmdlets
ms:assetid: 42a30a34-d66b-4c91-b596-a6fc7666e600
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690019(v=OCS.15)
ms:contentKeyID: 48183973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2959cb53cd044a9a33d945f070fb1d2fdb55d821
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-cmdlets-in-lync-server-2013"></a><span data-ttu-id="419fc-102">Lync Server 2013의 모바일 기능 cmdlet</span><span class="sxs-lookup"><span data-stu-id="419fc-102">Mobility cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="419fc-103">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="419fc-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="419fc-104">Mobility cmdlet은 Lync Server 2010 용 누적 업데이트에서 추가 된 모바일 기능을 관리 하기 위해 도입 되었습니다 2011.</span><span class="sxs-lookup"><span data-stu-id="419fc-104">Mobility cmdlets were introduced to manage the mobility feature added in cumulative update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="419fc-105">이러한 cmdlet을 사용하여 Mobility Service 구성 및 사용자 정책과 같은 모바일 기능의 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419fc-105">Use these cmdlets to manage settings for mobility features, such as Mobility Service configuration and user policies.</span></span>

<div>

## <a name="mobility-cmdlets"></a><span data-ttu-id="419fc-106">모바일 기능 cmdlet</span><span class="sxs-lookup"><span data-stu-id="419fc-106">Mobility Cmdlets</span></span>

<span data-ttu-id="419fc-107">모바일 기능을 구성 하는 cmdlet을 사용 하면 Lync Server 관리 셸에서 명령을 실행 하거나 여러 이동성 설정을 구성 및 테스트 하기 위해 스크립트를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419fc-107">The cmdlets that configure mobility features allow you to run commands from the Lync Server Management Shell or to write scripts to configure and test various mobility settings.</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-108">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-108">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-109">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-109">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-110">[Get-csautodiscoverconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Hh690054(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-110">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-111">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-111">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-112">[은 new-csweblink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-112">[New-CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="419fc-113">[Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-113">[Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-114">[새-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-114">[New-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-115">[-CsMcxConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Hh690026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-115">[Remove-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-116">[-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-116">[Set-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="419fc-117">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-117">[Get-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-118">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-118">[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-119">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-119">[New-CsMobilityPolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-120">[Get-csmobilitypolicy을 제거 합니다.](https://technet.microsoft.com/library/Hh690048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-120">[Remove-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-121">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-121">[Set-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="419fc-122">[Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-122">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-123">[Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-123">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-124">[Get-cspushnotificationconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Hh690028(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-124">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690028(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-125">[Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-125">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="419fc-126">[Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-126">[Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-127">[Test-csmcxp2pim](https://technet.microsoft.com/library/Hh690020(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-127">[Test-CsMcxP2PIM](https://technet.microsoft.com/library/Hh690020(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="419fc-128">[Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="419fc-128">[Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="419fc-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="419fc-129">See Also</span></span>


[<span data-ttu-id="419fc-130">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="419fc-130">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

