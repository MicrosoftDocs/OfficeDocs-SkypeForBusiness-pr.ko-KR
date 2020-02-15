---
title: 'Lync Server 2013: 사용자별 PIN 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9523794808ca3b689cf1f3213c1f4ad657c83c25
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030121"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="1d2f0-102">Lync Server 2013에서 사용자별 PIN 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1d2f0-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="1d2f0-103">전화 접속 회의 PIN (개인 식별 번호) 정책은 Lync Server 2013 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="1d2f0-104">하나 이상의 사용자별 PIN 정책을 배포 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-104">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="1d2f0-105">또한 글로벌 수준 PIN 정책 또는 사이트 수준 PIN 정책만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-105">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="1d2f0-106">사용자별 정책을 배포하는 경우에는 해당 정책을 사용자, 그룹 또는 연락처 개체에 명시적으로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="1d2f0-107">전화 접속 회의에 대 한 Pin 사용에 대 한 사용자 권한 및 사용 권한은 특정 사이트 수준 또는 사용자별 정책이 할당 되지 않은 경우 전역 수준 PIN 정책에 정의 된 대로 자동으로 기본값으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-107">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="1d2f0-108">하나 이상의 사용자별 PIN 정책을 만든 후이 항목의 절차를 사용 하 여 서버에서 특정 사용자가 만들고 사용 하는 Pin에 대해 설정할 제약 조건을 지정 하는 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="1d2f0-109">사용자별 전화 접속 회의 PIN 정책을 만드는 방법에 대 한 자세한 내용은 [사이트 또는 사용자 그룹에 대해 Lync Server 2013에서 전화 접속 회의 pin 설정 만들기 또는 수정을](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="1d2f0-110">사용자별 PIN 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="1d2f0-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="1d2f0-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d2f0-112">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d2f0-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d2f0-114">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="1d2f0-115">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="1d2f0-116">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="1d2f0-117">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="1d2f0-118">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="1d2f0-119">**필터 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="1d2f0-120">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="1d2f0-121">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="1d2f0-122">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="1d2f0-123">쿼리에 검색 절을 더 추가하려면 <STRONG>필터 추가</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="1d2f0-124">**찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-124">Click **Find**.</span></span>

6.  <span data-ttu-id="1d2f0-125">검색 결과에서 사용자를 클릭하고 **동작**을 클릭한 후에 **정책 할당**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="1d2f0-126">여러 사용자에 게 동일한 사용자별 PIN 정책을 적용 하려면 검색 결과에서 여러 사용자를 선택 하 고 <STRONG>동작</STRONG>을 클릭 한 후에 <STRONG>정책 할당</STRONG>을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="1d2f0-127">**정책 할당**의 **PIN 정책**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1d2f0-128"><STRONG>정책 할당</STRONG> 대화 <STRONG> &lt;상자를&gt; 사용</STRONG> 하 여 구성할 수 있는 정책이 여러 개 있으므로 대화 상자의 모든 정책에 대해 다음 사용자가 기본적으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="1d2f0-129">이 설정을 변경하지 않으면 이전에 사용자에게 지정된 정책이 계속 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="1d2f0-130">Lync Server 2013에서 전역 수준 정책을 자동으로 선택 하도록 허용 하거나, 정의 된 경우 사이트 수준 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="1d2f0-131">**PIN 정책** 페이지에서 이전에 정의한 사용자별 PIN 정책의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="1d2f0-132">지정할 정책을 쉽게 결정하려면 정책 이름을 클릭한 후 <STRONG>보기</STRONG>를 클릭하여 정책에 정의된 사용자 권한 및 권한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="1d2f0-133">작업을 마치면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1d2f0-134">Windows PowerShell Cmdlet을 사용 하 여 사용자별 PIN 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1d2f0-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1d2f0-135">Windows PowerShell 및 **get-cspinpolicy** cmdlet을 사용 하 여 사용자별 PIN 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="1d2f0-136">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1d2f0-137">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="1d2f0-138">단일 사용자에 게 사용자별 PIN 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="1d2f0-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="1d2f0-139">다음 명령은 사용자 Ken Myer에 게 사용자별 PIN 정책 Redmondpinpolicy가 포함를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="1d2f0-140">여러 사용자에 게 사용자별 PIN 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="1d2f0-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="1d2f0-141">다음 명령은 Redmond의 도시에서 근무 하는 모든 사용자에 게 사용자별 PIN 정책 RedmondUsersPinPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="1d2f0-142">이 명령에서 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="1d2f0-143">사용자별 PIN 정책을 할당 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="1d2f0-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="1d2f0-144">다음 명령은 이전에 Ken Myer에 할당 된 사용자별 PIN 정책을 할당 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-144">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="1d2f0-145">사용자별 정책을 지정 해제한 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용해서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="1d2f0-146">사이트 정책은 글로벌 정책보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="1d2f0-147">자세한 내용은 [Grant-get-cspinpolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d2f0-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d2f0-148">See Also</span></span>


[<span data-ttu-id="1d2f0-149">Lync Server 2013에서 새 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1d2f0-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="1d2f0-150">Lync Server 2013에서 사용자별 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1d2f0-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

