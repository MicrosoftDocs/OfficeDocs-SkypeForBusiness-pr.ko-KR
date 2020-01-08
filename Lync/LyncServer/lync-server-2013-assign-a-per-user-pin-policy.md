---
title: 'Lync Server 2013: 사용자 단위 PIN 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c60943ad13bd03de6e4474ec35f2deea1964bad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976242"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="f67a6-102">Lync Server 2013에서 사용자 단위 PIN 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f67a6-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="f67a6-103">전화 접속 회의 개인 식별 번호 (PIN) 정책은 Lync Server 2013 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="f67a6-104">사용자 단위 PIN 정책은 하나 이상 배포 하는 것이 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-104">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="f67a6-105">전역 수준 PIN 정책 또는 사이트 수준 PIN 정책만 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-105">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="f67a6-106">사용자별 정책을 배포 하는 경우 사용자, 그룹 또는 연락처 개체에 명시적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="f67a6-107">특정 사이트 수준 또는 사용자별 정책이 할당 되지 않은 경우 전화 접속 회의의 핀 사용에 대 한 사용자 권한 및 사용 권한은 자동으로 전역 수준 PIN 정책에 정의 된 것과 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-107">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="f67a6-108">하나 이상의 사용자 단위 PIN 정책을 만든 후에는이 항목의 절차를 사용 하 여 서버가 특정 사용자가 만들고 사용 하는 핀에 대해 설정할 제약 조건을 지정 하는 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="f67a6-109">사용자 단위 전화 접속 회의 PIN 정책을 만드는 방법에 대 한 자세한 내용은 [사이트 또는 사용자 그룹에 대 한 Lync Server 2013에서 전화 접속 회의 pin 설정 만들기 또는 수정을](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f67a6-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="f67a6-110">사용자 단위 PIN 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="f67a6-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="f67a6-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f67a6-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f67a6-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f67a6-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f67a6-114">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f67a6-115">사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="f67a6-116">사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="f67a6-117">저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="f67a6-118">) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="f67a6-119">**필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="f67a6-120">사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="f67a6-121">다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="f67a6-122">선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="f67a6-123">쿼리에 추가 검색 절을 추가 하려면 <STRONG>필터 추가</STRONG>를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="f67a6-124">**찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-124">Click **Find**.</span></span>

6.  <span data-ttu-id="f67a6-125">검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음 **정책 할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="f67a6-126">동일한 사용자별 PIN 정책을 여러 사용자에 게 적용 하려면 검색 결과에서 여러 사용자를 선택한 다음 <STRONG>작업</STRONG>을 클릭 하 고 <STRONG>정책 할당</STRONG>을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="f67a6-127">**지정 정책**에서 **핀 정책**아래에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="f67a6-128"><STRONG>정책 할당</STRONG> 대화 상자를 <STRONG> &lt;&gt; </STRONG> 사용 하 여 구성할 수 있는 정책이 여러 개 있기 때문에 대화 상자에 있는 모든 정책에 대해 다음으로 유지 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="f67a6-129">이전에이 설정을 변경 하지 않고 사용자에 게 할당 된 정책을 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="f67a6-130">Lync Server 2013이 전역 수준 정책을 자동으로 선택 하도록 허용 하거나 정의 된 경우 사이트 수준 정책으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="f67a6-131">이전에 **PIN 정책** 페이지에 정의한 사용자 단위 PIN 정책의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="f67a6-132">할당 하려는 정책을 결정할 수 있도록 정책 이름을 클릭 한 후 <STRONG>보기</STRONG> 를 클릭 하 여 정책에 정의 된 사용자 권한 및 사용 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="f67a6-133">완료 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f67a6-134">Windows PowerShell Cmdlet을 사용 하 여 사용자 단위 PIN 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f67a6-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f67a6-135">Windows PowerShell 및 **CsPinPolicy** cmdlet을 사용 하 여 사용자 단위 PIN 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="f67a6-136">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f67a6-137">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f67a6-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="f67a6-138">단일 사용자에 게 사용자 단위 PIN 정책을 할당 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="f67a6-139">다음 명령을 사용 하 여 사용자 단위 핀 정책 RedmondPinPolicy: 진구 Myer에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="f67a6-140">사용자 단위 PIN 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="f67a6-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="f67a6-141">다음 명령을 사용 하 여 사용자 단위 핀 정책 RedmondUsersPinPolicy을 Redmond의 구/군/시로 근무 하는 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="f67a6-142">이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f67a6-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="f67a6-143">사용자 단위 PIN 정책의 할당을 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="f67a6-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="f67a6-144">다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 PIN 정책을 할당 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-144">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="f67a6-145">사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책을 사용 하 여 자동으로 관리 되거나 있는 경우 해당 로컬 사이트 정책이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="f67a6-146">사이트 정책이 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a6-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="f67a6-147">자세한 내용은 [허용-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f67a6-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="f67a6-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f67a6-148">See Also</span></span>


[<span data-ttu-id="f67a6-149">Lync Server 2013에서 새 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f67a6-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="f67a6-150">Lync Server 2013에서 사용자별 정책 지정</span><span class="sxs-lookup"><span data-stu-id="f67a6-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

