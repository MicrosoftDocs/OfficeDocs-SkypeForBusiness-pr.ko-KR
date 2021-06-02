---
title: 통화 공유 및 그룹 전화 받기
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
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
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 통화 공유 및 그룹 호출 픽업을 통해 사용자가 들어오는 전화를 동료와 공유할 수 있으므로 사용자를 사용할 수 없는 경우 호출을 캡처할 수 있습니다.
ms.openlocfilehash: 98094ff0b4b5d7b037915273b2c2730d42517c22
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717839"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>통화 공유 및 그룹 통화 Microsoft Teams

통화 공유 및 그룹 호출 Microsoft Teams 사용자가 들어오는 호출을 동료와 공유할 수 있도록 하여 사용자가 사용자를 사용할 수 없는 동안 발생하는 호출에 응답할 수 있도록 합니다.

그룹 통화 픽업은 다른 형태의 통화 공유(예: 통화 전달 또는 동시 벨소리)보다 받는 사람에게 덜 방해가 됩니다. 이는 사용자가 들어오는 공유 통화에 대한 알림을 받는 방법을 구성할 수 있기 때문에(오디오 및 시각적 알림, 시각적 전용 또는 배너를 통해) 수신자에 대한 응답 여부를 Teams 수 있습니다.

다른 사용자와 통화를 공유하기 위해 사용자는 통화 그룹을 만들고 통화를 공유할 사용자를 추가합니다. 그런 다음 동시 링 또는 앞으로 설정을 선택할 수 있습니다. 자세한 [내용은](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 전화 전달 및 Teams 링을 참조합니다. 모바일 디바이스는 배너 및 벨소리로 설정되어 있는 경우 알림을 받을 수 있습니다.

> [!IMPORTANT]
> 사용자, 호출 그룹 소유자 및 호출 그룹의 구성원은 배포 Teams 있어야 합니다. 배포 모드에 대한 Teams 자세한 내용은 Microsoft Teams 및 상호 비즈니스용 Skype 이해를 [참조합니다.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>라이선스 필수

사용자는 통화 공유 및 그룹 통화 Microsoft Teams 전화 시스템 설정 및 사용하려면 사용자 라이선스를 할당해야 합니다. 라이선스 모델 [전화 시스템에](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)대한 자세한 내용은 다음을 참조하세요.

## <a name="configure-group-call-pickup"></a>그룹 호출 픽업 구성

그룹 호출 픽업을 설정하기 위해 사용자는 먼저 호출 그룹을 구성합니다(보안 그룹 또는 Microsoft 365 그룹과 같지 않습니다). 그런 다음 동시 링을 선택하거나 앞으로 설정을 호출합니다. 자세한 정보 및 단계별 절차는 에서 전달 및 동시 링 [호출을 Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

통화 그룹 만들기 및 알림 기본 설정은 사용자 기반 기능입니다. 관리자는 사용자에 대해 이러한 기능을 구성할 수 없습니다. 통화 그룹은 보안 그룹 또는 그룹에서 만들 수 Microsoft 365 없습니다. 은 에서 만들어 Teams.

관리자는 사용자에 대한 **TeamsCallingPolicy AllowCallGroups** 설정을 통해 통화 그룹을 사용하도록 설정해야 합니다. 관리자는 관리자 포털을 통해 Teams 수 있습니다.  또한 구성된 사용자는 클라이언트를 통해 직접 호출 그룹을 구성할 수도 있습니다. 관리자 또는 최종 사용자는 서로 구성을 차단할 수 없지만 Teams 포털 및 Teams 클라이언트는 두 위치 모두에서 이 관계를 정확하게 표시해야 합니다. 

중요: 관리자가 사용자에 대한 통화 그룹을 끄면(통화 그룹 관계가 설정되어 통화 그룹 관계가 구성된 후) 관리자는 잘못된 통화 라우팅을 방지하기 위해 Teams 관리 센터의 사용자에 대한 통화 그룹 관계를 정리해야 합니다. 

## <a name="limitations"></a>제한 사항

구성된 각 호출 그룹에는 최대 25명 또는 32,768자까지 사용할 수 있습니다. 

## <a name="more-information"></a>추가 정보

[통화에서 전달 및 동시 Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
