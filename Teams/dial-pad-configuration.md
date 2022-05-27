---
title: 다이얼 패드 구성 Teams
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 사용자가 PSTN(공중 전화망) 기능에 액세스할 수 있도록 Teams 클라이언트에서 다이얼 패드를 구성하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 6aa5edf8f57574fa08a224541772c1f9e662f9ca
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676160"
---
# <a name="dial-pad-configuration"></a>다이얼 패드 구성

Teams 클라이언트에서 다이얼 패드를 사용하면 사용자가 PSTN(공중 전화망) 기능에 액세스할 수 있습니다. 다이얼 패드는 전화 시스템 라이선스가 있는 사용자가 올바르게 구성된 경우 사용할 수 있습니다. 다이얼 패드를 표시하려면 다음 조건이 모두 필요합니다.

- 사용자에게 사용 가능한 전화 시스템("MCOEV") 라이선스가 있습니다.
- 사용자에게 Microsoft 통화 플랜, 운영자 연결 또는 직접 라우팅이 사용하도록 설정되어 있습니다.
- 사용자가 Enterprise Voice 사용하도록 설정되었습니다.
- 사용자는 온-프레미스에서 비즈니스용 Skype 않고 온라인 상태입니다.
- 사용자가 Teams 통화 정책을 사용하도록 설정했습니다.

다음 섹션에서는 PowerShell을 사용하여 조건을 확인하는 방법을 설명합니다. 대부분의 경우 Get-CsOnlineUser cmdlet의 출력에서 다양한 속성을 확인해야 합니다. 예제에서는 $user 사용자의 UPN 또는 sip 주소라고 가정합니다.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>사용자에게 사용 가능한 전화 시스템("MCOEV") 라이선스가 있습니다.

사용자에 대해 할당된 계획에 **Enabled로 설정된 CapabilityStatus 특성** 과 **MCOEV**(전화 시스템 라이선스)로 설정된 기능이 표시되는지 확인합니다. MCOEV, MCOEV1 등이 표시될 수 있습니다. 기능이 MCOEV로 시작하는 한 모두 허용됩니다.

특성이 올바르게 설정되었는지 확인하려면 다음 명령을 사용합니다.

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

출력은 다음과 같습니다. **CapabilityStatus** 및 **기능** 특성만 확인하면 됩니다.

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

## <a name="user-has-microsoft-calling-plan-operator-connect-or-is-enabled-for-direct-routing"></a>사용자에게 Microsoft 통화 플랜, 운영자 연결 OR이 직접 라우팅에 사용하도록 설정되어 있습니다.

**사용자에게 Microsoft 통화 플랜이 있는 경우** **CapabilityStatus 특성이 Enabled로 설정되어** 있고 **기능이 MCOPSTN으로 설정되어** 있는지 확인합니다. MCOPSTN1, MCOPSTN2 등이 표시될 수 있습니다. 기능이 MCOPSTN으로 시작하는 한 모두 허용됩니다.

특성을 확인하려면 다음 명령을 사용합니다.

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

출력은 다음과 같습니다. **CapabilityStatus** 및 **기능** 특성만 확인하면 됩니다.

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 MCOPSTN2        Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 5a10155d-f5c1-411a-a8ec-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

**사용자가 운영자 연결 사용하도록 설정된 경우** TeamsCarrierEmergencyCallRoutingPolicy에 대해 null이 아닌 값이 있어야 합니다. 특성을 확인하려면 다음 명령을 사용합니다.

```PowerShell
Get-CsOnlineUser -Identity $user|Select TeamsCarrierEmergencyCallRoutingPolicy
```

출력에는 null이 아닌 값이 있어야 합니다. 예를 들면 다음과 같습니다.

```PowerShell
TeamsCarrierEmergencyCallRoutingPolicy
--------------------------------------
Synergy_98d1a5cb-d3e6-4306-885e-69a95f2da5c3
```

**사용자가 직접 라우팅을 사용하도록 설정된 경우** 사용자에게 OnlineVoiceRoutingPolicy에 대해 null이 아닌 값이 할당되어야 합니다. 특성을 확인하려면 다음 명령을 사용합니다.

```PowerShell
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy
```

출력에는 null이 아닌 값이 있어야 합니다. 예를 들면 다음과 같습니다.

```PowerShell
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>사용자가 Enterprise Voice 사용하도록 설정되었습니다.

사용자가 Enterprise Voice 사용하도록 설정되어 있는지 확인하려면 다음 명령을 사용합니다.

```PowerShell
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

출력은 다음과 같습니다.

```PowerShell
EnterpriseVoiceEnabled
----------------------
                  True
```

## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>사용자는 온-프레미스에서 비즈니스용 Skype 않고 온라인 상태입니다.

사용자가 온-프레미스에 비즈니스용 Skype 아니라 온라인 상태로 유지되도록 하려면 RegistrarPool이 null이 아니어야 하며 HostingProvider에 "sipfed.online"로 시작하는 값이 포함되어야 합니다.  값을 확인하려면 다음 명령을 사용합니다.

```PowerShell
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

출력은 다음과 유사해야 합니다.

```PowerShell
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>사용자가 Teams 통화 정책을 사용하도록 설정했습니다.

사용자의 유효한 TeamsCallingPolicy에는 AllowPrivateCalling이 true로 설정되어 있어야 합니다.  기본적으로 사용자는 AllowPrivateCallingPolicy가 기본적으로 true로 설정된 전역 정책을 상속합니다.

사용자에 대한 TeamsCallingPolicy를 가져와 AllowPrivateCalling이 true로 설정되어 있는지 확인하려면 다음 명령을 사용합니다.

```PowerShell
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
```

출력은 다음과 같습니다.

```PowerShell
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

## <a name="additional-notes"></a>추가 참고 사항

- 이러한 구성을 변경한 후 Teams 클라이언트를 다시 시작해야 할 수 있습니다.

- 최근에 위의 조건을 업데이트한 경우 클라이언트가 새 설정을 받을 때까지 몇 시간을 기다려야 할 수 있습니다.

- 다이얼 패드가 여전히 표시되지 않는 경우 다음 명령을 사용하여 프로비전 오류가 있는지 확인합니다.

  ```PowerShell
  Get-CsOnlineUser -Identity $user|Select UserValidationErrors
  ```

- 24시간이 넘었고 여전히 문제가 발생하는 경우 지원에 문의하세요.
