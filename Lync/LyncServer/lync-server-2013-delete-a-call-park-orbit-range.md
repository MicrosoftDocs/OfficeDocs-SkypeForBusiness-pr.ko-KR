---
title: 'Lync Server 2013: 통화 대기 궤도 범위 삭제'
description: 'Lync Server 2013: 통화 대기 번호 범위를 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Call Park orbit range
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182546(v=OCS.15)
ms:contentKeyID: 48184713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fb0bbd34a1f151b32067b7375948f712fa6d902
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544814"
---
# <a name="delete-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="dde31-103">Lync Server 2013에서 통화 대기 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="dde31-103">Delete a Call Park orbit range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dde31-104">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="dde31-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="dde31-105">통화 대기 번호 범위를 삭제 하려면 다음 절차 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-105">Use one of the following procedures to delete a Call Park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="dde31-106">Lync Server 제어판을 사용 하 여 통화 대기 번호 범위를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="dde31-106">To use Lync Server Control Panel to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="dde31-107">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="dde31-108">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dde31-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dde31-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dde31-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dde31-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dde31-111">왼쪽 탐색 모음에서 **음성 기능**을 클릭하고 **통화 대기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-111">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="dde31-112">**통화 대기** 페이지의 검색 필드에 삭제할 번호 범위의 이름 전부 또는 일부를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-112">On the **Call Park** page, in the search field, type all or part of the name of the orbit range that you want to delete.</span></span>

5.  <span data-ttu-id="dde31-113">결과로 표시된 번호 목록에서 번호를 클릭하고 **편집**을 클릭한 후 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-113">In the resulting list of orbits, click the orbit, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="dde31-114">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-114">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="dde31-115">Windows PowerShell을 사용 하 여 통화 대기 번호 범위를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="dde31-115">To use Windows PowerShell to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="dde31-116">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-116">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dde31-117">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dde31-118">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-118">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    <span data-ttu-id="dde31-119">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-119">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dde31-120">기타 옵션에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">get-cscallparkorbit</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dde31-120">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dde31-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dde31-121">See Also</span></span>


[<span data-ttu-id="dde31-122">Lync Server 2013에서 통화 대기 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="dde31-122">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="dde31-123">Get-cscallparkorbit을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="dde31-123">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="dde31-124">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="dde31-124">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

