---
title: 'Lync Server 2013: 장치 업데이트 규칙 제거'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3776fe2b80e301e02c099f3c6154afc1c382d0d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="dd671-102">Lync Server 2013에서 장치 업데이트 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="dd671-102">Remove a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd671-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="dd671-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dd671-104">장치 업데이트 규칙을 제거 하면 장치 업데이트 대기열에서 영구적으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="dd671-105">규칙 제거는 배포의 장치나 테스트 장치에서 업데이트를 제거 하는 것과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="dd671-106">배포에서 승인 된 업데이트를 제거 하려면 장치 업데이트 규칙을 *복원* 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="dd671-107">자세한 내용은 [Lync Server 2013에서 장치 업데이트 규칙 복원을](lync-server-2013-restore-a-device-update-rule.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd671-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="dd671-108">테스트 장치에서 승인 하지 않은 업데이트를 제거 하려면 *다시 설정* 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="dd671-109">자세한 내용은 [Lync Server 2013에서 장치 업데이트 규칙 다시 설정을](lync-server-2013-reset-a-device-update-rule.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd671-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="dd671-110">Lync Server 제어판 또는 Windows PowerShell을 사용 하 여 디바이스 업데이트 규칙을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="dd671-111">Lync Server 제어판을 사용 하 여 장치 업데이트 규칙을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="dd671-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dd671-112">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dd671-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dd671-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd671-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dd671-115">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 업데이트** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="dd671-116">**장치 업데이트** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="dd671-117">규칙 하나를 제거 하려면 삭제 하려는 규칙을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="dd671-118">모든 규칙을 제거 하려면 **편집** 메뉴를 클릭 한 다음 **모두 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="dd671-119">**편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dd671-120">Windows PowerShell Cmdlet을 사용 하 여 장치 업데이트 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="dd671-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dd671-121">Windows PowerShell 및 **CsDeviceUpdateRule** cmdlet을 사용 하 여 디바이스 업데이트 규칙을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="dd671-122">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dd671-123">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd671-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="dd671-124">서버에서 단일 장치 업데이트 규칙을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="dd671-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="dd671-125">다음 명령은 atl-cs-001.litwareinc.com의 웹 서버에서 장치 업데이트 규칙 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="dd671-126">서버에서 모든 장치 업데이트 규칙을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="dd671-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="dd671-127">이 명령은 atl-cs-001.litwareinc.com의 웹 서버에서 모든 장치 업데이트 규칙을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd671-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="dd671-128">자세한 내용은 [제거 CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd671-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd671-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd671-129">See Also</span></span>


[<span data-ttu-id="dd671-130">Lync Server 2013에서 장치 업데이트 규칙 승인</span><span class="sxs-lookup"><span data-stu-id="dd671-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

