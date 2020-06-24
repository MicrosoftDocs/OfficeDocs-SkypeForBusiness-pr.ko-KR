---
title: 팀 전용 모드 고려 사항
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 관리자는 Microsoft 팀 관리 센터에서 Microsoft 팀 전용 모드로 업그레이드를 준비 하는 방법에 대해 알아볼 수 있습니다.
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
ms.openlocfilehash: 96ff2652a326e537f200c47495496dd81ea9fd4b
ms.sourcegitcommit: 27fae90d4429e81143ea285edab9dbc19bd3c0bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44854100"
---
# <a name="teams-only-mode-considerations"></a>팀 전용 모드 고려 사항

Microsoft 365 또는 Office 365 조직의 관리자는 Microsoft 팀 관리 센터에서 팀 전용 모드로 업그레이드 하는 옵션이 표시 됩니다. 이 기능을 사용 하 여 개별 사용자 또는 전체 테 넌 트 중 하나를 업그레이드할 수 있습니다.  

팀 전용 모드로 업그레이드 하면 단일 클라이언트 환경을 통해 microsoft 365 또는 Office 365의 팀워크에 대 한 허브가 Microsoft 팀의 모든 혜택을 제공 하 게 됩니다. 또한 팀 전용 모드의 사용자는 보낸 사람이 비즈니스용 Skype를 사용 하 고 있는지 여부에 관계 없이 팀의 모든 통화와 채팅을 받게 되며 interop 및 페더레이션 지원의 혜택을 받습니다.

수천 명의 고객이 Microsoft 팀으로 업그레이드 한 후 조직의 업그레이드 시간 표시 막대와 사용자 환경에 영향을 미칠 수 있는 고려 사항이 있습니다. 특히, 업그레이드 옵션이 반드시 조직이이 변경에 대 한 것을 의미 하는 것은 아닙니다. 최상의 사용자 환경을 위해서는 Teams가 공동 작업 및 커뮤니케이션 요구 사항을 충족하는지와 네트워크가 Teams를 지원할 준비가 되었는지를 확인하고 사용자를 Teams에 업그레이드하기 전에 사용자 준비를 위한 계획을 구현해야 합니다. 

> [!IMPORTANT]
> 업그레이드 계획을 시작 하는 경우 [Microsoft 팀 업그레이드 가이드 시작](upgrade-start-here.md) 을 검토 하세요. 

**공존 고려 사항**: 이미 비즈니스용 skype Online 및/또는 비즈니스용 skype 서버를 사용 하는 조직은 사용자의 요구에 맞는 속도로 팀을 환경에 도입할 수 있습니다. 조직에서는 필요에 따라 팀을 원하는 사용자 집합에 점진적으로 롤아웃할 수 있으며, 팀을 사용 하는 사용자는 비즈니스용 Skype를 사용 하는 사용자와 통신할 수 있으며 그 반대의 경우도 마찬가지입니다. 이러한 경험을 관리 하기 위해 관리자는 최종 사용자 클라이언트 경험, 들어오는 채팅 및 통화의 라우팅 동작, 팀에서 새 모임을 예약 했는지 여부, 그리고 비즈니스용 Skype를 사용 하는 등을 정의 하는 공존 모드를 사용할 수 있습니다. 사용자가 **팀**으로 업그레이드 한 경우 다른 조직의 사용자와 페더레이션 할 수 있습니다. 그러나 두 사용자가 모두 팀을 사용 하는 경우 최상의 환경이 제공 됩니다. 팀으로 업그레이드 한 사용자는 비즈니스용 Skype 모임에 계속 참가할 수 있습니다. 

> [!IMPORTANT]
> 공존에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md)를 참조 하세요. 

**테 넌 트 전체 고려 사항**: 다음 환경에서 팀을 사용 하도록 설정할 수 있습니다. 그러나 지금은 비즈니스용 Skype 테 넌 트가 다음 환경 중 하나에서 호스팅되는 경우 관리자는 조직의 모든 사용자를 업그레이드 하지 않아야 합니다.

 - 21Vianet에서 운영 하는 Office 365
 - Office 365 독일
 - 비즈니스용 Skype 테 넌 **트가 대한민국에서** 호스팅되며 조직에는 대한민국에 저장 되는 팀 데이터가 필요 합니다. 현재 대한민국에 저장 된 비즈니스용 Skype 데이터를 보유 하 고 있는 조직에서 팀으로 업그레이드 하면 해당 팀 데이터가 동남 한국 데이터 센터 지역에 저장 되지 않고 아시아 데이터 센터 지역에 저장 됩니다.

**사용자 관련 고려 사항**: 일부 사용자 시나리오는 계속 진화 하 고 있으며, 관리자는 조직의 다른 사용자를 업그레이드 하면서 특정 사용자의 업그레이드를 일시적으로 연기 하도록 결정할 수 있습니다. 특히, 기본 장치가 VDI 기반 사용자에 대 한 주소 지정 시나리오를 계속 사용 하 고 있습니다. [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap) 사이트에서 공지 사항을 모니터링 하세요.

> [!NOTE]
> 팀 전용 모드로 이동 하기 전에 팀을 지원 하지 않는 장치를 바꾸거나 업데이트 해야 합니다. 

> [!IMPORTANT]
> 팀으로 이동 하는 것은 기술적 마이그레이션 보다 더 **주의할**사항입니다. 성공적인 업그레이드는 기술 준비 및 최종 사용자 준비를 모두 평가 합니다. 팀으로 업그레이드를 구현 하는 방법을 계획 하는 방법에 대 한 자세한 내용은 팀의 비즈니스용 Skype [업그레이드 지침](upgrade-framework.md) 을 참조 하세요.  
