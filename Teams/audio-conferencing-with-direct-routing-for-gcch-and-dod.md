---
title: 직접 라우팅, GCCH 및 DoD를 통해 오디오 회의
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 관리자는 GCCH 및 DoD 환경에서 직접 라우팅을 사용하여 오디오 회의를 사용하는 방법에 대해 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 274173387374591e91a067e2a5340bb735910fa7
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055878"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High 및 DoD를 위해 직접 라우팅으로 오디오 회의

High 및 DoD에 대한 직접 라우팅을 사용하는 오디오 회의를 통해 GCC 디바이스를 사용하여 참가자가 Teams 또는 DoD 조직에서 GCC 모임에 참가할 수 있습니다. 모임 참가자는 전화 장치를 사용하여 인터넷 연결이 제한되거나 사용자가 도로에 Teams 액세스 권한이 없는 경우와 같은 시나리오에서 Teams. 참가자는 조직의 전화 접속 전화 번호에 전화를 걸거나 모임이 휴대폰 디바이스에 전화 접속하여 모임에 참가할 수 있습니다.

High 및 DoD에 대한 직접 라우팅을 사용하는 오디오 회의를 사용하여 조직에서 자체 GCC 전화 접속 전화 번호로 사용하며 전화 디바이스에 대한 모든 모임 전화 접속은 직접 라우팅을 통해 라우팅됩니다. 서비스를 사용하도록 설정하려면 조직에서 직접 라우팅을 설정하고 전화 접속 전화 번호로 사용할 수 있는 전화 번호를 구성해야 합니다. 직접 라우팅을 사용해야 하는 요구 사항은 Microsoft에서 전화 접속 전화 번호를 제공하는 비도우급 높음 및 비도드 조직에 제공되는 GCC 오디오 회의 서비스와 다릅니다.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>High 및 DoD에 대한 직접 라우팅을 GCC 오디오 회의 배포

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>1단계: 하이 또는 DoD 라이선스에 대한 직접 라우팅을 GCC 오디오 회의하기

높음 GCC 또는 doD에서 오디오 회의를 사용하려면 조직 및 조직의 사용자가 직접 라우팅 라이선스가 할당된 오디오 회의를 지정해야 합니다. 다음은 하이 또는 DoD에 대한 직접 라우팅을 사용하여 오디오 회의를 사용하도록 설정하는 데 GCC 라이선스입니다.

- GCC 높음: 오디오 회의 - GCC 높은 테넌트 라이선스 및 오디오 회의에 대한 하이 테넌트 라이선스 - GCC 높은 라이선스를 제공합니다.

- DoD: 오디오 회의 - 조직 및 오디오 회의에 대한 DoD 테넌트 라이선스 - 사용자에 대한 DoD 라이선스입니다.

서비스를 사용하도록 설정하려면 테넌트 라이선스 및 하나 이상의 사용자 라이선스가 필요합니다. 테넌트 라이선스 또는 사용자 라이선스만 사용하여 서비스를 사용하도록 설정할 수 없습니다. 테넌트 및 조직의 사용자에 대한 서비스 라이선스를 얻하려면 계정 팀에 문의하세요.

> [!IMPORTANT]
> 전화 접속 전화 번호가 설정될 때까지 직접 라우팅을 사용하여 오디오 회의를 사용할 수 없습니다. 이 문서에 설명된 GCC 전화 접속 전화 번호를 설정하기 전까지는 하이 또는 DoD 라이선스에 대한 직접 라우팅을 사용하여 오디오 회의를 할당하지 않는 것이 좋습니다.  이 지침을 따르지 않을 경우 클라이언트에서 다이얼 패드가 Teams 수 있습니다.

### <a name="step-2-set-up-direct-routing"></a>2단계: 직접 라우팅 설정

직접 라우팅을 설정하는 경우 다음 문서를 참조합니다.

- [직접 라우팅 계획](direct-routing-plan.md)

- [직접 라우팅 구성](direct-routing-configure.md)

> [!NOTE]
> 직접 라우팅을 설정할 때 다음 두 문서에 설명된 GCC 높은 또는 DoD 관련 FQDNs 및 포트를 사용하는 것이 잊지 말아야 합니다.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>3단계: 전화 접속 전화 번호 설정

