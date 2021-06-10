---
title: Teams 패드 구성
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
description: 사용자가 PSTN(공용 전환 전화 네트워크) 기능에 액세스할 수 있도록 Teams 클라이언트에서 다이얼 패드를 구성하는 방법에 대해 자세히 알아보겠습니다.
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012423"
---
# <a name="dial-pad-configuration"></a>다이얼 패드 구성

클라이언트에서 Teams 패드를 사용하면 사용자가 PSTN(공용 전환 전화 네트워크) 기능에 액세스할 수 있습니다. 다이얼 패드는 제대로 구성된 경우 전화 시스템 라이선스가 있는 사용자가 사용할 수 있습니다. 다이얼 패드에 표시하려면 다음 조건이 모두 필요합니다.

- 사용자에게 사용 전화 시스템("MCOEV") 라이선스가 있습니다.
- 사용자가 Microsoft 통화 계획이 있는 경우 또는 직접 라우팅에 사용하도록 설정되어 있습니다.
- 사용자가 Enterprise Voice 설정되어 있습니다.
- 사용자가 온라인에 홈이 됐고 비즈니스용 Skype 없습니다.
- 사용자가 Teams 통화 정책을 사용하도록 설정했습니다.

다음 섹션에서는 PowerShell을 사용하여 조건을 검사하는 방법을 설명합니다. 대부분의 경우 cmdlet의 출력에서 다양한 속성을 Get-CsOnlineUser 합니다. 예를 $user 사용자의 UPN 또는 sip 주소로 가정합니다.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>사용자에게 사용 전화 시스템("MCOEV") 라이선스가 있습니다.

사용자에 대해 할당된 계획에 사용 가능으로 설정된 **CapabilityStatus** 특성과 기능 계획이 **MCOEV(라이선스)로** 전화 시스템 있어야 합니다. MCOEV, MCOEV1 등도 표시될 수 있습니다. 기능 계획이 MCOEV로 시작하는 한 모든 것이 허용됩니다.

특성이 올바르게 설정되어 있는지 확인하려면 다음 명령을 사용 합니다.

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

출력은 다음과 같습니다. **CapabilityStatus** 및 기능 계획 특성만 **확인하면** 됩니다.

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>사용자가 Microsoft 통화 계획 또는 직접 라우팅에 사용하도록 설정되어 있습니다.

**사용자에게 Microsoft 호출** 계획이 있는 경우 **CapabilityStatus** 특성이 사용하도록 설정되어 있으며 기능 계획이 **MCOPSTN으로** 설정되어 있어야 합니다. MCOPSTN1, MCOPSTN2 등도 표시될 수 있습니다. 기능 계획이 MCOPSTN으로 시작하는 한 모든 것이 허용됩니다.

특성을 확인하기 위해 다음 명령을 사용 합니다.

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

출력은 다음과 같습니다. **CapabilityStatus** 및 기능 계획 특성만 **확인하면** 됩니다.

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

**사용자가 직접** 라우팅을 사용하도록 설정되어 있는 경우, 사용자는 OnlineVoiceRoutingPolicy에 대해 null이 아닌 값을 할당해야 합니다. 특성을 확인하기 위해 다음 명령을 사용 합니다.
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

출력에는 null 값이 아닌 값이 있습니다( 예:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>사용자가 Enterprise Voice 설정되어 있습니다.

사용자가 사용 가능한 Enterprise Voice 확인을 위해 다음 명령을 사용 합니다.

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

출력은 다음과 같아야 합니다.

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>사용자가 온라인에 홈이 됐고 비즈니스용 Skype 없습니다.

사용자가 온라인에 홈이 되도록 비즈니스용 Skype 등록 기관은 null이 아니며 HostingProvider에 "sipfed.online" 값을 포함해야 합니다.  값을 확인하기 위해 다음 명령을 사용합니다.

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

출력은 다음과 유사해야 합니다.

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>사용자가 Teams 통화 정책을 사용하도록 설정했습니다.

사용자의 효과적인 TeamsCallingPolicy에는 AllowPrivateCalling이 true로 설정되어 있어야 합니다.  기본적으로 사용자는 AllowPrivateCallingPolicy를 true로 설정한 전역 정책을 상속합니다.

사용자에 대한 TeamsCallingPolicy를 얻게 하여 AllowPrivateCalling이 true로 설정되어 있는지 확인하기 위해 다음 명령을 사용 합니다.

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

출력은 다음과 같아야 합니다.

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

## <a name="additional-notes"></a>추가 정보

-   이러한 구성을 변경한 Teams 클라이언트를 다시 시작해야 할 수 있습니다.

-   위 조건 중 어느 것이든 최근에 업데이트한 경우 클라이언트가 새 설정을 수신할 때까지 몇 시간을 기다려야 할 수 있습니다.

-   다이얼 패드가 계속 표시되지 않는 경우 다음 명령을 사용하여 프로비전 오류가 발생하는지 검사합니다.

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    24시간이 넘고 문제가 계속 발생하면 지원에 문의합니다.


