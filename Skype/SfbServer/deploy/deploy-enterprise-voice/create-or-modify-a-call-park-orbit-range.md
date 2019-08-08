---
title: 비즈니스용 Skype에서 통화 공원 궤도 범위 만들기 또는 수정
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 비즈니스용 Skype Server Enterprise Voice에서 통화 공원 궤도 범위 테이블을 만들거나 수정 합니다.
ms.openlocfilehash: 305404ce74d3aec26741c0e26b999f6227dabe37
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233683"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="cc4db-103">비즈니스용 Skype에서 통화 공원 궤도 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="cc4db-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="cc4db-104">비즈니스용 Skype Server Enterprise Voice에서 통화 공원 궤도 범위 테이블을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="cc4db-105">통화 공원는 orbits 통화를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="cc4db-106">사용자가 전화를 걸고 검색할 수 있으려면 통화 공원 표를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="cc4db-107">조직에서 파킹 통화를 위해 예약 하는 내선 번호 범위 (orbits)를 지정 하 고 각 범위에 대 한 통화 공원 풀 핸들을 지정 하 여 해당 범위에 대 한 라우팅을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="cc4db-108">궤도 범위를 정의 하는 경우 orbits 충분 한 회전을 사용 하는 것이 목표는 하지만, 사용자 또는 다른 서비스에 대해 제공 되는 확장 수를 제한 하는 것이 여러 orbits 되지 않도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="cc4db-109">통화 공원 응용 프로그램이 배포 된 각 비즈니스용 Skype 서버 풀에 대해 여러 통화 공원 궤도 범위를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="cc4db-110">각 통화 공원 궤도 범위에는 전역 고유 이름과 고유한 확장명 집합이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc4db-111">궤도 범위는 일반적으로 100 이하의 orbits를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-111">An orbit range typically encompasses 100 or fewer orbits.</span></span> <span data-ttu-id="cc4db-112">각 범위는 범위 당 최대 1만 orbits 보다 작고 orbits 5만 보다 적은 수의 용량을 보유 한 경우에 한 하 여 훨씬 더 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-112">Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool.</span></span> <span data-ttu-id="cc4db-113">범위가 너무 작으면 orbits 보다 빠르게 다시 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-113">If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="cc4db-114">궤도 범위에 대 한 가상 확장 블록 (사용자 또는 전화 번호를 지정 하지 않은 확장명)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="cc4db-115">직접 연결 된 전화 접속 (연결) 번호를 통화 공원 궤도 테이블의 궤도 번호로 지정 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="cc4db-116">다음 절차 중 하나를 사용 하 여 통화 공원 궤도 범위를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="cc4db-117">비즈니스용 Skype Server 제어판을 사용 하 여 파킹 통화에 대 한 번호 범위를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="cc4db-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="cc4db-118">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cc4db-119">자세한 내용은 **대리인 설정 사용**을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc4db-119">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="cc4db-120">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="cc4db-121">왼쪽 탐색 모음에서 **음성 기능** 을 클릭 한 다음 **통화 공원**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="cc4db-122">**통화 공원** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="cc4db-123">새 궤도 범위를 만들려면 **새로**만들기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-123">To create a new orbit range, click **New**.</span></span> <span data-ttu-id="cc4db-124">**이름**에이 숫자 범위에 대 한 식별 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-124">In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="cc4db-125">데이터베이스에 궤도 범위를 커밋한 후에는이 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="cc4db-126">기존 궤도 범위를 수정 하려면 검색 필드에 궤도 범위의 이름 전체 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-126">To modify an existing orbit range, type all or part of the name of the orbit range in the search field.</span></span> <span data-ttu-id="cc4db-127">Orbits의 결과 목록에서 원하는 궤도를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-127">In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="cc4db-128">첫 번째 **숫자 범위** 필드에이 통화 공원 궤도에 대 한 확장 범위의 시작 번호를 입력 하 고 두 번째 **숫자 범위** 필드에 범위의 끝 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="cc4db-129">주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-129">Be aware:</span></span>

   - <span data-ttu-id="cc4db-130">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="cc4db-131">범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="cc4db-132">궤도 범위는 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-132">The orbit range must be unique.</span></span> <span data-ttu-id="cc4db-133">범위가 다른 범위와 겹쳐서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-133">This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="cc4db-134">궤도 범위가 문자 \* 또는 번호로 시작 하는 경우 범위는 100 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="cc4db-135">유효한 값: 정규식 문자열과 일치 해야 합니다 ([\\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="cc4db-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="cc4db-136">즉, value는 문자 \* 또는 숫자 1부터 9까지 (첫 문자는 0이 될 수 없음)로 시작 하는 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="cc4db-137">첫 번째 문자가 \* or # 이면 다음 문자는 1부터 9 까지의 숫자 (0이 될 수 없음) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="cc4db-138">이후 문자는 0 ~ 9 개 까지의 추가 문자 (예: "#6000", "\*92000", "\*95551212", "915551212") 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="cc4db-139">첫 문자 \* 를 입력 하는 경우 첫 번째 문자는 1 ~ 9 (0이 될 수 없음) 다음에 최대 8 자, 즉 각각 0 ~ 9 (예: "915551212", "41212", "300") 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="cc4db-140">풀 당 총 5만 orbits를 넘지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-140">You should not have more than a total of 50,000 orbits per pool.</span></span> <span data-ttu-id="cc4db-141">일반적으로 각 궤도 범위는 100 개 이하의 orbits에 포함 되지만, 1만 orbits 보다 적은 만큼 더 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-141">Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits.</span></span> <span data-ttu-id="cc4db-142">예를 들어 시작 번호를 "7000000"으로, 끝 번호를 "8000000"으로 지정하는 대신 시작 번호를 "7000000"으로, 끝 번호를 "7000100"으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-142">For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="cc4db-143">**대상 서버의 fqdn**(정규화 된 도메인 이름) 또는 통화 공원 응용 프로그램을 호스팅하는 응용 프로그램 서비스의 서비스 ID (fqdn)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="cc4db-144">궤도 범위의 시작 번호와 끝 번호로 지정 된 범위 내에 있는 모든 통화는이 서버 또는 풀로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="cc4db-145">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="cc4db-146">비즈니스용 Skype Server Management Shell을 사용 하 여 파킹 통화에 대 한 숫자 범위를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="cc4db-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="cc4db-147">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="cc4db-148">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="cc4db-149">**New-CsCallParkOrbit** 를 사용 하 여 궤도 번호의 새 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="cc4db-150">**Set-CsCallParkOrbit** 를 사용 하 여 기존 궤도 번호 범위를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="cc4db-151">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-151">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="cc4db-152">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-152">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="cc4db-153">다음 예제에서는 기존 궤도 범위에서 숫자를 수정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc4db-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="cc4db-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc4db-154">See also</span></span>

[<span data-ttu-id="cc4db-155">새로운 CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="cc4db-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="cc4db-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="cc4db-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="cc4db-157">통화 공원 궤도 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="cc4db-157">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
