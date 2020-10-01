---
title: 비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c359b39707b57a653f35e75497672d306209ccd
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328217"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>비즈니스용 Skype Server 온-프레미스를 사용 하는 조직에 대 한 업그레이드 고려 사항 &mdash; IT 관리자 용

이 문서에서는 비즈니스용 Skype Server 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항에 대해 설명 합니다. 이 문서는 IT 관리자의 업그레이드 개념 및 구현을 설명 하는 여러 가지 항목 중 네 번째입니다.  

- [개요](upgrade-to-teams-on-prem-overview.md)
- [업그레이드 방법](upgrade-to-teams-on-prem-upgrade-methods.md)
- [업그레이드 관리 도구](upgrade-to-teams-on-prem-tools.md)
- **비즈니스용 Skype 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항** (이 문서)
- [업그레이드 구현](upgrade-to-teams-on-prem-implement.md)
- [PSTN (공개 통신 네트워크) 고려 사항](upgrade-to-teams-on-prem-pstn-considerations.md)

또한 다음 문서에서는 중요 한 업그레이드 개념 및 공존 동작에 대해 설명 합니다.

- [팀과 비즈니스용 Skype의 공존](upgrade-to-teams-on-prem-coexistence.md)
- [공존 모드-참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>비즈니스용 Skype Server 온-프레미스를 사용 하는 조직에 대 한 고려 사항

- 비즈니스용 Skype 하이브리드을 설정 하는 것은 팀 전용 모드로 마이그레이션하는 필수 사항입니다. 통합 없이 아일랜드 모드에서 팀을 사용할 수 있지만, 사용자가 비즈니스용 Skype 온-프레미스에서 비즈니스용 Skype Online ( [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)사용)으로 이동할 때 까지는 TeamsOnly 모드 전환 기능을 설정할 수 없습니다. 자세한 내용은 [하이브리드 연결 구성을](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)참조 하세요.

- 조직에 비즈니스용 Skype 서버가 있고 하이브리드 연결을 구성 하지 않은 상태에서 팀을 사용 하 여 팀의 기능을 관리 하려면 onmicrosoft.com 도메인이 있는 관리자 계정을 사용 해야 합니다. 

- 비즈니스용 Skype 계정이 있는 (즉, 이동-CsUser를 사용 하 여 클라우드로 아직 이동 하지 않은) 팀 사용자는 비즈니스용 Skype 사용자와 상호 운용할 수 없으며 외부 사용자와 페더레이션 할 수도 없습니다. 이 기능은 사용자를 클라우드로 이동한 후에만 사용할 수 있습니다 (예를 들어, 아일랜드 모드에서 또는 Team사용자만 해당). 

- 비즈니스용 Skype 계정을 보유 하 고 있는 사용자가 있는 경우 테 넌 트 수준에서 TeamsOnly 모드를 할당할 수 없습니다. 먼저 온-프레미스 비즈니스용 Skype 계정으로 모든 사용자를 클라우드로 이동한 다음 하이브리드을 사용 `Move-CsUser` [하지 않도록 설정 하 여 클라우드로 마이그레이션을 완료](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)해야 합니다.  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` Office 365 이외의 위치를 가리키는 lyncdiscover 레코드가 검색 되는 경우 테 넌 트 수준에서 작동 하지 않습니다.

- 올바른 비즈니스용 Skype 특성을 사용 하 여 사용자가 Azure AD로 적절 하 게 동기화 되었는지 확인 해야 합니다. 이러한 특성은 모두 "msRTCSIP"이 포함 된 접두사입니다. 사용자가 Azure AD에 올바르게 동기화 되지 않은 경우 팀의 관리 도구에서 이러한 사용자를 관리할 수 없게 됩니다. 예를 들어 이러한 특성을 적절 하 게 동기화 하지 않는 한 온-프레미스 사용자에 게 팀 정책을 할당할 수 없게 됩니다. 자세한 내용은 [팀 및 비즈니스용 Skype에 대 한 AZURE AD Connect 구성을](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)참조 하세요.

- 하이브리드 조직에서 새 팀 또는 비즈니스용 Skype Online 사용자를 만들려면 *먼저 비즈니스용 Skype Server 온-프레미스에서 사용자를 사용 하도록 설정*하 고 사용자를 이동-csuser를 사용 하 여 온-프레미스에서 클라우드로 이동 합니다.  온-프레미스에서 사용자를 만들면 남아 있는 나머지 온-프레미스 비즈니스용 Skype 사용자가 새로 만든 사용자에 게 경로를 지정할 수 있게 됩니다. 모든 사용자가 온라인으로 이동한 후에는 온-프레미스에서 사용자를 활성화 하는 데 더 이상 필요 하지 않습니다.

- 사용자가 온-프레미스에서 클라우드로 이동 하는 경우, 해당 사용자가 구성한 모임은 비즈니스용 Skype Online 또는 팀으로 마이그레이션됩니다--MoveToTeams 스위치가 지정 되었는지 여부에 따라 달라 집니다.

- 온-프레미스 사용자 용 Skype for Business 클라이언트에 알림을 표시 하려는 경우 온-프레미스 도구 모음에서 TeamsUpgradePolicy를 사용 해야 합니다. NotifySfbUsers 매개 변수만 온-프레미스 사용자와 관련이 있습니다.  온-프레미스 사용자는 TeamsUpgradePolicy의 온라인 인스턴스에서 자신의 모드를 받습니다. [허용-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)의 메모를 참조 하세요. 

>[!NOTE]
> 2 월 3 일 이후에 만들어진 모든 새 테 넌 트는 조직에 비즈니스용 Skype 서버에 대 한 온-프레미스 배포가 이미 있는 경우 2019를 제외 하 고는 TeamsOnly 넌 트로만 생성 됩니다. Microsoft는 DNS 레코드를 사용 하 여 온-프레미스 비즈니스용 Skype 서버 조직을 식별 합니다. 조직에서 공용 DNS 항목이 없는 온-프레미스 비즈니스용 Skype 서버를 사용 하는 경우 Microsoft 지원에 전화를 걸어 새 테 넌 트가 다운 그레이드 되도록 해야 합니다. 













## <a name="related-links"></a>관련 링크

[비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[부여-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS (모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

