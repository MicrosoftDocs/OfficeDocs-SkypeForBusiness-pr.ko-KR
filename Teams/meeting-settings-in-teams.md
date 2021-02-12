---
title: 모임 설정 관리
author: cichur
ms.author: v-cichur
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
- m365initiative-meetings
description: 사용자가 조직에서 예약하는 모든 Teams 모임 설정을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: d3301c8232fda2133e77f973ca0efbc13cfa571d
ms.sourcegitcommit: c6b999226294aeea98dafa9ef5f0bd256fcb6a0c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2021
ms.locfileid: "49903569"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Microsoft Teams에서의 모임 설정 관리

관리자는 Teams 모임 설정을 사용하여 익명 사용자가 Teams 모임에 참여하고 모임 초대를 사용자 지정하고 QoS(서비스 품질)을 활성화하고 실시간 트래픽에 대한 포트 범위를 설정할 수 있습니다. 이 설정은 사용자가 조직에서 예약하는 모든 Teams 모임에 적용됩니다. Microsoft Teams 관리 센터의 **모임** > **모임 설정** 에서 이러한 설정을 관리합니다.

## <a name="allow-anonymous-users-to-join-meetings"></a>익명 사용자가 모임에 참가하도록 허용

익명 참가를 사용하면 누구나 모임 초대의 링크를 클릭하여 익명 사용자로 모임에 참여할 수 있습니다. 자세한 내용은 [Teams 계정 없이 모임에 참가](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)를 참조하세요.

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

