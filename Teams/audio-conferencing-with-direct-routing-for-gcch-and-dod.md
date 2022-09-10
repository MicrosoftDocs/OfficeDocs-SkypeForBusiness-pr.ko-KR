---
title: 직접 라우팅, GCCH 및 DoD를 사용하여 오디오 회의
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
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 관리 GCCH 및 DoD 환경에서 직접 라우팅을 사용하여 오디오 회의를 사용하는 방법에 대해 알아볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd467b9da8d296c21d4a0405d651bbaa6b001fd3
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641779"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High 및 DoD를 위해 직접 라우팅으로 오디오 회의

GCC High 및 DoD에 대한 직접 라우팅을 사용한 오디오 회의를 통해 참가자는 전화 장치를 사용하여 GCC High 또는 DoD 조직에서 Teams 모임에 참가할 수 있습니다. 모임 참가자는 전화 장치를 사용하여 인터넷 연결이 제한된 경우 또는 사용자가 도로에 있고 Teams에 액세스할 수 없는 경우와 같은 시나리오에서 Teams 모임에 참가하는 것을 선호할 수 있습니다. 참가자는 조직의 전화 접속 전화 번호로 전화를 걸거나 모임이 전화 장치로 전화를 걸어 모임에 참가하도록 선택할 수 있습니다.

GCC High 및 DoD에 대한 직접 라우팅을 사용한 오디오 회의를 통해 조직은 자체 번호를 전화 접속 전화 번호로 사용하고 전화 장치에 대한 모든 모임 전화 접속은 직접 라우팅을 통해 라우팅됩니다. 서비스를 사용하도록 설정하려면 조직에서 직접 라우팅을 설정하고 전화 접속 전화 번호로 사용할 수 있는 전화 번호를 구성해야 합니다. 직접 라우팅을 사용해야 하는 요구 사항은 전화 접속 전화 번호가 Microsoft에서 제공하는 비GCC High 및 비 DoD 조직에 제공되는 오디오 회의 서비스와 다릅니다.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High 및 DoD에 대한 직접 라우팅을 사용하여 오디오 회의 배포

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>1단계: GCC High 또는 DoD 라이선스에 대한 직접 라우팅을 사용하여 오디오 회의 가져오기

GCC High 또는 DoD에서 오디오 회의를 사용하려면 조직과 조직의 사용자에게 직접 라우팅 라이선스가 할당된 오디오 회의가 있어야 합니다. GCC High 또는 DoD에 대한 직접 라우팅을 사용하여 오디오 회의를 사용하도록 설정하는 데 필요한 라이선스는 다음과 같습니다.

- GCC High: 오디오 회의 - 조직에 대한 GCC High 테넌트 라이선스 및 오디오 회의 - 사용자를 위한 GCC High 라이선스

- DoD: 오디오 회의 - 조직에 대한 DoD 테넌트 라이선스 및 오디오 회의 - 사용자를 위한 DoD 라이선스입니다.

서비스를 사용하도록 설정하려면 테넌트 라이선스와 하나 이상의 사용자 라이선스가 필요합니다. 테넌트 라이선스만 사용하거나 사용자 라이선스만 사용하여 서비스를 사용하도록 설정할 수 없습니다. 테넌트 및 조직의 사용자에 대한 서비스 라이선스를 얻으려면 계정 팀에 문의하세요.

> [!IMPORTANT]
> 전화 접속 전화 번호가 설정될 때까지 직접 라우팅을 사용하여 오디오 회의를 사용하도록 설정할 수 없습니다. 이 문서에 설명된 대로 전화 접속 전화 번호를 설정할 때까지 GCC High 또는 DoD 라이선스에 대한 직접 라우팅을 사용하여 오디오 회의를 사용자에게 할당하지 않는 것이 좋습니다.  이 지침을 따르지 않으면 Teams 클라이언트에서 다이얼 패드가 완전히 누락될 수 있습니다.

### <a name="step-2-set-up-direct-routing"></a>2단계: 직접 라우팅 설정

직접 라우팅을 설정하려면 다음 문서를 참조하세요.

- [직접 라우팅 계획](direct-routing-plan.md)

- [직접 라우팅 구성](direct-routing-configure.md)

> [!NOTE]
> 직접 라우팅을 설정할 때는 이 두 문서에 설명된 GCC High 또는 DoD 관련 FQDN 및 포트를 사용해야 합니다.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>3단계: 전화 접속 전화 번호 설정

