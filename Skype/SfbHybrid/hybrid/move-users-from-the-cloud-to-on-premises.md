---
title: 클라우드에서 사내로 사용자 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 사용자를 프레미스에서 Teams 이동하는 방법을 배워야 합니다.
ms.openlocfilehash: 782fd16fb4ad5c8567600ffcf781410a4532c213
ms.sourcegitcommit: d0fb9035903d9e1ce184417250913db10608b1a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2021
ms.locfileid: "53660716"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>클라우드에서 사내로 사용자 이동 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

필요한 경우 이전에 마이그레이션한 사용자를 사내에서 다시 Teams 수 있습니다. TeamsOnly 모드에서 다시 비즈니스용 Skype 서버 배포로 사용자를 이동하기 위해 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용합니다. 두 cmdlet은 모두 사내 도구입니다. 사용자를 다시 사내 배포로 이동할 때 사용자를 이동할 풀을 결정해야 합니다.

> [!Important]
> 사용자가 이전에 TeamsOnly 모드에 있으며 CU8이 있는 비즈니스용 Skype 서버 2015보다 이전 버전을 사용하는 경우 해당 사용자에 대한 TeamsUpgradePolicy의 TeamsOnly 모드 할당도 제거해야 합니다. On-premises users must not have mode= TeamsOnly.  후속 버전의 비즈니스용 Skype 서버 이 할당을 자동으로 제거합니다. 자세한 내용은 [Grant-CsTeamsUpgradePolicy를 참조합니다.](/powershell/module/skype/grant-csteamsupgradepolicy)

## <a name="prerequisites"></a>필수 구성 요소

- 조직은 Azure AD 커넥트 구성에 설명된 바와 같이 사용자의 모든 관련 특성을 올바르게 구성하고 동기화해야 [커넥트.](configure-azure-ad-connect.md)
- 다시 온라인에서 다시 사내로 이동하는 사용자는 이미온-프레미스 Active Directory에 있어야 합니다.
- 비즈니스용 Skype 하이브리드 구성에 설명된 바와 같이 하이브리드를 [구성해야 비즈니스용 Skype 합니다.](configure-federation-with-skype-for-business-online.md)

## <a name="moving-users-back-to-on-premises"></a>사용자를 다시온-프레미스로 이동

사용자를 클라우드에서 다시 On-premises로 이동한 후:

- 사용자는 기능을 위해 비즈니스용 Skype 서버 사용자 배포와 상호 작용합니다. 
- 모든 연락처가 Teams 마이그레이션되지 비즈니스용 Skype 서버. 두 연락처 집합이 병합된 다음 다시 사내로 마이그레이션됩니다.  또한 기존 연락처는 Teams 남아 Teams.
- 또한 사용자가 Teams 사용하는 경우 사용자와 상호 비즈니스용 Skype 기능을 사용할 수 없으며, 페더러가 있는 조직의 사용자와도 통신할 수 없습니다.

### <a name="move-users-with-move-csuser"></a>사용자 이동을 Move-CsUser

Move-CsUser 관리 셸 PowerShell 창의 비즈니스용 Skype 사용할 수 있습니다. 필수 관리 자격 증명 에 설명된 바와 같이 클라우드 서비스 조직(Microsoft 365)뿐만 아니라 사내 환경 모두에 충분한 권한이 [있어야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) 두 환경에서 모두 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 비즈니스용 Skype 서버 자격 증명을 사용하여 사내 비즈니스용 Skype 서버 관리 셸 창을 시작하고 이 매개 변수를 사용하여 필요한 관리 역할로 Microsoft 365 계정에 대한 자격 증명을 지정할 수 `-Credential` 있습니다.

Move-CsUser를 사용하여 사용자를 사내로 이동하는 경우:

- Identity 매개 변수를 사용하여 이동할 사용자를 지정합니다.
- 사용자를 호스팅할 원하는 온-프레미스 풀의 정식 도메인 이름으로 -Target 매개 변수를 지정합니다.
- 사내 및 클라우드 서비스(Microsoft 365)에서 충분한 사용 권한이 있는 계정이 하나도 없는 경우 -credential 매개 변수를 사용하여 Microsoft 365.
- Microsoft 365 권한이 있는 계정이 "on.microsoft.com"로 끝나지 않는 경우 필수 관리 자격 증명에 설명된 올바른 값으로 -HostedMigrationOverrideUrl 매개 변수를 지정해야 [합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

다음 cmdlet 시퀀스를 사용하여 사용자를 비즈니스용 Skype 서버 수 있으며 Microsoft 365 자격 증명이 별도의 계정으로 제공된 것으로 가정하고 Get-Credential 프롬프트에 대한 입력으로 제공됩니다.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>제어판을 사용하여 비즈니스용 Skype 서버 이동

1. 제어판 비즈니스용 Skype 서버 를 니다.
2. 왼쪽 탐색에서 사용자 를 **선택 합니다.**
3. **Find를** 사용하여 다시 사내로 이동할 사용자를 찾습니다.
4. 사용자를 선택하고 목록 위의 작업  드롭다운에서 선택한 사용자를 프레미스로 **이동을 선택합니다.**
5. 마법사에서 사용자를 호스팅할 사용자 풀을 선택하고 다음 을 **클릭합니다.**
6. 메시지가 표시될 경우 .Microsoft 365 계정으로 로그인하여 onmicrosoft.com 권한이 있습니다.
7. **다음을** 클릭하고 **다음을** 한 번 더 클릭하여 사용자를 이동합니다.
8. 성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.

### <a name="removing-teamsonly-mode"></a>TeamsOnly 모드 제거

CU8과 함께 비즈니스용 Skype 2015 이전 버전을 사용 중이고 사용자가 TeamsOnly 모드에서 다시 On-premises로 이동되는 경우 사용자를 이동하기 전에 UpgradeToTeams 인스턴스를 제거해야 `TeamsUpgradePolicy` 합니다. 다른 모드를 사용하여 정책을 명시적으로 부여하거나 해당 사용자의 기존 정책 할당을 제거하여 테넌트의 글로벌 정책이 UpgradeToTeams가 아닌 경우 글로벌 정책을 사용할 수 있습니다.

사용자의 TeamsUpgradePolicy 할당을 제거하려면 PowerShell 창의 Teams 실행합니다.

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

또는 mode=TeamsOnly가 없는 TeamsUpgradePolicy의 다른 인스턴스를 할당하기 위해 cmdlet에서 원하는 인스턴스의 이름을 PolicyName 매개 변수 값으로 지정할 수 있습니다. TeamsUpgradePolicy의 사용 가능한 인스턴스 목록을 표시하기 위해 Get-CsTeamsUpgradePolicy를 실행합니다.


## <a name="see-also"></a>참고 항목

[Move-CsUser](/powershell/module/skype/move-csuser)