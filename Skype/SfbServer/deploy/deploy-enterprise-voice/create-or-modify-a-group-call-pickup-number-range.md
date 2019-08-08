---
title: 비즈니스용 Skype에서 그룹 통화 픽업 번호 범위 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 비즈니스용 Skype Server Enterprise Voice에서 그룹 통화 픽업 번호 범위를 만들거나 수정 합니다.
ms.openlocfilehash: 3098d7cf1554586dd2fd2ace934682ae58a90489
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233680"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="d1bc8-103">비즈니스용 Skype에서 그룹 통화 픽업 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d1bc8-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="d1bc8-104">비즈니스용 Skype Server Enterprise Voice에서 그룹 통화 픽업 번호 범위를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="d1bc8-105">그룹 통화 픽업는 통화 공원 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="d1bc8-106">그룹 통화 픽업을 배포 하는 경우 통화 픽업 그룹 번호로 지정 된 전화 번호 범위를 사용 하 여 통화 공원 궤도 테이블을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="d1bc8-107">이러한 그룹 번호는 다른 사용자에 게 연결 되는 통화를 선택 하기 위해 사용자가 전화를 거는 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="d1bc8-108">통화 공원 번호와 같은 통화 픽업 그룹 번호는 사용자 또는 전화가 할당 되지 않은 가상 확장명 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="d1bc8-109">그룹 통화 픽업을 배포 하는 각 프런트 엔드 풀에는 하나 이상의 통화 픽업 그룹 번호 범위가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="d1bc8-110">그룹 번호 범위는 배포에서 전역적으로 고유 해야 하며 **Grouppickup** 유형으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="d1bc8-111">통화 공원 표에서 통화 픽업 그룹 번호 범위를 만들거나 수정 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="d1bc8-112">통화 공원 궤도 테이블에서 그룹 통화 픽업 번호 범위를 만들고, 수정 하 고, 제거 하 고, 표시 하려면 비즈니스용 Skype Server Management Shell을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="d1bc8-113">비즈니스용 Skype Server 제어판에서는 그룹 통화 픽업 번호 범위를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="d1bc8-114">통화 픽업 그룹 번호 범위는 다음 규칙을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="d1bc8-115">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="d1bc8-116">범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="d1bc8-p104">번호 범위는 고유해야 합니다. 범위가 다른 범위와 겹쳐서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="d1bc8-119">숫자 범위가 문자로 \* 시작 하는 경우 범위는 100 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="d1bc8-120">유효한 값: 정규식 문자열과 일치 해야 합니다 ([\\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="d1bc8-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="d1bc8-121">즉, value는 문자 \* 또는 숫자 1부터 9까지 (첫 문자는 0이 될 수 없음)로 시작 하는 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="d1bc8-122">첫 번째 문자가 \* or # 이면 다음 문자는 1부터 9 까지의 숫자 (0이 될 수 없음) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="d1bc8-123">이후 문자는 0 ~ 9 개 까지의 추가 문자 (예: "#6000", "\*92000", "\*95551212", "915551212") 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="d1bc8-124">첫 문자 \* 를 입력 하는 경우 첫 번째 문자는 1 ~ 9 (0이 될 수 없음) 다음에 최대 8 자, 즉 각각 0 ~ 9 (예: "915551212", "41212", "300") 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="d1bc8-125">통화 픽업 그룹 범위를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="d1bc8-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="d1bc8-126">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="d1bc8-127">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="d1bc8-128">**New-CsCallParkOrbit** 를 사용 하 여 통화 픽업 그룹 번호의 새 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="d1bc8-129">**Set-CsCallParkOrbit** 를 사용 하 여 기존 통화 픽업 번호 범위를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="d1bc8-130">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-130">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="d1bc8-131">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-131">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="d1bc8-132">다음 예제에서는 통화 공원 orbits에서 pickup 그룹으로 숫자 범위를 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="d1bc8-133">이 cmdlet을 사용 하 여 처음에 잘못 된 유형을 지정 하 고 그룹 범위가 아직 사용 되지 않은 경우에만 숫자 범위에 할당 된 유형을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="d1bc8-134">번호 범위를 CallPark에서 GroupPickup으로 변경 하거나 그 반대의 경우 또는 그 반대로, 그리고 해당 번호 범위를 이미 사용 중인 경우에는 통화 공원 또는 그룹 통화 픽업이 해당 번호 범위에 대해 작동을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="d1bc8-135">예를 들어, 번호 범위를 CallPark에서 GroupPick로 변경 하면 통화 공원 응용 프로그램이 더 이상 통화를 파킹 하기 위해 해당 orbits 범위를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bc8-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1bc8-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1bc8-136">See also</span></span>

[<span data-ttu-id="d1bc8-137">새로운 CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="d1bc8-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="d1bc8-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="d1bc8-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="d1bc8-139">통화 공원 궤도 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="d1bc8-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
