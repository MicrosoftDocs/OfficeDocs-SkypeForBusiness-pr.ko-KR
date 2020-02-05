---
title: 비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: '요약: 비즈니스용 Skype 서버 제어판을 사용 하 여 다이얼 플랜을 만들거나 수정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 44917b45180abe02926aa0905b5fd20cbed0ccec
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767351"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a><span data-ttu-id="1d09e-103">비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="1d09e-103">Create or modify a dial plan in Skype for Business Server</span></span>

<span data-ttu-id="1d09e-104">**요약:** 비즈니스용 Skype 서버 제어판을 사용 하 여 다이얼 플랜을 만들거나 수정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-104">**Summary:** Learn how to create or modify a dial plan by using the Skype for Business Server Control Panel.</span></span>

### <a name="to-create-a-dial-plan"></a><span data-ttu-id="1d09e-105">다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="1d09e-105">To create a dial plan</span></span>

1. <span data-ttu-id="1d09e-106">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-106">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="1d09e-107">왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **다이얼 플랜**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-107">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

3. <span data-ttu-id="1d09e-108">**다이얼 플랜** 페이지에서 **새로 만들기** 를 클릭 하 고 다이얼 플랜의 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-108">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>

   - <span data-ttu-id="1d09e-109">**사이트 다이얼 플랜** 은 사용자 다이얼 플랜에 할당 된 사용자 또는 그룹을 제외한 전체 사이트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-109">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="1d09e-110">다이얼 플랜의 범위에 대해 **사이트** 를 선택 하는 경우 **사이트 선택** 대화 상자에서 사이트를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-110">If you select **Site** for a dial plan's scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="1d09e-111">사이트에 대 한 다이얼 플랜을 이미 만든 경우 사이트 **선택** 대화 상자에 해당 사이트가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-111">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="1d09e-112">**풀 다이얼 플랜** 은 PSTN (공개 교환 전화 네트워크) 게이트웨이 또는 등록자에 게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-112">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="1d09e-113">다이얼 플랜의 범위에 대해 **Pool (풀** )을 선택 하는 경우 **서비스 선택** 대화 상자에서 PSTN 게이트웨이 또는 등록자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-113">If you select **Pool** for a dial plan's scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="1d09e-114">서비스에 대해 다이얼 플랜을 이미 만든 경우 (PSTN 게이트웨이 또는 등록자) 해당 서비스는 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-114">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>

   - <span data-ttu-id="1d09e-115">지정 된 사용자 또는 그룹에 **사용자 다이얼 플랜** 을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-115">**User dial plan** can be applied to specified users or groups.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1d09e-116">다이얼 플랜 범위를 선택한 후에는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-116">After you select the dial plan scope, it cannot be changed.</span></span>

4. <span data-ttu-id="1d09e-117">사용자 다이얼 플랜을 만드는 경우 **새 다이얼 플랜** 대화 상자의 **이름** 필드에 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-117">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box.</span></span> <span data-ttu-id="1d09e-118">이 이름이 저장 된 후에는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-118">After this name is saved, it cannot be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d09e-119">사이트 다이얼 플랜의 경우 **이름** 필드는 사이트 이름으로 미리 채워져 있으며 변경할 수 없습니다. 풀 다이얼 플랜의 > **이름** 필드는 PSTN 게이트웨이 또는 등록자 이름으로 미리 채워 있으므로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-119">For site dial plans, the **Name** field is prepopulated with the site name and cannot be changed.> For pool dial plans, the **Name** field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

