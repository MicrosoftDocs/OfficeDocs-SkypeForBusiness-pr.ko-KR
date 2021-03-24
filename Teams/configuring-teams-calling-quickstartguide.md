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
description: Microsoft Teams에서 호출 계획을 구성하기 위한 빠른 시작 가이드를 통해 사용자 집합을 실행하고 시작할 수 있습니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101184"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>빠른 시작 가이드: Microsoft Teams의 통화 플랜 구성
==============================================================

이 가이드는 Teams에서 통화 계획을 탐색할 수 있도록 사용자 집합을 설정하고 실행하는 데 도움이 됩니다.

2017년 12월 12일, Teams의 통화 계획 발표: [Intelligent Communications는 Teams에서](https://aka.ms/ipyqus) 통화를 통해 다음 단계를 진행합니다.

> [!NOTE]
> 이 빠른 시작 가이드와 병행하여 통화 [](calling-plan-landing-page.md) 계획 및 [FastTrack을](https://aka.ms/cloudvoice) 통해 전화 시스템을 읽고 성공적인 롤아웃을 계획하고 구동하는 것이 좋습니다.

이제 비즈니스용 Skype에서 사용하는 Microsoft 365 및 Office 365 기능인 통화 계획을 추가하여 이제 Teams를 사용하여 PSTN(공용 전화 네트워크)을 통해 전화선 및 휴대폰으로 전화 통화를 걸거나 받을 수 있습니다.

![Teams의 연락처 페이지를 보여주는 스크린샷](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Teams에서 통화 탭을 사용하도록  설정하기 위한 전제
Teams에서  통화 탭을 사용하도록 설정하려면 Teams에서 1:1 호출을 사용하도록 설정하고 1:1 Teams 호출을 지원하는 Teams 클라이언트를 사용해야 합니다. Teams에서 1:1 통화를 관리하는 방법에 대해 알아보고자 하는 경우 [Set-CsTeamsCallingPolicy 를 읽어보아야 합니다.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) 호출을 지원하는 클라이언트를 알아보고자 하는 경우 Microsoft Teams의 제한 및 [사양을 읽어보아야 합니다.](./limits-specifications-teams.md)

> [!NOTE]
> 현재 사용자가 PSTN 호출에 대해 사용하도록 설정되어 있지 않으면 통화 탭에서 Voicemail을 사용할 수 없습니다. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Teams에서 다이얼 패드를 사용하도록 설정하기 **위한** 전제
Teams에서 **다이얼** 패드 탭을 사용하도록 설정하고 사용자가 PSTN 통화를 걸고 받을 수 있도록 허용하려면 전화 시스템 및 통화 요금제에 대한 사용자를 프로비전해야 합니다. 통화 계획을 설정하는 방법에 대해 알아보고자 하는 경우 통화 계획 설정 [을 읽어보아야 합니다.](./set-up-calling-plans.md)
또한 Teams만 사용자에 대해 Teams 호출 정책에서 "개인 호출 허용"이 사용하도록 설정되어 있어야 합니다. 자세한 [내용은 새 Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md) 관리 센터로 전환하는 동안 팀 관리를 참조하세요.
> [!NOTE]
> 직접 라우팅을 사용하여 사용자가 PSTN 통화를 걸고 받을 수 있도록 할 수도 있습니다. 직접 라우팅을 설정하는 방법에 대한 자세한 내용은 직접 라우팅 [구성 을 읽어보아야 합니다.](./direct-routing-configure.md)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>TeamsUpgradePolicy를 사용하여 토지 호출 위치를 제어합니다.
받는 전화(및 채팅)가 Teams 또는 비즈니스용 Skype에 있는지 여부를 제어하려면 관리자는 [Microsoft](https://aka.ms/teamsadmincenter) Teams 관리 센터를 사용하거나 비즈니스용 [Skype](/powershell/module/skype) cmdlet을 사용하여 원격 Windows PowerShell TeamsUpgradePolicy를 사용하세요.


TeamsUpgradePolicy의 기본 구성은 Teams 배포 중에 기존 비즈니스 워크플로가 중단되지 않도록 설계된 제도 모드입니다. 기본적으로 사용자에 대한 VoIP, PSTN 및 페더링된 호출은 Teams에 인바운드 호출을 사용하도록 정책을 업데이트할 때까지 비즈니스용 Skype로 계속 라우팅됩니다.  받는 사람이 섬 모드인 경우:

 - 비즈니스용 Skype에서 시작된 수신 VOIP 호출은 항상 받는 사람의 비즈니스용 Skype 클라이언트에 연결됩니다.
 - 발신자 및 수신자가 동일한 테넌트에 있는 경우 Teams에서 시작된 수신 VOIP 호출은 *Teams에 있습니다.*
 - 들어오는 페더리드 VOIP(클라이언트가 시작된 대상에 관계 없이) 및 PSTN 호출은 항상 받는 사람의 비즈니스용 Skype 클라이언트에 연결됩니다.
 
들어오는 VOIP 및 PSTN 호출이 항상 사용자의 Teams 클라이언트에 랜드되도록 보장하려면 사용자의 공존 모드를 TeamsOnly로 업데이트합니다(즉, TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당합니다.  공존 모드 및 TeamsUpgradePolicy에 대한 자세한 내용은 비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 실행성 지침을 [참조하세요.](./migration-interop-guidance-for-teams-with-skype.md)

**참고 사항**
 - 비즈니스용 Skype IP 휴대폰은 사용자가 TeamsOnly 모드인 경우에도 통화를 수신합니다.  
 - 비즈니스용 Skype Online에 사용할 전화 시스템 및 통화 계획 라이선스로 프로비전된 사용자(예: OnlineVoiceRoutingPolicy의 값)는 Teams에서 사용하도록 설정되고 관리자가 관리 작업을 수행하지 않고 Teams에서 아웃바운드 PSTN 전화를 걸 수 있습니다.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Teams에서 들어오는 모든 VOIP 및 PSTN 호출을 수신하도록 사용자를 구성하는 방법
사용자가 Teams에서 들어오는 모든 VOIP 및 PSTN 통화를 받을 수 있도록 Microsoft Teams 관리 센터에서 TeamsOnly로 사용자의 공존 모드를 설정하거나 비즈니스용 Skype 원격 Windows PowerShell 세션을 사용하여 TeamsUpgradePolicy를 다음과 같이 업데이트합니다.

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>참고 항목
[통화 플랜 설정](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침](./migration-interop-guidance-for-teams-with-skype.md)

[통화 플랜을 사용하는 전화 시스템](calling-plan-landing-page.md)

[비즈니스용 Skype PowerShell cmdlet 참조](/powershell/module/skype)