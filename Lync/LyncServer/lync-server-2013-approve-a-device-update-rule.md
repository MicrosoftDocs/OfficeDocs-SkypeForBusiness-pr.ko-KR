---
title: 'Lync Server 2013: 장치 업데이트 규칙 승인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bb464d0845f70012bdd8e70365c8a7993de6b4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="9706f-102">Lync Server 2013에서 장치 업데이트 규칙 승인</span><span class="sxs-lookup"><span data-stu-id="9706f-102">Approve a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9706f-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9706f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9706f-104">장치 업데이트 규칙을 가져온 후에는 테스트 장치에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-104">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="9706f-105">테스트에 성공 하 고 조직에 업데이트를 배포 하려는 경우 Lync Server 제어판 또는 Windows PowerShell을 사용 하 여 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-105">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="9706f-106">Lync Server 제어판을 사용 하 여 디바이스 업데이트 규칙을 승인 하려면</span><span class="sxs-lookup"><span data-stu-id="9706f-106">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9706f-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9706f-108">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9706f-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9706f-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9706f-110">**장치 업데이트** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-110">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9706f-111">하나의 규칙을 승인 하려면 해당 규칙을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-111">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="9706f-112">모든 규칙을 승인 하려면 **편집**을 클릭 한 다음 **모두 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-112">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="9706f-113">**작업**을 클릭 한 다음 **승인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-113">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9706f-114">Windows PowerShell Cmdlet을 사용 하 여 디바이스 업데이트 규칙 승인</span><span class="sxs-lookup"><span data-stu-id="9706f-114">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9706f-115">Windows PowerShell 및 **CsDeviceUpdateRule** cmdlet을 사용 하 여 디바이스 업데이트 규칙을 승인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-115">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="9706f-116">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9706f-117">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9706f-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="9706f-118">단일 장치 업데이트 규칙을 승인 하려면</span><span class="sxs-lookup"><span data-stu-id="9706f-118">To approve a single device update rule</span></span>

  - <span data-ttu-id="9706f-119">다음 명령은 웹 서버 atl-cs-001.litwareinc.com에서 찾을 수 있는 장치 업데이트 규칙 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9을 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-119">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="9706f-120">여러 장치 업데이트 규칙을 승인 하려면</span><span class="sxs-lookup"><span data-stu-id="9706f-120">To approve multiple device update rules</span></span>

  - <span data-ttu-id="9706f-121">이 명령은 Microsoft 브랜드 장치에 대 한 모든 장치 업데이트 규칙을 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9706f-121">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="9706f-122">자세한 내용은 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9706f-122">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9706f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9706f-123">See Also</span></span>


[<span data-ttu-id="9706f-124">Lync Server 2013에서 장치 업데이트 규칙 가져오기</span><span class="sxs-lookup"><span data-stu-id="9706f-124">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="9706f-125">Lync Server 2013에서 장치 업데이트 규칙 복원</span><span class="sxs-lookup"><span data-stu-id="9706f-125">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

