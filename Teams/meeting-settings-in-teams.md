---
title: 모임 설정 관리
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: high
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
ms.openlocfilehash: 4ff1118818ac22040e9bf9f8c44288991e24d8b0
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205308"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Microsoft Teams에서의 모임 설정 관리

관리자는 Teams 모임 설정을 사용하여 익명 사용자가 Teams 모임에 참여하고 모임 초대를 사용자 지정하고 QoS(서비스 품질)을 활성화하고 실시간 트래픽에 대한 포트 범위를 설정할 수 있습니다. 이 설정은 사용자가 조직에서 예약하는 모든 Teams 모임에 적용됩니다. Microsoft Teams 관리 센터의 **모임** > **모임 설정** 에서 이러한 설정을 관리합니다.

이제 관리자는 이끌이별 정책 설정을 통해 특정 사용자 또는 사용자 그룹이 익명 사용자가 구성한 모임에 참가하도록 허용할지 여부를 제어할 수 있습니다. 이끌이별 및 조직 차원의 정책 설정은 모두 익명 조인을 제어하고 더 제한적으로 적용됩니다.

> [!Important]
 > **-DisableAnonymousJoin** 은 조직 전체의 정책 설정입니다. 앞으로는 더 이상 사용되지 않을 것이며 이후에는 이끌이별 정책이 익명 조인을 제어하는 유일한 방법이 될 것입니다.

## <a name="allow-anonymous-users-to-join-meetings"></a>익명 사용자가 모임에 참가하도록 허용

익명 참가를 사용하면 누구나 모임 초대의 링크를 클릭하여 익명 사용자로 모임에 참여할 수 있습니다. 자세한 내용은 [Teams 계정 없이 모임에 참가](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)를 참조하세요. 두 가지 다른 정책 설정을 사용하여 조직 수준에서 또는 모임 이끌이별로 모임에 참가하는 익명 사용자의 기능을 제어할 수 있습니다.

 ### <a name="using-the-microsoft-teams-admin-center-to-configure-organization-wide-policy"></a>Microsoft Teams 관리 센터를 사용하여 조직 전체 정책 구성

이러한 변경을 수행하려면 Teams 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.

1. [Teams 관리 센터](https://admin.teams.microsoft.net)로 이동합니다.

2. 왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.

3. **참가자** 아래에서 **익명 사용자가 모임에 참가할 수 있습니다** 를 설정합니다.

    ![관리 센터에서 모임에 대한 참가자 설정 스크린샷.](media/meeting-settings-participants.png "Microsoft Teams 관리 센터에서 Teams 모임에 대한 참가자 설정의 스크린샷")

> [!CAUTION]
> 익명 사용자가 조직의 사용자가 예약한 모임에 참여하지 못하게 하려면 이 설정을 해제합니다.

### <a name="using-powershell-to-configure-per-organizer-policy"></a>PowerShell을 사용하여 이끌이별 정책 구성

이제 관리자는 특정 사용자 또는 사용자 그룹이 익명의 사용자가 자신이 주최하는 모임에 참여하도록 허용할지 여부를 제어할 수 있습니다. 이 새로운 이끌이별 정책은 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)의 **-AllowAnonymousUsersToJoinMeeting** 매개변수를 사용하여 제어됩니다. Teams PowerShell 버전 2.6.0 이상과 함께 제공됩니다.

조직 전체 또는 조직자별 정책을 사용하여 익명 가입을 관리할 수 있습니다. 이끌이별 정책을 구현하는 것이 좋습니다. 조직 전체의 정책 설정은 앞으로 더 이상 사용되지 않으며 이끌이별 정책은 익명 가입을 제어하는 ​​유일한 방법이 될 것입니다.

조직 전체 및 조직자별 정책 모두 익명 가입을 제어하므로 보다 제한적인 설정이 효과적입니다. 예를 들어 조직 수준에서 익명 가입을 허용하지 않으면 조직자별 정책에 대해 구성한 내용에 관계없이 유효한 정책이 됩니다. 따라서 익명 사용자가 모임에 참가할 수 있도록 하려면 다음 값을 설정하여 익명 참가를 허용하도록 두 정책을 모두 구성해야 합니다.

