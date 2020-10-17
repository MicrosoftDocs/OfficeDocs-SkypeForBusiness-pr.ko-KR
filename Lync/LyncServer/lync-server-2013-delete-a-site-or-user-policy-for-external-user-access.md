---
title: 'Lync Server 2013: 외부 사용자 액세스에 대 한 사이트 또는 사용자 정책 삭제'
description: 'Lync Server 2013: 외부 사용자 액세스에 대 한 사이트 또는 사용자 정책을 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aac81e7b50603e5eb80cde8877cdc06f138d872
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553714"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="838fc-103">Lync Server 2013에서 외부 사용자 액세스에 대 한 사이트 또는 사용자 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="838fc-103">Delete a site or user policy for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="838fc-104">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="838fc-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="838fc-105">**외부 액세스 정책** 페이지의 Lync Server 제어판에 나열 된 모든 사이트 또는 사용자 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-105">You can delete any site or user policy that is listed in Lync Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="838fc-106">글로벌 정책을 삭제 해도 실제로 삭제 되지는 않지만이를 기본 설정으로 다시 설정 하면 외부 사용자 액세스 옵션에 대 한 지원이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-106">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="838fc-107">전역 정책을 다시 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 대 한 전역 정책 다시 설정](lync-server-2013-reset-the-global-policy-for-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="838fc-107">For details about resetting the global policy, see [Reset the global policy for external user access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span></span>

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="838fc-108">외부 사용자 액세스에 대 한 사이트 또는 사용자 정책을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="838fc-108">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="838fc-109">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="838fc-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="838fc-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="838fc-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="838fc-112">**외부 사용자 액세스**를 클릭 하 고 **외부 액세스 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-112">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="838fc-113">**외부 액세스 정책** 탭에서 삭제할 사이트 또는 사용자 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-113">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="838fc-114">삭제를 확인하는 메시지가 표시되면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-114">When prompted to confirm the deletion, click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="838fc-115">Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 제거</span><span class="sxs-lookup"><span data-stu-id="838fc-115">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="838fc-116">Windows PowerShell 및 Remove-CsExternalAccessPolicy cmdlet을 사용 하 여 외부 액세스 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-116">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="838fc-117">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="838fc-118">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="838fc-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="838fc-119">특정 외부 액세스 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="838fc-119">To remove a specific external access policy</span></span>

  - <span data-ttu-id="838fc-120">이 명령은 Redmond 사이트에 적용 된 외부 액세스 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-120">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="838fc-121">사용자별 범위에 적용 된 모든 외부 액세스 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="838fc-121">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="838fc-122">이 명령은 사용자별 범위에서 구성 된 모든 외부 액세스 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-122">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="838fc-123">외부 사용자 액세스를 사용 하지 않도록 설정 된 모든 외부 액세스 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="838fc-123">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="838fc-124">이 명령은 외부 사용자 액세스가 해제 된 모든 외부 액세스 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="838fc-124">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

<span data-ttu-id="838fc-125">자세한 내용은 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="838fc-125">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