전화 접속 전화 번호는 오디오 회의 브리지에 연결된 전화 번호입니다. 이러한 숫자는 참가자가 조직의 사용자가 예약한 모임에 참가하는 데 사용됩니다. 이러한 번호는 조직의 모임을 예약하는 사용자의 모임 초대 및 "로컬 번호 찾기" 페이지에도 포함됩니다.

#### <a name="define-service-phone-numbers-in-your-tenant"></a>테넌트에서 서비스 전화 번호 정의

New-csHybridTelephoneNumber PowerShell cmdlet을 사용하여 직접 라우팅을 통해 오디오 회의 서비스에 대한 호출을 라우팅하는 데 사용할 수 있는 테넌트에서 서비스 전화 번호를 정의할 수 있습니다.

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

예를 들면 다음과 같습니다.

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>조직의 오디오 회의 브리지에 서비스 전화 번호 할당

Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet을 사용하여 조직의 오디오 회의 브리지에 서비스 전화 번호를 할당할 수 있습니다.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Get-CsOnlineDialInConferencingBridge를 사용하여 오디오 회의 브리지의 ID를 볼 수 있습니다. 예를 들면 다음과 같습니다.

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>4단계: 모임에서 아웃바운드 호출 라우팅을 사용하도록 전역 음성 라우팅 정책 정의

조직의 사용자가 구성한 모임에서 PSTN에 대한 아웃바운드 호출 라우팅은 조직의 글로벌 음성 라우팅 정책에 의해 정의됩니다. 조직에 글로벌 음성 라우팅 정책이 정의되어 있는 경우 글로벌 음성 라우팅 정책이 조직의 사용자가 조직한 모임에서 시작될 것으로 예상되는 PSTN에 대한 아웃바운드 호출을 허용하는지 확인하시기 바랍니다. 조직에 글로벌 음성 라우팅 정책이 정의되지 않은 경우 조직의 사용자가 구성한 모임에서 PSTN에 대한 아웃바운드 호출의 라우팅을 사용하도록 설정하도록 정의해야 합니다. 조직의 글로벌 음성 라우팅 정책은 조직의 사용자가 PSTN에 대한 일대일 통화에도 적용됩니다. 조직의 사용자가 PSTN에 대한 일대일 호출을 사용하도록 설정되어 있는 경우 글로벌 음성 라우팅 정책이 두 유형의 호출에 대한 조직의 요구 사항을 충족하는지 확인합니다.

> [!NOTE]
> Location-Based(Microsoft 365 정부 커뮤니티 클라우드) 높거나 DoD 배포에서 Microsoft 365 정부 커뮤니티 클라우드(GCC) 사용할 수 없습니다. 오디오 회의를 사용하도록 설정하는 경우 하이 또는 DoD 환경의 오디오 회의 사용자가 GCC 라우팅에 사용하도록 설정되어 Location-Based 확인합니다.

#### <a name="defining-a-global-voice-routing-policy"></a>글로벌 음성 라우팅 정책 정의

글로벌 음성 라우팅 정책은 PSTN 사용량, 음성 경로, 음성 라우팅 정책을 정의하고 조직의 글로벌 음성 라우팅 정책으로 새 음성 라우팅 정책을 할당하여 정의할 수 있습니다.

다음 단계에서는 하나 없이 조직에 대한 새 전역 음성 라우팅 정책을 정의하는 방법을 설명합니다. 조직에 이미 음성 라우팅 정책이 정의되어 있는 경우 다음 구성이 조직의 기존 음성 라우팅 정책과 충돌하지 않는지 확인합니다.

온라인에서 원격 PowerShell 세션에서 새 PSTN 비즈니스용 Skype 다음 명령을 사용합니다.

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

자세한 내용은 [Set-CsOnlinePstnUsage 를 참조하세요.](/powershell/module/skype/set-csonlinepstnusage)

새 음성 경로를 만들 경우 다음 명령을 사용 합니다.

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

조직에 대한 새 음성 경로를 정의할 때 직접 라우팅 구성 중에 조직에 대해 정의된 PSTN 온라인 PSTN 게이트웨이 중 하나 또는 여러 개를 지정하세요.

번호 패턴은 호출의 대상 전화 번호를 기반으로 지정된 게이트웨이 목록을 통해 라우팅될 호출을 지정합니다. 위의 예제에서는 전 세계 모든 대상에 대한 호출이 음성 경로와 일치합니다. 조직의 사용자 모임에서 전화를 걸 수 있는 전화 번호를 제한하고자 하는 경우 음성 경로가 허용되는 대상의 숫자 패턴만 일치하도록 번호 패턴을 변경할 수 있습니다. 특정 통화의 대상 전화 번호의 번호 패턴과 일치하는 음성 경로가 없는 경우 통화가 라우팅되지 않습니다.

