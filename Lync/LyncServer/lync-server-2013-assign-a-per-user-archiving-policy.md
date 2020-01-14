---
title: 'Lync Server 2013: 사용자별 보관 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d23e44e397a77f0d490d8fda27ee711d1c61c5
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111582"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="b8a6a-102">Lync Server 2013에서 사용자 단위 보관 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b8a6a-102">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="b8a6a-103">보관 정책은 Lync Server 2013 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-103">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="b8a6a-104">하나 이상의 사용자 단위 보관 정책을 배포 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-104">Deploying one or more per-user archiving policies is optional.</span></span> <span data-ttu-id="b8a6a-105">전역 수준의 보관 정책 또는 사이트 수준 보관 정책만 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-105">You can also deploy only a global-level archiving policy or site-level archiving policy.</span></span> <span data-ttu-id="b8a6a-106">사용자별 정책을 배포 하는 경우 사용자, 그룹 또는 연락처 개체에 명시적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="b8a6a-107">특정 사이트 수준 또는 사용자 단위 정책이 할당 되지 않은 경우 전역 수준 회의 정책에 정의 된 대로 자동으로 보관 요구 사항을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-107">Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="b8a6a-108">사용자 당 하나 이상의 보관 정책을 만든 후에는이 항목의 절차를 사용 하 여 특정 사용자의 내부 통신, 외부 통신 또는 두 가지 모두를 서버에서 보관 하는지 여부를 적절 하 게 지정 하는 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-108">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="b8a6a-109">사용자별 보관 정책을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 보관 정책 만들기를 참조 하 여 특정 사이트 또는 사용자에 대 한 내부 또는 외부 통신을 사용 하거나 보관 하지 않도록 설정](lync-server-2013-create-archiving-policy-sites-users.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-109">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="b8a6a-110">사용자별 보관 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="b8a6a-110">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="b8a6a-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b8a6a-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b8a6a-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b8a6a-114">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b8a6a-115">사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="b8a6a-116">사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="b8a6a-117">저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="b8a6a-118">) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="b8a6a-119">**필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="b8a6a-120">사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="b8a6a-121">다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="b8a6a-122">선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b8a6a-123">쿼리에 추가 검색 절을 추가 하려면 <STRONG>필터 추가</STRONG>를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="b8a6a-124">**찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-124">Click **Find**.</span></span>

6.  <span data-ttu-id="b8a6a-125">검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음 **정책 할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="b8a6a-126">동일한 사용자별 보관 정책을 여러 사용자에 게 적용 하려면 검색 결과에서 여러 사용자를 선택한 다음 <STRONG>작업</STRONG>을 클릭 하 고 <STRONG>정책 할당</STRONG>을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-126">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="b8a6a-127">**정책 할당**의 **보관 정책**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-127">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b8a6a-128"><STRONG>정책 할당</STRONG> 대화 상자를 <STRONG> &lt;&gt; </STRONG> 사용 하 여 구성할 수 있는 정책이 여러 개 있기 때문에 대화 상자에 있는 모든 정책에 대해 다음으로 유지 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="b8a6a-129">이전에이 설정을 변경 하지 않고 사용자에 게 할당 된 정책을 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="b8a6a-130">Lync Server 2013이 전역 수준 정책을 자동으로 선택 하도록 허용 하거나 정의 된 경우 사이트 수준 정책으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="b8a6a-131">이전에 **보관 정책** 페이지에 정의한 사용자 단위 보관 정책의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-131">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b8a6a-132">할당할 정책을 결정 하는 데 도움이 되도록 정책 이름을 클릭 한 후 <STRONG>보기</STRONG> 를 클릭 하 여 정책에 정의 된 사용자 권한 및 사용 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-132">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="b8a6a-133">완료 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b8a6a-134">Windows PowerShell Cmdlet을 사용 하 여 사용자별 보관 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b8a6a-134">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b8a6a-135">Windows PowerShell 및 **CsArchivingPolicy** cmdlet을 사용 하 여 사용자별 보관 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-135">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="b8a6a-136">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-136">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b8a6a-137">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="b8a6a-138">단일 사용자에 게 사용자별 보관 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="b8a6a-138">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="b8a6a-139">다음 명령을 사용 하 여 사용자 단위 보관 정책을 RedmondArchivingPolicy: 진구 Myer에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-139">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="b8a6a-140">사용자 단위 보관 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="b8a6a-140">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="b8a6a-141">이 명령은 등록자 풀 atl-cs-001.litwareinc.com에 속한 계정이 있는 모든 사용자에 대해 사용자 단위 보관 정책 RedmondArchivingPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-141">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b8a6a-142">이 명령에 사용 된 필터 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="b8a6a-143">사용자별 보관 정책을 할당 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="b8a6a-143">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="b8a6a-144">다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 보관 정책을 할당 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-144">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="b8a6a-145">사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책을 사용 하 여 자동으로 관리 되거나 있는 경우 해당 로컬 사이트 정책이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="b8a6a-146">사이트 정책이 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="b8a6a-147">자세한 내용은 [CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8a6a-147">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8a6a-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8a6a-148">See Also</span></span>


[<span data-ttu-id="b8a6a-149">특정 사이트 또는 사용자에 대 한 내부 또는 외부 통신의 보관을 사용 하거나 사용 하지 않도록 설정 하 여 Lync Server 2013에서 보관 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b8a6a-149">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="b8a6a-150">Lync Server 2013에서 사용자별 정책 지정</span><span class="sxs-lookup"><span data-stu-id="b8a6a-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

