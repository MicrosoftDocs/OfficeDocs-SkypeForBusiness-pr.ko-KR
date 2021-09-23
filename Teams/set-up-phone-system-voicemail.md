---
title: 클라우드 음성 사서함 설정
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '사용자에 대한 클라우드 음성 사서함 방법을 자세히 알아보습니다. '
ms.openlocfilehash: 37cf89d4c728cab491d0312762a2c845bb711dcd
ms.sourcegitcommit: 5f19df90443810e027085f8b38d22218e4123a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59482422"
---
# <a name="set-up-cloud-voicemail"></a>클라우드 음성 사서함 설정

이 문서는 Microsoft 365 Office 365 모든 사용자에 대한 클라우드 음성 사서함 [](/microsoft-365/admin/add-users/about-admin-roles) 관리자 역할에 설명된 클라우드 음성 사서함 관리자에 대한 것입니다.

> [!NOTE]
> 클라우드 음성 사서함 사서함에서만 음성 메일 메시지를 Exchange 지원하며 타사 전자 메일 시스템을 지원하지 않습니다. 

> [!NOTE]
> 대리인이 위임자를 대신하여 호출에 응답하면 알림은 위임자에서 사용할 수 클라우드 음성 사서함. 사용자는 부재 중 전화에 대한 알림을 받을 수 있습니다.

## <a name="cloud-voicemail-for-teams-users"></a>클라우드 음성 사서함 사용자에 Teams

Teams 사용자의 경우 클라우드 음성 사서함 자동으로 설정되고 프로비전됩니다. 라이선스는 전화 시스템 라이선스가 필요하지 클라우드 음성 사서함. 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>사서함 사용자에 클라우드 음성 사서함 Exchange Server 설정

다음 정보는 온라인에 클라우드 음성 사서함 사용자와 함께 작업할 수 있도록 전화 시스템 사서함을 Exchange Server. 
  
1. 음성 메일 메시지는 사용자의 Exchange 통해 라우팅된 SMTP를 통해 Exchange Online Protection. 이러한 메시지를 성공적으로 배달하도록 설정하려면 Exchange 서버와 서버 간에 커넥터가 올바르게 Exchange 있는지 Exchange Online Protection. [커넥터를 사용하여 메일](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)Flow. 

2. 클라이언트에서 인사말 사용자 지정 및 비즈니스용 Skype 음성 메일과 같은 Voicemail 기능을 사용하도록 설정하려면 웹 서비스를 통해 Microsoft 365 Office 365 Exchange 서버 사서함에 Exchange 필요합니다. 이 연결을 사용하도록 설정하려면 Exchange 조직과 조직 간에 [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)인증 구성에 설명된 새 Exchange Exchange Online 인증 프로토콜을 구성하거나 2013 CU5 이상에서 Exchange 하이브리드 마법사를 Exchange 실행해야 합니다. 또한 온라인 및 비즈니스용 Skype 및 OAuth 구성에 설명된 비즈니스용 Skype 및 Exchange 서버 간에 통합 및 [Oauth를 비즈니스용 Skype 구성해야 Exchange Server.](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>사용자에 클라우드 음성 사서함 비즈니스용 Skype 서버 설정

비즈니스용 Skype 서버 사용자를 클라우드 음성 사서함 프레미스 사용자에 대한 클라우드 음성 사서함 계획 [을 참조합니다.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>조직에서 보호된 음성메일 사용

조직의 사용자에 대한 음성 메일 메시지를 남기면 음성 메일이 사용자의 사서함에 전자 메일 메시지 첨부 파일로 배달됩니다. 메일 흐름 규칙을 사용하여 메시지 암호화를 적용하면 해당 음성 메일 메시지가 다른 받는 사람에게 전달되지 못하게 할 수 있습니다. 보호된 음성 메일을 사용하도록 설정하면 사용자는 음성 메일 사서함으로 전화를 걸거나 Android 또는 iOS용 Outlook, 웹용 Outlook 또는 Outlook 수신기에서 보호된 음성 메일 메시지를 수신 수신할 수 있습니다. 보호된 음성 메일 메시지를 비즈니스용 Skype 또는 Microsoft Teams.

메시지 암호화에 대한 자세한 내용은 전자 [메일 암호화를 참조하세요.](/microsoft-365/compliance/email-encryption?view=o365-worldwide)


보호된 음성메일을 설정하기 위해 다음을 합니다.

1. 전역 관리자 권한으로 계정으로 이동하여 https://admin.microsoft.com 로그인합니다.
2. 모두 **표시를** 선택한 다음 관리 센터로  >  **Exchange.**
3. 관리 Exchange 메일 흐름 규칙을   >  **선택합니다.**
4. 추가 **+** **를** 선택한 다음 메시지에 Office 365 메시지 암호화 **권한 보호 적용을 선택합니다.**
5. 새 메일 흐름 규칙에 대한 이름을 입력한 다음 이 규칙 적용에서 **메시지** 속성에 메시지 형식 음성 메일  >  **포함 을**  >  **선택합니다.** 확인 **을 선택합니다.**
6. 다음 **작업을 진행할** 때 메시지에 Office 365 메시지 암호화 권한 보호 적용을 선택한 다음 을  **선택합니다.** **RMS 템플릿에서** 전달 **안 을 선택합니다.** **확인을** 선택한 다음 을 **저장합니다.**
    > [!NOTE]
    > **RMS 템플릿 목록이** 비어 있는 경우 메시지 암호화를 설정해야 합니다. 메시지 암호화 설정에 대한 자세한 내용은 다음 문서를 참조하세요.
    > - [새 메시지 암호화 기능 설정](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Azure Information Protection에 대한 템플릿 구성 및 관리](/information-protection/deploy-use/configure-policy-templates)
    > - [전자 메일에 대한 전달 안 하세요 옵션](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

    > [!NOTE]
    > Voicemail 양식을 표시하려는 사용자, 기업 및 조직에 대해 다음 레지스트리 키를 설정해야 합니다. [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Outlook\Addins] "AllowVoicemailForm"=dword:00000001                           

## <a name="help-your-users-learn-teams-voicemail-features"></a>사용자가 음성 Teams 학습하는 데 도움이 됩니다.

음성메일 설정 관리 및 기타 통화 기능 관리에 대한 사용자에 대한 정보는 다음과 Teams.

- [에서](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)통화 설정을 Teams. 이 문서에서는 모든 최종 사용자 호출 기능을 관리하는 Teams 설명합니다. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>사용자가 음성 비즈니스용 Skype 학습할 수 있도록 지원

사용자가 음성 비즈니스용 Skype 수 있도록 도와주는 교육 정보 및 문서가 있습니다. 다음 문서를 지적합니다.

- [비즈니스용 Skype](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)음성 메일 및 옵션 확인: 이 문서에서는 음성 메일에서 음성 메일 비즈니스용 Skype 음성 메일 인사말을 변경하고, 음성 메일 설정을 변경하고, 다른 속도로 음성 메일에 귀를 기울이는 방법을 설명합니다.

- [비즈니스용 Skype 2016 교육](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>관련 주제
[비즈니스용 Skype 온라인 설정](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[다음은 통화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)

[비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획](/SkypeForBusiness/hybrid/plan-um-migration)
