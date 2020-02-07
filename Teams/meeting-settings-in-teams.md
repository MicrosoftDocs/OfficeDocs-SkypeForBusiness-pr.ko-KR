---
title: 모임 설정 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: 사용자가 조직에서 예약한 팀 모임에 대 한 설정을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: bed367c9c40bb7124235abf204bbfa0395859685
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836468"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Microsoft 팀에서 모임 설정 관리

관리자는 팀 모임 설정을 사용 하 여 익명 사용자가 팀 모임에 참가 하 고, 모임 초대를 사용자 지정 하 고, 서비스 품질 (QoS)을 사용할 수 있는지 여부를 제어 하 고, 실시간 트래픽에 대 한 포트 범위를 설정 합니다. 이러한 설정은 사용자가 조직에서 예약 하는 모든 팀 모임에 적용 됩니다. Microsoft 팀 관리 센터의 **모임** > **모임 설정** 에서 이러한 설정을 관리할 수 있습니다.

## <a name="allow-anonymous-users-to-join-meetings"></a>익명 사용자가 모임에 참가할 수 있도록 허용

익명 참가를 사용 하면 모든 사용자가 모임 초대의 링크를 클릭 하 여 익명 사용자로 모임에 참가할 수 있습니다. 자세히 알아보려면 [팀 계정 없이 모임 참가](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)를 참고 하세요.


