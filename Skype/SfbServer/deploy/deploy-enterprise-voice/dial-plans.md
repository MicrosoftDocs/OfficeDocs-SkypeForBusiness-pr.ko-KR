---
title: 비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정
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
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: '요약: 비즈니스용 Skype 서버 제어판을 사용하여 다이얼 플랜을 만들거나 수정하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 858ddf652d4c9308c5ec4088fb0d01d284318703
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831028"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a><span data-ttu-id="5a671-103">비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="5a671-103">Create or modify a dial plan in Skype for Business Server</span></span>

<span data-ttu-id="5a671-104">**요약:** 비즈니스용 Skype 서버 제어판을 사용하여 다이얼 플랜을 만들거나 수정하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-104">**Summary:** Learn how to create or modify a dial plan by using the Skype for Business Server Control Panel.</span></span>

### <a name="to-create-a-dial-plan"></a><span data-ttu-id="5a671-105">다이얼 플랜을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-105">To create a dial plan</span></span>

1. <span data-ttu-id="5a671-106">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-106">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="5a671-107">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **다이얼 플랜** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-107">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

3. <span data-ttu-id="5a671-108">다이얼 **플랜 페이지에서** 새로 고기를 **클릭하고** 다이얼 플랜의 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-108">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>

   - <span data-ttu-id="5a671-109">**사이트 다이얼 플랜은** 사용자 다이얼 플랜에 할당된 사용자 또는 그룹을 제외한 전체 사이트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-109">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="5a671-110">다이얼 플랜 범위에 대해 **사이트를** 선택하는 경우 사이트 선택 대화 상자에서 사이트를 **선택해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-110">If you select **Site** for a dial plan's scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="5a671-111">사이트에 대한 다이얼 플랜이 이미 만들어진 경우 사이트 선택 대화 상자에 사이트가 **나타나지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-111">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="5a671-112">**풀 다이얼 플랜은** PSTN(Public Switched Telephone Network) 게이트웨이 또는 등록자에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-112">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="5a671-113">다이얼 **플랜** 범위에 풀을 선택하는 경우 서비스 선택 대화 상자에서 PSTN 게이트웨이 또는 등록자를  선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-113">If you select **Pool** for a dial plan's scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="5a671-114">서비스에 대한 다이얼 플랜(PSTN 게이트웨이 또는 등록자)이 이미 만들어진 경우 서비스가 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-114">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>

   - <span data-ttu-id="5a671-115">**사용자 다이얼 플랜을** 지정된 사용자 또는 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-115">**User dial plan** can be applied to specified users or groups.</span></span>

     > [!NOTE]
     > <span data-ttu-id="5a671-116">다이얼 플랜 범위를 선택한 후 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-116">After you select the dial plan scope, it cannot be changed.</span></span>

4. <span data-ttu-id="5a671-117">사용자 다이얼 플랜을 만드는 경우 새 다이얼 플랜  대화 상자의 이름 필드에 설명이 있는 이름을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="5a671-117">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box.</span></span> <span data-ttu-id="5a671-118">이 이름을 저장한 후 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-118">After this name is saved, it cannot be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a671-119">사이트 다이얼 플랜의 경우 **이름** 필드에 사이트 이름이 미리 입력되어 있으며 변경할 수 없습니다.> 풀  다이얼 플랜의 경우 이름 필드에 PSTN 게이트웨이 또는 등록자 이름이 미리 입력되어 있으며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-119">For site dial plans, the **Name** field is prepopulated with the site name and cannot be changed.> For pool dial plans, the **Name** field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

