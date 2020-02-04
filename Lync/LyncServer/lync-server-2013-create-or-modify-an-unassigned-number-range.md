---
title: 'Lync Server 2013: 할당 되지 않은 숫자 범위 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90b6068de77a1a32f45afbc34604dc70a4daf58e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="e5316-102">Lync Server 2013에서 할당 되지 않은 숫자 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="e5316-102">Create or modify an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5316-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e5316-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e5316-104">다음 절차 중 하나를 사용 하 여 알림 신청에 대해 할당 되지 않은 번호 범위를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-104">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5316-105">지정 하지 않은 번호 테이블을 구성 하기 전에 이미 하나 이상의 알림을 정의 하거나 UM (Exchange 통합 메시징) 자동 전화 교환을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-105">Before you configure the unassigned number table, you must have already defined one or more announcements or set up an Exchange Unified Messaging (UM) Auto Attendant.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="e5316-106">Lync Server 제어판을 사용 하 여 할당 되지 않은 전화 번호를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="e5316-106">To use Lync Server Control Panel to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="e5316-107">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e5316-108">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5316-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e5316-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e5316-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5316-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e5316-111">왼쪽 탐색 모음에서 **음성 기능**을 클릭 한 다음 지정 하지 **않은 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-111">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="e5316-112">지정 하지 **않은 번호** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-112">On the **Unassigned Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e5316-113">새 번호 범위를 만들려면 **새로**만들기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-113">To create a new number range, click **New**.</span></span> <span data-ttu-id="e5316-114">**이름**에이 숫자 범위에 대 한 식별 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-114">In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e5316-115">데이터베이스에 새 할당 되지 않은 번호 범위를 커밋한 후에는이 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-115">After you commit the new unassigned number range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="e5316-116">기존 번호 범위를 수정 하려면 검색 필드에 숫자 범위 이름 전체 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-116">To modify an existing number range, type all or part of the name of the number range in the search field.</span></span> <span data-ttu-id="e5316-117">결과 번호 범위 목록에서 원하는 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-117">In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e5316-118">첫 번째 **숫자 범위** 필드에 범위의 시작 번호를 입력 하 고 두 번째 **숫자 범위** 필드에 범위의 끝 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-118">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="e5316-119">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-119">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e5316-120">범위의 시작 번호 또는 범위의 끝 번호에 내선 번호가 포함 된 경우, 시작 번호와 범위의 끝 번호에는 확장명이 포함 되어야 하 고, 내선 번호는 시작 번호와이 둘 다에 대해 동일 해야 합니다. 끝 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-120">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e5316-121">번호는 정규식 (tel:)과 일치 해야 합니다 ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="e5316-121">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="e5316-122">즉,이 숫자는 문자열 tel로 시작 될 수 있습니다 (해당 문자열을 지정 하지 않으면 자동으로 추가 됩니다), 더하기 기호 (+), 숫자 1 ~ 9</span><span class="sxs-lookup"><span data-stu-id="e5316-122">This means the number may begin with the string tel: (if you don’t specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="e5316-123">전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-123">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="e5316-124">**알림 서비스**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-124">In **Announcement service**, do one of the following:</span></span>
    
      - <span data-ttu-id="e5316-125">**공지 사항을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-125">Click **Announcement**.</span></span>
    
      - <span data-ttu-id="e5316-126">**EXCHANGE UM**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-126">Click **Exchange UM**.</span></span>

7.  <span data-ttu-id="e5316-127">이전 단계에서 **공지 사항을**클릭 한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-127">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    1.  <span data-ttu-id="e5316-128">**대상 서버의 FQDN**아래에서 **선택을**클릭 하 고 알림 응용 프로그램을 실행 하는 응용 프로그램 서비스의 서비스 ID를 클릭 하 여이 범위의 지정 되지 않은 번호로 걸려오는 통화를 처리 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-128">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    2.  <span data-ttu-id="e5316-129">**알림에서**이 지정 되지 않은 숫자 범위에 대해 재생할 공지 사항을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-129">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>

8.  <span data-ttu-id="e5316-130">이전 단계에서 **EXCHANGE UM**을 클릭 한 후 **자동 전화 교환 전화 번호**아래에서 **선택을**클릭 하 고 지정 하지 않은이 범위의 번호에 사용할 전화 번호를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-130">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>

9.  <span data-ttu-id="e5316-131">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-131">Click **OK**.</span></span>

10. <span data-ttu-id="e5316-132">지정 하지 않은 **번호** 페이지에서 지정 하지 않은 번호 범위가 원하는 순서 대로 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-132">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want.</span></span> <span data-ttu-id="e5316-133">표에서 범위의 위치를 변경 하려면 범위 목록에서 하나 이상의 연속 된 이름을 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-133">To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e5316-134">지정 하지 않은 번호 표를 맨 위에서 아래로 검색 하 고 지정 된 번호와 일치 하는 첫 번째 범위를 사용 하는 Lync Server</span><span class="sxs-lookup"><span data-stu-id="e5316-134">Lync Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="e5316-135">겹치는 범위와 한 범위에서 마지막 리조트 작업을 지정 하는 경우 해당 범위가 목록의 맨 아래에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-135">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

    
    </div>

11. <span data-ttu-id="e5316-136">지정 하지 않은 번호 범위가 원하는 순서 대로 되어 있으면 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-136">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="e5316-137">Windows PowerShell을 사용 하 여 지정 되지 않은 전화 번호를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="e5316-137">To use Windows PowerShell to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="e5316-138">Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-138">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e5316-139">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e5316-140">**New-CsUnassignedNumber** 를 사용 하 여 할당 되지 않은 새 번호 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-140">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="e5316-141">**Set-CsUnassignedNumber** 를 사용 하 여 지정 되지 않은 기존 번호 범위를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-141">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e5316-142">범위가 겹쳐져 특정 순서로 범위를 적용 하려면 Priority 매개 변수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-142">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="e5316-143">우선 순위가 가장 높은 범위가 통화에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-143">The range with the highest priority will be applied to the call.</span></span>

    
    </div>
    
    <span data-ttu-id="e5316-144">명령줄에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-144">At the command line, do one of the following:</span></span>
    
      - <span data-ttu-id="e5316-145">알림 서비스에 대 한 번호 범위를 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-145">To create a number range for an Announcement service, run:</span></span>
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - <span data-ttu-id="e5316-146">또는 Exchange UM 자동 전화 교환에 대 한 숫자 범위를 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-146">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    <span data-ttu-id="e5316-147">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-147">For example:</span></span>
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    <span data-ttu-id="e5316-148">또는</span><span class="sxs-lookup"><span data-stu-id="e5316-148">Or</span></span>
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    <span data-ttu-id="e5316-149">다음 예제에서는 기존에 할당 되지 않은 숫자 범위에서 숫자를 수정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5316-149">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5316-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5316-150">See Also</span></span>


[<span data-ttu-id="e5316-151">Lync Server 2013에서 할당 되지 않은 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="e5316-151">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)  


[<span data-ttu-id="e5316-152">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e5316-152">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[<span data-ttu-id="e5316-153">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e5316-153">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[<span data-ttu-id="e5316-154">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e5316-154">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

