---
title: 'Lync Server 2013: 기존 클라이언트 버전 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99936b495075034e6eae3f90e6dd95325bf6e2be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="2ab21-102">Lync Server 2013에서 기존 클라이언트 버전 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="2ab21-102">Delete an existing client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ab21-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2ab21-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2ab21-104">이전에 구성한 클라이언트 버전 정책을 삭제 하려는 경우 Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-104">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="2ab21-105">Lync Server 제어판을 사용 하 여 클라이언트 버전 정책을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="2ab21-105">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2ab21-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ab21-107">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2ab21-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab21-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2ab21-109">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **클라이언트 버전 정책** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-109">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="2ab21-110">**클라이언트 버전 정책** 페이지에서 삭제 하려는 클라이언트 버전 정책 또는 정책을 선택 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-110">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2ab21-111">Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="2ab21-111">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2ab21-112">**제거-CsClientVersionPolicy** cmdlet을 사용 하 여 클라이언트 버전 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-112">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="2ab21-113">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2ab21-114">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab21-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="2ab21-115">특정 클라이언트 버전 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="2ab21-115">To remove a specific client version policy</span></span>

  - <span data-ttu-id="2ab21-116">이 명령은 Redmond 사이트에 적용 된 클라이언트 버전 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-116">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="2ab21-117">사이트 범위에 적용 된 모든 클라이언트 버전 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="2ab21-117">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="2ab21-118">이 명령은 사이트 범위에서 구성 된 클라이언트 버전 정책을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-118">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="2ab21-119">특정 사용자 에이전트를 포함 하지 않는 클라이언트 버전 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="2ab21-119">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="2ab21-120">이 명령은 WPLync (Windows Phone Lync) 사용자 에이전트에 대 한 규칙을 포함 하지 않는 모든 클라이언트 버전 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-120">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="2ab21-121">자세한 내용은 [CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab21-121">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

