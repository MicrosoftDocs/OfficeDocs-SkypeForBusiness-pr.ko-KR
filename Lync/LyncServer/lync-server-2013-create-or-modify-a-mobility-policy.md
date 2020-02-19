---
title: 'Lync Server 2013: 모바일 정책 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4246569ad7d66788cef507488b78567b6b892f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="02d3f-102">Lync Server 2013에서 모바일 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="02d3f-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02d3f-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="02d3f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="02d3f-104">모바일 사용자가 IM(인스턴트 메시징), 현재 상태 및 연락처 등 Lync 기능용으로 지원되는 모바일 장치를 사용할 수 있도록 모바일 정책을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="02d3f-105">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 모바일 정책을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="02d3f-106">Lync Server 제어판을 사용 하 여 모바일 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="02d3f-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="02d3f-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02d3f-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="02d3f-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="02d3f-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="02d3f-110">왼쪽 탐색 표시줄에서 **클라이언트**를 클릭하고 **모바일 정책** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="02d3f-111">**모바일 정책** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="02d3f-112">사이트 모바일 정책을 만들려면 **사이트 정책**을 클릭하고 사이트 하나를 클릭한 다음 **확인**을 클릭하고 기본 설정을 검토한 후 원할 경우 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="02d3f-113">사용자 모바일 정책을 만들려면 **사용자 정책**을 클릭하고 이름 하나를 입력한 다음 기본 설정을 검토한 후 원할 경우 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="02d3f-114">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="02d3f-115">Lync Server 제어판을 사용 하 여 모바일 정책을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="02d3f-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="02d3f-116">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02d3f-117">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="02d3f-118">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="02d3f-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="02d3f-119">왼쪽 탐색 표시줄에서 **클라이언트**를 클릭하고 **모바일 정책** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="02d3f-120">**모바일 정책** 페이지에서 기존 모바일 정책 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="02d3f-121">**편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="02d3f-122">설정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="02d3f-123">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="02d3f-124">Windows PowerShell Cmdlet을 사용 하 여 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="02d3f-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="02d3f-125">Windows PowerShell 및 **get-csmobilitypolicy** cmdlet을 사용 하 여 사이트 범위 또는 사용자별 범위에서 모바일 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="02d3f-126">또한 **get-csmobilitypolicy** cmdlet을 사용 하 여 전역 정책을 비롯 한 기존 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="02d3f-127">이러한 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="02d3f-128">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="02d3f-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="02d3f-129">사이트 범위에서 모바일 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="02d3f-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="02d3f-130">이 명령은 Redmond 사이트에 대한 새로운 모바일 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="02d3f-131">이전 명령에 매개 변수(필수 Identity 매개 변수 이외)가 지정되지 않았으므로 정책에서 모든 속성에 대해 기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="02d3f-132">사용자별 범위에서 모바일 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="02d3f-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="02d3f-133">사용자별 범위에서 모바일 정책을 만들려면 정책에 대한 고유 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="02d3f-134">모바일 정책을 만들 때 단일 속성 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="02d3f-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="02d3f-p105">다양한 속성 값을 사용하는 정책을 만들려면 해당 매개 변수 및 매개 변수 값을 포함합니다. 예를 들면 이 명령은 회사번호로 전화 기능을 사용하지 않도록 설정하는 모바일 정책을 만듭니다.:</span><span class="sxs-lookup"><span data-stu-id="02d3f-p105">To create policies that use different property values, include the appropriate parameter and parameter value. For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="02d3f-137">모바일 정책을 만들 때 여러 속성 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="02d3f-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="02d3f-p106">여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들면 이 명령은 모바일 및 회사번호로 전화 기능을 둘 다 사용하지 않도록 설정하는 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02d3f-p106">Multiple property values can be modified by including multiple parameters. For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="02d3f-140">자세한 내용은 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) 및 [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlet 관련 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="02d3f-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02d3f-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02d3f-141">See Also</span></span>


[<span data-ttu-id="02d3f-142">Lync Server 2013에서 모바일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="02d3f-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

