---
title: 모임 구성 설정 모음 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="61d3b-102">Lync Server 2013에서 모임 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="61d3b-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61d3b-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="61d3b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="61d3b-104">모임 구성 페이지의 설정을 사용 하 여 모임 참가 환경의 다양 한 특성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-104">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience.</span></span> <span data-ttu-id="61d3b-105">기본적으로 전역 설정은 참가 환경을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-105">By default, the global settings define the join experience.</span></span> <span data-ttu-id="61d3b-106">사이트 수준 및 풀 수준 모임 참가 설정을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-106">You can also create site-level and pool-level meeting join settings.</span></span> <span data-ttu-id="61d3b-107">풀 수준 설정을 만드는 경우 해당 설정이 해당 풀에서 호스트 하는 모든 모임에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-107">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="61d3b-108">풀 수준 설정을 만들지 않으면 사이트 수준 설정이 있는 경우 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-108">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="61d3b-109">사이트 수준 설정을 정의 하지 않으면 모든 모임에 전역 설정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-109">If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="61d3b-110">새 모임 참가 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="61d3b-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="61d3b-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="61d3b-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="61d3b-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61d3b-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="61d3b-114">왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **모임 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="61d3b-115">**모임 구성** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="61d3b-116">사이트 수준 정책을 만들려면 **사이트 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-116">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="61d3b-117">사이트 검색 **선택** 필드에 모임 참가 설정을 정의할 사이트 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-117">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="61d3b-118">사이트 결과 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-118">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="61d3b-119">풀 수준 정책을 만들려면 **풀 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-119">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="61d3b-120">서비스 검색 **선택** 필드에 모임 참가 설정을 정의할 풀 서비스 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-120">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="61d3b-121">결과 서비스 목록에서 원하는 풀을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-121">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="61d3b-122">대기실를 통해 PSTN (공개 교환 전화 네트워크)에서 전화 접속 하는 참가자를 라우팅하려면 **pstn 발신자의 로비 사용 안 함** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-122">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box.</span></span> <span data-ttu-id="61d3b-123">기본적으로 PSTN에서 전화를 거는 참가자는 모임으로 직접 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-123">By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="61d3b-124">모임에서 발표자가 될 수 있는 사용자를 구성 하려면 **발표자로 지정**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="61d3b-125">이끌이 이외의 사용자가 발표자가 될 수 없도록 하려면 **없음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="61d3b-126">조직의 구성원 인 참가자만 발표자로 지정할 수 있도록 하려면 **회사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-126">To allow only participants who are members of your organization to be a presenter, click **Company**.</span></span> <span data-ttu-id="61d3b-127">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-127">This is the default setting.</span></span>
    
      - <span data-ttu-id="61d3b-128">모든 참가자가 발표자로 지정 하도록 허용 하려면 **모든 사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="61d3b-129">모임을 예약할 때 주최자가 회의 유형을 선택 하도록 하려면 **기본적으로 지정 된 회의 유형** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-129">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box.</span></span> <span data-ttu-id="61d3b-130">기본적으로 회의 유형은 자동으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-130">By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="61d3b-131">익명 (인증 되지 않은) 사용자가 자동으로 허용 되지 않도록 하려면 **기본적으로 익명 사용자** 허용 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-131">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box.</span></span> <span data-ttu-id="61d3b-132">기본적으로 익명 사용자는 자동으로 모임에 참석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-132">By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="61d3b-133">참가자에 게 전송 되는 모임 초대를 사용자 지정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="61d3b-134">Url 및 사용자 지정 바닥글 텍스트에 대 한 최대 길이는 1KB 것을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="61d3b-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="61d3b-135">**도움말 URL**을 제외한 사용자 지정에 대 한 값을 지정 하지 않으면 모임에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="61d3b-136">사용자 지정 도움말 URL이 포함 되어 있지 않으면 Lync에 대 한 기본 도움말 URL이 초대에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="61d3b-137">모임 초대에 표시 되는 로고를 사용자 지정 하려면 **로고 URL**에 로고의 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="61d3b-138">로고는 188 x 30 픽셀 크기의 GIF 또는 JPG 이미지 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="61d3b-139">모임 초대에 표시 되는 도움말 텍스트를 사용자 지정 하려면 **도움말 URL**에 도움말 텍스트의 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="61d3b-140">모임 초대에 표시 되는 법률 텍스트를 사용자 지정 하려면 **legal 텍스트 URL**에 법률 텍스트의 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="61d3b-141">모임 초대에 표시 되는 바닥글 텍스트를 사용자 지정 하려면 **사용자 지정 바닥글 텍스트**에 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="61d3b-142">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="61d3b-143">기존 모임 구성 모음을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="61d3b-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="61d3b-144">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="61d3b-145">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="61d3b-146">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61d3b-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="61d3b-147">왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **모임 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="61d3b-148">모임 구성 목록에서 변경 하려는 구성을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="61d3b-149">**모임 구성 편집**에서 수정할 수 없는 구성 이름을 제외한 모든 구성 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="61d3b-150">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="61d3b-151">Windows PowerShell Cmdlet을 사용 하 여 새 모임 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="61d3b-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="61d3b-152">Windows PowerShell 및 새 CsMeetingConfiguration cmdlet을 사용 하 여 모임 구성 설정을 만들 수 있습니다 (사이트 범위에만 해당).</span><span class="sxs-lookup"><span data-stu-id="61d3b-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="61d3b-153">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="61d3b-154">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61d3b-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="61d3b-155">기본 값을 사용 하는 모임 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="61d3b-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="61d3b-156">이 명령은 Redmond 사이트에 대 한 새 모임 구성 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="61d3b-157">앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 모임 구성 설정에는 해당 속성에 대 한 기본값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="61d3b-158">모임 구성 설정을 만들 때 속성 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="61d3b-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="61d3b-159">다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-159">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="61d3b-160">예를 들어 기본적으로 모든 사용자가 발표자로 모임에 참가 하도록 허용 하는 모임 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-160">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="61d3b-161">모임 구성 설정을 만들 때 여러 속성 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="61d3b-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="61d3b-162">여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-162">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="61d3b-163">예를 들어이 명령은 모든 사람을 발표자로 모임에 입장할, PSTN 사용자가 모임에 공식적으로 참석할 때까지 대기실에서 대기 하도록 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d3b-163">For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="61d3b-164">자세한 내용은 [새 CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61d3b-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

