---
title: 원격 Teams 서비스와 함께 사용
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 원격 데스크톱 서비스와 함께 Microsoft Teams 방법을 자세히 알아보습니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7090aac3c5e7ff724a079e7f9d9ffe9d712cd447
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119097"
---
# <a name="teams-in-remote-desktop-services"></a>Teams 데스크톱 서비스에서 사용

이 문서에서는 원격 데스크톱 서비스(RDS) 환경에서 Microsoft Teams 사용에 대한 요구 사항 및 제한 사항을 설명합니다.

## <a name="what-is-rds"></a>RDS란?

원격 데스크톱 서비스(RDS)는 모든 최종 고객 요구에 대한 가상화 솔루션을 구축하기 위한 선택의 플랫폼입니다. RDS를 사용하면 개별 가상화된 애플리케이션을 제공하고, 안전한 모바일 및 원격 데스크톱 액세스를 제공하고, 최종 사용자에게 클라우드에서 애플리케이션 및 데스크톱을 실행할 수 있는 기능을 제공합니다.

RDS는 배포 유연성, 비용 효율성 및 확장성을 제공합니다. RDS는 다양한 배포 옵션을 통해 전달됩니다. Windows Server 2016 배포를 위한 Windows Server 2016, 클라우드 배포를 위한 Microsoft Azure 및 강력한 파트너 솔루션 배열을 비롯한 다양한 배포 옵션을 통해 제공됩니다.
환경 및 기본 설정에 따라 세션 기반 가상화에 대한 RDS 솔루션을 VDI(가상 데스크톱 인프라)로 설정할 수 있습니다.

현재 원격 데스크톱 Teams 환경에서 공동 작업 및 채팅 기능을 지원하여 사용할 수 있습니다. 최적의 사용자 환경을 보장하기 위해 이 문서의 지침을 따르하세요.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams 공동 작업을 통해 RDS에서 작업

조직에서 채팅 및 공동 작업 기능만 사용하려는 Teams 사용자 수준 정책을 설정하여 통화 및 모임 기능을 Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>통화 및 모임 기능을 해제하기 위한 정책 설정

관리자 센터 또는 PowerShell을 사용하여 정책을 Microsoft Teams 수 있습니다. 정책 변경이 전파하는 데 몇 시간(몇 시간)이 걸릴 수 있습니다. 특정 계정에 대한 변경 내용이 즉시 표시되지 않는 경우 몇 시간 후에 다시 시도하세요.

[**호출 경찰**](teams-calling-policy.md): Teams 모든 호출 기능이 꺼져 있는 기본 제공 DisallowCalling 호출 정책이 포함되어 있습니다. 가상화된 환경에서 사용자를 사용하는 조직의 모든 Teams DisallowCalling 정책을 할당합니다.

[**모임 정책**](meeting-policies-in-teams.md): Teams 모든 모임 기능을 해제하는 기본 제공 AllOff 모임 정책이 포함됩니다. 가상화된 환경에서 모든 사용자를 사용하는 Teams AllOff 정책을 할당합니다.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>관리 센터를 사용하여 Microsoft Teams 할당

DisallowCalling 호출 정책 및 AllOff 모임 정책을 사용자에게 할당하는 경우:

1. 관리 센터의 왼쪽 Microsoft Teams 사용자로 **이동하세요.**
2. 사용자 이름의 왼쪽을 선택하여 사용자를 선택한 다음 설정 편집 **을 선택합니다.**
3. 다음 단계를 수행합니다.

    a.  호출 **정책에서** **DisallowCalling 을 선택합니다.**

    b.  모임 **정책에서** **AllOff 를 선택합니다.**

4. 적용 **을 선택합니다.**

한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
2. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 &#x2713;(확인 표시)를 선택합니다.
3. 설정 **편집을 선택하고** 원하는 내용을 변경한 다음 적용을 **선택합니다.**

또는 다음 단계를 수행하면 됩니다.

1. 관리 센터의 왼쪽 Microsoft Teams 할당할 정책으로 이동하세요. 예를 들면 다음과 같습니다.

    - 음성 통화  >  **정책으로 이동한** **다음, DisallowCalling 을 선택합니다.**
    - 모임 모임 **정책으로**  >  이동한 다음 **AllOff 를 선택합니다.**

2. **사용자 관리** 를 선택합니다.
3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요. 추가할 각 사용자에 대해 이 단계를 반복합니다.
4. 사용자 추가가 완료되면 저장 을 **선택합니다.**

#### <a name="assign-policies-using-powershell"></a>PowerShell을 사용하여 정책 할당

다음 예제에서는 [Grant-CsTeamsCallingPolicy를](/powershell/module/skype/grant-csteamscallingpolicy) 사용하여 사용자에게 DisallowCalling 호출 정책을 할당하는 방법을 보여줍니다.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

PowerShell을 사용하여 통화 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)를 참조합니다.

다음 예제에서는 [Grant-CsTeamsMeetingPolicy를](/powershell/module/skype/grant-csteamsmeetingpolicy) 사용하여 AllOff 모임 정책을 사용자에게 할당하는 방법을 보여줍니다.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

PowerShell을 사용하여 모임 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조합니다.