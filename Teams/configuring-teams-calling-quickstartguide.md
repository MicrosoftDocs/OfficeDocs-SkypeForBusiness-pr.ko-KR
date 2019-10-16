---
title: 빠른 시작 가이드-Microsoft 팀에서 전화 요금제 구성
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Microsoft 팀에서 통화 계획을 구성 하기 위한 빠른 시작 가이드입니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87670ea398150e4895f2d87ccc48f60aba2d1377
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37517060"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>빠른 시작 가이드: Microsoft 팀에서 통화 계획 구성
==============================================================

이 가이드는 팀에서 통화 계획을 탐색할 수 있도록 사용자 집합을 준비 하 고 실행 하는 데 도움을 줍니다.

12 월 12 일, 2017, 팀의 통화 계획 공지 사항: [지능형 통신은 팀에서 호출 하는 다음 단계를 수행 합니다](https://aka.ms/ipyqus) .

> [!NOTE]
> 이 빠른 시작 가이드를 사용 하 여 통화 요금제와 [Fasttrack](https://aka.ms/cloudvoice) 을 함께 사용 하 여 성공적인 출시를 계획 하 고 구동 하는 방법으로 [전화 시스템](calling-plan-landing-page.md) 을 읽을 것을 권장 합니다.

통화 계획 추가-비즈니스용 Skype에서 제공 하는 Office 365 기능-이제 팀을 사용 하 여 PSTN (공공 교환 전화 네트워크)을 통해 지역 및 휴대폰으로 전화를 걸고 받을 수 있습니다.

![팀의 연락처 페이지를 보여주는 스크린샷](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>팀에서 **통화** 탭을 사용 하기 위한 필수 구성 요소
팀에서 **통화** 탭을 사용 하도록 설정 하려면 팀에서 1:1 통화를 사용 하도록 설정 하 고 1:1 팀 호출을 지 원하는 팀 클라이언트를 사용 해야 합니다. 팀에서 1:1 통화를 관리 하는 방법에 대 한 자세한 내용은 [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)를 참조 하세요. 전화를 지 원하는 클라이언트에 [대 한 자세한 내용은 Microsoft 팀에 대 한 제한 사항 및 사양을](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)참조 하세요.

> [!NOTE]
> 현재, 사용자가 PSTN 통화를 사용 하도록 설정 하지 않은 경우에는 통화 탭에서 음성 메일을 사용할 수 없습니다. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>팀에서 **다이얼 패드** 를 사용 하기 위한 필수 조건
팀에서 **다이얼 패드** 탭을 사용 하도록 설정 하 고 사용자가 PSTN 통화를 설정 하 고 수신할 수 있도록 하려면 전화 시스템 및 통화 요금제에 대 한 사용자를 프로 비전 해야 합니다. 통화 계획을 설정 하는 방법에 대 한 자세한 내용은 [통화 계획 설정을](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)참조 하세요.

> [!NOTE]
> 또한 직접 라우팅을 사용 하 여 사용자가 PSTN 전화를 걸고 받을 수 있습니다. 직접 라우팅을 설정 하는 방법에 대 한 자세한 내용은 [직접 라우팅 구성을](https://docs.microsoft.com/microsoftteams/direct-routing-configure)참조 하세요.

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>TeamsUpgradePolicy를 사용 하 여 전화를 거는 위치 제어
팀 또는 비즈니스용 Skype에서 걸려오는 통화 (및 채팅)가 어디에 있는지 제어 하기 위해 관리자는 [Microsoft 팀 관리 센터](https://aka.ms/teamsadmincenter) 를 사용 하거나 [비즈니스용 Skype](https://docs.microsoft.com/powershell/module/skype) 에서 원격 Windows PowerShell 세션을 사용 하 여 TeamsUpgradePolicy를 사용 합니다. cmdlet.


TeamsUpgradePolicy의 기본 구성은 팀을 배포 하는 동안 기존 비즈니스 워크플로가 중단 되지 않도록 설계 된 아일랜드 모드입니다. 기본적으로 사용자에 대 한 VoIP, PSTN 및 페더레이션된 통화는 팀에 대 한 인바운드 호출을 사용 하도록 정책을 업데이트할 때까지 계속 해 서 비즈니스용 Skype로 라우팅됩니다.  받는 사람이 아일랜드 모드일 때:

 - 비즈니스용 Skype에서 시작 된 수신 VOIP 통화는 항상 받는 사람의 비즈니스용 Skype 클라이언트에 배치 됩니다.
 - *발신자와 수신자가 동일한 테 넌 트에 있는 경우*팀에서 생성 된 수신 VOIP 통화
 - 들어오는 페더레이션 VOIP (클라이언트의 연결 여부에 관계 없음) 및 PSTN 호출은 항상 받는 사람의 Skype for Business 클라이언트에 연결 됩니다.
 
들어오는 VOIP 및 PSTN 통화가 사용자의 팀 클라이언트에 항상 존재 하도록 하려면 사용자의 공존 모드를 팀 전용으로 업데이트 하세요 (즉, "UpgradeToTeams" 인스턴스를 할당 하는 것을 의미 함).  공존 모드 및 TeamsUpgradePolicy에 대 한 자세한 내용은 [비즈니스용 Skype로 함께 팀을 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) 을 참조 하세요.

**상속자**
 - 비즈니스용 Skype IP 전화는 사용자가 TeamsOnly 모드에 있더라도 전화를 받습니다.  
 - Skype for Business Online에서 사용할 수 있도록 전화 시스템 및 통화 계획 라이선스로 프로 비전 된 사용자 (예: OnlineVoiceRoutingPolicy 값이 지정 된 경우)는 팀에서 통화 탭을 사용 하도록 설정 하 고 아웃 바운드 PSTN 통화를 관리자가 없는 팀은 관리 작업을 수행 해야 합니다.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>팀에서 모든 수신 VOIP 및 PSTN 통화를 받도록 사용자를 구성 하는 방법
사용자가 팀에서 모든 수신 VOIP 및 PSTN 통화를 받을 수 있도록 하려면 사용자의 공존 모드를 Microsoft 팀 관리 센터 에서만 TeamsOnly로 설정 하거나 비즈니스용 Skype 원격 Windows PowerShell 세션을 사용 하 여 다음과 같이 TeamsUpgradePolicy를 업데이트 합니다.

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>참고 항목
[통화 요금제 설정](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[통화 요금제가 포함 되어 있는 전화 시스템](calling-plan-landing-page.md)

[비즈니스용 Skype PowerShell cmdlet 참조](https://docs.microsoft.com/powershell/module/skype)

