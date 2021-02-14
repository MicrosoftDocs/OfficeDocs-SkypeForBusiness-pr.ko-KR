---
title: 비즈니스용 Skype 서버에서 사용자 PIN 잠금 또는 잠금 해제
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
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '요약: 비즈니스용 Skype 서버에 대한 사용자의 전화 접속 회의 PIN을 잠그거나 잠금을 해제합니다.'
ms.openlocfilehash: 73bd9affa159fba4ab35844896b9662eea3e1780
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828368"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="805b9-103">비즈니스용 Skype 서버에서 사용자 PIN 잠금 또는 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="805b9-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="805b9-104">**요약:** 비즈니스용 Skype 서버에 대한 사용자의 전화 접속 회의 PIN을 잠그거나 잠금을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="805b9-105">비즈니스용 Skype 서버 제어판의 **사용자** 섹션에서 사용자의 PIN을 잠그거나 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="805b9-106">비즈니스용 Skype 서버 제어판에서 사용자의 PIN을 잠그기 위해</span><span class="sxs-lookup"><span data-stu-id="805b9-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="805b9-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="805b9-108">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="805b9-109">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="805b9-110">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="805b9-111">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="805b9-112">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="805b9-113">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="805b9-114">a.</span><span class="sxs-lookup"><span data-stu-id="805b9-114">a.</span></span> <span data-ttu-id="805b9-115">**필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="805b9-116">b.</span><span class="sxs-lookup"><span data-stu-id="805b9-116">b.</span></span> <span data-ttu-id="805b9-117">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="805b9-118">c.</span><span class="sxs-lookup"><span data-stu-id="805b9-118">c.</span></span> <span data-ttu-id="805b9-119">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="805b9-120">d.</span><span class="sxs-lookup"><span data-stu-id="805b9-120">d.</span></span> <span data-ttu-id="805b9-121">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="805b9-122">쿼리에 검색 절을 더 추가하려면 **필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="805b9-123">e.</span><span class="sxs-lookup"><span data-stu-id="805b9-123">e.</span></span> <span data-ttu-id="805b9-124">**찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-124">Click **Find**.</span></span>
    
   <span data-ttu-id="805b9-125">f.</span><span class="sxs-lookup"><span data-stu-id="805b9-125">f.</span></span> <span data-ttu-id="805b9-126">사용자를 클릭하고, **작업** 을 클릭한 후 **PIN 잠금** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="805b9-127">비즈니스용 Skype 서버 제어판에서 사용자의 PIN 잠금을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="805b9-128">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="805b9-129">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="805b9-130">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="805b9-131">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="805b9-132">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="805b9-133">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="805b9-134">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="805b9-135">a.</span><span class="sxs-lookup"><span data-stu-id="805b9-135">a.</span></span> <span data-ttu-id="805b9-136">**필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="805b9-137">b.</span><span class="sxs-lookup"><span data-stu-id="805b9-137">b.</span></span> <span data-ttu-id="805b9-138">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="805b9-139">c.</span><span class="sxs-lookup"><span data-stu-id="805b9-139">c.</span></span> <span data-ttu-id="805b9-140">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="805b9-141">d.</span><span class="sxs-lookup"><span data-stu-id="805b9-141">d.</span></span> <span data-ttu-id="805b9-142">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="805b9-143">쿼리에 검색 절을 더 추가하려면 **필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="805b9-144">e.</span><span class="sxs-lookup"><span data-stu-id="805b9-144">e.</span></span> <span data-ttu-id="805b9-145">**찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-145">Click **Find**.</span></span>
    
   <span data-ttu-id="805b9-146">f.</span><span class="sxs-lookup"><span data-stu-id="805b9-146">f.</span></span> <span data-ttu-id="805b9-147">사용자를 클릭하고 **작업** 을 클릭한 후 **PIN 잠금 해제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="805b9-148">cmdlet을 사용하여 사용자 WINDOWS POWERSHELL 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="805b9-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="805b9-149">cmdlet 및 Windows PowerShell cmdlet을 사용하여 사용자 Lock-CsClientPin 잠금을 Unlock-CsClientPin 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="805b9-150">이러한 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버의 원격 세션에서 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="805b9-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="805b9-151">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="805b9-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="805b9-152">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="805b9-153">사용자 PIN을 잠그려면</span><span class="sxs-lookup"><span data-stu-id="805b9-153">To lock a user PIN</span></span>

- <span data-ttu-id="805b9-154">사용자의 PIN을 잠그기 위해 Lock-CsClientPin cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="805b9-155">예:</span><span class="sxs-lookup"><span data-stu-id="805b9-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="805b9-156">사용자 PIN의 잠금을 해제하려면</span><span class="sxs-lookup"><span data-stu-id="805b9-156">To unlock a user PIN</span></span>

- <span data-ttu-id="805b9-157">사용자 PIN의 잠금을 해제하기 위해 Unlock-CsClientPin cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="805b9-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="805b9-158">예시:</span><span class="sxs-lookup"><span data-stu-id="805b9-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="805b9-159">자세한 내용은 [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) 및 [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="805b9-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