![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **모임** > **모임 설정**으로 이동 합니다.
2. **참가자**에서 **익명 사용자가 모임에 참가할 수 있도록**설정 합니다.

    ![관리 센터의 모임 참가자 설정 스크린샷](media/meeting-settings-participants.png "Microsoft 팀 관리 센터의 팀 모임에 대 한 참가자 설정 스크린샷")

익명 사용자가 조직의 사용자가 예약한 모임에 참가 하는 것을 원하지 않는다면이 설정을 끄세요.

## <a name="customize-meeting-invitations"></a>모임 초대의 사용자 지정

조직의 요구 사항에 맞게 팀 모임 초대를 사용자 지정할 수 있습니다. 조직의 로고를 추가 하 고, 지원 웹사이트 링크, 법적 고 지 사항, 텍스트 전용 바닥글 등의 유용한 정보를 포함할 수 있습니다.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>모임 초대에 대 한 로고 만들기 팁  

1. 너비가 188 픽셀을 초과 하지 않는 이미지를 만들 수 있습니다 (크기는 매우 작아서 약 30 픽셀).
2. 이미지를 JPG 또는 PNG 형식으로 저장 합니다.
3. 초대를 받는 모든 사람이 액세스할 수 있는 위치 (예: 공용 웹 사이트)에 이미지를 저장 합니다.

    이제 모임 초대에 추가할 수 있습니다. 다음 단계를 참조 하세요.

### <a name="customize-your-meeting-invitations"></a>모임 초대 사용자 지정

![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **모임** > **모임 설정**으로 이동 합니다.
2. **전자 메일 초대장**에서 다음을 수행 합니다.

    ![사용자 지정할 수 있는 모임 초대 설정의 스크린샷](media/meeting-settings-invitation.png "팀 모임에 대해 사용자 지정할 수 있는 모임 초대 설정의 스크린샷")

    - **로고 URL** 로고가 저장 된 위치에 URL을 입력 합니다.
    - **올바른 URL** 조직에 다른 사용자가 관심을 가질 수 있도록 법률 웹 사이트가 있는 경우 여기에 URL을 입력 합니다.
    - **도움말 URL** 조직에 문제가 발생 하는 경우 사용자에 게 보낼 지원 웹 사이트가 있는 경우 여기에 URL을 입력 합니다.
    - **바닥글** 바닥글로 포함할 텍스트를 입력 합니다.
3. 변경 내용이 전파 되는 시간을 기다립니다. 그런 다음 팀 회의 일정을 계획 하 여 모임 초대의 모양을 확인할 수 있습니다.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>팀 모임에 대 한 실시간 미디어 트래픽을 처리 하는 방법을 설정 합니다.

<a name="bknetwork"> </a>

[Qos (](qos-in-teams.md) 서비스 품질)를 사용 하 여 네트워크 트래픽의 우선 순위를 지정 하는 경우 qos 마커를 사용 하도록 설정 하 고 각 미디어 트래픽 유형에 대해 포트 범위를 설정할 수 있습니다. 여러 트래픽 유형에 대해 포트 범위를 설정 하는 것은 실시간 미디어를 처리 하는 단계 중 하나입니다. [팀에서 QoS (서비스 품질)](qos-in-teams.md) 를 자세히 확인 하세요.

> [!IMPORTANT]
> Microsoft 팀 서비스에 대 한 Microsoft 팀 관리 센터에서 QoS를 사용 하거나 설정을 변경 하는 경우 팀에서 QoS에 대 한 변경 내용을 완벽 하 게 구현 하려면 [모든 사용자 장치](QoS-in-Teams-clients.md) 및 모든 내부 네트워크 장치에 일치 하는 설정을 적용 해야 할 수도 있습니다.

 ![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **모임** > **모임 설정**으로 이동 합니다.
2. **네트워크**에서 다음을 수행 합니다.

    ![관리 센터의 모임에 대 한 네트워크 설정 스크린샷](media/meeting-settings-network.png "Microsoft 팀 관리 센터의 팀 모임에 대 한 네트워크 설정 스크린샷")

    - QoS에 DSCP 표시를 사용 하는 것을 허용 하려면 **실시간 미디어 트래픽에 qos (서비스 품질) 마커를 삽입**하도록 설정 합니다. 마커를 사용 하는 옵션만 사용할 수 있습니다. 각 트래픽 유형에 대해 사용자 지정 표식을 설정할 수 없습니다. DSCP 마커에 대 한 자세한 내용은 [QoS 구현 방법 선택을](QoS-in-Teams.md#select-a-qos-implementation-method) 참조 하세요.
    > [!NOTE] 
    > **실시간 미디어 트래픽에 대 한 QoS (서비스 품질) 마커** 를 설정 하면 UDP 포트 3479 (오디오), 3480 (비디오) 및 3481 (공유)로 전송 릴레이와 통신할 수 있습니다.
    - 포트 범위를 지정 하려면 **각 실시간 미디어 트래픽 형식에 대 한 포트 범위 선택**옆의 **포트 범위 지정**을 선택한 다음 오디오, 비디오 및 화면 공유를 위한 시작 및 종료 포트를 입력 합니다. QoS를 구현 하려면이 옵션을 선택 해야 합니다.
    > [!IMPORTANT]
    > **사용 가능한 포트를 자동으로 사용**을 선택 하는 경우 1024 및 65535 사이의 사용 가능한 포트를 사용 합니다. QoS를 구현 하지 않는 경우에만이 옵션을 사용 합니다.
    >
    > 너무 좁은 포트 범위를 선택 하면 통화 손실이 발생 하 고 통화 품질이 저하 될 수 있습니다. 아래 권장 사항은 최소가입니다.

환경에서 사용할 포트 범위가 확실 하지 않은 경우 다음 설정을 사용 하는 것이 좋습니다. 자세한 내용은 [Microsoft 팀에서 QoS (서비스 품질) 구현을](QoS-in-Teams.md)참조 하세요. 이는 필요한 DSCP 표식 및 제안 된 적절 한 미디어 포트 범위를 팀과 Express에서 모두 사용 하는 것입니다.

_포트 범위 및 DSCP 표식_

미디어 트래픽 형식| 클라이언트 원본 포트 범위\* |프로토콜별|DSCP 값|DSCP 클래스|
|:---             |:---                         |:---    |:---      |:---      |
|오디오            | 50000 – 50019               |TCP/UDP |46        |전달 발송 (EF)|
|비디오만            | 50,020–50,039               |TCP/UDP |34        |전달 보장 (AF41)|
|응용 프로그램/화면 공유| 50,040–50,059      |TCP/UDP |awg        |전달 보장 (AF21)|
| | | | |

\*지정 하는 포트 범위는 겹칠 수 없으며 서로 옆에 있어야 합니다.

특정 기간 동안 QoS를 사용 하는 경우에는 이러한 세 가지 작업 부하 각각에 대 한 사용 정보가 필요 하며, 사용자는 해당 요구 사항에 따라 변경할 내용을 선택할 수 있습니다. [통화 음질 대시보드가](turning-on-and-using-call-quality-dashboard.md) 도움이 됩니다.
