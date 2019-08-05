---
title: 비즈니스용 Skype 서버에서 전화 접속 회의를 위한 PIN 정책 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의를 위한 PIN 정책을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: a8db6fc0398d2f577afe54ab2289c3122adcb197
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188925"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="980a4-103">비즈니스용 Skype 서버에서 전화 접속 회의를 위한 PIN 정책 관리</span><span class="sxs-lookup"><span data-stu-id="980a4-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="980a4-104">**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의를 위한 PIN 정책을 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="980a4-105">조직의 AD DS (Active Directory 도메인 서비스) 자격 증명이 있는 비즈니스용 Skype 서버 사용자는 PIN (개인 식별 번호)을 사용 하 여 인증 된 사용자로 전화 접속 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="980a4-106">고정 정책 전화 접속 회의 핀이 작동 하는 방법에 대 한 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="980a4-107">전체 조직에 동일한 PIN 정책을 사용 하려는 경우 전역 PIN 정책을 사용 하 고 필요에 따라 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="980a4-108">글로벌 PIN 정책은 포리스트 수준의 전화 접속 회의 핀에 대 한 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-108">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="980a4-109">글로벌 PIN 정책은 수정할 수 있지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-109">You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="980a4-110">특정 정책을 사이트 또는 특정 사용자 그룹에 적용 하려는 경우 새 PIN 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="980a4-111">PIN 정책은 가장 좁은 범위의 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="980a4-112">사용자 수준 PIN 정책을 사용자에 게 할당 하면 해당 설정이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="980a4-113">사용자 정책을 할당 하지 않으면 사이트 수준 PIN 정책이 있는 경우 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="980a4-114">사용자 또는 사이트 정책이 적용 되지 않으면 글로벌 PIN 정책이 기본 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="980a4-115">고정 정책에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="980a4-115">View information about PIN policies</span></span>

<span data-ttu-id="980a4-116">비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 PIN 정책에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="980a4-117">비즈니스용 Skype Server 제어판을 사용 하 여 PIN 정책에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="980a4-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="980a4-118">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="980a4-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="980a4-119">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="980a4-120">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="980a4-121">**고정 정책** 페이지에서 보려는 pin 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="980a4-122">비즈니스용 Skype Server Management Shell을 사용 하 여 PIN 정책에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="980a4-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="980a4-123">핀 정책에 대 한 정보를 보려면 **CsPinPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="980a4-124">예를 들어 다음 명령은 Id 사이트: Redmond: 인 단일 PIN 정책에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="980a4-125">전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980a4-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="980a4-126">글로벌 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="980a4-126">Modify the global PIN policy</span></span>

