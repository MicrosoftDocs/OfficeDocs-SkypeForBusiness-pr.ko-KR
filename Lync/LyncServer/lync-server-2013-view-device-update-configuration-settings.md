---
title: 'Lync Server 2013: 장치 업데이트 구성 설정 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Device Update configuration settings
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994059(v=OCS.15)
ms:contentKeyID: 51803970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cf34d5f8241735263547fe64dc0f3e3b124bb10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="ca8c3-102">Lync Server 2013의 장치 업데이트 구성 설정 보기</span><span class="sxs-lookup"><span data-stu-id="ca8c3-102">View Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca8c3-103">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ca8c3-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ca8c3-104">Lync Server 관리 셸을 사용 하 여 장치 업데이트 서비스 구성 설정을 확인 하 고 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있는 **new-csdeviceupdateconfiguration** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8c3-104">You can view the Device Update Service configuration settings by using Lync Server Management Shell and the **Get-CsDeviceUpdateConfiguration** cmdlet, which you can run from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca8c3-105">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca8c3-105">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>


  - <span data-ttu-id="ca8c3-106">모든 음성 경로에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ca8c3-106">To view information about all your voice routes, type the following command in the Lync Server Management Shell and press Enter:</span></span>
    
        Get-CsDeviceUpdateConfiguration
    
    <span data-ttu-id="ca8c3-107">이 명령은 다음과 비슷한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8c3-107">This command returns information similar to the following:</span></span>
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

<span data-ttu-id="ca8c3-108">이 cmdlet에 대 한 자세한 내용은 [new-csdeviceupdateconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration)의 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca8c3-108">For details about this cmdlet, see Help topic at [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

