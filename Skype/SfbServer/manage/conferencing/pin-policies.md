---
title: 비즈니스용 Skype 서버에서 전화 접속 회의에 대한 PIN 정책 관리
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
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의에 대한 PIN 정책을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 6544586071f1107537232a117de196dfbffeb4aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827958"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="35049-103">비즈니스용 Skype 서버에서 전화 접속 회의에 대한 PIN 정책 관리</span><span class="sxs-lookup"><span data-stu-id="35049-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="35049-104">**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의에 대한 PIN 정책을 관리하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="35049-105">조직에서 AD DS(Active Directory 도메인 서비스) 자격 증명이 있는 비즈니스용 Skype 서버 사용자는 PIN(개인 식별 번호)을 사용하여 인증된 사용자로 전화 접속 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="35049-106">PIN 정책은 전화 접속 회의 PIN의 작동 방식에 대한 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="35049-107">전체 조직에 대해 동일한 PIN 정책을 사용하려는 경우 전역 PIN 정책을 사용하여 필요할 때 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="35049-108">전역 PIN 정책은 포리스트 수준의 전화 접속 회의 PIN에 대한 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-108">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="35049-109">전역 PIN 정책을 수정할 수는 있지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-109">You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="35049-110">특정 정책을 사이트 또는 특정 사용자 그룹에 적용하려는 경우 새 PIN 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="35049-111">PIN 정책은 가장 좁은 범위에서 가장 넓은 범위까지 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35049-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="35049-112">사용자에게 사용자 수준 PIN 정책을 할당하는 경우 해당 설정이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="35049-113">사용자 정책을 할당하지 않는 경우 사이트 수준 PIN 정책이 적용됩니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="35049-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="35049-114">사용자 또는 사이트 정책이 적용되지 않는다면 전역 PIN 정책이 기본 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="35049-115">PIN 정책에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="35049-115">View information about PIN policies</span></span>

<span data-ttu-id="35049-116">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 PIN 정책에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="35049-117">비즈니스용 Skype 서버 제어판을 사용하여 PIN 정책에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="35049-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="35049-118">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="35049-119">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="35049-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="35049-120">왼쪽 탐색 모음에서 **회의** 를 클릭하고 **PIN 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="35049-121">PIN 정책 **페이지에서** 보하려는 PIN 정책을 클릭하고 **편집을** 클릭한 다음 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="35049-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="35049-122">비즈니스용 Skype 서버 관리 셸을 사용하여 PIN 정책에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="35049-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="35049-123">PIN 정책에 대한 정보를 보시다시피 **Get-CsPinPolicy** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="35049-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="35049-124">예를 들어 다음 명령은 ID가 site:Redmond인 단일 PIN 정책에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="35049-125">전체 구문 설명 및 매개 변수 목록을 비롯한 자세한 내용은 [Get-CsPinPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="35049-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="35049-126">전역 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="35049-126">Modify the global PIN policy</span></span>

