---
title: 원격 데스크톱 서비스에서 Teams 사용
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 원격 데스크톱 서비스에서 Microsoft Teams를 사용하는 방법을 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e18aa0ad95033550d0ef2f7c6049e700d917798
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606097"
---
# <a name="teams-in-remote-desktop-services"></a>원격 데스크톱 서비스의 팀

이 문서에서는 RDS(원격 데스크톱 서비스) 환경에서 Microsoft Teams를 사용하기 위한 요구 사항 및 제한 사항에 대해 설명합니다.

## <a name="what-is-rds"></a>RDS란?

RDS(원격 데스크톱 서비스)는 모든 최종 고객 요구 사항에 대한 가상화 솔루션을 빌드하기 위해 선택하는 플랫폼입니다. RDS를 사용하면 개별 가상화된 애플리케이션을 제공하고, 안전한 모바일 및 원격 데스크톱 액세스를 제공하고, 최종 사용자에게 클라우드에서 애플리케이션 및 데스크톱을 실행할 수 있는 기능을 제공할 수 있습니다.

RDS는 배포 유연성, 비용 효율성 및 확장성을 제공합니다. RDS는 온-프레미스 배포에 대한 Windows Server 2016, 클라우드 배포용 Microsoft Azure 및 강력한 파트너 솔루션 배열을 포함하여 다양한 배포 옵션을 통해 제공됩니다.
환경 및 기본 설정에 따라 세션 기반 가상화를 위한 RDS 솔루션을 VDI(가상 데스크톱 인프라)로 설정할 수 있습니다.

현재 원격 데스크톱 서비스 환경의 Teams는 공동 작업 및 채팅 기능을 지원하여 사용할 수 있습니다. 최적의 사용자 환경을 보장하려면 이 문서의 지침을 따르세요.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>채팅 및 공동 작업을 사용하는 RDS의 Teams

조직에서 Teams에서 채팅 및 공동 작업 기능만 사용하려는 경우 Teams에서 통화 및 모임 기능을 해제하도록 사용자 수준 정책을 설정할 수 있습니다.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>통화 및 모임 기능을 해제하는 정책 설정

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 정책을 설정할 수 있습니다. 정책 변경 내용이 전파되려면 몇 시간 정도 걸릴 수 있습니다. 지정된 계정에 대한 변경 내용이 즉시 표시되지 않으면 몇 시간 후에 다시 시도하세요.

[**통화 정책**](teams-calling-policy.md): Teams에는 모든 통화 기능이 꺼져 있는 기본 제공 DisallowCalling 통화 정책이 포함되어 있습니다. 가상화된 환경에서 Teams를 사용하는 조직의 모든 사용자에게 DisallowCalling 정책을 할당합니다.

[**모임 정책**](meeting-policies-overview.md): Teams에는 모든 모임 기능이 꺼져 있는 기본 제공 AllOff 모임 정책이 포함되어 있습니다. 가상화된 환경에서 Teams를 사용하는 조직의 모든 사용자에게 AllOff 정책을 할당합니다.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 정책 할당

사용자에게 DisallowCalling 통화 정책 및 AllOff 모임 정책을 할당하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동합니다.
2. 사용자 이름 왼쪽을 선택하여 사용자를 선택한 다음 **설정 편집** 을 선택합니다.
3. 다음 단계를 수행합니다.

    a.  **통화 정책** 에서 **DisallowCalling을** 선택합니다.

    b.  **모임 정책** 에서 **AllOff** 를 선택합니다.

4. **적용** 을 선택합니다.

한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
2. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 테이블 맨 위에 있는 &#x2713;(확인 표시)를 선택합니다.
3. **설정 편집** 을 선택하고 원하는 대로 변경한 다음 **적용** 을 선택합니다.

또는 다음 단계를 수행할 수도 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 할당하려는 정책으로 이동합니다. 예를 들면 다음과 같습니다.

    - **음성** > **통화 정책** 으로 이동한 다음 **DisallowCalling을** 선택합니다.
    - 모임 **모임 정책****으로** >  이동한 다음 **AllOff** 를 선택합니다.

2. **사용자 관리** 를 선택합니다.
3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요. 추가할 각 사용자에 대해 이 단계를 반복합니다.
4. 사용자 추가가 완료되면 **저장** 을 선택합니다.

#### <a name="assign-policies-using-powershell"></a>PowerShell을 사용하여 정책 할당

다음 예제에서는 [Grant-CsTeamsCallingPolicy를](/powershell/module/skype/grant-csteamscallingpolicy) 사용하여 DisallowCalling 호출 정책을 사용자에게 할당하는 방법을 보여 줍니다.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

PowerShell을 사용하여 통화 정책을 관리하는 방법에 대한 자세한 내용은 [Set-CsTeamsCallingPolicy를 참조하세요](/powershell/module/skype/set-csteamscallingpolicy).

다음 예제에서는 [Grant-CsTeamsMeetingPolicy를](/powershell/module/skype/grant-csteamsmeetingpolicy) 사용하여 사용자에게 AllOff 모임 정책을 할당하는 방법을 보여 줍니다.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

PowerShell을 사용하여 모임 정책을 관리하는 방법에 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy를 참조하세요](/powershell/module/skype/set-csteamsmeetingpolicy).