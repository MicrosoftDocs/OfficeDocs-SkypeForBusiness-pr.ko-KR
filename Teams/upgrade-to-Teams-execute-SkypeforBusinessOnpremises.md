---
title: 비즈니스용 Skype 온-프레미스를 Teams로 업그레이드
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype 온-프레미스 배포에서 Microsoft Teams로 조직을 전환하는 방법을 알아봅니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b06134a0fe0f72e8dc9c01b4faa85c67a6063f3
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615444"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>비즈니스용 Skype 온-프레미스 배포에서 Teams로 업그레이드

![배포 및 구현 단계에 중점을 둔 업그레이드 과정의 단계입니다.](media/upgrade-banner-deployment.png "배포 및 구현 단계에 중점을 둔 업그레이드 과정의 단계")

이 문서는 업그레이드 과정의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 작업을 완료했는지 확인합니다.

- [프로젝트 관련자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)
- [비즈니스용 Skype 및 Teams의 공존 및 상호 운용성 이해](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [업그레이드 경험 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](./upgrade-prepare-environment.md)
- [조직 준비](./upgrade-prepare-organization.md)
- [파일럿 수행](./pilot-essentials.md)

비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포했으며 조직에서 여러 공존 모드 또는 올인을 사용하여 선택적으로 Microsoft Teams로 업그레이드하려는 경우 이 문서의 지침을 따릅니다. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>1단계: 하이브리드 연결 배포

사용자를 Teams로 업그레이드하기 위한 주요 필수 구성 요소는 하이브리드 연결을 배포하는 것입니다.

자세한 내용은 [비즈니스용 Skype 서버 비즈니스용 Skype Online 간의 하이브리드 연결 배포](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)를 참조하세요.

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>2단계: 조직에 대해 선택한 업그레이드 경험 구현

하이브리드 설정을 완료한 후에는 사용자를 Microsoft 365 또는 Office 365 이동할 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [TeamsUpgradePolicy: 마이그레이션 및 공존 관리](upgrade-to-teams-on-prem-tools.md).

- [온-프레미스에서 비즈니스용 Skype Online으로 사용자를 이동합니다](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>전화 시스템 및 Teams 업그레이드

온-프레미스 전화 시스템에서 Teams로 전환하면 전화 시스템 직접 라우팅("직접 라우팅") 또는 Microsoft 365 또는 Office 365 대한 Microsoft 제공 통화 플랜을 활용할 수 있습니다.

통화 플랜을 사용하지 않는 경우 Teams 업그레이드의 일환으로 엔터프라이즈 음성 배포를 전화 시스템 직접 라우팅으로 전환해야 합니다.

자세한 내용은 [전화 시스템 직접 라우팅에 대한 추가 고려 사항을 참조하세요](./direct-routing-landing-page.md). 통화 플랜을 사용하려는 경우 [전화 번호를 Teams로 전송하기](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 위한 지침을 참조하세요.