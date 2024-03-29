---
title: Teams 전용 모드 고려 사항
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 관리 Microsoft Teams 관리 센터에서 Microsoft Teams 전용 모드로 업그레이드를 준비하는 방법에 대해 알아볼 수 있습니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b80a563d6d3938a597e57aab4ac93e41df976d32
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605867"
---
# <a name="teams-only-mode-considerations"></a>Teams 전용 모드 고려 사항

Microsoft 365 또는 Office 365 조직의 관리자는 개별 사용자 또는 전체 테넌트 중 하나를 Teams 전용 모드로 업그레이드할 수 있습니다.  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Teams 전용 모드로 업그레이드하면 단일 클라이언트 환경을 통해 Microsoft 365 또는 Office 365 팀워크를 위한 허브인 Microsoft Teams의 모든 이점을 사용자에게 제공합니다. Teams 전용 모드의 사용자는 발신자가 비즈니스용 Skype 또는 Teams를 사용하는지 여부에 관계없이 Teams의 모든 통화 및 채팅을 수신하고 interop 및 페더레이션 지원을 활용합니다.

수천 명의 고객이 Microsoft Teams로 성공적으로 업그레이드되었지만 조직의 업그레이드 타임라인 및 사용자 환경에 영향을 줄 수 있는 고려 사항이 있습니다. 최상의 사용자 환경을 위해서는 Teams가 공동 작업 및 커뮤니케이션 요구 사항을 충족하는지와 네트워크가 Teams를 지원할 준비가 되었는지를 확인하고 사용자를 Teams에 업그레이드하기 전에 사용자 준비를 위한 계획을 구현해야 합니다. 

> [!IMPORTANT]
> 업그레이드 계획을 막 시작하는 경우 [Microsoft Teams](upgrade-start-here.md) 업그레이드 가이드 시작 가이드를 검토해야 합니다. 

**공존 고려 사항**: 이미 비즈니스용 Skype Online 및/또는 비즈니스용 Skype 서버 사용하는 조직은 요구 사항을 충족하는 속도로 Teams를 환경에 도입할 수 있습니다. 조직은 필요에 따라 원하는 사용자 집합에 Teams를 증분 방식으로 배포할 수 있으며, Teams를 사용하는 사용자는 비즈니스용 Skype 사용하는 사용자와 통신할 수 있으며 그 반대의 경우도 마찬가지입니다. 이 환경을 관리하기 위해 관리자는 최종 사용자 클라이언트 환경, 들어오는 채팅 및 통화의 라우팅 동작 및 Teams 또는 비즈니스용 Skype 새 모임이 예약되는지 여부를 정의하는 공존 모드를 사용합니다. 사용자가 **Teams 전용** 으로 업그레이드된 경우 사용자는 다른 조직의 사용자와 페더레이션할 수 있습니다. 그러나 두 사용자가 Teams를 사용할 때 최상의 환경이 제공됩니다. Teams로 업그레이드된 사용자만 비즈니스용 Skype 모임에 참가할 수 있습니다. 

> [!IMPORTANT]
> 공존에 대한 자세한 내용은 [Microsoft Teams 이해 및 비즈니스용 Skype 공존 및 상호 운용성을](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 참조하세요. Teams 및 Skype(소비자)에 대한 자세한 내용은 [Teams 및 Skype 상호 운용성을](teams-skype-interop.md) 참조하세요.


**사용자별 고려 사항**: 일부 사용자 시나리오는 계속 발전하고 있으며 관리자는 조직의 다른 사용자를 업그레이드하는 동안 특정 사용자의 업그레이드를 일시적으로 연기하기로 결정할 수 있습니다. 특히 기본 디바이스가 VDI 기반인 사용자에 대한 시나리오를 해결하기 위해 여전히 노력하고 있습니다. 사이트 공지 사항의 경우 [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap)을 모니터링합니다.

> [!NOTE]
> Teams 전용 모드로 전환하기 전에 Teams를 지원하지 않는 장치를 교체하거나 업데이트해야 합니다. 

> [!IMPORTANT]
> **기억하세요**. Teams로의 이동은 기술 마이그레이션 이상입니다. 성공적인 업그레이드는 기술 준비 상태와 최종 사용자 준비 상태를 모두 평가합니다. Teams 업그레이드 구현 계획에 대한 자세한 내용은 Teams [업그레이드 지침](upgrade-framework.md)에 대한 비즈니스용 Skype 검토하세요.  
