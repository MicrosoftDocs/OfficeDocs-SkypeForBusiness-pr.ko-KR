---
title: 여러 사용자를 파일럿 풀로 이동
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a5a92b0438e72be0ecb5acaa1b8e1886768ad59
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="d6043-102">여러 사용자를 파일럿 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="d6043-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6043-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d6043-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d6043-104">Lync server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 Lync Server 2010 풀에서 Lync server 2013 파일럿 풀로 여러 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="d6043-105">Lync Server 2013 제어판을 사용 하 여 여러 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="d6043-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="d6043-106">**Lync Server 제어판**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="d6043-107">**사용자**, 검색, **찾기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="d6043-108">Lync Server 2013 풀로 이동 하려는 두 명의 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="d6043-109">이 예에서는 사용자 Chen Yang과 Claus Hansen을 이동하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="d6043-110">![사용자를 특정 등록 풀로 이동](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "사용자를 특정 등록 풀로 이동")</span><span class="sxs-lookup"><span data-stu-id="d6043-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="d6043-111">**동작** 메뉴에서 **선택한 사용자를 풀로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="d6043-112">드롭다운 목록에서 Lync Server 2013 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="d6043-113">**동작**, **선택한 사용자를 풀로 이동**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="d6043-114">확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-114">Click OK.</span></span>
    
    <span data-ttu-id="d6043-115">![사용자 이동, 대상 등록자 풀 대화 상자](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "사용자 이동, 대상 등록자 풀 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="d6043-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="d6043-116">사용자의 **등록자 풀** 열에 사용자가 성공적으로 이동 되었음을 나타내는 Lync Server 2013 풀이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="d6043-117">Lync Server 2013 관리 셸을 사용 하 여 여러 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="d6043-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="d6043-118">Lync Server 2013 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="d6043-119">명령줄에서 다음을 입력 하 고 **User1** **과 사용자 1을 이동** 하려는 특정 사용자 이름으로 바꾸고 **풀 \_ FQDN** 을 대상 풀의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="d6043-120">이 예에서는 Hao Chen과 Katie Jordan을 이동하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="d6043-121">![PowerShell Get CsUser cmdlet의 예](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell Get CsUser cmdlet의 예")</span><span class="sxs-lookup"><span data-stu-id="d6043-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="d6043-122">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="d6043-123">이제 **등록자 풀** id가 이전 단계에서 **풀 \_ FQDN** 으로 지정한 풀을 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="d6043-124">ID는 이제 사용자가 이전 단계에서 pool_FQDN으로 지정한 풀을 가리킵니다.이 ID가 있으면 사용자가 성공적으로 이동된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="d6043-125">이 단계를 반복하여 **User2**가 이동되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="d6043-126">![PowerShell Get-UsUser-Identity cmdlet의 출력](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell Get-UsUser-Identity cmdlet의 출력")</span><span class="sxs-lookup"><span data-stu-id="d6043-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="d6043-127">Lync Server 2013 관리 셸을 사용 하 여 모든 사용자를 동시에 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="d6043-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="d6043-128">이 예에서는 모든 사용자가 Lync Server 2010 pool (pool01.contoso.net)로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="d6043-129">Lync Server 2013 관리 셸을 사용 하 여 모든 사용자를 Lync Server 2013 풀 (pool02.contoso.net)과 동시에 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="d6043-130">**Lync Server 2013 관리 셸을**엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="d6043-131">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="d6043-132">![관리 셸에서 PowerShell cmdlet 및 결과](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "관리 셸에서 PowerShell cmdlet 및 결과")</span><span class="sxs-lookup"><span data-stu-id="d6043-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="d6043-133">그런 다음 파일럿 사용자 한 명에 대해 **Get-CsUser**를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="d6043-134">이제 각 사용자의 **등록자 풀** id가 \_ 이전 단계에서 "Pool FQDN"으로 지정한 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="d6043-135">이 ID가 있으면 사용자가 성공적으로 이동되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="d6043-136">또한 Lync Server 2013 제어판의 사용자 목록을 보고 등록자 풀 값이 Lync Server 2013 풀을 가리키는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6043-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="d6043-137">![Lync Server 2013 제어판 사용자 목록](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 제어판 사용자 목록")</span><span class="sxs-lookup"><span data-stu-id="d6043-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

