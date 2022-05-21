---
title: 인사말 및 전자 메일의 기본 언어 변경
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 조직의 기본 음성 메일 인사말에 다른 언어를 사용하도록 Microsoft Teams 및 비즈니스용 Skype 설정하는 방법을 알아봅니다.
ms.openlocfilehash: 5e486e94470fd6303d132fdaa9c23b0ca6f65b98
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624092"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>인사말 및 전자 메일의 기본 언어 변경

클라우드 음성 사서함 다양한 언어 설정을 사용하여 인사말을 재생하고, 전사 번역을 생성하고, 음성 메일 메시지를 생성합니다. 언어 설정은 기본적으로 테넌트 수준, 정책 또는 지정된 사용자에 대해 개별적으로 지정할 수 있습니다.

## <a name="greetings"></a>인사
음성 메일을 떠나는 발신자에게 인사말이 재생되며 다음과 같은 유형이 될 수 있습니다.

- 시스템 인사말
- 호출 중인 사용자가 기록한 사용자 지정 인사말
- 호출 중인 사용자에게 지정된 사용자 지정 텍스트 음성 변환 인사말

시스템 인사말을 재생하는 데 사용되는 언어는 우선 순위에 따라 사용자에게 할당된 온라인 음성 메일 정책에 지정된 기본 및 보조 프롬프트 언어, 사용자에게 지정된 기본 언어 또는 기본 테넌트 언어입니다.

사용자 지정 및 외부 인사말은 사용자가 선택한 언어로 사용자가 기록합니다.

사용자 또는 테넌트 관리자 사용자에 대해 사용자 지정 텍스트 음성 변환 인사말을 지정하는 경우 음성을 생성하는 데 사용되는 언어는 텍스트 음성 변환 인사말과 함께 지정된 PromptLanguage입니다.

사용자 지정 텍스트 음성 변환 인사말은 사용자에 대해 기록된 사용자 지정 인사말이 없는 경우에만 사용됩니다.

## <a name="transcription"></a>전사
호출 중인 사용자에 대한 온라인 음성 메일 정책에서 사용하도록 설정된 경우 클라우드 음성 사서함 발신자가 남긴 음성 메일을 전사하려고 합니다. 음성 검색을 사용하여 오디오 콘텐츠에 사용되는 언어를 이해하고, 가능하면 검색된 언어를 사용하여 콘텐츠를 전사합니다.

## <a name="transcription-translation"></a>전사 번역
호출 중인 사용자에 대한 온라인 음성 메일 정책에 의해 활성화된 경우 클라우드 음성 사서함 전사된 음성 메일을 번역합니다. 음성 검색 중에 검색된 언어에서 사용자 또는 기본 테넌트 언어에 대해 지정된 기본 언어로 우선 순위순으로 변환됩니다.

## <a name="voicemail-message-template"></a>음성 메일 메시지 템플릿
클라우드 음성 사서함 사용자 또는 기본 테넌트 언어에 지정된 기본 언어를 기반으로 하는 언어 템플릿을 사용하여 음성 메일 메시지를 우선 순위에 따라 생성합니다.

## <a name="setting-the-preferred-language-for-a-user"></a>사용자의 기본 설정 언어 설정
Azure Active Directory 또는 온-프레미스 Active Directory PowerShell을 사용하여 사용자의 기본 설정 언어를 설정할 수 있습니다. 자세한 내용은 [Microsoft 365 또는 Office 365 언어 및 지역 설정을 지정하는 방법을 참조하세요](/office365/troubleshoot/access-management/set-language-and-region).

사용자는 로그인 후 설정을 통해 원하는 언어를 변경할 수 있습니다. 자세한 내용은 [비즈니스용 Microsoft 365 표시 언어 및 표준 시간대 변경을 참조하세요](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US).

## <a name="change-the-system-language-for-everyone-in-your-organization"></a>조직의 모든 사용자에 대한 시스템 언어 변경

1. 에서 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)[전역 관리자](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 계정으로 로그인합니다.

2. Microsoft 365 관리 센터 **설정** > **Org** **settingsOrganization** >  프로필을 선택합니다.
3. **조직 정보를** 선택합니다.
4. 조직의 모든 사용자에 대한 **기본 설정 언어 목록에서 언어** 를 선택합니다.
5. **저장** 을 선택합니다.

**사용 가능한 언어는 조직의 위치에 따라 결정됩니다**. 예를 들어 조직이 미국 있는 경우 기본 언어를 영어 또는 스페인어로 설정할 수 있습니다. 조직이 캐나다에 있는 경우 영어와 프랑스어 중에서 선택할 수 있습니다.

## <a name="supported-languages-in-cloud-voicemail"></a>클라우드 음성 사서함 지원되는 언어
Microsoft Teams 및 비즈니스용 Skype 클라우드 음성 사서함 지원[되는 언어 목록은 지원되는 언어 클라우드 음성 사서함 참조하세요](languages-for-voicemail-greetings-and-messages.md).
  

## <a name="custom-greeting-recorded-by-a-user"></a>사용자가 기록한 사용자 지정 인사말
사용자는 자신의 사용자 지정 및 외부 사용자 지정 인사말을 기록할 수 있습니다. [Teams 데스크톱 클라이언트 설정](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) 및 [비즈니스용 Skype 음성 메일 및 옵션을 확인하세요](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).

## <a name="custom-text-to-speech-greeting-specified-for-a-user"></a>사용자에 대해 지정된 사용자 지정 텍스트 음성 변환 인사말
테넌트 관리자 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet을 사용하여 사용자에 대한 사용자 지정 텍스트 음성 변환 인사말 및 프롬프트 언어를 지정할 수 있습니다.

## <a name="custom-text-to-speech-greeting-specified-by-a-user"></a>사용자가 지정한 사용자 지정 텍스트 음성 변환 인사말
사용자는 자신의 사용자 지정 텍스트 음성 변환 인사말과 인사말에 사용되는 언어를 지정할 수 있습니다. Microsoft Teams 경우 - 사용자는 [Teams 데스크톱 클라이언트 설정](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)에서 음성 메일 인사말을 변경할 수 있습니다. 비즈니스용 Skype 경우 - [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) **프롬프트** 언어에서 새 언어를 선택합니다. 


## <a name="related-articles"></a>관련 기사

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)

[Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)
