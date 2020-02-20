---
title: 'Lync Server 2013: PIN 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 044c8a6ac5d87723a58c1f692c5e969701b72a37
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a><span data-ttu-id="e3de2-102">Lync Server 2013에서 PIN 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="e3de2-102">Delete a PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3de2-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e3de2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e3de2-104">PIN(개인 식별 번호) 정책을 삭제하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-104">Follow these steps to delete a personal identification number (PIN) policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3de2-105">전역 PIN 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a><span data-ttu-id="e3de2-106">Lync Server 2013 제어판에서 PIN 정책을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="e3de2-106">To delete a PIN policy in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="e3de2-107">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e3de2-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e3de2-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3de2-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e3de2-110">왼쪽 탐색 모음에서 **보안**을 클릭하고 **PIN 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="e3de2-111">**PIN 정책** 페이지의 검색 필드에 삭제할 정책의 이름 전부 또는 일부를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="e3de2-112">정책 목록에서 원하는 정책을 클릭하고 **편집**을 클릭한 다음 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="e3de2-113">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-113">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e3de2-114">Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 제거</span><span class="sxs-lookup"><span data-stu-id="e3de2-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e3de2-115">Windows PowerShell 및 Get-cspinpolicy cmdlet을 사용 하 여 PIN 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="e3de2-116">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e3de2-117">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3de2-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="e3de2-118">특정 PIN 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="e3de2-118">To remove a specific PIN policy</span></span>

  - <span data-ttu-id="e3de2-119">이 명령은 ID RedmondPinPolicy가 포함된 PIN 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-119">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="e3de2-120">사이트 범위에 적용 된 모든 PIN 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="e3de2-120">To remove all the PIN policies applied to the site scope</span></span>

  - <span data-ttu-id="e3de2-121">이 명령은 사이트 범위에 구성된 모든 PIN 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-121">This command removes all the PIN policies configured at the site scope:</span></span>
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="e3de2-122">공통 패턴 사용을 허용 하는 모든 PIN 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="e3de2-122">To remove all the PIN policies that allow the use of common patterns</span></span>

  - <span data-ttu-id="e3de2-123">그리고 이 명령은 공통 패턴 사용을 허용하는 모든 PIN 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e3de2-123">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

<span data-ttu-id="e3de2-124">자세한 내용은 [get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3de2-124">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

