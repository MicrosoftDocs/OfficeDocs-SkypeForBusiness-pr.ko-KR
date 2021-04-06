---
title: 비즈니스용 Skype 환경 해제
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
description: 비즈니스용 Skype 환경을 해제하는 방법에 대한 지침입니다.
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593901"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>비즈니스용 Skype 환경 해제

조직에서 비즈니스용 Skype 서버의 온-프레미스 배포에서 Teams 또는 비즈니스용 Skype Online을 사용하는 경우 이러한 환경을 클라우드로 완전히 마이그레이션한 다음 비즈니스용 Skype 서버의 온-프레미스 배포를 중지할 수 있습니다. 

> [!NOTE]
> 사내 환경을 해제하기 전에, 사내 [](configure-hybrid-connectivity.md) 배포와 Microsoft 365 간에 하이브리드 연결을 구성해야 합니다. 하이브리드 연결을 구성한 후 사용자를 클라우드로 마이그레이션하면서 모임을 사내에서 마이그레이션하고 비즈니스용 Skype 서버에서 Teams로 연락처를 마이그레이션할 수 있습니다. 하이브리드 연결을 구성하는 것은 사용자를 사내에서 클라우드로 마이그레이션하고 전체 Teams 기능을 보장하는 데 필요한 단계입니다.

사내에서 클라우드로의 이동을 완료하고 사내 비즈니스용 Skype 서버 환경을 해제하려면 다음 단계를 순서대로 완료해야 합니다.

- **1단계.** 필요한 모든 사용자 및 [응용 프로그램 끝점을](decommission-move-on-prem-users.md)프레미스에서 온라인으로 이동

- **2단계.** [하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)

- **3단계.** [비즈니스용 Skype 배포를 제거합니다.](decommission-remove-on-prem.md)

