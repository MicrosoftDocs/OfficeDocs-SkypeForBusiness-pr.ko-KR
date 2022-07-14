---
title: 통화 공유 및 그룹 전화 받기
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 통화 공유 및 그룹 통화 픽업을 사용하면 사용자가 전화를 사용할 수 없을 때 통화를 캡처할 수 있도록 동료와 수신 전화를 공유할 수 있습니다.
ms.openlocfilehash: 70b1be389309d52b01852e575d08093ef7095a04
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789953"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams에서 통화 공유 및 그룹 통화 픽업

Microsoft Teams의 통화 공유 및 그룹 통화 픽업 기능을 사용하면 사용자가 수신 전화를 동료와 공유할 수 있으므로 동료가 사용자를 사용할 수 없는 동안 발생하는 통화에 응답할 수 있습니다.

그룹 통화 픽업은 다른 형태의 통화 공유(예: 착신 전환 또는 동시 벨소리)보다 받는 사람에게 덜 방해가 됩니다. 사용자가 수신 공유 통화에 대한 알림을 받는 방법을 구성할 수 있기 때문입니다(Teams 앱의 오디오 및 시각적 알림, 시각적 알림만 또는 배너를 통해).

다른 사용자와 통화를 공유하기 위해 사용자는 통화 그룹을 만들고 통화를 공유하려는 사용자를 추가합니다. 그런 다음 동시 링 또는 정방향 설정을 선택합니다. 자세한 내용은 [Teams에서 착신 전환 및 동시 링을](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 참조하세요. 모바일 장치는 배너 및 벨소리로 설정된 경우에만 알림을 받습니다.

> [!IMPORTANT]
> 사용자, 통화 그룹 소유자 및 통화 그룹의 구성원은 Teams 전용 배포 모드에 있어야 합니다. Teams 배포 모드에 대한 자세한 내용은 [Microsoft Teams 이해 및 비즈니스용 Skype 공존 및 상호 운용성을](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 참조하세요.

## <a name="license-required"></a>라이선스 필요

통화 공유 및 그룹 통화 픽업을 설정하고 사용하려면 사용자에게 Microsoft Teams 전화 시스템 라이선스가 할당되어야 합니다. 라이선스 모델에 대한 자세한 내용은 [전화 시스템을 사용하여 얻을 수 있는 항목을 참조](/MicrosoftTeams/here-s-what-you-get-with-phone-system)하세요.

## <a name="configure-group-call-pickup"></a>그룹 호출 픽업 구성

그룹 통화 픽업을 설정하기 위해 사용자는 먼저 통화 그룹(보안 그룹 또는 Microsoft 365 그룹과 동일하지 않음)을 구성한 다음 통화를 공유하려는 사용자를 추가합니다. 그런 다음 동시 링 또는 착신 전환 설정을 선택합니다. 자세한 내용 및 단계별 절차는 [Teams에서 착신 전환 및 동시 링을 참조하세요](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

통화 그룹 만들기 및 알림 기본 설정은 사용자 기반 기능입니다. 관리자는 사용자에 대해 이러한 기능을 구성할 필요가 없습니다. 보안 그룹 또는 Microsoft 365 그룹에서 호출 그룹을 만들 수 없습니다. Teams에서 만들어야 합니다.

관리자는 사용자에 대한 **TeamsCallingPolicy AllowCallGroups** 설정을 통해 통화 그룹을 사용하도록 설정해야 합니다. 관리자는 Teams 관리 포털을 통해 이를 사용하도록 설정할 수도 있습니다.  또한 구성된 사용자는 클라이언트를 통해 직접 통화 그룹을 구성할 수도 있습니다. 관리 또는 최종 사용자가 서로 구성을 차단할 수는 없지만 Teams 관리 포털 및 Teams 클라이언트는 두 위치에서 이 관계를 정확하게 표시해야 합니다. 

중요: 관리자가 사용자에 대한 통화 그룹을 끄면(통화 그룹 관계가 설정된 후) 관리자는 잘못된 통화 라우팅을 방지하기 위해 Teams 관리 센터의 사용자에 대한 통화 그룹 관계를 정리해야 합니다. 

## <a name="limitations"></a>제한 사항

구성된 각 통화 그룹은 최대 25명의 사용자 또는 32,768자를 가질 수 있습니다. 

## <a name="more-information"></a>추가 정보

[Teams에서 착신 전환 및 동시 연결](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
