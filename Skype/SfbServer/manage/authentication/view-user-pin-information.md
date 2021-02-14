---
title: 비즈니스용 Skype 서버에서 사용자 PIN 정보 보기
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
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: '요약: 비즈니스용 Skype 서버에서 사용자 PIN 정보를 볼 수 있습니다.'
ms.openlocfilehash: fa5385c1ca318c4a41e17088368d9928fd6d0e0b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806508"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="6adfe-103">비즈니스용 Skype 서버에서 사용자 PIN 정보 보기</span><span class="sxs-lookup"><span data-stu-id="6adfe-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="6adfe-104">**요약:** 비즈니스용 Skype 서버에서 사용자 PIN 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="6adfe-105">인증된 사용자로 전화 접속 회의에 참가하려면 AD DS(Active Directory 도메인 서비스) 자격 증명이 있는 비즈니스용 Skype 서버 사용자에게는 개인식별번호(PIN)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="6adfe-106">비즈니스용 Skype 서버 제어판에서 사용자의 PIN 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6adfe-107">PIN이 설정되었는지 여부 또는 PIN이 마지막으로 변경된 시간 등의 PIN 상태 정보를 볼 수 있지만 PIN 상태로 조회해서 현재 PIN을 볼 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="6adfe-108">사용자가 PIN을 분실한 경우 비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN 설정 절차에 따라 PIN을 다시 설정할 [수 있습니다.](set-a-user-s-dial-in-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="6adfe-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="6adfe-109">비즈니스용 Skype 서버 제어판에서 사용자의 PIN을 표시</span><span class="sxs-lookup"><span data-stu-id="6adfe-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6adfe-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6adfe-111">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="6adfe-112">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="6adfe-113">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="6adfe-114">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="6adfe-115">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="6adfe-116">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="6adfe-117">a.</span><span class="sxs-lookup"><span data-stu-id="6adfe-117">a.</span></span> <span data-ttu-id="6adfe-118">**필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="6adfe-119">b.</span><span class="sxs-lookup"><span data-stu-id="6adfe-119">b.</span></span> <span data-ttu-id="6adfe-120">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="6adfe-121">c.</span><span class="sxs-lookup"><span data-stu-id="6adfe-121">c.</span></span> <span data-ttu-id="6adfe-122">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="6adfe-123">d.</span><span class="sxs-lookup"><span data-stu-id="6adfe-123">d.</span></span> <span data-ttu-id="6adfe-124">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6adfe-125">쿼리에 검색 절을 더 추가하려면 **필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="6adfe-126">e.</span><span class="sxs-lookup"><span data-stu-id="6adfe-126">e.</span></span> <span data-ttu-id="6adfe-127">**찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6adfe-p108">PIN이 잠겨 있는 경우에는 PIN 잠금을 해제해야 설정할 수 있습니다. PIN 잠금을 해제하려면 사용자를 클릭하고 **동작** 을 클릭한 후에 **PIN 잠금 해제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="6adfe-130">검색 결과에서 사용자를 클릭하고 **동작** 을 클릭한 후에 **PIN 상태 보기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6adfe-131">cmdlet을 사용하여 사용자 PIN Windows PowerShell 보기</span><span class="sxs-lookup"><span data-stu-id="6adfe-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="6adfe-132">Get-CsClientPinInfo cmdlet을 사용하여 사용자 PIN 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="6adfe-133">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6adfe-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6adfe-134">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6adfe-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6adfe-135">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="6adfe-136">사용자 PIN 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="6adfe-136">To view user PIN information</span></span>

<span data-ttu-id="6adfe-137">사용자의 PIN 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에서 다음과 비슷한 명령을 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="6adfe-138">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6adfe-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="6adfe-139">자세한 내용은 [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6adfe-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6adfe-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6adfe-140">See also</span></span>

[<span data-ttu-id="6adfe-141">비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN 설정</span><span class="sxs-lookup"><span data-stu-id="6adfe-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="6adfe-142">비즈니스용 Skype 서버에서 사용자 PIN 잠금 또는 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="6adfe-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