- **-DisableAnonymousJoin** 이 **$false** 로 설정됨
- **-AllowAnonymousUsersToJoinMeeting** 이 **$true** 로 설정됨

다른 값 조합은 익명 사용자가 모임에 참여하지 못하도록 합니다.
> [!NOTE]
> 조직별로 익명 가입이 해제된 조직에 대해 조직자별 정책을 사용하려면 관리자가 정책을 생성한 다음 사용자에게 할당해야 합니다. 방법을 알아보려면 [Microsoft Teams에서 모임 정책 관리](/microsoftteams/meeting-policies-overview)를 참조하세요.


## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a>익명 사용자가 모임에서 앱과 상호 작용할 수 있도록 허용

이제 익명 사용자는 사용자 수준 전역 기본 사용 권한 정책을 상속합니다. 그러면 익명 사용자가 사용자 수준 사용 권한 정책에서 앱을 사용하도록 설정한 동안에는 익명 사용자가 Teams 모임에서 앱과 상호 작용할 수 있습니다. 익명 사용자는 모임에서 이미 사용 가능한 앱만 상호 작용할 수 있으며 이러한 앱을 획득 및/또는 관리할 수 없습니다. 

> [!IMPORTANT]
> 기본적으로 익명 사용자가 모임에서 앱과 상호 작용할 수 있도록 허용하는 설정이 사용됩니다.

 **Microsoft Teams 관리 센터 사용**

이 설정에 액세스하려면 Teams 서비스 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.

1. 관리 센터로 이동합니다.

2. 왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.

3. **참가자** 에서 **익명 사용자가 모임의 앱과 상호 작용 가능** 에 대한 설정을 변경할 수 있습니다.

> [!CAUTION]
> 익명 사용자가 조직의 사용자가 예약한 모임에 앱과 상호 작용하지 못하게 하려면 이 설정을 해제합니다.

## <a name="customize-meeting-invitations"></a>모임 초대장의 사용자 지정

조직의 필요에 따라 Teams 모임 초대를 사용자 정의할 수 있습니다. 조직의 로고를 추가하고 지원 웹 사이트 링크 및 법적 고지 사항, 텍스트 전용 바닥글과 같은 유용한 정보를 포함할 수 있습니다.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>모임 초대장에 대한 로고 만들기 팁  

1. 너비가 188픽셀, 높이가 30픽셀(상당히 작음) 이하인 이미지를 만듭니다.
2. 이미지를 JPG 또는 PNG 형식으로 저장합니다.
3. 초대장을 받은 모든 사용자가 액세스할 수 있는 위치(예: 공용 웹사이트)에 이미지를 저장합니다.

    이제 모임 초대장에 추가할 수 있습니다. 다음 단계를 참조하세요.

### <a name="customize-your-meeting-invitations"></a>모임 초대장의 사용자 지정

 **Microsoft Teams 관리 센터 사용**

1. 관리 센터로 이동합니다.
2. 왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.
3. **전자 메일 초대장** 에서 다음을 수행합니다.

    ![사용자 지정할 수 있는 모임 초대장 설정 스크린샷.](media/meeting-settings-invitation.png "Teams 모임에 대해 사용자 지정할 수 있는 모임 초대장 설정의 스크린샷")

    - **로고 URL** 로고가 저장된 URL을 입력합니다.
    - **법률 정보 URL** 법률적인 우려에 대해 사용자의 방문을 원하는 법률 정보 웹사이트를 조직이 보유한 경우 여기에 URL을 입력합니다.
    - **도움말 URL** 사용자에게 문제가 발생했을 때 사용자의 방문을 원하는 지원 웹사이트를 조직이 보유한 경우 여기에 URL을 입력합니다.
    - **바닥글** 바닥글에 포함할 텍스트를 입력합니다.
4. **초대장 미리보기** 를 클릭하여 모임 초대장의 미리보기를 확인합니다.
5. 모두 마쳤으면 **저장** 을 클릭합니다.
6. 변경 사항을 적용하려면 1시간 정도 기다립니다. 그런 다음 Teams 모임을 예약하여 모임 초대장 모양을 확인할 수 있습니다.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Teams 모임에 대한 실시간 미디어 트래픽 처리 방법 설정