5. <span data-ttu-id="5a671-120">Simple **name** 필드는 Name 필드에 나타나는 이름과 같은 이름으로 **미리 채우게** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-120">The **Simple name** field is prepopulated with the same name that appears in the **Name** field.</span></span> <span data-ttu-id="5a671-121">원하는 경우 이 필드를 편집하여 다이얼 플랜이 적용되는 사이트, 서비스 또는 사용자를 반영하는 보다 자세한 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-121">You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="5a671-122">단순 **이름은** 배포의 모든 다이얼 플랜에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-122">The **Simple name** must be unique among all dial plans in your deployment.</span></span> <span data-ttu-id="5a671-123">이 코드는 256개 유니코드 문자를 초과할 수 없습니다. 각 문자는 사전순 또는 숫자 문자, 하이픈(-), 마침침(.) 또는 밑선(_).> **Characters는** RFC 3966()에 정의된 공백 및 예약 문자를 포함할 수 있습니다. <http://www.ietf.org/rfc/rfc3966.txt></span><span class="sxs-lookup"><span data-stu-id="5a671-123">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).> Characters **not supported** include spaces and Reserved characters as defined in RFC 3966 (<http://www.ietf.org/rfc/rfc3966.txt>).</span></span> <span data-ttu-id="5a671-124">단순 이름에서  지원되지 않는  예약된 문자에는 ";"> 포함됩니다. "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="5a671-124">Reserved characters that are **not supported** in the **Simple Name** include the following:> ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

