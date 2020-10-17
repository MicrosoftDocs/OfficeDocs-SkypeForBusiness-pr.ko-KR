---
title: 'Lync Server 2013: 워크플로 삭제'
description: 'Lync Server 2013: 워크플로를 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a588a1dc0428660db95d4d492abbd1b157ca7a0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553704"
---
# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="21133-103">Lync Server 2013에서 워크플로 삭제</span><span class="sxs-lookup"><span data-stu-id="21133-103">Delete a workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21133-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="21133-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="21133-105">다음 절차 중 하나를 수행하여 워크플로를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-105">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="21133-106">Lync Server 제어판을 사용 하 여 워크플로를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="21133-106">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="21133-107">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="21133-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="21133-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="21133-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="21133-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="21133-110">왼쪽 탐색 모음에서 **응답 그룹**을 클릭하고 **워크플로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-110">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="21133-111">**워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-111">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="21133-112">**서비스 선택** 검색 필드에 삭제할 워크플로를 호스팅하는 **ApplicationServer** 서비스의 이름을 일부분 또는 모두 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-112">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="21133-113">서비스 목록에서 원하는 서비스를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-113">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21133-114">응답 그룹 구성 도구 웹 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="21133-114">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="21133-115"><STRONG>Https:// &lt; webpoolfqdn &gt; /RgsConfig</STRONG>에 연결 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구 웹 페이지를 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21133-115">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="21133-116">**기존 워크플로 관리**에서 삭제할 워크플로를 찾은 다음 **동작**에서 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-116">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="21133-117">**예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-117">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="21133-118">Windows PowerShell을 사용 하 여 워크플로를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="21133-118">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="21133-119">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="21133-120">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="21133-121">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="21133-121">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="21133-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21133-122">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

