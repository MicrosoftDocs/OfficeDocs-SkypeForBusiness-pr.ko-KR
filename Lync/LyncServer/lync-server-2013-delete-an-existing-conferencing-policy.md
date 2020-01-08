---
title: 'Lync Server 2013: 기존 회의 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3571c7b731579c0397da62d2c5805be19dcfa809
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="8fd78-102">Lync Server 2013에서 기존 회의 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="8fd78-102">Delete an existing conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fd78-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8fd78-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8fd78-104">사용자 수준 또는 사이트 수준 회의 정책을 삭제 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="8fd78-104">Follow these steps to delete a user-level or a site-level conferencing policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8fd78-105">전역 회의 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd78-105">You cannot delete the global conferencing policy.</span></span>



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a><span data-ttu-id="8fd78-106">사이트 또는 사용자 회의 정책을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="8fd78-106">To delete a site or user conferencing policy</span></span>

1.  <span data-ttu-id="8fd78-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd78-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8fd78-108">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8fd78-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8fd78-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd78-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8fd78-110">왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **회의 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd78-110">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="8fd78-111">회의 정책 목록에서 삭제 하려는 사이트 또는 사용자 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd78-111">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8fd78-112">Windows PowerShell Cmdlet을 사용 하 여 회의 정책 제거</span><span class="sxs-lookup"><span data-stu-id="8fd78-112">Removing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8fd78-113">Lync Server Management Shell 및 **Remove-CsConferencingPolicy** cmdlet을 사용 하 여 회의 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd78-113">You can delete conferencing policies by using Lync Server Management Shell and the **Remove-CsConferencingPolicy** cmdlet.</span></span> <span data-ttu-id="8fd78-114">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd78-114">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8fd78-115">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd78-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a><span data-ttu-id="8fd78-116">지정 된 회의 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="8fd78-116">To remove a specified conferencing policy</span></span>

  - <span data-ttu-id="8fd78-117">다음 명령은 Id RedmondConferencingPolicy를 사용 하 여 회의 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd78-117">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="8fd78-118">사용자별 범위에 적용 된 모든 회의 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="8fd78-118">To remove all of the conferencing policies applied to the per-user scope</span></span>

  - <span data-ttu-id="8fd78-119">다음 명령은 사용자 단위 범위에서 구성 된 모든 회의 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd78-119">The following command removes all the conferencing policies configured at the per-user scope:</span></span>
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a><span data-ttu-id="8fd78-120">외부 사용자의 기록을 허용 하는 모든 회의 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="8fd78-120">To remove all of the conferencing polices that allow recording by external users</span></span>

  - <span data-ttu-id="8fd78-121">다음 명령은 외부 사용자가 회의를 녹음할 수 있도록 허용 하는 회의 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd78-121">The following command deletes any conferencing policies that allow external users to record the conference:</span></span>
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

<span data-ttu-id="8fd78-122">자세한 내용은 [제거-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd78-122">For details, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

