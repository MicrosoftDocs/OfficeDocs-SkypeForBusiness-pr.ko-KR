---
title: 'Lync Server 2013: 사용자를 다른 풀로 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d2702e744fbadc5d51ea42095d7bd3d60f6f010
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="f6721-102">Lync Server 2013의 다른 풀로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="f6721-102">Move users to another pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="f6721-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="f6721-103">

<span> </span></span></span>

<span data-ttu-id="f6721-104">_**마지막으로 수정 된 항목:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="f6721-104">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="f6721-105">Lync Server 제어판을 사용 하 여 특정 서버나 풀에 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-105">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f6721-106">Lync Server 2010 이전 버전을 실행 중인 원본 풀에서 모든 기존 사용자를 복잡 한 Active Directory 환경의 Lync Server 2013 대상 풀로 이동 하면 Active Directory 복제가 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-106">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="f6721-107">이를 방지 하려면 검색 필터를 사용 하 여 Lync Server 2010 이전 버전을 실행 하는 풀에서 사용자를 개별적으로 이동 하거나 Lync Server 관리 셸을 사용 하 여 사용자를 cmdlet으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-107">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="f6721-108">또한 filter 기능은 Lync Server 2013 users 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-108">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="f6721-109">선택한 사용자를 다른 서버나 풀로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="f6721-109">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="f6721-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6721-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f6721-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f6721-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f6721-113">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f6721-114">**사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="f6721-115">테이블의 목록에서 특정 사용자 또는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-115">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="f6721-116">**동작** 메뉴에서 **선택한 사용자를 풀로 이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-116">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="f6721-117">**사용자 이동**의 **대상 등록자 풀**에서 사용자를 이동할 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-117">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="f6721-118">(선택 사항) 대상 서버나 풀을 사용할 수 없는 경우 **강제 적용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-118">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="f6721-119"><STRONG>Force</STRONG>를 선택 하면 사용자 계정이 이동 되지만 예약 된 전화 회의 및 연락처와 같은 관련 사용자 데이터는 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-119">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="f6721-120">특정 서버나 풀의 모든 사용자를 다른 서버나 풀로 이동하려면</span><span class="sxs-lookup"><span data-stu-id="f6721-120">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="f6721-121">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6721-122">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f6721-123">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f6721-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f6721-124">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-124">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f6721-125">**동작** 메뉴에서 **모든 사용자를 풀로 이동**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-125">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="f6721-126">**사용자 이동**의 **원본 등록자 풀**에서 이동할 사용자 계정이 있는 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-126">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="f6721-127">**대상 등록자 풀**에서 사용자를 이동할 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-127">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="f6721-128">(선택 사항) 대상 서버나 풀을 사용할 수 없는 경우 **강제 적용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-128">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="f6721-129"><STRONG>Force</STRONG>를 선택 하면 사용자 계정이 이동 되지만 예약 된 전화 회의 및 연락처와 같은 관련 사용자 데이터는 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-129">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="f6721-130">필터를 사용하여 한 풀에서 다른 풀로 사용자를 이동하려면</span><span class="sxs-lookup"><span data-stu-id="f6721-130">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="f6721-131">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6721-132">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f6721-133">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f6721-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f6721-134">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-134">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f6721-135">**사용자 검색**에서 **검색**을 클릭 하 고 **필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-135">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="f6721-136">검색 조건에서 **등록자 풀**, **같음**, **현재 풀 FQDN**을 차례로 선택한 후 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-136">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="f6721-137">**동작** 메뉴에서 **모든 사용자를 풀로 이동**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-137">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6721-138">필터를 기존 사용자 집합에 적용 하면 <STRONG>모든 사용자를 풀로 이동</STRONG> 옵션이 <STRONG><EM>모든</EM></STRONG> 가능한 사용자가 아닌 필터링 된 사용자 하위 집합의 컨텍스트로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-138">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="f6721-139">**사용자 이동**의 **원본 등록자 풀**에서 이동할 사용자 계정이 있는 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-139">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="f6721-140">**대상 등록자 풀**에서 사용자를 이동할 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-140">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="f6721-141">(선택 사항) 대상 서버나 풀을 사용할 수 없는 경우 **강제 적용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-141">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="f6721-142"><STRONG>Force</STRONG>를 선택 하면 사용자 계정이 이동 되지만 예약 된 전화 회의 및 연락처와 같은 관련 사용자 데이터는 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-142">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="f6721-143">Windows PowerShell cmdlet을 사용 하 여 풀 간에 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="f6721-143">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="f6721-144">Windows PowerShell 명령 (로컬 또는 원격)을 실행 하는 방법에 따라 다음과 같이 올바른 Lync Server 2013 관리 역할의 구성원으로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-144">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="f6721-145">로컬 컴퓨터에서 명령을 실행 하는 경우 (예: 프런트 엔드 서버에 직접 로그온 하는 경우), Lync Server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 위임 설정](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-145">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="f6721-146">다른 컴퓨터에서 원격으로 명령을 실행 하는 경우 (예를 들어, 컴퓨터에 로그온 하 고 Standard Edition 프런트 엔드 서버에서 원격으로 명령을 실행 하는 경우): CsUserAdministrator 역할 또는 CsAdministrator에 할당 된 사용자 계정에서 역할 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-146">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6721-147">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f6721-148">단일 사용자를 이동하려면 다음과 같이 Move-CsUser cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-148">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="f6721-149">이동할 사용자가 사용자 Pilar Ackerman이 고 사용자가 현재 할당 된 홈 풀에서 풀로 이동 됩니다 pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f6721-149">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="f6721-150">많은 수의 사용자를 이동하려면 **Get-CsUser** cmdlet과 함께 필터를 사용하고 결과 사용자 집합을 **Move-CsUser**에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-150">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="f6721-151">**Get-CsUser** 및 **Move-CsUser**의 조합 명령의 결과는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6721-151">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6721-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6721-152">See Also</span></span>


[<span data-ttu-id="f6721-153">Lync Server 2013에서 사용자 계정 속성 수정</span><span class="sxs-lookup"><span data-stu-id="f6721-153">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="f6721-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f6721-154"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

