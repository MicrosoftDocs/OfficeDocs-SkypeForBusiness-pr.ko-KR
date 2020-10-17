---
title: 'Lync Server 2013: 사용자의 전화 접속 회의 PIN 설정'
description: 'Lync Server 2013: 사용자의 전화 접속 회의 PIN을 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 238c2a72da81a53b409d81c1b91c885f1ddabcbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543334"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="3b72c-103">Lync Server 2013에서 사용자의 전화 접속 회의 PIN 설정</span><span class="sxs-lookup"><span data-stu-id="3b72c-103">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b72c-104">_**마지막으로 수정 된 항목:** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="3b72c-104">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="3b72c-105">전화 접속 회의에 인증 된 사용자로 참가 하려면 AD DS (Active Directory 도메인 서비스) 자격 증명을 사용 하는 Lync Server 2013 사용자에 게 PIN (개인 식별 번호)이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-105">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="3b72c-106">사용자가 전화 접속 회의 PIN을 잊어버린 경우 Lync Server를 사용 하 여 PIN을 설정 하지 않은 경우 Lync Server 제어판에서 사용자의 PIN을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="3b72c-107">PIN은 자동으로 생성할 수도 있고 수동으로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-107">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b72c-108">최소 길이와 같은 PIN의 특정 특성을 정책으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-108">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="3b72c-109">글로벌 정책뿐 아니라, 개별 사이트 또는 사용자에 대한 PIN 정책도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-109">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="3b72c-110">PIN 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Lync Server 2013에서 전화 접속 회의 PIN (개인 식별 번호) 규칙 구성을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b72c-110">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="3b72c-111">사용자 PIN을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="3b72c-111">To set a user’s PIN</span></span>

1.  <span data-ttu-id="3b72c-112">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b72c-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3b72c-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b72c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3b72c-115">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3b72c-116">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="3b72c-117">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="3b72c-118">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="3b72c-119">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="3b72c-120">**필터 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="3b72c-121">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="3b72c-122">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="3b72c-123">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-123">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="3b72c-124">쿼리에 검색 절을 더 추가하려면 <STRONG>필터 추가</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="3b72c-125">**찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-125">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b72c-p104">PIN이 잠겨 있는 경우에는 PIN 잠금을 해제해야 설정할 수 있습니다. PIN 잠금을 해제하려면 사용자를 클릭하고 <STRONG>동작</STRONG>을 클릭한 후에 <STRONG>PIN 잠금 해제</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="3b72c-128">검색 결과에서 사용자를 클릭하고 **동작**을 클릭한 후에 **PIN 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-128">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="3b72c-129">**PIN 설정** 대화 상자에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-129">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="3b72c-130">Lync Server 2013에서 사용자의 PIN을 생성 하도록 하려면 **자동으로 올바른 PIN 생성** (기본값)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-130">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="3b72c-131">PIN을 직접 만들려면 **특정 PIN을 수동으로 입력**을 클릭하고 텍스트 상자를 클릭한 후에 PIN 정책 설정에 지정된 PIN 요구 사항을 충족하는 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-131">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="3b72c-132">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-132">Click **OK**.</span></span>

9.  <span data-ttu-id="3b72c-133">**PIN 설정**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-133">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="3b72c-134">**PIN 표시** 확인란을 선택하여 PIN을 표시한 다음 PIN을 복사하여 조직에서 사용하는 기본 방법을 통해 사용자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-134">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="3b72c-p105">PIN을 전자 메일로 보내려면 **내 전자 메일 응용 프로그램을 열어 새 PIN을 사용자에게 보내기**를 클릭합니다. Microsoft Office Outlook이 전자 메일 클라이언트인 경우 PIN이 새 전자 메일 메시지에 자동으로 복사됩니다. 다른 전자 메일 클라이언트를 사용하는 경우에는 **PIN 표시** 확인란을 선택하여 PIN을 표시한 다음 전자 메일 메시지에 PIN을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-p105">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="3b72c-138">**닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-138">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3b72c-139">Windows PowerShell Cmdlet을 사용 하 여 사용자 PIN 할당</span><span class="sxs-lookup"><span data-stu-id="3b72c-139">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3b72c-140">Set-CsClientPin cmdlet을 사용 하 여 PIN 번호 할당을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-140">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="3b72c-141">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-141">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3b72c-142">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b72c-142">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="3b72c-143">사용자에 게 PIN 번호를 자동으로 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="3b72c-143">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="3b72c-144">다음 명령은 Myer라는 사용자에게 PIN 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-144">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="3b72c-145">Pin 매개 변수는 포함 되지 않으므로 Lync Server에서는 PIN 번호를 자동으로 생성 및 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-145">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="3b72c-146">사용자에 게 특정 PIN 번호를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="3b72c-146">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="3b72c-147">이 명령은 Pin 매개 변수를 사용해서 Ken Myer라는 사용자에게 PIN 번호 121989를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72c-147">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="3b72c-148">자세한 내용은 [CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b72c-148">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b72c-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b72c-149">See Also</span></span>


<span data-ttu-id="3b72c-150">[전화 접속 액세스 번호](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b72c-150">[Dial-in Access Number](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="3b72c-151">Lync Server 2013에서 전화 접속 회의 PIN (개인 식별 번호) 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="3b72c-151">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

