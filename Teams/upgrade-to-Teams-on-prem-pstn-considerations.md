---
title: 비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 팀으로 업그레이드 음성 고려 사항
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a709f747d448b8a820cdd3d6fc3d1b732cc4a2a
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955891"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a>IT 관리자를 위해 팀으로 업그레이드할 때 PSTN 고려 사항 &mdash;

이 문서에서는 팀으로 업그레이드할 때의 PSTN (공개 통신 네트워크) 고려 사항에 대해 설명 합니다. 이 문서는 IT 관리자의 업그레이드 개념 및 구현에 대해 설명 하는 몇 가지 항목 중 여섯 번째입니다.  

- [개요](upgrade-to-teams-on-prem-overview.md)
- [업그레이드 방법](upgrade-to-teams-on-prem-upgrade-methods.md)
- [업그레이드 관리 도구](upgrade-to-teams-on-prem-tools.md)
- [비즈니스용 Skype 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항](upgrade-to-teams-on-prem-considerations.md)
- [업그레이드 수행](upgrade-to-teams-on-prem-implement.md)
- **PSTN (공개 통신 네트워크) 고려 사항** (이 문서)

또한 다음 문서에서는 중요 한 업그레이드 개념 및 공존 동작에 대해 설명 합니다.

- [팀과 비즈니스용 Skype의 공존](upgrade-to-teams-on-prem-coexistence.md)
- [공존 모드-참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > 팀과 함께 전화 시스템을 사용 하는 것은 사용자가 TeamsOnly 모드에 있는 경우에만 지원 됩니다.  사용자가 군도 모드에 있는 경우, 전화 시스템은 비즈니스용 Skype 에서만 지원 됩니다. 


## <a name="pstn-calling-scenarios"></a>PSTN 통화 시나리오

팀 전용 모드로 전환할 때는 다음과 같은 네 가지 호출 시나리오가 가능 합니다.

- [Microsoft 전화 요금제를 사용 하 여 비즈니스용 Skype Online의 사용자](#from-skype-for-business-online-with-microsoft-calling-plans)입니다. 업그레이드 되 면이 사용자는 계속 Microsoft 통화 요금제를 보유 하 게 됩니다.

- 비즈니스용 skype Online의 Skype for Business for 온 [-프레미스 음성 기능을 사용 하는 사용자](#from-skype-for-business-online-with-on-premises-voice) 팀으로의 사용자 업그레이드는 사용자가 자신에 게 PSTN 기능을가지고 있는지를 확인 하기 위해 자신을 마이그레이션하도록 조정 해야 합니다.

- [비즈니스용 Skype 온-프레미스에서 엔터프라이즈 음성을 사용 하 여](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)온라인으로 전환 하 고 온-프레미스 PSTN 연결을 유지 하는 사용자입니다.  이 사용자를 팀으로 마이그레이션하면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동 하 고 사용자의 직접 라우팅에 맞게 이동 하도록 조정 해야 합니다. 

- Enterprise Voice를 사용 하는 [비즈니스용 Skype 온-프레미스 사용자](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)로 서, 온라인으로 이동 하 고 Microsoft의 통화 요금제를 사용 하 게 됩니다.  이 사용자를 팀으로 마이그레이션하면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동 하 고 해당 사용자의 전화 번호를 Microsoft 통화 요금제 또는 B로 이동 하 여 사용 가능한 지역에서 새 구독자 번호를 할당 해야 합니다.

이 문서에서는 상위 수준의 개요만 제공 합니다. 자세한 내용은 [전화 시스템 다이렉트 라우팅](direct-routing-landing-page.md) 및 [통화 계획](calling-plan-landing-page.md)을 참조 하세요. 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Microsoft 통화 요금제를 사용 하 여 비즈니스용 Skype Online에서 

이는 음성 관련 가장 간단한 업그레이드 시나리오입니다. 

1. 사용자에 게 팀 라이선스가 할당 되었는지 확인 합니다. 기본적으로 Microsoft 365 또는 Office 365 라이선스를 할당 하는 경우 팀을 사용할 수 있으므로 이전에 팀 라이선스를 사용 하지 않도록 설정 하지 않은 경우에는 아무런 작업도 필요 하지 않습니다.

2.  사용자가 이미 전화 번호를 사용 하는 Microsoft 호출 계획이 있는 경우, TeamsUpgradePolicy에 사용자 팀 전용 모드를 할당 하는 것 으로만 변경 해야 합니다.  팀 전용 모드를 할당 하기 전에 들어오는 PSTN 통화가 사용자의 비즈니스용 Skype 클라이언트에 배치 됩니다. 팀 전용 모드로 업그레이드 한 후에는 들어오는 PSTN 통화가 사용자의 팀 클라이언트에 배치 됩니다.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>온-프레미스 음성으로 비즈니스용 Skype Online에서

이 시나리오에서는 사용자가 이미 비즈니스용 Skype Online에 있지만, 하이브리드 모드 또는 클라우드 커넥터 에디션에 비즈니스용 Skype Server를 사용 하 여 PSTN 연결이 온-프레미스입니다. PSTN 기능을 사용 하 여이 사용자를 팀 전용 모드로 마이그레이션하면 PSTN trunks가 클라우드의 직접 라우팅 서비스에 직접 연결 하 여 온-프레미스 세션 경계 컨트롤러 (SBC)를 통해 직접 라우팅에 사용할 수 있도록 합니다.

기본 단계는 다음과 같습니다.  1-4 단계는 제안 된 순서 대로 나열 되지만 순서에 관계 없이 수행할 수 있습니다. 중요 한 것은 5 단계 이전에 모두 완료 되어야 한다는 것입니다.

1. 테 넌 트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정 하는 경우 앞에서 설명한 대로 해당 아일랜드 모드를 명시적으로 할당 하 여 기존 아일랜드 사용자에 게 grandfather 합니다.

2. 직접 라우팅을 위해 테 넌 트를 구성 합니다. [직접 라우팅의 테 넌 트 단위 구성 요약을](#summary-of-per-tenant-configuration-of-direct-routing)참조 하세요.

3. 필요한 경우 이러한 사용자에 대 한 다양 한 팀 정책을 구성 합니다 (예: TeamsMessagingPolicy, TeamsMeetingPolicy 등). 언제 든 지이 작업을 수행할 수 있지만, 사용자를 업그레이드할 때 올바른 구성을 유지 하려면 사용자가 TeamsOnly 모드로 업그레이드 하기 전에이 작업을 수행 하는 것이 가장 좋습니다.

4. 음성 마이그레이션을 위해 사용자 선택 준비: 
   - 필요한 경우 팀 라이선스를 할당 합니다.  비즈니스용 Skype Online 온-프레미스 음성에서 사용자가 이미 기능을 사용 하 고 있는 경우, 사용자는 이미 비즈니스용 Skype 요금제 2와 Microsoft 전화 시스템을 보유 하 고 있는 것으로 간주 합니다. 비즈니스용 Skype Online 요금제 2 라이선스를 포함 하 여 사용 하도록 설정 된 계획을 모두 유지 합니다.  
   - 원하는 OnlineVoiceRoutingPolicy를 할당 합니다. 

5. 사용자 업그레이드: 이러한 단계는 조정 해야 합니다. 

   - Microsoft 365 또는 Office 365에서 사용자를 TeamsOnly 모드 (CsTeamsUpgradePolicy)로 업그레이드 합니다.
   - SBC에서 온-프레미스 중재 서버 대신 다이렉트 라우팅에 대 한 통화를 보내 들어오는 전화를 사용할 수 있도록 음성 라우팅을 구성 합니다.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>비즈니스용 Skype Server 온-프레미스에서 엔터프라이즈 음성을 사용 하 여 직접 라우팅

이 시나리오에서는 사용자가 계속 비즈니스용 Skype 온-프레미스에 있고, PSTN 연결도 온-프레미스입니다. PSTN 기능을 사용 하 여이 사용자를 팀 전용 모드로 마이그레이션하는 것은 직접 라우팅에 대해 사용 하도록 설정한 다음 사용자를 클라우드로 이동 하는 것을 의미 합니다. 
 
기본 단계는 다음과 같습니다.  1-5 단계는 제안 된 순서 대로 나열 되지만 순서에 관계 없이 수행할 수 있습니다. 중요 한 것은 6 단계 이전에 모두 완료 되어야 한다는 것입니다.

1. 테 넌 트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정 하는 경우 앞에서 설명한 대로 해당 아일랜드 모드를 명시적으로 할당 하 여 기존 아일랜드 사용자를 grandfather 야 합니다.

2. 아직 수행 하지 않은 경우 [비즈니스용 Skype 하이브리드에 맞게 조직을 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)합니다.

3. 직접 라우팅을 위해 테 넌 트를 구성 합니다. [직접 라우팅의 테 넌 트 단위 구성 요약을](#summary-of-per-tenant-configuration-of-direct-routing)참조 하세요.

4. 필요한 경우, 이러한 사용자에 대해 다양 한 팀 정책을 구성 합니다 (예: TeamsMessagingPolicy, TeamsMeetingPolicy 등). 언제 든 지이 작업을 수행할 수 있지만, 업그레이드 시 사용자가 올바른 구성을 보유 하 고 있는지 확인 하려면 사용자가 TeamsOnly으로 업그레이드 하기 전에이 작업을 수행 하는 것이 가장 좋습니다.

5. 필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당 합니다.  사용자는 휴대폰 시스템과 함께 팀과 비즈니스용 Skype Online 요금제 2를 보유 해야 합니다. 비즈니스용 Skype Online 요금제 2를 사용할 수 없는 경우 다시 사용 하도록 설정 합니다.  

6. 사용자 업그레이드: 이러한 단계는 조정 해야 합니다. 

   - 온-프레미스 비즈니스용 Skype 도구를 사용 하 여-MoveToTeams 스위치를 사용 하 여 CsUser Move 사용자를 실행 합니다. -MoveToTeams 스위치를 지원 하지 않는 비즈니스용 Skype Server 버전을 사용 하는 경우 먼저 이동-CsUser를 실행 한 다음 테 넌 트 원격 PowerShell 또는 팀 관리 콘솔에서 TeamsOnly 모드를 할당 합니다.

   - SBC에서 온-프레미스 중재 서버 대신 다이렉트 라우팅에 대 한 통화를 보내 들어오는 전화를 사용할 수 있도록 음성 라우팅을 구성 합니다. 

   - Microsoft 365 또는 Office 365: 나가는 통화를 사용할 수 있도록 관련 OnlineVoiceRoutingPolicy를 할당 합니다. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>비즈니스용 Skype Server 온-프레미스에서 Enterprise Voice를 사용 하 여 Microsoft 통화 요금제로

이 시나리오에서는 사용자가 계속 비즈니스용 Skype 온-프레미스에 있고, PSTN 연결도 온-프레미스입니다. PSTN 기능을 사용 하 여 이러한 사용자를 팀 전용 모드로 마이그레이션하면 사용자를 클라우드로 이동 하 고 이전 캐리어에서 Microsoft 호출 계획으로 해당 번호를 이식 하거나 사용자에 게 새 번호를 할당 하는 것을 의미 합니다. 

기본 단계는 다음과 같습니다.1-5 단계는 제안 된 순서 대로 나열 되지만 순서에 관계 없이 수행할 수 있습니다. 중요 한 것은 6 단계 이전에 모두 완료 되어야 한다는 것입니다. 

1. 테 넌 트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정 하는 경우 앞에서 설명한 대로 해당 아일랜드 모드를 명시적으로 할당 하 여 기존 아일랜드 사용자를 grandfather 야 합니다. 

2. 아직 수행 하지 않은 경우 [비즈니스용 Skype 하이브리드에 맞게 조직을 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)합니다. 

3. 필요한 경우 이러한 사용자에 대 한 다양 한 팀 정책을 구성 합니다 (예: TeamsMessagingPolicy, TeamsMeetingPolicy 등). 언제 든 지이 작업을 수행할 수 있지만, 업그레이드 시 사용자가 올바른 구성을 보유 하 고 있는지 확인 하려면 사용자가 TeamsOnly으로 업그레이드 하기 전에이 작업을 수행 하는 것이 가장 좋습니다. 

4. 필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당 합니다.사용자는 휴대폰 시스템과 함께 팀과 비즈니스용 Skype Online 요금제 2를 보유 해야 합니다. 비즈니스용 Skype Online 요금제 2를 사용할 수 없는 경우 다시 사용 하도록 설정 합니다.  

5. 사용자의 전화 번호를 가져옵니다. (자세한 내용은 [조직의 전화 번호 관리](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)를 참조 하세요.)

   - 번호를 다시 사용 하는 경우에는 해당 통신 업체에 포팅 요청을 제출 합니다.  
   - 또는 Microsoft에서 직접 새 번호를 받을 수 있습니다. 

6. 사용자를 업그레이드 하 고 필요한 경우 LineUri를 할당 합니다. 온-프레미스 비즈니스용 Skype 도구를 사용 하 여-MoveToTeams 스위치와 함께 CsUser Move를 실행 합니다.  

    - Microsoft로 번호를 포팅 하는 경우 포트가 발생할 때이 작업이 발생 하는 시기를 조정 해야 합니다. 

    - Microsoft에서 새 번호를 사용 하는 경우 사용자의 LineUri를 변경 해야 합니다. 사용자가 CsOnlineVoiceUser를 사용 하 여 온라인으로 이동한 후에이 작업을 수행 해야 합니다.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>직접 라우팅의 테 넌 트 단위 구성 요약 

1. [이 목록을](direct-routing-border-controllers.md)검토 하 여 SBC (세션 경계 컨트롤러)가 직접 라우팅이 지원 되는지 확인 합니다. 또한 올바른 펌웨어 버전이 있는지 확인 해야 합니다.  

2. 온-프레미스 SBC를 팀 다이렉트 라우팅 서비스와 쌍으로 연결 합니다. 자세한 내용은 [전화 시스템의 다이렉트 라우팅 서비스에 SBC 페어링](direct-routing-configure.md)을 참조 하세요. 

3. 이 구성은 본질적으로 온-프레미스 구성의 미러입니다. 온라인 구성은 다음으로 구성 됩니다. 
   - OnlineVoiceRoutingPolicy (비즈니스용 Skype Online에서 사용자를 마이그레이션하는 경우 온-프레미스 VoiceRoutingPolicy를 기반으로 하며, 사용자를 Enterprise Voice를 통해 온-프레미스에서 마이그레이션하는 경우 VoicePolicy에 기반을 둔 경우).
   - OnlinePSTNUsage 개체 (온-프레미스 PSTN 사용 기준). 
   - OnlineVoiceRoute 개체 (기반 온-프레미스 VoiceRoute). 

자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요. 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>마이그레이션 중 EnterpriseVoiceEnabled 속성 관리 

직접 라우팅 또는 Microsoft 호출 계획을 사용 하는 경우 사용자는 사용자가 PSTN 기능을 사용할 수 있도록 Azure AD에서 EnterpriseVoiceEnabled = true를 가져야 합니다.  EnterpriseVoiceEnabled ("EV 사용")는 온-프레미스 디렉터리와 클라우드에 모두 존재 하는 속성 (정책 아님)입니다. 클라우드의 가치는 팀에 중요 한 역할을 합니다.  EV 사용이 true로 설정 되는 방법에 대 한 정확한 논리는 다음 시나리오에 따라 달라 집니다. 

- 사용자가 온-프레미스 비즈니스용 Skype 서버에서 EV를 사용 하도록 설정 되어 있고 사용자를 이동-CsUser와 함께 클라우드로 이동 하기 전에 사용자에 게 할당 된 전화 시스템 라이선스가 있는 경우, 온라인 사용자는 EV 사용 = true를 사용 하 여 프로 비전 됩니다. 

- 기존 팀 또는 비즈니스용 Skype Online 사용자에 게 전화 시스템 라이선스가 할당 되 면 기본적으로 EV 사용이 true로 설정 되지 않습니다.  이는 전화 시스템 라이선스를 할당 하기 전에 온-프레미스 사용자가 클라우드로 이동 하는 경우에도 해당 됩니다. 두 경우 모두 관리자는 다음 cmdlet을 지정 해야 합니다. 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>관련 링크

[비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[부여-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS (모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

