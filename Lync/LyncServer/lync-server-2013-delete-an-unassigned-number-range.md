---
title: 'Lync Server 2013: 지정 되지 않은 번호 범위 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 452eea98fee3dc70fa88d637893c0136c7edf8d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="9fd89-102">Lync Server 2013에서 할당 되지 않은 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="9fd89-102">Delete an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fd89-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9fd89-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9fd89-104">알림에 대해 할당되지 않은 번호 범위를 삭제하려면 다음 절차를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="9fd89-104">Use one of the following procedures to delete an unassigned number range for Announcements.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="9fd89-105">Lync Server 제어판을 사용 하 여 지정 되지 않은 번호 범위를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="9fd89-105">To use Lync Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="9fd89-106">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9fd89-107">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9fd89-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9fd89-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9fd89-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9fd89-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9fd89-110">왼쪽 탐색 모음에서 **음성 기능**을 클릭하고 **지정되지 않은 번호**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-110">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="9fd89-111">**지정되지 않은 번호** 페이지의 검색 필드에 삭제할 할당되지 않은 번호 범위의 이름 일부나 전체를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-111">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>

5.  <span data-ttu-id="9fd89-112">결과 번호 범위 목록에서 이름을 클릭하고 **편집**을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-112">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="9fd89-113">**모두 커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-113">Click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="9fd89-114">Windows PowerShell을 사용 하 여 지정 되지 않은 번호 범위를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="9fd89-114">To use Windows PowerShell to delete an unassigned number range</span></span>

1.  <span data-ttu-id="9fd89-115">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9fd89-116">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9fd89-117">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-117">At the command line, type:</span></span>
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    <span data-ttu-id="9fd89-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-118">For example:</span></span>
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9fd89-119">기타 옵션에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">get-cscallparkorbit</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9fd89-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9fd89-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fd89-120">See Also</span></span>


[<span data-ttu-id="9fd89-121">Lync Server 2013에서 할당 되지 않은 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="9fd89-121">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[<span data-ttu-id="9fd89-122">New-csunassignednumber을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd89-122">Remove-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[<span data-ttu-id="9fd89-123">New-csunassignednumber</span><span class="sxs-lookup"><span data-stu-id="9fd89-123">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

