---
title: 'Lync Server 2013: 사용자 단위 클라이언트 버전 정책 할당'
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
ms.openlocfilehash: e509427b6d2651f84b96a96c87fbe7cfd6177a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738378"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="a3c38-102">Lync Server 2013에서 사용자 단위 클라이언트 버전 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a3c38-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="a3c38-103">클라이언트 버전 정책은 Lync Server 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="a3c38-104">하나 이상의 사용자 단위 클라이언트 버전 정책을 배포 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="a3c38-105">전역 수준의 클라이언트 버전 정책 또는 사이트 수준 또는 풀 수준의 클라이언트 버전 정책만 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="a3c38-106">사용자별 정책을 배포 하는 경우 사용자, 그룹 또는 연락처 개체에 명시적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="a3c38-107">특정 사이트 수준, 풀 수준 또는 사용자 단위 정책이 할당 되지 않은 경우 Lync Server 2013에서 등록할 수 있는 기본 클라이언트는 전역 수준의 클라이언트 버전 정책에 정의 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="a3c38-108">하나 이상의 사용자 단위 클라이언트 버전 정책을 만든 후에는이 항목의 절차를 사용 하 여 Lync Server에 등록할 수 있도록 허용 하려는 클라이언트 버전을 지정 하는 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="a3c38-109">사용자 단위 클라이언트 버전 정책을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에 로그온 하는 데 사용할 수 있는 클라이언트 응용 프로그램 지정](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3c38-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="a3c38-110">사용자별 클라이언트 버전 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="a3c38-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="a3c38-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a3c38-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a3c38-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3c38-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a3c38-114">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="a3c38-115">사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="a3c38-116">사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="a3c38-117">저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="a3c38-118">) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="a3c38-119">**필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="a3c38-120">사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="a3c38-121">다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="a3c38-122">선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="a3c38-123">쿼리에 추가 검색 절을 추가 하려면 <STRONG>필터 추가</STRONG>를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="a3c38-124">**찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-124">Click **Find**.</span></span>

6.  <span data-ttu-id="a3c38-125">검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음 **정책 할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="a3c38-126">동일한 사용자별 클라이언트 버전 정책을 여러 사용자에 게 적용 하려면 검색 결과에서 여러 사용자를 선택한 다음 <STRONG>작업</STRONG>을 클릭 하 고 <STRONG>정책 할당</STRONG>을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="a3c38-127">**지정 정책**에서 **클라이언트 버전 정책**아래에 있는 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="a3c38-128"><STRONG>정책 할당</STRONG> 대화 상자를 <STRONG> &lt;&gt; </STRONG> 사용 하 여 구성할 수 있는 정책이 여러 개 있기 때문에 대화 상자에 있는 모든 정책에 대해 다음으로 유지 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="a3c38-129">이전에이 설정을 변경 하지 않고 사용자에 게 할당 된 정책을 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="a3c38-130">Lync Server가 전역 수준 정책을 자동으로 선택 하도록 허용 하거나 정의 된 경우 사이트 수준 정책 또는 풀 수준 정책 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="a3c38-131">이전에 **클라이언트 버전 정책** 페이지에 정의한 사용자 단위 클라이언트 버전 정책의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="a3c38-132">할당 하려는 정책을 결정할 수 있도록 정책 이름을 클릭 한 후 <STRONG>보기</STRONG> 를 클릭 하 여 정책에 정의 된 사용자 권한 및 사용 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="a3c38-133">완료 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a3c38-134">Windows PowerShell Cmdlet을 사용 하 여 사용자 단위 클라이언트 버전 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a3c38-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a3c38-135">허용-CsClientVersionPolicy cmdlet을 사용 하 여 사용자별 클라이언트 버전 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="a3c38-136">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a3c38-137">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3c38-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="a3c38-138">사용자 단위 클라이언트 버전 정책을 단일 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="a3c38-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="a3c38-139">다음 명령을 사용 하 여 사용자: 진구 Myer에 사용자 단위 클라이언트 버전 정책 RedmondClientVersionPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="a3c38-140">사용자 단위 클라이언트 버전 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="a3c38-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="a3c38-141">이 명령은 사용자 단위 클라이언트 버전 정책 RedmondClientVersionPolicy를 현재 음성 정책 RedmondVoicePolicy에 할당 된 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="a3c38-142">이 명령에 사용 된 필터 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3c38-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="a3c38-143">사용자별 클라이언트 버전 정책을 할당 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="a3c38-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="a3c38-144">다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 클라이언트 버전 정책을 할당 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-144">The following command unassigns any per-user client version policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="a3c38-145">사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책, 해당 로컬 사이트 정책 (있는 경우) 또는 해당 등록자에 게 할당 된 서비스 범위 정책을 사용 하 여 자동으로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar.</span></span> <span data-ttu-id="a3c38-146">서비스 범위 정책은 모든 사이트 정책에 우선 하므로 사이트 정책이 전역 정책에 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c38-146">A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="a3c38-147">자세한 내용은 [권한 부여-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3c38-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3c38-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3c38-148">See Also</span></span>


[<span data-ttu-id="a3c38-149">Lync Server 2013에서 사용자별 정책 지정</span><span class="sxs-lookup"><span data-stu-id="a3c38-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="a3c38-150">Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="a3c38-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

