---
title: 비즈니스용 Skype에서 통화 파크 궤도 범위 만들기 또는 수정
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 비즈니스용 Skype 서버 2013에서 통화 파크 궤도 범위 테이블을 만들거나 Enterprise Voice.
ms.openlocfilehash: eab1c3e6e53eaa878546b5fe4a9684147a00c583
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106324"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="63ddb-103">비즈니스용 Skype에서 통화 파크 궤도 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="63ddb-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="63ddb-104">비즈니스용 Skype 서버 2013에서 통화 파크 궤도 범위 테이블을 만들거나 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="63ddb-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="63ddb-105">통화 파킹된 통화는 통화를 파킹하는 데 파킹된 통화를 사용하는 파킹된 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="63ddb-106">사용자가 통화를 파기하고 검색하려면 먼저 통화 파크 파크 파선 테이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="63ddb-107">조직에서 통화를 파킹하기 위해 예약할 내선 번호 범위(파킹된 통화 번호)를 지정하고 각 범위를 처리하는 통화 파킹 풀을 지정하여 해당 범위에 대한 라우팅을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="63ddb-108">궤도 범위를 정의할 때 목표는 하나의 궤도를 너무 빨리 다시 사용할 수 없는 충분한 궤도를 가지지만, 사용자 또는 기타 서비스에 사용할 수 있는 내선 번호 수를 제한하는 것이 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="63ddb-109">통화 파크 응용 프로그램이 배포된 각 비즈니스용 Skype 서버 풀에 대해 여러 통화 파크 파크 파서 범위를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="63ddb-110">각 통화 파크 파크 파선 범위에는 전역적으로 고유한 이름과 고유한 내선이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63ddb-111">궤도 범위에는 일반적으로 100 이하의 궤도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-111">An orbit range typically encompasses 100 or fewer orbits.</span></span> <span data-ttu-id="63ddb-112">범위당 최대 10,000개 궤도보다 작고 풀당 50,000개 미만인 경우 각 범위는 훨씬 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-112">Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool.</span></span> <span data-ttu-id="63ddb-113">범위가 너무 작을 경우 궤도는 더 빠르게 다시 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-113">If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="63ddb-114">궤도 범위에 가상 내선 번호 블록(사용자 또는 전화가 할당되지 않은 내선 번호)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="63ddb-115">DID(Direct Inward Dialing) 번호를 통화 파킹된 통화 번호 테이블의 파킹된 통화 번호 번호로 할당하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="63ddb-116">다음 절차 중 하나를 사용하여 통화 대기 번호 범위를 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="63ddb-117">비즈니스용 Skype 서버 제어판을 사용하여 통화를 파킹하기 위한 번호 범위를 만들거나 수정하려면</span><span class="sxs-lookup"><span data-stu-id="63ddb-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="63ddb-118">RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="63ddb-119">자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="63ddb-119">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="63ddb-120">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="63ddb-121">왼쪽 탐색 모음에서 **음성 기능** 을 클릭하고 **통화 대기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="63ddb-122">**통화 대기** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="63ddb-p104">새 번호 범위를 만들려면 **새로 만들기** 를 클릭합니다. **이름** 에 이 번호 범위에 대한 식별 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="63ddb-125">번호 범위를 데이터베이스에 커밋하고 나면 이 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="63ddb-p105">기존 번호 범위를 수정하려면 검색 필드에 번호 범위의 이름 전체 또는 일부를 입력합니다. 결과로 표시된 번호 목록에서 원하는 번호를 클릭하고 **편집** 을 클릭한 후 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="63ddb-128">첫 번째 **번호 범위** 필드에는 이 통화 대기 파킹된 통화 번호에 대한 내선 번호 범위의 시작 번호를 입력하고, 두 번째 **번호 범위** 필드에는 해당 범위의 끝 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="63ddb-129">유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-129">Be aware:</span></span>

   - <span data-ttu-id="63ddb-130">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="63ddb-131">범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="63ddb-p107">파킹된 통화 번호 범위는 고유해야 하며, 다른 범위와 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="63ddb-134">번호 범위가 문자 또는 #으로 시작하는 경우 범위는 \* 100보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="63ddb-135">유효한 값: 정규식 문자열([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="63ddb-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="63ddb-136">즉, 값은 문자나 #으로 시작되는 문자열 또는 1에서 9까지의 숫자(첫 번째 문자는 \* 0일 수 없습니다.)입니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="63ddb-137">첫 문자가 또는 #이면 다음 문자는 1에서 9까지의 숫자가 되어야 합니다. 0이 될 \* 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="63ddb-138">이후 문자는 "#6000", \* "92000", " \* 95551212" 및 "915551212"과 같은 최대 7개의 추가 문자까지 0에서 9까지의 숫자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="63ddb-139">첫 번째 문자가 또는 #이 아니면 첫 번째 문자는 1에서 9까지의 숫자가 되어야 합니다(0일 수 없습니다). 그 다음에 숫자 0에서 9까지의 숫자를 입력할 수 있습니다(예: \* "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="63ddb-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="63ddb-p109">풀당 파킹된 통화 번호는 5만 개까지 포함할 수 있습니다. 각 파킹된 통화 번호 범위에는 일반적으로 100개 이하의 파킹된 통화 번호가 포함되지만, 그보다 훨씬 커질 수도 있습니다(1만 개 이하의 파킹된 통화 번호 포함). 예를 들어 시작 번호를 "7000000"로, 끝 번호를 "8000000"으로 지정하는 대신 시작 번호를 "7000000"로, 끝 번호를 "7000100"으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="63ddb-p110">**대상 서버의 FQDN** 에서 통화 대기 응용 프로그램을 호스팅하는 응용 프로그램 서비스의 FQDN(정규화된 도메인 이름) 또는 서비스 ID를 클릭합니다. 파킹된 통화 번호 범위의 시작 번호 및 끝 번호에 의해 지정된 범위 내의 번호에 대기된 모든 통화는 이 서버나 풀로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-p110">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="63ddb-145">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="63ddb-146">비즈니스용 Skype 서버 관리 셸을 사용하여 통화를 파킹하기 위한 번호 범위를 만들거나 수정하려면</span><span class="sxs-lookup"><span data-stu-id="63ddb-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="63ddb-147">비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 설치 권한 위임에 설명된 필요한 사용자 권한으로 **로그온합니다.**</span><span class="sxs-lookup"><span data-stu-id="63ddb-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="63ddb-148">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="63ddb-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="63ddb-149">번호의 새 범위를 만들려면 **New-CsCallParkOrbit** 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="63ddb-150">번호의 기존 범위를 수정하려면 **Set-CsCallParkOrbit** 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="63ddb-151">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-151">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="63ddb-152">예:</span><span class="sxs-lookup"><span data-stu-id="63ddb-152">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="63ddb-153">다음 예에서는 기존 번호 범위의 번호를 수정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="63ddb-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="63ddb-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63ddb-154">See also</span></span>

[<span data-ttu-id="63ddb-155">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="63ddb-155">New-CsCallParkOrbit</span></span>](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="63ddb-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="63ddb-156">Set-CsCallParkOrbit</span></span>](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="63ddb-157">통화 대기 파킹된 통화 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="63ddb-157">Delete a Call Park Orbit Range</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)