---
title: 'Lync Server 2013: 사용자 PIN 잠금 또는 잠금 해제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61892a19fde4f9584d39557eac2f3ae46c51092
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a><span data-ttu-id="9186f-102">Lync Server 2013에서 사용자 PIN 잠금 또는 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="9186f-102">Lock or unlock a user PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9186f-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9186f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9186f-104">Lync Server 2013 제어판의 **사용자** 섹션에서 사용자 PIN을 잠그거나 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-104">You can lock or unlock a user’s PIN from the **Users** section of Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="9186f-105">Lync Server 제어판에서 사용자 PIN을 잠그려면</span><span class="sxs-lookup"><span data-stu-id="9186f-105">To lock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9186f-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9186f-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9186f-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9186f-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9186f-109">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9186f-110">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="9186f-111">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="9186f-112">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="9186f-113">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="9186f-114">**필터 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="9186f-115">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="9186f-116">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="9186f-117">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-117">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="9186f-118">쿼리에 검색 절을 더 추가하려면 <STRONG>필터 추가</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="9186f-119">**찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-119">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="9186f-120">사용자를 클릭하고, **작업**을 클릭한 후 **PIN 잠금**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-120">Click the user, click **Action**, and then click **Lock PIN**.</span></span>

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="9186f-121">Lync Server 제어판에서 사용자 PIN의 잠금을 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="9186f-121">To unlock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9186f-122">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9186f-123">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9186f-124">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9186f-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9186f-125">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9186f-126">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-126">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="9186f-127">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-127">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="9186f-128">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-128">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="9186f-129">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-129">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="9186f-130">**필터 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-130">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="9186f-131">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-131">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="9186f-132">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-132">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="9186f-133">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-133">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="9186f-134">쿼리에 검색 절을 더 추가하려면 <STRONG>필터 추가</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-134">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="9186f-135">**찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-135">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="9186f-136">사용자를 클릭하고 **작업**을 클릭한 후 **PIN 잠금 해제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-136">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9186f-137">Windows PowerShell Cmdlet을 사용 하 여 사용자 Pin 잠금 및 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="9186f-137">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9186f-138">Windows PowerShell 및 잠금-csclientpin cmdlet을 사용 하 여 사용자 Pin을 잠그거나 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-138">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="9186f-139">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 이러한 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9186f-139">You can run these cmdlets either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9186f-140">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9186f-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-lock-a-user-pin"></a><span data-ttu-id="9186f-141">사용자 PIN을 잠그려면</span><span class="sxs-lookup"><span data-stu-id="9186f-141">To lock a user PIN</span></span>

  - <span data-ttu-id="9186f-p104">사용자 PIN을 잠그려면 Lock-CsClientPin cmdlet을 사용합니다. 예:</span><span class="sxs-lookup"><span data-stu-id="9186f-p104">To lock a user’s PIN, use the Lock-CsClientPin cmdlet. For example:</span></span>
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a><span data-ttu-id="9186f-144">사용자 PIN의 잠금을 해제하려면</span><span class="sxs-lookup"><span data-stu-id="9186f-144">To unlock a user PIN</span></span>

  - <span data-ttu-id="9186f-p105">사용자 PIN의 잠금을 해제하려면 Unlock-CsClientPin cmdlet을 사용합니다. 예:</span><span class="sxs-lookup"><span data-stu-id="9186f-p105">To unlock a user’s PIN, use the Unlock-CsClientPin cmdlet. For example:</span></span>
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

<span data-ttu-id="9186f-147">자세한 내용은 [Lock-csclientpin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) 및 [Unlock-csclientpin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9186f-147">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

