---
title: 'Lync Server 2013: 에이전트 그룹 삭제'
description: 'Lync Server 2013: 에이전트 그룹을 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dded2db0957e37a624d7e8bf3a06e102f8d35cad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553684"
---
# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="2bb07-103">Lync Server 2013에서 에이전트 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="2bb07-103">Delete an agent group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bb07-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2bb07-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2bb07-105">다음 절차 중 하나를 사용하여 에이전트 그룹을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-105">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="2bb07-106">Lync Server 제어판을 사용 하 여 에이전트 그룹을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="2bb07-106">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="2bb07-107">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="2bb07-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2bb07-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2bb07-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2bb07-110">왼쪽 탐색 모음에서 **응답 그룹**을 클릭한 다음 **그룹**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-110">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="2bb07-111">**리소스 그룹** 페이지의 검색 필드에 삭제할 에이전트 그룹의 이름 일부나 전체를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-111">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="2bb07-112">결과 목록에서 삭제할 그룹을 클릭하고 **편집**, **삭제**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-112">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="2bb07-113">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-113">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="2bb07-114">Windows PowerShell을 사용 하 여 에이전트 그룹을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="2bb07-114">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="2bb07-115">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-115">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="2bb07-116">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2bb07-117">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-117">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="2bb07-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-118">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2bb07-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bb07-119">See Also</span></span>


[<span data-ttu-id="2bb07-120">Lync Server 2013에서 에이전트 그룹 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="2bb07-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="2bb07-121">Get-csrgsagentgroup을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb07-121">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="2bb07-122">Get-csrgsagentgroup</span><span class="sxs-lookup"><span data-stu-id="2bb07-122">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

