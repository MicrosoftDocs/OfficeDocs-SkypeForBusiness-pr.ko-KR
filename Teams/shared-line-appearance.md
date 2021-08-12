---
title: 공유 줄 모양의 Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: 오디오 회의 정보를 통해 사용자에게 전자 메일을 보내는 방법에 대해 Microsoft Teams.
ms.openlocfilehash: 6c3a60bbdde46ae707543e2f28cd936dbbb2fc13dfb3535661a710984c284d75
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350440"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>공유 줄 모양의 Microsoft Teams

공유 줄 모양은 사용자가 대신 호출에 응답하거나 처리할 대리인을 선택할 수 있는 위임 기능의 일부입니다. 이 기능은 사용자의 호출을 정기적으로 처리하는 관리 도우미가 있는 경우 유용합니다. 공유 줄 모양의 컨텍스트에서 관리자는 대리인을 대신하여 전화를 걸거나 받을 수 있도록 권한을 위임하는 사람으로, 대리인은 다른 사람을 대신하여 전화를 걸고 받을 수 있습니다.

> [!IMPORTANT]
> 이 기능은 배포 Teams 사용할 수 있습니다. 배포 모드에 대한 Teams 자세한 내용은 Microsoft Teams 및 상호 비즈니스용 Skype 이해를 [참조합니다.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>라이선스 필수

사용자는 PSTN 연결(전화 시스템 계획 라이선스 또는 직접 라우팅 OnlineVoiceRoutingPolicy)을 사용하여 위임 또는 위임 설정 및 다른 사용자가 대신 전화를 걸거나 받을 수 있도록 해야 합니다.

관리자와 대리인 모두 PSTN 연결(전화 시스템 계획 라이선스 또는 Direct 라우팅 OnlineVoiceRoutingPolicy)을 사용할 수 있어야 합니다. 공유 줄 환경은 위임의 일부로 전화 시스템. 라이선스 모델에 대한 자세한 내용은 서비스 [Microsoft Teams 참조하세요.](/office365/servicedescriptions/teams-service-description)

## <a name="configuring-delegation-and-shared-line-appearance"></a>위임 및 공유 줄 모양 구성

위임 및 공유 줄 모양은 사용자 기반 기능입니다. 구성할 관리자 설정이 없습니다. 이 기능을 사용하는 방법에 대한 자세한 내용은 대리인과 전화선 [공유를 참조하세요.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

테넌트 관리자는 **TeamsCallingPolicy AllowDelegation** 설정을 통해 위임하거나 이 기능을 사용할 Teams 관리 포털을 통해 위임할 수 있습니다. 

테넌트 관리자는 관리 센터의 사용자에 대한 위임 Teams 수 있습니다. 또한 최종 사용자는 해당 위임 관계를 직접 구성할 Teams. 테넌트 관리자 또는 사용자가 서로 구성을 차단할 수 없지만 Teams 관리 센터 및 Teams 클라이언트는 두 위치 모두에서 이 관계를 정확하게 표시해야 합니다. 

> [!IMPORTANT]
> 테넌트 관리자가 사용자에 대한 위임(설정한 후)을 해제하면 잘못된 호출 라우팅을 방지하기 위해 Teams 관리 센터에서 해당 사용자에 대한 위임 관계를 정리해야 합니다.

## <a name="shared-line-appearance-feature-availability"></a>공유 줄 모양 기능 가용성

공유 줄 모양은 현재 다음 앱 및 장치에서 지원됩니다.

| 기능 | Teams 데스크톱 | Teams Mac 앱 | Teams 웹앱(Edge) |Teams iOS/Android 앱 | Teams IP 전화 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 위임 설정 | 예 | 예 | 예 | 아니요 | 예 |
| 다른 대신 통화 받기 | 예 | 예 | 예 | 예 | 예 |
| 다른 대신 전화 번호로 전화 걸기 | 예 | 예 | 예 | 예 | 예 |
| 다른 사용자를 대신하여 Teams 사용자를 호출합니다. | 예 | 예 | 예 | 예 | 예 |
| 공유 줄의 관리자 보기를 참조하세요. | 예 | 예 | 예 | 아니요 | 아니요 |
| 관리자의 통화 활동의 관리자 보기 보기를 참조하세요. | 예 | 예 | 예 | 아니요 | 아니요 |
| 대리인의 관리자 보기 | 예 | 예 | 예 | 아니요 | 아니요 |
| 관리자 또는 관리자는 보류 또는 재개할 수 있습니다. | 예 | 예 | 예 | 아니요 | 아니요 |

## <a name="limitations"></a>제한 사항

관리자는 최대 25명까지 대리인을 추가할 수 있으며 대리인은 최대 25명의 관리자를 사용할 수 있습니다. 테넌트에서 만들 수 있는 위임 관계 수에는 제한이 없습니다. 
 
위임자 및 대리인이 동일한 지리적 위치에 있지 않은 경우 발신자 ID가 위임된(대신) 호출에 대해 다른 지리적 위치에서 표시하도록 허용하는 것은 PSTN 공급자의 의결입니다. 
 
## <a name="more-information"></a>추가 정보

[대리인과 전화선 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)