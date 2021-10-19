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
description: 사용자에 대한 클라우드 음성 사서함 방법을 자세히 알아보습니다.
ms.openlocfilehash: f448ba79c2451383c0ca85916309bdfab3b69a96
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462372"
---
# <a name="set-up-cloud-voicemail"></a>클라우드 음성 사서함 설정

이 문서는 Microsoft 365 Office 365 모든 사용자에 대한 클라우드 음성 사서함 [](/microsoft-365/admin/add-users/about-admin-roles) 관리자 역할에 설명된 클라우드 음성 사서함 관리자에 대한 것입니다. 클라우드 음성 사서함 메일 메시지를 Exchange 사용자에 대한 사서함이 필요합니다. 타사 전자 메일 시스템을 지원하지 않습니다.

## <a name="cloud-voicemail-for-teams-users"></a>클라우드 음성 사서함 사용자에 Teams

Teams 사용자의 경우 클라우드 음성 사서함 자동으로 설정되고 프로비전됩니다. Microsoft Teams 전화 라이선스가 필요하지 클라우드 음성 사서함.

## <a name="help-your-users-learn-teams-voicemail-features"></a>사용자가 음성 Teams 학습하는 데 도움이 됩니다.

음성메일 사용 및 관리에 대한 사용자에 대한 정보는 다음과 Teams.

- [음성 Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [통화 설정 관리 Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="setting-up-cloud-voicemail-to-work-with-on-premises-users"></a>프레미스 클라우드 음성 사서함 작업할 수 있도록 설정

전자 메일 클라우드 음성 사서함 Exchange 서버에 사서함이 있는 사용자 또는 사용자에 대한 음성 메일 기능을 비즈니스용 Skype 서버. 이 섹션에서는 이러한 시나리오에 대한 정보를 제공합니다. 

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>사서함 사용자에 클라우드 음성 사서함 Exchange Server 설정

다음 정보는 사서함이 있는 클라우드 음성 사서함 사용자와 함께 작업할 Microsoft Teams 전화 구성하는 Exchange Server.

1. 음성 메일 메시지는 사용자의 Exchange 통해 라우팅된 SMTP를 통해 Exchange Online Protection. 이러한 메시지의 성공적인 배달을 사용하도록 설정하려면 Exchange 서버와 Exchange 커넥터가 올바르게 구성되어 있는지 Exchange Online Protection. [커넥터를 사용하여 메일](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)Flow.

2. 클라이언트에서 인사말 사용자 지정 및 비즈니스용 Skype 음성 메일과 같은 Voicemail 기능을 사용하도록 설정하려면 웹 서비스를 통해 Microsoft 365 Office 365 Exchange 서버 사서함에 Exchange 필요합니다. 이 연결을 사용하도록 설정하려면 Exchange 조직과 조직 간에 [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)인증 구성에 설명된 새 Exchange Exchange Online 인증 프로토콜을 구성하거나 2013 CU5 이상에서 Exchange 하이브리드 마법사를 Exchange 실행해야 합니다. 또한 온라인 및 비즈니스용 Skype 및 OAuth 구성에 설명된 비즈니스용 Skype 및 Exchange 서버 간에 통합 및 [Oauth를 비즈니스용 Skype 구성해야 Exchange Server.](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)

### <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>사용자에 클라우드 음성 사서함 비즈니스용 Skype 서버 설정

비즈니스용 Skype 서버 사용자를 클라우드 음성 사서함 프레미스 사용자에 대한 클라우드 음성 사서함 계획 [을 참조합니다.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>조직에서 보호된 음성메일 사용

조직의 사용자에 대한 음성 메일 메시지를 남기면 음성 메일이 사용자의 사서함에 전자 메일 메시지 첨부 파일로 배달됩니다. 메일 흐름 규칙을 사용하여 메시지 암호화를 적용하면 해당 음성 메일 메시지가 다른 받는 사람에게 전달되지 못하게 할 수 있습니다. 보호된 음성 메일을 사용하도록 설정하면 사용자는 음성 메일 사서함으로 전화를 걸거나 Android 또는 iOS용 Outlook, 웹용 Outlook 또는 Outlook 수신기에서 보호된 음성 메일 메시지를 수신 수신할 수 있습니다. 보호된 음성 메일 메시지를 비즈니스용 Skype 또는 Microsoft Teams.

메시지 암호화에 대한 자세한 내용은 메일 흐름 규칙 정의를 참조하여 전자 메일 메시지를 [암호화합니다.](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)
