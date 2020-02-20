---
title: 'Lync Server 2013: 응답 그룹 큐 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Response Group queue
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521008(v=OCS.15)
ms:contentKeyID: 48184356
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f818ac0bbb56434863ec68f0ba9283d9006ec10
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-response-group-queue-in-lync-server-2013"></a><span data-ttu-id="b261b-102">Lync Server 2013에서 응답 그룹 큐 삭제</span><span class="sxs-lookup"><span data-stu-id="b261b-102">Delete a Response Group queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b261b-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b261b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b261b-104">다음 절차 중 하나를 사용해서 큐를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-104">Use one of the following procedures to delete a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-queue"></a><span data-ttu-id="b261b-105">Lync Server 제어판을 사용 하 여 큐를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="b261b-105">To use Lync Server Control Panel to delete a queue</span></span>

1.  <span data-ttu-id="b261b-106">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="b261b-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b261b-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b261b-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b261b-109">왼쪽 탐색 모음에서 **응답 그룹**을 클릭하고 **큐**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-109">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="b261b-110">검색 필드에 삭제할 큐의 이름을 일부분 또는 모두 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-110">In the search field, type part or all of the name of the queue you want to delete.</span></span>

5.  <span data-ttu-id="b261b-111">큐 목록에서 삭제할 큐를 클릭하고 **편집**을 클릭한 다음 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-111">In the list of queues, click the queue that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="b261b-112">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-queue"></a><span data-ttu-id="b261b-113">Windows PowerShell을 사용 하 여 큐를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="b261b-113">To use Windows PowerShell to delete a queue</span></span>

1.  <span data-ttu-id="b261b-114">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="b261b-115">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b261b-116">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-116">At the command line, run:</span></span>
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    <span data-ttu-id="b261b-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b261b-117">For example:</span></span>
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

</div>

</div>

<span> </span>

</div>

</div>

</div>

