---
title: 빠른 시작 가이드 - 통화 계획 구성
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 실행 중인 사용자 집합을 Microsoft Teams 호출 계획을 구성하기 위한 빠른 시작 가이드입니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3bea5bda6f0a03fdd058898361d6cbaa787ae874
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234623"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>빠른 시작 가이드: Microsoft Teams의 통화 플랜 구성

이 가이드는 사용자 집합을 설정하고 실행하는 데 도움이 되어 사용자가 전화 요금제에서 호출 계획을 탐색할 수 Teams.

2017년 12월 12일, Teams: [Intelligent Communications는](https://aka.ms/ipyqus) 다음 단계를 Teams

> [!NOTE]
> 이 빠른 시작 가이드와 병행하여 통화 [](calling-plan-landing-page.md) 계획을 전화 시스템 읽고 성공적인 롤아웃을 계획하고 FastTrack 계획하는 것이 좋습니다. [](https://aka.ms/cloudvoice)

이제 PSTN(공용 Microsoft 365 Office 365)을 통해 전화 통화 요금제와 비즈니스용 Skype 기능을 추가하여 Teams 전화 통화를 걸고 받을 수 있습니다.

![연락처 페이지를 보여주는 화면 Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>통화 탭을 사용할 수 있도록  설정하기 위한 Teams
사용자가 Teams  통화 탭을 사용하도록 설정하려면 사용자가 1:1 Teams 1:1 호출을 지원하는 Teams 클라이언트를 사용하여 1:1 호출을 사용하도록 설정해야 Teams. 에서 1:1 호출을 관리하는 방법을 알아보 Teams [Set-CsTeamsCallingPolicy 를 읽어보아야 합니다.](/powershell/module/skype/set-csteamscallingpolicy) 호출을 지원하는 클라이언트를 알아보시고 에 대한 제한 및 사양을 [Microsoft Teams.](./limits-specifications-teams.md)

> [!NOTE]
> 현재 사용자가 PSTN 호출에 대해 사용하도록 설정되어 있지 않으면 통화 탭에서 Voicemail을 사용할 수 없습니다. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>다이얼 패드를 사용할 수 있도록  설정하기 위한 Teams
전화 걸기 패드 탭을 Teams 사용자가 PSTN 통화를 걸고 받을 수 있도록 허용하려면 사용자 전화 시스템 및 통화 요금제에 대해 사용자를 프로비전해야 합니다.  통화 계획을 설정하는 방법에 대해 알아보고자 하는 경우 통화 계획 설정 [을 읽어보아야 합니다.](./set-up-calling-plans.md)
또한 사용자만 Teams 경우 통화 정책에서 "개인 호출 허용"을 사용하도록 Teams 해야 합니다. 자세한 Teams 관리 [센터로](./manage-teams-skypeforbusiness-admin-center.md) 전환하는 동안 Microsoft Teams 관리 를 참조하세요.
> [!NOTE]
> 직접 라우팅을 사용하여 사용자가 PSTN 통화를 걸고 받을 수 있도록 할 수도 있습니다. 직접 라우팅을 설정하는 방법에 대한 자세한 내용은 직접 라우팅 [구성 을 읽어보아야 합니다.](./direct-routing-configure.md)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>TeamsUpgradePolicy를 사용하여 토지 호출 위치를 제어합니다.
들어오는 호출(및 채팅)이 Teams 비즈니스용 Skype 여부를 제어하기 위해 관리자는 관리자 센터에서 Microsoft Teams 또는 원격 Windows PowerShell [](https://aka.ms/teamsadmincenter) cmdlet을 사용하여 TeamsUpgradePolicy를 [](/powershell/module/skype) 비즈니스용 Skype 있습니다.


TeamsUpgradePolicy의 기본 구성은 기존 비즈니스 워크플로가 배포하는 동안 중단되지 않도록 Teams 모드입니다. 기본적으로 사용자에 대한 VoIP, PSTN Teams 및 페더링된 호출은 정책을 업데이트할 때까지 비즈니스용 Skype 로 라우팅됩니다.  받는 사람이 섬 모드인 경우:

 - 수신 VOIP 호출은 비즈니스용 Skype 클라이언트에 항상 비즈니스용 Skype 호출합니다.
 - 보낸 사람 및 수신기가 동일한 Teams 에 Teams 수신 VOIP 호출
 - 들어오는 페더리드 VOIP(클라이언트가 시작된 대상에 관계 없이) 및 PSTN 호출은 항상 받는 사람의 클라이언트에 비즈니스용 Skype 호출합니다.
 
들어오는 VOIP 및 PSTN 호출이 항상 사용자의 클라이언트에 Teams 있도록 사용자의 공존 모드를 TeamsOnly로 업데이트합니다(즉, TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당합니다.  공존 모드 및 TeamsUpgradePolicy에 대한 자세한 내용은 사용자와 함께 Teams 조직에 대한 마이그레이션 [및](./migration-interop-guidance-for-teams-with-skype.md) 상호운용성 비즈니스용 Skype

**참고 사항**
 - 비즈니스용 Skype 사용자가 TeamsOnly 모드인 경우에도 IP 휴대폰에서 통화가 수신됩니다.  
 - 전화 시스템 온라인과 함께 사용하기 위해 비즈니스용 Skype 및 호출 계획 라이선스로 프로비전된 사용자(예: OnlineVoiceRoutingPolicy의 값)에는 호출 탭이 Teams 설정되고 관리자가 관리 작업을 수행하지 않고도 Teams 아웃바운드 PSTN 호출을 할당할 수 있습니다.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>들어오는 모든 VOIP 및 PSTN 호출을 수신하도록 사용자를 구성하는 Teams
사용자가 수신되는 모든 VOIP 및 PSTN 호출을 Teams 관리 센터에서 TeamsOnly로 설정하거나 Microsoft Teams 비즈니스용 Skype 원격 Windows PowerShell 세션을 사용하여 TeamsUpgradePolicy를 다음과 같이 업데이트합니다.

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>참고 항목
[통화 플랜 설정](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype](./migration-interop-guidance-for-teams-with-skype.md)

[통화 플랜을 사용하는 전화 시스템](calling-plan-landing-page.md)

[비즈니스용 Skype PowerShell cmdlet 참조](/powershell/module/skype)
