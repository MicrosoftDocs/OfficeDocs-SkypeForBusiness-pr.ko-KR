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
ms.openlocfilehash: 335f14018e9e489dbb6ca4db5a4d6138eb330faf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030131"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="64014-102">Lync Server 2013에서 사용자별 영구 채팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="64014-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="64014-103">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 사용자별 영구 채팅 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64014-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="64014-104">영구 채팅 서버에 대 한 사용자 정책을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 영구 채팅에 대 한 사용자 정책 만들기](lync-server-2013-create-a-user-policy-for-persistent-chat.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64014-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="64014-105">Lync Server 제어판을 사용 하 여 사용자별 영구 채팅 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="64014-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="64014-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="64014-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="64014-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="64014-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64014-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="64014-109">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="64014-110">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="64014-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="64014-111">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="64014-112">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="64014-113">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="64014-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="64014-114">**필터 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="64014-115">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="64014-116">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="64014-117">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="64014-118">쿼리에 검색 절을 더 추가하려면 <STRONG>필터 추가</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="64014-119">**찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-119">Click **Find**.</span></span>

6.  <span data-ttu-id="64014-120">검색 결과에서 사용자를 클릭하고 **동작**을 클릭한 후 **정책 할당**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="64014-121">동일한 사용자별 영구 채팅 정책을 여러 사용자에게 적용하려면 검색 결과에서 여러 사용자를 선택하고 <STRONG>동작</STRONG>을 클릭한 다음 <STRONG>정책 할당</STRONG>을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="64014-122">**정책 할당**의 **영구 채팅 정책(Persistent Chat policy)** 아래에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="64014-123"><STRONG>정책 할당</STRONG> 대화 <STRONG> &lt;상자를&gt; 사용</STRONG> 하 여 구성할 수 있는 정책이 여러 개 있으므로 대화 상자의 모든 정책에 대해 다음 사용자가 기본적으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64014-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="64014-124">이 설정을 변경하지 않으면 이전에 사용자에게 지정된 정책이 계속 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="64014-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="64014-125">Lync Server 2013에서 전역 수준 정책을 자동으로 선택 하도록 허용 하려면 \*\* \<자동\> \*\* 을 선택 하 고 사이트 수준 정책을 정의 하는 경우</span><span class="sxs-lookup"><span data-stu-id="64014-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="64014-126">**영구 채팅 정책(Persistent Chat Policy)** 페이지에서 이전에 정의한 사용자별 영구 채팅 정책의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="64014-127">할당할 정책을 쉽게 결정하려면 정책 이름을 클릭한 후 <STRONG>보기</STRONG>를 클릭하여 정책에 정의된 사용자 권한 및 권한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="64014-128">작업을 마치면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="64014-129">Windows PowerShell Cmdlet을 사용 하 여 사용자별 영구 채팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="64014-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="64014-130">**Grant-cspersistentchatpolicy** cmdlet을 사용 하 여 사용자별 영구 채팅 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64014-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="64014-131">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64014-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="64014-132">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64014-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="64014-133">단일 사용자에 게 사용자별 영구 채팅 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="64014-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="64014-134">다음 명령은 사용자별 영구 채팅 정책인 RedmondPersistentChatPolicy를 사용자 Ken Myer에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="64014-135">사용자별 영구 채팅 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="64014-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="64014-136">이 명령은 영구 채팅 정책인 RedmondUsersPersistentChatPolicy를 IT 부서에서 근무하는 모든 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="64014-137">이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [csuser, user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64014-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="64014-138">사용자별 영구 채팅 정책을 할당 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="64014-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="64014-p106">다음 명령은 Ken Mayer에게 이전에 할당된 사용자별 영구 채팅 정책을 할당 해제합니다. 사용자별 영구 채팅이 할당 해제된 후 Ken Myer는 자동으로 글로벌 정책이나 로컬 사이트 정책(있는 경우)을 사용하여 관리됩니다. 사이트 정책이 글로벌 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="64014-p106">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="64014-142">자세한 내용은 [grant-cspersistentchatpolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64014-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="64014-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64014-143">See Also</span></span>


[<span data-ttu-id="64014-144">Lync Server 2013의 영구 채팅에 대 한 사용자 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="64014-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