자세한 내용은 [New-CsOnlineVoiceRoute 를 참조하세요.](/powershell/module/skype/new-csonlinevoiceroute)

새 음성 라우팅 정책을 만들 경우 다음 명령을 사용 합니다.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

음성 라우팅 정책에서 여러 PSTN 사용량을 정의하는 경우 정의되는 순서대로 평가됩니다. PSTN 사용량은 PSTN 사용과 연결된 음성 경로의 숫자 패턴 측면에서 가장 일반적인 순서로 정의하는 것이 좋습니다. 예를 들어 미국으로의 호출을 라우팅하기 위해 PSTN 사용량이 정의되고 다른 PSTN 사용량이 전 세계의 다른 위치로 호출을 라우팅하기 위해 정의된 경우 미국에 대한 호출에 대한 PSTN 사용량은 전 세계의 다른 위치로 호출을 라우팅하기 위해 PSTN 사용 앞의 음성 라우팅 정책에 나열해야 합니다.

자세한 내용은 [New-CsOnlineVoiceRoutingPolicy 를 참조하세요.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)

조직의 글로벌 음성 라우팅 정책에 새 음성 경로를 할당하기 위해 다음 명령을 사용 합니다.

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

자세한 내용은 [Grant-CsOnlineVoiceRoutingPolicy 를 참조하세요.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

글로벌 음성 라우팅 정책이 정의된 후 조직의 사용자가 구성한 모임에서 만든 아웃바운드 호출은 글로벌 음성 라우팅 정책의 PSTN 사용과 연결된 음성 경로에 대해 평가됩니다. 아웃바운드 호출은 전화 걸기 전화 번호의 번호 패턴과 일치하는 첫 번째 음성 경로에 따라 라우팅됩니다.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>5단계: 사용자에게 높은 또는 DoD 라이선스에 대한 직접 라우팅을 GCC 오디오 회의 할당

사용자에 대한 직접 라우팅을 통해 오디오 회의를 GCC 또는 DoD 라이선스를 사용자에게 할당하는 경우 사용자에게 라이선스 할당을 [참조합니다.](/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>6단계: (선택 사항) 오디오 회의 번호 목록을 Teams

조직의 오디오 회의 번호 목록을 확인한 다음 에서 오디오 회의 번호 [목록 보기로 Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>7단계: (선택 사항) 조직의 오디오 회의 전화 접속 번호에 대한 자동 참석 언어 설정

조직의 오디오 회의 전화 접속 번호의 언어를 변경하는 경우 에서 오디오 회의에 대한 자동 참석 언어 설정 을 [Microsoft Teams.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>8단계: (선택 사항) 조직의 오디오 회의 브리지 설정 변경

조직의 오디오 회의 브리지 설정을 변경하려면 오디오 회의 브리지의 설정 변경을 [참조하세요.](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>9단계: (선택 사항) 조직의 사용자의 모임 초대에 포함된 전화 번호 설정

사용자의 모임 초대에 포함된 전화 번호 집합을 변경하는 것은 조직입니다. 의 초대에 포함된 전화 번호 [집합을](set-the-phone-numbers-included-on-invites-in-teams.md)Microsoft Teams.

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>High 및 DoD에 대한 직접 라우팅을 통해 오디오 회의에서 지원되지 GCC 오디오 회의 기능

다음은 하이 및 DoD에 대한 직접 라우팅을 통해 오디오 회의에서 지원되지 GCC 기능입니다.

- 이름 기록을 사용하여 알림 입력 및 종료 직접 라우팅을 사용하여 오디오 회의의 경우 입력 및 종료 알림이 모임에서 톤으로 재생됩니다.

- 모임 특정 이끌이에 대한 무료 전화 번호 사용을 사용하지 않도록 설정합니다. 조직의 모임에 참가하기 위해 무료 번호 사용을 제한하는 사용자 수준 제어는 직접 라우팅을 통해 라우팅된 호출에는 적용되지 않습니다.

- 설정이 변경될 때 사용자에게 알림 전자 메일을 전송합니다. 오디오 회의 알림 전자 메일은 하이 및 DoD에 대한 직접 라우팅을 사용하여 오디오 회의에 GCC 지원되지 않습니다.