<span data-ttu-id="35049-127">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 전역 PIN 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="35049-128">비즈니스용 Skype 서버 제어판을 사용하여 전역 전화 접속 회의 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="35049-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="35049-129">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="35049-130">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="35049-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="35049-131">왼쪽 탐색 모음에서 **회의** 를 클릭하고 **PIN 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="35049-132">**PIN 정책** 페이지에서 **전역** 정책을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="35049-p105">**PIN 정책 편집** 의 **최소 PIN 길이** 에서 허용할 최소 PIN 길이를 입력하거나 선택합니다. 기본 최소 길이는 5자리입니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="35049-p106">사용자가 잠길 때까지의 최대 로그온 시도 횟수를 지정하려면 **최대 로그온 시도 횟수 지정** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN 길이에 따라 최대 로그온 시도 횟수가 자동으로 결정됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="35049-138">**최대 로그온 시도 횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도 횟수** 에 허용할 최대 로그온 시도 횟수를 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="35049-p107">PIN이 만료되도록 하려면 **PIN 만료 사용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN이 만료되지 않습니다. 기본적으로 PIN은 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="35049-142">**PIN 만료 사용** 확인란을 선택한 경우 **다음 이후 PIN 만료(일)** 에 PIN이 만료될 때까지의 기간(일)을 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="35049-p108">**PIN 기록 카운트** 에 사용자가 PIN을 다시 사용할 수 있을 때까지 만들어야 하는 PIN의 개수를 입력합니다. 기본적으로 사용자는 PIN을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="35049-p109">PIN에서 연속하는 숫자, 반복되는 숫자 집합 등의 공통 숫자 패턴을 허용하려면 **공통 패턴 허용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 복잡한 숫자 패턴만 허용됩니다. 기본적으로는 복잡한 숫자 패턴만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="35049-148">보안상의 이유로 Microsoft는 공통 패턴을 허용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="35049-149">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="35049-150">비즈니스용 Skype 서버 관리 셸을 사용하여 전역 전화 접속 회의 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="35049-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="35049-151">전역 전화 접속 회의 PIN 정책을 수정하려면 **Set-CsPinPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="35049-152">다음 명령은 조직에서 사용하도록 구성된 모든 PIN 정책의 MinPasswordLength 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-152">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization.</span></span> <span data-ttu-id="35049-153">이 작업을 위해 명령은 먼저 매개 변수 없이 **Get-CsPinPolicy** cmdlet을 호출하여 모든 기존 PIN 정책의 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-153">To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies.</span></span> <span data-ttu-id="35049-154">이 컬렉션은 **Set-CsPinPolicy** cmdlet에 파이프됩니다. 이 cmdlet은 컬렉션의 각 정책에 대한 MinPasswordLength 속성 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-154">That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="35049-155">전체 구문 설명 및 매개 변수 목록을 비롯한 자세한 내용은 [Set-CsPinPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="35049-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="35049-156">사용자 또는 사이트 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="35049-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="35049-157">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 또는 사이트 PIN 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="35049-158">비즈니스용 Skype 서버 제어판을 사용하여 사용자 또는 사이트 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="35049-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="35049-159">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="35049-160">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="35049-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="35049-161">왼쪽 탐색 모음에서 **회의** 를 클릭하고 **PIN 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="35049-162">**PIN 정책** 페이지에서 **새로 만들기** 를 클릭한 다음, 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="35049-p111">사용자 수준 정책을 만들려면 **사용자 정책** 을 클릭합니다. **새 PIN 정책** 의 **이름** 에 정책에 대해 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="35049-p112">사이트 수준 정책을 만들려면 **사이트 정책** 을 클릭합니다. **사이트 선택** 검색 필드에 정책을 만들 사이트의 이름 전부 또는 일부를 입력합니다. 사이트 목록에서 원하는 사이트를 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="35049-168">**설명** 필드에 PIN 정책에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="35049-p113">**최소 PIN 길이** 필드에서 허용할 최소 PIN 길이를 입력하거나 선택합니다. 기본 최소 길이는 5자리입니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="35049-p114">사용자가 잠길 때까지의 최대 로그온 시도 횟수를 지정하려면 **최대 로그온 시도 횟수 지정** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN 길이에 따라 최대 로그온 시도 횟수가 자동으로 결정됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="35049-174">**최대 로그온 시도 횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도 횟수** 에 허용할 최대 로그온 시도 횟수를 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="35049-p115">PIN이 만료되도록 하려면 **PIN 만료 사용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN이 만료되지 않습니다. 기본적으로 PIN은 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="35049-178">**PIN 만료 사용** 확인란을 선택한 경우 **다음 이후 PIN 만료(일)** 에 PIN이 만료될 때까지의 기간(일)을 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="35049-p116">**PIN 기록 카운트** 에 사용자가 PIN을 다시 사용할 수 있을 때까지 만들어야 하는 PIN의 개수를 입력합니다. 기본적으로 사용자는 PIN을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="35049-p117">PIN에서 연속하는 숫자, 반복되는 숫자 집합 등의 공통 숫자 패턴을 허용하려면 **공통 패턴 허용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 복잡한 숫자 패턴만 허용됩니다. 기본적으로는 복잡한 숫자 패턴만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35049-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="35049-184">보안상의 이유로 Microsoft는 공통 패턴을 허용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="35049-185">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="35049-186">비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 또는 사이트 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="35049-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="35049-187">사용자 또는 사이트 PIN 정책을 만들 경우 **New-CsPinPolicy** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="35049-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="35049-188">다음 명령은 ID가 site:Redmond인 새 PIN 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35049-188">The following command creates a new PIN policy with the Identity site:Redmond.</span></span> <span data-ttu-id="35049-189">이 명령에는 MinPasswordLength 속성을 7로 설정하는 데 사용되는 하나의 선택적 매개 변수인 MinPasswordLength만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="35049-189">This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7.</span></span> <span data-ttu-id="35049-190">나머지 모든 정책 속성은 기본값을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="35049-190">All the remaining policy properties will be configured using the default values.</span></span>
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="35049-191">전체 구문 설명 및 매개 변수 목록을 비롯한 자세한 내용은 [New-CsPinPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="35049-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="35049-192">사용자 또는 사이트 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="35049-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="35049-193">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 또는 사이트 PIN 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="35049-194">비즈니스용 Skype 서버 제어판을 사용하여 사용자 또는 사이트 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="35049-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="35049-195">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="35049-196">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="35049-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="35049-197">왼쪽 탐색 모음에서 **회의** 를 클릭하고 **PIN 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="35049-198">**PIN 정책** 페이지에서 변경할 PIN 정책을 클릭한 다음 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="35049-199">**PIN 정책 편집** 에서 원하는 정책 설정을 수정합니다(이름은 수정할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="35049-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="35049-200">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="35049-201">비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 또는 사이트 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="35049-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="35049-202">전화 접속 회의 PIN 정책을 수정하려면 **Set-CsPinPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="35049-203">다음 명령은 Redmond 사이트에 할당된 PIN 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-203">The following command modifies the PIN policy assigned to the Redmond site.</span></span> <span data-ttu-id="35049-204">이 경우 명령은 MinPasswordLength 속성 값을 10으로 변경합니다. 즉, 새 PI는 10자리 이상의 숫자를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-204">In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="35049-205">전체 구문 설명 및 매개 변수 목록을 비롯한 자세한 내용은 [Set-CsPinPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="35049-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="35049-206">사용자 또는 사이트 PIN 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="35049-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="35049-207">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 또는 사이트 PIN 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35049-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="35049-208">비즈니스용 Skype 서버 제어판을 사용하여 사용자 또는 사이트 PIN 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="35049-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="35049-209">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="35049-210">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="35049-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="35049-211">왼쪽 탐색 모음에서 **회의** 를 클릭하고 **PIN 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="35049-212">**PIN** 정책 페이지에서 변경할 PIN 정책을 클릭하고 **편집을** 클릭한 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="35049-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="35049-213">비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 또는 사이트 PIN 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="35049-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="35049-214">사용자 또는 사이트 PIN 정책을 삭제하려면 **Remove-CsPinPolicy** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="35049-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="35049-215">다음 명령은 사이트 범위에서 구성된 모든 PIN 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-215">The following command removes all the PIN policies that have been configured at the site scope.</span></span> <span data-ttu-id="35049-216">이 작업을 위해 Filter 매개 변수와 함께 **Get-CsPinPolicy** cmdlet을 사용하여 ID가 "site:" 문자로 시작하는 모든 정책 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-216">To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:".</span></span> <span data-ttu-id="35049-217">이 컬렉션은 **Remove-CsPinPolicy** cmdlet에 파이프됩니다. 이 cmdlet은 컬렉션의 각 정책을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="35049-217">This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="35049-218">전체 구문 설명 및 매개 변수 목록을 비롯한 자세한 내용은 [Remove-CsPinPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="35049-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

