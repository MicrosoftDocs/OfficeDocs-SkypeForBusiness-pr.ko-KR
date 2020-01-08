---
title: 'Lync Server 2013: 사용자의 전화 접속 회의 PIN 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 258c6e5da1dc5b78d53bbc3779d50890935d7b58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="9a4a8-102">Lync Server 2013에서 사용자의 전화 접속 회의 PIN 설정</span><span class="sxs-lookup"><span data-stu-id="9a4a8-102">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a4a8-103">_**마지막으로 수정한 주제:** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="9a4a8-103">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="9a4a8-104">전화 접속 회의에 인증 된 사용자로 참가 하려면 AD DS (Active Directory 도메인 서비스) 자격 증명을 사용 하는 Lync Server 2013 사용자에 게 PIN (개인 식별 번호)이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="9a4a8-105">사용자가 전화 접속 회의 PIN을 잊어버린 경우 또는 Lync Server를 사용 하 여 PIN을 설정 하지 않은 경우 Lync Server 제어판에서 사용자의 PIN을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-105">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="9a4a8-106">자동으로 PIN을 생성 하거나 수동으로 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-106">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a4a8-107">최소 길이와 같은 PIN의 특정 특성은 정책으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-107">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="9a4a8-108">전역 정책 외에도 개별 사이트 또는 사용자에 대 한 PIN 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-108">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="9a4a8-109">PIN 정책 구성에 대 한 자세한 내용은 <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Lync Server 2013에서 전화 접속 회의 PIN (개인 식별 번호) 규칙 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-109">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="9a4a8-110">사용자의 PIN을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="9a4a8-110">To set a user’s PIN</span></span>

1.  <span data-ttu-id="9a4a8-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a4a8-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9a4a8-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9a4a8-114">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9a4a8-115">사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="9a4a8-116">사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="9a4a8-117">저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="9a4a8-118">) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="9a4a8-119">**필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="9a4a8-120">사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="9a4a8-121">다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="9a4a8-122">선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-122">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="9a4a8-123">쿼리에 추가 검색 절을 추가 하려면 <STRONG>필터 추가</STRONG>를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="9a4a8-124">**찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-124">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a4a8-125">PIN이 잠겨 있으면 PIN을 설정 하기 전에 잠금을 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-125">If the PIN is locked, you must unlock the PIN before you can set it.</span></span> <span data-ttu-id="9a4a8-126">PIN의 잠금을 해제 하려면 사용자를 클릭 하 고 <STRONG>동작</STRONG>을 클릭 한 다음 <STRONG>pin 잠금 해제</STRONG>를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-126">To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="9a4a8-127">검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음, **PIN 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-127">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="9a4a8-128">**핀 설정** 대화 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-128">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="9a4a8-129">Lync Server 2013에서 사용자 PIN을 생성 하도록 허용 하려면 **자동으로 유효한 PIN** (기본값) 생성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-129">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="9a4a8-130">고유한 PIN을 만들려면 **수동으로 특정 pin 입력**을 클릭 하 고 텍스트 상자를 클릭 한 다음 pin 정책 설정에 지정 된 pin 요구 사항에 맞는 pin을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-130">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="9a4a8-131">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-131">Click **OK**.</span></span>

9.  <span data-ttu-id="9a4a8-132">**SET 핀**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-132">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="9a4a8-133">Pin **표시** 확인란을 선택 하 여 pin을 표시 한 다음, pin을 복사 하 고 조직의 기본 설정 메서드를 사용 하 여 사용자에 게 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-133">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="9a4a8-134">**내 전자 메일 응용 프로그램 열기를 클릭 하 여 새 pin을 사용자에 게 보내어** 전자 메일로 pin을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-134">Click **Open my email application to send the new PIN to the user** to send the PIN by email.</span></span> <span data-ttu-id="9a4a8-135">Microsoft Office Outlook이 전자 메일 클라이언트 이면 PIN이 새 전자 메일 메시지에 자동으로 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-135">If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message.</span></span> <span data-ttu-id="9a4a8-136">다른 전자 메일 클라이언트를 사용 하는 경우에는 pin **표시** 확인란을 선택 하 여 pin을 표시 한 다음 전자 메일 메시지에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-136">If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="9a4a8-137">**닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-137">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9a4a8-138">Windows PowerShell Cmdlet을 사용 하 여 사용자 PIN 할당</span><span class="sxs-lookup"><span data-stu-id="9a4a8-138">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9a4a8-139">또한 Set CsClientPin cmdlet을 사용 하 여 PIN 번호를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-139">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="9a4a8-140">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-140">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9a4a8-141">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-141">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="9a4a8-142">사용자에 게 자동으로 PIN 번호 할당</span><span class="sxs-lookup"><span data-stu-id="9a4a8-142">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="9a4a8-143">다음 명령은 사용자: 진구 Myer에 PIN 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-143">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="9a4a8-144">Pin 매개 변수는 포함 되지 않기 때문에 Lync Server는 자동으로 PIN 번호를 생성 하 고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-144">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="9a4a8-145">특정 PIN 번호를 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="9a4a8-145">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="9a4a8-146">이 명령은 Pin 매개 변수를 사용 하 여 사용자: 진구 Myer에 PIN 번호 121989를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-146">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="9a4a8-147">자세한 내용은 [집합 CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4a8-147">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a4a8-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a4a8-148">See Also</span></span>


<span data-ttu-id="9a4a8-149">[전화 접속 액세스 번호](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9a4a8-149">[Dial-in Access Number](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="9a4a8-150">Lync Server 2013에서 전화 접속 회의 PIN (개인 식별 번호) 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="9a4a8-150">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

