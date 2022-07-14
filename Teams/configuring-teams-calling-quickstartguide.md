---
title: 빠른 시작 가이드 - 통화 플랜 구성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 사용자 집합을 시작하고 실행할 수 있도록 Microsoft Teams에서 통화 플랜을 구성하기 위한 빠른 시작 가이드입니다.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ff6c85e337e2a3fe226347fc0b0ef68710d3d18
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789583"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>빠른 시작 가이드: Microsoft Teams의 통화 플랜 구성

이 가이드는 Teams에서 통화 플랜을 탐색할 수 있도록 사용자 집합을 시작하고 실행하는 데 도움이 됩니다.

2017년 12월 12일, Teams의 통화 플랜 발표: [지능형 커뮤니케이션은 Teams에서 통화와 함께 다음 단계를 수행합니다](https://aka.ms/ipyqus).

> [!NOTE]
> 이 빠른 시작 가이드와 병행하여 통화 플랜 및 [FastTrack](https://aka.ms/cloudvoice)[이 있는 전화 시스템을](calling-plan-landing-page.md) 읽고 성공적인 출시를 계획하고 추진하는 것이 좋습니다.

비즈니스용 Skype 제공하는 Microsoft 365 및 Office 365 기능인 통화 플랜을 추가하여 이제 Teams를 사용하여 공중 전화망(PSTN)을 통해 유선 및 휴대폰으로 전화를 걸고 받을 수 있습니다.

![Teams의 연락처 페이지를 보여 주는 스크린샷.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Teams에서 **통화** 탭을 사용하도록 설정하기 위한 필수 구성 요소
Teams에서 **통화** 탭을 사용하도록 설정하려면 Teams에서 1:1 통화를 사용하도록 설정하고 1:1 Teams 통화를 지원하는 Teams 클라이언트를 사용해야 합니다. Teams에서 1:1 통화를 관리하는 방법을 알아보려면 [Set-CsTeamsCallingPolicy를](/powershell/module/skype/set-csteamscallingpolicy) 읽어보세요. 통화를 지원하는 클라이언트에 대해 알아보려면 [Microsoft Teams의 제한 사항 및 사양을](./limits-specifications-teams.md) 읽어보세요.

> [!NOTE]
> 현재 사용자가 PSTN 호출을 사용하도록 설정하지 않으면 통화 탭에서 음성 메일을 사용할 수 없습니다. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Teams에서 **Dial Pad** 를 사용하도록 설정하기 위한 필수 구성 요소
Teams에서 **Dial Pad** 탭을 사용하도록 설정하고 사용자가 PSTN 전화를 걸고 받을 수 있도록 하려면 전화 시스템 및 통화 플랜에 대한 사용자를 프로비전해야 합니다. 통화 플랜을 설정하는 방법을 알아보려면 [통화 플랜 설정을](./set-up-calling-plans.md) 읽어보세요.
또한 Teams 사용자만의 경우 Teams 통화 정책에서 "프라이빗 통화 허용"이 사용하도록 설정되어 있는지 확인해야 합니다. 자세한 내용은 [새 Microsoft Teams 관리 센터로 전환하는 동안 Teams 관리를](./manage-teams-skypeforbusiness-admin-center.md) 참조하세요.
> [!NOTE]
> 직접 라우팅을 사용하여 사용자가 PSTN 전화를 걸고 받을 수 있도록 할 수도 있습니다. 직접 라우팅을 설정하는 방법을 알아보려면 [직접 라우팅 구성을](./direct-routing-configure.md) 읽어보세요.

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>TeamsUpgradePolicy를 사용하여 호출 위치 제어
수신 통화(및 채팅)가 Teams 또는 비즈니스용 Skype 들어오는지 여부를 제어하기 위해 관리자는 [Microsoft Teams 관리 센터를](https://aka.ms/teamsadmincenter) 사용하거나 [비즈니스용 Skype cmdlet](/powershell/module/skype)과 원격 Windows PowerShell 세션을 사용하여 TeamsUpgradePolicy를 사용합니다.


TeamsUpgradePolicy의 기본 구성은 Islands 모드로, Teams 배포 중에 기존 비즈니스 워크플로가 중단되지 않도록 설계되었습니다. 기본적으로 사용자에 대한 VoIP, PSTN 및 페더레이션된 호출은 Teams에 대한 인바운드 통화를 사용하도록 정책을 업데이트할 때까지 계속 비즈니스용 Skype 라우팅됩니다.  받는 사람이 아일랜드 모드에 있는 경우:

 - 비즈니스용 Skype 시작된 수신 VOIP 호출은 항상 받는 사람의 비즈니스용 Skype 클라이언트에 배치됩니다.
 - *발신자와 수신자가 동일한 테넌트에 있는 경우* Teams에서 시작된 수신 VOIP 호출은 Teams에 연결됩니다.
 - 들어오는 페더레이션된 VOIP(클라이언트의 시작에 관계 없이) 및 PSTN 호출은 항상 받는 사람의 비즈니스용 Skype 클라이언트에 연결됩니다.
 
들어오는 VOIP 및 PSTN 호출이 항상 사용자의 Teams 클라이언트에 배치되도록 하려면 사용자의 공존 모드를 TeamsOnly로 업데이트합니다(즉, TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당).  공존 모드 및 TeamsUpgradePolicy에 대한 자세한 내용은 [Teams를 사용하는 조직의 마이그레이션 및 상호 운용성 지침을 참조하세요비즈니스용 Skype](./migration-interop-guidance-for-teams-with-skype.md)

**노트**
 - 비즈니스용 Skype IP 휴대폰은 사용자가 TeamsOnly 모드인 경우에도 전화를 받습니다.  
 - 비즈니스용 Skype Online에서 사용하기 위해 전화 시스템 및 통화 플랜 라이선스로 프로비전된 사용자(예: OnlineVoiceRoutingPolicy 값이 할당됨)는 Teams에서 통화 탭을 사용하도록 설정하고 관리자가 관리 조치를 취하지 않고 Teams에서 아웃바운드 PSTN 통화를 할 수 있습니다.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Teams에서 들어오는 모든 VOIP 및 PSTN 호출을 받도록 사용자를 구성하는 방법
사용자가 Teams에서 들어오는 모든 VOIP 및 PSTN 호출을 받도록 하려면 Microsoft Teams 관리 센터에서 사용자의 공존 모드를 TeamsOnly로 설정하거나 비즈니스용 Skype 원격 Windows PowerShell 세션을 사용하여 다음과 같이 TeamsUpgradePolicy를 업데이트합니다.

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>참고 항목
[통화 플랜 설정](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Teams를 사용하는 조직을 위한 마이그레이션 및 상호 운용성 지침과 비즈니스용 Skype](./migration-interop-guidance-for-teams-with-skype.md)

[통화 플랜을 사용하는 전화 시스템](calling-plan-landing-page.md)

[powerShell cmdlet 참조 비즈니스용 Skype](/powershell/module/skype)
