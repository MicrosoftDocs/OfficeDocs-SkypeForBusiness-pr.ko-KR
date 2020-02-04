---
title: 'Lync Server 2013: 사용자 단위 다이얼 플랜 정책 할당'
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
ms.openlocfilehash: f2bc62981a69b1260ba5f2fbaeabc112553b85f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722968"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="38166-102">Lync Server 2013에서 사용자 단위 다이얼 플랜 정책 할당</span><span class="sxs-lookup"><span data-stu-id="38166-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="38166-103">Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대 한 사용자 계정 구성을 완료 하려면 사용자에 게 다이얼 플랜을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-103">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="38166-104">사용자 계정에 글로벌 다이얼 플랜 (있는 경우)이 자동으로 사용 되며, 기존 사용자 단위 다이얼 플랜을 명시적으로 할당 하지 않은 경우에도 사이트 수준 다이얼 플랜입니다.</span><span class="sxs-lookup"><span data-stu-id="38166-104">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="38166-105">Enterprise Voice에 대해 설정 된 모든 사용자에 대해 전역 또는 사이트 다이얼 플랜을 사용 하려는 경우이 섹션을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38166-105">If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="38166-106">Lync Server 2013 제어판을 사용 하 여 다이얼 플랜을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="38166-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="38166-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="38166-108">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="38166-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="38166-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38166-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="38166-110">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="38166-111">**사용자 검색** 상자에 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하도록 설정할 사용자 계정의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="38166-112">테이블에서 다이얼 플랜을 할당할 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="38166-113">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="38166-114">**Lync Server 사용자 편집** 페이지의 **전화 통신**에서 **엔터프라이즈 음성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="38166-115">**다이얼 플랜 정책을**클릭 한 다음 원하는 다이얼 플랜을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="38166-116">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-116">Click **Commit**.</span></span>

<span data-ttu-id="38166-117">다이얼 플랜을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 다이얼 플랜 구성](lync-server-2013-configuring-dial-plans.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38166-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="38166-118">Windows PowerShell Cmdlet을 사용 하 여 사용자 단위 다이얼 플랜 할당</span><span class="sxs-lookup"><span data-stu-id="38166-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="38166-119">Windows PowerShell 및 **권한 부여-csdialplan** cmdlet을 사용 하 여 사용자 단위 다이얼 플랜을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38166-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="38166-120">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38166-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="38166-121">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38166-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="38166-122">사용자 당 다이얼 플랜을 단일 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="38166-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="38166-123">다음 명령은 사용자 단위 다이얼 플랜 RedmondDialPlan을 사용자: 진구 Myer에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="38166-124">사용자 단위 다이얼 플랜을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="38166-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="38166-125">이 명령은 Redmond의 구/군/시를 사용 하는 모든 사용자에 게 사용자 단위 다이얼 플랜 RedmondDialPlan를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="38166-126">이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38166-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="38166-127">사용자 단위 다이얼 플랜을 할당 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="38166-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="38166-128">다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 다이얼 플랜을 할당 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-128">The following command unassigns any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="38166-129">사용자 단위 다이얼 플랜의 할당을 해제 한 후에는 전역 다이얼 플랜, 해당 로컬 사이트 다이얼 플랜 (있는 경우) 또는 해당 레지스트라 또는 PSTN 게이트웨이에 지정 된 서비스 범위 다이얼 플랜을 사용 하 여: 진구 Myer가 자동으로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38166-129">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="38166-130">서비스 범위 다이얼 플랜은 사이트 다이얼 플랜 보다 우선 하므로 사이트 다이얼 플랜은 전역 다이얼 플랜 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="38166-130">A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="38166-131">자세한 내용은 [CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38166-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="38166-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38166-132">See Also</span></span>


[<span data-ttu-id="38166-133">Lync Server 2013에서 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="38166-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="38166-134">Lync Server 2013에 대해 사용 하도록 설정 된 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="38166-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

