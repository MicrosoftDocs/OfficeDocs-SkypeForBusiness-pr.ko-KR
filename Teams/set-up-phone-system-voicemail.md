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
description: 사용자에 대한 클라우드 음성 사서함 방법을 자세히 알아보습니다.
ms.openlocfilehash: dd98275ac768990337a47f1f4ba6dacbdb385087
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592723"
---
# <a name="set-up-cloud-voicemail"></a>클라우드 음성 사서함 설정

이 문서는 사용자에 Microsoft 365 설정하려는 클라우드 음성 사서함 관리자를 위한 것입니다.

클라우드 음성 사서함 사서함에 음성 메일 메시지를 Exchange 있습니다. 클라우드 음성 사서함 타사 전자 메일 시스템을 지원하지 않습니다. 라이선스 Exchange Online 요구 사항은 서비스 Exchange Online [참조하세요](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). 관리자 역할에 대한 자세한 내용은 관리자 역할 [정보를 참조하세요](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>클라우드 음성 사서함 프로비전

Teams 사용자의 경우 클라우드 음성 사서함 자동으로 설정되고 프로비전됩니다. *Microsoft Teams 전화 라이선스가 필요하지 클라우드 음성 사서함.*

Teams 사용자에 대한 프로비전은 온라인 사용자에 대한 프로비전과 비즈니스용 Skype 없습니다. 비즈니스용 Skype 온라인 사용자의 경우 사용자가 클라우드 음성 사서함 라이선스가 할당되고 프로비전 시스템에서 전화 시스템 설정될 때 Enterprise Voice 자동으로 설정되고 프로비전됩니다.

비즈니스용 Skype 서버 사용자에 대해 클라우드 음성 사서함 자동으로 설정 및 프로비전됩니다. 그러나 호출을 라우팅하도록 비즈니스용 Skype 서버 환경을 구성해야 클라우드 음성 사서함. 자세한 내용은 프레미스 클라우드 음성 사서함 서비스 계획 [을 참조하세요](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>클라우드 음성 사서함 저장소

사용자 클라우드 음성 사서함 생성된 음성 메일 메시지는 사용자의 Exchange 사서함에 전달되고 저장됩니다Exchange Online 또는 Exchange Server. 음성메일에 대한 특정 저장소나 추가 저장소는 없습니다. 음성 메일에 액세스하는 클라이언트(예: Microsoft Outlook, Microsoft Teams 또는 비즈니스용 Skype)는 Exchange API를 통해 이 작업을 합니다.

음성 메일 메시지에는 음성 메시지와 음성 메일 전사(사용 가능한 경우)가 포함된 첨부된 오디오 파일이 포함되어 있습니다.

사용자의 Exchange 사서함은 사용자 지정 기록 인사말을 저장합니다. 이러한 인사말은 수신 클라우드 음성 사서함 요청에 따라 검색됩니다.

## <a name="cloud-voicemail-processing"></a>클라우드 음성 사서함 처리

호출의 기록 및 전사는 클라우드 음성 사서함 Microsoft 365 호출의 원본에서 시작하여 클라우드 음성 사서함. 그러면 메시지는 사용자의 사서함에 Exchange 전달됩니다.

예를 들어 유럽의 SBC(세션 테두리 컨트롤러)를 통해 사용할 수 없는 직접 라우팅 사용자에게 전화를 걸 경우 음성메일 녹음 및 전사는 유럽에서 수행됩니다. 그러면 메시지는 사용자의 사서함에 Exchange 전달됩니다. 다른 예제의 경우 Teams 사용자가 북아메리카 사용할 수 없는 사용자로 Teams 가정합니다. 이 경우 호출이 북아메리카 시작하고 처리가 북아메리카, 음성 메일이 유럽의 사용자 Exchange 배달됩니다.

다른 전자 메일과 Exchange SMTP(간단한 메일 전송 프로토콜)를 사용하여 사서함에 음성 메일 배달이 수행됩니다.

## <a name="manage-cloud-voicemail-for-users"></a>사용자 클라우드 음성 사서함 관리

사용자에 클라우드 음성 사서함 기능을 관리하기 위해 다음과 같이 Teams PowerShell 모듈을 사용합니다.

사용자 그룹에 클라우드 음성 사서함 기능을 관리하기 위해 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy) cmdlet을 사용 합니다.
통화 응답 규칙, 음성 메시지 전사, 전사 언행 마스킹, 전사 번역 및 시스템 프롬프트 언어와 같은 기능에 대해 기존 또는 새 음성 메시지 정책을 구성하고 할당할 수 있습니다. 자세한 내용은 [New-CsOnlineVoicemailPolicy를 참조하세요](/powershell/module/skype/new-csonlinevoicemailpolicy).

개별 클라우드 음성 사서함 설정 관리하려면 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet을 사용합니다. 클라우드 음성 사서함 사용자에 적용할 수 있는 설정에는 통화 응답 규칙, 프롬프트 언어, 음성 기본 텍스트 및 휴가 인사말이 포함됩니다. 자세한 내용은 [Set-CsOnlineVoicemailUserSettings를 참조하세요](/powershell/module/skype/set-csonlinevoicemailusersettings).
(최종 사용자는  ->  다음으로 이동하여 클라이언트에서 이러한 Teams **CallsConfigure** ->  **Voicemail** 로 이동하여 설정 수 있습니다.

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet을 사용하고 VoicemailEnabled 매개 변수를 $false. 클라우드 음성 사서함 이 설정은 사용자에 대한 클라우드 음성 사서함 더 이상 녹음할 수 없습니다.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>통화에 대한 호출 라우팅을 클라우드 음성 사서함

에 프로비전된 모든 사용자의 기본 설정은 클라우드 음성 사서함 호출 라우팅을 허용하고 사용자가 클라우드 음성 사서함 호출을 전달할 수 있도록 허용하는 클라우드 음성 사서함.

AllowVoicemail 매개 변수를 사용하여 클라우드 음성 사서함 Teams 사용자에 대한 호출 라우팅을 Set-CsTeamsCallingPolicy 제어할 수 있습니다. 자세한 내용은 [Set-CsTeamsCallingPolicy를 참조하세요](/powershell/module/skype/set-csteamscallingpolicy).

- AllowVoicemail을 AlwaysDisabled로 설정한 경우 통화가 음성메일로 라우팅되지 않습니다. 사용자에 대한 통화 전달 또는 변경되지 않은 설정에 관계없이 호출이 음성메일로 라우팅되지 않습니다. 음성메일은 통화 전달 또는 지원되지 않는 설정으로 사용할 수 Teams.

- AllowVoicemail을 AlwaysEnabled로 설정한 경우 사용자의 통화 전달 설정에 관계 없이 30초 동안 벨소리가 울린 후 통화가 음성메일로 항상 전달됩니다.

- AllowVoicemail을 UserOverride로 설정한 경우 사용자의 통화 전달 및/또는 변경되지 않은 설정에 따라 통화가 음성메일로 전달됩니다.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>프레미스 클라우드 음성 사서함 작업할 수 있도록 설정

전자 메일 클라우드 음성 사서함 서버에 사서함이 있는 사용자 또는 사용자 또는 사용자에 대한 음성 메일 기능을 Exchange 음성 메일 기능을 비즈니스용 Skype 서버.

이 섹션에서는 사서함 사용자에 대해 클라우드 음성 사서함 Exchange Server 방법을 설명합니다. 사용자에 대한 클라우드 음성 사서함 비즈니스용 Skype 서버 방법에 대한 자세한 내용은 클라우드 음성 사서함 서비스 계획 [을 참조하세요](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>사서함 사용자에 클라우드 음성 사서함 Exchange Server 설정

다음 정보는 사서함이 있는 클라우드 음성 사서함 사용자와 Teams 구성하는 Exchange Server.

1. 음성 메일 메시지는 사용자 Exchange 통해 라우팅된 SMTP를 통해 Exchange Online Protection. 이러한 메시지를 성공적으로 배달하도록 설정하려면 Exchange 서버와 서버 간에 커넥터가 Exchange 올바르게 Exchange Online Protection. 자세한 [내용은 커넥터를](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 사용하여 메일 구성을 Flow.

2. 클라이언트에서 인사말 사용자 지정 및 Teams 음성 메일과 같은 Voicemail 기능을 사용하도록 설정하려면 Microsoft 365 사서함과 Exchange Server 설정해야 합니다. 이 연결을 사용하도록 설정하려면 Exchange 조직과 조직 간에 [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) 인증 구성에 설명된 Exchange Exchange Online 인증 프로토콜을 구성하거나 2013 CU5 이상에서 Exchange 하이브리드 마법사를 Exchange 실행해야 합니다. 또한 통합 및 [OAuth Teams 및 OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) Teams 및 Exchange Server 간에 통합 및 Oauth를 Teams Exchange Server.

## <a name="enable-protected-voicemail-in-your-organization"></a>조직에서 보호된 음성메일 사용

조직의 사용자에 대한 음성 메일 메시지를 남기면 음성 메일이 사용자의 사서함에 전자 메일 메시지 첨부 파일로 배달됩니다. 

이 Microsoft Information Protection 사용하여 내부 및 외부 호출자 모두에서 남은 음성 메일 메시지를 암호화할 수 있습니다. 사용자가 이러한 메시지를 전달하지 못하도록 할 수도 있습니다. 이 기능은 사서함이 있는 Exchange Online 지원됩니다.

음성 메일 메시지를 암호화하기 위해 민감도 레이블을 만들 수 있습니다. 자동 레이블 지정 기능을 사용하면 들어오는 음성 메일 메시지에 레이블이 자동으로 적용되도록 할 수 있습니다. 

보호된 음성 메일을 사용하도록 설정하면 사용자는 음성 메일 사서함으로 전화를 걸거나 Android 또는 iOS용 음성 메일에서 메시지를 Outlook 웹용 Outlook 또는 Outlook 수신할 수 있습니다. 보호된 음성 메일 메시지를 Microsoft Teams 또는 비즈니스용 Skype.

음성메일에 대한 민감도 레이블을 만들 경우 민감도 레이블 [사용을 참조합니다](/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions). 암호화 **섹션에서** 사용자가 레이블을 적용할 때 권한을 **할당할 수 있도록 를 선택하세요**. **에서 Outlook 다음** 제한 사항 중 하나를 적용한 다음 전달 안 하세요 **옵션을** 선택합니다.

음성메일에 민감도 레이블을 적용하기 위한 자동 레이블 지정 정책을 만들하려면 자동 레이블 지정 정책을 구성하는 방법을 참조 [하고 다음 특정](/microsoft-365/compliance/apply-sensitivity-label-automatically?view=o365-worldwide#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) 설정을 지정합니다.

-   이 **레이블을 적용할** 정보 선택의 경우 사용자 지정 **정책을 선택합니다**.

-   레이블 **을 적용할** 위치를 선택하려면 위치 **: 모든 Exchange 선택합니다**.

-   일반  **또는 고급 규칙을 설정** 하려면 **고급 규칙을 선택합니다**.

- Exchange 규칙:
    - 조건:<br>
        - **헤더는 패턴과 일치합니다.**<br>
              Content-Class = Voice-CA
       -  **보낸 사람 IP 주소는:**<br>
               13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- 자동으로 **적용할** 레이블을 선택하려면 위의 단계에서 음성메일에 대해 만든 민감도 레이블을 선택합니다.

- 전자 **메일에 대한 추가 설정** 은 조직 외부에서 받은 전자 **메일** 에 암호화 적용을 선택하고 권한 관리 소유자를 지정합니다.

보낸 사람 IP 주소에 지정된 IP V4 범위는 URL 및 IP 주소 범위의 ID 12 Office 365 기준으로 [합니다](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams).

메시지 암호화에 대한 자세한 내용은 전자 메일 메시지를 암호화하는 [메일 흐름 규칙 정의를 참조하세요](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>사용자가 기능에 대해 클라우드 음성 사서함 도움말

사용자가 기능을 사용 및 관리하는 방법에 대해 알아보는 데 클라우드 음성 사서함 다음 문서를 추천할 수 있습니다.

- [음성 Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [통화 설정 관리 Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
