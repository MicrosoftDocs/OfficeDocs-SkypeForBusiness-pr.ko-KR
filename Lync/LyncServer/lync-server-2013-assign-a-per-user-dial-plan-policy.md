---
title: 'Lync Server 2013: 사용자별 다이얼 플랜 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ea17e772bd98501b0d50674a2b82a9abb0e0b38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043710"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="5571e-102">Lync Server 2013에서 사용자별 다이얼 플랜 정책 할당</span><span class="sxs-lookup"><span data-stu-id="5571e-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="5571e-p101">Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대한 사용자 계정 구성을 완료하려면 사용자에게 다이얼 플랜이 할당되어 있어야 합니다. 기존 사용자별 다이얼 플랜을 명시적으로 할당하지 않은 경우 사용자 계정에는 전역 다이얼 플랜 또는 사이트 수준 다이얼 플랜 중에서 이미 있는 항목이 자동으로 사용됩니다. Enterprise Voice를 사용하도록 설정된 모든 사용자에 대해 전역 또는 사이트 다이얼 플랜을 사용하려면 이 섹션을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-p101">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan. User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan. If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="5571e-106">Lync Server 2013 제어판을 사용 하 여 다이얼 플랜을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="5571e-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="5571e-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5571e-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5571e-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5571e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5571e-110">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="5571e-111">**사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="5571e-112">테이블에서 다이얼 플랜을 할당할 사용자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="5571e-113">**편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="5571e-114">**Lync Server 사용자 편집** 페이지의 **전화 통신** 아래에서 **Enterprise Voice**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="5571e-115">**다이얼 플랜 정책**을 클릭한 후 원하는 다이얼 플랜을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="5571e-116">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-116">Click **Commit**.</span></span>

<span data-ttu-id="5571e-117">다이얼 플랜을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 다이얼 플랜 구성](lync-server-2013-configuring-dial-plans.md) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5571e-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5571e-118">Windows PowerShell Cmdlet을 사용 하 여 사용자별 다이얼 플랜 할당</span><span class="sxs-lookup"><span data-stu-id="5571e-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5571e-119">Windows PowerShell 및 **부여-CsdialPlan 플랜** cmdlet을 사용 하 여 사용자별 다이얼 플랜을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="5571e-120">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5571e-121">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5571e-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="5571e-122">단일 사용자에 게 사용자별 다이얼 플랜을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="5571e-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="5571e-123">다음 명령은 사용자 Ken Myer에게 사용자별 다이얼 플랜 RedmondDialPlan을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="5571e-124">여러 사용자에 게 사용자별 다이얼 플랜을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="5571e-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="5571e-125">이 명령은 사용자별 다이얼 플랜 RedmondDialPlan을 Redmond 도시에서 작업하는 모든 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="5571e-126">이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [csuser, user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5571e-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="5571e-127">사용자별 다이얼 플랜을 할당 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="5571e-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="5571e-p105">다음 명령은 Ken Myer에게 이전에 할당된 사용자별 다이얼 플랜을 할당 해제합니다. 사용자별 다이얼 플랜을 할당 해제한 후에는 Ken Myer가 자동으로 전역 다이얼 플랜, 해당 로컬 사이트 플랜(있는 경우) 또는 해당 등록자 또는 PSTN 게이트웨이에 할당된 서비스 범위 다이얼 플랜을 사용하여 관리됩니다. 사이트 다이얼 플랜이 전역 다이얼 플랜보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="5571e-p105">The following command unassigns any per-user dial plan previously assigned to Ken Myer. After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway. A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="5571e-131">자세한 내용은 [부여-CsDialPlan 플랜](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5571e-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="5571e-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5571e-132">See Also</span></span>


[<span data-ttu-id="5571e-133">Lync Server 2013에서 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="5571e-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="5571e-134">Lync Server 2013에 사용할 수 있는 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="5571e-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

