---
title: Voicemail 정책 관리
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 사용자에 대한 Voicemail 정책을 관리합니다.
ms.openlocfilehash: 112a2ac98ee22c46cb78c579ead947f70a1d6d447ac81ace3aef224304a281dd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342972"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>조직의 음성메일 정책 설정

> [!WARNING]
> 비즈니스용 Skype 고객의 경우 전화 통화 정책을 통해 음성 Microsoft Teams 사용하지 않도록 설정하면 사용자에 대한 음성 비즈니스용 Skype 수 있습니다.

## <a name="voicemail-organization-defaults-for-all-users"></a>모든 사용자에 대한 Voicemail 조직 기본값
- 음성메일 전사가 활성화되어 있습니다.
- Voicemail 전사 불경한 마스킹을 사용하지 않도록 설정됩니다.
- 최대 녹화 시간은 5분으로 설정됩니다.

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 및 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet을 사용하여 이러한 기본값을 제어할 수 있습니다.

조직의 사용자가 수신한 음성 메일 메시지는 조직 또는 조직이 호스트되는 Microsoft 365 Office 365 전사됩니다. 테넌트가 호스트되는 지역은 음성 메일 메시지를 받는 사용자가 있는 지역과 같지 않을 수 있습니다. 테넌트가 호스팅되는 지역을 보려면 조직 [](https://go.microsoft.com/fwlink/p/?linkid=2067339) 프로필 페이지로 이동한 다음 데이터 위치 옆의 **세부** 정보 **보기를 클릭합니다.**

> [!IMPORTANT]
> **New-CsOnlineVoiceMailPolicy** cmdlet을 사용하여 전사 및 전사 불경한 마스킹에 대한 새 정책 인스턴스를 만들 수 없습니다. **Remove-CsOnlineVoiceMailPolicy** cmdlet을 사용하여 기존 정책 인스턴스를 제거할 수 없습니다.

음성메일 정책을 사용하여 사용자에 대한 전사 설정을 관리할 수 있습니다. 사용 가능한 모든 음성우선 정책 인스턴스를 표시하기 위해 [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet을 사용할 수 있습니다.

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
## <a name="turning-off-transcription-for-your-organization"></a>조직에 대한 전사 해제

전사에 대한 기본 설정이 조직에 설정되어 있기 때문에 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)를 사용하여 사용하지 않도록 설정할 수 있습니다. 이렇게 하여 다음을 실행합니다.

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>조직에 대한 전사 언행 마스킹 켜기

전사 언행 마스킹은 기본적으로 조직에서 사용할 수 없습니다. 사용하도록 설정해야 하는 비즈니스 요구 사항이 있는 경우 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)를 사용하여 전사 비하인드 마스킹을 사용하도록 설정할 수 있습니다. 이렇게 하여 다음을 실행합니다.

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a>조직의 기록 기간 변경

최대 기록 길이는 조직에 대해 기본적으로 5분으로 설정됩니다. 최대 기록 길이를 늘리거나 줄이는 비즈니스 요구 사항이 있는 경우 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)를 사용하여 수행될 수 있습니다. 예를 들어 최대 기록 시간을 60초로 설정하면 다음을 실행합니다.

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a>조직에 대한 이중 언어 시스템 프롬프트

기본적으로 음성 메시지 시스템 프롬프트는 음성 메시지를 설정할 때 사용자가 선택한 언어로 발신자에 표시됩니다. 음성 메시지 시스템 프롬프트를 두 언어로 표시해야 하는 비즈니스 요구 사항이 있는 경우 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)를 사용하여 수행될 수 있습니다. 기본 언어와 보조 언어를 설정해야 하며 동일하지 않을 수 있습니다. 이렇게 하여 다음을 실행합니다.

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a>사용자에 대한 전사 해제

사용자 정책은 조직 기본 설정 전에 평가됩니다. 예를 들어 모든 사용자에 대해 음성사본 전사가 사용하도록 설정된 경우 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet을 사용하여 특정 사용자에 대한 전사 기능을 사용하지 않도록 정책을 할당할 수 있습니다.

단일 사용자에 대한 전사 기능을 사용하지 않도록 설정하면 다음을 실행합니다.

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a>사용자에 대한 전사 언행 마스킹 켜기

특정 사용자에 대한 전사 불경한 마스킹을 사용하도록 설정하려면 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet을 사용하여 특정 사용자에 대한 전사 불경한 마스킹을 사용하도록 정책을 할당할 수 있습니다.

단일 사용자에 대한 전사 언행 마스킹을 사용하도록 설정하려면 다음을 실행합니다.

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a>사용자의 기록 기간 변경

먼저 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet을 사용하여 사용자 지정 음성메일 정책을 만들어야 합니다. 아래 표시된 명령은 MaximumRecordingLength가 60초로 설정되고 다른 필드가 테넌트 수준 전역 값으로 설정된 사용자별 온라인 음성우선 정책 OneMinuteVoicemailPolicy를 만듭니다.

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

사용자에게 이 사용자 지정 정책을 할당하기 위해 다음을 실행합니다. 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a>사용자에 대한 이중 언어 시스템 프롬프트

먼저 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet을 사용하여 사용자 지정 음성메일 정책을 만들어야 합니다. 아래 표시된 명령은 PrimarySystemPromptLanguage가 en-US(영어 - 미국)로 설정되어 있으며 SecondarySystemPromptLanguage가 es-SP(스페인어 - 스페인)로 설정된 사용자당 온라인 음성메일 정책 enUS-esSP-VoicemailPolicy를 만듭니다.

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

사용자에게 이 사용자 지정 정책을 할당하기 위해 다음을 실행합니다. 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> Get-CsOnlineVoicemailPolicy cmdlet은 현재 PrimarySystemPromptLanguage 및 SecondarySystemPromptLanguage에 대한 값을 반환하지 않습니다. 다음 값을 참조하려면 다음과 같이 명령을 수정합니다.
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> **PolicyName을** 정책 이름으로 바 대체합니다.


> [!IMPORTANT]
> 음성 Microsoft 365 및 Office 365 서비스는 음성 Office 365 캐시를 캐시하고 6시간마다 캐시를 업데이트합니다. 따라서 정책 변경 내용을 적용하는 데 최대 6시간이 걸릴 수 있습니다.
