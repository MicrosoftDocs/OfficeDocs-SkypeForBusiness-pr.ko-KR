---
title: 'Lync Server 2013: 보관 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f151a940958273509191b35ed817409ba52b6dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="7f889-102">Lync Server 2013에서 보관 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="7f889-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f889-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7f889-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7f889-104">사용자 정책 또는 사이트 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="7f889-105">전역 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-105">The global policy cannot be removed.</span></span> <span data-ttu-id="7f889-106">전역 정책을 삭제 하려고 하면 Lync Server 2013에서 자동으로 정책을 기본값으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f889-107">배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 Exchange 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7f889-108">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f889-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="7f889-109">보관을 위해 사용자 또는 사이트 정책을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="7f889-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="7f889-110">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7f889-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7f889-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f889-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7f889-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="7f889-114">보관 정책 목록에서 삭제 하려는 사용자 또는 사이트 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="7f889-115">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7f889-116">Windows PowerShell Cmdlet을 사용 하 여 보관 정책 제거</span><span class="sxs-lookup"><span data-stu-id="7f889-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7f889-117">Windows PowerShell 및 **CsArchivingPolicy** cmdlet을 사용 하 여 보관 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="7f889-118">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7f889-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f889-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="7f889-120">지정 된 보관 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="7f889-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="7f889-121">예를 들어, **CsArchivingPolicy** 는 id 사이트: Redmond를 사용 하 여 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-121">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="7f889-122">사이트 범위에서 구성 된 정책을 삭제 하는 경우 이전에 사이트 정책에서 관리 하는 사용자는 전역 보관 정책에 의해 자동으로 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-122">Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead.</span></span> <span data-ttu-id="7f889-123">다음 명령은 Redmond 사이트에 적용 된 보관을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-123">The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="7f889-124">사용자별 범위에 적용 된 모든 보관 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="7f889-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="7f889-125">이 명령은 사용자별 범위에 적용 된 모든 보관 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="7f889-126">내부 보관을 사용 하지 않도록 설정 하는 모든 보관 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="7f889-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="7f889-127">이 명령은 내부 보관을 사용 하지 않도록 설정한 모든 보관 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f889-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="7f889-128">자세한 내용은 [제거 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f889-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f889-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f889-129">See Also</span></span>


[<span data-ttu-id="7f889-130">Lync Server 2013의 내부 및 외부 통신 보관 관리</span><span class="sxs-lookup"><span data-stu-id="7f889-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

