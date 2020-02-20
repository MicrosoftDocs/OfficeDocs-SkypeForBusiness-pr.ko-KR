---
title: 'Lync Server 2013: 통화 대기 번호 범위 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddf119e62d7e7c8ecd71fc8c121a4a623440d6f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="cc262-102">Lync Server 2013에서 통화 대기 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="cc262-102">Create or modify a Call Park orbit range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc262-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cc262-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cc262-104">다음 절차 중 하나를 사용하여 통화 대기 번호 범위를 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-104">Use one of the following procedures to create or modify a call park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="cc262-105">Lync Server 제어판을 사용 하 여 파킹 통화를 위한 번호 범위를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="cc262-105">To use Lync Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="cc262-106">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cc262-107">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc262-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cc262-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cc262-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc262-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cc262-110">왼쪽 탐색 모음에서 **음성 기능**을 클릭하고 **통화 대기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="cc262-111">**통화 대기** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-111">On the **Call Park** page, do one of the following:</span></span>
    
      - <span data-ttu-id="cc262-p103">새 번호 범위를 만들려면 **새로 만들기**를 클릭합니다. **이름**에 이 번호 범위에 대한 식별 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-p103">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cc262-114">번호 범위를 데이터베이스에 커밋하고 나면 이 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-114">After you commit the orbit range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="cc262-p104">기존 번호 범위를 수정하려면 검색 필드에 번호 범위의 이름 전체 또는 일부를 입력합니다. 결과로 표시된 번호 목록에서 원하는 번호를 클릭하고 **편집**을 클릭한 후 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-p104">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cc262-117">첫 번째 **번호 범위** 필드에는 이 통화 대기 파킹된 통화 번호에 대한 내선 번호 범위의 시작 번호를 입력하고, 두 번째 **번호 범위** 필드에는 해당 범위의 끝 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-117">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="cc262-118">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-118">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cc262-119">범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-119">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cc262-p105">파킹된 통화 번호 범위는 고유해야 하며, 다른 범위와 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-p105">The orbit range must be unique. This range cannot overlap with any other range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cc262-122">파킹된 통화 번호 범위가 \* 또는 # 문자로 시작하는 경우 범위는 100보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-122">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cc262-123">유효한 값: 정규식 문자열과 일치 해야 합니다 ([\*| #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="cc262-123">Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="cc262-124">즉, 값은 \* 또는 # 문자나 1~9 사이의 숫자로 시작하는 문자열이어야 하며, 첫 문자가 0일 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-124">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="cc262-125">첫 문자가 \* 또는 #인 경우 다음 문자는 숫자 1-9여야 합니다(0일 수 없음).</span><span class="sxs-lookup"><span data-stu-id="cc262-125">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="cc262-126">이후 문자에는 0에서 9 까지의 추가 문자 (예: "#6000", "*92000", "* 95551212" 및 "915551212")가 최대 7 자까지 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-126">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "*92000", "* 95551212", and "915551212").</span></span> <span data-ttu-id="cc262-127">첫 문자가 \* 또는 #이 아닌 경우 첫 문자는 숫자 1-9여야 하고(0일 수 없음) 그 뒤에는 숫자 0-9가 최대 8자까지 올 수 있습니다(예: "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="cc262-127">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cc262-p107">풀당 파킹된 통화 번호는 5만 개까지 포함할 수 있습니다. 각 파킹된 통화 번호 범위에는 일반적으로 100개 이하의 파킹된 통화 번호가 포함되지만, 그보다 훨씬 커질 수도 있습니다(1만 개 이하의 파킹된 통화 번호 포함). 예를 들어 시작 번호를 "7000000"로, 끝 번호를 "8000000"으로 지정하는 대신 시작 번호를 "7000000"로, 끝 번호를 "7000100"으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-p107">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="cc262-p108">**대상 서버의 FQDN**에서 통화 대기 응용 프로그램을 호스팅하는 응용 프로그램 서비스의 FQDN(정규화된 도메인 이름) 또는 서비스 ID를 클릭합니다. 파킹된 통화 번호 범위의 시작 번호 및 끝 번호에 의해 지정된 범위 내의 번호에 대기된 모든 통화는 이 서버나 풀로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-p108">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7.  <span data-ttu-id="cc262-133">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-133">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="cc262-134">Windows PowerShell을 사용 하 여 파킹 통화를 위한 번호 범위를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="cc262-134">To use Windows PowerShell to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="cc262-135">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-135">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cc262-136">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cc262-137">번호의 새 범위를 만들려면 **New-CsCallParkOrbit**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-137">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="cc262-138">번호의 기존 범위를 수정하려면 **Set-CsCallParkOrbit**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-138">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="cc262-139">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-139">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    <span data-ttu-id="cc262-140">예:</span><span class="sxs-lookup"><span data-stu-id="cc262-140">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    <span data-ttu-id="cc262-141">다음 예에서는 기존 번호 범위의 번호를 수정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc262-141">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc262-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc262-142">See Also</span></span>


[<span data-ttu-id="cc262-143">Lync Server 2013에서 통화 대기 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="cc262-143">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="cc262-144">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="cc262-144">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="cc262-145">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="cc262-145">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

