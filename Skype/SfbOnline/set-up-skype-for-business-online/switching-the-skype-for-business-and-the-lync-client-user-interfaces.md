---
title: 비즈니스용 Skype와 Lync 클라이언트 사용자 인터페이스 간 전환
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Office 365에서 PowerShell을 사용 하 여 비즈니스용 Skype와 Lync 클라이언트 사용자 인터페이스 간 전환 하는 방법 알아보기 '
ms.openlocfilehash: 0f24879c136c98db1a856765cb164d376417ad5a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962886"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="018e7-103">비즈니스용 Skype와 Lync 클라이언트 사용자 인터페이스 간 전환</span><span class="sxs-lookup"><span data-stu-id="018e7-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

<span data-ttu-id="018e7-104">비즈니스용 Skype Online 조 직의 경우 Office 365의 원격 PowerShell을 사용 하 여 비즈니스용 Skype 사용자가 비즈니스용 skype 클라이언트 또는 비즈니스용 Skype (Lync) 클라이언트 사용자 인터페이스를 사용할 수 있도록 설정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-104">For Skype for Business Online organizations, you can use the Remote PowerShell in Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="018e7-105">기본 설정은 사용자가 비즈니스용 Skype 클라이언트 사용자 인터페이스를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-105">The default setting is for users to use the Skype for Business client user interface.</span></span> <span data-ttu-id="018e7-106">Lync 클라이언트 환경을 사용 하려는 경우이 항목의 뒷부분에 나오는 단계에 따라 첫 번째 시작 클라이언트 동작을 관리 하 여 Lync 사용자 인터페이스를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-106">If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="018e7-107">Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전에 대 한 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-107">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="018e7-108">Lync 2013 클라이언트를 사용 하도록 클라이언트 환경을 구성 하기 전에 클라이언트 버전을 확인 하 여 숫자 16으로 시작 되지 않는지 확인 하세요. 예: x.x.x.</span><span class="sxs-lookup"><span data-stu-id="018e7-108">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="018e7-109">사용자 인터페이스를 쉽게 전환 하 고 수동 단계를 수행 하지 않으려는 경우 PowerShell 스크립트의 [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?LinkId=532431) 를 참조 하 여 더 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="018e7-110">사용자의 비즈니스용 Skype 사용자 인터페이스 전환</span><span class="sxs-lookup"><span data-stu-id="018e7-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="018e7-111">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-111">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="018e7-112">64 비트 컴퓨터 에서만 지원 되는이 모듈은 [비즈니스용 Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-112">This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="018e7-113">다른 정보는 [비즈니스용 Skype Online 관리에 맞게 컴퓨터 구성을](https://go.microsoft.com/fwlink/?LinkId=534539)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="018e7-113">For other information, see [Configuring your computer for Skype for Business Online management](https://go.microsoft.com/fwlink/?LinkId=534539).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="018e7-114">사용자 인터페이스 전환에 대 한 _전역_ 정책 설정은 사용자 지정 정책이 이미 적용 된 사용자에 게 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-114">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied.</span></span> <span data-ttu-id="018e7-115">사용자 인터페이스를 변경할 수 있으려면 사용자 지정 정책이 적용 된 각 사용자에 대해 다음을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-115">To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="018e7-116">_ClientPolicyEnableSkypeUI_ 정책은 사용자에 대 한 기존 사용자 지정 정책 설정을 대체 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="018e7-117">조직의 모든 사용자가 비즈니스용 Skype 클라이언트를 사용 하도록 설정 하려면 원격 PowerShell을 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="018e7-118">정책 권한을 설정 하는 경우 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-118">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="018e7-120">조직의 모든 사용자가 비즈니스용 Skype (Lync) 클라이언트를 사용 하도록 설정 하려면 원격 PowerShell을 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="018e7-121">정책 권한을 설정 하는 경우 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-121">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="018e7-123">조직의 단일 사용자가 비즈니스용 Skype 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="018e7-124">정책 권한을 설정 하는 경우 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-124">If you set the policy right, you will see:</span></span>
  
![비즈니스용 Skype Online-UI 사용](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="018e7-126">조직의 단일 사용자가 비즈니스용 Skype (Lync) 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="018e7-127">정책 권한을 설정 하는 경우 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-127">If you set the policy right, you will see:</span></span>
  
![비즈니스용 Skype Online-UI 사용 안 함](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="018e7-129">조직의 여러 사용자가 비즈니스용 Skype 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-129">To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="018e7-130">조직의 여러 사용자가 비즈니스용 Skype (Lync) 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="018e7-131">조직의 사용자 그룹이 비즈니스용 Skype 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="018e7-132">조직의 사용자 그룹이 Skype for Business (Lync) 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="018e7-133">사용자 이름은 정책이 할당 되어야 하는 사용자 계정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-133">The user's name is the name of the user's account that the policy should be assigned to.</span></span> <span data-ttu-id="018e7-134">사용자의 계정 이름은 다음 형식 중 하나로 입력할 수 있습니다: 사용자의 사용자> 도메인\\사용자 이름에 대 한 UPN (>> 사용자의 SIP 주소) 사용자의 Active Directory 표시 이름></span><span class="sxs-lookup"><span data-stu-id="018e7-134">The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="018e7-135">Windows PowerShell을 사용 하 여 Lync Online 관리</span><span class="sxs-lookup"><span data-stu-id="018e7-135">Using Windows PowerShell to manage Lync Online</span></span>](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="018e7-136">비즈니스용 Skype Online 정책 설정</span><span class="sxs-lookup"><span data-stu-id="018e7-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="018e7-137">이 표에는 정책이 사용자에 게 처음 적용 될 때의 사용자 환경이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="018e7-138">**관리 정책 설정**</span><span class="sxs-lookup"><span data-stu-id="018e7-138">**Admin policy setting**</span></span>|<span data-ttu-id="018e7-139">**표시 되는 사용자 인터페이스**</span><span class="sxs-lookup"><span data-stu-id="018e7-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="018e7-140">정책이 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-140">The policy isn't set.</span></span> |<span data-ttu-id="018e7-141">이 사용자는 비즈니스용 Skype 클라이언트 사용자 인터페이스를 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-141">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|<span data-ttu-id="018e7-142">이 사용자는 비즈니스용 Skype 클라이언트 사용자 인터페이스를 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-142">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|<span data-ttu-id="018e7-143">사용자가 비즈니스용 Skype (Lync) 클라이언트 사용자 인터페이스로 전환 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-143">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="018e7-144">나중에 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-144">They can switch later.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|<span data-ttu-id="018e7-145">사용자가 비즈니스용 Skype 클라이언트 사용자 인터페이스를 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-145">The user will be using the Skype for Business client user interface.</span></span> |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|<span data-ttu-id="018e7-146">사용자가 비즈니스용 Skype (Lync) 클라이언트 사용자 인터페이스로 전환 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-146">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="018e7-147">관리자는 향후 비즈니스용 Skype 클라이언트 사용자 인터페이스로 전환 되는 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-147">An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="018e7-148">이 표에는 정책이 변경 되는 경우의 사용자 환경이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="018e7-149">**관리 정책 설정**</span><span class="sxs-lookup"><span data-stu-id="018e7-149">**Admin policy setting**</span></span>|<span data-ttu-id="018e7-150">**비즈니스용 Skype (Lync) 사용자 인터페이스**</span><span class="sxs-lookup"><span data-stu-id="018e7-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="018e7-151">**비즈니스용 Skype 사용자 인터페이스**</span><span class="sxs-lookup"><span data-stu-id="018e7-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|<span data-ttu-id="018e7-152">사용자가 비즈니스용 Skype 클라이언트 사용자 인터페이스로 전환 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="018e7-153">사용자가 계속 비즈니스용 Skype 클라이언트 사용자 인터페이스를 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|<span data-ttu-id="018e7-154">사용자가 계속 해 서 비즈니스용 Skype (Lync) 인터페이스를 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="018e7-155">사용자가 비즈니스용 Skype (Lync) 클라이언트 사용자 인터페이스로 전환 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="018e7-156">정책이 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="018e7-157">정책이 설정 되지 않은 경우 사용자는 비즈니스용 Skype (Lync) 클라이언트 사용자 인터페이스가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-157">Users will never see the Skype for Business (Lync) client user interface if the policy is not set.</span></span> <span data-ttu-id="018e7-158">항상 비즈니스용 Skype 클라이언트 사용자 인터페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-158">They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="018e7-159">사용자가 계속 비즈니스용 Skype 클라이언트 사용자 인터페이스를 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="018e7-160">이 표에는 사용 가능한 모든 온라인 사용자 지정 정책이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-160">This table shows all the Online custom policies available.</span></span> <span data-ttu-id="018e7-161">EnableSkypeUI 플래그 간에 전환 하는 동안 이전 사용자 지정 정책을 유지 하는 데 관리자의 융통성을 제공 하기 위해 생성 된 새 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-161">There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags.</span></span> <span data-ttu-id="018e7-162">위의 cmdlet을 사용 하 여 아래 정책 중 하나를 사용자에 게 부여 하세요.</span><span class="sxs-lookup"><span data-stu-id="018e7-162">Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="018e7-163">**정책 이름**</span><span class="sxs-lookup"><span data-stu-id="018e7-163">**Policy name**</span></span>|<span data-ttu-id="018e7-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="018e7-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |<span data-ttu-id="018e7-165">해제</span><span class="sxs-lookup"><span data-stu-id="018e7-165">False</span></span>|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |<span data-ttu-id="018e7-166">해제</span><span class="sxs-lookup"><span data-stu-id="018e7-166">False</span></span>|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |<span data-ttu-id="018e7-167">해제</span><span class="sxs-lookup"><span data-stu-id="018e7-167">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |<span data-ttu-id="018e7-168">해제</span><span class="sxs-lookup"><span data-stu-id="018e7-168">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |<span data-ttu-id="018e7-169">해제</span><span class="sxs-lookup"><span data-stu-id="018e7-169">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|<span data-ttu-id="018e7-170">해제</span><span class="sxs-lookup"><span data-stu-id="018e7-170">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |<span data-ttu-id="018e7-171">해제</span><span class="sxs-lookup"><span data-stu-id="018e7-171">False</span></span>|

   
<span data-ttu-id="018e7-172">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="018e7-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- [<span data-ttu-id="018e7-173">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="018e7-173">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [<span data-ttu-id="018e7-174">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="018e7-174">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="018e7-175">첫 번째 클라이언트 동작 시작</span><span class="sxs-lookup"><span data-stu-id="018e7-175">First launch client behaviors</span></span>

<span data-ttu-id="018e7-176">기본적으로 사용자가 비즈니스용 Skype를 처음 실행할 때, 앞에서 설명한 대로 클라이언트 정책을 Lync 클라이언트 환경 (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`)으로 설정 하 여 lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 skype 사용자 인터페이스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-176">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously.</span></span> <span data-ttu-id="018e7-177">몇 분 후에 사용자에 게 Lync 모드로 전환 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-177">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="018e7-178">사용자가 비즈니스용 Skype 클라이언트를 처음 실행할 때 Lync 사용자 인터페이스를 표시 하려는 경우 클라이언트를 업데이트 한 후 처음 시작 하기 전에 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="018e7-179">이 항목의 앞에 나오는 단계를 따라 클라이언트 정책이 비즈니스용 Skype 사용자 인터페이스를 사용 하지 않도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="018e7-180">사용자의 컴퓨터에서 시스템 레지스트리를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-180">Update the system registry on the user's computer.</span></span> <span data-ttu-id="018e7-181">사용자가 비즈니스용 Skype 클라이언트를 처음 시작 하기 전에이 작업을 수행 하 고이 작업을 한 번만 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-181">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="018e7-182">도메인에 가입 된 컴퓨터에서 그룹 정책 개체를 만들어 레지스트리를 업데이트 하는 방법에 대 한 자세한 내용은이 항목의 뒷부분에 있는 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="018e7-182">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="018e7-183">**[HKEY_CURRENT_USER\\소프트웨어\\Microsoft\\Office\\Lync]** 키에서 새 **이진** 값을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="018e7-184">**값 이름은** **EnableSkypeUI**이어야 하며 **값 데이터** 를 **00 00 00 00**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="018e7-185">키의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="018e7-186">[HKEY_CURRENT_USER\\소프트웨어\\Microsoft\\Office\\Lync]</span><span class="sxs-lookup"><span data-stu-id="018e7-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="018e7-187">"CanSharePptInCollab" = dword: 00000001</span><span class="sxs-lookup"><span data-stu-id="018e7-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="018e7-188">"CanShareOneNoteInCollab" = dword: 00000001</span><span class="sxs-lookup"><span data-stu-id="018e7-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="018e7-189">"CanAppShareInCollab" = dword: 00000001</span><span class="sxs-lookup"><span data-stu-id="018e7-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="018e7-190">"EnableSkypeUI" = hex: 00, 00, 00, 00</span><span class="sxs-lookup"><span data-stu-id="018e7-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="018e7-191">이제 사용자가 비즈니스용 Skype 클라이언트를 처음 실행할 때 Lync 사용자 인터페이스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="018e7-192">시작 화면 자습서의 표시 제어</span><span class="sxs-lookup"><span data-stu-id="018e7-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="018e7-193">사용자가 비즈니스용 Skype 클라이언트를 열 때 기본 동작은 *가장 사용자가 질문 하는 7 가지 간단한 팁*을 포함 하는 시작 화면을 표시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-193">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="018e7-194">시작 화면 표시를 해제할 수 있지만, 클라이언트 컴퓨터에서 다음 레지스트리 값을 추가 하 여 사용자가 자습서에 액세스 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-194">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="018e7-195">**[\\HKEY_CURRENT_USER 소프트웨어\\Microsoft\\Office\\15.0\\Lync]** 키에서 새 **dword(32 (32 비트) 값**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-195">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="018e7-196">**값 이름은** **IsBasicTutorialSeenByUser**이어야 하며 **값 데이터** 는 **1**로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-196">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="018e7-197">키의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-197">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="018e7-198">클라이언트 자습서 끄기</span><span class="sxs-lookup"><span data-stu-id="018e7-198">Turn off the client tutorial</span></span>

<span data-ttu-id="018e7-199">사용자가 자습서에 액세스할 수 없게 하려면 다음 레지스트리 값을 사용 하 여 클라이언트 자습서를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="018e7-200">**[\\HKEY_CURRENT_USER 소프트웨어\\Microsoft\\Office\\15.0\\Lync]** 키에서 새 **dword(32 (32 비트) 값**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-200">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="018e7-201">**값 이름은** **TutorialFeatureEnabled**이어야 하며 **값 데이터** 는 **0**으로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-201">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```PowerShell
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="018e7-202">**값 데이터** 를 **1**로 설정 하 여 자습서를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="018e7-203">도메인에 가입 된 컴퓨터에서 그룹 정책 개체를 만들어 레지스트리 수정</span><span class="sxs-lookup"><span data-stu-id="018e7-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="018e7-204">사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작할 때 Lync 클라이언트 환경을 표시 하는 레지스트리 업데이트는 한 번만 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-204">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="018e7-205">GPO (그룹 정책 개체)를 사용 하 여 레지스트리를 업데이트 하는 경우 값 데이터를 업데이트 하는 대신 새 값을 만들기 위해 개체를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-205">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="018e7-206">GPO가 적용 되 면 새 값이 없는 경우 GPO가 생성 하 고 값 데이터를 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-206">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="018e7-207">다음 절차에서는 사용자가 비즈니스용 Skype를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 레지스트리를 수정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-207">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="018e7-208">또한 앞에서 설명한 대로이 절차를 사용 하 여 레지스트리를 업데이트 하 여 시작 화면 자습서를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-208">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="018e7-209">**GPO를 만들려면**</span><span class="sxs-lookup"><span data-stu-id="018e7-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="018e7-210">**그룹 정책 관리 콘솔**을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="018e7-211">그룹 정책 관리 콘솔을 사용 하는 방법에 대 한 자세한 내용은 [그룹 정책 관리 콘솔](https://go.microsoft.com/fwlink/?LinkId=532759)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="018e7-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="018e7-212">**그룹 정책 개체** 노드를 마우스 오른쪽 단추로 클릭 하 고 메뉴에서 **새로 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="018e7-213">**새 gpo** 대화 상자에서 GPO 이름 (예: MakeLyncDefaultUI)을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="018e7-214">방금 만든 새 GPO를 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="018e7-215">**그룹 정책 관리 편집기**에서 **사용자 구성**, **기본 설정**, **Windows 설정을**차례로 확장 한 다음 **레지스트리** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="018e7-216">**레지스트리** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새** > **레지스트리 항목**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="018e7-217">**새 레지스트리 속성** 대화 상자에서 다음을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="018e7-218">**칸**</span><span class="sxs-lookup"><span data-stu-id="018e7-218">**Field**</span></span>|<span data-ttu-id="018e7-219">**선택 하거나 입력할 값**</span><span class="sxs-lookup"><span data-stu-id="018e7-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="018e7-220">**작업**</span><span class="sxs-lookup"><span data-stu-id="018e7-220">**Action**</span></span> <br/> |<span data-ttu-id="018e7-221">**만드는**</span><span class="sxs-lookup"><span data-stu-id="018e7-221">**Create**</span></span> <br/> |
|<span data-ttu-id="018e7-222">**벌**</span><span class="sxs-lookup"><span data-stu-id="018e7-222">**Hive**</span></span> <br/> | <span data-ttu-id="018e7-223">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="018e7-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="018e7-224">**키 경로**</span><span class="sxs-lookup"><span data-stu-id="018e7-224">**Key Path**</span></span> <br/> |<span data-ttu-id="018e7-225">소프트웨어\\Microsoft\\Office\\Lync</span><span class="sxs-lookup"><span data-stu-id="018e7-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="018e7-226">**값 이름**</span><span class="sxs-lookup"><span data-stu-id="018e7-226">**Value name**</span></span> <br/> |<span data-ttu-id="018e7-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="018e7-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="018e7-228">**값 형식**</span><span class="sxs-lookup"><span data-stu-id="018e7-228">**Value type**</span></span> <br/> |<span data-ttu-id="018e7-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="018e7-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="018e7-230">**값 데이터**</span><span class="sxs-lookup"><span data-stu-id="018e7-230">**Value data**</span></span> <br/> |<span data-ttu-id="018e7-231">00000000</span><span class="sxs-lookup"><span data-stu-id="018e7-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="018e7-232">**확인** 을 클릭 하 여 변경 내용을 저장 한 다음 GPO를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="018e7-233">다음에는 OU와 같이 정책을 할당 하려는 사용자의 그룹에 만든 GPO를 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="018e7-234">**GPO를 사용 하 여 정책 할당**</span><span class="sxs-lookup"><span data-stu-id="018e7-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="018e7-235">그룹 정책 관리 콘솔에서 정책을 할당 하려는 OU를 마우스 오른쪽 단추로 클릭 한 다음 **기존 GPO에 연결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="018e7-236">**Gpo 선택** 대화 상자에서 사용자가 만든 gpo를 선택한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="018e7-237">대상 사용자의 컴퓨터에서 명령 프롬프트를 열고 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="018e7-238">**gpupdate/target: user**</span><span class="sxs-lookup"><span data-stu-id="018e7-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="018e7-239">"정책 업데이트 중 ..." 메시지가 나타난다 GPO가 적용 되는 동안 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-239">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="018e7-240">완료 되 면 "사용자 정책 업데이트 완료 됨" 이라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-240">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="018e7-241">명령 프롬프트에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="018e7-242">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="018e7-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="018e7-243">아래에 표시 한 GPO의 이름과 함께 "할당 된 그룹 정책 개체"가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="018e7-244">또한, 레지스트리를 검사 하 여 GPO가 사용자 컴퓨터의 레지스트리를 성공적으로 업데이트 했는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-244">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="018e7-245">레지스트리 편집기를 열고 **[HKEY_CURRENT_USER\\소프트웨어\\Microsoft\\Office\\Lync]** 키로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-245">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key.</span></span> <span data-ttu-id="018e7-246">GPO가 성공적으로 레지스트리를 업데이트 하면 값이 0 인 EnableSkypeUI 이라는 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="018e7-246">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="018e7-247">관련 주제</span><span class="sxs-lookup"><span data-stu-id="018e7-247">Related topics</span></span>
[<span data-ttu-id="018e7-248">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="018e7-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="018e7-249">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="018e7-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