전화 접속 전화 번호는 오디오 회의 브리지에 연결된 전화 번호입니다. 이러한 숫자는 참가자가 조직의 사용자가 예약한 모임에 참가하는 데 사용됩니다. 이러한 번호는 조직에서 모임을 예약하는 사용자의 모임 초대와 "로컬 번호 찾기" 페이지에도 포함됩니다.

#### <a name="define-service-phone-numbers-in-your-tenant"></a>테넌트에서 서비스 전화 번호 정의

New-csHybridTelephoneNumber PowerShell cmdlet을 사용하여 직접 라우팅을 통해 오디오 회의 서비스로 통화를 라우팅하는 데 사용할 수 있는 테넌트의 서비스 전화 번호를 정의할 수 있습니다.

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

### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>4단계: 모임에서 아웃바운드 통화 라우팅을 사용하도록 글로벌 음성 라우팅 정책 정의

조직의 사용자가 구성한 모임에서 PSTN으로 수행되는 아웃바운드 호출의 라우팅은 조직의 글로벌 음성 라우팅 정책에 의해 정의됩니다. 조직에 전역 음성 라우팅 정책이 정의된 경우 전역 음성 라우팅 정책에서 조직의 사용자가 구성한 모임에서 시작될 것으로 예상되는 PSTN에 대한 아웃바운드 호출을 허용하는지 확인합니다. 조직에 전역 음성 라우팅 정책이 정의되어 있지 않은 경우 조직의 사용자가 구성한 모임에서 PSTN에 대한 아웃바운드 통화 라우팅을 사용하도록 설정하도록 정의해야 합니다. 조직의 글로벌 음성 라우팅 정책은 조직의 사용자가 PSTN에 대한 일대일 호출에도 적용됩니다. 조직의 사용자에 대해 PSTN에 대한 일대일 호출이 사용하도록 설정된 경우 전역 음성 라우팅 정책이 두 통화 유형 모두에 대한 조직의 요구 사항을 충족하는지 확인합니다.

> [!NOTE]
> Location-Based 라우팅은 Microsoft 365 GCC(Government Community Cloud) High 또는 DoD 배포에서 사용할 수 없습니다. 오디오 회의를 사용하도록 설정할 때 GCC High 또는 DoD 환경의 오디오 회의 사용자가 Location-Based 라우팅에 사용하도록 설정되어 있지 않은지 확인합니다.

#### <a name="defining-a-global-voice-routing-policy"></a>전역 음성 라우팅 정책 정의

글로벌 음성 라우팅 정책은 PSTN 사용량, 음성 경로, 음성 라우팅 정책을 정의하고 새 음성 라우팅 정책을 조직의 글로벌 음성 라우팅 정책으로 할당하여 정의할 수 있습니다.

다음 단계에서는 조직에서 하나도 없는 새 글로벌 음성 라우팅 정책을 정의하는 방법을 설명합니다. 조직에 이미 정의된 음성 라우팅 정책이 있는 경우 다음 구성이 조직의 기존 음성 라우팅 정책과 충돌하지 않는지 확인합니다.

Teams의 원격 PowerShell 세션에서 새 PSTN 사용을 만들려면 다음 명령을 사용합니다.

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

자세한 내용은 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage)를 참조하세요.

새 음성 경로를 만들려면 다음 명령을 사용합니다.

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

조직에 대한 새 음성 경로를 정의할 때 직접 라우팅을 구성하는 동안 조직에 대해 정의된 PSTN 온라인 PSTN 게이트웨이 중 하나 또는 여러 개 지정합니다.

번호 패턴은 통화의 대상 전화 번호에 따라 지정된 게이트웨이 목록을 통해 라우팅할 호출을 지정합니다. 위의 예제에서 전 세계의 모든 대상에 대한 호출은 음성 경로와 일치합니다. 조직의 사용자 모임에서 전화를 걸 수 있는 전화 번호를 제한하려는 경우 음성 경로가 허용된 대상의 번호 패턴만 일치하도록 번호 패턴을 변경할 수 있습니다. 지정된 통화의 대상 전화 번호의 번호 패턴과 일치하는 음성 경로가 없으면 통화가 라우팅되지 않습니다.

자세한 내용은 [New-CsOnlineVoiceRoute를 참조하세요](/powershell/module/skype/new-csonlinevoiceroute).

