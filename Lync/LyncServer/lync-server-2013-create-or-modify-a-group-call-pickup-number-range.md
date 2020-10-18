---
title: 'Lync Server 2013: 그룹 통화 픽업 번호 범위 만들기 또는 수정'
description: 'Lync Server 2013: 그룹 통화 픽업 번호 범위를 만들거나 수정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc2072a5d80e9c3b09e0c0d2275233214a21e764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577924"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="d9fe3-103">Lync Server 2013에서 그룹 통화 픽업 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d9fe3-103">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9fe3-104">_**마지막으로 수정 된 항목:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="d9fe3-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="d9fe3-105">다음 절차에 따라 통화 대기 궤도 테이블에서 통화 픽업 그룹 번호 범위를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-105">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9fe3-106">Lync Server 관리 셸을 사용 하 여 통화 대기 궤도 테이블에서 그룹 통화 픽업 번호 범위를 만들고, 수정 하 고, 제거 하 고, 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-106">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="d9fe3-107">Lync Server 제어판에서는 그룹 통화 픽업 번호 범위를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-107">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d9fe3-108">Call pickup 그룹 번호 범위에는 GroupPickup 유형이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-108">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="d9fe3-109">사용자가 할당 된 그룹 번호가 GroupPickup 형식인 경우에만 그룹 통화 픽업 지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-109">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="d9fe3-110">Call pickup 그룹 번호 범위는 다음 규칙을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-110">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="d9fe3-111">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="d9fe3-112">범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="d9fe3-113">번호 범위는 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-113">The number range must be unique.</span></span> <span data-ttu-id="d9fe3-114">이 범위는 다른 범위와 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-114">This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="d9fe3-115">숫자 범위가 문자로 시작 하는 경우 \* \# 에는 범위가 100 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-115">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="d9fe3-116">유효한 값:은 정규식 문자열 ( \[ \\ \* | \# \] ? \[ 1-9 \] \\ d {0,7} ) | ( \[ 1-9 \] \\ d {0,8} )</span><span class="sxs-lookup"><span data-stu-id="d9fe3-116">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="d9fe3-117">즉,이 값은 \* \# 1부터 9 까지의 숫자로 시작 하는 문자열 (첫 번째 문자는 0이 될 수 없음)입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-117">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="d9fe3-118">첫 번째 문자가 or 인 \* 경우 \# 다음 문자는 1에서 9 사이의 숫자 (0이 될 수 없음) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-118">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="d9fe3-119">이후 문자에는 0에서 9 까지의 추가 문자 (예: " \# 6000", " \* 92000", " \* 95551212" 및 "915551212")가 최대 7 자까지 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="d9fe3-120">첫 문자가 아닌 경우 첫 번째 \* \# 문자는 1부터 9 까지의 숫자 (0이 될 수 없음)와 최대 8 자 (예: "915551212", "41212", "300") 사이에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-120">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="d9fe3-121">통화 픽업 그룹 범위를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="d9fe3-121">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="d9fe3-122">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-122">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d9fe3-123">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d9fe3-124">**Get-cscallparkorbit** 을 사용 하 여 통화 픽업 그룹 번호의 새 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-124">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="d9fe3-125">**Get-cscallparkorbit** 을 사용 하 여 기존 통화 픽업 번호 범위를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-125">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="d9fe3-126">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-126">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="d9fe3-127">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-127">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="d9fe3-128">다음 예에서는 통화 대기 궤도에서 pickup 그룹으로 번호 범위를 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-128">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d9fe3-129">이 cmdlet을 사용 하 여 처음에 잘못 된 유형을 지정 했 고 그룹 범위가 아직 사용 되지 않은 경우에만 번호 범위에 할당 된 형식을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-129">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="d9fe3-130">번호 범위를 CallPark에서 GroupPickup로 변경 하거나 그 반대로, 숫자 범위를 이미 사용 중인 경우에는 통화 대기 또는 그룹 통화 픽업이 해당 번호 범위에 대해 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-130">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="d9fe3-131">예를 들어 번호 범위를 CallPark에서 GroupPick로 변경 하는 경우 통화 대기 응용 프로그램은 더 이상이 궤도 범위를 사용 하 여 통화를 대기 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fe3-131">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9fe3-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9fe3-132">See Also</span></span>


[<span data-ttu-id="d9fe3-133">Lync Server 2013에서 통화 대기 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="d9fe3-133">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="d9fe3-134">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="d9fe3-134">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="d9fe3-135">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="d9fe3-135">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

