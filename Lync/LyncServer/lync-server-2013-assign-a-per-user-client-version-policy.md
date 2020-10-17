---
title: 'Lync Server 2013: 사용자별 클라이언트 버전 정책을 할당 합니다.'
description: 'Lync Server 2013: 사용자별 클라이언트 버전 정책을 할당 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec2fcbf9c005806a97dfbdceb22095fe0ff8f33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559984"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="9c56a-103">Lync Server 2013에서 사용자별 클라이언트 버전 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9c56a-103">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="9c56a-104">클라이언트 버전 정책은 Lync Server 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-104">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="9c56a-105">하나 이상의 사용자별 클라이언트 버전 정책을 배포하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-105">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="9c56a-106">전역 수준 클라이언트 버전 정책이나 사이트 수준 또는 풀 수준 클라이언트 버전 정책만 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-106">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="9c56a-107">사용자별 정책을 배포하는 경우에는 해당 정책을 사용자, 그룹 또는 연락처 개체에 명시적으로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-107">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="9c56a-108">특정 사이트 수준, 풀 수준 또는 사용자별 정책이 할당 되지 않은 경우 Lync Server 2013에서 등록할 수 있는 기본 클라이언트는 전역 수준 클라이언트 버전 정책에 정의 된 것과 같은 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-108">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="9c56a-109">하나 이상의 사용자별 클라이언트 버전 정책을 만든 후이 항목의 절차를 사용 하 여 Lync Server에 등록 하도록 허용할 클라이언트 버전을 지정 하는 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-109">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="9c56a-110">사용자별 클라이언트 버전 정책을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에 로그온 하는 데 사용할 수 있는 클라이언트 응용 프로그램 지정](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9c56a-110">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="9c56a-111">사용자별 클라이언트 버전 정책을 할당하려면</span><span class="sxs-lookup"><span data-stu-id="9c56a-111">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="9c56a-112">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9c56a-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9c56a-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9c56a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9c56a-115">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9c56a-116">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="9c56a-117">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="9c56a-118">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="9c56a-119">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="9c56a-120">**필터 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="9c56a-121">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="9c56a-122">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="9c56a-123">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="9c56a-124">쿼리에 검색 절을 더 추가하려면 <STRONG>필터 추가</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="9c56a-125">**찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-125">Click **Find**.</span></span>

6.  <span data-ttu-id="9c56a-126">검색 결과에서 사용자를 클릭하고 **동작**을 클릭한 후에 **정책 할당**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="9c56a-127">여러 사용자에게 동일한 사용자별 클라이언트 버전 정책을 적용하려면 검색 결과에서 여러 사용자를 선택한 후 <STRONG>동작</STRONG>, <STRONG>정책 할당</STRONG>을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-127">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="9c56a-128">**정책 할당**의 **클라이언트 버전 정책**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-128">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="9c56a-129"><STRONG>정책 할당</STRONG> 대화 <STRONG>상자를 &lt; &gt; 사용</STRONG> 하 여 구성할 수 있는 정책이 여러 개 있으므로 대화 상자의 모든 정책에 대해 다음 사용자가 기본적으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="9c56a-130">이 설정을 변경하지 않으면 이전에 사용자에게 지정된 정책이 계속 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="9c56a-131">Lync Server에서 전역 수준 정책을 자동으로 선택 하도록 허용 하거나, 정의 된 경우 사이트 수준 정책 또는 풀 수준 정책</span><span class="sxs-lookup"><span data-stu-id="9c56a-131">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="9c56a-132">**클라이언트 버전 정책** 페이지에서 이전에 정의한 사용자별 클라이언트 버전 정책의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-132">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="9c56a-133">할당할 정책을 쉽게 결정하려면 정책 이름을 클릭한 후 <STRONG>보기</STRONG>를 클릭하여 정책에 정의된 사용자 권한 및 권한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="9c56a-134">작업을 마치면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9c56a-135">Windows PowerShell Cmdlet을 사용 하 여 Per-User 클라이언트 버전 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9c56a-135">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9c56a-136">Grant-CsClientVersionPolicy cmdlet을 사용하여 사용자별 클라이언트 버전 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-136">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="9c56a-137">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-137">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9c56a-138">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c56a-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="9c56a-139">사용자별 클라이언트 버전 정책을 단일 사용자에게 할당하려면</span><span class="sxs-lookup"><span data-stu-id="9c56a-139">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="9c56a-140">다음 명령은 사용자별 클라이언트 버전 정책인 RedmondClientVersionPolicy를 사용자 Ken Myer에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-140">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="9c56a-141">사용자별 클라이언트 버전 정책을 여러 사용자에게 할당하려면</span><span class="sxs-lookup"><span data-stu-id="9c56a-141">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="9c56a-142">이 명령은 사용자별 클라이언트 버전 정책인 RedmondClientVersionPolicy를 현재 음성 정책인 RedmondVoicePolicy가 할당되어 있는 모든 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-142">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="9c56a-143">이 명령에 사용 되는 Filter 매개 변수에 대 한 자세한 내용은 [csuser S\user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet의 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9c56a-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="9c56a-144">사용자별 클라이언트 버전 정책 할당을 해제하려면</span><span class="sxs-lookup"><span data-stu-id="9c56a-144">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="9c56a-p106">다음 명령은 Ken Myer에게 이전에 할당된 사용자별 클라이언트 버전 정책 할당을 해제합니다. 사용자별 정책 할당이 해제된 후에는 글로벌 정책, 로컬 사이트 정책(있는 경우) 또는 고급 등록자에 할당된 서비스 범위 정책을 사용하여 Ken Myer가 자동으로 관리됩니다. 서비스 범위 정책을 사이트 정책보다 우선하며 사이트 정책을 글로벌 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="9c56a-p106">The following command unassigns any per-user client version policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar. A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="9c56a-148">자세한 내용은 [부여-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9c56a-148">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c56a-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c56a-149">See Also</span></span>


[<span data-ttu-id="9c56a-150">Lync Server 2013에서 사용자별 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9c56a-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="9c56a-151">Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="9c56a-151">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

