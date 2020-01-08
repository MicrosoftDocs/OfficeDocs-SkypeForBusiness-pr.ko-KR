---
title: 'Lync Server 2013: 사용자 단위 회의 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dbeb129ef58c6993d1cd919b03d7417d35b439a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985648"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="aebc2-102">Lync Server 2013에서 사용자 단위 회의 정책 할당</span><span class="sxs-lookup"><span data-stu-id="aebc2-102">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="aebc2-103">회의 정책은 Lync Server 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-103">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="aebc2-104">하나 이상의 사용자 단위 회의 정책을 배포 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-104">Deploying one or more per-user conferencing policies is optional.</span></span> <span data-ttu-id="aebc2-105">전역 수준 회의 정책 또는 사이트 수준 회의 정책만 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-105">You can also deploy only a global-level conferencing policy or site-level conferencing policy.</span></span> <span data-ttu-id="aebc2-106">사용자별 정책을 배포 하는 경우 사용자, 그룹 또는 연락처 개체에 명시적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span> <span data-ttu-id="aebc2-107">회의 사용자 권한 및 사용 권한은 특정 사이트 수준 또는 사용자 단위 정책이 할당 되지 않은 경우 전역 수준 회의 정책에 정의 된 대로 자동으로 기본값으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-107">Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="aebc2-108">하나 이상의 사용자 단위 회의 정책을 만든 후에는이 항목의 절차를 사용 하 여 서버에서 특정 사용자가 구성한 모임에 부여 하는 데 사용할 사용자 권한 및 사용 권한을 지정 하는 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-108">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="aebc2-109">사용 가능한 모든 회의 정책 설정 목록은 [Lync Server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aebc2-109">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="aebc2-110">회의 정책을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 회의 정책 만들기 또는 수정을](lync-server-2013-create-or-modify-a-conferencing-policy.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aebc2-110">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="aebc2-111">사용자 단위 회의 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="aebc2-111">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="aebc2-112">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aebc2-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aebc2-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aebc2-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aebc2-115">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="aebc2-116">사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="aebc2-117">사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="aebc2-118">저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="aebc2-119">) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="aebc2-120">**필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="aebc2-121">사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="aebc2-122">다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="aebc2-123">선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="aebc2-124">쿼리에 추가 검색 절을 추가 하려면 <STRONG>필터 추가</STRONG>를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="aebc2-125">**찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-125">Click **Find**.</span></span>

6.  <span data-ttu-id="aebc2-126">검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음 **정책 할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="aebc2-127">동일한 사용자별 회의 정책을 여러 사용자에 게 적용 하려는 경우 검색 결과에서 여러 사용자를 선택한 다음 <STRONG>작업</STRONG>을 클릭 하 고 <STRONG>정책 할당</STRONG>을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-127">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="aebc2-128">**지정 정책**에 있는 **회의 정책**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-128">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="aebc2-129"><STRONG>지정 정책</STRONG>에 구성할 수 있는 정책이 여러 개 있으므로 대화 상자의 모든 정책에 대해 다음 <STRONG> &lt;으로&gt; 유지</STRONG> 가 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-129">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="aebc2-130">이전에이 설정을 변경 하지 않고 사용자에 게 할당 된 정책을 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="aebc2-131">Lync Server 2013이 전역 수준 정책을 자동으로 선택 하도록 허용 하려면 \*\* \<자동\> \*\* 을 선택 하 고, 정의 하면 사이트 수준 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-131">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="aebc2-132">이전에 **회의 정책** 페이지에 정의한 사용자 단위 회의 정책의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-132">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="aebc2-133">할당 하려는 정책을 결정할 수 있도록 정책 이름을 클릭 한 후 <STRONG>보기</STRONG> 를 클릭 하 여 정책에 정의 된 사용자 권한 및 사용 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="aebc2-134">완료 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aebc2-135">Windows PowerShell Cmdlet을 사용 하 여 사용자 단위 회의 정책 할당</span><span class="sxs-lookup"><span data-stu-id="aebc2-135">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aebc2-136">사용자 단위 회의 정책은 Windows PowerShell 및 CsConferencingPolicy cmdlet을 사용 하 여 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-136">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="aebc2-137">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-137">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aebc2-138">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aebc2-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="aebc2-139">단일 사용자에 게 사용자 단위 회의 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="aebc2-139">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="aebc2-140">다음 명령을 사용 하 여 사용자: 진구 Myer에 사용자 단위 회의 정책 RedmondConferencingPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-140">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="aebc2-141">사용자 단위 회의 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="aebc2-141">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="aebc2-142">이 명령은 인사부에서 근무 하는 모든 사용자에 게 사용자 단위 회의 정책 HRConferencingPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-142">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="aebc2-143">이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aebc2-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="aebc2-144">사용자 단위 회의 정책을 할당 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="aebc2-144">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="aebc2-145">다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 회의 정책을 할당 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-145">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="aebc2-146">사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책을 사용 하 여 자동으로 관리 되거나 있는 경우 해당 로컬 사이트 정책이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="aebc2-147">사이트 정책이 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="aebc2-147">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="aebc2-148">자세한 내용은 [CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aebc2-148">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="aebc2-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aebc2-149">See Also</span></span>


[<span data-ttu-id="aebc2-150">Lync Server 2013에서 회의 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="aebc2-150">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="aebc2-151">Lync Server 2013에서 사용자별 정책 지정</span><span class="sxs-lookup"><span data-stu-id="aebc2-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

