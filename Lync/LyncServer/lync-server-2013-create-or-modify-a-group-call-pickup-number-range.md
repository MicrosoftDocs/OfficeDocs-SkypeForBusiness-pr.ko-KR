---
title: 'Lync Server 2013: 그룹 통화 픽업 번호 범위 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a82f9cdc02052bf08dba3e9529871eff2b01211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="b3d64-102">Lync Server 2013에서 그룹 통화 픽업 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="b3d64-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3d64-103">_**마지막으로 수정한 주제:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="b3d64-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="b3d64-104">통화 공원 표에서 통화 픽업 그룹 번호 범위를 만들거나 수정 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-104">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3d64-105">Lync Server Management Shell을 사용 하 여 통화 공원 궤도 테이블에서 그룹 통화 픽업 번호 범위를 만들고, 수정 하 고, 제거 하 고, 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-105">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="b3d64-106">Lync Server 제어판에서는 그룹 통화 픽업 번호 범위를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-106">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3d64-107">통화 픽업 그룹 번호 범위에 GroupPickup 종류를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-107">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="b3d64-108">사용자는 자신에 게 할당 된 그룹 번호가 GroupPickup 형식인 경우에만 그룹 통화 픽업 트럭을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-108">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="b3d64-109">통화 픽업 그룹 번호 범위는 다음 규칙을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-109">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="b3d64-110">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-110">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="b3d64-111">범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-111">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="b3d64-p103">번호 범위는 고유해야 합니다. 범위가 다른 범위와 겹쳐서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="b3d64-114">숫자 범위가 문자로 \* 시작 하거나 \#범위가 100 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-114">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="b3d64-115">유효한 값: 정규식 문자열 (?\[\\\*|\#\]\[ )과 일치 해야 합니다. 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="b3d64-115">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="b3d64-116">즉, 값이 문자 \* 또는 \# 숫자 1부터 9 (첫 문자는 0이 될 수 없음)로 시작 하는 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-116">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="b3d64-117">첫 번째 문자가 \* or \#이면 다음 문자는 1부터 9 까지의 숫자 (0이 될 수 없음) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-117">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="b3d64-118">이후 문자는 0 ~ 9 개의 추가 문자 (예: "\#6000", "\*92000", "\*95551212" 및 "915551212") 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-118">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="b3d64-119">첫 문자를 입력 하지 않은 \* \#경우 첫 번째 문자는 1 ~ 9 (0이 될 수 없음) 다음에 최대 8 자, 각 숫자 0 ~ 9 (예: "915551212", "41212", "300") 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-119">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="b3d64-120">통화 픽업 그룹 범위를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="b3d64-120">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="b3d64-121">Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-121">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b3d64-122">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b3d64-123">**New-CsCallParkOrbit** 를 사용 하 여 통화 픽업 그룹 번호의 새 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-123">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="b3d64-124">**Set-CsCallParkOrbit** 를 사용 하 여 기존 통화 픽업 번호 범위를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-124">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="b3d64-125">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-125">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="b3d64-126">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-126">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="b3d64-127">다음 예제에서는 통화 공원 orbits에서 pickup 그룹으로 숫자 범위를 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-127">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b3d64-128">이 cmdlet을 사용 하 여 처음에 잘못 된 유형을 지정 하 고 그룹 범위가 아직 사용 되지 않은 경우에만 숫자 범위에 할당 된 유형을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-128">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="b3d64-129">번호 범위를 CallPark에서 GroupPickup으로 변경 하거나 그 반대의 경우 또는 그 반대로, 그리고 해당 번호 범위를 이미 사용 중인 경우에는 통화 공원 또는 그룹 통화 픽업이 해당 번호 범위에 대해 작동을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-129">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="b3d64-130">예를 들어, 번호 범위를 CallPark에서 GroupPick로 변경 하면 통화 공원 응용 프로그램이 더 이상 통화를 파킹 하기 위해 해당 orbits 범위를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d64-130">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3d64-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3d64-131">See Also</span></span>


[<span data-ttu-id="b3d64-132">Lync Server 2013에서 통화 공원 궤도 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="b3d64-132">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="b3d64-133">새로운 CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="b3d64-133">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="b3d64-134">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="b3d64-134">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

