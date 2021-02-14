---
title: Teams 전용 모드 고려 사항
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 관리자는 Microsoft Teams 관리 센터에서 Microsoft Teams 전용 모드로 업그레이드를 준비하는 방법을 배울 수 있습니다.
localization_priority: Normal
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
ms.openlocfilehash: 86c27d8619a436c6a77ab435cfcb2cc4133befe0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802378"
---
# <a name="teams-only-mode-considerations"></a>Teams 전용 모드 고려 사항

Microsoft 365 또는 Office 365 조직의 관리자인 경우 이제 Microsoft Teams 관리 센터에서 Teams 전용 모드로 업그레이드하는 옵션이 표시됩니다. 이 기능을 사용하면 개별 사용자 또는 전체 테넌트 중 하나를 업그레이드할 수 있습니다.  

Teams 전용 모드로 업그레이드하면 단일 클라이언트 환경을 통해 Microsoft 365 또는 Office 365의 팀워크 허브인 Microsoft Teams의 모든 이점을 사용자에게 제공합니다. 또한 Teams 전용 모드의 사용자는 보낸 사람이 비즈니스용 Skype 또는 Teams를 사용하는지 여부에 관계없이 Teams에서 모든 통화와 채팅을 받고 상호 연계 및 페더맹 지원을 활용합니다.

수천 명의 고객이 Microsoft Teams로 성공적으로 업그레이드하는 동안 조직의 업그레이드 타임라인 및 사용자 경험에 영향을 줄 수 있는 고려 사항이 있습니다. 특히 업그레이드 옵션이 있는다고 해서 조직이 반드시 이 변경을 준비하고 있는 것은 아닙니다. 최상의 사용자 환경을 위해서는 Teams가 공동 작업 및 커뮤니케이션 요구 사항을 충족하는지와 네트워크가 Teams를 지원할 준비가 되었는지를 확인하고 사용자를 Teams에 업그레이드하기 전에 사용자 준비를 위한 계획을 구현해야 합니다. 

> [!IMPORTANT]
> 업그레이드 계획을 방금 시작한 경우 Microsoft Teams 업그레이드 가이드 시작 가이드를 [검토하세요.](upgrade-start-here.md) 

**공존 고려** 사항: 이미 비즈니스용 Skype Online 및/또는 비즈니스용 Skype Server를 사용하는 조직은 자신의 요구를 충족하는 속도로 Teams를 환경에 도입할 수 있습니다. 조직은 필요한 경우 원하는 사용자 집합으로 Teams를 증분 롤아웃할 수 있으며, Teams를 사용하는 사용자는 비즈니스용 Skype를 사용하는 사용자와 통신할 수 있으며 그 반대의 경우도 마찬가지입니다. 이 환경을 관리하기 위해 관리자는 최종 사용자 클라이언트 환경, 들어오는 채팅 및 통화의 라우팅 동작 및 Teams 또는 비즈니스용 Skype에서 새 모임을 예약하는지 여부를 정의하는 공존 모드를 사용하세요. 사용자가 Teams 전용으로 업그레이드된 경우 사용자는 다른 조직의 사용자와 페더러화할 **수 있습니다.** 그러나 두 사용자가 Teams를 모두 사용할 때 최상의 환경이 제공됩니다. Teams로 업그레이드된 사용자만 비즈니스용 Skype 모임에 참가할 수 있습니다. 

> [!IMPORTANT]
> 공존에 대한 자세한 내용은 Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 연동성 이해를 [참조하세요.](teams-and-skypeforbusiness-coexistence-and-interoperability.md) Teams 및 Skype(소비자)에 대한 자세한 내용은 Teams 및 Skype 상호 [연동성을 참조하세요.](teams-skype-interop.md)

**테넌트** 전체 고려 사항: 다음 환경에서 Teams를 사용하도록 설정하기 위해 작업 중입니다. 그러나 지금은 비즈니스용 Skype 테넌트가 다음 환경 중 하나에서 호스팅된 경우 관리자는 조직의 사용자를 업그레이드하지 말아야 합니다.

 - 21Vianet에서 운영하는 Office 365
 - Office 365 Germany
 - 비즈니스용 Skype 테넌트는 대한민국에서 호스팅되고 조직에서는 Teams 데이터를 대한민국에 저장해야 합니다.  현재 Teams로 업그레이드하는 비즈니스용 Skype 데이터가 대한민국에 저장된 조직에는 Teams 데이터가 대한민국 데이터 센터 지역이 아닌 아시아 데이터 센터 지역에 저장됩니다.

**사용자별 고려** 사항: 일부 사용자 시나리오는 계속 진화하고 있으며 관리자는 조직의 다른 사용자를 업그레이드하는 동안 특정 사용자의 업그레이드를 일시적으로 연기하기로 결정할 수 있습니다. 특히 주 디바이스가 VDI 기반인 사용자의 시나리오를 해결하기 위해 계속 작업하고 있습니다. Microsoft [365 로드맵](https://www.microsoft.com/microsoft-365/roadmap) 사이트에서 공지 사항을 모니터링하세요.

> [!NOTE]
> Teams 전용 모드로 전환하기 전에 Teams를 지원하지 않는 장치를 바꾸거나 업데이트해야 합니다. 

> [!IMPORTANT]
> **Teams로** 이동하는 것은 기술적인 마이그레이션보다 더 많은 것입니다. 성공적인 업그레이드는 기술 준비와 최종 사용자 준비 상태를 평가합니다. Teams로의 업그레이드 구현 [](upgrade-framework.md) 계획에 대한 자세한 내용은 비즈니스용 Skype-Teams 업그레이드 지침을 검토하세요.  
