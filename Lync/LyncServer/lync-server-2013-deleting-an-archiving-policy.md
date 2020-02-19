---
title: 'Lync Server 2013: 보관 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cac48287063e61be00495077f51042b1810f65
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="6a620-102">Lync Server 2013에서 보관 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="6a620-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a620-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6a620-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6a620-104">사용자 정책 또는 사이트 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="6a620-105">전역 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-105">The global policy cannot be removed.</span></span> <span data-ttu-id="6a620-106">글로벌 정책을 삭제 하려고 하면 Lync Server 2013에서 정책을 기본값으로 자동으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a620-107">배포에 Microsoft Exchange 통합을 사용 하도록 설정 하면 Exchange 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정할지 여부를 제어 하 고 사서함을 원본 위치 유지 상태로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="6a620-108">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a620-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="6a620-109">보관을 위해 사용자 또는 사이트 정책을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="6a620-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="6a620-110">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6a620-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6a620-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a620-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6a620-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="6a620-114">보관 정책 목록에서 삭제하려는 사용자 또는 사이트 정책을 클릭하고, **편집**을 클릭한 후 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="6a620-115">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6a620-116">Windows PowerShell Cmdlet을 사용 하 여 보관 정책 제거</span><span class="sxs-lookup"><span data-stu-id="6a620-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6a620-117">Windows PowerShell 및 **grant-csarchivingpolicy** cmdlet을 사용 하 여 보관 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="6a620-118">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6a620-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a620-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="6a620-120">지정 된 보관 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="6a620-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="6a620-p105">한 예로, **Remove-CsArchivingPolicy**는 Identity가 site:Redmond인 정책을 삭제합니다. 사이트 범위로 구성된 정책을 삭제하면 해당 사이트 정책으로 이전에 관리되던 사용자가 자동으로 이전 정책 대신 전역 보관 정책에 의해 제어됩니다. 다음 명령은 Redmond 사이트에 적용된 보관 기능을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-p105">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond. Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead. The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="6a620-124">사용자별 범위에 적용 된 모든 보관 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="6a620-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="6a620-125">이 명령은 사용자별 범위에 적용된 모든 보관 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="6a620-126">내부 보관을 사용 하지 않도록 설정 하는 모든 보관 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="6a620-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="6a620-127">이 명령은 내부 보관이 해제된 모든 보관 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6a620-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="6a620-128">자세한 내용은 [grant-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a620-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6a620-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a620-129">See Also</span></span>


[<span data-ttu-id="6a620-130">Lync Server 2013에서 내부 및 외부 통신의 보관 관리</span><span class="sxs-lookup"><span data-stu-id="6a620-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

