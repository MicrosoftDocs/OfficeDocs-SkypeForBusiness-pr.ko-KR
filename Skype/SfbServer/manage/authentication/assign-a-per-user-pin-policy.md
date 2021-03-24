---
title: 비즈니스용 Skype 서버에서 사용자당 PIN 정책 할당
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
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: '요약: 비즈니스용 Skype 서버에 대해 AV 및 OAuth 인증서를 준비합니다.'
ms.openlocfilehash: a5cd533dccffb878fad7d7562ded3da301fc0ce3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096834"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="a15f2-103">비즈니스용 Skype 서버에서 사용자당 PIN 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a15f2-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="a15f2-104">**요약:** 비즈니스용 Skype 서버에 대한 AV 및 OAuth 인증서를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="a15f2-105">전화 접속 회의 PIN(개인 식별 번호) 정책은 비즈니스용 Skype 서버 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="a15f2-106">하나 이상의 사용자당 PIN 정책을 배포하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-106">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="a15f2-107">전역 수준 PIN 정책 또는 사이트 수준 PIN 정책만 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-107">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="a15f2-108">사용자별 정책을 배포하는 경우에는 해당 정책을 사용자, 그룹 또는 연락처 개체에 명시적으로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-108">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="a15f2-109">특정 사이트 수준 또는 사용자별 정책이 할당되지 않은 경우 전화 접속 회의에 PIN을 사용하는 데 관한 사용자 권한 및 사용 권한은 자동으로 전역 수준 PIN 정책에 정의된 권한으로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-109">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="a15f2-110">사용자당 PIN 정책을 하나 이상 만든 후 이 항목의 절차에 따라 서버에서 특정 사용자가 만들고 사용하는 PIN에 대해 부과할 제약 조건을 지정하는 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="a15f2-111">사용자당 PIN 정책을 할당하기 위해</span><span class="sxs-lookup"><span data-stu-id="a15f2-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="a15f2-112">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a15f2-113">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a15f2-114">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a15f2-115">다음 방법 중 하나를 통해 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="a15f2-116">**사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="a15f2-117">저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="a15f2-118">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="a15f2-119">a.</span><span class="sxs-lookup"><span data-stu-id="a15f2-119">a.</span></span> <span data-ttu-id="a15f2-120">**필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="a15f2-121">b.</span><span class="sxs-lookup"><span data-stu-id="a15f2-121">b.</span></span> <span data-ttu-id="a15f2-122">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="a15f2-123">c.</span><span class="sxs-lookup"><span data-stu-id="a15f2-123">c.</span></span> <span data-ttu-id="a15f2-124">**같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="a15f2-125">d.</span><span class="sxs-lookup"><span data-stu-id="a15f2-125">d.</span></span> <span data-ttu-id="a15f2-126">선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a15f2-127">쿼리에 검색 절을 더 추가하려면 **필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="a15f2-128">e.</span><span class="sxs-lookup"><span data-stu-id="a15f2-128">e.</span></span> <span data-ttu-id="a15f2-129">**찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="a15f2-130">검색 결과에서 사용자를 클릭하고 **동작** 을 클릭한 후에 **정책 할당** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a15f2-131">동일한 사용자당 PIN 정책을 여러 사용자에게 적용하려면 검색 결과에서 여러 사용자를 선택한 다음 작업을 **클릭한** 다음 정책 **할당을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a15f2-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="a15f2-132">정책 **할당 에서** **PIN 정책** 아래에서 다음 중 하나를 합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a15f2-133">정책 할당 대화 상자를 사용하여 구성할 수 있는 정책이 여러 개이기 때문에 대화 상자의 모든 정책에 대해 기본적으로  **\<Keep as is\>** 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="a15f2-134">이 설정을 변경하지 않으면 이전에 사용자에게 지정된 정책이 계속 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="a15f2-135">비즈니스용 Skype 서버에서 전역 수준 정책 또는 사이트 수준 정책(정의된 경우)을 자동으로 선택하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="a15f2-136">PIN 정책 페이지에서 이전에 정의한 사용자당 PIN 정책의 **이름을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="a15f2-137">지정할 정책을 쉽게 결정하려면 정책 이름을 클릭한 후 **보기** 를 클릭하여 정책에 정의된 사용자 권한 및 권한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="a15f2-138">작업을 마치면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a15f2-139">cmdlet을 Per-User PIN 정책 Windows PowerShell 지정</span><span class="sxs-lookup"><span data-stu-id="a15f2-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a15f2-140">사용자당 PIN 정책은 **Grant-CsPinPolicy** cmdlet과 Windows PowerShell 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="a15f2-141">비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a15f2-142">원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버에 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="a15f2-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a15f2-143">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="a15f2-144">단일 사용자에게 사용자당 PIN 정책을 할당하는 경우</span><span class="sxs-lookup"><span data-stu-id="a15f2-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="a15f2-145">다음 명령은 사용자 Ken Myer에게 사용자당 PIN 정책 RedmondPinPolicy를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="a15f2-146">여러 사용자에게 사용자당 PIN 정책을 할당하기 위해</span><span class="sxs-lookup"><span data-stu-id="a15f2-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="a15f2-147">다음 명령은 Redmond 시에서 작업하는 모든 사용자에게 사용자당 PIN 정책 RedmondUsersPinPolicy를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="a15f2-148">이 명령에 사용되는 LdapFilter 매개 변수에 대한 자세한 내용은 [Get-CsUser를 참조합니다.](/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a15f2-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="a15f2-149">사용자당 PIN 정책의 위임</span><span class="sxs-lookup"><span data-stu-id="a15f2-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="a15f2-150">다음 명령은 이전에 Ken Myer에게 할당된 사용자당 PIN 정책을 할당을 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-150">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="a15f2-151">사용자별 정책을 지정 해제한 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용해서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-151">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="a15f2-152">사이트 정책은 글로벌 정책보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a15f2-152">A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="a15f2-153">자세한 내용은 [Grant-CsPinPolicy를 참조합니다.](/powershell/module/skype/grant-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a15f2-153">For details, see [Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a15f2-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a15f2-154">See also</span></span>

[<span data-ttu-id="a15f2-155">비즈니스용 Skype 서버에서 새 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a15f2-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)