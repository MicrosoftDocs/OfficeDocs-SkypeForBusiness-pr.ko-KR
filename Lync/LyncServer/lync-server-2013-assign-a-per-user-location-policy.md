---
title: 'Lync Server 2013: 사용자 단위 위치 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a387d0f603addea31bd1e3ee6b591e06a26b2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981602"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="4a8ab-102">Lync Server 2013에서 사용자 단위 위치 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4a8ab-102">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="4a8ab-103">위치 정책은 Lync Server 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-103">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="4a8ab-104">하나 이상의 사용자 단위 위치 정책을 배포 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-104">Deploying one or more per-user location policies is optional.</span></span> <span data-ttu-id="4a8ab-105">전역 수준의 위치 정책 또는 서브넷 수준 위치 정책만 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-105">You can also deploy only a global-level location policy or subnet-level location policy.</span></span> <span data-ttu-id="4a8ab-106">사용자별 정책을 배포 하는 경우 사용자, 그룹 또는 연락처 개체에 명시적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="4a8ab-107">향상 된 9-1-1 (E9-1) 설정은 특정 서브넷 수준 또는 사용자 단위 정책이 할당 되지 않은 경우 전역 수준 위치 정책에 정의 된 대로 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-107">Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="4a8ab-108">하나 이상의 사용자 기준 정책을 만든 후에는이 항목의 절차를 사용 하 여 특정 사용자가 설정한 비상 전화에 대해 서버가 적용할 설정을 지정 하는 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-108">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="4a8ab-109">사용할 수 있는 모든 위치 정책 설정 목록은 [Lync Server 2013의 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-109">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="4a8ab-110">위치 정책 만들기에 대 한 자세한 내용은 [Lync Server 2013에서 위치 정책 만들기](lync-server-2013-create-location-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-110">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="4a8ab-111">Lync Server 제어판을 사용 하 여 사용자 단위 위치 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="4a8ab-111">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4a8ab-112">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4a8ab-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4a8ab-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4a8ab-115">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="4a8ab-116">사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="4a8ab-117">사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="4a8ab-118">저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="4a8ab-119">) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="4a8ab-120">**필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="4a8ab-121">사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="4a8ab-122">다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="4a8ab-123">선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="4a8ab-124">쿼리에 추가 검색 절을 추가 하려면 <STRONG>필터 추가</STRONG>를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="4a8ab-125">**찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-125">Click **Find**.</span></span>

6.  <span data-ttu-id="4a8ab-126">검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음 **정책 할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="4a8ab-127">동일한 사용자별 위치 정책을 여러 사용자에 게 적용 하려면 검색 결과에서 여러 사용자를 선택한 다음 <STRONG>작업</STRONG>을 클릭 하 고 <STRONG>정책 할당</STRONG>을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-127">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="4a8ab-128">**지정 정책**에서 **위치 정책**아래에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-128">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="4a8ab-129"><STRONG>정책 할당</STRONG> 대화 상자를 <STRONG> &lt;&gt; </STRONG> 사용 하 여 구성할 수 있는 정책이 여러 개 있기 때문에 대화 상자에 있는 모든 정책에 대해 다음으로 유지 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="4a8ab-130">이전에이 설정을 변경 하지 않고 사용자에 게 할당 된 정책을 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="4a8ab-131">Lync Server 2013이 전역 수준 정책을 자동으로 선택 하도록 허용 하거나 정의 된 경우 서브넷 수준 정책 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="4a8ab-132">**새-CsLocationPolicy** cmdlet을 실행 하 여 이전에 정의한 사용자 단위 위치 정책의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-132">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="4a8ab-133">할당할 정책을 결정 하는 데 도움이 되도록 정책 이름을 클릭 한 후 <STRONG>보기</STRONG> 를 클릭 하 여 정책에 정의 된 사용자 권한 및 사용 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="4a8ab-134">완료 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="4a8ab-135">Lync Server Management Shell Cmdlet을 사용 하 여 사용자 단위 위치 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4a8ab-135">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="4a8ab-136">허용-CsLocationPolicy cmdlet을 사용 하 여 사용자별 위치 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-136">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="4a8ab-137">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4a8ab-138">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="4a8ab-139">단일 사용자에 게 사용자별 위치 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="4a8ab-139">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="4a8ab-140">다음 명령을 사용 하 여 사용자: 진구 Myer에 사용자별 위치 정책 RedmondLocationPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-140">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="4a8ab-141">사용자별 위치 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="4a8ab-141">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="4a8ab-142">이 명령은 회계 부서로 근무 하는 모든 사용자에 게 사용자별 위치 정책 AccountingDepartmentLocationPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-142">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="4a8ab-143">이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="4a8ab-144">사용자별 위치 정책을 할당 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="4a8ab-144">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="4a8ab-145">다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 위치 정책을 할당 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-145">The following command unassigns any per-user location policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="4a8ab-146">사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책을 사용 하 여 자동으로 관리 되거나 있는 경우 해당 로컬 사이트 정책이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="4a8ab-147">사이트 정책이 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-147">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="4a8ab-148">자세한 내용은 [-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-148">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

