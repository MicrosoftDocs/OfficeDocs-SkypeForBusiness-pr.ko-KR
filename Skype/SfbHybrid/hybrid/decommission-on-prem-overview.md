---
title: 온-프레미스 비즈니스용 Skype 환경 해제
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
description: 프레미스 클라우드 환경을 해제하는 비즈니스용 Skype 지침입니다.
ms.openlocfilehash: 0f1b25c6960739992913f31a89a9f554fb180e949df3e6dd213b5fbe14c4af82
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280354"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>온-프레미스 비즈니스용 Skype 환경 해제

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

조직에서 Teams 온-프레미스 배포와 함께 비즈니스용 Skype 서버 이러한 환경을 클라우드로 완전히 마이그레이션한 다음 온-프레미스 배포를 중지할 수 비즈니스용 Skype 서버. 

> [!NOTE]
> 프레미스 환경을 해제하기 전에, 프레미스 배포와 프레미스 배포 간에 하이브리드 연결을 구성해야 Microsoft 365. [](configure-hybrid-connectivity.md) 하이브리드 연결을 구성한 후 사용자를 클라우드로 마이그레이션하는 동시에 모임을 사내에서 마이그레이션하고 연락처를 클라우드에서 클라우드로 마이그레이션할 비즈니스용 Skype 서버 Teams. 하이브리드 연결을 구성하는 것은 사용자를 사내에서 클라우드로 마이그레이션하고 전체 하이브리드 연결 기능을 Teams 단계입니다.

사내에서 클라우드로의 이동을 완료하고 비즈니스용 Skype 서버 환경을 해제하려면 다음 단계를 순서대로 완료해야 합니다.

- **1단계.** 필요한 모든 사용자를 프레미스에서 [온라인으로 이동](decommission-move-on-prem-users.md)

- **2단계.** [하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)

- **3단계.** [하이브리드 응용 프로그램 끝점을](decommission-move-on-prem-endpoints.md)프레미스에서 온라인으로 이동

- **4단계.** [배포 에서 프레미스 비즈니스용 Skype 제거합니다.](decommission-remove-on-prem.md)

