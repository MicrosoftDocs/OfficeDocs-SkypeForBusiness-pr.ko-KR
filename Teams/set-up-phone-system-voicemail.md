---
title: 클라우드 보이스 메일 설정
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '사용자를 위해 클라우드 보이스 메일을 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: f53ae3ac948c7b50fa2e68a3fc10cf619299fd16
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571560"
---
# <a name="set-up-cloud-voicemail"></a>클라우드 보이스 메일 설정

이 문서는 비즈니스의 모든 사용자에 대해 클라우드 보이스 메일 기능을 설정 하려는 [Office 365 관리자](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 를 대상으로 합니다.

> [!NOTE]
> 클라우드 보이스 메일은 Exchange 사서함 에서만 depositing 보이스 메일 메시지를 지원 하며 제 3 자 이메일 시스템을 지원 하지 않습니다. 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>클라우드 전용 환경: 클라우드 보이스 메일 설정

비즈니스용 Skype Online 및 통화 계획 사용자의 경우, **전화 시스템** 라이선스와 전화 번호를 할당 한 후 사용자에 대 한 클라우드 보이스 메일이 자동으로 설정 되 고 제공 됩니다.
  
1. 전화 시스템 기능이 요금제에 포함 되어 있지 않은 경우에는 **전화 시스템** 추가 기능 라이선스를 구입 해야 할 수 있습니다. Exchange Online 라이선스를 구입 해야 할 수도 있습니다. [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.
    
2. 비즈니스용 [Office 365에 대 한 라이선스를 할당 또는 제거](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)하 고, [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)및 Exchange Online 라이선스를 비즈니스 사용자에 게 부여 합니다. 이렇게 하면 해당 사용자가 보이스 메일 메시지를 받을 수 있습니다.
    
3. 보이스 메일에 대 한 지원은 3 월 2017 (으)로 추가 되었으며 모든 조직 및 사용자에 대해 기본적으로 사용 하도록 설정 되어 있습니다. Windows PowerShell을 사용 하 고 아래 단계를 수행 하 여 조직의 기록을 사용 하지 않도록 설정할 수 있습니다.

## <a name="phone-system-with-on-premises-environments"></a>온-프레미스 환경에서 사용 하는 전화 시스템

다음 정보는 온-프레미스 호출 계획 환경과 작동 하도록 클라우드 보이스 메일을 구성 하는 것입니다.
  
1. 전화 시스템 기능이 요금제에 포함 되어 있지 않은 경우에는 **전화 시스템** 추가 기능 라이선스를 구입 해야 할 수 있습니다. 또한 Exchange Online 라이선스를 구입 해야 합니다. [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.
    
2. 비즈니스용 [Office 365에 대 한 라이선스를 할당 또는 제거](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)하 고, [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)및 Exchange Online 라이선스를 비즈니스 사용자에 게 부여 합니다.
    
3. 사용자를 위해 배포 된 온-프레미스 PSTN 호출 솔루션에 맞는 지침을 따르세요. Cloud Connector Edition의 경우 [비즈니스용 Skype 클라우드 커넥터 구성 가이드](https://technet.microsoft.com/library/mt605228.aspx)의 **전화 시스템 음성 및 보이스 메일 서비스 사용** 섹션의 지침을 따릅니다. 비즈니스용 Skype 서버와 PSTN 통화를 하려면, [온-프레미스 엔터프라이즈 음성을 사용할 수 있도록 설정](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)합니다. 직접 라우팅에 대 한 자세한 내용은 전화 번호 구성 및 [다이렉트 라우팅 구성](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)의 **enterprise voice and 보이스 메일 사용** 섹션을 참조 하세요.

4. 보이스 메일에 대 한 지원은 3 월 2017 (으)로 추가 되었으며 모든 조직 및 사용자에 대해 기본적으로 사용 하도록 설정 되어 있습니다. Windows PowerShell을 사용 하 고 아래 단계를 수행 하 여 조직의 기록을 사용 하지 않도록 설정할 수 있습니다.

5. 보이스 메일 메시지는 Exchange Online 보호를 통해 라우팅된 SMTP를 통해 사용자의 Exchange 사서함으로 배달 됩니다. 이러한 메시지를 성공적으로 배달 하려면 exchange 서버와 Exchange Online 보호 간에 Exchange 커넥터가 올바르게 구성 되어 있는지 확인 하세요. [커넥터를 사용 하 여 메일 흐름을 구성](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)합니다. 

6. 인사말 사용자 지정, 비즈니스용 Skype 클라이언트의 시각적 보이스 메일 기능을 사용 하도록 설정 하려면 Exchange Web Services를 통해 Office 365에서 Exchange server 사서함으로 연결 해야 합니다. 이 연결을 사용 하도록 설정 하려면 [exchange 및 Exchange Online 조 직 간 Oauth 인증 구성](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)에서 설명한 새 exchange Oauth 인증 프로토콜을 구성 하거나 EXCHANGE 2013 CU5에서 Exchange 하이브리드 마법사를 실행 해야 합니다. 이상. 또한 통합 구성에 설명 된 비즈니스용 Skype Online 및 Exchange server (비즈니스용 [Skype online 및 Exchange server 간](https://docs.microsoft.com/en-us/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises))의 통합 및 oauth를 구성 해야 합니다. 

## <a name="setting-voicemail-policies-in-your-organization"></a>조직에서 음성 메일 정책 설정

> [!WARNING]
> 비즈니스용 Skype 고객의 경우 Microsoft 팀 호출 정책으로 보이스 메일을 사용 하지 않도록 설정 하면 비즈니스용 Skype 사용자를 위한 보이스 메일 서비스를 사용 하지 못할 수도 있습니다.

보이스 메일은 기본적으로 사용 하도록 설정 되어 있으며, 모든 조직 및 사용자에 대해 기본적으로 기록 불경 마스크를 사용할 수 없습니다. 그러나 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 및 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet을 사용 하 여 컨트롤을 제어할 수 있습니다.

조직의 사용자가 받은 보이스 메일 메시지는 Office 365 테 넌 트가 호스팅되는 지역의 transcribed입니다. 테 넌 트가 호스팅되는 영역은 보이스 메일 메시지를 받는 사용자가 있는 지역과 다를 수 있습니다. 테 넌 트가 호스팅되는 지역을 보려면 [조직 프로필](https://go.microsoft.com/fwlink/p/?linkid=2067339) 페이지로 이동한 다음 **데이터 위치**옆에 있는 **세부 정보 보기** 를 클릭 합니다.

> [!IMPORTANT]
> **새 CsOnlineVoiceMailPolicy** cmdlet을 사용 하 여 기록 및 기록 불경 표시 해제에 대 한 새 정책 인스턴스를 만들 수 없으며, **CsOnlineVoiceMailPolicy** cmdlet을 사용 하 여 기존 정책 인스턴스를 제거할 수 없습니다. .

음성 메일 정책을 사용 하 여 사용자의 기록 설정을 관리할 수 있습니다. 사용할 수 있는 모든 보이스 메일 정책 인스턴스를 보려면 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet을 사용 합니다.

 **PS C:\\> CsOnlineVoicemailPolicy**
  
![CsOnlineVoiceMailPolicy 결과 창입니다.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>조직의 기록을 끄는 중

조직에 대 한 기본 기록 설정이 설정 되어 있으므로, [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)를 사용 하 여 기록을 사용 하지 않도록 설정할 수 있습니다. 이 작업을 수행 하려면 다음을 실행 합니다.

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>조직의 기록 불경 마스크 설정

조직에서는 기본적으로 기록 불경 마스크를 사용할 수 없습니다. 기능을 사용 하도록 설정 해야 하는 경우 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)를 사용 하 여 기록 비속어 마스킹을 사용 하도록 설정할 수 있습니다. 이 작업을 수행 하려면 다음을 실행 합니다.

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>사용자에 대 한 기록을 끄는 중

사용자 정책은 조직 기본 설정 전에 평가 됩니다. 예를 들어 모든 사용자에 대해 음성 메일을 사용할 수 있는 경우 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet을 사용 하 여 특정 사용자에 대 한 기록을 사용 하지 않도록 정책을 할당할 수 있습니다.

단일 사용자에 대 한 기록을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>사용자에 대 한 기록 사용 금지 마스크 설정

특정 사용자에 대해 기록 불경 마스크를 사용 하도록 설정 하려면 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet을 사용 하 여 특정 사용자에 대 한 기록 불경 마스크를 사용 하도록 설정 하는 정책을 할당 하면 됩니다.

단일 사용자에 대해 기록 불경 마스크를 사용 하도록 설정 하려면 다음을 실행 합니다.

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Office 365의 보이스 메일 서비스는 음성 메일 정책을 캐시 하 고 4 시간 마다 캐시를 업데이트 합니다. 따라서 정책 변경은 적용 하는 데 최대 4 시간까지 걸릴 수 있습니다.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>사용자가 비즈니스용 Skype 보이스 메일 기능 배우기

사용자에 게 비즈니스용 Skype 보이스 메일을 성공적으로 사용 하는 데 도움이 되는 교육 정보와 기사가 제공 됩니다. 다음 문서를 가리킵니다.

- [비즈니스용 skype 음성 메일 및 옵션 확인](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8):이 문서에서는 비즈니스용 skype에서 음성 메일을 청취 하 고, 음성 사서함을 변경 하 고, 음성 사서함 설정을 변경 하 고, 보이스 메일을 다른 속도로 청취 하는 방법에 대해 설명 합니다.

- [비즈니스용 Skype 2016 교육](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype Online 설정](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능](here-s-what-you-get-with-phone-system.md)

[비즈니스용 Skype 서버 및 Exchange Server 마이그레이션 계획](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


