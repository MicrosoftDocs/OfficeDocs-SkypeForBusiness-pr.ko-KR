---
title: 비즈니스용 Skype 하이브리드 배포를 Teams로 업그레이드
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype 하이브리드 배포에서 Microsoft Teams로 조직을 업그레이드하는 방법을 알아봅니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea8db9f53b891002cf7fbe1f5282051e7aca7ea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615604"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>비즈니스용 Skype 하이브리드 배포에서 Teams로 업그레이드

![배포 및 구현 단계에 중점을 둔 업그레이드 과정의 단계입니다.](media/upgrade-banner-deployment.png "배포 및 구현 단계에 중점을 둔 업그레이드 과정의 단계")

이 문서는 업그레이드 과정의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 작업을 완료했는지 확인합니다.

- [프로젝트 관련자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)
- [비즈니스용 Skype 및 Teams의 공존 및 상호 운용성 이해](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [업그레이드 경험 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](./upgrade-prepare-environment.md)
- [조직 준비](./upgrade-prepare-organization.md)
- [파일럿 수행](./pilot-essentials.md)

비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포하고 Microsoft 365 또는 Office 365 조직에서 하이브리드 배포에 구성했으며 조직에서 여러 공존 모드 또는 올인을 사용하여 선택적으로 Teams로 업그레이드하려는 경우 이 문서의 지침을 따릅니다. 업그레이드 과정의 경우 사용자를 비즈니스용 Skype Online(아직 온라인 홈이 아닌 경우)으로 이동한 다음 적절한 공존 및 업그레이드 모드를 할당해야 합니다.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>1단계: 사용자를 비즈니스용 Skype Online으로 이동

이 단계는 현재 온-프레미스에 있는 사용자에게 적용됩니다. 이러한 사용자를 비즈니스용 Skype Online으로 이동하는 방법에 대한 자세한 내용은 [온-프레미스에서 비즈니스용 Skype Online으로 사용자 이동을](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online) 참조하세요.

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>2단계: 공존 및 업그레이드 모드 할당

사용자를 비즈니스용 Skype Online으로 이동한 후에는 조직에서 선택한 업그레이드 경험에 따라 적절한 공존 모드를 할당할 수 있습니다. 자세한 내용은 [공존 및 업그레이드 설정 및](./setting-your-coexistence-and-upgrade-settings.md) [TeamsUpgradePolicy 설정: 마이그레이션 및 공존 관리를](upgrade-to-teams-on-prem-tools.md) 참조하세요.

> [!NOTE]
> 비즈니스용 Skype 서버 2019 및 향후 비즈니스용 Skype 서버 2015의 누적 업데이트를 사용하면 1단계(사용자를 비즈니스용 Skype Online으로 이동) 및 2단계(사용자를 Teams로 업그레이드)를 한 단계로 수행할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버 2019가 릴리스된 후에 제공됩니다.

## <a name="phone-system-and-teams-upgrade"></a>전화 시스템 및 Teams 업그레이드

비즈니스용 Skype 하이브리드 배포를 통화 플랜이 있는 전화 시스템으로 전환하는 경우 Microsoft는 PSTN(공중 전화망) 공급자가 되며 전화 번호 포팅을 완료했다고 가정하면 사용자를 Teams로 업그레이드하면 인바운드 PSTN 통화가 Teams로 자동으로 전환됩니다.

통화 플랜을 사용할 수 없거나 기존 PSTN 연결 공급자를 사용하려는 경우 엔터프라이즈 음성 배포 또는 기존 온-프레미스 배포 또는 클라우드 커넥터 버전을 사용하는 하이브리드 음성 배포를 Microsoft Phone 시스템 직접 라우팅으로 전환해야 합니다. 사용자를 Teams로 업그레이드하려면 [전화 시스템 직접 라우팅에 대한 추가 고려 사항을](./direct-routing-landing-page.md) 참조하세요.