이러한 변경을 위해 Teams 서비스 관리자 되어야 합니다. Teams [관리자 역할을 사용하여 Teams를](https://docs.microsoft.com/microsoftteams/using-admin-roles) 관리하여 관리자 역할 및 사용 권한을 부여하는 방법을 참조하세요.

1. 관리 센터로 이동

2. 왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.

3. **참가자** 아래에서 **익명 사용자가 모임에 참가할 수 있습니다** 를 설정합니다.

    ![관리 센터에서 모임에 대한 참가자 설정의 스크린샷](media/meeting-settings-participants.png "Microsoft Teams 관리 센터에서 Teams 모임에 대한 참가자 설정의 스크린샷")

> [!CAUTION]
> 익명 사용자가 조직의 사용자가 예약한 모임에 참여하지 못하게 하려면 이 설정을 해제합니다.

## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a>익명 사용자가 모임에서 앱과 상호 작용할 수 있도록 허용

이제 익명 사용자는 사용자 수준 전역 기본 사용 권한 정책을 상속합니다. 그러면 익명 사용자가 사용자 수준 사용 권한 정책이 앱을 사용하도록 설정한 경우 익명 사용자가 Teams 모임에서 앱과 상호 작용할 수 있습니다. 익명 사용자는 모임에서 이미 사용할 수 있는 앱과만 상호 작용할 수 있으며 이러한 앱을 획득 및/또는 관리할 수 없습니다. 

> [!IMPORTANT]
> 기본적으로 익명 사용자가 모임에서 앱과 상호 작용할 수 있도록 허용하는 설정이 사용됩니다.

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

이 설정에 액세스하려면 Teams 서비스 관리자 되어야 합니다. Teams [관리자 역할을 사용하여 Teams를](https://docs.microsoft.com/microsoftteams/using-admin-roles) 관리하여 관리자 역할 및 사용 권한을 부여하는 방법을 참조하세요.

1. 관리 센터로 이동

2. 왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.

3. 참가자 **아래에서** 익명 사용자에 대한 **설정은 모임에서** 앱과 상호 작용할 수 있습니다.

> [!CAUTION]
> 익명 사용자가 조직의 사용자가 예약한 모임에서 앱과 상호 작용하지 못하게 하려는 경우 이 설정을 해제합니다.

## <a name="customize-meeting-invitations"></a>모임 초대장의 사용자 지정

조직의 요구에 맞게 Teams 모임 초대장을 사용자 지정할 수 있습니다. 조직의 로고를 추가하고 지원 웹 사이트에 대한 링크와 법적 고지 사항 및 텍스트 전용 바닥글과 같은 유용한 정보를 포함할 수 있습니다.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>모임 초대장에 대한 로고 만들기 팁  

1. 너비가 188픽셀, 높이가 30픽셀(상당히 작음) 이하인 이미지를 만듭니다.
2. 이미지를 JPG 또는 PNG 형식으로 저장합니다.
3. 초대장을 받은 모든 사용자가 액세스할 수 있는 위치(예: 공용 웹사이트)에 이미지를 저장합니다.

    이제 이것을 모임 초대장에 추가할 수 있습니다. 다음 단계를 참조하세요.

### <a name="customize-your-meeting-invitations"></a>모임 초대장의 사용자 지정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 관리 센터로 이동
2. 왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.
3. **전자 메일 초대장** 에서 다음을 수행합니다.

    ![사용자 지정할 수 있는 모임 초대장 설정의 스크린샷](media/meeting-settings-invitation.png "Teams 모임에 대해 사용자 지정할 수 있는 모임 초대장 설정의 스크린샷")

    - **로고 URL** 로고가 저장된 URL을 입력합니다.
    - **법률 정보 URL** 법률적인 우려에 대해 사용자의 방문을 원하는 법률 정보 웹사이트를 조직이 보유한 경우 여기에 URL을 입력합니다.
    - **도움말 URL** 사용자에게 문제가 발생했을 때 사용자의 방문을 원하는 지원 웹사이트를 조직이 보유한 경우 여기에 URL을 입력합니다.
    - **바닥글** 바닥글에 포함할 텍스트를 입력합니다.
4. **초대장 미리보기** 를 클릭하여 모임 초대장의 미리보기를 확인합니다.
5. 모두 마쳤으면 **저장** 을 클릭합니다.
6. 변경 사항을 적용하려면 1시간 정도 기다립니다. 그런 다음 Teams 모임을 예약하여 모임 초대장 모양을 확인할 수 있습니다.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Teams 모임에 대한 실시간 미디어 트래픽 처리 방법 설정

<a name="bknetwork"> </a>

QoS(서비스 품질)를 사용하여 네트워크 트래픽의 우선 순위를 지정하는 경우 QoS 마커를 사용하도록 설정하고 각 유형의 미디어 트래픽에 대한 포트 범위를 설정할 수 있습니다. 다양한 트래픽 유형에 대한 포트 범위를 설정하는 것은 실시간 미디어를 처리하는 한 단계입니다. 자세한 내용은 [Teams의 QoS(서비스 품질)](qos-in-teams.md)를 참조하세요.

> [!IMPORTANT]
> Teams 서비스에 대한 Microsoft Teams 관리 센터에서 QoS를 사용하도록 설정하거나 설정을 [](QoS-in-Teams-clients.md) 변경하는 경우 Teams에서 QoS에 대한 변경 내용을 완전히 구현하려면 모든 사용자 장치 및 모든 내부 네트워크 장치에 일치하는 설정을 적용해야 합니다.

 ![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**
1. 관리 센터로 이동
2. 왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.
3. **네트워크** 에서 다음을 수행합니다.

    ![관리 센터에서 모임에 대한 네트워크 설정의 스크린샷](media/meeting-settings-network.png "Microsoft Teams 관리 센터에서 Teams 모임에 대한 네트워크 설정의 스크린샷")

    - DSCP 마커를 QoS에 사용하려면 **실시간 미디어 트래픽에 대한 QoS(서비스 품질) 마커 삽입** 을 설정합니다. 마커의 사용 옵션만 선택할 수 있습니다. 각 트래픽 유형에 대해 사용자 지정 마커를 설정할 수 없습니다. DSCP 마커에 대한 자세한 내용은 [QoS 구현 방법 선택](QoS-in-Teams.md#select-a-qos-implementation-method)을 참조하세요.
        > [!NOTE]
        > DSCP 태그 지정은 일반적으로 원본 포트를 통해 수행됩니다. UDP 트래픽은 기본적으로 대상 포트가 3478인 Transport Relay로 라우팅됩니다. 회사에서 대상 포트에 태그를 지정해야 하는 경우 지원에 문의하여 UDP 포트 3479(오디오), 3480(비디오) 및 3481(공유)을 사용하여 전송 릴레이와 통신할 수 있도록 합니다.
    - 포트 범위를 지정하려면 **각 유형의 실시간 미디어 트래픽에 대한 포트 범위 선택** 옆에 있는 **포트 범위 지정** 을 선택한 다음 오디오, 비디오 및 화면 공유를 위한 시작 및 종료 포트를 입력합니다. QoS를 구현하려면 이 옵션을 선택해야 합니다. 
        > [!Note]
        > 실시간 미디어 트래픽에 **대한 QoS(서비스 품질)** 마커가 설정되어 있는 경우 포트 설정을 관리해야 합니다. 자동으로 관리되지 않습니다.
        
        > [!IMPORTANT]
        > **사용 가능한 포트 자동 사용** 을 선택하면 1024에서 65535 사이의 사용 가능한 포트가 사용됩니다. QoS를 구현하지 않는 경우에만 이 옵션을 사용합니다.
        >
        > 포트 범위를 너무 좁게 선택하면 통화 손실이 발생하고 통화 품질이 떨어집니다. 아래의 권장 사항이 최소 범위입니다.

사용자 환경에서 어떤 포트 범위를 사용해야 하는지 잘 모르는 경우 다음 설정을 사용하는 것이 좋습니다. 자세한 내용은 [Microsoft Teams에서 QoS(서비스 품질) 구현](QoS-in-Teams.md)을 참조하세요. 이는 필수 DSCP 마킹 및 Teams와 ExpressRoute에서 사용하는 해당 미디어 포트 범위입니다.

### <a name="port-ranges-and-dscp-markings"></a>포트 범위 및 DSCP 마킹

미디어 트래픽 유형| 클라이언트 원본 포트 범위 \* |프로토콜|DSCP 값|DSCP 클래스|
|:---             |:---                         |:---    |:---      |:---      |
|오디오            | 50,000~50,019               |TCP/UDP |46        |Expedited Forwarding(EF)|
|비디오            | 50,020~50,039               |TCP/UDP |34        |Assured Forwarding(AF41)|
|응용 프로그램/화면 공유| 50,040~50,059      |TCP/UDP |18        |Assured Forwarding(AF21)|
| | | | |

\* 할당한 포트 범위는 겹칠 수 없습니다. 서로 인접해야 합니다.

QoS를 한동안 사용하고 나면 이 세 가지 작업 각각의 수요에 대한 사용량 정보가 제공되며 특정 요구에 따라 변경할 사항을 선택할 수 있습니다. [통화 품질 대시보드](turning-on-and-using-call-quality-dashboard.md)가 여기에 도움이 됩니다.