6. <span data-ttu-id="5a671-125">(선택 사항) 설명 **필드에** 다이얼 플랜에 대한 추가 설명 정보를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-125">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="5a671-p106">(선택 사항) 이 다이얼 플랜을 전화 접속 액세스 번호의 지역으로 사용하려면 **전화 접속 회의 지역** 을 지정합니다. 전화 접속 액세스 번호에 이 다이얼 플랜을 사용하지 않으려면 이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a671-128">전화 접속 회의 액세스 번호를 하나 이상의 다이얼 플랜과 연결하려면 전화 접속 회의 지역이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-128">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="5a671-129">(선택 사항) 외부 액세스 **prefix** 필드에서 사용자가 외부 선을 얻기 위해 하나 이상의 추가 선행 숫자(예: 9)로 전화를 걸 필요가 있는 경우만 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-129">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="5a671-130">최대 4자(#, \*, 0-9)의 prefix 값을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-130">You can type in a prefix value of up to four characters (#, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a671-131">외부 액세스 접두사를 지정하면 접두사를 수용하기 위해 새 정규화 규칙을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-131">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="5a671-132">다이얼 플랜에 대한 정규화 규칙을 다음과 같이 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-132">Associate and configure normalization rules for the dial plan as follows:</span></span>

    - <span data-ttu-id="5a671-133">사용자 지정 배포에서 사용할 수 있는 모든 정규화 규칙 목록에서 하나 Enterprise Voice 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5a671-133">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5a671-134">정규화 **규칙** 선택에서 다이얼 플랜과 연결하려는 규칙을 강조 표시하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5a671-134">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="5a671-135">새 정규화 규칙을 정의하고 다이얼 플랜과 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-135">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="5a671-136">새 규칙을 정의하는 데 대한 자세한 내용은 비즈니스용 Skype에서 정규화 규칙 만들기 또는 [수정을 참조하세요.](normalization-rules.md)</span><span class="sxs-lookup"><span data-stu-id="5a671-136">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="5a671-137">다이얼 플랜과 이미 연결된 정규화 규칙을 편집하려면 규칙 이름을 강조하고 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-137">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="5a671-138">기존의 정규화 규칙을 복사한 후 이를 기반으로 새 규칙을 정의하려면 규칙 이름을 강조하고 **복사** 를 클릭한 다음 **붙여넣기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-138">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="5a671-139">정규화 규칙을 다이얼 플랜에서 제거하려면 규칙 이름을 강조하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-139">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="5a671-140">각각의 다이얼 플랜마다 적어도 하나의 정규화 규칙이 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-140">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="5a671-141">다이얼 플랜에 필요한 모든 정규화 규칙을 확인하는 방법에 대한 자세한 내용은 계획 설명서에서 비즈니스용 [Skype 서버의](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) 아웃바운드 음성 라우팅 계획을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a671-141">For information about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="5a671-142">다이얼 플랜의 정규화 규칙이 올바른 순서로 정렬된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-142">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="5a671-143">목록에서 규칙의 위치를 변경하려면 규칙 이름을 강조 표시한 다음 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-143">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5a671-144">비즈니스용 Skype 서버는 정규화 규칙 목록을 위쪽부터 트래버스하고 전화를 걸고 번호와 일치하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-144">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="5a671-145">전화를 건 번호가 둘 이상의 정규화 규칙과 일치하도록 다이얼 플랜을 구성하는 경우 더 제한적인 규칙을 덜 제한적인 규칙보다 위에 정렬되게 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a671-145">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="5a671-146">> **모든** 정규화 규칙^(\d {11} )$은 11자리 숫자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-146">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="5a671-147">예를 들어 1425로 시작하는 11자리 숫자와 일치하는 정규화 규칙을 추가하는 경우 **모두** 유지가 보다 제한적인^(1425\d )$ 규칙 아래에 {7} 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-147">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="5a671-p113">(선택 사항) 다이얼 플랜을 테스트할 번호를 입력한 다음 **이동** 을 클릭합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-p113">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

12. <span data-ttu-id="5a671-150">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-150">Click **OK**.</span></span>

13. <span data-ttu-id="5a671-151">**다이얼 플랜** 페이지에서 **커밋** 을 클릭한 다음 **모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-151">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a671-152">다이얼 플랜을 만들 때 구성 변경을 게시하려면 모두 커밋 명령을 실행해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="5a671-152">Any time you create a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="5a671-153">자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a671-153">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-modify-a-dial-plan"></a><span data-ttu-id="5a671-154">다이얼 플랜을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="5a671-154">To modify a dial plan</span></span>

1. <span data-ttu-id="5a671-155">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-155">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="5a671-156">자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a671-156">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="5a671-157">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-157">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="5a671-158">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **다이얼 플랜** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-158">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4. <span data-ttu-id="5a671-159">**다이얼 플랜** 페이지에서 다이얼 플랜 이름을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-159">On the **Dial Plan** page, double-click a dial plan name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a671-p116">다이얼 플랜 범위 및 이름은 다이얼 플랜이 만들어질 때 설정되었습니다. 이러한 설정은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-p116">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

5. <span data-ttu-id="5a671-162">(선택 사항) **다이얼 플랜 편집** 에서 **이름** 필드에 나타나는 것과 동일한 이름으로 미리 채워진 **단순한 이름** 필드를 편집하여 다이얼 플랜을 적용할 사이트, 서비스 또는 사용자를 나타내는 자세한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-162">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5a671-163">단순 **이름은** Lync Server 2013 배포 내의 모든 다이얼 플랜에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-163">The **Simple name** must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="5a671-164">이 코드는 256개 유니코드 문자를 초과할 수 없습니다. 각 문자는 사전순 또는 숫자 문자, 하이픈(-), 마침차(.), 더하기 기호(+) 또는 밑선(_).> 공백이 될 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="5a671-164">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).> Spaces are not allowed in the **Simple name** field.</span></span>

6. <span data-ttu-id="5a671-165">(선택 사항) **설명** 필드에 다이얼 플랜에 대한 자세한 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-165">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="5a671-p118">(선택 사항) 이 다이얼 플랜을 전화 접속 액세스 번호의 지역으로 사용하려면 **전화 접속 회의 지역** 을 지정합니다. 전화 접속 액세스 번호에 이 다이얼 플랜을 사용하지 않으려면 이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-p118">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a671-168">전화 접속 회의 액세스 번호를 하나 이상의 다이얼 플랜과 연결하려면 전화 접속 회의 지역이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-168">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="5a671-p119">(선택 사항) 사용자가 외부 회선에 연결하기 위해 하나 이상의 추가 선행 번호(예: 9)를 눌러야 하는 경우에만 **외부 액세스 접두사** 필드에 값을 지정합니다. 최대 4자의 접두사 값을 입력할 수 있습니다(즉, #, \*, 0-9).</span><span class="sxs-lookup"><span data-stu-id="5a671-p119">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9). You can type in a prefix value of up to four characters (that is, #, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a671-171">외부 액세스 접두사를 지정하면 접두사를 수용하기 위해 새 정규화 규칙을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-171">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="5a671-172">다이얼 플랜의 정규화 규칙을 연결하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-172">Associate and configure normalization rules for the dial plan:</span></span>

   - <span data-ttu-id="5a671-173">사용자 지정 배포에서 사용할 수 있는 모든 정규화 규칙 목록에서 하나 Enterprise Voice 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5a671-173">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5a671-174">**정규화 규칙 선택** 대화 상자에서 다이얼 플랜과 연결할 규칙을 강조한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-174">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="5a671-175">새 정규화 규칙을 정의하고 다이얼 플랜과 연결하려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-175">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="5a671-176">새 규칙을 정의하는 데 대한 자세한 내용은 비즈니스용 Skype에서 정규화 규칙 만들기 또는 [수정을 참조하세요.](normalization-rules.md)</span><span class="sxs-lookup"><span data-stu-id="5a671-176">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="5a671-177">다이얼 플랜과 이미 연결된 정규화 규칙을 편집하려면 규칙 이름을 강조하고 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-177">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="5a671-178">기존의 정규화 규칙을 복사한 후 이를 기반으로 새 규칙을 정의하려면 규칙 이름을 강조하고 **복사** 를 클릭한 다음 **붙여넣기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-178">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="5a671-179">정규화 규칙을 다이얼 플랜에서 제거하려면 규칙 이름을 강조하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-179">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="5a671-180">각각의 다이얼 플랜마다 적어도 하나의 정규화 규칙이 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-180">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="5a671-181">다이얼 플랜에 필요한 모든 정규화 규칙을 결정하는 방법에 대한 자세한 내용은 계획 설명서에서 비즈니스용 [Skype 서버의](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) 아웃바운드 음성 라우팅 계획을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a671-181">For details about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="5a671-182">다이얼 플랜의 정규화 규칙이 올바른 순서로 정렬된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-182">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="5a671-183">목록에서 규칙의 위치를 변경하려면 규칙 이름을 강조 표시한 다음 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-183">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5a671-184">비즈니스용 Skype 서버는 정규화 규칙 목록을 위쪽부터 트래버스하고 전화를 걸고 번호와 일치하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-184">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="5a671-185">전화를 건 번호가 둘 이상의 정규화 규칙과 일치하도록 다이얼 플랜을 구성하는 경우 더 제한적인 규칙을 덜 제한적인 규칙보다 위에 정렬되게 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a671-185">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="5a671-186">> **모든** 정규화 규칙^(\d {11} )$은 11자리 숫자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-186">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="5a671-187">예를 들어 1425로 시작하는 11자리 숫자와 일치하는 정규화 규칙을 추가하는 경우 **모두** 유지가 보다 제한적인^(1425\d )$ 규칙 아래에 {7} 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-187">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="5a671-p125">(선택 사항) 다이얼 플랜을 테스트할 번호를 입력한 다음 **이동** 을 클릭합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-p125">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a671-190">아직 테스트를 통과하지 않은 다이얼 플랜을 저장한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-190">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="5a671-191">자세한 내용은 [Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a671-191">For details, see [Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

12. <span data-ttu-id="5a671-192">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-192">Click **OK**.</span></span>

13. <span data-ttu-id="5a671-193">**다이얼 플랜** 페이지에서 **커밋** 을 클릭한 다음 **모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-193">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a671-194">다이얼 플랜을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행하며 구성 변경을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a671-194">Any time you create or modify a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="5a671-195">자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a671-195">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a671-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a671-196">See also</span></span>

[<span data-ttu-id="5a671-197">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="5a671-197">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