<span data-ttu-id="980a4-127">비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 글로벌 PIN 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="980a4-128">비즈니스용 Skype Server 제어판을 사용 하 여 글로벌 전화 접속 회의 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="980a4-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="980a4-129">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="980a4-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="980a4-130">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="980a4-131">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="980a4-132">**고정 정책** 페이지에서 **전역** 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="980a4-133">**Pin 편집 정책**에서 **최소 pin 길이**에 허용 하려는 최소 pin 길이를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-133">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="980a4-134">기본 최소 길이는 다섯 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-134">The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="980a4-135">사용자가 잠길 때까지 허용 되는 최대 로그온 시도 횟수를 지정할 수 있으려면 **최대 로그온 시도 수 지정** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-135">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="980a4-136">이 옵션을 선택 하지 않으면 허용 되는 최대 시도 수는 PIN 길이에 따라 자동으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-136">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="980a4-137">기본적으로 최대 시도 횟수는 자동으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-137">By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="980a4-138">최대 로그온 시도 **횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도**에서 허용 하려는 최대 로그온 시도 횟수를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="980a4-139">핀이 만료 되 게 하려면 **PIN 만료 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-139">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="980a4-140">이 옵션을 선택 하지 않으면 Pin이 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-140">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="980a4-141">기본적으로 Pin은 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-141">By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="980a4-142">**Pin 만료 사용** 확인란을 선택한 경우 **pin이 (일) 후에 만료**되는 경우 해당 pin이 만료 되는 일 수를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="980a4-143">**Pin 기록 개수**에 사용자가 PIN을 다시 사용할 수 있으려면 먼저 사용자가 만들어야 하는 pin의 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-143">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="980a4-144">기본적으로 사용자는 Pin을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-144">By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="980a4-145">일련 번호와 반복 되는 숫자 집합 등의 일반 숫자 패턴을 허용 하려면 **일반 패턴 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-145">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="980a4-146">이 옵션을 선택 하지 않으면 복잡 한 자릿수의 숫자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-146">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="980a4-147">기본적으로 복잡 한 자릿수 패턴만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-147">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="980a4-148">보안상의 이유로, Microsoft에서는 일반적인 패턴을 허용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="980a4-149">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="980a4-150">비즈니스용 Skype Server Management Shell을 사용 하 여 전역 전화 접속 회의 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="980a4-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="980a4-151">전역 전화 접속 회의 PIN 정책을 수정 하려면 **CsPinPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="980a4-152">다음 명령은 조직에서 사용 하도록 구성 된 모든 PIN 정책에 대 한 MinPasswordLength 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-152">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization.</span></span> <span data-ttu-id="980a4-153">이렇게 하려면 명령은 먼저 모든 기존 PIN 정책의 컬렉션을 검색 하기 위해 매개 변수 없이 **CsPinPolicy** cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-153">To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies.</span></span> <span data-ttu-id="980a4-154">그런 다음 해당 컬렉션은 컬렉션의 각 정책에 대 한 MinPasswordLength 속성 값을 수정 하는 **Set CsPinPolicy** cmdlet으로 파이프 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-154">That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="980a4-155">전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980a4-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="980a4-156">사용자 또는 사이트 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="980a4-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="980a4-157">비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="980a4-158">비즈니스용 Skype Server 제어판을 사용 하 여 사용자 또는 사이트 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="980a4-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="980a4-159">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="980a4-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="980a4-160">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="980a4-161">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="980a4-162">**고정 정책** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="980a4-163">사용자 수준 정책을 만들려면 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-163">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="980a4-164">**새 PIN 정책의** **이름**에 정책을 설명 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-164">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="980a4-165">사이트 수준 정책을 만들려면 **사이트 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-165">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="980a4-166">사이트 검색 **선택** 필드에 정책을 만들려는 사이트 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-166">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="980a4-167">사이트 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-167">In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="980a4-168">**설명** 필드에 고정 정책에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="980a4-169">**최소 pin 길이** 필드에 허용 하려는 최소 pin 길이를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-169">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="980a4-170">기본 최소 길이는 다섯 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-170">The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="980a4-171">사용자가 잠길 때까지 허용 되는 최대 로그온 시도 횟수를 지정할 수 있으려면 **최대 로그온 시도 수 지정** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-171">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="980a4-172">이 옵션을 선택 하지 않으면 허용 되는 최대 시도 수는 PIN 길이에 따라 자동으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-172">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="980a4-173">기본적으로 최대 시도 횟수는 자동으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-173">By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="980a4-174">최대 로그온 시도 **횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도**에서 허용 하려는 최대 로그온 시도 횟수를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="980a4-175">핀이 만료 되 게 하려면 **PIN 만료 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-175">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="980a4-176">이 옵션을 선택 하지 않으면 Pin이 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-176">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="980a4-177">기본적으로 Pin은 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-177">By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="980a4-178">**Pin 만료 사용** 확인란을 선택한 경우 **pin이 (일) 후에 만료**되는 경우 해당 pin이 만료 되는 일 수를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="980a4-179">**Pin 기록 개수**에 사용자가 PIN을 다시 사용할 수 있으려면 먼저 사용자가 만들어야 하는 pin의 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-179">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="980a4-180">기본적으로 사용자는 Pin을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-180">By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="980a4-181">일련 번호와 반복 되는 숫자 집합 등의 일반 숫자 패턴을 허용 하려면 **일반 패턴 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-181">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="980a4-182">이 옵션을 선택 하지 않으면 복잡 한 자릿수의 숫자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-182">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="980a4-183">기본적으로 복잡 한 자릿수 패턴만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-183">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="980a4-184">보안상의 이유로, Microsoft에서는 일반적인 패턴을 허용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="980a4-185">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="980a4-186">비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="980a4-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="980a4-187">사용자 또는 사이트 PIN 정책을 만들려면 **새 CsPinPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="980a4-188">다음 명령은 Id 사이트: Redmond를 사용 하 여 새 PIN 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-188">The following command creates a new PIN policy with the Identity site:Redmond.</span></span> <span data-ttu-id="980a4-189">이 명령에는 MinPasswordLength 속성을 7로 설정 하는 데 사용 되는 선택적 매개 변수인 MinPasswordLength가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-189">This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7.</span></span> <span data-ttu-id="980a4-190">나머지 모든 정책 속성은 기본 값을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-190">All the remaining policy properties will be configured using the default values.</span></span>
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="980a4-191">전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980a4-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="980a4-192">사용자 또는 사이트 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="980a4-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="980a4-193">비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="980a4-194">비즈니스용 Skype Server 제어판을 사용 하 여 사용자 또는 사이트 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="980a4-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="980a4-195">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="980a4-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="980a4-196">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="980a4-197">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="980a4-198">**고정 정책** 페이지에서 변경 하려는 pin 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="980a4-199">**PIN 정책 편집**에서 정책 설정을 수정 합니다 (수정할 수 없는 정책 이름을 제외한).</span><span class="sxs-lookup"><span data-stu-id="980a4-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="980a4-200">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="980a4-201">비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="980a4-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="980a4-202">전화 접속 회의 PIN 정책을 수정 하려면 **Set-CsPinPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="980a4-203">다음 명령은 Redmond 사이트에 할당 된 PIN 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-203">The following command modifies the PIN policy assigned to the Redmond site.</span></span> <span data-ttu-id="980a4-204">이 경우 명령은 MinPasswordLength 속성 값을 10으로 변경 합니다. 즉, 새 Pin에는 최소 10 자리 숫자를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-204">In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="980a4-205">전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980a4-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="980a4-206">사용자 또는 사이트 PIN 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="980a4-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="980a4-207">비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="980a4-208">비즈니스용 Skype Server 제어판을 사용 하 여 사용자 또는 사이트 PIN 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="980a4-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="980a4-209">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="980a4-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="980a4-210">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="980a4-211">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="980a4-212">**고정 정책** 페이지에서 변경 하려는 pin 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="980a4-213">비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="980a4-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="980a4-214">사용자 또는 사이트 PIN 정책을 삭제 하려면 **CsPinPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="980a4-215">다음 명령을 사용 하 여 사이트 범위에서 구성 된 PIN 정책을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-215">The following command removes all the PIN policies that have been configured at the site scope.</span></span> <span data-ttu-id="980a4-216">이렇게 하려면 Filter 매개 변수와 함께 **CsPinPolicy** cmdlet을 사용 하 여 id가 "site:" 문자로 시작 하는 모든 정책의 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-216">To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:".</span></span> <span data-ttu-id="980a4-217">그런 다음이 컬렉션은 컬렉션의 각 정책을 삭제 하는 **CsPinPolicy** cmdlet으로 파이프 됩니다.</span><span class="sxs-lookup"><span data-stu-id="980a4-217">This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="980a4-218">전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="980a4-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

