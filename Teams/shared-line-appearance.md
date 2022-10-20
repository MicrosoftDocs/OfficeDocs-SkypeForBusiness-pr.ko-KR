---
title: Microsoft Teams의 공유 줄 모양
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Microsoft Teams의 공유 줄 모양 기능에 대해 알아봅니다.
ms.openlocfilehash: 7e3259e948e5a3443d5959eef693416ca3d754ca
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614100"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams의 공유 줄 모양

공유 줄 모양을 사용하면 사용자가 대리자를 선택하여 대신 전화를 받거나 처리할 수 있습니다. 이 기능은 사용자에게 정기적으로 사용자의 호출을 처리하는 관리 도우미가 있는 경우에 유용합니다. 공유 회선 모양 컨텍스트에서 관리자는 대리인에게 대리인을 대신하여 전화를 걸거나 받을 수 있는 권한을 부여하는 사람입니다. 대리자는 위임자를 대신하여 전화를 걸거나 받을 수 있습니다.

> [!IMPORTANT]
> 이 기능은 Teams 전용 배포 모드에서만 사용할 수 있습니다. Teams 배포 모드에 대한 자세한 내용은 [Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md)를 참조하세요.

## <a name="license-required"></a>라이선스 필요

관리자와 대리인 모두 PSTN 연결(통화 플랜, 운영자 연결 또는 직접 라우팅)이 있는 전화 시스템 라이선스가 있어야 합니다. 공유 회선 환경은 위임의 일부이며 전화 시스템에 포함됩니다. 라이선스에 대한 자세한 내용은 [Microsoft Teams 서비스 설명을](/office365/servicedescriptions/teams-service-description) 참조하세요.

## <a name="shared-line-appearance-feature-availability"></a>공유 줄 모양 기능 가용성

공유 줄 모양은 현재 다음 앱 및 디바이스에서 지원됩니다.

| 기능 | Teams 데스크톱 | Teams Mac 앱 | Teams 웹앱(Edge) |Teams 모바일 iOS/Android 앱 | Teams IP 전화 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 위임 설정 | 예 | 예 | 예 | 아니요 | 예 |
| 다른 사용자 대신 통화 받기 | 예 | 예 | 예 | 예 | 예 |
| 다른 전화번호를 대신하여 전화번호로 전화 | 예 | 예 | 예 | 예 | 예 |
| 다른 사용자를 대신하여 Teams 사용자 호출 | 예 | 예 | 예 | 예 | 예 |
| 공유 줄의 대리자 보기 보기 보기 | 예 | 예 | 예 | 아니요 | 예 |
| 관리자의 통화 활동의 대리자 보기 보기 보기 | 예 | 예 | 예 | 아니요 | 예 |
| 대리자의 관리자 보기 보기 | 예 | 예 | 예 | 아니요 | 예 |
| 대리인 또는 관리자는 보류하거나 다시 시작할 수 있습니다. | 예 | 예 | 예 | 아니요 | 예 |

## <a name="limitations"></a>제한 사항

관리자는 최대 25명의 대리인을 추가할 수 있으며, 대리인은 최대 25명의 관리자를 가질 수 있습니다. 테넌트에서 만들 수 있는 위임 관계의 수에는 제한이 없습니다. 
 
위임자와 대리자가 동일한 지리적 위치에 있지 않은 경우 PSTN 공급자는 위임된 호출에 대해 다른 지리적 위치에서 호출자 ID를 표시하도록 허용해야 합니다. 

순환 위임 구성은 허용되지 않습니다. 위임된 사용자에게도 위임이 있는 경우 초기 위임이 아닌 위임만 볼 수 있습니다.

## <a name="enable-delegation-and-shared-line-appearance"></a>위임 및 공유 줄 모양 사용

**TeamsCallingPolicy AllowDelegation** 설정을 사용하여 위임을 사용하도록 설정합니다. Teams 관리 센터 또는 Teamms PowerShell을 사용할 수 있습니다. 

사용하도록 설정하면 최종 사용자가 Teams에서 직접 위임 관계를 구성할 수 있습니다. 

> [!IMPORTANT]
> 사용자에 대한 위임을 해제하는 경우 잘못된 통화 라우팅을 방지하기 위해 Teams 관리 센터에서 해당 사용자에 대한 위임 관계도 정리해야 합니다.

## <a name="use-teams-admin-center"></a>Teams 관리 센터 사용

Teams 관리 센터를 사용하여 위임 및 공유 회선 모양을 구성하려면 [사용자에 대한 통화 설정 구성을 참조하세요](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>PowerShell 사용

Teams PowerShell을 사용하여 위임 및 공유 줄 모양을 구성하려면 다음 cmdlet을 사용합니다.

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)

- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)

- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)

### <a name="examples"></a>예제

다음 예제에서 user2@contoso.com user1을 대신하여 전화를 걸고 받을 수 있는 권한이 있는 user1@contoso.com 대리자로 추가되고 다른 대리자의 설정을 변경합니다.

```powershell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

다음 예제에서는 대리자 user2@contoso.com user1을 대신하여 더 이상 호출할 수 없습니다.

```powershell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

다음 예제에서는 user2@contoso.com user1@contoso.com 대리자로 제거됩니다.

```powershell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```
 
## <a name="more-information"></a>추가 정보

[대리인과 전화 회선 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

[Teams 통화 정책](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
