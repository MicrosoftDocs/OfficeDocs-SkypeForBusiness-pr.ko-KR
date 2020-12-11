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
description: 통화 공유 및 그룹 통화 픽업을 통해 사용자가 수신 전화를 동료와 공유할 수 있으므로 사용자를 사용할 수 없는 경우 통화를 캡처할 수 있습니다.
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620729"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams에서 통화 공유 및 그룹 통화 픽업

Microsoft Teams의 통화 공유 및 그룹 통화 픽업 기능을 통해 사용자가 수신 전화를 동료와 공유할 수 있으므로 사용자가 전화를 사용할 수 없는 동안 동료가 발생하는 통화에 응답할 수 있습니다.

그룹 통화 선택은 다른 형태의 통화 공유(예: 통화 전달 또는 동시 연결)보다 받는 사람에게 덜 방해가 됩니다. 사용자가 수신 공유 통화에 대한 알림을 받는 방법을 구성할 수 있으며(Teams 앱에서 오디오 및 시각적 알림, 시각적 전용 또는 배너를 통해) 응답할지 여부를 결정할 수 있기 때문에 수신자에게 덜 방해가 됩니다.

다른 사용자와 통화를 공유하기 위해 사용자는 통화 그룹을 만들고 통화를 공유하려는 사용자를 추가합니다. 그런 다음 동시 링 또는 앞으로 설정을 선택 합니다. 자세한 [내용은 Teams에서](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 통화 전달 및 동시 링을 참조합니다. 모바일 디바이스는 배너 및 벨소리가 설정된 경우 알림을 받을 수 있습니다.

> [!IMPORTANT]
> 사용자, 통화 그룹 소유자 및 통화 그룹의 구성원은 Teams 전용 배포 모드에 있어야 합니다. Teams 배포 모드에 대한 자세한 내용은 Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 연동성 [이해를 참조하세요.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>라이선스 필요

사용자는 통화 Enterprise Voice 및 그룹 통화 픽업을 설정하고 사용할 수 있도록 설정되어 있어야 합니다. 라이선스 모델에 대한 자세한 내용은 Microsoft Teams 서비스 [설명을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="configure-group-call-pickup"></a>그룹 호출 픽업 구성

그룹 통화 픽업을 설정하기 위해 사용자는 먼저 통화 그룹을 구성한 다음(보안 그룹 또는 Microsoft 365 그룹과는 다를 수) 통화를 공유하려는 사용자를 추가합니다. 그런 다음 동시 링 또는 전달 설정을 선택 합니다. 자세한 정보 및 단계별 절차는 Teams에서 통화 전달 및 동시 링을 [참조하세요.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

호출 그룹 만들기 및 알림 기본 설정은 사용자 기반 기능입니다. 관리자는 사용자에 대해 이러한 기능을 구성할 수 없습니다. 통화 그룹은 보안 그룹 또는 Microsoft 365 그룹에서 만들 수 없습니다. Teams에서 만들어야 합니다.

관리자는 사용자의 **TeamsCallingPolicy AllowCallGroups** 설정을 통해 통화 그룹을 사용하도록 설정해야 합니다. 관리자는 Teams 관리 포털을 통해 이를 사용하도록 설정할 수도 있습니다.  또한 구성된 사용자는 클라이언트를 통해 직접 호출 그룹을 구성할 수도 있습니다. 관리자 또는 최종 사용자는 서로 구성을 차단할 수 없지만 Teams 관리 포털 및 Teams 클라이언트는 두 위치 모두에서 이 관계를 정확하게 표시해야 합니다. 

중요: 관리자가 사용자에 대한 통화 그룹을 끄면(통화 그룹 관계가 설정되고 통화 그룹 관계가 구성된 후) 관리자는 Teams 관리 센터에서 사용자의 통화 그룹 관계를 정리하여 잘못된 통화 라우팅을 방지해야 합니다. 

## <a name="limitations"></a>제한 사항

테넌트에는 최대 32,768개 호출 그룹이 포함될 수 있습니다. 각 통화 그룹에는 최대 25명까지 사용자가 있을 수 있습니다. 

## <a name="more-information"></a>추가 정보

[Teams에서 통화 전달 및 동시 링](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
