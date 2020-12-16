---
title: 비즈니스용 Skype-프레미스 배포에서 Teams로 업그레이드할 때 PSTN 고려 사항
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
ms.openlocfilehash: 8a9783f5d60e5a595d548bbfc83ee013500934ed
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686434"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>비즈니스용 Skype-프레미스에서 Teams로 업그레이드하기 위한 PSTN 고려 사항

이 문서에서는 Teams로 업그레이드할 때 PSTN(Public Switched Telephone Network) 고려 사항을 설명하고 있습니다.   


또한 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명하고 있습니다.

- [Teams 및 비즈니스용 Skype의 공존](upgrade-to-teams-on-prem-coexistence.md)
- [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - Teams에서 전화 시스템 사용은 사용자가 TeamsOnly 모드일 때만 지원됩니다.  사용자가 제도 모드인 경우 전화 시스템은 비즈니스용 Skype에서만 지원됩니다. 
 > - 비즈니스용 Skype의 통화 전달, 팀 호출 그룹 및 위임 설정은 마이그레이션되지 않습니다. Teams를 위해 다시 다시 만드셔야 합니다.
 > - Microsoft Teams 클라우드 음성 기능에 대한 일반적인 개요와 조직에 적합한 Microsoft 음성 솔루션을 결정하기 위한 도움말은 Teams 음성 솔루션 계획을 [참조하세요.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>PSTN 통화 시나리오

TeamsOnly 모드로 전환할 때 다음과 같은 4개의 가능한 호출 시나리오가 있습니다.

- Microsoft 통화 요금제가 있는 비즈니스용 [Skype Online의 사용자.](#from-skype-for-business-online-with-microsoft-calling-plans) 업그레이드 시 이 사용자는 계속해서 Microsoft 통화 요금제가 있습니다.

- [비즈니스용 Skype Online의](#from-skype-for-business-online-with-on-premises-voice) 사용자는 비즈니스용 Skype-프레미스 또는 클라우드 커넥터 에디션을 통해 비즈니스용 Skype 음성 기능을 사용할 수 있습니다. Teams로의 사용자의 업그레이드는 TeamsOnly 사용자에게 PSTN 기능이 있도록 사용자를 직접 라우팅으로 마이그레이션하는 데 조정해야 합니다.

- [온라인으로 이동하고](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)Enterprise Voice PSTN 연결을 유지할 수 있는 비즈니스용 Skype의 Enterprise Voice 사용자입니다.  이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 사용자의 마이그레이션과 직접 라우팅을 조정해야 합니다. 

- [온라인으로](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)이동하고 Microsoft 통화 요금제로 Enterprise Voice 비즈니스용 Skype의 사용자입니다.  이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 A) 사용자의 전화 번호 포트를 Microsoft 통화 요금제로 이동하거나 B) 사용 가능한 지역에서 새 구독자 번호를 할당하도록 조정해야 합니다.

이 문서에서는 개략적인 개요만 제공합니다. 자세한 내용은 [전화 시스템](direct-routing-landing-page.md) 직접 라우팅 및 통화 [계획을 참조하세요.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>비즈니스용 Skype Online에서 Microsoft 통화 요금제 사용 

음성과 관련된 가장 간단한 업그레이드 시나리오입니다. 

1. 사용자에게 Teams 라이선스가 할당되어 있는지 확인 기본적으로 Microsoft 365 또는 Office 365 라이선스를 할당하면 Teams가 활성화됩니다. 따라서 이전에 Teams 라이선스를 사용하지 않도록 설정하지 않은 경우 아무 작업도 필요하지 않습니다.

2.  사용자가 이미 전화 번호가 있는 Microsoft 통화 요금제가 있는 경우 필요한 유일한 변경은 TeamsUpgradePolicy에서 사용자 TeamsOnly 모드를 할당하는 것입니다.  TeamsOnly 모드를 할당하기 전에 들어오는 PSTN 통화가 사용자의 비즈니스용 Skype 클라이언트에 연결됩니다. TeamsOnly 모드로 업그레이드한 후 들어오는 PSTN 통화가 사용자의 Teams 클라이언트에 연결됩니다.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>비즈니스용 Skype Online에서 주문형 음성 사용

이 시나리오에서는 사용자가 이미 비즈니스용 Skype Online에 있지만 PSTN 연결은 하이브리드 모드 또는 Cloud Connector Edition에서 비즈니스용 Skype Server를 사용하는 경우의 모든 PSTN 연결입니다. PSTN 기능을 사용하여 이러한 사용자를 TeamsOnly 모드로 마이그레이션하는 것은 직접 라우팅을 사용하도록 설정하는 것을 의미합니다. 이 경우 PSTN 트렁크는 SBC(프레미스 세션 테두리 컨트롤러)를 통해 클라우드의 직접 라우팅 서비스에 직접 연결됩니다.

기본 단계는 다음과 같습니다.  1-4단계는 제안된 순서대로 나열되지만 순서에 따라 완료할 수 있습니다. 핵심은 이러한 모든 작업을 5단계 전에 완료해야 한다는 데 있습니다.

1. 테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나에 설정하는 경우 앞서 설명한 바와 같이 명시적으로 기존 제도 사용자를 할당해야 합니다.

2. 직접 라우팅에 대한 테넌트 구성 직접 라우팅의 테넌트당 [구성 요약을 참조합니다.](#summary-of-per-tenant-configuration-of-direct-routing)

3. 원하는 경우 이러한 사용자에 대한 다양한 Teams 정책(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등)을 구성합니다. 이 작업을 언제든 할 수 있지만 업그레이드할 때 사용자가 올바른 구성을 하도록 하려는 경우 사용자가 TeamsOnly 모드로 업그레이드되기 전에 이 작업을 하는 것이 가장 좋습니다.

4. 음성 마이그레이션을 위해 선택된 사용자를 준비합니다. 
   - 필요한 경우 Teams 라이선스를 할당합니다.  사용자가 비즈니스용 Skype Online-프레미스 음성에서 이미 작동하고 있는 경우 사용자는 이미 비즈니스용 Skype 요금제 2와 Microsoft Phone System을 사용하고 있습니다. 비즈니스용 Skype Online 요금제 2 라이선스를 포함하여 두 요금제 모두를 사용하도록 설정합니다.  
   - 원하는 OnlineVoiceRoutingPolicy를 할당합니다. 

5. 사용자 업그레이드: 이러한 단계를 조정해야 합니다. 

   - Microsoft 365 또는 Office 365에서 사용자를 TeamsOnly 모드(Grant-CsTeamsUpgradePolicy)로 업그레이드합니다.
   - SBC에서 음성 라우팅을 구성하여 전화를 직접 라우팅에 전송하여 수신 전화를 사용하도록 구성합니다.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>비즈니스용 Skype Server의 모든 Enterprise Voice 라우팅에 연결

이 시나리오에서는 사용자가 비즈니스용 Skype의 온라인 프레미스에 계속 있으며 PSTN 연결도 온라인 상태입니다. PSTN 기능을 사용하여 이러한 사용자를 TeamsOnly 모드로 마이그레이션하는 것은 직접 라우팅을 사용하도록 설정한 다음 사용자를 클라우드로 이동하는 것입니다. 
 
기본 단계는 다음과 같습니다.  1-5단계는 제안된 순서대로 나열되지만 순서에 따라 완료할 수 있습니다. 핵심은 이러한 모든 작업을 6단계 전에 완료해야 한다는 데 있습니다.

1. 테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나에 설정하는 경우 앞서 설명한 바와 같이 명시적으로 기존 제도 사용자를 할당해야 합니다.

2. 아직 수행하지 않은 경우 비즈니스용 Skype 하이브리드에 대한 [조직을 구성합니다.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. 직접 라우팅에 대한 테넌트 구성 직접 라우팅의 테넌트당 [구성 요약을 참조합니다.](#summary-of-per-tenant-configuration-of-direct-routing)

4. 원하는 경우 이러한 사용자에 대한 다양한 Teams 정책(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등)을 구성합니다. 이 작업을 언제든 할 수 있지만 업그레이드할 때 사용자가 올바른 구성을 하도록 하려는 경우 사용자가 TeamsOnly로 업그레이드되기 전에 이 작업을 하는 것이 가장 좋습니다.

5. 필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당합니다.  사용자에게는 Teams와 비즈니스용 Skype Online 요금제 2와 전화 시스템이 모두 있습니다. 비즈니스용 Skype Online 요금제 2를 사용하지 않도록 설정한 경우 다시 사용하도록 설정하세요.  

6. 사용자 업그레이드: 이러한 단계를 조정해야 합니다. 

   - -MoveToTeams 스위치로 Move-CsUser 비즈니스용 Skype 도구를 사용하여 실행합니다. -MoveToTeams 스위치를 지원하지 않는 비즈니스용 Skype Server 버전을 사용하는 경우 먼저 이 기능을 Move-CsUser 테넌트 원격 PowerShell 또는 Teams 관리 콘솔에서 TeamsOnly 모드를 할당합니다.

   - SBC에서 음성 라우팅을 구성하여 전화를 직접 라우팅에 전송하여 수신 전화를 사용하도록 구성합니다. 

   - Microsoft 365 또는 Office 365: 관련 OnlineVoiceRoutingPolicy를 할당하여 통화를 활성화합니다. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>비즈니스용 Skype Server의 모든 기능을 Enterprise Voice Microsoft 통화 요금제로

이 시나리오에서는 사용자가 비즈니스용 Skype의 온라인 프레미스에 계속 있으며 PSTN 연결도 온라인 상태입니다. PSTN 기능을 사용하여 이러한 사용자를 TeamsOnly 모드로 마이그레이션하는 것은 사용자를 클라우드로 이동하고 이전 통신 사업자에서 Microsoft 통화 요금제로 번호를 이식하거나 사용자에게 새 번호를 할당하는 것입니다. 

기본 단계는 다음과 같습니다.1-5단계는 제안된 순서대로 나열되지만 순서에 따라 완료할 수 있습니다. 핵심은 이러한 모든 작업을 6단계 전에 완료해야 한다는 데 있습니다. 

1. 테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나에 설정하는 경우 앞서 설명한 바와 같이 명시적으로 기존 제도 사용자를 할당해야 합니다. 

2. 아직 수행하지 않은 경우 비즈니스용 Skype 하이브리드에 대한 [조직을 구성합니다.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. 원하는 경우 이러한 사용자에 대한 다양한 Teams 정책(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등)을 구성합니다. 이 작업을 언제든 할 수 있지만 업그레이드할 때 사용자가 올바른 구성을 하도록 하려는 경우 사용자가 TeamsOnly로 업그레이드되기 전에 이 작업을 하는 것이 가장 좋습니다. 

4. 필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당합니다.사용자에게는 Teams와 비즈니스용 Skype Online 요금제 2와 전화 시스템이 모두 있습니다. 비즈니스용 Skype Online 요금제 2를 사용하지 않도록 설정한 경우 다시 사용하도록 설정하세요.  

5. 사용자의 전화 번호를 얻습니다. (자세한 내용은 [조직의 전화 번호 관리를 참조합니다.)](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

   - 번호를 다시 사용하는 경우 운송업체에 포터링 요청을 제출합니다.  
   - 또는 Microsoft에서 직접 새 번호를 획득할 수 있습니다. 

6. 사용자를 업그레이드하고 필요한 경우 LineUri를 할당합니다. -MoveToTeams 스위치로 Move-CsUser 비즈니스용 Skype 도구를 사용하여 실행합니다.  

    - Microsoft에 숫자를 포식하는 경우 포트가 발생할 때 이 작업의 타이밍을 조정해야 합니다. 

    - Microsoft에서 새 번호를 사용하는 경우 사용자의 LineUri를 변경해야 합니다. 사용자가 Set-CsOnlineVoiceUser를 사용하여 온라인으로 이동한 후에 이 방법을 완료해야 합니다.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>직접 라우팅의 테넌트당 구성 요약 

1. 이 목록을 검토하여 SBC(세션 테두리 컨트롤러)가 직접 라우팅에서 [지원되도록 합니다.](direct-routing-border-controllers.md) 또한 올바른 버전의 펌웨어가 있는지도 확인합니다.  

2. Teams 직접 라우팅 서비스를 통해 프레미스 SBC를 페어링합니다. 자세한 내용은 휴대폰 시스템의 직접 라우팅 서비스에 [SBC 쌍을 참조합니다.](direct-routing-configure.md) 

3. 이 구성은 기본적으로 이 구성의 미러입니다. 온라인 구성은 다음으로 구성됩니다. 
   - OnlineVoiceRoutingPolicy(비즈니스용 Skype Online에서 사용자를 마이그레이션하는 경우와 사용자를 마이그레이션하는 경우 VoicePolicy 기반인 경우 Enterprise Voice)
   - OnlinePSTNUsage 개체(온-프레미스 PSTN 사용량 기준). 
   - OnlineVoiceRoute 개체(On-premises VoiceRoute 기반). 

자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>마이그레이션 중 EnterpriseVoiceEnabled 속성 관리 

사용자가 PSTN 기능을 사용하려면 직접 라우팅 또는 Microsoft 통화 요금제 사용 여부에 따라 Azure AD에서 EnterpriseVoiceEnabled=true가 있어야 합니다.  EnterpriseVoiceEnabled("EV 사용")는 정책이 아닌 속성으로, 이 속성은 클라우드와 모두에 있습니다. 클라우드의 가치는 Teams에 중요합니다.  EV 사용이 true로 설정되는 방법에 대한 정확한 논리는 다음 시나리오에 따라 다릅니다. 

- 사용자가 이동 CsUser를 통해 클라우드로 이동하기 전에 사용자가 EV를 사용하도록 설정하고 사용자에게 전화 시스템 라이선스가 할당된 경우 온라인 사용자는 EV-enabled=true로 프로비전됩니다. 

- 기존 TeamsOnly 또는 비즈니스용 Skype Online 사용자에게 전화 시스템 라이선스가 할당된 경우 EV 사용이 기본적으로 true로 설정되지 않습니다.  이는 전화 시스템 라이선스를 할당하기 전에 클라우드로 이동한 경우에도 해당됩니다. 두 경우 모두 관리자는 다음 cmdlet을 지정해야 합니다. 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>관련 링크

[Teams 음성 솔루션 계획](cloud-voice-landing-page.md)

[비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype Server와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

