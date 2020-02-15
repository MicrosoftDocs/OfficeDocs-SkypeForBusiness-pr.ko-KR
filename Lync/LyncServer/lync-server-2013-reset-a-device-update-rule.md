---
title: 'Lync Server 2013: 장치 업데이트 규칙 다시 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1079236ceab3fda42b1920675761f272333d264
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="8124b-102">Lync Server 2013에서 장치 업데이트 규칙 다시 설정</span><span class="sxs-lookup"><span data-stu-id="8124b-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8124b-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8124b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8124b-104">테스트 장치에서 업데이트가 작동 하는 방식이 마음에 들지 않는 경우에는 장치 업데이트 규칙을 다시 설정 하 여 해당 규칙의 보류 중 상태를 제거 하 고 테스트 장치에서 업데이트를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="8124b-105">Lync Server 제어판 또는 Windows PowerShell을 사용 하 여 장치 업데이트 규칙을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8124b-106">이미 승인 된 규칙 (롤아웃)을 제거 하려면 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="8124b-107">자세한 내용은 <A href="lync-server-2013-restore-a-device-update-rule.md">Lync Server 2013에서 장치 업데이트 규칙 복원을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8124b-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="8124b-108">Lync Server 제어판을 사용 하 여 장치 업데이트 규칙을 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="8124b-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8124b-109">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8124b-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8124b-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8124b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8124b-112">왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **장치 업데이트** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="8124b-113">**장치 업데이트** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="8124b-114">규칙 하나를 다시 설정 하려면 다시 설정 하려는 규칙을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="8124b-115">모든 규칙을 다시 설정 하려면 **편집** 메뉴에서 **모두 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="8124b-116">한 브랜드에 대해 모든 규칙을 다시 설정 하려면 **브랜드** 열 메뉴를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="8124b-117">**동작**을 클릭 한 다음 **보류 중인 업데이트 취소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="8124b-118">취소 한 장치 업데이트 규칙을 롤아웃할 필요가 없는 경우에는 삭제 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="8124b-119">자세한 내용은 <A href="lync-server-2013-remove-a-device-update-rule.md">Lync Server 2013에서 장치 업데이트 규칙 제거</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8124b-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8124b-120">Windows PowerShell Cmdlet을 사용 하 여 장치 업데이트 규칙 다시 설정</span><span class="sxs-lookup"><span data-stu-id="8124b-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8124b-121">Windows PowerShell 및 **get-csdeviceupdaterule** cmdlet을 사용 하 여 장치 업데이트 규칙을 다시 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="8124b-122">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8124b-123">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8124b-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="8124b-124">서버에서 특정 장치 업데이트 규칙을 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="8124b-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="8124b-125">다음 명령은 웹 서버 atl-cs-001.litwareinc.com에서 장치 업데이트 규칙 d5ce3c10-2588-420a-82ac-82ac-dc2d9b1222ff9를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="8124b-126">서버에서 모든 장치 업데이트 규칙을 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="8124b-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="8124b-127">이 명령은 웹 서버 atl-cs-001.litwareinc.com의 모든 장치 업데이트 규칙을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="8124b-128">특정 브랜드의 모든 장치 업데이트 규칙을 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="8124b-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="8124b-129">이 예에서는 조직이 다음과 같은 브랜드의 조직 전체에서 모든 장치 업데이트가 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8124b-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="8124b-130">자세한 내용은 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8124b-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8124b-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8124b-131">See Also</span></span>


[<span data-ttu-id="8124b-132">Lync Server 2013에서 장치 업데이트 규칙 승인</span><span class="sxs-lookup"><span data-stu-id="8124b-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

