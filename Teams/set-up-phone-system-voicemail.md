---
title: 클라우드 음성 메일 설정
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
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
description: '사용자를 위해 Cloud Voicemail을 설정하는 방법을 배워야 합니다. '
ms.openlocfilehash: 81e5f83b251a0bd648cb2ab2afd69f35357fc49f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662213"
---
# <a name="set-up-cloud-voicemail"></a>클라우드 음성 메일 설정

이 문서는 비즈니스의 모든 사용자에 대해 Cloud Voicemail [](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 기능을 설정하려는 관리자 역할에 설명된 Microsoft 365 또는 Office 365 관리자용입니다.

> [!NOTE]
> Cloud Voicemail은 Exchange 사서함에만 음성 메일 메시지 저장을 지원하며 타사 전자 메일 시스템을 지원하지 않습니다. 

> [!NOTE]
> 대리인이 위임자를 대신하여 통화에 응답하면 알림은 Cloud Voicemail에서 사용할 수 없습니다. 사용자는 부재 중 전화에 대한 알림을 받을 수 있습니다.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>클라우드 전용 환경: 온라인 전화 시스템 사용자를 위한 Cloud Voicemail 설정

온라인 전화 시스템 사용자의 경우 사용자에게 전화 시스템 라이선스를 할당하면 Cloud  Voicemail이 자동으로 설정되고 프로비전됩니다. 

> [!NOTE]
> 온라인 비즈니스용 Skype 전화 시스템 사용자에 대해 제공된 전화 번호가 있는 경우 [Set-CsUser -HostedVoicemail](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)$True. 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>사서함 사용자에 대한 클라우드 Exchange Server 설정

다음 정보는 전화 시스템용 온라인이지만 사서함이 있는 사용자와 작업할 수 있도록 Cloud Voicemail을 구성하는 Exchange Server. 
  
1. 음성 메일 메시지는 Exchange Online Protection을 통해 라우팅되는 SMTP를 통해 사용자의 Exchange 사서함에 배달됩니다. 이러한 메시지를 성공적으로 배달하려면 Exchange Server와 Exchange Online Protection 간에 Exchange 커넥터가 올바르게 구성되어 있는지 확인하세요. [커넥터를 사용하여 메일 흐름을 구성합니다.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. 비즈니스용 Skype 클라이언트에서 인사말 및 시각적 음성 메일 사용자 지정과 같은 음성 메일 기능을 사용하려면 Microsoft 365 또는 Office 365에서 Exchange Web Services를 통한 Exchange 서버 사서함으로의 연결이 필요합니다. 이 연결을 사용하려면 Exchange와 Exchange Online 조직 간의 OAuth 인증 구성에 설명된 새 Exchange [Oauth](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)인증 프로토콜을 구성하거나 Exchange 2013 CU5 이상에서 Exchange 하이브리드 마법사를 실행해야 합니다. 또한 비즈니스용 Skype Online과 비즈니스용 Skype Online과 비즈니스용 Skype Online 간의 통합 및 OAuth 구성에 설명된 Exchange 서버 간에 통합 및 [Oauth를](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)Exchange Server. 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>비즈니스용 Skype 서버 사용자를 위한 Cloud Voicemail 설정

Cloud Voicemail에 대한 비즈니스용 Skype 서버 사용자를 구성하는 경우, 클라우드 음성 통화 서비스 계획(On-프레미스 사용자용)을 [참조하세요.](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>조직에서 보호된 음성메일 사용

조직 내 사용자에 대한 음성 메일 메시지를 남기면 음성 메일이 사용자의 사서함에 전자 메일 메시지 첨부 파일로 배달됩니다. 메일 흐름 규칙을 사용하여 메시지 암호화를 적용하면 해당 음성 메일 메시지가 다른 받는 사람에게 전달되지 않도록 할 수 있습니다. 보호된 음성 메일을 사용하도록 설정하면 사용자는 음성 사서함에 전화를 걸거나 Outlook, 웹용 Outlook 또는 Android 또는 iOS용 Outlook에서 메시지를 열고 보호된 음성 메일 메시지를 들을 수 있습니다. 보호된 음성 메일 메시지는 비즈니스용 Skype 또는 Microsoft Teams에서 열 수 없습니다.

메시지 암호화에 대한 자세한 내용은 전자 메일 [암호화를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)

보호된 음성메일을 설정하기 위해 다음을 합니다.

1. 전역 관리자 권한이 있는 계정을 사용하여 이동하여 https://admin.microsoft.com 로그인합니다.
2. 모두 **표시를** 선택한 다음 관리 센터   >  **Exchange로 이동**
3. Exchange 관리 센터에서 **메일** 흐름 규칙을  >  **선택합니다.**
4. 추가를 선택한 다음 **+**  **메시지에 Office 365 메시지 암호화** 및 권한 보호 적용을 선택합니다.
5. 새 메일 흐름 규칙의 이름을 입력한 다음 이 규칙 적용 아래에서 메시지 속성에 메시지 유형 음성 메일   >    >  **포함을 선택합니다.** 확인을 **선택합니다.**
6. 다음 **작업을 통해** **메시지에 Office 365** 메시지 암호화 및 권한 보호 적용을 선택한 다음 하나를 **선택합니다.** **RMS 템플릿에서** 전달 **안 을 선택합니다.** **확인을** 선택한 다음 **저장합니다.**
    > [!NOTE]
    > **RMS 템플릿 목록이** 비어 있는 경우 메시지 암호화를 설정해야 합니다. 메시지 암호화 설정에 대한 자세한 내용은 다음 문서를 참조하세요.
    > - [새 메시지 암호화 기능 설정](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Azure Information Protection에 대한 템플릿 구성 및 관리](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [전자 메일에 대해 전달 안 하세요 옵션](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>조직에서 음성메일 정책 설정

> [!WARNING]
> 비즈니스용 Skype 고객의 경우 Microsoft Teams 통화 정책을 통해 음성메일을 사용하지 않도록 설정하면 비즈니스용 Skype 사용자의 음성메일 서비스를 사용하지 않도록 설정할 수도 있습니다.

음성메일 전사는 기본적으로 사용하도록 설정되어 있으며, 모든 조직 및 사용자에 대해 기본적으로 전사 불경한 언행 마스킹이 비활성화됩니다. 그러나 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 및 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet을 사용하여 제어할 수 있습니다.

조직의 사용자가 받은 음성 메일 메시지는 Microsoft 365 또는 Office 365 조직이 호스팅되는 지역에서 기록됩니다. 테넌트가 호스트되는 지역은 음성 메일 메시지를 받는 사용자가 있는 지역과 같지 않을 수 있습니다. 테넌트가 호스트되는 지역을 보려면 조직 [](https://go.microsoft.com/fwlink/p/?linkid=2067339) 프로필 페이지로 이동한 다음 데이터 위치 옆에 있는 세부 정보 **보기를 클릭합니다.** 

> [!IMPORTANT]
> **New-CsOnlineVoiceMailPolicy** cmdlet을 사용하여 전사 및 전사 불경한 언행 마스킹을 위한 새 정책 인스턴스를 만들 수 없습니다. **Remove-CsOnlineVoiceMailPolicy** cmdlet을 사용하여 기존 정책 인스턴스를 제거할 수 없습니다.

음성메일 정책을 사용하여 사용자의 전사 설정을 관리할 수 있습니다. 사용 가능한 모든 음성메일 정책 인스턴스를 표시하기 위해 [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet을 사용할 수 있습니다.

 **PS C: \\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy 창을 선택합니다.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>조직에 대한 전사 해제

조직에 대한 기본 전사 설정이 설정되어 있기 때문에 [Set-CsOnlineVoicemailPolicy를](https://technet.microsoft.com/library/mt798310.aspx)사용하여 사용하지 않도록 설정할 수 있습니다. 이를 위해 다음을 실행합니다.

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>조직에 대한 전사 불경한 언행 마스킹 켜기

전사 불경한 언행 마스킹은 조직에 대해 기본적으로 사용하지 않도록 설정됩니다. 사용하도록 설정해야 하는 비즈니스 요구 사항이 있는 경우 [Set-CsOnlineVoicemailPolicy를](https://technet.microsoft.com/library/mt798310.aspx)사용하여 전사 불경한 언행 마스킹을 사용하도록 설정할 수 있습니다. 이를 위해 다음을 실행합니다.

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>사용자에 대한 전사 해제

사용자 정책은 조직 기본 설정 전에 평가됩니다. 예를 들어 모든 사용자에 대해 음성메일 전사가 사용하도록 설정된 경우 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet을 사용하여 특정 사용자에 대한 전사를 사용하지 않도록 정책을 할당할 수 있습니다.

단일 사용자에 대한 전사를 사용하지 않도록 설정하는 경우 다음을 실행합니다.

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>사용자에 대한 전사 불경한 언행 마스킹 켜기

특정 사용자에 대해 전사 불경한 언행 마스킹을 사용하도록 설정하려면 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet을 사용하여 특정 사용자에 대해 전사 불경한 언행 마스킹을 사용하도록 정책을 할당할 수 있습니다.

단일 사용자에 대해 전사 불경한 언행 마스킹을 사용하도록 설정하려면 다음을 실행합니다.

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Microsoft 365 및 Office 365의 음성메일 서비스는 음성메일 정책을 캐시하고 4시간마다 캐시를 업데이트합니다. 따라서 정책 변경 내용을 적용하는 데 최대 4시간이 걸릴 수 있습니다.

## <a name="help-your-users-learn-teams-voicemail-features"></a>사용자가 Teams 음성메일 기능을 학습할 수 있도록 지원

Teams의 다른 통화 기능뿐만 아니라 음성메일 설정 관리에 대한 사용자에 대한 다음 정보가 있습니다.

- [Teams에서 통화 설정을 관리합니다.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) 이 문서에서는 모든 최종 사용자 Teams 통화 기능을 관리하는 방법을 설명하고 있습니다. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>사용자가 비즈니스용 Skype 음성메일 기능을 학습할 수 있도록 지원

사용자가 비즈니스용 Skype 음성메일을 성공적으로 사용할 수 있도록 도와주는 교육 정보와 문서가 있습니다. 다음 문서를 설명합니다.

- [비즈니스용 Skype](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)음성 메일 및 옵션 확인: 이 문서에서는 비즈니스용 Skype에서 음성 메일을 듣고, 음성 메일 인사말을 변경하고, 음성 메일 설정을 변경하고, 다양한 속도로 음성 메일을 듣는 방법을 설명하고 있습니다.

- [비즈니스용 Skype 2016 교육](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 설정](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[다음은 전화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)

[비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
