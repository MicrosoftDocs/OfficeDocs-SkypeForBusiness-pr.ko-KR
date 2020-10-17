---
title: 'Lync Server 2013: 장치 업데이트 구성 설정 모음 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 520247186289f4b02a136b3109ec86fa4fa1a6a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525745"
---
# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="73ceb-102">Lync Server 2013에서 장치 업데이트 구성 설정 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="73ceb-102">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73ceb-103">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="73ceb-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="73ceb-104">장치 업데이트 구성 설정은 Windows PowerShell 및 **new-csdeviceupdateconfiguration** cmdlet을 사용 하 여 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ceb-104">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="73ceb-105">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ceb-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="73ceb-106">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="73ceb-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="73ceb-107">장치 업데이트 구성 설정의 특정 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="73ceb-107">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="73ceb-108">이 명령은 Redmond 사이트에 적용 된 장치 업데이트 구성 설정을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="73ceb-108">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="73ceb-109">사이트 범위에 적용 된 모든 장치 업데이트 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="73ceb-109">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="73ceb-110">이 명령은 사이트 범위에 적용 된 모든 장치 업데이트 구성 설정을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="73ceb-110">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="73ceb-111">LogCleanUpInterval 속성 값에 따라 장치 업데이트 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="73ceb-111">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="73ceb-112">다음 명령은 로그 정리 간격이 10 일 (10.00:00:00) 보다 큰 모든 장치 업데이트 구성 설정을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="73ceb-112">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="73ceb-113">자세한 내용은 [new-csdeviceupdateconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73ceb-113">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

