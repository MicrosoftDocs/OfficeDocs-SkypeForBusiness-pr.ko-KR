---
title: Microsoft Teams에 대한 엔드투엔드 암호화
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 03/08/2022
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ashgupt
description: Microsoft Teams의 향상된 암호화 기능에 대해 알아보고, Teams 관리 센터 및 Microsoft PowerShell을 사용하여 엔드투엔드 암호화를 관리합니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- purview-compliance
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e0d47107771add6e091afeeddc35d47110d7938
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614641"
---
# <a name="use-end-to-end-encryption-for-one-to-one-microsoft-teams-calls"></a>일대일 Microsoft Teams 통화에 엔드투엔드 암호화 사용

> [!IMPORTANT]
> Teams 서비스 모델 및 암호화 지원은 고객 환경을 개선하기 위해 변경될 수 있습니다. 예를 들어 서비스는 더 이상 안전하지 않은 암호 그룹을 정기적으로 사용하지 않습니다. 그러한 변경 사항은 원칙적으로 Teams를 안전하고 신뢰할 수 있는 상태로 유지하는 것을 목표로 수행됩니다. 또한, Microsoft 데이터 센터의 모든 고객 콘텐츠가 암호화됩니다. Microsoft 365 암호화 계층에 대한 자세한 내용은 [Microsoft 365](/microsoft-365/compliance/encryption) 암호화를 참조하세요.

E2EE(엔드투엔드 암호화)는 콘텐츠가 전송되기 전에 암호화되고 의도된 받는 사람만 암호를 해독하는 경우 발생합니다. 엔드투엔드 암호화를 사용하면 두 엔드포인트 시스템만 호출 데이터를 암호화하고 암호 해독하는 데 관여합니다. Microsoft를 포함한 다른 당사자는 암호가 해독된 대화에 액세스할 수 없습니다.

예약되지 않은 일대일 통화에 대한 E2EE를 사용하면 일대일 Teams 통화의 실시간 미디어 흐름, 즉 비디오 및 음성 데이터만 엔드투엔드 암호화됩니다. 두 당사자 모두 엔드투엔드 암호화를 사용하도록 설정하려면 이 설정을 켜야 합니다. [Microsoft 365 암호화](/microsoft-365/compliance/encryption)는 통화에서 채팅, 파일 공유, 현재 상태 및 기타 콘텐츠를 보호합니다.

당사자가 Windows 또는 Mac용 Teams 데스크톱 클라이언트의 최신 버전을 사용 중이거나, iOS 및 Android용 최신 업데이트가 있는 모바일 디바이스에 있거나, 최신 업데이트를 사용하여 Windows 디바이스에서 Teams 룸 경우 두 당사자 간에 엔드 투 엔드 암호화 호출을 수행할 수 있습니다.

