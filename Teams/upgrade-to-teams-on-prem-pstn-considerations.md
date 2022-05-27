---
title: 비즈니스용 Skype Teams 업그레이드할 때 PSTN 고려 사항
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype Teams 업그레이드를 위한 음성 고려 사항
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 130ff6164de3cae82902487f70dd6eaefb631c27
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681349"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>비즈니스용 Skype 온-프레미스에서 Teams 업그레이드하기 위한 PSTN 고려 사항

이 문서에서는 Teams 업그레이드할 때 PSTN(공중 전화망) 고려 사항에 대해 설명합니다.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

다음 문서에서는 중요한 업그레이드 개념 및 공존 동작에 대해 설명합니다.

- [Teams 및 비즈니스용 Skype 공존](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!NOTE]
>
> - Teams 전화 시스템 사용은 사용자의 계정에 Teams 전용 모드의 Teams 업그레이드 정책이 할당된 경우에만 지원됩니다.
> - 비즈니스용 Skype 전화 시스템 사용은 사용자의 계정에 SfB 모드가 있는 Teams 업그레이드 정책이 할당된 경우에만 지원됩니다.
> - 사용자의 계정에 아일랜드 모드의 Teams 업그레이드 정책이 할당된 경우 전화 시스템 지원되지 않습니다.
> - 비즈니스용 Skype 모든 착신 전환, 팀 호출 그룹 및 위임 설정은 마이그레이션되지 않으며 Teams 위해 다시 만들어야 합니다.
> - Microsoft Teams 클라우드 음성 기능에 대한 일반적인 개요와 조직에 적합한 Microsoft 음성 솔루션을 결정하는 데 도움이 되는 방법은 [Teams 음성 솔루션 계획을 참조하세요](cloud-voice-landing-page.md).

## <a name="pstn-calling-scenarios"></a>PSTN 호출 시나리오

TeamsOnly 모드로 전환할 때 다음과 같은 4가지 호출 시나리오가 있습니다.

- [Microsoft 통화 플랜을 사용하는 비즈니스용 Skype Online의 사용자](#from-skype-for-business-online-with-microsoft-calling-plans)입니다. 업그레이드 시 이 사용자는 계속해서 Microsoft 통화 계획을 갖습니다.

- 비즈니스용 Skype 온-프레미스 또는 Cloud Connector Edition[을 통해 온-프레미스 음성 기능을](#from-skype-for-business-online-with-on-premises-voice) 사용하는 비즈니스용 Skype Online의 사용자입니다. TeamsOnly 사용자에게 PSTN 기능이 있는지 확인하려면 사용자의 업그레이드를 직접 라우팅으로 마이그레이션하여 Teams 조정해야 합니다.

- [Enterprise Voice 온-프레미스에 비즈니스용 Skype 사용자는](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing) 온라인으로 이동하고 온-프레미스 PSTN 연결을 유지합니다.  이 사용자를 Teams 마이그레이션하려면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동하고 사용자를 직접 라우팅으로 마이그레이션하는 작업을 조정해야 합니다.

- [Enterprise Voice 온-프레미스에 비즈니스용 Skype 사용자는](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan) 온라인으로 전환하고 Microsoft 통화 플랜을 사용합니다.  이 사용자를 Teams 마이그레이션하려면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동해야 합니다. 사용 가능한 지역에서 새 구독자 번호를 할당하는 A) 사용자의 전화 번호 포트를 Microsoft 통화 플랜 또는 B)로 조정해야 합니다.

이 문서에서는 개략적인 개요만 제공합니다. 자세한 내용은 [전화 시스템 직접 라우팅](direct-routing-landing-page.md) 및 [통화 플랜](calling-plan-landing-page.md)을 참조하세요.

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Microsoft 통화 플랜을 사용하는 비즈니스용 Skype Online에서

이 시나리오는 음성과 관련된 가장 간단한 업그레이드 시나리오입니다.

