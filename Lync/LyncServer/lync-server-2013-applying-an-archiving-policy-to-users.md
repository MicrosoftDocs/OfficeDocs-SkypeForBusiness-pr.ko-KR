---
title: 'Lync Server 2013: 사용자에 게 보관 정책 적용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1cf0db76b888b9774a16f7a6353ccf1b399eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a><span data-ttu-id="7fe20-102">Lync Server 2013에서 사용자에 게 보관 정책 적용</span><span class="sxs-lookup"><span data-stu-id="7fe20-102">Applying an Archiving policy to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fe20-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7fe20-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7fe20-104">사용자가 Lync Server 2013을 사용 하도록 설정 되어 있고 Lync Server 2013에 속한 사용자에 대해 보관 하기 위해 하나 이상의 사용자 정책을 만든 경우 해당 사용자 또는 사용자 그룹에 적절 한 정책을 적용 하 여 특정 사용자에 대 한 보관 지원을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-104">If a user has been enabled for Lync Server 2013 and you have created one or more user policies for archiving for users homed on Lync Server 2013, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="7fe20-105">예를 들어 내부 통신 보관을 지원 하기 위한 정책을 만들면 사용자의 Lync Server 2013 통신 보관을 지원 하기 위해 하나 이상의 사용자 또는 사용자 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-105">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user’s Lync Server 2013 communications.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7fe20-106">배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 Exchange 원본 위치 유지 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-106">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7fe20-107">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fe20-107">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="7fe20-108">보관을 사용 하도록 설정 하기 전에 보관 구성에서 해당 하는 모든 옵션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="7fe20-109">자세한 내용은 운영 설명서에서 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fe20-109">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="7fe20-110">이 항목의 절차를 사용 하 여 이전에 만든 보관 사용자 정책을 하나 이상의 사용자 계정 또는 사용자 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-110">Use the procedure in this topic to apply a previously created Archiving user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a><span data-ttu-id="7fe20-111">사용자 계정에 보관 사용자 정책을 적용 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-111">To apply an archiving user policy to a user account</span></span>

1.  <span data-ttu-id="7fe20-112">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7fe20-113">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7fe20-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fe20-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7fe20-115">왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 구성 하려는 사용자 계정을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-115">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="7fe20-116">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-116">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7fe20-117">**보관 정책**에서 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-117">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7fe20-118">자동 설정은 기본 서버 설치 설정을 적용 합니다. <STRONG> &lt;&gt; </STRONG></span><span class="sxs-lookup"><span data-stu-id="7fe20-118">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="7fe20-119">이러한 설정은 서버에 의해 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-119">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="7fe20-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7fe20-121">Windows PowerShell Cmdlet을 사용 하 여 사용자별 보관 정책 할당</span><span class="sxs-lookup"><span data-stu-id="7fe20-121">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7fe20-122">사용자 단위 보관 정책은 Windows PowerShell 및 **CsArchivingPolicy** cmdlet을 사용 하 여 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-122">Per-user archiving policies can be assigned by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="7fe20-123">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-123">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7fe20-124">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fe20-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="7fe20-125">단일 사용자에 게 사용자별 보관 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="7fe20-125">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="7fe20-126">다음 명령을 사용 하 여 사용자 단위 보관 정책을 RedmondArchivingPolicy: 진구 Myer에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-126">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="7fe20-127">사용자 단위 보관 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="7fe20-127">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="7fe20-128">이 명령은 등록자 풀 atl-cs-001.litwareinc.com에 속한 계정이 있는 모든 사용자에 대해 사용자별 보관 정책 RedmondArchivingPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-128">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="7fe20-129">이 명령에 사용 된 필터 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fe20-129">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet documentation.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="7fe20-130">사용자별 보관 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="7fe20-130">To assign a per-user archiving policy</span></span>

  - <span data-ttu-id="7fe20-131">다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 보관 정책을 할당 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-131">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="7fe20-132">사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책을 사용 하 여 자동으로 관리 되거나 있는 경우 해당 로컬 사이트 정책이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-132">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="7fe20-133">사이트 정책이 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe20-133">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="7fe20-134">자세한 내용은 [CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fe20-134">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7fe20-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fe20-135">See Also</span></span>


[<span data-ttu-id="7fe20-136">Lync Server 2013의 내부 및 외부 통신 보관 관리</span><span class="sxs-lookup"><span data-stu-id="7fe20-136">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[<span data-ttu-id="7fe20-137">Lync Server 2013에서 사용자별 정책 지정</span><span class="sxs-lookup"><span data-stu-id="7fe20-137">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

