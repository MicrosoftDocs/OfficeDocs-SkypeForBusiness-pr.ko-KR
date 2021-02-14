---
title: 비즈니스용 Skype에서 그룹 통화 선택 번호 범위 만들기 또는 수정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 비즈니스용 Skype 서버에서 그룹 통화 선택 번호 범위를 만들거나 Enterprise Voice.
ms.openlocfilehash: f487c277b8eaa03a5b31ce0dc9696b0efe712340
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822408"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="04c6b-103">비즈니스용 Skype에서 그룹 통화 선택 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="04c6b-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="04c6b-104">비즈니스용 Skype 서버에서 그룹 통화 선택 번호 범위를 만들거나 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="04c6b-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="04c6b-105">그룹 통화 Pickup은 통화 파크 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="04c6b-106">그룹 통화 선택을 배포할 때 통화 Pickup 그룹 번호로 지정된 전화 번호 범위로 통화 파크 파선 번호 테이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="04c6b-107">이러한 그룹 번호는 사용자가 다른 사용자를 위해 울리는 전화를 걸기 위해 전화를 걸 수 있는 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="04c6b-108">통화 걸기 그룹 번호와 마찬가지로, 통화 선택 그룹 번호는 사용자에게 할당된 사용자나 전화가 없는 가상 내선 번호가 아니어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="04c6b-109">그룹 통화 선택을 배포하는 각 프런트 엔드 풀에는 하나 이상의 통화 선택 그룹 번호 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="04c6b-110">그룹 번호 범위는 배포에서 전역적으로 고유해야 하며 **GroupPickup** 유형으로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="04c6b-111">다음 절차에 따라 통화 파크 궤도 테이블에서 통화 선택 그룹 번호 범위를 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="04c6b-112">비즈니스용 Skype 서버 관리 셸을 사용하여 통화 파크 파운데이트 테이블에서 그룹 통화 선택 번호 범위를 만들고, 수정하고, 제거하고, 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="04c6b-113">그룹 통화 선택 번호 범위는 비즈니스용 Skype 서버 제어판에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="04c6b-114">통화 선택 그룹 번호 범위는 다음 규칙을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="04c6b-115">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="04c6b-116">범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="04c6b-117">번호 범위는 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-117">The number range must be unique.</span></span> <span data-ttu-id="04c6b-118">이 범위는 다른 범위와 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-118">This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="04c6b-119">번호 범위가 문자나 #으로 시작하는 경우 범위는 \* 100보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="04c6b-120">유효한 값: 정규식 문자열([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d). {0,8}</span><span class="sxs-lookup"><span data-stu-id="04c6b-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="04c6b-121">즉, 값은 문자나 #으로 시작되는 문자열 또는 1에서 9까지의 숫자가 되어야 합니다. 첫 번째 문자는 \* 0이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="04c6b-122">첫 번째 문자가 #이면 다음 문자는 1에서 9까지의 숫자가 되어야 합니다. 이 문자는 \* 0이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="04c6b-123">이후 문자는 "#6000", \* "92000", \* "95551212" 및 "915551212"과 같은 최대 7자까지의 숫자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="04c6b-124">첫 문자가 #이 아니거나 #이면 첫 번째 문자는 1에서 9까지의 숫자가 되어야 합니다(0일 수 없습니다). 그 다음에 0에서 9까지의 숫자를 입력할 수 있습니다(예: \* "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="04c6b-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="04c6b-125">통화 선택 그룹 범위를 만들거나 수정하려면</span><span class="sxs-lookup"><span data-stu-id="04c6b-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="04c6b-126">비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원 또는 위임 설치 권한에 설명된 필요한 사용자 권한으로 설치된 컴퓨터에 로그온합니다. </span><span class="sxs-lookup"><span data-stu-id="04c6b-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="04c6b-127">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="04c6b-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="04c6b-128">**New-CsCallParkOrbit를** 사용하여 새 통화 선택 그룹 번호를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="04c6b-129">**Set-CsCallParkOrbit를** 사용하여 기존 통화 선택 번호 범위를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="04c6b-130">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="04c6b-131">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="04c6b-132">다음 예에서는 통화 파크 궤도에서 Pickup 그룹으로 번호 범위를 변경하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="04c6b-133">이 cmdlet을 사용하여 처음에 잘못된 형식을 지정하고 그룹 범위가 아직 사용되지 않은 경우 번호 범위에 할당된 형식을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="04c6b-134">번호 범위를 CallPark에서 GroupPickup으로 변경하거나 그 반대로 변경하고 번호 범위가 이미 사용 중이면 통화 파킹 또는 그룹 통화 선택이 해당 번호 범위에 대해 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="04c6b-135">예를 들어 번호 범위를 CallPark에서 GroupPick으로 변경하는 경우 통화 파킹된 응용 프로그램은 더 이상 통화를 파킹하는 데 해당 파킹된 통화 번호 범위를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6b-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="04c6b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04c6b-136">See also</span></span>

[<span data-ttu-id="04c6b-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="04c6b-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="04c6b-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="04c6b-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="04c6b-139">통화 대기 파킹된 통화 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="04c6b-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
