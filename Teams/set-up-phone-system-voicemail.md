---
title: 클라우드 음성 사서함 설정
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
description: 사용자에 대한 클라우드 음성 사서함 설정하는 방법을 알아봅니다.
ms.openlocfilehash: 9d6752098ff9dee6294d53fb24f6b7df6ee8e21c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616254"
---
# <a name="set-up-cloud-voicemail"></a>클라우드 음성 사서함 설정

이 문서는 사용자에 대한 클라우드 음성 사서함 설정하려는 Microsoft 365 관리자를 위한 것입니다.

클라우드 음성 사서함 사용자의 Exchange 사서함에 음성 메일 메시지를 입금합니다. 클라우드 음성 사서함 타사 전자 메일 시스템을 지원하지 않습니다. Exchange Online 라이선스 요구 사항은 [Exchange Online 서비스 설명을](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans) 참조하세요. 관리자 역할에 대한 자세한 내용은 [관리자 역할 정보를 참조하세요](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>클라우드 음성 사서함 프로비전

Teams 사용자의 경우 클라우드 음성 사서함 자동으로 설정되고 프로비전됩니다. *클라우드 음성 사서함 Microsoft Teams 전화 라이선스가 필요하지 않습니다.*

Teams 사용자를 위한 프로비저닝은 비즈니스용 Skype Online 사용자와 동일하지 않습니다. 비즈니스용 Skype Online 사용자의 경우 사용자에게 전화 시스템 라이선스가 할당되고 프로비저닝 시스템에서 Enterprise Voice 사용하도록 설정되었을 때 클라우드 음성 사서함 자동으로 설정 및 프로비전되었습니다.

비즈니스용 Skype 서버 온-프레미스 사용자의 경우 클라우드 음성 사서함 자동으로 설정 및 프로비전됩니다. 그러나 호출을 클라우드 음성 사서함 라우팅하도록 비즈니스용 Skype 서버 환경을 구성해야 합니다. 자세한 내용은 [온-프레미스 사용자에 대한 클라우드 음성 사서함 서비스 계획을 참조하세요](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>클라우드 음성 사서함 스토리지

클라우드 음성 사서함 생성된 음성 메일 메시지는 Exchange Online 또는 Exchange Server 사용자의 Exchange 사서함에 배달되고 저장됩니다. 음성 메일에 대한 특정 또는 추가 스토리지가 없습니다. 음성 메일에 액세스하는 클라이언트(예: Microsoft Outlook, Microsoft Teams 또는 비즈니스용 Skype)는 Exchange 사서함 및 제공된 API를 통해 이 작업을 수행합니다.

음성 메일 메시지에는 음성 메시지와 음성 메일 전사가 있는 첨부된 오디오 파일이 포함되어 있습니다(활성화된 경우).

사용자의 Exchange 사서함에는 기록된 사용자 지정 인사말이 저장됩니다. 이러한 인사말은 들어오는 통화 중에 필요에 따라 클라우드 음성 사서함 검색됩니다.

## <a name="cloud-voicemail-processing"></a>클라우드 음성 사서함 처리

클라우드 음성 사서함 녹음 및 전사는 클라우드 음성 사서함 라우팅되는 통화의 원본에 있는 Microsoft 365에서 시작됩니다. 그러면 메시지가 사용자의 Exchange 사서함으로 배달됩니다.

예를 들어 유럽의 SBC(세션 테두리 컨트롤러)를 통해 사용할 수 없는 직접 라우팅 사용자에게 전화가 오면 유럽에서 음성 메일 녹음 및 전사가 수행됩니다. 그러면 메시지가 사용자의 Exchange 사서함으로 배달됩니다. 또 다른 예에서는 북아메리카 Teams 사용자가 유럽에서 사용할 수 없는 Teams 사용자를 호출했다고 가정합니다. 이 경우 통화가 북아메리카 시작되고 북아메리카 처리가 수행된 다음 음성 메일이 유럽의 사용자 Exchange 사서함으로 배달됩니다.

Exchange 사서함에 음성 메일 배달은 다른 전자 메일과 마찬가지로 SMTP(Simple Mail Transport Protocol)를 사용하여 수행됩니다.

## <a name="manage-cloud-voicemail-for-users"></a>사용자에 대한 클라우드 음성 사서함 관리

음성 메일 정책을 지정하고 음성 메일 설정을 구성하여 사용자에 대한 클라우드 음성 사서함 관리할 수 있습니다.  

- **음성 메일 정책을** 사용하면 사용자 그룹에 대한 기능을 관리할 수 있습니다. 통화 응답 규칙, 음성 메일 전사, 전사 욕설 마스킹, 전사 번역 및 시스템 프롬프트 언어와 같은 기능에 대해 기존 또는 새로운 음성 메일 정책을 구성하고 할당할 수 있습니다. 음성 메일 정책 관리에 대한 자세한 내용은 [음성 메일 정책 관리를](manage-voicemail-policies.md) 참조하세요.

- **음성 메일 설정을** 사용하면 개별 사용자에 대한 설정을 구성할 수 있습니다. 통화 응답 규칙, 프롬프트 언어, 텍스트 음성 변환 기본값 및 휴가 인사말과 같은 설정을 구성할 수 있습니다. 개별 사용자에 대한 설정을 구성하는 방법에 대한 자세한 내용은 [음성 메일 설정 관리를 참조하세요](manage-voicemail-settings.md). 최종 사용자는 설정 **-> 통화 -> Voicemail 구성** 으로 이동하여 Teams 클라이언트에서 이러한 설정을 구성할 수도 있습니다.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>클라우드 음성 사서함 호출 라우팅 제어

클라우드 음성 사서함 프로비전된 모든 사용자에 대한 기본 설정은 클라우드 음성 사서함 대한 호출 라우팅을 허용하고 사용자가 클라우드 음성 사서함 호출을 전달할 수 있도록 하는 것입니다.

Teams 관리 센터를 사용하거나 PowerShell을 사용하여 Teams 사용자에게 클라우드 음성 사서함 대한 통화 라우팅이 허용되는지 여부를 제어할 수 있습니다. 

- Teams 관리 센터를 사용하려면 **음성** -> **통화 정책** -> 새 정책을 추가하거나 기존 정책을 편집합니다. > **Voicemail은 인바운드 통화 라우팅에 사용할 수 있습니다**.  

- PowerShell에서 AllowVoicemail 매개 변수와 함께 Set-CsTeamsCallingPolicy cmdlet을 사용합니다. 자세한 내용은 [Set-CsTeamsCallingPolicy를 참조하세요](/powershell/module/skype/set-csteamscallingpolicy).

  - AllowVoicemail을 AlwaysDisabled로 설정하면 사용자의 통화 전달 또는 응답되지 않은 설정에 관계없이 통화가 음성 메일로 라우팅되지 않습니다. Teams에서는 음성 메일을 착신 전환 또는 응답하지 않는 설정으로 사용할 수 없습니다.

  - AllowVoicemail을 AlwaysEnabled로 설정하면 사용자의 응답되지 않은 통화 전달 설정에 관계없이 30초 동안 울린 후 응답이 없는 음성 메일로 통화가 항상 전달됩니다.

  - AllowVoicemail을 UserOverride로 설정하면 통화 전달 및/또는 사용자에 대한 응답이 없는 설정에 따라 통화가 음성 메일로 전달됩니다.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>온-프레미스 사용자와 작업하도록 클라우드 음성 사서함 설정

클라우드 음성 사서함 사용하여 Exchange Server에 사서함이 있는 사용자 또는 비즈니스용 Skype 서버 사용하는 사용자에게 음성 메일 기능을 제공할 수 있습니다.

이 섹션에서는 Exchange Server 사서함 사용자에 대한 클라우드 음성 사서함 설정하는 방법을 설명합니다. 비즈니스용 Skype 서버 사용자에 대한 클라우드 음성 사서함 구성하는 방법에 대한 자세한 내용은 [온-프레미스 사용자에 대한 클라우드 음성 사서함 서비스 계획을 참조하세요](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Exchange Server 사서함 사용자에 대한 클라우드 음성 사서함 설정

다음 정보는 Exchange Server 사서함이 있는 Teams 사용자와 함께 작동하도록 클라우드 음성 사서함 구성하는 방법에 관한 것입니다.

1. 음성 메일 메시지는 Exchange Online Protection 통해 라우팅된 SMTP를 통해 사용자의 Exchange 사서함으로 배달됩니다. 이러한 메시지를 성공적으로 배달하려면 Exchange 서버와 Exchange Online Protection 간에 Exchange Connector가 올바르게 구성되어 있는지 확인합니다. 자세한 내용은 [커넥터를 사용하여 메일 흐름 구성을](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 참조하세요.

2. Teams 클라이언트에서 인사말 및 시각적 음성 메일 사용자 지정과 같은 음성 메일 기능을 사용하도록 설정하려면 Microsoft 365와 Exchange Server 사서함 간의 연결을 설정해야 합니다. 이 연결을 사용하려면 [Exchange와 Exchange Online 조직 간의 OAuth 인증 구성에 설명된 새 Exchange Oauth 인증](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) 프로토콜을 구성하거나 Exchange 2013 CU5 이상에서 Exchange 하이브리드 마법사를 실행해야 합니다. Teams와 Exchange Server [간의 통합 및 OAuth 구성에 설명된 Exchange Server 간에 통합 및 Oauth를 구성](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)해야 합니다.

## <a name="enable-protected-voicemail-in-your-organization"></a>조직에서 보호된 음성 메일 사용

조직 내 사용자에 대한 음성 메일 메시지를 남기면 음성 메일이 사용자의 사서함에 전자 메일 메시지 첨부 파일로 전달됩니다.

Microsoft Purview Information Protection 사용하여 내부 및 외부 발신자가 남긴 음성 메일 메시지를 암호화할 수 있습니다. 사용자가 이러한 메시지를 전달하지 못하도록 방지할 수도 있습니다. 이 기능은 Exchange Online 사서함이 있는 사용자에 대해 지원됩니다.

음성 메일 메시지를 암호화하려면 민감도 레이블을 만들 수 있습니다. 자동 레이블 지정 기능을 사용하면 레이블이 들어오는 음성 메일 메시지에 자동으로 적용되도록 할 수 있습니다.

보호된 음성 메일을 사용하도록 설정하면 사용자는 Outlook, 웹용 Outlook 또는 Android 또는 iOS용 Outlook에서 메시지를 열어 보호된 음성 메일 메시지를 들을 수 있습니다. 보호된 음성 메일 메시지는 Microsoft Teams 또는 비즈니스용 Skype 열 수 없습니다.

음성 메일에 대한 민감도 레이블을 만들려면 [민감도 레이블 사용을 참조하세요](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions). **암호화** 섹션에서 **사용자가 레이블을 적용할 때 사용 권한을 할당하도록 허용을** 선택합니다. **Outlook에서 다음 제한 사항 중 하나를 적용** 한 다음 전달 **안 함** 옵션을 선택합니다.

음성 메일에 민감도 레이블을 적용하는 자동 레이블 지정 정책을 만들려면 [자동 레이블 지정 정책을 구성하는 방법을](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) 참조하고 다음 특정 설정을 지정합니다.

- **이 레이블을 적용할 정보 선택** 의 경우 **사용자 지정 정책을** 선택합니다.

- **레이블을 적용할 위치를 선택하려면** **위치: 모든 사용자에 대한 Exchange를** 선택합니다.

- **일반 또는 고급 규칙을 설정** 하려면 **고급 규칙을** 선택합니다.

- Exchange 규칙:
  - 조건:
    - **헤더 일치 패턴**: Content-Class = Voice-CA
    - **보낸 사람 IP 주소:** 13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- **자동으로 적용할 레이블을 선택하려면** 위의 단계에서 음성 메일에 대해 만든 민감도 레이블을 선택합니다.

- **전자 메일에 대한 추가 설정을** 보려면 **조직 외부에서 받은 전자 메일에 암호화 적용** 을 선택하고 Rights Management 소유자를 지정합니다.

보낸 사람 IP 주소에 지정된 IP V4 범위는 [OFFICE 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)의 ID 12 목록을 기반으로 합니다.

메시지 암호화에 대한 자세한 내용은 [메일 메시지를 암호화하는 메일 흐름 규칙 정의를](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email) 참조하세요.

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>사용자가 클라우드 음성 사서함 기능에 대해 알아보는 데 도움이 됩니다.

사용자가 클라우드 음성 사서함 기능을 사용하고 관리하는 방법을 알아보려면 다음 문서를 추천할 수 있습니다.

- [Teams에서 음성 메일 확인](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Teams에서 통화 설정 관리](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
