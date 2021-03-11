---
title: 비즈니스용 Skype 서버에서 미지정 번호 범위 만들기 또는 수정
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 비즈니스용 Skype 서버 2013에서 공지사항 응용 프로그램에 대한 미지정 번호 범위를 만들거나 수정하거나 Enterprise Voice. 이는 미지정 번호에 대한 호출이 처리된 방식에 영향을 미치게 됩니다.
ms.openlocfilehash: 19a30aa4063f8ec0f4e890c4e244309347ed99c6
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711635"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="ee1d2-104">비즈니스용 Skype 서버에서 미지정 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="ee1d2-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="ee1d2-105">비즈니스용 Skype 서버 2013에서 공지사항 응용 프로그램에 대한 미지정 번호 범위를 만들거나 수정하거나 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="ee1d2-106">이는 미지정 번호에 대한 호출이 처리된 방식에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="ee1d2-107">비즈니스용 Skype 서버를 사용하면 조직에 유효하지만 사용자나 전화에 할당되지 않은 전화 번호로 걸치는 수신 전화에 대해 어떤 일이 발생하는지 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="ee1d2-108">이러한 호출을 처리하기 위해 미지정 번호 테이블을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="ee1d2-109">이 표를 사용하여 호출을 공지 응용 프로그램 또는 Exchange UM 서버로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="ee1d2-110">할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-110">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="ee1d2-111">조직에 대해 유효한 모든 내선 번호로 또는 할당되지 않은 내선 번호만으로 또는 두 번호 유형의 결합으로 테이블을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-111">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="ee1d2-112">할당되지 않은 번호 테이블은 할당된 번호와 할당되지 않은 번호를 모두 포함할 수 있지만 발신자가 현재 할당되지 않은 번호로 전화를 걸 때만 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-112">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="ee1d2-113">할당되지 않은 번호 테이블에 유효한 내선 번호를 모두 포함하면 테이블을 재구성하지 않고도 다른 사용자가 조직을 떠날 때마다 발생하는 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-113">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="ee1d2-114">테이블에 지정되지 않은 내선 번호를 포함하면 특정 번호에 대해 발생하는 작업을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-114">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="ee1d2-115">예를 들어 고객 서비스 센터의 내선 번호를 변경하는 경우 테이블에 이전 고객 서비스 번호를 포함한 다음 새 번호를 제공하는 공지에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-115">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="ee1d2-116">미지정 전화 번호 구성</span><span class="sxs-lookup"><span data-stu-id="ee1d2-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="ee1d2-117">다음 절차 중 하나를 사용하여 공지사항 응용 프로그램에 대한 미지정 번호 범위를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ee1d2-118">배정되지 않은 번호 테이블을 구성하기 전에 시스템에 이미 알림을 정의하거나 UM(Exchange 통합 메시징)을 설정해야 자동 전화 교환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="ee1d2-119">누군가가 미지정 번호로 전화를 걸면 비즈니스용 Skype 서버가 미지정 번호 테이블을 위쪽에서 아래쪽으로 검색하고 첫 번째 일치 범위를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="ee1d2-120">따라서 마지막 수단으로 수행하려는 작업은 표의 마지막 범위에 대해 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="ee1d2-121">비즈니스용 Skype 서버 제어판을 사용하여 미지정 전화 번호를 구성</span><span class="sxs-lookup"><span data-stu-id="ee1d2-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="ee1d2-122">RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ee1d2-123">자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ee1d2-124">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ee1d2-125">왼쪽 탐색 모음에서 **음성 기능** 을 클릭하고 **지정되지 않은 번호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="ee1d2-126">**지정되지 않은 번호** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="ee1d2-p107">새 번호 범위를 만들려면 **새로 만들기** 를 클릭하고 **이름** 에 이 번호 범위에 대한 식별 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="ee1d2-129">할당되지 않은 새 번호 범위를 데이터베이스에 커밋하고 나면 이 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="ee1d2-p108">기존 번호 범위를 수정하려면 검색 필드에 번호 범위의 이름을 모두 또는 일부분 입력합니다. 결과 번호 범위 목록에서 수정할 이름을 클릭하고 **편집** 을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ee1d2-132">첫 번째 **번호 범위** 필드에는 범위의 시작 번호를 입력하고, 두 번째 **번호 범위** 필드에는 해당 범위의 끝 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="ee1d2-133">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="ee1d2-134">범위의 시작 번호나 끝 번호에 내선 번호가 포함된 경우에는 범위의 시작 번호와 끝 번호 둘 다에 내선 번호가 포함되어야 하며, 내선 번호는 시작 번호와 끝 번호에 대해 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="ee1d2-135">숫자는 정규식과 일치해야 `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-135">The number must match the regular expression `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?`.</span></span> <span data-ttu-id="ee1d2-136">즉, 숫자가 문자열로 시작될 수 있습니다(해당 문자열을 지정하지 않으면 자동으로 추가됩니다), 더하기 `tel:` 기호(+) 및 숫자 1-9.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-136">This means the number may begin with the string `tel:` (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="ee1d2-137">전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="ee1d2-138">**알림 서비스** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="ee1d2-139">**알림** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="ee1d2-140">**Exchange UM** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="ee1d2-141">이전 단계에서 **알림** 을 클릭한 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="ee1d2-142">a.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-142">a.</span></span> <span data-ttu-id="ee1d2-143">**대상 서버의 FQDN** 에서 **선택** 을 클릭하고, 이 지정되지 않은 번호 범위에 대한 수신 전화를 처리할 알림 응용 프로그램을 실행하는 응용 프로그램 서비스의 서비스 ID를 클릭한 후에 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="ee1d2-144">b.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-144">b.</span></span> <span data-ttu-id="ee1d2-145">**알림** 에서 이 지정되지 않은 번호 범위에 대해 재생할 알림을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="ee1d2-146">이전 단계에서 **Exchange UM** 을 클릭한 경우에는 **자동 전화 교환 전화 번호** 에서 **선택** 을 클릭하고 이 지정되지 않은 번호 범위에 사용할 전화 번호를 클릭한 후에 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="ee1d2-147">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="ee1d2-p112">**지정되지 않은 번호** 페이지에서 지정되지 않은 번호 범위가 원하는 순서로 정렬되어 있는지 확인합니다. 표에서 범위 위치를 변경하려면 범위 목록에서 연속하는 이름을 하나 이상 클릭하고 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ee1d2-150">비즈니스용 Skype 서버는 미지정 번호 테이블을 위쪽에서 아래쪽으로 검색하고, 미지정 번호와 일치하는 첫 번째 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="ee1d2-151">겹치는 범위와 최후의 수단으로 수행할 작업을 지정하는 범위가 있는 경우에는 해당 범위가 목록 맨 밑에 오도록 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="ee1d2-152">할당되지 않은 번호 범위를 원하는 순서대로 표시하려면 **모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="ee1d2-153">비즈니스용 Skype 서버 관리 셸을 사용하여 미지정 전화 번호를 구성</span><span class="sxs-lookup"><span data-stu-id="ee1d2-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="ee1d2-154">비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 설치 권한 위임에 설명된 필요한 사용자 권한으로 **로그온합니다.**</span><span class="sxs-lookup"><span data-stu-id="ee1d2-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ee1d2-155">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ee1d2-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ee1d2-156">**New-CsUnassignedNumber를** 사용하여 새 미지정 번호 범위를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="ee1d2-157">**Set-CsUnassignedNumber를** 사용하여 기존 미지정 번호 범위를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ee1d2-158">겹치는 범위가 있고 해당 범위가 특정 순서로 적용되게 하려는 경우에는 Priority 매개 변수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="ee1d2-159">우선 순위가 가장 높은 범위가 통화 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="ee1d2-160">값 0은 가장 높은 우선 순위를 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="ee1d2-161">명령줄에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="ee1d2-162">알림 서비스에 대한 번호 범위를 만들려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-162">To create a number range for an Announcement service, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="ee1d2-163">또는 Exchange UM 자동 전화 교환에 대한 번호 범위를 만들려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="ee1d2-164">예:</span><span class="sxs-lookup"><span data-stu-id="ee1d2-164">For example:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="ee1d2-165">또는</span><span class="sxs-lookup"><span data-stu-id="ee1d2-165">Or</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="ee1d2-166">다음 예에서는 지정되지 않은 기존 번호 범위의 번호를 수정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="ee1d2-167">분석되지 않은 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="ee1d2-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="ee1d2-168">비즈니스용 Skype 서버 제어판을 사용하여 미지정 번호 범위를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="ee1d2-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="ee1d2-169">RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-169">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ee1d2-170">자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-170">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ee1d2-171">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ee1d2-172">왼쪽 탐색 모음에서 **음성 기능** 을 클릭하고 **지정되지 않은 번호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="ee1d2-173">**지정되지 않은 번호** 페이지의 검색 필드에 삭제할 할당되지 않은 번호 범위의 이름 일부나 전체를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="ee1d2-174">결과 번호 범위 목록에서 이름을 클릭하고 **편집** 을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="ee1d2-175">**모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="ee1d2-176">비즈니스용 Skype 서버 관리 셸을 사용하여 미지정 번호 범위를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="ee1d2-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="ee1d2-177">비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 설치 권한 위임에 설명된 필요한 사용자 권한으로 **로그온합니다.**</span><span class="sxs-lookup"><span data-stu-id="ee1d2-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ee1d2-178">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ee1d2-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ee1d2-179">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-179">At the command line, type:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="ee1d2-180">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ee1d2-180">For example:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="ee1d2-181">추가 옵션에 대한 자세한 내용은 [Remove-CsCallParkOrbit을 참조하세요.](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ee1d2-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ee1d2-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee1d2-182">See also</span></span>

[<span data-ttu-id="ee1d2-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ee1d2-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="ee1d2-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ee1d2-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="ee1d2-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ee1d2-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
