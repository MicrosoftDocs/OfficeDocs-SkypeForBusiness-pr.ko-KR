---
title: 'Lync Server 2013: 사용자별 모바일 정책을 할당 합니다.'
description: 'Lync Server 2013: 사용자별 모바일 정책을 할당 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b17c58cf3477002a7fa43035b72c77963663316
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559834"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="2470a-103">Lync Server 2013에서 사용자별 모바일 정책 할당</span><span class="sxs-lookup"><span data-stu-id="2470a-103">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="2470a-104">모바일 정책은 Lync Server 제어판 또는 Lync Server 관리 셸에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-104">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="2470a-105">Lync Server 제어판을 사용 하 여 사용자별 모바일 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="2470a-105">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2470a-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2470a-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2470a-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2470a-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2470a-109">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="2470a-110">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="2470a-111">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="2470a-112">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="2470a-113">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="2470a-114">**필터 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="2470a-115">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="2470a-116">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="2470a-117">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="2470a-118">쿼리에 검색 절을 더 추가하려면 <STRONG>필터 추가</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="2470a-119">**찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-119">Click **Find**.</span></span>

6.  <span data-ttu-id="2470a-120">검색 결과에서 사용자를 클릭하고 **동작**을 클릭한 후에 **정책 할당**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="2470a-121">여러 사용자에게 동일한 사용자별 모바일 정책을 적용하려면 검색 결과에서 여러 사용자를 선택한 후 <STRONG>동작</STRONG>, <STRONG>정책 할당</STRONG>을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-121">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="2470a-122">**정책 할당**의 **모바일 정책**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-122">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="2470a-123"><STRONG>Assign Policies</STRONG> <STRONG> &lt; 정책 &gt; </STRONG> 할당에서 구성할 수 있는 정책이 여러 개 있으므로 대화 상자의 모든 정책에 대해 다음 사용자가 기본적으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-123">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="2470a-124">이 설정을 변경하지 않으면 이전에 사용자에게 지정된 정책이 계속 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="2470a-125">**\<Automatic\>** Lync Server 2013이 전역 수준 정책을 자동으로 선택 하도록 허용 하려면 (정의 된 경우), 사이트 수준 정책</span><span class="sxs-lookup"><span data-stu-id="2470a-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="2470a-126">**모바일 정책** 페이지에서 이전에 정의한 사용자별 모바일 정책의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-126">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="2470a-127">할당할 정책을 쉽게 결정하려면 정책 이름을 클릭한 후 <STRONG>보기</STRONG>를 클릭하여 정책에 정의된 사용자 권한 및 권한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="2470a-128">작업을 마치면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2470a-129">Windows PowerShell Cmdlet을 사용 하 여 Per-User 모바일 정책 할당</span><span class="sxs-lookup"><span data-stu-id="2470a-129">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2470a-130">Windows PowerShell 및 **get-csmobilitypolicy** cmdlet을 사용 하 여 사용자별 모바일 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-130">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="2470a-131">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-131">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2470a-132">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="2470a-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="2470a-133">단일 사용자에게 사용자별 모바일 정책을 할당하려면</span><span class="sxs-lookup"><span data-stu-id="2470a-133">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="2470a-134">다음 명령을 실행하면 사용자별 모바일 정책인 RedmondMobilityPolicy를 사용자 Ken Myer에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-134">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="2470a-135">여러 사용자에게 사용자별 모바일 정책을 할당하려면</span><span class="sxs-lookup"><span data-stu-id="2470a-135">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="2470a-136">다음 명령을 실행하면 NorthAmericaMobilityPolicy 정책을 현재 할당받은 모든 사용자에게 사용자별 모바일 정책인 RedmondMobilityPolicy가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-136">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="2470a-137">이 명령에 사용 된 Filter 매개 변수에 대 한 자세한 내용은 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2470a-137">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="2470a-138">사용자별 모바일 정책을 할당 해제하려면</span><span class="sxs-lookup"><span data-stu-id="2470a-138">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="2470a-p105">다음 명령을 실행하면 이전에 Ken Myer에게 할당한 사용자별 모바일 정책을 할당 해제할 수 있습니다. 사용자별 정책을 할당 해제한 후 Ken Myer는 자동으로 전역 정책을 사용하여 관리되거나 로컬 사이트 정책이 있는 경우 로컬 사이트 정책으로 관리됩니다. 사이트 정책은 전역 정책보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2470a-p105">The following command unassigns any per-user mobility policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="2470a-142">자세한 내용은 [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\))를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2470a-142">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="2470a-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2470a-143">See Also</span></span>


[<span data-ttu-id="2470a-144">Lync Server 2013에서 모바일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="2470a-144">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