엔드투엔드 암호화를 사용하도록 설정하지 않으면 Teams는 업계 표준에 따라 암호화를 사용하여 통화 또는 모임을 계속 보호합니다. 통화 중에 교환된 데이터는 전송 중이거나 미사용 상태일 때 항상 안전합니다. 자세한 내용은 [Teams에 대한 미디어 암호화](teams-security-guide.md#media-encryption)를 참조하세요.

엔드투엔드 암호화 통화 중에 Teams는 다음 기능을 보호합니다.

- 오디오

- 비디오

- 화면 공유.

E2EE 통화 중에는 다음 고급 기능을 사용할 수 없습니다.

- 라이브 캡션 및 전사

- 통화 전환

- 통화 병합

- 통화 대기

- 상의 후 전환

- 도우미를 호출하고 다른 디바이스로 전환

- 참가자 추가

- 녹음/녹화

또한 조직에서 규정 준수 기록을 사용하는 경우 엔드투엔드 암호화를 사용할 수 없습니다. Teams에서 규정 준수 녹음을 지원하는 방법에 대한 자세한 내용은 [통화 및 모임에 대한 Teams 정책 기반 녹음 소개](teams-recording-policy.md)를 참조하세요.

## <a name="configure-end-to-end-encryption-for-microsoft-teams"></a>Microsoft Teams에 대한 엔드투엔드 암호화 구성

사용자가 엔드투엔드 암호화 통화를 할 수 있도록 이러한 작업을 완료합니다.

- 엔드투엔드 암호화를 사용할 수 있는 사용자를 정의하는 정책을 하나 이상 만들어 조직에 엔드투엔드 암호화를 사용하도록 설정합니다. 시작하기 전에 직장 또는 학교 계정에 Teams 또는 전역 관리자 역할이 할당되었는지 확인하세요. 자세한 내용은 [Microsoft Teams 관리자 역할을 사용하여 Teams 관리](using-admin-roles.md)를 참조하세요. E2EE를 설정할 준비가 되면 Teams 관리 센터 또는 Microsoft PowerShell을 사용할 수 있습니다.

- 디바이스의 Teams 설정에서 엔드투엔드 암호화 호출을 켭니다. 각 사용자는 이 작업을 완료해야 하지만 하나의 장치에서만 작업을 수행하면 됩니다. Teams는 각 사용자에 대해 지원되는 엔드포인트 간에 이 설정을 동기화합니다. 지침은 [Teams 통화에 엔드투엔드 암호화 사용](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)을 참조하세요.

### <a name="use-the-teams-admin-center-to-configure-end-to-end-encryption"></a>Teams 관리 센터를 사용하여 엔드투엔드 암호화 구성

조직 전체의 전역 기본 정책은 엔드투엔드 암호화를 사용하지 않도록 지정합니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다. 엔드투엔드 암호화를 사용하도록 설정하려면 새 암호화 정책을 만들거나 전역 기본 정책을 수정합니다. Teams 관리 센터를 사용하여 엔드투엔드 암호화를 사용하도록 설정하려면 다음 단계를 완료합니다.

1. Teams 또는 전역 관리자 역할이 할당된 회사 또는 학교 계정을 사용하여 [Teams 관리 센터](https://admin.teams.microsoft.com/)에 로그인합니다.

2. **향상된 암호화 정책** 으로 이동합니다.

3. 기본 정책을 선택하거나 **추가** 를 선택하고 새 정책을 추가한 다음 새 정책의 이름을 지정합니다.

4. 사용자에 대해 엔드 투 엔드 암호화를 사용하도록 설정하려면 **엔드 투 엔드 호출 암호화에** **대해 사용하도록 설정하지 않음을 선택하지만 사용자가 사용하도록 설정한** 다음 **저장** 을 선택할 수 있습니다.

   엔드 투 엔드 암호화를 사용하지 않도록 설정하려면 **[사용 안 함]을** 선택합니다.

정책 설정을 완료한 후에는 다른 Teams 정책을 관리하는 것과 동일한 방식으로 사용자, 그룹 또는 전체 테넌트에게 정책을 할당합니다. Teams에서 정책을 사용하는 방법에 대한 자세한 내용은 [정책으로 Teams 관리](manage-teams-with-policies.md)를 참조하세요.

### <a name="use-microsoft-powershell-to-configure-end-to-end-encryption"></a>Microsoft PowerShell을 사용하여 엔드투엔드 암호화 구성

Microsoft PowerShell 및 Teams 관리 센터를 사용하여 엔드투엔드 암호화 정책을 관리할 수 있습니다. 여러 엔드투엔드 암호화 cmdlet이 Teams PowerShell 모듈에 포함되어 있으며 [Microsoft Teams cmdlet 참조](/powershell/teams/?view=teams-ps&preserve-view=true)에 문서화되어 있습니다. 이 문서에서는 사용할 수 있는 cmdlet을 나열하고 간단한 예제 구성을 제공합니다. 이러한 구성은 기본 전역 정책을 사용합니다. 조직에 더 복잡한 정책 구성이 필요할 수 있습니다. 이러한 cmdlet에 대한 전체 정보는 cmdlet 참조에서 제공됩니다.

엔드투엔드 암호화 PowerShell cmdlet:

- [Get-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Get-CsTeamsEnhancedEncryptionPolicy)는 조직의 Teams 향상된 암호화 정책에 대한 정보를 반환합니다.

- [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy)는 사용자에게 기존 향상된 암호화 정책을 할당하고 할당 해제합니다. `$NULL`을 사용하여 사용자로부터 모든 정책 할당을 취소합니다.

- [New-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/New-CsTeamsEnhancedEncryptionPolicy)는 새 Teams 향상된 암호화 정책을 만듭니다.

- [Remove-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Remove-CsTeamsEnhancedEncryptionPolicy)는 조직에서 향상된 암호화 정책을 삭제합니다. 전역 기본 정책은 삭제할 수 없습니다.

- [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy)는 기존 Teams 향상된 암호화 정책의 값을 업데이트합니다.

회사 또는 학교 계정에는 엔드투엔드 암호화를 구성하기 위한 Teams 또는 전역 관리자 역할이 필요합니다.

#### <a name="to-enable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>전역 정책을 사용하여 전체 테넌트에서 엔드투엔드 암호화를 사용하도록 설정하려면

By default, end-to-end encryption is disabled. To enable end-to-end encryption for the entire tenant by setting the default global policy, run the [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) cmdlet as follows.

```powershell
Set-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType DisabledUserOverride
```

여기서,

- `Global`은 이 구성을 전역 조직 전체 기본 정책에 설정하고 있는 것입니다.

- `DisabledUserOverride`sms 기본적으로 Teams에서 E2EE가 사용하지 않도록 설정되어 있지만, Teams 설정에서 사용자가 기본값을 재정의하고 E2EE를 켤 수 있음을 의미합니다.

#### <a name="to-disable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>전역 정책을 사용하여 전체 테넌트에서 엔드투엔드 암호화를 사용하지 않도록 설정하려면

By default, end-to-end encryption is disabled. If you've made changes to the global policy, you can change the setting back by running the [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) cmdlet as follows.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType Disabled
```

여기서,

- `Global`은 이 구성을 전역 조직 전체 기본 정책에 설정하고 있는 것입니다.

- `Disabled`는 모든 사용자에 대해 E2EE를 사용하지 않도록 설정했으며 사용자가 Teams 설정에서 E2EE를 켤 수 없음을 의미합니다.

#### <a name="to-enable-end-to-end-encryption-for-a-single-user"></a>단일 사용자에 대해 엔드투엔드 암호화를 사용하도록 설정하려면

사용자에 대해 엔드투엔드 암호화를 사용하도록 설정하려면 다음과 같이 [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) cmdlet을 실행합니다.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "username" -PolicyName "policyname"
```

여기서,

- *`username`* 은 사용자의 이름입니다.

- *`policyname`* 은 정책에 사용할 이름입니다. 정책 이름은 공백을 포함할 수 없습니다(예: ContosoE2EEUserPolicy).

Users still need to switch on end-to-end encrypted calling in their Teams settings before they can make an end-to-end encrypted call. For instructions, see [Use end-to-end encryption for Teams calls](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

예를 들면 다음과 같습니다.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName "ContosoE2EEUserPolicy"
```

#### <a name="to-unassign-an-end-to-end-encryption-policy-from-a-single-user"></a>단일 사용자로부터 엔드투엔드 암호화 정책 할당을 취소하려면

사용자에게는 한 번에 하나의 암호화 정책만 할당될 수 있습니다. 사용자의 정책 할당을 취소하면 사용자에게 전역, 조직 전체의 기본 정책이 할당됩니다. 기본 정책의 할당을 취소할 수 없습니다. 사용자로부터 엔드투엔드 암호화 정책의 할당을 취소하려면 다음과 같이 [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) cmdlet을 실행합니다.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName $NULL
```

## <a name="switch-on-end-to-end-encryption-on-your-device"></a>디바이스에서 엔드투엔드 암호화 켜기

지침은 [Teams 통화에 엔드투엔드 암호화 사용](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)을 참조하세요.

## <a name="related-topics"></a>관련 항목

[보안 팀이 재택 근무를 지원하는 상위 12가지 작업](/microsoft-365/security/top-security-tasks-for-remote-work)

[Microsoft Teams에서의 모임 설정 관리](./meeting-settings-in-teams.md)
