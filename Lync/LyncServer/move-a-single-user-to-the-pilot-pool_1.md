---
title: 파일럿 풀로 단일 사용자 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7320f55b88786ccf4e1a1a26c28483f3ccbd7d77
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="80ddd-102">파일럿 풀로 단일 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="80ddd-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80ddd-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="80ddd-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="80ddd-104">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 Office Communications Server 2007 R2 풀에서 Lync Server 2013 파일럿 풀로 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="80ddd-105">아래 예에서 등록자 풀 열에 있는 \*\* \<office communications\> \*\* server는 office communications server 2007 R2 풀 이며, 6 명의 사용자는이 풀에 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="80ddd-106">Lync server 2013 제어판 및 Lync Server 관리 셸을 사용 하 여 사용자를 Lync Server 2013 풀로 이동 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="80ddd-107">![Lync Server 제어판에서 OCS 사용자 검색](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Lync Server 제어판에서 OCS 사용자 검색")</span><span class="sxs-lookup"><span data-stu-id="80ddd-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="80ddd-108">Lync Server 2013 제어판을 사용 하 여 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="80ddd-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="80ddd-109">RTCUniversalServerAdmins 그룹의 구성원이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원인 계정으로 프런트 엔드 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="80ddd-110">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="80ddd-111">**사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-111">Click **Users**.</span></span>

4.  <span data-ttu-id="80ddd-112">**사용자 검색** 탭에서 **검색** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="80ddd-113">그런 다음 **필터 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="80ddd-114">**Office Communications Server 사용자**가 **True**인 필터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="80ddd-115">**찾기를** 클릭 하 여 레거시 Office Communications Server 2007 R2 사용자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="80ddd-116">![Lync Server 제어판에서 OCS 사용자 검색](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Lync Server 제어판에서 OCS 사용자 검색")</span><span class="sxs-lookup"><span data-stu-id="80ddd-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="80ddd-117">Lync Server 2013 풀로 이동 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="80ddd-118">이 예에서는 Sara Davis를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="80ddd-119">**동작** 메뉴에서 **선택한 사용자를 풀로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="80ddd-120">드롭다운 목록에서 Lync Server 2013 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="80ddd-121">**동작**, **선택한 사용자를 풀로 이동**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="80ddd-122">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-122">Click **OK**.</span></span>
    
    <span data-ttu-id="80ddd-123">![사용자 이동 대화 상자에서 대상 풀 설정](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "사용자 이동 대화 상자에서 대상 풀 설정")</span><span class="sxs-lookup"><span data-stu-id="80ddd-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="80ddd-124">사용자의 **등록자 풀** 열에 사용자가 성공적으로 이동 되었음을 나타내는 Lync Server 2013 풀이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="80ddd-125">Lync Server 2013 관리 셸을 사용 하 여 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="80ddd-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="80ddd-126">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="80ddd-127">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="80ddd-128">그런 다음 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="80ddd-129">이제 **RegistrarPool** Id는 Lync Server 2013 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="80ddd-130">이 ID가 있으면 사용자가 성공적으로 이동되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="80ddd-131">![Identity 필터가 포함 된 CsUser cmdlet의 출력](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Identity 필터가 포함 된 CsUser cmdlet의 출력")</span><span class="sxs-lookup"><span data-stu-id="80ddd-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80ddd-132"><STRONG>Get-CsUser</STRONG> cmdlet에 대한 자세한 내용을 보려면 <STRONG>Get-Help Get-CsUser –Detailed</STRONG>를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="80ddd-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