<a name="bknetwork"> </a>

QoS(서비스 품질)를 사용하여 네트워크 트래픽의 우선 순위를 지정하는 경우 QoS 마커를 사용하도록 설정하고 각 미디어 트래픽 유형에 대해 포트 범위를 설정할 수 있습니다. 다양한 트래픽 유형에 대한 포트 범위를 설정하는 것은 실시간 미디어를 처리하는 한 단계입니다. 자세한 내용은 [Teams의 QoS(서비스 품질)](qos-in-teams.md)를 참조하세요.

> [!IMPORTANT]
> Apple 기반 시스템: Apple 기반 장치가 실제로 DSCP 값을 설정하는 위치를 아는 유일한 인스턴스는 다음 조건을 모두 충족하는 경우입니다.
> - iOS.
> - WiFi 네트워크.
> - Cisco 스위치.
> - 네트워크 관리자가 승인된 목록에 앱을 추가함.
>
> Android 기반 시스템: 알려진 제한 사항이 없습니다.
>
> Teams 서비스에 대해 Microsoft Teams 관리 센터에서 QoS를 활성화하거나 설정을 변경하는 경우, Teams에서 QoS에 대한 변경 사항을 완전히 구현하려면 모든 네트워크 장치 및 [모든 사용자 장치에 일치하는 설정을 적용](QoS-in-Teams-clients.md)해야 합니다.

  **Microsoft Teams 관리 센터 사용**
1. 관리 센터로 이동합니다.
2. 왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.
3. **네트워크** 에서 다음을 수행합니다.

    ![관리 센터에서 모임에 대한 네트워크 설정의 스크린샷.](media/meeting-settings-network.png "Microsoft Teams 관리 센터에서 Teams 모임에 대한 네트워크 설정의 스크린샷")

    - DSCP 마커를 QoS에 사용하려면 **실시간 미디어 트래픽에 대한 QoS(서비스 품질) 마커** 를 설정합니다. 마커의 사용 옵션만 선택할 수 있습니다. 각 트래픽 유형에 대해 사용자 지정 마커를 설정할 수 없습니다. DSCP 마커에 대한 자세한 내용은 [QoS 구현 방법 선택](QoS-in-Teams.md#select-a-qos-implementation-method)을 참조하세요.

        > [!IMPORTANT]
        > QoS를 사용하도록 설정하는 작업은 클라이언트에서 나가는 패킷에 태그를 지정하는 엔드포인트에서만 수행합니다. 하지만 들어오는 트래픽에 대한 모든 내부 네트워크 장치에도 일치하는 QoS 규칙을 적용하는 것이 좋습니다.
        
        > [!NOTE]
        > DSCP 태그 지정은 일반적으로 원본 포트를 통해 수행되며 UDP 트래픽은 기본적으로 대상 포트가 3478인 전송 릴레이로 라우팅됩니다. 회사에서 대상 포트에 태그를 지정해야 하는 경우 지원 팀에 문의하여 UDP 포트 3479(오디오), 3480(비디오) 및 3481(공유)가 있는 전송 릴레이로의 통신을 사용 설정하세요.
    - 포트 범위를 지정하려면 **각 유형의 실시간 미디어 트래픽에 대한 포트 범위 선택** 옆에 있는 **포트 범위 지정** 을 선택한 다음 오디오, 비디오 및 화면 공유를 위한 시작 및 종료 포트를 입력합니다. QoS를 구현하려면 이 옵션을 선택해야 합니다. 
        > [!Note]
        > **실시간 트래픽에 대한 QoS(서비스 품질) 표식** 이 켜져 있는 경우 포트 설정을 관리해야 합니다. 해당 설정은 자동으로 관리되지 않습니다.
        
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

\* 할당하는 포트 범위는 겹칠 수 없으며 서로 근접해 있어야 합니다.

QoS를 한동안 사용하고 나면 이 세 가지 작업 각각의 수요에 대한 사용량 정보가 제공되며 특정 요구에 따라 변경할 사항을 선택할 수 있습니다. [통화 품질 대시보드](turning-on-and-using-call-quality-dashboard.md)가 도움이 될 것입니다.