5. <span data-ttu-id="1d09e-120">**간단한 이름** 필드는 **이름** 필드에 표시 되는 것과 동일한 이름으로 미리 채워져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-120">The **Simple name** field is prepopulated with the same name that appears in the **Name** field.</span></span> <span data-ttu-id="1d09e-121">필요에 따라이 필드를 편집 하 여 다이얼 플랜이 적용 되는 사이트, 서비스 또는 사용자를 반영 하는 보다 설명적인 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-121">You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1d09e-122">**단순한 이름은** 배포의 모든 다이얼 플랜에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-122">The **Simple name** must be unique among all dial plans in your deployment.</span></span> <span data-ttu-id="1d09e-123">256 유니코드 문자를 초과할 수 없으며 각각 영문자 또는 숫자, 하이픈 (-), 마침표 (.) 또는 밑줄 (_)이 될 수 있습니다. **지원 되지 않는** > 문자는 RFC 3966 (<http://www.ietf.org/rfc/rfc3966.txt>)에 정의 된 대로 공백 및 예약 문자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-123">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).> Characters **not supported** include spaces and Reserved characters as defined in RFC 3966 (<http://www.ietf.org/rfc/rfc3966.txt>).</span></span> <span data-ttu-id="1d09e-124">**간단한 이름** 에 **지원 되지** 않는 예약 문자에는 다음이 포함 됩니다. > ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="1d09e-124">Reserved characters that are **not supported** in the **Simple Name** include the following:> ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

6. <span data-ttu-id="1d09e-125">) **설명** 필드에 다이얼 플랜에 대 한 추가 설명 정보를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-125">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="1d09e-126">) 이 다이얼 플랜을 전화 접속 액세스 번호의 지역으로 사용 하려는 경우 **전화 접속 회의 영역**을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-126">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="1d09e-127">전화 접속 액세스 번호에이 다이얼 플랜을 사용 하지 않으려면이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-127">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d09e-128">전화 접속 회의 액세스 번호는 하나 이상의 다이얼 플랜에 연결 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-128">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="1d09e-129">) 외부 회선을 사용 하기 위해 사용자가 하나 이상의 추가 선행 번호 (예: 9)를 사용 해야 하는 경우에만 **external access 접두사** 필드에 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-129">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="1d09e-130">접두사 값에 최대 4 자 (#, \*, 0-9)를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-130">You can type in a prefix value of up to four characters (#, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d09e-131">외부 액세스 접두사를 지정 하는 경우 접두사를 수용할 수 있는 새 정규화 규칙을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-131">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="1d09e-132">다음과 같이 다이얼 플랜에 대 한 정규화 규칙을 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-132">Associate and configure normalization rules for the dial plan as follows:</span></span>

    - <span data-ttu-id="1d09e-133">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 정규화 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-133">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="1d09e-134">**정규화 규칙 선택**에서 다이얼 플랜에 연결 하려는 규칙을 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-134">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="1d09e-135">새 정규화 규칙을 정의 하 고 다이얼 플랜에 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-135">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="1d09e-136">새 규칙을 정의 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정을](normalization-rules.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d09e-136">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="1d09e-137">다이얼 플랜에 이미 연결 된 정규화 규칙을 편집 하려면 규칙 이름을 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-137">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="1d09e-138">기존 정규화 규칙을 복사 하 여 새 규칙을 정의 하는 출발점으로 사용할 수 있도록 규칙 이름을 강조 표시 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-138">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="1d09e-139">다이얼 플랜에서 정규화 규칙을 제거 하려면 규칙 이름을 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-139">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1d09e-140">각 다이얼 플랜에는 하나 이상의 관련 정규화 규칙이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-140">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="1d09e-141">다이얼 플랜에 필요한 모든 정규화 규칙을 확인 하는 방법에 대 한 자세한 내용은 계획 설명서의 [비즈니스용 Skype 서버에서 아웃 바운드 음성 라우팅 계획](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d09e-141">For information about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="1d09e-142">다이얼 플랜의 정규화 규칙이 올바른 순서로 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-142">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="1d09e-143">목록에서 규칙의 위치를 변경 하려면 규칙 이름을 강조 표시 한 다음 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-143">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1d09e-144">비즈니스용 Skype Server는 위에서 아래로 표준화 규칙 목록을 트래버스 하 고, 전화 번호와 일치 하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-144">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="1d09e-145">전화 거는 번호가 둘 이상의 정규화 규칙을 충족 하도록 다이얼 플랜을 구성한 경우 더 제한적인 규칙이 덜 제한적인 규칙 보다 먼저 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-145">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="1d09e-146">기본 모든 정규화 규칙 **유지** ^ (\d{11}) $는 11 자리 숫자와 일치 합니다. ></span><span class="sxs-lookup"><span data-stu-id="1d09e-146">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="1d09e-147">예를 들어 1425으로 시작 하는 11 자리 숫자와 일치 하는 정규화 규칙을 추가 하는 경우, 더 제한적인 ^ (1425 \ d{7}) $ 규칙 아래에 **모두 유지** 를 정렬 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-147">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="1d09e-148">) 번호를 입력 하 여 다이얼 플랜을 테스트 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-148">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="1d09e-149">테스트 결과가 **테스트에 대 한 숫자 입력**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-149">The test results are displayed under **Enter a number to test**.</span></span>

12. <span data-ttu-id="1d09e-150">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-150">Click **OK**.</span></span>

13. <span data-ttu-id="1d09e-151">**다이얼 플랜** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-151">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d09e-152">다이얼 플랜을 만들 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-152">Any time you create a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="1d09e-153">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d09e-153">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-modify-a-dial-plan"></a><span data-ttu-id="1d09e-154">다이얼 플랜을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="1d09e-154">To modify a dial plan</span></span>

1. <span data-ttu-id="1d09e-155">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-155">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1d09e-156">자세한 내용은 **대리인 설정 사용**을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d09e-156">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="1d09e-157">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-157">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1d09e-158">왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **다이얼 플랜**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-158">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4. <span data-ttu-id="1d09e-159">**다이얼 플랜** 페이지에서 다이얼 플랜 이름을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-159">On the **Dial Plan** page, double-click a dial plan name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d09e-160">다이얼 플랜을 만들 때 다이얼 플랜 범위와 이름을 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-160">The dial plan scope and name were set when the dial plan was created.</span></span> <span data-ttu-id="1d09e-161">변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-161">They cannot be changed.</span></span>

