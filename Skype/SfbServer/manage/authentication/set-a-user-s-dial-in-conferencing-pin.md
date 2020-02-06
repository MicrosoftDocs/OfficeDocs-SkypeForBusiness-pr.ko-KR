---
title: 비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN 설정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: '요약: 비즈니스용 Skype 서버에 대 한 사용자의 전화 접속 회의 PIN을 설정 합니다.'
ms.openlocfilehash: eb025f069156dd54ba772dd866c09adc59d078eb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818740"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="a28d2-103">비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN 설정</span><span class="sxs-lookup"><span data-stu-id="a28d2-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="a28d2-104">**요약:** 비즈니스용 Skype 서버에 대 한 사용자의 전화 접속 회의 PIN을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="a28d2-105">전화 접속 회의에 인증 된 사용자로 참가 하려면 AD DS (Active Directory 도메인 서비스) 자격 증명을 사용 하는 비즈니스용 Skype Server 사용자에 게 PIN (개인 식별 번호)이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="a28d2-106">사용자가 전화 접속 회의 PIN을 잊어버린 경우 또는 비즈니스용 Skype Server를 사용 하 여 PIN을 설정 하지 않은 경우 비즈니스용 Skype Server 제어판에서 사용자의 PIN을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="a28d2-107">자동으로 PIN을 생성 하거나 수동으로 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a28d2-108">최소 길이와 같은 PIN의 특정 특성은 정책으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-108">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="a28d2-109">전역 정책 외에도 개별 사이트 또는 사용자에 대 한 PIN 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-109">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="a28d2-110">사용자의 PIN을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="a28d2-110">To set a user's PIN</span></span>

1. <span data-ttu-id="a28d2-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a28d2-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a28d2-113">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a28d2-114">사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="a28d2-115">사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="a28d2-116">저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="a28d2-117">) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="a28d2-118">에서.</span><span class="sxs-lookup"><span data-stu-id="a28d2-118">a.</span></span> <span data-ttu-id="a28d2-119">**필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="a28d2-120">b.</span><span class="sxs-lookup"><span data-stu-id="a28d2-120">b.</span></span> <span data-ttu-id="a28d2-121">사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="a28d2-122">c.</span><span class="sxs-lookup"><span data-stu-id="a28d2-122">c.</span></span> <span data-ttu-id="a28d2-123">다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="a28d2-124">a.</span><span class="sxs-lookup"><span data-stu-id="a28d2-124">d.</span></span> <span data-ttu-id="a28d2-125">선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a28d2-126">쿼리에 추가 검색 절을 추가 하려면 **필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="a28d2-127">z.e.n.works.</span><span class="sxs-lookup"><span data-stu-id="a28d2-127">e.</span></span> <span data-ttu-id="a28d2-128">**찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a28d2-129">PIN이 잠겨 있으면 PIN을 설정 하기 전에 잠금을 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-129">If the PIN is locked, you must unlock the PIN before you can set it.</span></span> <span data-ttu-id="a28d2-130">PIN의 잠금을 해제 하려면 사용자를 클릭 하 고 **동작**을 클릭 한 다음 **pin 잠금 해제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-130">To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="a28d2-131">검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음, **PIN 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="a28d2-132">**핀 설정** 대화 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="a28d2-133">비즈니스용 Skype 서버에서 사용자의 PIN을 생성 하도록 허용 하려면 **자동으로 유효한 PIN** (기본값) 생성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="a28d2-134">고유한 PIN을 만들려면 **수동으로 특정 pin 입력**을 클릭 하 고 텍스트 상자를 클릭 한 다음 pin 정책 설정에 지정 된 pin 요구 사항에 맞는 pin을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="a28d2-135">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="a28d2-136">**SET 핀**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="a28d2-137">Pin **표시** 확인란을 선택 하 여 pin을 표시 한 다음, pin을 복사 하 고 조직의 기본 설정 메서드를 사용 하 여 사용자에 게 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="a28d2-138">**내 전자 메일 응용 프로그램 열기를 클릭 하 여 새 pin을 사용자에 게 보내어** 전자 메일로 pin을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-138">Click **Open my email application to send the new PIN to the user** to send the PIN by email.</span></span> <span data-ttu-id="a28d2-139">Microsoft Office Outlook이 전자 메일 클라이언트 이면 PIN이 새 전자 메일 메시지에 자동으로 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-139">If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message.</span></span> <span data-ttu-id="a28d2-140">다른 전자 메일 클라이언트를 사용 하는 경우에는 pin **표시** 확인란을 선택 하 여 pin을 표시 한 다음 전자 메일 메시지에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-140">If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="a28d2-141">**닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a28d2-142">Windows PowerShell Cmdlet을 사용 하 여 사용자 PIN 할당</span><span class="sxs-lookup"><span data-stu-id="a28d2-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a28d2-143">또한 Set CsClientPin cmdlet을 사용 하 여 PIN 번호를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="a28d2-144">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a28d2-145">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a28d2-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a28d2-146">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="a28d2-147">사용자에 게 자동으로 PIN 번호 할당</span><span class="sxs-lookup"><span data-stu-id="a28d2-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="a28d2-148">다음 명령은 사용자: 진구 Myer에 PIN 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="a28d2-149">Pin 매개 변수는 포함 되지 않기 때문에 비즈니스용 Skype Server는 자동으로 PIN 번호를 생성 하 고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="a28d2-150">특정 PIN 번호를 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="a28d2-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="a28d2-151">이 명령은 Pin 매개 변수를 사용 하 여 사용자: 진구 Myer에 PIN 번호 121989를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28d2-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="a28d2-152">자세한 내용은 [집합 CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a28d2-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

