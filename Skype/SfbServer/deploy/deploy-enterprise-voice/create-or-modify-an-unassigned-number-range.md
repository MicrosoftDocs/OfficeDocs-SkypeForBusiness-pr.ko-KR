---
title: 비즈니스용 Skype 서버에서 할당 되지 않은 번호 범위 만들기 또는 수정
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 비즈니스용 Skype Server Enterprise Voice에서 알림 신청에 대해 할당 되지 않은 번호 범위를 만들거나 수정 하거나 삭제 합니다. 이는 할당 되지 않은 번호로의 호출이 처리 되는 방식에 영향을 줍니다.
ms.openlocfilehash: d357a97bffda50d6d387ba40a12f62dacac5ce31
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767751"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="e5898-104">비즈니스용 Skype 서버에서 할당 되지 않은 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="e5898-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="e5898-105">비즈니스용 Skype Server Enterprise Voice에서 알림 신청에 대해 할당 되지 않은 번호 범위를 만들거나 수정 하거나 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="e5898-106">이는 할당 되지 않은 번호로의 호출이 처리 되는 방식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="e5898-107">비즈니스용 Skype Server를 사용 하면 조직에 유효 하지만 사용자 또는 휴대폰에 할당 되지 않은 전화 번호로 들어오는 호출에 대해 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="e5898-108">이러한 호출을 처리 하려면 지정 하지 않은 번호 표를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="e5898-109">표를 사용 하 여 알림 응용 프로그램이 나 Exchange UM 서버로 전화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="e5898-110">할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-110">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="e5898-111">조직에 대해 유효한 모든 내선 번호로 또는 할당되지 않은 내선 번호만으로 또는 두 번호 유형의 결합으로 테이블을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-111">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="e5898-112">할당되지 않은 번호 테이블은 할당된 번호와 할당되지 않은 번호를 모두 포함할 수 있지만 발신자가 현재 할당되지 않은 번호로 전화를 걸 때만 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-112">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="e5898-113">할당되지 않은 번호 테이블에 유효한 내선 번호를 모두 포함하면 테이블을 재구성하지 않고도 다른 사용자가 조직을 떠날 때마다 발생하는 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-113">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="e5898-114">표에 할당 되지 않은 확장명을 포함 하는 경우 특정 숫자에 대해 발생 하는 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-114">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="e5898-115">예를 들어 고객 서비스 데스크에 대 한 내선 번호를 변경 하는 경우에는 테이블에 이전의 고객 서비스 번호가 포함 된 다음 새 번호를 제공 하는 공지 사항에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-115">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="e5898-116">지정 하지 않은 전화 번호 구성</span><span class="sxs-lookup"><span data-stu-id="e5898-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="e5898-117">다음 절차 중 하나를 사용 하 여 알림 신청에 대해 할당 되지 않은 번호 범위를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e5898-118">할당 되지 않은 번호 테이블을 구성 하기 전에 시스템에 이미 공지가 정의 되어 있거나 UM (Exchange 통합 메시징) 자동 전화 교환이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="e5898-119">다른 사용자가 지정 되지 않은 번호를 호출 하는 경우 비즈니스용 Skype 서버는 지정 되지 않은 번호 표를 위에서 아래로 검색 하 고 첫 번째 일치 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="e5898-120">따라서 표의 마지막 범위에 대해 마지막 수단으로 수행 하려는 작업을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="e5898-121">비즈니스용 Skype 서버 제어판을 사용 하 여 할당 되지 않은 전화 번호를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="e5898-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="e5898-122">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e5898-123">자세한 내용은 **대리인 설정 사용**을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5898-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="e5898-124">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e5898-125">왼쪽 탐색 모음에서 **음성 기능**을 클릭 한 다음 지정 하지 **않은 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="e5898-126">지정 하지 **않은 번호** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="e5898-127">새 번호 범위를 만들려면 **새로**만들기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-127">To create a new number range, click **New**.</span></span> <span data-ttu-id="e5898-128">**이름**에이 숫자 범위에 대 한 식별 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-128">In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="e5898-129">데이터베이스에 새 할당 되지 않은 번호 범위를 커밋한 후에는이 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="e5898-130">기존 번호 범위를 수정 하려면 검색 필드에 숫자 범위 이름 전체 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-130">To modify an existing number range, type all or part of the name of the number range in the search field.</span></span> <span data-ttu-id="e5898-131">결과 번호 범위 목록에서 원하는 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-131">In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e5898-132">첫 번째 **숫자 범위** 필드에 범위의 시작 번호를 입력 하 고 두 번째 **숫자 범위** 필드에 범위의 끝 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="e5898-133">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="e5898-134">범위의 시작 번호 또는 범위의 끝 번호에 내선 번호가 포함 된 경우, 시작 번호와 범위의 끝 번호에는 확장명이 포함 되어야 하 고, 내선 번호는 시작 번호와이 둘 다에 대해 동일 해야 합니다. 끝 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="e5898-135">번호는 정규식 (tel:)과 일치 해야 합니다 ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="e5898-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="e5898-136">즉,이 숫자는 문자열 tel로 시작 될 수 있습니다 (해당 문자열을 지정 하지 않으면 자동으로 추가 됩니다), 더하기 기호 (+), 숫자 1 ~ 9</span><span class="sxs-lookup"><span data-stu-id="e5898-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="e5898-137">전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="e5898-138">**알림 서비스**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="e5898-139">**공지 사항을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="e5898-140">**EXCHANGE UM**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="e5898-141">이전 단계에서 **공지 사항을**클릭 한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="e5898-142">에서.</span><span class="sxs-lookup"><span data-stu-id="e5898-142">a.</span></span> <span data-ttu-id="e5898-143">**대상 서버의 FQDN**아래에서 **선택을**클릭 하 고 알림 응용 프로그램을 실행 하는 응용 프로그램 서비스의 서비스 ID를 클릭 하 여이 범위의 지정 되지 않은 번호로 걸려오는 통화를 처리 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="e5898-144">b.</span><span class="sxs-lookup"><span data-stu-id="e5898-144">b.</span></span> <span data-ttu-id="e5898-145">**알림에서**이 지정 되지 않은 숫자 범위에 대해 재생할 공지 사항을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="e5898-146">이전 단계에서 **EXCHANGE UM**을 클릭 한 후 **자동 전화 교환 전화 번호**아래에서 **선택을**클릭 하 고 지정 하지 않은이 범위의 번호에 사용할 전화 번호를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="e5898-147">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="e5898-148">지정 하지 않은 **번호** 페이지에서 지정 하지 않은 번호 범위가 원하는 순서 대로 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-148">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want.</span></span> <span data-ttu-id="e5898-149">표에서 범위의 위치를 변경 하려면 범위 목록에서 하나 이상의 연속 된 이름을 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-149">To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e5898-150">비즈니스용 Skype Server는 할당 되지 않은 번호 테이블을 위에서 아래로 검색 하 고 지정 된 번호와 일치 하는 첫 번째 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="e5898-151">겹치는 범위와 한 범위에서 마지막 리조트 작업을 지정 하는 경우 해당 범위가 목록의 맨 아래에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="e5898-152">지정 하지 않은 번호 범위가 원하는 순서 대로 되어 있으면 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="e5898-153">비즈니스용 Skype Server Management Shell을 사용 하 여 할당 되지 않은 전화 번호를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="e5898-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="e5898-154">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="e5898-155">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e5898-156">**New-CsUnassignedNumber** 를 사용 하 여 할당 되지 않은 새 번호 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="e5898-157">**Set-CsUnassignedNumber** 를 사용 하 여 지정 되지 않은 기존 번호 범위를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e5898-158">범위가 겹쳐져 특정 순서로 범위를 적용 하려면 Priority 매개 변수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="e5898-159">우선 순위가 가장 높은 범위가 통화에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="e5898-160">값 0은 가장 높은 우선 순위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="e5898-161">명령줄에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="e5898-162">알림 서비스에 대 한 번호 범위를 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-162">To create a number range for an Announcement service, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="e5898-163">또는 Exchange UM 자동 전화 교환에 대 한 숫자 범위를 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="e5898-164">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-164">For example:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="e5898-165">또는</span><span class="sxs-lookup"><span data-stu-id="e5898-165">Or</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="e5898-166">다음 예제에서는 기존에 할당 되지 않은 숫자 범위에서 숫자를 수정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="e5898-167">Unnasigned 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="e5898-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="e5898-168">비즈니스용 Skype Server 제어판을 사용 하 여 지정 되지 않은 번호 범위를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="e5898-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="e5898-169">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-169">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e5898-170">자세한 내용은 **대리인 설정 사용**을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5898-170">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="e5898-171">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e5898-172">왼쪽 탐색 모음에서 **음성 기능** 을 클릭 한 다음 지정 하지 **않은 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="e5898-173">지정 하지 **않은 번호** 페이지의 검색 필드에 삭제 하려는 배정 되지 않은 번호 범위 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="e5898-174">결과 번호 범위 목록에서 이름을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="e5898-175">**모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="e5898-176">비즈니스용 Skype Server Management Shell을 사용 하 여 지정 되지 않은 번호 범위를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="e5898-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="e5898-177">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="e5898-178">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e5898-179">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-179">At the command line, type:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="e5898-180">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5898-180">For example:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="e5898-181">추가 옵션에 대 한 자세한 내용은 [제거-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5898-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e5898-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5898-182">See also</span></span>

[<span data-ttu-id="e5898-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e5898-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="e5898-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e5898-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="e5898-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e5898-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
