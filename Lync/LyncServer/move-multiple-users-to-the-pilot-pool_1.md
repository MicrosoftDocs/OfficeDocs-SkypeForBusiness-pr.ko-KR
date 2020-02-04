---
title: 여러 사용자를 시험 운용 풀로 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70d031481746f9f7408cc7b5e36081bb977b189d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="6bdbd-102">여러 사용자를 시험 운용 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="6bdbd-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bdbd-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6bdbd-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6bdbd-104">Lync Server 2013 제어판 또는 Lync Server 2013 Management Shell을 사용 하 여 Office Communications Server 2007 R2 풀에서 Lync Server 2013 파일럿 풀로 여러 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="6bdbd-105">Lync Server 2013 제어판을 사용 하 여 여러 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="6bdbd-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="6bdbd-106">**Lync Server 제어판**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="6bdbd-107">**사용자 검색** 탭에서 **검색** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="6bdbd-108">그런 다음 **필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="6bdbd-109">**Office Communications Server 사용자** 가 **True**인 필터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="6bdbd-110">**찾기를** 클릭 하 여 레거시 Office Communications Server 2007 R2 사용자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="6bdbd-111">Lync Server 2013 풀로 이동 하려는 두 명의 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="6bdbd-112">이 예제에서는 사용자 Yang 및 Claus Hansen를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="6bdbd-113">![OCS 사용자 검색 결과 표시된 사용자 목록](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "OCS 사용자 검색 결과 표시된 사용자 목록")</span><span class="sxs-lookup"><span data-stu-id="6bdbd-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="6bdbd-114">**작업** 메뉴에서 **선택한 사용자 이동을 선택 하 여 그룹으로 이동**합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="6bdbd-115">드롭다운 목록에서 Lync Server 2013 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="6bdbd-116">**작업** 을 클릭 한 다음 **선택한 사용자 이동을 클릭 하 여 그룹을 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="6bdbd-117">확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-117">Click OK.</span></span>
    
    <span data-ttu-id="6bdbd-118">![사용자 이동, 대상 등록자 풀 대화 상자](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "사용자 이동, 대상 등록자 풀 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="6bdbd-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="6bdbd-119">사용자의 **등록자 풀** 열에 사용자가 성공적으로 이동 되었음을 나타내는 Lync Server 2013 풀이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="6bdbd-120">Lync Server 2013 관리 셸을 사용 하 여 여러 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="6bdbd-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="6bdbd-121">Lync Server 2013 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="6bdbd-122">명령줄에 다음을 입력 하 고 **User1** **과 사용자** 이름을 이동 하려는 특정 사용자 이름으로 바꾸고 **풀\_FQDN** 을 대상 풀의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="6bdbd-123">이 예제에서는 사용자 Hao 및 Katie를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="6bdbd-124">![레거시 사용자를 이동하는 cmdlet의 예제](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "레거시 사용자를 이동하는 cmdlet의 예제")</span><span class="sxs-lookup"><span data-stu-id="6bdbd-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="6bdbd-125">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="6bdbd-126">이제 **등록자 풀** id는 이전 단계에서 **풀\_FQDN** 으로 지정한 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="6bdbd-127">이 id가 있으면 사용자가 성공적으로 이동 했음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="6bdbd-128">단계를 반복 하 여 %2이 (가) **이동 되었는지 확인** 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="6bdbd-129">![PowerShell Get UsUser-Identity cmdlet의 출력](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell Get-UsUser -Identity cmdlet의 출력")</span><span class="sxs-lookup"><span data-stu-id="6bdbd-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="6bdbd-130">Lync Server 2013 관리 셸을 사용 하 여 모든 사용자를 동시에 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="6bdbd-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="6bdbd-131">이 예제에서는 모든 사용자가 Office Communications Server 2007 R2 풀 (pool01.contoso.net)에 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="6bdbd-132">Lync Server 2013 관리 셸을 사용 하 여 모든 사용자를 Lync Server 2013 풀 (pool02.contoso.net)로 동시에 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="6bdbd-133">**Lync Server 2013 관리 셸을**엽니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="6bdbd-134">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="6bdbd-135">![풀의 모든 레거시 사용자를 이동하는 cmdlet의 예제](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "풀의 모든 레거시 사용자를 이동하는 cmdlet의 예제")</span><span class="sxs-lookup"><span data-stu-id="6bdbd-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="6bdbd-136">다음으로, 파일럿 사용자 중 한 명에 대해 **Get-CsUser** 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="6bdbd-137">각 사용자의 **등록자 풀** id는 이제 이전 단계에서 "풀\_FQDN"으로 지정 된 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="6bdbd-138">이 id가 있으면 사용자가 성공적으로 이동 했음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="6bdbd-139">또한 Lync Server 2013 제어판에서 사용자 목록을 볼 수 있으며 이제 등록자 그룹 값이 Lync Server 2013 풀을 가리키는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdbd-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="6bdbd-140">![Lync Server 2013 제어판 사용자 목록](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 제어판 사용자 목록")</span><span class="sxs-lookup"><span data-stu-id="6bdbd-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

