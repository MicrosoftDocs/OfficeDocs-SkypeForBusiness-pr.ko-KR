---
title: 'Lync Server 2013: 사용자 PIN 정보 보기'
description: 'Lync Server 2013: 사용자 PIN 정보를 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f0808e645a2589841ff70d4923fa2de2c020ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580064"
---
# <a name="view-user-pin-information-in-lync-server-2013"></a><span data-ttu-id="33613-103">Lync Server 2013에서 사용자 PIN 정보 보기</span><span class="sxs-lookup"><span data-stu-id="33613-103">View user PIN information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33613-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="33613-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="33613-105">전화 접속 회의에 인증 된 사용자로 참가 하려면 AD DS (Active Directory 도메인 서비스) 자격 증명을 사용 하는 Lync Server 2013 사용자에 게 PIN (개인 식별 번호)이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-105">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="33613-106">Lync Server 2013 제어판에서 사용자의 PIN 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33613-106">You can view a user’s PIN information from Lync Server 2013 Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="33613-107">PIN이 설정되었는지 여부 또는 PIN이 마지막으로 변경된 시간 등의 PIN 상태 정보를 볼 수 있지만 PIN 상태로 조회해서 현재 PIN을 볼 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33613-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="33613-108">사용자가 PIN을 잃은 경우 <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Lync Server 2013에서 사용자의 전화 접속 회의 PIN 설정</A> 의 절차에 따라 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33613-108">If a user has lost their PIN, you can reset it by following the procedures in <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Set a user's dial-in conferencing PIN in Lync Server 2013</A></span></span>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="33613-109">Lync Server 제어판에서 사용자의 PIN을 보려면</span><span class="sxs-lookup"><span data-stu-id="33613-109">To view a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="33613-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33613-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="33613-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33613-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="33613-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33613-113">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="33613-114">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="33613-114">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="33613-115">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="33613-116">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="33613-117">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="33613-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="33613-118">**필터 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-118">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="33613-119">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-119">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="33613-120">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-120">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="33613-121">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="33613-122">쿼리에 검색 절을 더 추가하려면 <STRONG>필터 추가</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-122">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="33613-123">**찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-123">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33613-p104">PIN이 잠겨 있는 경우에는 PIN 잠금을 해제해야 설정할 수 있습니다. PIN 잠금을 해제하려면 사용자를 클릭하고 <STRONG>동작</STRONG>을 클릭한 후에 <STRONG>PIN 잠금 해제</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="33613-126">검색 결과에서 사용자를 클릭하고 **동작**을 클릭한 후에 **PIN 상태 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="33613-126">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="33613-127">Windows PowerShell cmdlet을 사용 하 여 사용자 PIN 정보 보기</span><span class="sxs-lookup"><span data-stu-id="33613-127">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="33613-128">Get-CsClientPinInfo cmdlet을 사용하여 사용자 PIN 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33613-128">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="33613-129">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33613-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="33613-130">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="33613-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-user-pin-information"></a><span data-ttu-id="33613-131">사용자 PIN 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="33613-131">To view user PIN information</span></span>

  - <span data-ttu-id="33613-132">사용자에 대 한 PIN 정보를 보려면 Lync Server 관리 셸에서 다음과 같은 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="33613-132">To view PIN information for a user, type a command similar to the following in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    <span data-ttu-id="33613-133">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="33613-133">That will return information similar to this:</span></span>
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

<span data-ttu-id="33613-134">자세한 내용은 [get-csconferencedisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="33613-134">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33613-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33613-135">See Also</span></span>


[<span data-ttu-id="33613-136">Lync Server 2013에서 사용자의 전화 접속 회의 PIN 설정</span><span class="sxs-lookup"><span data-stu-id="33613-136">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[<span data-ttu-id="33613-137">Lync Server 2013에서 사용자 PIN 잠금 또는 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="33613-137">Lock or unlock a user PIN in Lync Server 2013</span></span>](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

