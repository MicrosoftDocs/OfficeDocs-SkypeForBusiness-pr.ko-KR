---
title: 'Lync Server 2013: 장치 업데이트 규칙 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0416092c7021d599ec7e516d72c19e8baa3c598
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="ef730-102">Lync Server 2013에서 장치 업데이트 규칙 복원</span><span class="sxs-lookup"><span data-stu-id="ef730-102">Restore a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef730-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ef730-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ef730-104">배포의 장치에서 장치 업데이트 규칙을 제거 하려면 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-104">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="ef730-105">장치 업데이트 규칙을 복원 하면 업데이트를 제거 하 고 해당 규칙의 이전 버전을 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-105">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="ef730-106">Lync Server 제어판 또는 Windows PowerShell을 사용 하 여 장치 업데이트 규칙을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-106">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="ef730-107">Lync Server 제어판을 사용 하 여 장치 업데이트 규칙을 복원 하려면</span><span class="sxs-lookup"><span data-stu-id="ef730-107">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ef730-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ef730-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ef730-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef730-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ef730-111">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 업데이트** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-111">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="ef730-112">**장치 업데이트** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-112">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="ef730-113">하나의 규칙을 복원 하려면 해당 규칙을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-113">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="ef730-114">모든 규칙을 복원 하려면 **편집**을 클릭 한 다음 **모두 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-114">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="ef730-115">**동작** 메뉴를 클릭 한 다음 **복원을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-115">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ef730-116">Windows PowerShell Cmdlet을 사용 하 여 장치 업데이트 규칙 복원</span><span class="sxs-lookup"><span data-stu-id="ef730-116">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ef730-117">Windows PowerShell 및 **Restore-CsDeviceUpdateRule** cmdlet을 사용 하 여 장치 업데이트 규칙을 복원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-117">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="ef730-118">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef730-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef730-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="ef730-120">서버에서 단일 장치 업데이트 규칙을 복원 하려면</span><span class="sxs-lookup"><span data-stu-id="ef730-120">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="ef730-121">다음 명령은 웹 서버 atl-cs-001.litwareinc.com에서 장치 업데이트 규칙 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-121">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="ef730-122">서버의 모든 장치 업데이트 규칙을 복원 하려면</span><span class="sxs-lookup"><span data-stu-id="ef730-122">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="ef730-123">이 명령은 웹 서버 atl-cs-001.litwareinc.com의 모든 장치 업데이트 규칙을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef730-123">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="ef730-124">자세한 내용은 [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef730-124">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

