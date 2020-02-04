---
title: 'Lync Server 2013: 사용자별 영구 채팅 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 616a171d4aedcc6014ddea3c5993a097d410a5e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722828"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="b50a5-102">Lync Server 2013에서 사용자별 영구 채팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b50a5-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="b50a5-103">Lync Server 2013 제어판 또는 Lync Server 2013 Management Shell을 사용 하 여 사용자 단위 영구 채팅 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="b50a5-104">영구 채팅 서버용 사용자 정책을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 영구 채팅에 대 한 사용자 정책 만들기](lync-server-2013-create-a-user-policy-for-persistent-chat.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b50a5-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="b50a5-105">Lync Server 제어판을 사용 하 여 사용자 단위 영구 채팅 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="b50a5-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b50a5-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b50a5-107">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b50a5-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b50a5-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b50a5-109">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b50a5-110">사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="b50a5-111">사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="b50a5-112">저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="b50a5-113">) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="b50a5-114">**필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="b50a5-115">사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="b50a5-116">다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="b50a5-117">선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b50a5-118">쿼리에 추가 검색 절을 추가 하려면 <STRONG>필터 추가</STRONG>를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="b50a5-119">**찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-119">Click **Find**.</span></span>

6.  <span data-ttu-id="b50a5-120">검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음 **정책 할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="b50a5-121">동일한 사용자별 영구 채팅 정책을 여러 사용자에 게 적용 하려면 검색 결과에서 여러 사용자를 선택한 다음 <STRONG>작업</STRONG>을 클릭 하 고 <STRONG>정책 할당</STRONG>을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="b50a5-122">**정책 할당**의 **영구 채팅 정책**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b50a5-123"><STRONG>정책 할당</STRONG> 대화 상자를 <STRONG> &lt;&gt; </STRONG> 사용 하 여 구성할 수 있는 정책이 여러 개 있기 때문에 대화 상자에 있는 모든 정책에 대해 다음으로 유지 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="b50a5-124">이전에이 설정을 변경 하지 않고 사용자에 게 할당 된 정책을 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="b50a5-125">Lync Server 2013이 전역 수준 정책을 자동으로 선택 하도록 허용 하려면 \*\* \<자동\> \*\* 을 선택 하 고, 정의 하면 사이트 수준 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="b50a5-126">**영구 채팅 정책** 페이지에 이전에 정의한 사용자 단위 영구 채팅 정책의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b50a5-127">할당 하려는 정책을 결정할 수 있도록 정책 이름을 클릭 한 후 <STRONG>보기</STRONG> 를 클릭 하 여 정책에 정의 된 사용자 권한 및 사용 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="b50a5-128">완료 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b50a5-129">Windows PowerShell Cmdlet을 사용 하 여 사용자별 영구 채팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b50a5-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b50a5-130">**CsPersistentChatPolicy** cmdlet을 사용 하 여 사용자별 영구 채팅 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="b50a5-131">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b50a5-132">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b50a5-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="b50a5-133">단일 사용자에 게 사용자별 영구 채팅 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="b50a5-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="b50a5-134">다음 명령을 사용 하 여 사용자 단위 영구 채팅 정책 RedmondPersistentChatPolicy: 진구 Myer에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="b50a5-135">사용자 단위 영구 채팅 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="b50a5-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="b50a5-136">이 명령은 사용자 단위 영구 채팅 정책 RedmondUsersPersistentChatPolicy를 IT 부서에 근무 하는 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="b50a5-137">이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b50a5-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="b50a5-138">사용자별 영구 채팅 정책을 할당 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="b50a5-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="b50a5-139">다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 영구 채팅 정책을 할당 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-139">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="b50a5-140">사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책을 사용 하 여 자동으로 관리 되거나 있는 경우 해당 로컬 사이트 정책이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-140">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="b50a5-141">사이트 정책이 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="b50a5-141">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="b50a5-142">자세한 내용은 [CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b50a5-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="b50a5-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b50a5-143">See Also</span></span>


[<span data-ttu-id="b50a5-144">Lync Server 2013에서 영구 채팅에 대한 사용자 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b50a5-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