1. 사용자에게 Teams 라이선스가 할당되었는지 확인합니다. 기본적으로 Microsoft 365 또는 Office 365 라이선스를 할당하면 Teams 사용하도록 설정됩니다. 이전에 Teams 라이선스를 사용하지 않도록 설정하지 않은 한 아무 작업도 필요하지 않습니다.

2. 사용자에게 이미 전화 번호가 있는 Microsoft 통화 플랜이 있는 경우 TeamsUpgradePolicy에서 사용자 TeamsOnly 모드를 할당하는 것만 변경하면 됩니다. TeamsOnly 모드를 할당하기 전에 들어오는 PSTN 호출이 사용자의 비즈니스용 Skype 클라이언트에 연결됩니다. TeamsOnly 모드로 업그레이드한 후 들어오는 PSTN 호출이 사용자의 Teams 클라이언트에 연결됩니다.

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>온-프레미스 음성을 사용하여 비즈니스용 Skype Online에서

이 시나리오에서 사용자는 이미 비즈니스용 Skype Online에 있습니다. 사용자의 PSTN 연결은 하이브리드 모드 또는 Cloud Connector Edition에서 비즈니스용 Skype 서버 사용하여 온-프레미스에 있습니다. PSTN 기능을 사용하여 이러한 사용자를 TeamsOnly 모드로 마이그레이션하려면 사용자가 직접 라우팅을 사용하도록 설정해야 합니다. 직접 라우팅을 사용하면 PSTN 트렁크가 온-프레미스 SBC(세션 테두리 컨트롤러)를 통해 직접 라우팅 서비스에 직접 연결됩니다.

기본 단계는 다음과 같습니다.  1-4단계는 제안된 시퀀스에 나열되지만 순서에 따라 수행할 수 있습니다. 이러한 단계는 5단계 전에 완료해야 합니다.

1. 테넌트 차원의 정책을 비즈니스용 Skype 모드 중 하나로 설정하는 경우 앞에서 설명한 대로 아일랜드 모드를 명시적으로 할당하여 기존 아일랜드 사용자를 할아버지로 지정해야 합니다.

