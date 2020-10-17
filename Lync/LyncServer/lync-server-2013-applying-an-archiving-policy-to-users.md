---
title: 'Lync Server 2013: 사용자에 게 보관 정책 적용'
description: 'Lync Server 2013: 사용자에 게 보관 정책 적용'
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
ms.openlocfilehash: 54b82a68a75da7b389167097d8b08358cf680e1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544974"
---
# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a><span data-ttu-id="920fb-103">Lync Server 2013의 사용자에 게 보관 정책 적용</span><span class="sxs-lookup"><span data-stu-id="920fb-103">Applying an Archiving policy to users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="920fb-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="920fb-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="920fb-105">사용자가 Lync Server 2013를 사용할 수 있도록 설정 되어 있고 Lync Server 2013에 있는 사용자에 대해 보관 하기 위한 사용자 정책을 하나 이상 만든 경우 해당 사용자 또는 사용자 그룹에 적절 한 정책을 적용 하 여 특정 사용자에 대 한 보관 지원을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-105">If a user has been enabled for Lync Server 2013 and you have created one or more user policies for archiving for users homed on Lync Server 2013, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="920fb-106">예를 들어 내부 통신 보관을 지원 하기 위한 정책을 만드는 경우 사용자의 Lync Server 2013 통신 보관을 지원 하기 위해 하나 이상의 사용자 또는 사용자 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user’s Lync Server 2013 communications.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="920fb-107">배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정 하 고 사서함을 In-Place 보류에 In-Place 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="920fb-108">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="920fb-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="920fb-109">보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="920fb-110">자세한 내용은 작업 설명서에서 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="920fb-110">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="920fb-111">이 항목의 절차를 사용하여 이전에 만든 보관 사용자 정책을 하나 이상의 사용자 계정 또는 사용자 그룹에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-111">Use the procedure in this topic to apply a previously created Archiving user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a><span data-ttu-id="920fb-112">사용자 계정에 보관 사용자 정책을 적용하려면</span><span class="sxs-lookup"><span data-stu-id="920fb-112">To apply an archiving user policy to a user account</span></span>

1.  <span data-ttu-id="920fb-113">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="920fb-114">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="920fb-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="920fb-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="920fb-116">왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성하려는 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-116">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="920fb-117">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-117">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="920fb-118">**보관 정책**아래의 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-118">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="920fb-119"><STRONG> &lt; 자동 &gt; </STRONG> 설정은 기본 서버 설치 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-119">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="920fb-120">이러한 설정은 서버에 의해 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-120">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="920fb-121">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="920fb-122">Windows PowerShell Cmdlet을 사용 하 여 Per-User 보관 정책 할당</span><span class="sxs-lookup"><span data-stu-id="920fb-122">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="920fb-123">사용자 단위 보관 정책은 Windows PowerShell 및 **grant-csarchivingpolicy** cmdlet을 사용 하 여 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-123">Per-user archiving policies can be assigned by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="920fb-124">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-124">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="920fb-125">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="920fb-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="920fb-126">단일 사용자에 게 사용자별 보관 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="920fb-126">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="920fb-127">다음 명령은 사용자별 보관 정책 RedmondArchivingPolicy를 Ken Myer라는 사용자에게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-127">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="920fb-128">사용자별 보관 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="920fb-128">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="920fb-129">이 명령은 사용자별 보관 정책 RedmondArchivingPolicy를 계정이 등록자 풀 atl-cs-001.litwareinc.com에 있는 모든 사용자에게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-129">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="920fb-130">이 명령에 사용 된 Filter 매개 변수에 대 한 자세한 내용은 [csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) c i c c i c c a c c-설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="920fb-130">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet documentation.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="920fb-131">사용자별 보관 정책을 할당하려면</span><span class="sxs-lookup"><span data-stu-id="920fb-131">To assign a per-user archiving policy</span></span>

  - <span data-ttu-id="920fb-p108">다음 명령은 이전에 Ken Myer에게 지정되었던 사용자별 보관 정책의 지정을 해제합니다. 사용자별 정책을 지정 해제한 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용해서 관리됩니다. 사이트 정책은 글로벌 정책보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="920fb-p108">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="920fb-135">자세한 내용은 [grant-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="920fb-135">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="920fb-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="920fb-136">See Also</span></span>


[<span data-ttu-id="920fb-137">Lync Server 2013에서 내부 및 외부 통신의 보관 관리</span><span class="sxs-lookup"><span data-stu-id="920fb-137">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[<span data-ttu-id="920fb-138">Lync Server 2013에서 사용자별 정책 할당</span><span class="sxs-lookup"><span data-stu-id="920fb-138">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

