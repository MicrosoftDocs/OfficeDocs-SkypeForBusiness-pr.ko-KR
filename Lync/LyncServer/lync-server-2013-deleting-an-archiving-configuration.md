---
title: 'Lync Server 2013: 보관 구성 삭제'
description: 'Lync Server 2013: 보관 구성을 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb267c119b49c9bbf06f365c3bdf2cbab459628
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575814"
---
# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a><span data-ttu-id="76612-103">Lync Server 2013에서 보관 구성 삭제</span><span class="sxs-lookup"><span data-stu-id="76612-103">Deleting an Archiving configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76612-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="76612-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="76612-105">사이트 구성 또는 풀 구성은 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76612-105">You can delete a site configuration or pool configuration.</span></span> <span data-ttu-id="76612-106">전역 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76612-106">The global configuration cannot be removed.</span></span> <span data-ttu-id="76612-107">전역 구성을 삭제하는 경우 자동으로 구성이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="76612-107">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="76612-108">지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성이 구현 되는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76612-108">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a><span data-ttu-id="76612-109">보관을 위해 사이트 또는 풀 구성을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="76612-109">To delete a site or pool configuration for archiving</span></span>

1.  <span data-ttu-id="76612-110">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="76612-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="76612-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="76612-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="76612-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76612-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="76612-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="76612-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="76612-114">보관 구성 목록에서 삭제할 사이트 또는 풀 구성을 클릭하고 **편집**을 클릭한 다음 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="76612-114">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="76612-115">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="76612-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="76612-116">Windows PowerShell Cmdlet을 사용 하 여 보관 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="76612-116">Removing Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="76612-117">보관 구성 설정은 Windows PowerShell 및 **get-csarchivingconfiguration** cmdlet을 사용 하 여 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76612-117">Archiving configuration settings can be deleted by using Windows PowerShell and the **Remove-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="76612-118">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76612-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="76612-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="76612-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a><span data-ttu-id="76612-120">지정 된 보관 구성 설정 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="76612-120">To remove a specified collection of archiving configuration settings</span></span>

  - <span data-ttu-id="76612-121">다음 명령은 Redmond 사이트에 적용된 보관 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="76612-121">The following command removes the archiving configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="76612-122">사이트 범위에 적용 된 모든 보관 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="76612-122">To remove all the archiving configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="76612-123">다음 명령은 서비스 범위에 적용된 모든 보관 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="76612-123">This command removes all the archiving configuration settings applied to the service scope:</span></span>
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a><span data-ttu-id="76612-124">지정 된 속성 값을 기반으로 보관 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="76612-124">To remove archiving configuration settings based on a specified property value</span></span>

  - <span data-ttu-id="76612-125">다음 명령은 Exchange 보관을 사용할 수 없도록 설정된 모든 보관 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="76612-125">This command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

<span data-ttu-id="76612-126">자세한 내용은 [get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76612-126">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76612-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76612-127">See Also</span></span>


[<span data-ttu-id="76612-128">Lync Server 2013에서 보관이 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="76612-128">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="76612-129">Lync Server 2013에서 내부 및 외부 통신의 보관 관리</span><span class="sxs-lookup"><span data-stu-id="76612-129">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

