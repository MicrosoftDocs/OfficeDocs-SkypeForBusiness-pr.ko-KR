---
title: 'Lync Server 2013: 에이전트 그룹 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adcdc0245f6fdd835492084fcae91389409f52c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="520cc-102">Lync Server 2013에서 에이전트 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="520cc-102">Delete an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="520cc-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="520cc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="520cc-104">다음 절차 중 하나를 사용 하 여 에이전트 그룹을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-104">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="520cc-105">Lync Server 제어판을 사용 하 여 에이전트 그룹을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="520cc-105">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="520cc-106">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="520cc-107">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="520cc-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="520cc-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="520cc-109">왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-109">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="520cc-110">**응답 그룹** 페이지에서 검색 필드에 삭제할 에이전트 그룹 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-110">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="520cc-111">결과 목록에서 삭제 하려는 그룹을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-111">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="520cc-112">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="520cc-113">Windows PowerShell을 사용 하 여 에이전트 그룹을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="520cc-113">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="520cc-114">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="520cc-115">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="520cc-116">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-116">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="520cc-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="520cc-117">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="520cc-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="520cc-118">See Also</span></span>


[<span data-ttu-id="520cc-119">Lync Server 2013에서 에이전트 그룹 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="520cc-119">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="520cc-120">제거-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="520cc-120">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="520cc-121">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="520cc-121">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

