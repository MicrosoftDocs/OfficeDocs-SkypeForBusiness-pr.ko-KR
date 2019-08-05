---
title: 비즈니스용 Skype 서버에서 사용자 PIN 잠금 또는 잠금 해제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '요약: 비즈니스용 Skype 서버용 사용자의 전화 접속 회의 PIN을 잠그거나 잠금 해제 합니다.'
ms.openlocfilehash: 600ddcb507c7cb0074a651580c684590fa283602
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196472"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="35095-103">비즈니스용 Skype 서버에서 사용자 PIN 잠금 또는 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="35095-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="35095-104">**요약:** 비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN을 잠그거나 잠금 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="35095-105">비즈니스용 Skype Server 제어판의 **사용자** 섹션에서 사용자의 PIN을 잠그거나 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35095-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="35095-106">비즈니스용 Skype Server 제어판에서 사용자의 PIN을 잠그려면</span><span class="sxs-lookup"><span data-stu-id="35095-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="35095-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="35095-108">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="35095-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="35095-109">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="35095-110">사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="35095-111">사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="35095-112">저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="35095-113">) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="35095-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="35095-114">에서.</span><span class="sxs-lookup"><span data-stu-id="35095-114">a.</span></span> <span data-ttu-id="35095-115">**필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="35095-116">b.</span><span class="sxs-lookup"><span data-stu-id="35095-116">b.</span></span> <span data-ttu-id="35095-117">사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="35095-118">c.</span><span class="sxs-lookup"><span data-stu-id="35095-118">c.</span></span> <span data-ttu-id="35095-119">다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="35095-120">a.</span><span class="sxs-lookup"><span data-stu-id="35095-120">d.</span></span> <span data-ttu-id="35095-121">선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="35095-122">쿼리에 추가 검색 절을 추가 하려면 **필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="35095-123">z.e.n.works.</span><span class="sxs-lookup"><span data-stu-id="35095-123">e.</span></span> <span data-ttu-id="35095-124">**찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-124">Click **Find**.</span></span>
    
   <span data-ttu-id="35095-125">f.</span><span class="sxs-lookup"><span data-stu-id="35095-125">f.</span></span> <span data-ttu-id="35095-126">사용자를 클릭 하 고 **동작**을 클릭 한 다음 **핀**고정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="35095-127">비즈니스용 Skype Server 제어판에서 사용자의 PIN 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="35095-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="35095-128">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="35095-129">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="35095-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="35095-130">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="35095-131">사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="35095-132">사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="35095-133">저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="35095-134">) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="35095-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="35095-135">에서.</span><span class="sxs-lookup"><span data-stu-id="35095-135">a.</span></span> <span data-ttu-id="35095-136">**필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="35095-137">b.</span><span class="sxs-lookup"><span data-stu-id="35095-137">b.</span></span> <span data-ttu-id="35095-138">사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="35095-139">c.</span><span class="sxs-lookup"><span data-stu-id="35095-139">c.</span></span> <span data-ttu-id="35095-140">다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="35095-141">a.</span><span class="sxs-lookup"><span data-stu-id="35095-141">d.</span></span> <span data-ttu-id="35095-142">선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="35095-143">쿼리에 추가 검색 절을 추가 하려면 **필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="35095-144">z.e.n.works.</span><span class="sxs-lookup"><span data-stu-id="35095-144">e.</span></span> <span data-ttu-id="35095-145">**찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-145">Click **Find**.</span></span>
    
   <span data-ttu-id="35095-146">f.</span><span class="sxs-lookup"><span data-stu-id="35095-146">f.</span></span> <span data-ttu-id="35095-147">사용자를 클릭 하 고 **작업**을 클릭 한 다음 **PIN 잠금 해제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="35095-148">Windows PowerShell Cmdlet을 사용 하 여 사용자 Pin 잠금 및 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="35095-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="35095-149">Windows PowerShell 및 잠금-csclientpin cmdlet을 사용 하 여 사용자 Pin을 잠그고 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35095-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="35095-150">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35095-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="35095-151">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35095-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="35095-152">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="35095-153">사용자 PIN을 잠그려면</span><span class="sxs-lookup"><span data-stu-id="35095-153">To lock a user PIN</span></span>

- <span data-ttu-id="35095-154">사용자의 PIN을 잠그려면 Lock-CsClientPin cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="35095-155">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35095-155">For example:</span></span>
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="35095-156">사용자 PIN의 잠금을 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="35095-156">To unlock a user PIN</span></span>

- <span data-ttu-id="35095-157">사용자 PIN의 잠금을 해제 하려면 잠금 해제-CsClientPin cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35095-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="35095-158">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35095-158">For example:</span></span>
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="35095-159">자세한 내용은 [잠금 csclientpin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) 및 [잠금 해제-csclientpin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35095-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
