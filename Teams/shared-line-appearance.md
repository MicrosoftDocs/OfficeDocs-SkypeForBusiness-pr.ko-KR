---
title: Microsoft 팀의 공유 선 모양
ms.author: lolaj
author: LolaJacobsen
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
description: Microsoft 팀의 오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일을 보내는 방법에 대해 알아봅니다.
ms.openlocfilehash: 92eda8a1818d98689e71d81f31c5355df3ef1e26
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45125981"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft 팀의 공유 선 모양

공유 선 모양은 사용자가 자신을 대신 하 여 통화에 응답 하거나 처리할 대리인을 선택할 수 있는 위임 기능의 일부입니다. 이 기능은 사용자가 사용자의 통화를 정기적으로 처리 하는 관리 도우미가 있는 경우에 유용 합니다. 공유 선 모양의 컨텍스트에서 관리자는 자신을 대신 하 여 전화를 걸거나 받을 대리인에 게 권한을 부여 하 고 대리인이 다른 사람을 대신 하 여 전화를 걸고 받을 수 있는 사람을 말합니다.

> [!IMPORTANT]
> 이 기능은 팀 전용 배포 모드 에서만 사용할 수 있습니다. 팀 배포 모드에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하세요.

## <a name="license-required"></a>라이선스 필요

사용자에 게는 휴대폰 시스템 (통화 계획 라이선스 또는 다이렉트 라우팅 OnlineVoiceRoutingPolicy)이 대리인 이거나 위임을 설정 하 고 다른 사용자가 자신을 대신 하 여 전화를 걸거나 받을 수 있도록 해야 합니다.

관리자와 대리인 모두 PSTN 연결 (통화 계획 라이선스 또는 다이렉트 라우팅 OnlineVoiceRoutingPolicy)의 전화 시스템을 사용 해야 합니다. 공유 회선 환경은 위임의 일부 이며 전화 시스템에 포함 되어 있습니다. 라이선스 모델에 대 한 자세한 내용은 [Microsoft 팀 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)참조 하세요.

## <a name="configuring-delegation-and-shared-line-appearance"></a>위임 및 공유 선 모양 구성

위임 및 공유 선 모양은 구성할 관리 설정이 없기 때문에 사용자 기반 기능입니다. 이 기능을 사용 하는 방법에 대 한 자세한 내용은 [대리인과 전화 회선 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8) 를 참조 하세요.

테 넌 트 관리자는이 기능을 사용 하기 위해 **Teamscallingpolicy AllowDelegation** 설정 또는 팀 관리 포털을 통해 위임을 사용할 수 있습니다. 

테 넌 트 관리자는 또한 팀 관리 센터에서 사용자에 대 한 위임 관계를 구성할 수 있습니다. 또한 최종 사용자는 팀에서 직접 위임 관계를 구성할 수도 있습니다. 테 넌 트 관리자 또는 사용자는 서로에 대 한 구성을 차단할 수 없지만 팀 관리 센터 및 팀 클라이언트는이 관계를 두 위치에 정확 하 게 표시 해야 합니다. 

> [!IMPORTANT]
> 테 넌 트 관리자가 사용자에 대 한 위임 기능을 해제 하면 (설정 된 후) 팀 관리 센터에서 해당 사용자에 대 한 위임 관계도 정리 하 여 잘못 된 통화 라우팅이 발생 하지 않도록 해야 합니다.

## <a name="shared-line-appearance-feature-availability"></a>공유 선 모양 기능 가용성

현재 공유 선 모양은 다음 앱 및 장치에서 지원 됩니다.

| 기능 | 팀 데스크톱 | 팀 Mac 앱 | 팀 웹 앱 (Edge) |팀 모바일 iOS/Android 앱 | 팀 IP 전화 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 대리인 설정 | 예 | 예 | 예 | 아니오 | 예 |
| 다른 사람을 대신 하 여 전화 받기 | 예 | 예 | 예 | 예 | 예 |
| 다른 사람을 대신 하 여 전화 번호 호출 | 예 | 예 | 예 | 예 | 예 |
| 다른 사람을 대신 하 여 팀 사용자에 게 전화 | 예 | 예 | 예 | 예 | 예 |
| 공유 된 회선의 관리 보기를 참조 하세요. | 예 | 예 | 예 | 아니요 | 아니요 |
| 관리자의 통화 활동에 대 한 관리 보기를 참조 하세요. | 예 | 예 | 예 | 아니요 | 아니요 |
| 대리인의 관리자 보기 참조 | 예 | 예 | 예 | 아니요 | 아니요 |
| 관리자 또는 관리자가 보류 또는 다시 시작 가능 | 예 | 예 | 예 | 아니요 | 아니요 |

## <a name="limitations"></a>따릅니다

관리자는 대리인을 최대 25 개까지 추가할 수 있으며 대리인은 최대 25 명의 관리자를 가질 수 있습니다. 테 넌 트에서 만들 수 있는 위임 관계의 수에는 제한이 없습니다. 
 
위임자와 대리인이 같은 지리적 위치에 있지 않은 경우 발신자 ID가 위임 됨 (대신) 통화에 대해 다른 지리적 위치에서 표시 되도록 하는 것은 PSTN 공급자에 게 있습니다. 
 
## <a name="more-information"></a>추가 정보

[대리인과 전화 라인 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
