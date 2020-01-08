---
title: 'Lync Server 2013: 새 클라이언트 버전 정책 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e9d9d2879d4633b1775f8934186b8b01992d13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="f85d6-102">Lync Server 2013에서 새 클라이언트 버전 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="f85d6-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f85d6-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f85d6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f85d6-104">클라이언트 버전 정책을 사용 하 여 해당 환경에서 지원 되는 클라이언트 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="f85d6-105">클라이언트 버전 관리를 사용 하면 여러 클라이언트 버전 지원과 관련 된 비용을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="f85d6-106">또한 이전 버전과 이후 버전의 클라이언트가 상호 작용 하는 경우 사용 가능한 기능을 이전 버전의 클라이언트로 제한할 수 있기 때문에 전체적인 사용자 환경을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="f85d6-107">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 정책을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="f85d6-108">Lync Server 제어판을 사용 하 여 클라이언트 버전 정책을 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="f85d6-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f85d6-109">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f85d6-110">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f85d6-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f85d6-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f85d6-112">왼쪽 탐색 모음에서 **클라이언트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f85d6-113"><STRONG>클라이언트 버전 정책</STRONG> 탭이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="f85d6-114">**클라이언트 버전 정책** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f85d6-115">클라이언트 버전 정책을 만들려면 **새로 만들기**를 클릭 하 고 **사이트 정책**, **풀 정책**또는 **사용자 정책을**선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="f85d6-116">전역 정책 또는 다른 기존 클라이언트 버전 정책을 수정 하려면 정책을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f85d6-117">**클라이언트 버전 정책 편집** 페이지에서 [Lync Server 2013의 새 클라이언트 버전 정책 만들기 또는 수정](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)에서 설명한 대로 규칙을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f85d6-118">Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="f85d6-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f85d6-119">**새 csclientversionpolicy** cmdlet을 사용 하 여 클라이언트 버전 정책을 만들고, **Set-csclientversionpolicy** cmdlet을 사용 하 여이를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="f85d6-120">이러한 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f85d6-121">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f85d6-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="f85d6-122">사이트 범위의 새 클라이언트 버전 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f85d6-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="f85d6-123">다음 명령은 Redmond 사이트에 적용 된 새 클라이언트 버전 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="f85d6-124">추가 매개 변수를 지정 하지 않았으므로 새 정책에 기본 클라이언트 버전 설정이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="f85d6-125">새 사용자 단위 클라이언트 버전 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f85d6-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="f85d6-126">사용자별 정책을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f85d6-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="f85d6-127">자세한 내용은 [새 CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) Cmdlet 및 [Set csclientversionpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) Cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f85d6-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

