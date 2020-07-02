---
title: 팀 다이얼 패드 구성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: 사용자가 PSTN (공개 전환 전화 네트워크) 기능에 액세스할 수 있도록 팀 클라이언트에서 다이얼 패드를 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012423"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="fdd54-103">다이얼 패드 구성</span><span class="sxs-lookup"><span data-stu-id="fdd54-103">Dial pad configuration</span></span>

<span data-ttu-id="fdd54-104">팀 클라이언트에서 다이얼 패드를 통해 사용자는 PSTN (공용 전환 통신 네트워크) 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="fdd54-105">전화 걸기 패드는 적절 하 게 구성 된 경우에만 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="fdd54-106">다음 조건은 다이얼 패드가 표시 되는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="fdd54-107">사용자가 전화 시스템 ("MCOEV") 라이선스를 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="fdd54-108">사용자에 게 Microsoft 통화 계획이 있거나 직접 라우팅이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="fdd54-109">사용자가 엔터프라이즈 음성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="fdd54-110">사용자가 온라인 상태이 고 온-프레미스 비즈니스용 Skype가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="fdd54-111">사용자에 게 팀 호출 정책을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="fdd54-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="fdd54-112">다음 섹션에서는 PowerShell을 사용 하 여 조건을 확인 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="fdd54-113">대부분의 경우 CsOnlineUser cmdlet의 출력에서 다양 한 속성을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="fdd54-114">예를 들어 $user 사용자의 UPN 또는 sip 주소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="fdd54-115">사용자가 전화 시스템 ("MCOEV") 라이선스를 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="fdd54-116">사용자에 게 할당 된 요금제가 **사용으로 설정 된 CapabilityStatus 특성** 을 표시 하 고 **기능 계획이 mcoev** (전화 시스템 라이선스)으로 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="fdd54-117">MCOEV, MCOEV1 등이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="fdd54-118">기능 계획이 MCOEV로 시작 하는 한 모두 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="fdd54-119">특성이 올바르게 설정 되어 있는지 확인 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="fdd54-120">출력이 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-120">The output will look like the following.</span></span> <span data-ttu-id="fdd54-121">**CapabilityStatus** 및 **기능 계획** 특성만 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="fdd54-122">사용자에 게 Microsoft 통화 계획이 있거나 직접 라우팅이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="fdd54-123">**사용자에 게 Microsoft 통화 계획이 있는 경우** **CapabilityStatus 특성을 사용으로 설정**하 고 **기능 계획이 mcopstn으로 설정**되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="fdd54-124">MCOPSTN1, MCOPSTN2 등이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="fdd54-125">모든 기능 계획이 MCOPSTN으로 시작 하는 한 모든 것이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="fdd54-126">특성을 확인 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="fdd54-127">출력이 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-127">The output will look like the following.</span></span> <span data-ttu-id="fdd54-128">**CapabilityStatus** 및 **기능 계획** 특성만 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

<span data-ttu-id="fdd54-129">**사용자가 직접 라우팅을 사용할 수 있는 경우**에는 사용자에 게 OnlineVoiceRoutingPolicy에 대해 null이 아닌 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="fdd54-130">특성을 확인 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="fdd54-131">다음과 같이 출력에 null이 아닌 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="fdd54-132">사용자가 엔터프라이즈 음성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="fdd54-133">사용자가 Enterprise 음성을 사용할 수 있는지 확인 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="fdd54-134">출력 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="fdd54-135">사용자가 온라인 상태이 고 온-프레미스 비즈니스용 Skype가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="fdd54-136">사용자가 온라인 상태이 고 비즈니스용 Skype를 사용 하 고 있지 않은지 확인 하려면 RegistrarPool는 null이 아니어야 하 고 HostingProvider에 "sipfed. online"으로 시작 하는 값이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="fdd54-137">값을 확인 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="fdd54-138">출력은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="fdd54-139">사용자에 게 팀 호출 정책을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="fdd54-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="fdd54-140">사용자의 효과적인 TeamsCallingPolicy에는 AllowPrivateCalling이 true로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="fdd54-141">기본적으로 사용자는 기본적으로 AllowPrivateCallingPolicy를 true로 설정 하는 전역 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="fdd54-142">사용자에 대 한 TeamsCallingPolicy를 가져오고 AllowPrivateCalling가 true로 설정 되어 있는지 확인 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="fdd54-143">출력 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-143">The output should look like:</span></span>

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a><span data-ttu-id="fdd54-144">추가 참고 사항</span><span class="sxs-lookup"><span data-stu-id="fdd54-144">Additional notes</span></span>

-   <span data-ttu-id="fdd54-145">이러한 구성을 변경한 후 팀 클라이언트를 다시 시작 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="fdd54-146">최근에 위의 조건을 업데이트 한 경우에는 클라이언트가 새 설정을 받을 때까지 몇 시간 동안 기다려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="fdd54-147">여전히 다이얼 패드가 표시 되지 않으면 다음 명령을 사용 하 여 프로비저닝 오류가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd54-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="fdd54-148">24 시간이 지난 후에도 문제가 계속 되 면 고객 지원에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="fdd54-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


