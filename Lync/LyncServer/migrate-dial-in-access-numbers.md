---
title: 전화 접속 액세스 번호 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0638ae76a9aa1108b11c1d1ff98fdd3eef08c938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="43909-102">전화 접속 액세스 번호 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="43909-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43909-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="43909-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="43909-104">Lync Server 2010에서 전화 접속 액세스 번호를 Lync Server 2013으로 마이그레이션하면 contact 개체를 마이그레이션하기 위해 **CsApplicationEndpoint** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="43909-105">Lync server 2010 및 Lync Server 2013 공존 기간 중에 Lync Server 2013에서 만든 전화 접속 액세스 번호는이 섹션에서 설명 하는 대로 Lync Server 2010에서 만든 전화 접속 액세스 번호와 유사 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="43909-106">Lync server 2010에서 만든 전화 접속 액세스 번호로, lync server 2013로 이동 하거나, 이전에 또는 마이그레이션 중에 Lync Server 2013에서 만든 연결에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43909-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="43909-107">Office Communications Server 2007 R2 모임 초대 및 전화 접속 액세스 번호 페이지에는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43909-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="43909-108">Lync Server 2010 모임 초대 및 전화 접속 액세스 번호 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43909-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="43909-109">Lync Server 2013 모임 초대 및 전화 접속 액세스 번호 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43909-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="43909-110">Office Communications Server 2007 R2 관리 도구에서 보거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43909-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="43909-111">Lync Server 2010 제어판 및 Lync Server 2010 관리 셸에서 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43909-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="43909-112">Lync Server 2013 제어판 및 Lync Server 2013 관리 셸에서 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43909-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="43909-113">CsDialinConferencingAccessNumber cmdlet을 Priority 매개 변수를 사용 하 여 영역 내에서 다시 시퀀싱 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43909-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="43909-114">Lync Server 2010 풀의 역할을 해제 하기 전에 Lync Server 2010 풀을 가리키는 전화 접속 액세스 번호 마이그레이션을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-114">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="43909-115">다음 절차에 설명 된 대로 전화 접속 액세스 번호 마이그레이션을 완료 하지 않은 경우에는 액세스 번호로 수신 되는 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-115">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="43909-116">Lync Server 2010 풀의 역할을 해제 하기 전에이 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="43909-117">짧은 서비스 중단 기간이 있는 경우 네트워크 사용량이 낮을 때 전화 접속 액세스 번호를 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="43909-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="43909-118">**전화 접속 액세스 번호를 확인 하 고 이동 하려면**</span><span class="sxs-lookup"><span data-stu-id="43909-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="43909-119">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="43909-120">각 전화 접속 액세스 번호를 Lync Server 2013에서 호스팅되는 풀로 이동 하려면 명령줄 실행에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="43909-121">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="43909-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="43909-122">왼쪽 탐색 모음에서 **회의**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="43909-123">**전화 접속 액세스 번호** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="43909-124">마이그레이션하는 Lync Server 2010 풀에 대 한 전화 접속 액세스 번호가 남아 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43909-125">모든 전화 접속 액세스 번호가 Lync Server 2013 풀을 가리키는 경우 Lync Server 2010 풀을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43909-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="43909-126">**Lync Server 제어판을 사용 하 여 전화 접속 액세스 번호 마이그레이션 확인**</span><span class="sxs-lookup"><span data-stu-id="43909-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="43909-127">**Csuseradministrator** 역할 또는 **csadministrator** 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="43909-128">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="43909-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="43909-129">왼쪽 탐색 모음에서 **회의**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="43909-130">**전화 접속 액세스 번호** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="43909-131">모든 전화 접속 액세스 번호가 Lync Server 2013에서 호스트 되는 풀로 마이그레이션 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="43909-132">**Lync Server Management Shell을 사용 하 여 전화 접속 액세스 번호 마이그레이션 확인**</span><span class="sxs-lookup"><span data-stu-id="43909-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="43909-133">Lync Server Management Shell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="43909-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="43909-134">마이그레이션된 모든 전화 접속 회의 액세스 번호를 명령줄 실행에서 반환 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="43909-135">모든 전화 접속 액세스 번호가 Lync Server 2013에서 호스트 되는 풀로 마이그레이션 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="43909-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