2. 직접 라우팅을 위해 테넌트를 구성합니다. [직접 라우팅의 테넌트별 구성 요약](#summary-of-per-tenant-configuration-of-direct-routing)을 참조하세요.

3. 원하는 경우 이러한 사용자에 대한 다양한 Teams 정책을 구성합니다(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등). 언제든지 poicies를 구성할 수 있습니다. 그러나 업그레이드할 때 사용자가 올바른 구성을 갖도록 하려면 사용자가 TeamsOnly 모드로 업그레이드되기 전에 이러한 정책을 구성합니다.

4. 음성 마이그레이션을 위한 사용자 선택 준비:
   - 필요한 경우 Teams 라이선스를 할당합니다.  사용자가 비즈니스용 Skype Online 온-프레미스 음성에서 이미 작동한다고 가정하면 사용자는 이미 플랜 2 및 Microsoft 전화 System을 비즈니스용 Skype 있습니다. 비즈니스용 Skype Online Plan 2 라이선스를 포함하여 두 계획을 모두 사용하도록 설정합니다.
   - 원하는 OnlineVoiceRoutingPolicy를 할당합니다.

5. 사용자 업그레이드: 이러한 단계를 조정해야 합니다.

   - Microsoft 365 또는 Office 365 사용자를 TeamsOnly 모드(Grant-CsTeamsUpgradePolicy)로 업그레이드합니다.
   - SBC에서 온-프레미스 중재 서버 대신 직접 라우팅으로 전화를 보내 수신 통화를 사용하도록 음성 라우팅을 구성합니다.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Enterprise Voice 있는 비즈니스용 Skype 서버 온-프레미스에서 직접 라우팅으로

이 시나리오에서는 사용자가 여전히 온-프레미스에 비즈니스용 Skype 있습니다. 사용자의 PSTN 연결도 온-프레미스입니다. PSTN 기능을 사용하여 이 사용자를 TeamsOnly 모드로 마이그레이션하려면 사용자가 직접 라우팅을 사용하도록 설정한 다음 사용자를 클라우드로 이동해야 합니다.

기본 단계는 다음과 같습니다. 1-5단계는 제안된 시퀀스에 나열되지만 순서에 따라 수행할 수 있습니다. 6단계 전에 1-5단계를 완료해야 합니다.

1. 테넌트 차원의 정책을 비즈니스용 Skype 모드 중 하나로 설정하는 경우 앞에서 설명한 대로 아일랜드 모드를 명시적으로 할당하여 기존 Islands 사용자를 할아버지에게 지정해야 합니다.

2. 아직 수행하지 않은 경우 [비즈니스용 Skype 하이브리드에 대한 조직을 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)합니다.

3. 직접 라우팅을 위해 테넌트를 구성합니다. [직접 라우팅의 테넌트별 구성 요약](#summary-of-per-tenant-configuration-of-direct-routing)을 참조하세요.

4. 원하는 경우 이러한 사용자에 대한 다양한 Teams 정책을 구성합니다(예: TeamsMessagingPolicy, TeamsMeetingPolicy). 언제든지 정책을 구성할 수 있습니다. 그러나 업그레이드할 때 사용자가 올바른 구성을 갖도록 하려면 사용자가 TeamsOnly로 업그레이드되기 전에 이러한 정책을 구성합니다.

5. 필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당합니다.  사용자에게는 Teams 및 비즈니스용 Skype 온라인 플랜 2와 전화 시스템 모두 있어야 합니다. 비즈니스용 Skype Online 플랜 2를 사용하지 않도록 설정한 경우 다시 사용하도록 설정합니다.

6. 사용자 업그레이드: 이러한 단계를 조정해야 합니다.

   - 온-프레미스 비즈니스용 Skype 도구를 사용하여 -MoveToTeams 스위치를 사용하여 Move-CsUser 실행합니다. -MoveToTeams 스위치를 지원하지 않는 비즈니스용 Skype 서버 버전을 사용하는 경우 먼저 Move-CsUser 실행한 다음 테넌트 원격 PowerShell 또는 Teams 관리 콘솔에서 TeamsOnly 모드를 할당합니다.

   - SBC에서 온-프레미스 중재 서버 대신 직접 라우팅으로 전화를 보내 수신 통화를 사용하도록 음성 라우팅을 구성합니다.

   - Microsoft 365 또는 Office 365: 발신 통화를 사용하도록 설정하려면 관련 OnlineVoiceRoutingPolicy를 할당합니다.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Enterprise Voice 비즈니스용 Skype 서버 온-프레미스에서 Microsoft 통화 플랜으로

이 시나리오에서는 사용자가 여전히 온-프레미스에 비즈니스용 Skype 있습니다. 사용자의 PSTN 연결도 온-프레미스입니다. PSTN 기능을 사용하여 이 사용자를 TeamsOnly 모드로 마이그레이션하려면 사용자를 클라우드로 이동하고 이전 이동 통신 사업자에서 Microsoft 통화 플랜으로 번호를 이식하거나 사용자에게 새 번호를 할당해야 합니다.

기본 단계는 다음과 같습니다. 1-5단계는 제안된 시퀀스에 나열되지만 순서에 따라 수행할 수 있습니다. 6단계 전에 1-5단계를 완료해야 합니다.

1. 테넌트 차원의 정책을 비즈니스용 Skype 모드 중 하나로 설정하는 경우 앞에서 설명한 대로 아일랜드 모드를 명시적으로 할당하여 기존 Islands 사용자를 할아버지에게 지정해야 합니다.

2. 아직 수행하지 않은 경우 [비즈니스용 Skype 하이브리드에 대한 조직을 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)합니다.

3. 원하는 경우 이러한 사용자에 대한 다양한 Teams 정책을 구성합니다(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등). 언제든지 정책을 구성할 수 있습니다. 그러나 업그레이드할 때 사용자가 올바른 구성을 갖도록 하려면 사용자가 TeamsOnly로 업그레이드되기 전에 이러한 정책을 구성합니다.

4. 필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당합니다. 사용자에게는 Teams 및 비즈니스용 Skype 온라인 플랜 2와 전화 시스템 모두 있어야 합니다. 비즈니스용 Skype Online 플랜 2를 사용하지 않도록 설정한 경우 다시 사용하도록 설정합니다.

5. 사용자의 전화 번호를 가져옵니다. 자세한 내용은 [조직의 전화 번호 관리를 참조하세요](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

   - 숫자를 다시 사용하는 경우 운송업체에 포팅 요청을 제출합니다.
   - 또는 Microsoft에서 직접 새 숫자를 가져올 수 있습니다.

6. 사용자를 업그레이드하고 필요한 경우 LineUri를 할당합니다. 온-프레미스 비즈니스용 Skype 도구를 사용하여 -MoveToTeams 스위치를 사용하여 Move-CsUser 실행합니다.

    - Microsoft로 번호를 포팅하는 경우 포트가 발생할 때 발생할 이 작업의 타이밍을 조정해야 합니다.

    - Microsoft에서 새 번호를 사용하는 경우 Set-CsPhoneNumberAssignment를 사용하여 사용자가 온라인으로 이동한 후 사용자의 LineUri를 변경해야 합니다.

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>직접 라우팅의 테넌트별 구성 요약

1. [이 목록을](direct-routing-border-controllers.md) 검토하여 SBC(세션 테두리 컨트롤러)가 직접 라우팅에서 지원되는지 확인합니다. 또한 올바른 버전의 펌웨어가 있는지 확인합니다.

2. 온-프레미스 SBC를 Teams 직접 라우팅 서비스와 페어링합니다. 자세한 내용은 [SBC를 전화 시스템 직접 라우팅 서비스에 페어링](direct-routing-configure.md)을 참조하세요.

3. 이 구성은 기본적으로 온-프레미스 구성의 미러입니다. 온라인 구성은 다음으로 구성됩니다.
   - OnlineVoiceRoutingPolicy(비즈니스용 Skype Online에서 사용자를 마이그레이션하는 경우 온-프레미스 VoiceRoutingPolicy를 기반으로 하며, Enterprise Voice 사용하여 온-프레미스에서 사용자를 마이그레이션하는 경우 VoicePolicy를 기반으로 합니다.
   - OnlinePSTNUsage 개체(온-프레미스 PSTN 사용량 기준)
   - OnlineVoiceRoute 개체(온-프레미스 VoiceRoute 기반)

자세한 내용은 [직접 라우팅 구성을 참조하세요](direct-routing-configure.md).

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>마이그레이션하는 동안 EnterpriseVoiceEnabled 속성 관리

직접 라우팅을 사용하든 Microsoft 통화 플랜을 사용하든 사용자가 PSTN 기능을 사용하려면 Azure AD EnterpriseVoiceEnabled=true가 있어야 합니다.  EnterpriseVoiceEnabled("EV 사용")는 온-프레미스 디렉터리와 클라우드에 모두 존재하는 속성(정책이 아님)입니다. 클라우드의 가치는 Teams 중요합니다.  EV 사용이 true로 설정되는 방법에 대한 정확한 논리는 다음 시나리오에 따라 달라집니다.

- 사용자가 온-프레미스 비즈니스용 Skype 서버 EV를 사용할 수 있고 Move-CsUser를 사용하여 사용자를 클라우드로 이동하기 전에 사용자에게 전화 시스템 라이선스가 할당된 경우 온라인 사용자는 EV 지원=true로 프로비전됩니다.

- 기존 TeamsOnly 또는 비즈니스용 Skype Online 사용자에게 전화 시스템 라이선스가 할당된 경우 EV 사용은 기본적으로 true로 설정되지 않습니다. 또한 전화 시스템 라이선스를 할당하기 전에 온-프레미스 사용자가 클라우드로 이동되는 경우도 있습니다. 두 경우 모두 관리자는 다음 cmdlet을 지정해야 합니다.

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True
  ```

## <a name="related-links"></a>관련 링크

[Teams 음성 솔루션 계획](cloud-voice-landing-page.md)

[비즈니스용 Skype 함께 Teams 사용하는 조직을 위한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)

[비즈니스용 Skype 서버 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
