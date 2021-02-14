---
title: 비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN 설정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: '요약: 비즈니스용 Skype 서버에 대한 사용자의 전화 접속 회의 PIN을 설정할 수 있습니다.'
ms.openlocfilehash: cd7375519fa9fc161c6414dcf1b9d0fbf6de6ef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828303"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="8e479-103">비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN 설정</span><span class="sxs-lookup"><span data-stu-id="8e479-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="8e479-104">**요약:** 비즈니스용 Skype 서버에 대한 사용자의 전화 접속 회의 PIN을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="8e479-105">인증된 사용자로 전화 접속 회의에 참가하려면 AD DS(Active Directory 도메인 서비스) 자격 증명이 있는 비즈니스용 Skype 서버 사용자에게는 개인식별번호(PIN)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="8e479-106">사용자가 전화 접속 회의 PIN을 잊어버리거나 비즈니스용 Skype 서버를 사용하여 PIN을 설정하지 않은 경우 비즈니스용 Skype 서버 제어판에서 사용자의 PIN을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="8e479-107">PIN은 자동으로 생성할 수도 있고 수동으로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e479-108">최소 길이와 같은 PIN의 특정 특성을 정책으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-108">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="8e479-109">글로벌 정책뿐 아니라, 개별 사이트 또는 사용자에 대한 PIN 정책도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-109">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="8e479-110">사용자의 PIN을 설정하는 경우</span><span class="sxs-lookup"><span data-stu-id="8e479-110">To set a user's PIN</span></span>

1. <span data-ttu-id="8e479-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8e479-112">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="8e479-113">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8e479-114">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="8e479-115">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="8e479-116">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="8e479-117">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="8e479-118">a.</span><span class="sxs-lookup"><span data-stu-id="8e479-118">a.</span></span> <span data-ttu-id="8e479-119">**필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="8e479-120">b.</span><span class="sxs-lookup"><span data-stu-id="8e479-120">b.</span></span> <span data-ttu-id="8e479-121">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="8e479-122">c.</span><span class="sxs-lookup"><span data-stu-id="8e479-122">c.</span></span> <span data-ttu-id="8e479-123">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="8e479-124">d.</span><span class="sxs-lookup"><span data-stu-id="8e479-124">d.</span></span> <span data-ttu-id="8e479-125">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8e479-126">쿼리에 검색 절을 더 추가하려면 **필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="8e479-127">e.</span><span class="sxs-lookup"><span data-stu-id="8e479-127">e.</span></span> <span data-ttu-id="8e479-128">**찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8e479-p108">PIN이 잠겨 있는 경우에는 PIN 잠금을 해제해야 설정할 수 있습니다. PIN 잠금을 해제하려면 사용자를 클릭하고 **동작** 을 클릭한 후에 **PIN 잠금 해제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="8e479-131">검색 결과에서 사용자를 클릭하고 **동작** 을 클릭한 후에 **PIN 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="8e479-132">**PIN 설정** 대화 상자에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="8e479-133">비즈니스용 Skype 서버에서 사용자의 PIN을 생성하도록 허용하려면 유효한 **PIN(기본값)을 자동으로** 생성하도록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="8e479-134">PIN을 직접 만들려면 **특정 PIN을 수동으로 입력** 을 클릭하고 텍스트 상자를 클릭한 후에 PIN 정책 설정에 지정된 PIN 요구 사항을 충족하는 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="8e479-135">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="8e479-136">**PIN 설정** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="8e479-137">**PIN 표시** 확인란을 선택하여 PIN을 표시한 다음 PIN을 복사하여 조직에서 사용하는 기본 방법을 통해 사용자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="8e479-p109">PIN을 전자 메일로 보내려면 **내 전자 메일 응용 프로그램을 열어 새 PIN을 사용자에게 보내기** 를 클릭합니다. Microsoft Office Outlook이 전자 메일 클라이언트인 경우 PIN이 새 전자 메일 메시지에 자동으로 복사됩니다. 다른 전자 메일 클라이언트를 사용하는 경우에는 **PIN 표시** 확인란을 선택하여 PIN을 표시한 다음 전자 메일 메시지에 PIN을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="8e479-141">**닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8e479-142">cmdlet을 사용하여 사용자 PIN Windows PowerShell 지정</span><span class="sxs-lookup"><span data-stu-id="8e479-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8e479-143">PIN 번호를 할당할 수도 있는 cmdlet을 사용하여 Set-CsClientPin 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="8e479-144">비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 이 cmdlet을 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e479-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8e479-145">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e479-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="8e479-146">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="8e479-147">사용자에게 PIN 번호를 자동 할당하는 경우</span><span class="sxs-lookup"><span data-stu-id="8e479-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="8e479-148">다음 명령은 Myer라는 사용자에게 PIN 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="8e479-149">Pin 매개 변수가 포함되지 않은 경우 비즈니스용 Skype 서버는 PIN 번호를 자동으로 생성하고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="8e479-150">사용자에게 특정 PIN 번호를 할당하기 위해</span><span class="sxs-lookup"><span data-stu-id="8e479-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="8e479-151">이 명령은 Pin 매개 변수를 사용해서 Ken Myer라는 사용자에게 PIN 번호 121989를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e479-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="8e479-152">자세한 내용은 [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e479-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

