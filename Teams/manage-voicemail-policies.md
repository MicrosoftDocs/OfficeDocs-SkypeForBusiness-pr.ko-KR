---
title: 음성 메일 정책 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 사용자에 대한 음성 메일 정책을 관리합니다.
ms.openlocfilehash: f6c14584ee5da1b15085cd4caddfc757fbb50476
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999313"
---
# <a name="manage-cloud-voicemail-policies-for-your-users"></a>사용자에 대한 클라우드 음성 사서함 정책 관리

> [!WARNING]
> 비즈니스용 Skype 고객의 경우 Microsoft Teams 통화 정책을 통해 음성 메일을 사용하지 않도록 설정하면 비즈니스용 Skype 사용자에 대한 음성 메일 서비스를 사용하지 않도록 설정할 수도 있습니다.

음성 메일 정책을 사용하면 통화 응답 규칙, 음성 메일 전사, 전사 욕설 마스킹, 전사 번역 및 시스템 프롬프트 언어와 같은 기능을 위해 사용자 그룹에 기존 또는 새 음성 메일 정책을 구성하고 할당할 수 있습니다.

정책을 지정하기 전에 [클라우드 음성 사서함 설정을](set-up-phone-system-voicemail.md) 읽어야 합니다. 개별 사용자의 설정을 관리하는 방법에 대한 자세한 내용은 [Voicemail setltings 관리를 참조하세요](manage-voicemail-settings.md).

음성 메일 정책을 관리하려면 Teams 관리 센터 또는 New-CsOnlineVoicemailPolicy PowerShell cmdlet을 사용할 수 있습니다. 

사용자에 대한 기본 정책은 다음과 같습니다.

- 음성 메일 전사를 사용할 수 있습니다.
- 음성 메일 전사 번역을 사용할 수 있습니다.
- 음성 메일 전사 욕설 마스킹을 사용할 수 없습니다.
- 최대 기록 기간은 5분으로 설정됩니다.
- 통화 응답 규칙을 편집할 수 있습니다.
- 기본 및 보조 시스템 프롬프트 언어는 null로 설정되고 사용자의 음성 메일 언어 설정이 사용됩니다.

자동으로 만들어지는 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.

> [!IMPORTANT]
> Microsoft 365의 음성 메일 서비스는 음성 메일 정책을 캐시하고 6시간마다 캐시를 업데이트합니다. 따라서 정책 변경 내용을 적용하는 데 최대 6시간이 걸릴 수 있습니다.

## <a name="use-teams-admin-center"></a>Teams 관리 센터 사용

### <a name="create-a-custom-voicemail-policy"></a>사용자 지정 음성 메일 정책 만들기

다음 단계에 따라 사용자 지정 음성 메일 정책을 만듭니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Voice Voicemail** > **정책** 으로 이동합니다.

2. **추가** 를 선택합니다.

3. 음성 메일 정책에서 사용하려는 기능을 켜거나 끕니다.

4. **저장** 을 선택합니다.

### <a name="edit-a-voicemail-policy"></a>음성 메일 정책 편집

다음 단계에 따라 기존 음성 메일 정책을 편집합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **사서함 정책을** 선택합니다.

2. 수정할 정책 옆을 클릭한 다음 **편집** 을 선택합니다.

3. 원하는 대로 변경한 다음 **저장** 을 클릭합니다.

> [!IMPORTANT]
> TranscriptionDisabled 및 TranscriptionProfanityMaskingEnabled라는 미리 구성된 정책 인스턴스를 편집하거나 제거할 수 없습니다.


### <a name="assign-a-custom-voicemail-policy-to-users"></a>사용자에게 사용자 지정 음성 메일 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="use-powershell"></a>PowerShell 사용

PowerShell을 사용하여 기존 또는 새 음성 메일 정책을 구성하고 할당할 수도 있습니다. PowerShell을 사용하여 정책을 관리하려면 다음 cmdlet을 사용합니다.

- [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

## <a name="voicemail-policy-settings"></a>음성 메일 정책 설정
  
- **전사 사용** - 이 설정은 클라우드 음성 사서함 서비스에서 녹음된 음성 메일의 텍스트 변환을 생성하고 음성 메일 메시지에 포함할지 여부를 제어합니다. 기록된 음성 메일에서 감지된 언어에 따라 전사가 수행됩니다.

- **전사 번역** - 이 설정은 클라우드 음성 사서함 서비스가 녹음된 음성 메일의 전사를 번역할지 여부를 제어합니다. 번역은 음성 메일 수신기의 기본 언어로 시도됩니다.

- **전사 욕설 마스킹** - 이 설정은 클라우드 음성 사서함 서비스가 음성 메일의 전사에 있는 욕설을 마스킹할지 여부를 제어합니다.

- **최대 녹음 기간** - 최대 녹음 길이는 음성 메일을 녹음할 수 있는 최대 시간을 제어합니다. 기본값은 5분입니다.

- **통화 응답 규칙** - 이 설정은 사용자가 Microsoft Teams에서 음성 메일 통화 응답 규칙을 구성할 수 있는지 여부를 제어합니다.

- **이중 언어 시스템 프롬프트** - 기본적으로 음성 메일 시스템 프롬프트는 음성 메일을 설정할 때 사용자가 선택한 언어로 발신자에게 표시됩니다. 음성 메일 시스템 프롬프트를 두 언어로 표시해야 하는 비즈니스 요구 사항이 있는 경우 기본 및 보조 언어를 설정할 수 있으며 동일하지 않을 수 있습니다.

### <a name="share-data-for-service-improvements"></a>서비스 개선을 위한 데이터 공유

음성 메일 및 전사 데이터를 교육 및 정확도 향상을 위해 서비스와 공유할지 여부를 지정합니다. false로 설정하면 사용자 선택에 관계없이 음성 메일 데이터가 공유되지 않습니다.


## <a name="related-articles"></a>관련 기사


