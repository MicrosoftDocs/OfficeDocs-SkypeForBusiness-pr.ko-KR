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
description: 사용자 집합을 시작하고 실행하기 위해 Microsoft Teams에서 통화 계획을 구성하기 위한 빠른 시작 가이드입니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799768"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>빠른 시작 가이드: Microsoft Teams의 통화 플랜 구성
==============================================================

이 가이드는 Teams에서 통화 계획을 탐색할 수 있도록 사용자 집합을 설정하고 실행하는 데 도움이 됩니다.

2017년 12월 12일, Teams의 통화 계획 발표: [Intelligent Communications는 Teams에서](https://aka.ms/ipyqus) 통화하는 다음 단계를 진행합니다.

> [!NOTE]
> 이 빠른 시작 가이드와 병렬로 통화 계획 [](calling-plan-landing-page.md) 및 [FastTrack을](https://aka.ms/cloudvoice) 통해 전화 시스템을 읽고 성공적인 출시를 계획하고 진행하는 것이 좋습니다.

비즈니스용 Skype에서 제공한 Microsoft 365 및 Office 365 기능인 통화 요금제를 추가하면 이제 Teams를 사용하여 PSTN(공용 전화망)을 통해 유선 및 휴대폰으로 전화를 걸거나 받을 수 있습니다.

![Teams의 연락처 페이지를 보여주는 스크린샷](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Teams에서 통화 탭을 사용하도록 설정하기 **위한** 전제
Teams 사용자의  통화 탭을 사용하려면 Teams에서 1:1 통화를 사용하도록 설정하고 1:1 Teams 통화를 지원하는 Teams 클라이언트를 사용하도록 설정해야 합니다. Teams에서 1:1 통화를 관리하는 방법에 대한 자세한 내용은 [Set-CsTeamsCallingPolicy를 읽어보아야 합니다.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) 어떤 클라이언트가 통화를 지원하는지 알아보고 Microsoft Teams에 대한 제한 및 [사양을 읽어 주세요.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)

> [!NOTE]
> 현재 사용자가 PSTN 통화를 사용하도록 설정되어 있지 않으면 통화 탭에서 음성메일을 사용할 수 없습니다. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Teams에서 다이얼 패드를 사용하도록 설정하기 위한 **전제**
Teams에서 **다이얼** 패드 탭을 사용하도록 설정하고 사용자가 PSTN 통화를 걸고 받을 수 있도록 허용하려면 전화 시스템 및 통화 요금제에 대한 사용자를 프로비전해야 합니다. 통화 요금제 설정 방법에 대한 [](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)자세한 내용은 통화 요금제 설정
또한 Teams 사용자만 Teams 통화 정책에서 "비공개 통화 허용"을 사용하도록 설정되어 있어야 합니다. 자세한 [내용은 새 Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) 관리 센터로 전환하는 동안 Teams 관리를 참조하세요.
> [!NOTE]
> 직접 라우팅을 사용하여 사용자가 PSTN 통화를 걸고 받을 수 있도록 허용할 수도 있습니다. 직접 라우팅을 설정하는 방법에 대한 자세한 내용은 직접 라우팅 [구성을 읽어 읽습니다.](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>TeamsUpgradePolicy를 사용하여 호출 위치 제어
수신 전화(및 채팅)가 Teams 또는 비즈니스용 [Skype에](https://docs.microsoft.com/powershell/module/skype) 있는지 여부를 제어하기 위해 관리자는 [Microsoft Teams](https://aka.ms/teamsadmincenter) 관리 센터 또는 비즈니스용 Skype cmdlet과의 원격 Windows PowerShell 세션을 사용하여 TeamsUpgradePolicy를 사용하세요.


TeamsUpgradePolicy의 기본 구성은 Teams 배포 중에 기존 비즈니스 워크플로가 중단되지 않도록 설계된 제도 모드입니다. 기본적으로 VoIP, PSTN 및 사용자에 대한 페더링된 통화는 Teams로의 인바운드 통화를 사용하도록 정책을 업데이트할 때까지 비즈니스용 Skype로 계속 라우팅됩니다.  받는 사람이 제도 모드에 있는 경우:

 - 비즈니스용 Skype에서 시작된 수신 VOIP 통화는 항상 받는 사람의 비즈니스용 Skype 클라이언트에 있습니다.
 - Teams에서 시작된 수신 VOIP 호출은 보낸 사람 및 받는 사람이 동일한 테넌트에 있는 경우 *Teams에 있습니다.*
 - 받는 페더러드 VOIP(클라이언트가 시작된 클라이언트에 관계 없이) 및 PSTN 통화는 항상 받는 사람의 비즈니스용 Skype 클라이언트에 있습니다.
 
들어오는 VOIP 및 PSTN 통화가 항상 사용자의 Teams 클라이언트에 연결되도록 사용자의 공존 모드를 TeamsOnly로 업데이트합니다(즉, TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당).  공존 모드 및 TeamsUpgradePolicy에 대한 자세한 내용은 [비즈니스용 Skype와](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침을 참조하세요.

**참고 사항**
 - 사용자가 TeamsOnly 모드에 있는 경우에도 비즈니스용 Skype IP 전화기에서 전화를 받게 됩니다.  
 - 비즈니스용 Skype Online에서 사용하기 위해 전화 시스템 및 통화 요금제 라이선스로 프로비전된 사용자(예: OnlineVoiceRoutingPolicy의 값이 할당된 사용자)는 Teams에서 통화 탭을 사용하도록 설정하고 관리자가 관리 작업을 수행하지 않고도 Teams에서 아웃바운드 PSTN 통화를 걸 수 있습니다.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Teams에서 들어오는 모든 VOIP 및 PSTN 통화를 받도록 사용자를 구성하는 방법
사용자가 Teams에서 들어오는 모든 VOIP 및 PSTN 통화를 수신하도록 Microsoft Teams 관리 센터에서 사용자의 공존 모드를 TeamsOnly로 설정하거나 비즈니스용 Skype 원격 Windows PowerShell 세션을 사용하여 다음과 같이 TeamsUpgradePolicy를 업데이트합니다.

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>참고 항목
[통화 플랜 설정](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[통화 플랜을 사용하는 전화 시스템](calling-plan-landing-page.md)

[비즈니스용 Skype PowerShell cmdlet 참조](https://docs.microsoft.com/powershell/module/skype)