새 음성 라우팅 정책을 만들려면 다음 명령을 사용합니다.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

음성 라우팅 정책에서 여러 PSTN 사용이 정의되는 경우 정의된 순서대로 평가됩니다. PSTN 사용량은 PSTN 사용량과 연결된 음성 경로의 수 패턴 측면에서 보다 일반적인 순서로 정의되는 것이 좋습니다. 예를 들어 호출을 미국 라우팅하도록 PSTN 사용이 정의되고 다른 PSTN 사용이 전 세계의 다른 위치로 호출을 라우팅하도록 정의된 경우, 미국 대한 호출에 대한 PSTN 사용량은 PSTN 사용량보다 먼저 음성 라우팅 정책에 나열되어 있어야 전 세계의 다른 위치로 호출을 라우팅할 수 있습니다.

자세한 내용은 [New-CsOnlineVoiceRoutingPolicy를 참조하세요](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

조직의 글로벌 음성 라우팅 정책에 새 음성 경로를 할당하려면 다음 명령을 사용합니다.

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

자세한 내용은 [Grant-CsOnlineVoiceRoutingPolicy를 참조하세요](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

전역 음성 라우팅 정책이 정의되면 조직의 사용자가 구성한 모임에서 수행된 모든 아웃바운드 통화는 전역 음성 라우팅 정책의 PSTN 사용과 관련된 음성 경로에 대해 평가됩니다. 아웃바운드 통화는 전화 접속 전화 번호의 번호 패턴과 일치하는 첫 번째 음성 경로에 따라 라우팅됩니다.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>5단계: 사용자에게 GCC High 또는 DoD 라이선스에 대한 직접 라우팅을 사용하여 오디오 회의 할당

사용자에게 GCC High 또는 DoD 라이선스에 대한 직접 라우팅을 사용하여 오디오 회의를 할당하려면 [사용자에게 라이선스 할당을](/microsoft-365/admin/manage/assign-licenses-to-users) 참조하세요.

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>6단계: (선택 사항) Teams의 오디오 회의 번호 목록 보기

조직의 오디오 회의 번호 목록을 보려면 [Microsoft Teams의 오디오 회의 번호 목록을 참조](see-a-list-of-audio-conferencing-numbers-in-teams.md)하세요.

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>7단계: (선택 사항) 조직의 오디오 회의 전화 접속 번호에 대한 자동 전화 교환 언어 설정

조직의 오디오 회의 전화 접속 번호의 언어를 변경하려면 [Microsoft Teams에서 오디오 회의에 대한 자동 전화 교환 언어 설정을](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) 참조하세요.

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>8단계: (선택 사항) 조직의 오디오 회의 브리지 설정 변경

조직의 오디오 회의 브리지 설정을 변경하려면 [오디오 회의 브리지에 대한 설정 변경을](change-the-settings-for-an-audio-conferencing-bridge.md) 참조하세요.

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>9단계: (선택 사항) 조직의 사용자 모임 초대에 포함된 전화 번호 설정

사용자의 모임 초대에 포함된 전화 번호 집합을 조직으로 변경하려면 [Microsoft Teams의 초대에 포함된 전화 번호 설정을](set-the-phone-numbers-included-on-invites-in-teams.md) 참조하세요.

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High 및 DoD에 대한 직접 라우팅을 사용하여 오디오 회의에서 지원되지 않는 오디오 회의 기능

다음은 GCC High 및 DoD에 대한 직접 라우팅을 사용하는 오디오 회의에서 지원되지 않는 오디오 회의 기능입니다.

- 이름 기록을 사용하는 항목 및 종료 알림입니다. 직접 라우팅을 사용한 오디오 회의의 경우 모임에서 입장 및 종료 알림이 톤으로 재생됩니다.

- 모임 관련 이끌이에 대한 무료 전화 번호 사용을 사용하지 않도록 설정합니다. 조직의 모임에 참가하기 위해 무료 전화 번호 사용을 제한하는 사용자 수준 컨트롤은 직접 라우팅을 통해 라우팅되는 통화에는 적용되지 않습니다.

- 설정이 변경되면 사용자에게 알림 전자 메일을 보냅니다. 오디오 회의 알림 이메일은 GCC High 및 DoD에 대한 직접 라우팅을 사용하는 오디오 회의에 지원되지 않습니다.
