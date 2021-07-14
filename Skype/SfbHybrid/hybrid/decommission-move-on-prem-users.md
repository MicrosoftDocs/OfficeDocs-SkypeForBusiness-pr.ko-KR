---
title: 클라우드로 사용자 이동
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
description: 사용자 이동을 해제하기 전에 비즈니스용 Skype 환경을 해제합니다.
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420813"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>사내 환경을 해제하기 전에 필요한 사용자 이동

이 문서에서는 필요한 사용자를 Microsoft 클라우드로 이동한 후, 해당 환경을 해제하기 전에 microsoft 클라우드로 이동하는 비즈니스용 Skype 설명되어 있습니다. 이 단계는 다음 단계 중 1단계로, 프레미스 환경을 해제합니다.

- **1단계. 필요한 모든 사용자를 온라인에서 프레미스로 이동** (이 문서)

- 2단계. [하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)

- 3단계. [하이브리드 응용 프로그램 끝점을](decommission-move-on-prem-endpoints.md)온라인 프레미스에서 온라인으로 마이그레이션합니다. 이 단계를 완료할 때까지 위의 2단계를 수행하는 시간 사이에 기존 하이브리드 응용 프로그램 끝점을 검색할 수 없습니다. 동일한 유지 관리 창에서 2단계와 3단계를 모두 수행하기로 계획해야 합니다.

- 4단계. [배포 에서 프레미스 비즈니스용 Skype 제거합니다.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>필요한 모든 사용자를 사내에서 클라우드로 이동

마이그레이션을 완료한 후에도 계속 사용할 모든 사용자는 먼저 사내에서 클라우드로 이동해야 합니다. 사용자는 사내 관리 도구를 사용하여 사용자를 이동합니다. 자세한 내용은 [Move users between on-premises and cloud을 참조합니다.](move-users-between-on-premises-and-cloud.md)

모든 계정을 사용하는 사용자가 비즈니스용 Skype 서버 계정을 사용할 수 Teams 이러한 사용자는 모든 기능을 사용할 수 Teams. 이러한 사용자는 여전히 온라인 또는 비즈니스용 Skype 사용하여 다른 사용자와 상호 비즈니스용 Skype 수 없습니다. 이러한 사용자는 자신의 클라이언트에서 PSTN 통화를 받을 Teams 없습니다. 따라서 이러한 사용자를 온라인으로 이동해야 합니다. 또한 이 단계에서는 모든 연락처 또는 모임이 비즈니스용 Skype 서버 마이그레이션되도록 Teams.

사내 배포에 남은 사용자가 있는 경우 PowerShell 창에서 다음 cmdlet을 비즈니스용 Skype 서버 실행합니다.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

사용자가 반환되는 경우 출력을 검토하여 계정을 클라우드로 이동해야 하는지 여부를 확인한 다음 해당 사용자에 대해 여기에 있는 단계를 [따릅니다.](move-users-between-on-premises-and-cloud.md) 더 이상 필요하지 않습니다. 사용자 계정의 경우 PowerShell cmdlet에 비즈니스용 Skype 서버 실행합니다.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> 이 Disable-CsUser 실행하면 필터 조건을 비즈니스용 Skype 모든 사용자에 대한 모든 비즈니스용 Skype 특성이 제거됩니다. 계속하기 전에 이러한 계정이 더 이상 필요하지 않습니다.


이제 하이브리드 구성을 [사용하지 않도록 설정할 준비가 완료되었습니다.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>참고 항목

- [온-프레미스 비즈니스용 Skype 환경 해제](decommission-on-prem-overview.md)

- [하이브리드 구성을 사용하지 않도록 설정](cloud-consolidation-disabling-hybrid.md)

- [하이브리드 응용 프로그램 끝점을 사내에서 온라인으로 이동](decommission-move-on-prem-endpoints.md)

- [온-프레미스 비즈니스용 Skype 배포 제거](decommission-remove-on-prem.md)




