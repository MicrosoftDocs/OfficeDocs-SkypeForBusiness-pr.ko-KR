---
title: 비즈니스용 Skype에서 Teams로 업그레이드할 때 PSTN 고려 사항
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드하기 위한 음성 고려 사항
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72a12cf1dbcb69af7b71bf259568e4a53d1a3a33
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115546"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>비즈니스용 Skype에서 Teams로 업그레이드하기 위한 PSTN 고려 사항

이 문서에서는 Teams로 업그레이드할 때 PSTN(공용 전환 전화 네트워크) 고려 사항을 설명합니다.   


또한 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명합니다.

- [Teams 및 비즈니스용 Skype의 공존](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - Teams와 전화 시스템 사용은 사용자가 TeamsOnly 모드일 때만 지원됩니다.  사용자가 제도 모드인 경우 전화 시스템은 비즈니스용 Skype에서만 지원됩니다. 
 > - 비즈니스용 Skype의 모든 통화 전달, 팀 호출 그룹 및 위임 설정은 마이그레이션되지 않습니다. Teams에 대해 다시 다시 구성해야 합니다.
 > - Microsoft Teams 클라우드 음성 기능에 대한 일반 개요 및 조직에 적합한 Microsoft 음성 솔루션 결정에 대한 자세한 내용은 Teams 음성 솔루션 계획 [을 참조하세요.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>PSTN 호출 시나리오

TeamsOnly 모드로 이동하는 경우 네 가지 가능한 호출 시나리오가 있습니다.

- Microsoft 통화 계획이 있는 [비즈니스용 Skype Online의 사용자입니다.](#from-skype-for-business-online-with-microsoft-calling-plans) 업그레이드 시 이 사용자는 Microsoft 통화 계획을 계속 하게 됩니다.

- [비즈니스용 Skype Online의](#from-skype-for-business-online-with-on-premises-voice) 사용자는 비즈니스용 Skype-프레미스 또는 클라우드 커넥터 에디션을 통해 프레미스 음성 기능을 제공합니다. Teams로의 사용자의 업그레이드는 TeamsOnly 사용자에게 PSTN 기능을 보장하기 위해 사용자를 직접 라우팅으로 마이그레이션하는 방법을 조정해야 합니다.

- [비즈니스용 Skype온-프레미스에서](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)Enterprise Voice 온라인으로 이동하고온-프레미스 PSTN 연결을 유지할 것입니다.  이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고, 사용자의 마이그레이션을 통해 직접 라우팅으로 이동하는 조정이 필요합니다. 

- [비즈니스용 Skype온-프레미스에서](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)Enterprise Voice 온라인으로 이동하고 Microsoft 통화 계획을 사용하는 사용자입니다.  이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 A) 해당 사용자의 전화 번호 포트를 Microsoft 통화 계획 또는 B로 이동하도록 조정해야 합니다. 사용 가능한 지역에서 새 구독자 번호를 할당합니다.

이 문서에서는 고급 개요만 제공합니다. 자세한 내용은 전화 시스템 [직접](direct-routing-landing-page.md) 라우팅 및 통화 [계획 을 참조하세요.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Microsoft 통화 계획을 통해 비즈니스용 Skype Online에서 

음성과 관련된 가장 간단한 업그레이드 시나리오입니다. 

1. 사용자에게 Teams 라이선스가 할당되어 있는지 확인합니다. 기본적으로 Microsoft 365 또는 Office 365 라이선스를 할당할 때 Teams가 사용하도록 설정되어 있으므로 이전에 Teams 라이선스를 사용하지 않도록 설정한 경우 작업이 필요하지 않습니다.

2.  사용자가 이미 전화 번호가 있는 Microsoft 통화 요금제가 있는 경우 TeamsUpgradePolicy에서 사용자 TeamsOnly 모드를 할당하는 것입니다.  TeamsOnly 모드를 할당하기 전에 들어오는 PSTN 호출이 사용자의 비즈니스용 Skype 클라이언트에 표시됩니다. TeamsOnly 모드로 업그레이드한 후 들어오는 PSTN 호출이 사용자의 Teams 클라이언트에 표시됩니다.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>비즈니스용 Skype Online에서온-프레미스 음성으로

이 시나리오에서는 사용자가 비즈니스용 Skype Online에 이미 있지만 해당 PSTN 연결은 하이브리드 모드 또는 Cloud Connector Edition에서 비즈니스용 Skype Server를 사용하는 프레미스에 있습니다. PSTN 기능을 사용하여 이러한 사용자를 TeamsOnly 모드로 마이그레이션하는 것은 PSTN 트렁크가 SBC(On-Premises Session Border Controller)를 통해 클라우드의 직접 라우팅 서비스에 직접 연결하는 직접 라우팅을 사용하도록 설정하는 것을 의미합니다.

기본 단계는 아래에 나열되어 있습니다.  1-4단계는 제안된 순서대로 나열되지만 순서대로 수행될 수 있습니다. 이 모든 작업을 5단계 전에 완료해야 한다는 것이 핵심입니다.

1. 테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정하는 경우 이전에 설명한 바와 같이 섬 모드를 명시적으로 할당하여 기존 아일랜드 사용자를 할아버지 해야 합니다.

2. 직접 라우팅에 대한 테넌트 구성 직접 라우팅의 테넌트당 구성 [요약을 참조합니다.](#summary-of-per-tenant-configuration-of-direct-routing)

3. 원하는 경우 이러한 사용자에 대한 다양한 Teams 정책(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등)을 구성합니다. 이 작업을 언제든 할 수 있지만 업그레이드할 때 사용자가 올바른 구성을 하도록 보장하려면 사용자가 TeamsOnly 모드로 업그레이드되기 전에 이 작업을 하는 것이 가장 좋습니다.

4. 음성 마이그레이션을 위해 선택 사용자를 준비합니다. 
   - 필요한 경우 Teams 라이선스를 할당합니다.  사용자가 비즈니스용 Skype Online온-프레미스 음성에서 이미 작동하고 있는 경우 사용자는 이미 비즈니스용 Skype 요금제 2와 Microsoft Phone System을 갖추고 있습니다. 비즈니스용 Skype Online 계획 2 라이선스를 포함하여 이러한 계획을 모두 사용하도록 설정합니다.  
   - 원하는 OnlineVoiceRoutingPolicy를 할당합니다. 

5. 사용자 업그레이드: 이러한 단계를 조정해야 합니다. 

   - Microsoft 365 또는 Office 365에서 사용자를 TeamsOnly 모드(Grant-CsTeamsUpgradePolicy)로 업그레이드합니다.
   - SBC에서 음성 라우팅을 구성하여 들어오는 통화를 활성화하기 위해 프레미스 중재 서버 대신 직접 라우팅에 대한 호출을 전송합니다.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>비즈니스용 Skype 서버의 온라인 Enterprise Voice 라우팅

이 시나리오에서는 사용자가 여전히 비즈니스용 Skype On-프레미스에 있으며 해당 PSTN 연결도 프레미스에 있습니다. PSTN 기능을 사용하여 이러한 사용자를 TeamsOnly 모드로 마이그레이션하는 것은 직접 라우팅을 사용하도록 설정한 다음 사용자를 클라우드로 이동하는 것입니다. 
 
기본 단계는 아래에 나열되어 있습니다.  1-5단계는 제안된 순서대로 나열되지만 순서대로 할 수 있습니다. 이 모든 작업을 6단계 전에 완료해야 한다는 것이 핵심입니다.

1. 테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정하는 경우 이전에 설명한 바와 같이 아일랜드 모드를 명시적으로 할당하여 기존 아일랜드 사용자를 할아버지 해야 합니다.

2. 아직 수행하지 않은 경우 [비즈니스용 Skype 하이브리드 조직을 구성합니다.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. 직접 라우팅에 대한 테넌트 구성 직접 라우팅의 테넌트당 구성 [요약을 참조합니다.](#summary-of-per-tenant-configuration-of-direct-routing)

4. 원하는 경우 이러한 사용자에 대한 다양한 Teams 정책(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등)을 구성합니다. 이 작업을 언제든 할 수 있지만 사용자가 업그레이드할 때 올바른 구성을 하도록 보장하려면 사용자가 TeamsOnly로 업그레이드하기 전에 이 작업을 하는 것이 가장 좋습니다.

5. 필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당합니다.  사용자에게는 전화 시스템뿐만 아니라 Teams 및 비즈니스용 Skype Online 계획 2가 모두 있습니다. 비즈니스용 Skype Online 계획 2를 사용하지 않도록 설정한 경우 다시 사용하도록 설정합니다.  

6. 사용자 업그레이드: 이러한 단계를 조정해야 합니다. 

   - 비즈니스용 Skype 도구를 사용하여 -MoveToTeams 스위치로 Move-CsUser 실행합니다. -MoveToTeams 스위치를 지원하지 않는 비즈니스용 Skype 서버 버전을 사용하는 경우 먼저 실행을 Move-CsUser 테넌트 원격 PowerShell 또는 Teams 관리 콘솔에서 TeamsOnly 모드를 할당합니다.

   - SBC에서 음성 라우팅을 구성하여 들어오는 통화를 활성화하기 위해 프레미스 중재 서버 대신 직접 라우팅에 대한 호출을 전송합니다. 

   - Microsoft 365 또는 Office 365: 관련 OnlineVoiceRoutingPolicy를 할당하여 통화를 활성화합니다. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>비즈니스용 Skype 서버의 모든 기능을 Enterprise Voice Microsoft 통화 계획으로

이 시나리오에서는 사용자가 여전히 비즈니스용 Skype On-프레미스에 있으며 해당 PSTN 연결도 프레미스에 있습니다. PSTN 기능을 사용하여 이러한 사용자를 TeamsOnly 모드로 마이그레이션하는 것은 사용자를 클라우드로 이동하고 이전 통신 사업자에서 Microsoft 통화 계획으로 번호를 이식하거나 사용자에게 새 번호를 할당하는 것입니다. 

기본 단계는 아래에 나열되어 있습니다.1-5단계는 제안된 순서대로 나열되지만 순서대로 할 수 있습니다. 이 모든 작업을 6단계 전에 완료해야 한다는 것이 핵심입니다. 

1. 테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정하는 경우 이전에 설명한 바와 같이 아일랜드 모드를 명시적으로 할당하여 기존 아일랜드 사용자를 할아버지 해야 합니다. 

2. 아직 수행하지 않은 경우 [비즈니스용 Skype 하이브리드 조직을 구성합니다.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. 원하는 경우 이러한 사용자에 대한 다양한 Teams 정책(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등)을 구성합니다. 이 작업을 언제든 할 수 있지만 사용자가 업그레이드할 때 올바른 구성을 하도록 보장하려면 사용자가 TeamsOnly로 업그레이드하기 전에 이 작업을 하는 것이 가장 좋습니다. 

4. 필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당합니다.사용자에게는 전화 시스템뿐만 아니라 Teams 및 비즈니스용 Skype Online 계획 2가 모두 있습니다. 비즈니스용 Skype Online 계획 2를 사용하지 않도록 설정한 경우 다시 사용하도록 설정합니다.  

5. 사용자에 대한 전화 번호를 얻습니다. (자세한 내용은 조직의 [전화 번호 관리를 참조합니다.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

   - 번호를 다시 사용하는 경우 이동통신사에 이식 요청을 제출합니다.  
   - 또는 Microsoft에서 직접 새 번호를 획득할 수 있습니다. 

6. 사용자를 업그레이드하고 필요한 경우 LineUri를 할당합니다. 비즈니스용 Skype 도구를 사용하여 -MoveToTeams Move-CsUser 실행합니다.  

    - Microsoft에 번호를 포터링하는 경우 포트가 발생할 때 이 작업의 타이밍을 조정해야 합니다. 

    - Microsoft에서 새 번호를 사용하는 경우 사용자에 대한 LineUri를 변경해야 합니다. Set-CsOnlineVoiceUser를 사용하여 사용자가 온라인으로 이동한 후 이 방법을 완료해야 합니다.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>직접 라우팅의 테넌트당 구성 요약 

1. 이 목록을 검토하여 SBC(세션 테두리 컨트롤러)가 직접 라우팅에서 [지원되는지 확인](direct-routing-border-controllers.md) 또한 올바른 버전의 펌웨어가 있는지도 확인해야 합니다.  

2. 팀 다이렉트 라우팅 서비스와 프레미스 SBC를 페어링합니다. 자세한 내용은 전화 시스템의 직접 라우팅 서비스에 [SBC 쌍을 참조합니다.](direct-routing-configure.md) 

3. 이 구성은 기본적으로 프레미스 구성의 미러입니다. 온라인 구성은 다음으로 구성됩니다. 
   - OnlineVoiceRoutingPolicy(비즈니스용 Skype Online에서 사용자를 마이그레이션하는 경우 On-프레미스 VoiceRoutingPolicy에 기반하고, 사용자가 프레미스에서 마이그레이션하는 경우 VoicePolicy를 기반으로 Enterprise Voice.
   - OnlinePSTNUsage 개체(온-프레미스 PSTN 사용량에 따라) 
   - OnlineVoiceRoute 개체(On-Premises VoiceRoute 기반). 

자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>마이그레이션하는 동안 EnterpriseVoiceEnabled 속성 관리 

직접 라우팅 또는 Microsoft 통화 요금제 사용 여부에 따라 사용자가 PSTN 기능을 사용하려면 Azure AD에 EnterpriseVoiceEnabled=true가 있어야 합니다.  EnterpriseVoiceEnabled("EV 사용")는 프레미스 디렉터리와 클라우드 모두에 있는 속성(정책이 아 아우름)입니다. 클라우드의 값은 Teams에 중요한 것입니다.  EV를 사용하도록 설정하는 방법에 대한 정확한 논리는 다음 시나리오에 따라 다릅니다. 

- 사용자가 비즈니스용 Skype 서버에서 EV를 사용하도록 설정하고 이동 CsUser를 통해 사용자를 클라우드로 이동하기 전에 사용자에게 전화 시스템 라이선스가 할당된 경우 온라인 사용자는 EV-enabled=true로 프로비전됩니다. 

- 기존 TeamsOnly 또는 비즈니스용 Skype Online 사용자에게 전화 시스템 라이선스가 할당된 경우 EV 사용은 기본적으로 true로 설정되지 않습니다.  이는 전화 시스템 라이선스를 할당하기 전에 프레미스 사용자가 클라우드로 이동하는 경우에도 해당됩니다. 두 경우 모두 관리자는 다음 cmdlet을 지정해야 합니다. 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>관련 링크

[Teams 음성 솔루션 계획](cloud-voice-landing-page.md)

[비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 연결 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)