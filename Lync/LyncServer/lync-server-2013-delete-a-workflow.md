---
title: 'Lync Server 2013: 워크플로 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aabb1b46d3f67408d586bada6db3d1efaf0538e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="eb573-102">Lync Server 2013에서 워크플로 삭제</span><span class="sxs-lookup"><span data-stu-id="eb573-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb573-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="eb573-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="eb573-104">다음 절차 중 하나를 사용 하 여 워크플로를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="eb573-105">Lync Server 제어판을 사용 하려면 워크플로를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="eb573-106">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="eb573-107">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eb573-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb573-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eb573-109">왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **워크플로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="eb573-110">**워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="eb573-111">서비스 검색 **선택** 필드에 삭제 하려는 워크플로를 호스팅하는 **applicationserver** 서비스 이름의 일부나 전부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="eb573-112">서비스 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb573-113">응답 그룹 구성 도구 웹 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="eb573-114"><STRONG>Https://&lt;webpoolfqdn&gt;/RgsConfig</STRONG>에 연결 하 여 웹 브라우저에서 응답 그룹 구성 도구 웹 페이지를 직접 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="eb573-115">**기존 워크플로 관리**에서 삭제 하려는 워크플로를 찾은 다음, **실행**에서 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="eb573-116">**예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="eb573-117">Windows PowerShell을 사용 하 여 워크플로를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="eb573-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="eb573-118">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="eb573-119">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="eb573-120">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="eb573-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eb573-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