5. <span data-ttu-id="1d09e-162">) **다이얼 플랜 편집**에서 **이름** 필드에 표시 되는 동일한 이름을 사용 하 여 미리 채워져 있는 **간단한 이름** 필드를 편집 하 여 다이얼 플랜이 적용 되는 사이트, 서비스 또는 사용자를 반영 하는 더 설명적인 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-162">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1d09e-163">**단순한 이름은** Lync Server 2013 배포 내의 모든 다이얼 플랜에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-163">The **Simple name** must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="1d09e-164">256 유니코드 문자는 영문자 또는 숫자, 하이픈 (-), 마침표 (.), 더하기 기호 (+) 또는 밑줄 (_)이 될 수 있습니다. > 공백은 **간단한 이름** 필드에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-164">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).> Spaces are not allowed in the **Simple name** field.</span></span>

6. <span data-ttu-id="1d09e-165">) **설명** 필드에 다이얼 플랜에 대 한 설명 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-165">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="1d09e-166">) 이 다이얼 플랜을 전화 접속 액세스 번호의 지역으로 사용 하려는 경우 **전화 접속 회의 영역**을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-166">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="1d09e-167">전화 접속 액세스 번호에이 다이얼 플랜을 사용 하지 않으려면이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-167">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d09e-168">전화 접속 회의 액세스 번호는 하나 이상의 다이얼 플랜에 연결 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-168">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="1d09e-169">) 외부 회선 (예: 9)을 가져오기 위해 사용자가 하나 이상의 추가 행간 번호를 사용 해야 하는 경우에만 **external access 접두사** 필드에 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-169">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="1d09e-170">접두사 값에 최대 4 자 (즉, #, \*, 0-9)를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-170">You can type in a prefix value of up to four characters (that is, #, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d09e-171">외부 액세스 접두사를 지정 하는 경우 접두사를 수용할 수 있는 새 정규화 규칙을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-171">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="1d09e-172">다이얼 플랜에 대 한 정규화 규칙을 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-172">Associate and configure normalization rules for the dial plan:</span></span>

   - <span data-ttu-id="1d09e-173">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 정규화 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-173">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="1d09e-174">**정규화 규칙 선택** 대화 상자에서 다이얼 플랜에 연결 하려는 규칙을 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-174">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="1d09e-175">새 정규화 규칙을 정의 하 고 다이얼 플랜에 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-175">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="1d09e-176">새 규칙을 정의 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정을](normalization-rules.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d09e-176">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="1d09e-177">다이얼 플랜에 이미 연결 된 정규화 규칙을 편집 하려면 규칙 이름을 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-177">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="1d09e-178">기존 정규화 규칙을 복사 하 여 새 규칙을 정의 하는 출발점으로 사용할 수 있도록 규칙 이름을 강조 표시 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-178">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="1d09e-179">다이얼 플랜에서 정규화 규칙을 제거 하려면 규칙 이름을 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-179">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1d09e-180">각 다이얼 플랜에는 하나 이상의 관련 정규화 규칙이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-180">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="1d09e-181">다이얼 플랜에 필요한 모든 정규화 규칙을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 [비즈니스용 Skype 서버에서 아웃 바운드 음성 라우팅 계획](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d09e-181">For details about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="1d09e-182">다이얼 플랜의 정규화 규칙이 올바른 순서로 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-182">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="1d09e-183">목록에서 규칙의 위치를 변경 하려면 규칙 이름을 강조 표시 한 다음 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-183">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1d09e-184">비즈니스용 Skype Server는 위에서 아래로 표준화 규칙 목록을 트래버스 하 고, 전화 번호와 일치 하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-184">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="1d09e-185">전화 거는 번호가 둘 이상의 정규화 규칙을 충족 하도록 다이얼 플랜을 구성한 경우 더 제한적인 규칙이 덜 제한적인 규칙 보다 먼저 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-185">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="1d09e-186">기본 모든 정규화 규칙 **유지** ^ (\d{11}) $는 11 자리 숫자와 일치 합니다. ></span><span class="sxs-lookup"><span data-stu-id="1d09e-186">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="1d09e-187">예를 들어 1425으로 시작 하는 11 자리 숫자와 일치 하는 정규화 규칙을 추가 하는 경우에는 **모두 유지** 가 보다 제한적인 ^ (1425{7}) $ rule 아래에 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-187">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="1d09e-188">) 번호를 입력 하 여 다이얼 플랜을 테스트 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-188">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="1d09e-189">테스트 결과가 **테스트에 대 한 숫자 입력**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-189">The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d09e-190">아직 테스트를 통과 하지 않은 다이얼 플랜을 저장 한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-190">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="1d09e-191">자세한 내용은 [음성 라우팅 테스트](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d09e-191">For details, see [Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

12. <span data-ttu-id="1d09e-192">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-192">Click **OK**.</span></span>

13. <span data-ttu-id="1d09e-193">**다이얼 플랜** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-193">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d09e-194">다이얼 플랜을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d09e-194">Any time you create or modify a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="1d09e-195">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d09e-195">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d09e-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d09e-196">See also</span></span>

[<span data-ttu-id="1d09e-197">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="1d09e-197">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

