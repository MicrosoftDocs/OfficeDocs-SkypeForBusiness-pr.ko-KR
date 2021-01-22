---
title: 모임 정책 관리
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Teams에서 모임 정책 설정을 관리하고 이를 사용하여 사용자가 예약한 모임에 모임 참가자가 사용할 수 있는 기능을 제어하는 방법을 배워야 합니다.
ms.openlocfilehash: 2eef5969ea054b8c8ca6d702189f05b1eaa46c65
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918914"
---
# <a name="manage-meeting-policies-in-teams"></a>Teams에서 모임 정책 관리

::: zone target="docs"
모임 정책은 조직에서 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다. 자동으로 생성되거나 사용자 지정 정책을 만들고 할당하는 전역(전체 기본) 정책을 사용할 수 있습니다. Microsoft Teams 관리 센터에서 또는 [PowerShell을](teams-powershell-overview.md)사용하여 모임 정책을 관리합니다.

> [!NOTE]
> 역할을 사용하여 모임 발표자 및 참석자 권한을 관리하는 자세한 내용은 Teams 모임의 역할을 [참조하세요.](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)

다음과 같은 방법으로 정책을 구현할 수 있습니다. 이 정책은 모임이 시작되기 전, 모임 중 또는 모임 후에 사용자의 모임 경험에 영향을 미치게 됩니다.

|구현 유형  |설명  |
|---------|---------|
|이끌이당    |이끌이당 정책을 구현할 때 모든 모임 참가자는 이끌이의 정책을 상속합니다. 예를 들어 **사용자를** 자동으로 인정하는 것은 이끌이 정책으로, 사용자가 직접 모임에 참가할지 아니면 정책이 할당된 사용자가 예약한 모임을 대기실에서 대기할지 여부를 제어합니다.          |
|사용자당    |사용자당 정책을 구현하는 경우 이끌이 및/또는 모임 참가자에 대한 특정 기능을 제한하기 위해 사용자당 정책만 적용됩니다. 예를 들어 **채널에서 지금 Meet 허용은** 사용자당 정책입니다.     |
|이끌이 및 사용자당     |이끌이 및 사용자당 정책의 조합을 구현할 때 특정 기능은 해당 정책 및 이끌이의 정책에 따라 모임 참가자에 대해 제한됩니다. 예를 들어 클라우드 **기록 허용은** 이끌이 및 사용자당 정책입니다. 사용자가 녹음/녹화를 시작하고 중지할 수 있도록 이 설정을 켜면 됩니다.

전역 정책에서 설정을 편집하거나 하나 이상의 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않는 한 사용자는 전역 정책을 얻게 됩니다.

> [!NOTE]
> 사용자가 오디오 회의 라이선스를 사용하도록 설정하거나 사용자가 오디오 회의를 허용하는 경우 모임 세부 정보 단추를 사용할 수 있습니다. 그렇지 않은 경우 모임 세부 정보를 사용할 수 없습니다.

## <a name="create-a-custom-meeting-policy"></a>사용자 지정 모임 정책 만들기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 모임 모임  >  **정책으로 이동하세요.**
2. **추가** 를 선택합니다.
3. 정책의 이름과 설명을 입력합니다. 이름은 특수 문자가 포함될 수 없으며 64자를 초과할 수 없습니다.
4. 원하는 설정을 선택합니다.
5. 저장을 **선택합니다.**

예를 들어, 사용자 수가 많은데 모임에 필요한 대역폭의 양을 제한하려고 한다고 가정해 보겠습니다. "제한된 대역폭"이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용하지 않도록 설정합니다.

**오디오 및 비디오** 에서:

- 클라우드 녹음/녹화 허용을 끕니다.
- IP 비디오 허용을 끕니다.

**콘텐츠 공유** 에서:

- 화면 공유 모드를 사용하지 않도록 설정합니다.
- 화이트보드 허용을 끕니다.
- 공유 노트 허용을 끕니다.

그 다음 사용자에게 정책을 할당합니다.

## <a name="edit-a-meeting-policy"></a>모임 정책 편집

전역 정책 및 만드는 모든 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 모임 모임  >  **정책으로 이동하세요.**
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 편집을 **선택합니다.**
3. 여기에서 원하는 내용을 변경합니다.
4. 저장을 **선택합니다.**

> [!NOTE]
> 한 번의 모임 정책만 사용자에게 할당할 수 있습니다.

## <a name="assign-a-meeting-policy-to-users"></a>사용자에게 모임 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> 사용자가 할당된 경우 정책을 삭제할 수 없습니다. 먼저 영향을 받는 모든 사용자에게 다른 정책을 할당한 다음 원래 정책을 삭제할 수 있습니다.

## <a name="meeting-policy-settings"></a>모임 정책 설정

모임 정책 페이지에서 기존  정책을 선택하거나  추가를 선택하여 새 정책을 추가하는 경우 다음에 대한 설정을 구성할 수 있습니다.

- [일반](#meeting-policy-settings---general)
- [오디오 & 비디오](#meeting-policy-settings---audio--video)
- [콘텐츠 공유](#meeting-policy-settings---content-sharing)
- [게스트를 & 참가자](#meeting-policy-settings---participants--guests)

::: zone-end

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>모임 정책 설정 - 일반

- [채널에서 지금 Meet 허용](#allow-meet-now-in-channels)
- [Outlook 추가 기능 허용](#allow-the-outlook-add-in)
- [채널 모임 참석 허용](#allow-channel-meeting-scheduling)
- [비공개 모임을 허용합니다.](#allow-scheduling-private-meetings)
- [비공개 모임에서 모임 허용](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a>채널에서 지금 만나기 허용

모임 **허용은** 사용자당 정책으로, 모임이 시작되기 전에 적용됩니다. 이 설정은 사용자가 Teams 채널에서 계획되지 않은 모임을 시작할 수 있는지 여부를 제어합니다. 이 설정을 켜면 사용자는 모임  단추를 선택하여 계획되지 않은 모임을 시작하거나 채널에서 모임을 예약할 수 있습니다. 기본값은 True입니다.

![메시지 아래의 Meet Now 아이콘을 보여주는 스크린샷](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a>Outlook 추가 기능 허용

이는 사용자당 정책으로, 모임이 시작되기 전에 적용됩니다. 이 설정은 Outlook(Windows, Mac, 웹 및 모바일) 내에서 Teams 모임을 예약할 수 있는지 여부를 제어합니다.

![새 모임을 예약하는 기능을 보여주는 스크린샷](media/meeting-policies-outlook-add-in.png)

이 기능을 해제하면 사용자가 예약할 수 없습니다. Outlook에서 새 모임을 만들 때 Teams 모임을 합니다. 예를 들어 Windows용 Outlook에서는 새 **Teams** 모임 옵션이 리본에 표시되지 않습니다.

### <a name="allow-channel-meeting-scheduling"></a>채널 모임 참석 허용

기존 AllowChannelMeetingScheduling 정책을 사용하여 팀 채널 일정에서 만들 수 있는 이벤트 유형을 제어합니다. 이는 사용자당 정책으로, 모임이 시작되기 전에 적용됩니다. 이 설정은 사용자가 Teams 채널에서 모임을 예약할 수 있는지 여부를 제어합니다. 기본적으로 이 설정은 켜져 있습니다.

이 정책이 해제되어 있는 경우 사용자는 새 채널 모임을 만들 수 없습니다. 그러나 이벤트 이끌이가 기존 채널 모임을 편집할 수 있습니다.

모임 예약이 비활성화됩니다.

 ![Teams에서 모임 예약 옵션을 보여주는 스크린샷](media/schedule-meeting-option.png)

채널 선택이 비활성화되어 있습니다.

![모임을 예약할 채널을 선택하는 일정 옵션입니다.](media/meeting-policies-select-a-channel-to-meet-in.png)

채널 게시물 페이지에서 다음 기능이 비활성화됩니다.

- **채널 회신** 작성 상자의 모임 예약 단추
  ![모임 예약 단추 회신 작성 상자](media/schedule-meeting-disabled-in-chat2.png)
  
- **채널 헤더의** 모임 예약 단추
  ![채널 헤더의 모임 예약 단추](media/schedule-now-in-header.png)

채널 일정에서:

- **채널 일정 헤더에** 새 이벤트 추가 단추가 비활성화됩니다.
  ![채널 일정 머리더의 단추를 사용할 수 없습니다.](media/add-new-event-disabled.png)

- 사용자는 채널 일정에서 시간 블록을 끌어서 선택하여 채널 모임을 만들 수 없습니다.

- 사용자는 바로 가기 키를 사용하여 채널 일정에서 모임을 만들 수 없습니다.

관리 센터에서:

채널 일정 앱은 앱 사용 권한 정책 페이지의 **Microsoft** 앱 섹션에 표시됩니다.

 ![Teams 관리 센터의 앱 사용 권한 정책](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a>비공개 모임을 허용합니다.

이는 사용자당 정책으로, 모임이 시작되기 전에 적용됩니다. 이 설정은 사용자가 Teams에서 비공개 모임을 예약할 수 있는지 여부를 제어합니다. 모임은 팀의 채널에 게시되지 않은 경우 비공개입니다.

비공개 모임 예약  및 채널 **모임** 예약 허용을 해제하면 Teams의 사용자에  대해 필요한 참석자  추가 및 채널 추가 옵션이 비활성화됩니다. 기본적으로 이 설정은 켜져 있습니다.

### <a name="allow-meet-now-in-private-meetings"></a>비공개 모임에서 모임 허용

이는 사용자당 정책으로, 모임이 시작되기 전에 적용됩니다. 이 설정은 사용자가 계획되지 않은 비공개 모임을 시작할 수 있는지 여부를 제어합니다.  기본적으로 이 설정은 켜져 있습니다.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>모임 정책 설정 - 오디오 & 비디오

- [전사 허용](#allow-transcription)
- [클라우드 녹음/녹화 허용](#allow-cloud-recording)
- [IP 오디오 모드](#mode-for-ip-audio)
- [IP 비디오 모드](#mode-for-ip-video)
- [IP 비디오 허용](#allow-ip-video)
- [미디어 비트 속도(KBS)](#media-bit-rate-kbs)

### <a name="allow-transcription"></a>전사 허용

이끌이 및 사용자당 정책의 조합입니다. 이 설정은 모임 녹화를 재생하는 동안 캡션 및 전사 기능을 사용할 수 있는지 여부를 제어합니다. 이 기능을 해제하면  모임 녹화를 재생하는 동안 검색 및 **CC** 옵션을 사용할 수 없습니다. 기록을 시작한 사람은 기록도 포함하기 위해 이 설정을 켜야 합니다.

기록된 모임에 대한 전사는 현재 Teams의 언어가 영어로 설정된 사용자와 모임에서 영어를 사용할 때만 지원됩니다.

![모임의 전사 옵션](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>클라우드 기록 허용

이 정책은 사용자당 정책에서 제어됩니다. 이 설정은 사용자가 기록할 수 있는지 여부를 제어합니다. 특정 정책 설정이 켜져 있으며 이끌이와 동일한 조직의 인증된 사용자인 경우 모임 이끌이 또는 다른 모임 참가자가 기록을 시작할 수 있습니다.

페더러드 및 익명 사용자와 같은 조직 외부의 사용자는 기록을 시작할 수 없습니다. 게스트 사용자는 기록을 시작하거나 중지할 수 없습니다.

![기록 옵션](media/meeting-policies-recording.png)

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |클라우드 기록 허용 |
|---------|---------|---------|
|Daniela | 전역   | 끄기 |
|Amanda | Location1MeetingPolicy | On|
|John(외부 사용자) | 해당 사항 없음 | 해당 사항 없음|

Daniela는 이끌이인 경우에도 정책이 꺼지기 때문에 기록할 수 없습니다. 정책 설정을 사용하도록 설정한 Amanda는 Daniela가 구성한 모임도 녹화할 수 있습니다. Amanda가 모임을 구성하는 경우 이 모임을 기록할 수 있습니다. 그러나 정책 설정을 사용할 수 없는 Daniela와 외부 사용자인 John은 해당 모임을 기록할 수 없습니다.

클라우드 모임 녹화에 대한 자세한 내용은 Teams 클라우드 모임 [녹화를 참조합니다.](cloud-recording.md)

### <a name="mode-for-ip-audio"></a>IP 오디오 모드

사용자당 정책입니다. 이 설정은 모임 및 그룹 통화에서 오디오를 설정할 수 있는지 여부를 제어합니다. 이 설정에 대한 값은 다음과 같습니다.

|값 설정 |동작  |
|---------|---------|
|**수신 오디오 및 수신 오디오 사용**    |모임에서 유출 및 수신 오디오가 허용됩니다. 기본 설정입니다. |
|**사용 안**     |모임에서 걸고 받는 오디오가 꺼져 있습니다.     |

사용자에 대해 **사용** 안 하도록 설정되어 있는 경우 해당 사용자는 여전히 모임을 예약하고 구성할 수 있지만 오디오를 사용할 수 없습니다. 모임에 참가하기 위해 PSTN(공용 전화망)을 통해 전화를 걸거나 모임에 전화를 걸고 전화로 참가해야 합니다. 정책이 할당되지 않은 모임 참가자(예: 익명 참가자)는 이 설정을 기본적으로 수신 및 수신 오디오로 **설정합니다.** Teams 모바일 클라이언트에서 이 설정을 사용하지 않도록 설정한 경우 사용자는 PSTN을 통해 모임에 전화 접속해야 합니다.

이 설정은 1:1 호출에 적용되지 않습니다. 1:1 통화를 제한하기 위해 [Teams](teams-calling-policy.md) 통화 정책을 구성하고 비공개 통화 설정 기능을 **해제합니다.** 이 설정은 Surface Hub 및 Microsoft Teams Room 장치와 같은 회의실 장치에도 적용되지 않습니다.

이 설정은 Microsoft 365 GCC(Government Community Cloud), GCC High 또는 DoD(국방부) 환경에서는 아직 사용할 수 없습니다.

자세한 내용은 모임 [참가자를 위한 오디오/비디오 관리를 참조합니다.](#manage-audiovideo-for-meeting-participants)

### <a name="mode-for-ip-video"></a>IP 비디오 모드

사용자당 정책입니다. 이 설정은 모임 및 그룹 통화에서 비디오를 설정할 수 있는지 여부를 제어합니다. 이 설정에 대한 값은 다음과 같습니다.

|값 설정 |동작  |
|---------|---------|
|**유출 및 수신 비디오 사용**    | 모임에서 유출 및 수신 비디오가 허용됩니다. 기본 설정입니다. |
|**사용 안**     | 모임에서 걸고 받는 비디오가 꺼져 있습니다. Teams 모바일 클라이언트에서는 사용자가 모임의 비디오 또는 사진을 공유할 수 없습니다. <br><br>IP 오디오 **모드가 비활성화된** 경우 **IP** 비디오 모드도 비활성화된 상태로 유지됩니다.  |

사용자에 대해 **사용** 안 하도록 설정한 경우 해당 사용자는 비디오를 켜거나 다른 모임 참가자가 공유한 비디오를 볼 수 없습니다. 정책이 할당되지 않은 모임 참가자(예: 익명 참가자)는 이 설정을 기본적으로 수신 및 수신 비디오로 **설정합니다.**

이 설정은 Surface Hub 및 Microsoft Teams Room 장치와 같은 회의실 장치에는 적용되지 않습니다.

이 설정은 Microsoft 365 GCC(Government Community Cloud), GCC High 또는 DoD(국방부) 환경에서는 아직 사용할 수 없습니다.

> [!NOTE]
> 이 설정은 내보이는 비디오와 들어오는 비디오를 제어하는 반면 **IP** 비디오 허용 설정은 진행하는 비디오를 제어합니다. 자세한 내용은 어떤 IP 비디오 정책 설정이 우선적으로 [적용하나요?](#which-ip-video-policy-setting-takes-precedence) 및 모임 참가자를 위한 [오디오/비디오 관리를 참조하세요.](#manage-audiovideo-for-meeting-participants)

자세한 내용은 모임 [참가자를 위한 오디오/비디오 관리를 참조합니다.](#manage-audiovideo-for-meeting-participants)

### <a name="allow-ip-video"></a>IP 비디오 허용

이끌이 및 사용자당 정책의 조합입니다. 비디오는 모임의 핵심 구성 요소입니다. 일부 조직에서는 관리자가 비디오가 있는 사용자의 모임에 대한 제어를 더 많이 원할 수 있습니다. 이 설정은 사용자가 호스트하는 모임 및 사용자가 시작한 1:1 및 그룹 통화에서 비디오를 설정할 수 있는지 여부를 제어합니다. Teams 모바일 클라이언트에서 이 설정은 사용자가 모임에서 사진과 비디오를 공유할 수 있는지 여부를 제어합니다.

이 정책 설정을 사용하도록 설정한 사용자가 구성한 모임은 모임 참가자가 정책 설정도 사용하도록 설정한 경우 모임 참가자가 모임에서 비디오 공유를 허용합니다. 정책이 할당되지 않은 모임 참가자(예: 익명 및 페더리된 참가자)는 모임 이끌이의 정책을 상속합니다.

> [!NOTE]
> 이 설정은 나선 비디오를 제어하는 반면 **IP** 비디오 설정 모드는 나선 비디오와 들어오는 비디오를 모두 제어합니다. 자세한 내용은 어떤 IP 비디오 정책 설정이 [우선하나요?](#which-ip-video-policy-setting-takes-precedence) 및 모임 참가자를 위한 [오디오/비디오 관리를 참조하세요.](#manage-audiovideo-for-meeting-participants)

| Teams 데스크톱 및 웹 클라이언트 |Teams 모바일 클라이언트  |
|:-------:|:-------:|
|![데스크톱의 오디오/비디오 설정이 있는 모임 참가를 보여주는 스크린샷](media/meeting-policies-audio-video-settings.png)    |![모바일에서 오디오/비디오 설정을 사용하여 모임 참가를 보여주는 스크린샷](media/meeting-policies-mobile-join.png)          |

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |IP 비디오 허용 |
|---------|---------|---------|
|Daniela   | 전역   | On       |
|아만다    | Location1MeetingPolicy        | 끄기      |

Daniela가 주최하는 모임에서는 비디오를 하도록 허용합니다. Daniela는 모임에 참가하고 비디오를 끄는 데 사용할 수 있습니다. Amanda의 정책이 비디오를 허용하지 않는 것으로 설정되어 있기 때문에 Daniela의 모임에서 Amanda는 비디오를 설정할 수 없습니다. Amanda는 모임의 다른 참가자가 공유한 비디오를 볼 수 있습니다.

Amanda가 주최하는 모임에서는 할당된 비디오 정책에 관계없이 아무도 비디오를 끄지 않습니다. 즉, Daniela는 Amanda의 모임에서 비디오를 끄지 못합니다.  

Daniela가 비디오로 Amanda를 호출하면 Amanda는 오디오로만 통화에 응답할 수 있습니다.  통화가 연결되면 Amanda에서 Daniela의 비디오를 볼 수 있지만 비디오를 켜지 못합니다. Amanda가 Daniela를 호출하면 Daniela는 비디오 및 오디오로 통화에 응답할 수 있습니다. 통화가 연결되면 Daniela는 필요한 경우 자신의 비디오를 설정하거나 해제할 수 있습니다.

자세한 내용은 모임 [참가자에 대한 오디오/비디오 관리를 참조합니다.](#manage-audiovideo-for-meeting-participants)

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>우선적으로 적용되는 IP 비디오 정책 설정

사용자의 경우 비디오에 대한 가장 제한적인 정책 설정이 우선합니다. 다음은 몇 가지 예입니다.

|IP 비디오 허용|IP 비디오 모드|모임 환경|
|---------|---------|---------|
|이끌이: <br><br>참가자:  |참가자: **사용 안**        |**IP 비디오 설정에 대한 모드가** 우선합니다. 이 정책이 할당된 참가자는 다른 사람이 공유한 비디오를 켜거나 볼 수 없습니다.|
|이끌이: <br><br>참가자:  |참가자: **유출 및 수신 비디오 사용**          |이 정책이 할당된 참가자는 다른 사람이 공유한 비디오를 켜거나 볼 수 있습니다.         |
|이끌이: <br><br>참가자: **끄기** |참가자: **유출 및 수신 비디오 사용**         |IP **비디오 허용 설정이** 우선합니다. 참가자는 들어오는 비디오만 볼 수 있으며 보내는 비디오를 보낼 수 없습니다.         |
|이끌이: <br><br>참가자: **끄기** |참가자: **사용 안**         |**IP 비디오 설정에 대한 모드가** 우선합니다. 참가자는 수신 또는 유출 비디오를 볼 수 없는 경우|
|이끌이: **끄기**    |       |IP **비디오** 허용 설정은 이끌이에 대해 꺼져 있기 때문에 우선적으로 적용됩니다. 이 정책이 할당된 사용자가 구성한 모임에서 비디오를 끄는 사용자는 없습니다.         |

### <a name="manage-audiovideo-for-meeting-participants"></a>모임 참가자를 위한 오디오/비디오 관리

|원하는 경우...  |다음 정책 설정 설정  |
|---------|---------|
|모임 참가자의 오디오 및 비디오 사용 안  |IP 오디오 모드: **사용 안**<br> IP 비디오 모드: **사용 안**<br>IP 비디오 허용: N/A       |
|모임 참가자에 대해 들어오는 비디오 및 오디오만 사용하도록 설정  |IP 오디오 모드: **내보내기** 및 수신 오디오 사용<br> IP 비디오 모드: 유출 및 들어오는 **비디오 사용**<br>IP 비디오 허용: **끄기**       |
|모임 참가자의 비디오 사용 안 하게 설정(참가자는 오디오만 사용)|  IP 오디오 모드: **내보내고 들어오는** 오디오 사용<br> IP 비디오 모드: **사용 안**<br>IP 비디오 허용: N/A
|모임 참가자에 대한 오디오 및 비디오 사용    |IP 오디오 모드: 수신 및 수신 **오디오** 사용(기본값)<br> IP 비디오 모드: 유출 및 들어오는 **비디오 사용(기본값)**<br>IP 비디오  허용: 설정(기본값)    |

모임 이끌이의 정책과 사용자의 정책 간에 가장 제한적인 정책이 적용됩니다. 예를 들어 이끌이에게 비디오를 제한하는 정책이 있으며 사용자의 정책이 비디오를 제한하지 않는 경우 모임 참가자는 모임 이끌이의 정책을 상속받고 모임의 비디오에 액세스할 수 없습니다. 즉, 오디오로만 모임에 참가할 수 있습니다.

> [!NOTE]
> 사용자가 전화로 참가하기 위한 그룹 통화를 시작하면 오디오 화면에 휴대폰 사용이 나타나지 않습니다.  이 문제는 해결하기 위해 작업하고 있는 알려진 문제입니다. 이 문제를 해결하려면 기타 조인 옵션에서 전화 **오디오를** **선택합니다.**  

#### <a name="teams-mobile-clients"></a>Teams 모바일 클라이언트

Teams 모바일 클라이언트의 사용자의 경우 모임 중에 사진 및 비디오를 공유하는 능력도 IP 비디오 또는 **IP** 비디오 모드 허용 설정에 **따라 결정됩니다.** 어떤 정책 설정이 우선적으로 적용될지에 따라 비디오 및 사진을 공유하는 기능을 사용할 수 없습니다. 별도의 화면 공유 모드 설정을 사용하여 구성하는 화면 공유에는 [영향을 주지](#screen-sharing-mode) 않습니다. 또한 모바일 사용자가 셀룰러 연결을 통해 IP 비디오를 사용하지 못하게 하는 [Teams](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) 모바일 정책을 설정할 수 있습니다. 즉, WiFi 연결을 사용해야 합니다.

### <a name="media-bit-rate-kbs"></a>미디어 비트 속도(KBS)

사용자당 정책입니다. 이 설정은 사용자의 통화 및 모임에서 오디오, 비디오 및 비디오 기반 앱 공유 전송에 대한 미디어 비트 전송률을 결정합니다. 통화 또는 모임의 사용자에 대한 업링크 및 다운링크 미디어 트래버스 모두에 적용됩니다. 이 설정은 조직의 대역폭 관리를 세밀하게 제어할 수 있습니다. 사용자가 요구하는 모임 시나리오에 따라 양호한 품질 환경을 위해 충분한 대역폭을 사용하는 것이 좋습니다. 최소값은 30 Kbps로, 최대값은 모임 시나리오에 따라 다릅니다. Teams에서 양질의 모임, 통화 및 라이브 이벤트에 권장되는 최소 대역폭에 대한 자세한 내용은 대역폭 요구 [사항을 참조하세요.](prepare-network.md#bandwidth-requirements)

모임에 대한 대역폭이 충분하지 않은 경우 참가자에게 네트워크 품질이 나쁨을 나타내는 메시지가 표시됩니다.

최고 품질의 비디오 환경(예: CEO 보드 모임 및 Teams 라이브 이벤트)이 필요한 모임의 경우 대역폭을 10Mbps로 설정하는 것이 좋습니다. 최대 환경을 설정한 경우에도 시나리오에 따라 특정 네트워크 조건이 감지될 때 Teams 미디어 스택이 낮은 대역폭 조건에 맞게 조정됩니다.

## <a name="meeting-policy-settings---content-sharing"></a>모임 정책 설정 - 콘텐츠 공유

- [화면 공유 모드](#screen-sharing-mode)
- [참가자가 제어권 제공 또는 요청 허용](#allow-a-participant-to-give-or-request-control)
- [외부 참가자가 제어권 제공 또는 요청 허용](#allow-an-external-participant-to-give-or-request-control)
- [PowerPoint 공유 허용](#allow-powerpoint-sharing)
- [화이트보드 허용](#allow-whiteboard)
- [공유 노트 허용](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>화면 공유 모드

> [!NOTE]
> 이 기능은 아직 개발 중입니다. 화면 공유는 참가자당 정책입니다. 그러나 이 섹션에 설명된 바와 같이 이끌이의 화면 공유 설정에 의해 영향을 받을 수 있습니다.

이 설정은 데스크톱 및/또는 창 공유가 사용자의 모임에서 허용될지 여부를 제어합니다. 정책이 할당되지 않은 모임 참가자(예: 익명, 게스트, B2B 및 페더러드 참가자)는 모임 이끌이의 정책을 상속합니다.

|값 설정 |동작  |
|---------|---------|
|**전체 화면**    | 모임에서 전체 데스크톱 공유 및 응용 프로그램 공유가 허용됩니다. |
|**단일 애플리케이션**   | 모임에서 응용 프로그램 공유가 허용됩니다.        |
|**사용 안**     |모임에서 화면 공유 및 응용 프로그램 공유가 해제되어 있습니다.       |

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책 |화면 공유 모드 |
|---------|---------|---------|
|Daniela  | 전역   | 전체 화면 |
|아만다   | Location1MeetingPolicy  | 사용 안 |

Daniela가 주최하는 모임을 통해 모임 참가자가 전체 화면 또는 특정 응용 프로그램을 공유할 수 있습니다. Amanda가 Daniela의 모임에 참가하는 경우 Amanda는 정책 설정이 비활성화되어 자신의 화면 또는 특정 응용 프로그램을 공유할 수 없습니다. Amanda에서 호스트하는 모임에서는 할당된 화면 공유 모드 정책에 관계없이 누구도 자신의 화면 또는 단일 응용 프로그램을 공유할 수 없습니다. 즉, Daniela는 Amanda의 모임에서 자신의 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.  

현재 사용자는 Google Chrome을 사용하는 경우 Teams 모임에서 비디오를 재생하거나 화면을 공유할 수 없습니다.

### <a name="allow-a-participant-to-give-or-request-control"></a>참가자가 제어권 제공 또는 요청 허용

사용자당 정책입니다. 이 설정은 사용자가 공유 데스크톱 또는 창을 다른 모임 참가자에게 제어할 수 있는지 여부를 제어합니다. 제어권을 제공하기 위해 화면 위쪽을 마우스로 니다.

사용자에 대해 이 설정이 켜져 있는 경우 **제어권** 제공 옵션이 공유 세션의 위쪽 표시줄에 표시됩니다.

![제어권 제공 옵션을 보여 주는 스크린샷](media/meeting-policies-give-control.png)

사용자에 대한 설정이 꺼져  있는 경우 제어권 제공 옵션을 사용할 수 없습니다.

![제어권 제공 옵션을 사용할 수 없는 경우를 보여 주는 스크린샷](media/meeting-policies-give-control-not-available.png)

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |참가자가 제어권 제공 또는 요청 허용 |
|---------|---------|---------|
|Daniela   | 전역   | On       |
|Babek    | Location1MeetingPolicy        | 끄기   |

Daniela는 Babek가 구성한 모임의 다른 참가자에게 공유 데스크톱 또는 창을 제어할 수 있는 반면 Babek는 다른 참가자에게 제어를 줄 수 없습니다.

PowerShell을 사용하여 제어 요청을 제어하거나 수락할 수 있는 사용자 제어를 위해 AllowParticipantGiveRequestControl cmdlet을 사용 합니다.

> [!NOTE]
> 공유 중에 공유 콘텐츠를 제공하고 제어하려면 두 당사자 모두 Teams 데스크톱 클라이언트를 사용하고 있어야 합니다. 컨트롤은 어느 쪽이든 브라우저에서 Teams를 실행 중인 경우 지원되지 않습니다. 이것은 해결하려고 하는 기술적 제한 때문입니다.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>외부 참가자가 제어권 제공 또는 요청 허용

사용자당 정책입니다. 조직에서 사용자에 대해 이 설정이 설정되어 있는지 여부는 모임 이끌이가 설정한 일과 관계 없이 외부 참가자가 할 수 있는 작업을 제어하지 않습니다. 이 매개 변수는 공유자가 조직의 모임 정책 내에서 설정한 값에 따라 외부 참가자에게 공유자 화면의 제어 또는 요청 제어를 부여할 수 있는지 여부를 제어합니다. Teams 모임의 외부 참가자는 다음과 같이 분류할 수 있습니다.  

- 익명 사용자
- 게스트 사용자  
- B2B 사용자
- 페더리된 사용자  

페더링된 사용자가 공유하는 동안 외부 사용자에게 제어권  제공 여부는 외부 참가자가 조직에서 제어 설정을 제공하거나 요청할 수 있도록 허용합니다.

PowerShell을 사용하여 외부 참가자가 제어를 위한 제어를 제공하거나 제어 요청을 수락할 수 있는지 여부를 제어하기 위해 AllowExternalParticipantGiveRequestControl cmdlet을 사용 합니다.

### <a name="allow-powerpoint-sharing"></a>PowerPoint 공유 허용

사용자당 정책입니다. 이 설정은 사용자가 모임에서 PowerPoint 슬라이드 데크를 공유할 수 있는지 여부를 제어합니다. 익명, 게스트 및 페더러드 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 상속합니다.

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |PowerPoint 공유 허용 |
|---------|---------|---------|
|Daniela   | 전역   | On       |
|아만다   | Location1MeetingPolicy        | 끄기   |

Amanda는 모임 이끌이인 경우에도 모임에서 PowerPoint 슬라이드 데크를 공유할 수 없습니다. Daniela는 모임이 Amanda에서 구성한 경우에도 PowerPoint 슬라이드 데크를 공유할 수 있습니다. Amanda는 PowerPoint 슬라이드 데크를 공유할 수 없는 경우에도 모임에 있는 다른 사람이 공유한 PowerPoint 슬라이드 데크를 볼 수 있습니다.

### <a name="allow-whiteboard"></a>화이트보드 허용

사용자당 정책입니다. 이 설정은 사용자가 모임에서 화이트보드를 공유할 수 있는지 여부를 제어합니다. 익명, B2B 및 페더러드 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 상속합니다.

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |화이트보드 허용|
|---------|---------|---------|
|Daniela   | 전역   | On       |
|아만다   | Location1MeetingPolicy        | 끄기   |

Amanda는 모임 이끌이인 경우에도 모임에서 화이트보드를 공유할 수 없습니다. Daniela는 Amanda에서 모임을 구성하는 경우에도 화이트보드를 공유할 수 있습니다.  

### <a name="allow-shared-notes"></a>공유 노트 허용

사용자당 정책입니다. 이 설정은 사용자가 모임에서 노트를 만들고 공유할 수 있는지 여부를 제어합니다. 익명, B2B 및 페더러드 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 상속합니다. 모임 **노트 탭은** 최대 100명이 참여하는 모임에서 지원됩니다.

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |공유 노트 허용 |
|---------|---------|---------|
|Daniela   | 전역   | On       |
|Amanda   | Location1MeetingPolicy | 끄기 |

Daniela는 Amanda의 모임에서 메모를 기록할 수 있으며, Amanda는 모임에서 메모를 기록할 수 없습니다.

## <a name="meeting-policy-settings---participants--guests"></a>모임 정책 설정 - 참가자 & 게스트

이러한 설정은 모임에 참가하기 전에 대기실에서 대기하는 모임 참가자와 모임에 허용되는 참가 수준을 제어합니다.

- [익명 사용자가 모임을 시작할 수 있습니다.](#let-anonymous-people-start-a-meeting)
- [자동으로 사람 입력](#automatically-admit-people)
- [전화 접속 사용자가 로비를 우회하도록 허용](#allow-dial-in-users-to-bypass-the-lobby)
- [라이브 캡션 사용](#enable-live-captions)
- [모임에서 채팅 허용](#allow-chat-in-meetings)

> [!NOTE]
>모임에 참가하는 옵션은 각 Teams 그룹의 설정 및 연결 방법에 따라 달라집니다. 그룹에 오디오 회의가 있으며 이를 사용하여 연결하는 경우 [오디오 회의를 참조합니다.](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365) Teams 그룹에 오디오 회의가 없는 경우 Teams에서 모임 [참가를 참조합니다.](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)

### <a name="let-anonymous-people-start-a-meeting"></a>익명 사용자가 모임을 시작할 수 있습니다.

이 정책은 리더 없는 전화 접속 회의 모임을 허용하는 이끌이당 정책입니다. 이 설정은 전화 접속 사용자가 조직의 인증된 사용자가 참석하지 않고 모임에 참가할 수 있는지 여부를 제어합니다. 기본적으로 이 설정은 해제되어 있습니다. 즉, 전화 접속 사용자는 조직의 인증된 사용자가 모임에 참가할 때까지 대기실에서 대기합니다.

> [!NOTE]
> 이 설정이 해제되어 있으며 전화 접속 사용자가 먼저 모임에 참가하고 로비에 배치된 경우 조직 사용자는 Teams 클라이언트와 모임에 참가하여 로비에서 사용자를 인정해야 합니다. 전화 접속 사용자에 사용할 수 있는 로비 컨트롤은 없습니다.

### <a name="automatically-admit-people"></a>자동으로 사람 입력

이 정책은 구성자당 정책입니다. 이 설정은 사용자가 직접 모임에 참가할지 또는 인증된 사용자가 입원할 때까지 대기실에서 대기하는지 여부를 제어합니다. 이 설정은 전화 접속 사용자에게는 적용되지 않습니다.

![로비에 있는 사용자와의 모임을 보여주는 스크린샷](media/meeting-policies-lobby.png)

 모임 이끌이는 **모임** 초대에서 모임 옵션을 선택하여 예약하는 각 모임에 대해 이 설정을 변경할 수 있습니다.

> [!NOTE]
> 모임 옵션에서 설정에는 "로비를 무시할 수 있는 사용자"라는 레이블이 지정됩니다. 사용자에 대한 기본 설정을 변경하면 해당 사용자가 구성한 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 적용됩니다.
  
|값 설정  |조인 동작 |
|---------|---------|
|**모든 사용자**   |모든 모임 참가자는 대기실에서 기다리지 않고 바로 모임에 참가합니다. 여기에는 인증된 사용자, 신뢰할 수 있는 조직의 외부 사용자(페더러드), 게스트 및 익명 사용자가 포함됩니다.     |
|**조직 및 페더러드 조직의 모든 사용자**     |게스트 사용자 및 신뢰할 수 있는 조직의 사용자를 포함하여 조직 내에서 인증된 사용자는 대기실에서 기다리지 않고 바로 모임에 참가합니다.  익명 사용자는 대기실에서 대기합니다.   |
|**조직의 모든 사용자**    |게스트 사용자를 포함하여 조직 내에서 인증된 사용자는 대기실에서 기다리지 않고 직접 모임에 참가합니다.  신뢰할 수 있는 조직의 사용자와 익명 사용자의 대기실에서 대기합니다. 기본 설정입니다.           |
|**이끌이만 해당**    |모임 이끌이만 대기실에서 기다리지 않고 바로 모임에 참가할 수 있습니다. 조직 내의 인증된 사용자, 게스트 사용자, 신뢰할 수 있는 조직의 사용자 및 익명 사용자 등 다른 모든 사용자는 대기실에서 기다려야 합니다.           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>전화 접속 사용자가 로비를 우회하도록 허용

이 정책은 구성자당 정책입니다. 이 설정은 전화로 전화 접속하는 사람이 모임에 직접 참가하거나 대기실에서 대기하는지 여부를 자동으로 사용자 설정에 관계없이 **제어합니다.** 기본적으로 이 설정은 해제되어 있습니다. 이 설정이 해제되어 있는 경우 전화 접속 사용자는 조직 사용자가 Teams 클라이언트로 모임에 참가하고 이를 인정할 때까지 대기실에서 대기합니다. 이 설정이 설정되어 있는 경우 조직 사용자가 모임에 참가하면 전화 접속 사용자가 자동으로 모임에 참가합니다.

> [!NOTE]
> 조직 사용자가 모임에 참가하기 전에 전화 접속 사용자가 모임에 참가하는 경우 조직 사용자가 Teams 클라이언트를 사용하여 모임에 참가하고 해당 사용자가 모임에 참가할 때까지 대기실에 배치됩니다. 사용자에 대한 기본 설정을 변경하면 해당 사용자가 구성한 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 적용됩니다.

### <a name="enable-live-captions"></a>라이브 캡션 사용

이는 사용자당 정책으로, 모임 중에 적용됩니다. 이 설정은 사용자가  참석하는 모임에서 라이브 캡션을 켜고 끄기 위해 라이브 캡션 켜기 옵션을 사용할 수 있는지 여부를 제어합니다.  

![라이브 캡션 켜기 옵션을 보여주는 스크린샷](media/meeting-policies-live-captions.png)

|값 설정 |동작  |
|---------|---------|
|**사용 안 되지만 사용자가 을(를)**     | 모임 중에 사용자에 대해 라이브 캡션이 자동으로 설정되지 않습니다. 사용자는 오버플로(...) 메뉴에 라이브 캡션켜기 옵션을 표시하여 켜세요.  기본 설정입니다. |
|**사용 안**     | 모임 중에 사용자가 라이브 캡션을 사용할 수 없습니다. 사용자에게 설정하는 옵션이 없습니다.          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>모임에서 채팅 허용

이는 참가자당 설정입니다. 이 설정은 사용자의 모임에서 모임 채팅을 허용할지 여부를 제어합니다.

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a>모임 정책 설정 - 지정된 발표자 역할 모드

사용자당 정책입니다. 이 설정을 사용하면 Teams 클라이언트의 모임 옵션에서 발표할 수 있는 **사람에** 대한 **기본값을** 변경할 수 있습니다. 이 정책 설정은 모임 시작을 포함하여 모든 모임에 영향을 미치고 있습니다.

누가 발표할 수 **있나요?** 설정을 사용하면 모임 이끌이가 모임에서 발표자가 될 수 있는 사람 선택이 있습니다. 자세한 내용은 Teams 모임에서 [Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 모임 및 역할에 대한 참가자 설정 [변경을 참조하세요.](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)

현재는 PowerShell만 사용하여 이 정책 설정을 구성할 수 있습니다. [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존 Teams 모임 정책을 편집할 수 있습니다. 또는 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새 Teams 모임 정책을 만들고 사용자에게 할당합니다.

Teams에서 사용할 수  있는 사용자 설정의 기본값을 지정하기 위해 **DesignatedPresenterRoleMode** 매개 변수를 다음 중 하나로 설정하세요.

- **EveryoneUserOverride:** 모든 모임 참가자가 발표자일 수 있습니다. 기본값입니다. 이 매개 변수는 Teams의 **모든 사용자** 설정에 해당합니다.
- **EveryoneInCompanyUserOverride:** 게스트 사용자를 포함하여 조직의 인증된 사용자는 발표자일 수 있습니다. 이 매개 변수는 Teams의 조직 **설정에 있는** 사용자에 해당합니다.
- **OrganizerOnlyUserOverride:** 모임 이끌이만 발표자가 될 수 있으며 모든 모임 참가자는 참석자로 지정됩니다. 이 매개 변수는 Teams의 **유일한** 설정에 해당합니다.

기본값을 설정한 후에도 모임 이끌이는 Teams에서 이 설정을 변경하고 예약하는 모임에 참석할 수 있는 사용자도 선택할 수 있습니다.

## <a name="meeting-policy-settings---meeting-attendance-report"></a>모임 정책 설정 - 모임 참석자 보고서

사용자당 정책입니다. 이 설정은 모임 이끌이가 모임 참석자 보고서를 [다운로드할 수 있는지 여부를 제어합니다.](teams-analytics-and-reports/meeting-attendance-report.md)

현재 PowerShell을 사용하여 이 정책 설정을 구성할 수 있습니다. [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존 Teams 모임 정책을 편집할 수 있습니다. 또는 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새 Teams 모임 정책을 만들고 사용자에게 할당합니다.

모임 이끌이가 모임 참석자 보고서를 다운로드할 수 있도록 설정하려면 **AllowEngagementReport** 매개 변수를 **사용으로 설정합니다.** 사용하도록 설정하면 보고서를 다운로드하는 옵션이 참가자 **창에** 표시됩니다.

모임 이끌이가 보고서를 다운로드하지 못하게 방지하려면 매개 변수를 사용 안 으로 **설정합니다.** 기본적으로 이 설정은 사용하지 않도록 설정되어 있으며 보고서를 다운로드하는 옵션을 사용할 수 없습니다.

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a>모임 정책 설정 - 모임 공급자 for Islands 모드

사용자당 정책입니다. 이 설정은 제도 모드에 있는 사용자에게 사용되는 Outlook 모임 추가 기능을 *제어합니다.* 사용자가 Teams 모임 추가 기능만 사용할 수 있는지 또는 Teams 모임 및 비즈니스용 Skype 모임 추가 기능을 모두 사용하여 Outlook에서 회의를 예약할 수 있는지 여부를 지정할 수 있습니다.

이 정책은 아일랜드 모드이면서 Teams 모임 정책에서 **AllowOutlookAddIn** 매개 변수가 **True** 로 설정된 사용자에게만 적용할 수 있습니다.

현재 PowerShell을 사용하여 이 정책을 설정할 수 있습니다. [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존 Teams 모임 정책을 편집할 수 있습니다. 또는 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새 Teams 모임 정책을 만들고 사용자에게 할당합니다.

사용자가 사용할 수 있는 모임 추가 기능을 지정하려는 경우 다음과 같이 **PreferredMeetingProviderForIslandsMode** 매개 변수를 설정합니다.

- Outlook에서 Teams 모임 추가 기능 및 비즈니스용 Skype 추가 기능을 모두 사용하도록 설정하려면 이 매개 변수를 **TeamsAndSfB로** 설정하세요. 기본값입니다.
- Outlook에서 Teams 모임 추가 기능만 사용하도록 설정하려면 매개 변수를 **Teams로** 설정합니다. 이 정책 설정은 향후 모든 모임에 Teams 모임 참가 링크가 있도록 합니다. 기존 비즈니스용 Skype 모임 참가 링크를 Teams로 마이그레이션하지 않습니다. 이 정책 설정은 현재 상태, 채팅, PSTN 통화 또는 비즈니스용 Skype의 기타 기능에 영향을 주지 않습니다. 즉, 사용자가 이러한 기능을 위해 비즈니스용 Skype를 계속 사용할 수 있습니다.

  매개 변수를 **Teams로** 설정한 다음 **TeamsAndSfB로** 다시 전환하면 두 모임 추가 기능이 모두 활성화됩니다. 그러나 기존 Teams 모임 참가 링크는 비즈니스용 Skype로 마이그레이션되지 않습니다. 변경 후 예약된 비즈니스용 Skype 모임만 비즈니스용 Skype 모임 참가 링크가 있습니다.

## <a name="meeting-policy-settings---video-filters-mode"></a>모임 정책 설정 - 비디오 필터 모드

사용자당 정책입니다. 이 설정은 사용자가 모임에서 자신의 비디오 배경을 사용자 지정할 수 있는지 여부를 제어합니다.

현재는 PowerShell만 사용하여 이 정책을 설정할 수 있습니다. [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존 Teams 모임 정책을 편집할 수 있습니다. 또는 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새 Teams 모임 정책을 만든 다음 사용자에게 정책을 할당합니다.

사용자가 모임에서 비디오 배경을 사용자 지정할 수 있는지 여부를 지정하기 위해 **VideoFiltersMode** 매개 변수를 다음과 같이 설정합니다.

|PowerShell에서 값 설정 |동작  |
|---------|---------|
|**NoFilters**     |사용자는 자신의 비디오 배경을 사용자 지정할 수 없습니다.|
|**BlurOnly**     |사용자는 비디오 배경을 흐리게 하는 옵션이 있습니다. |
|**BlurandDefaultBackgrounds**     |사용자는 비디오 배경을 흐리게 지정하거나 배경으로 사용할 기본 이미지 집합에서 선택할 수 있습니다. |
|**AllFilters**     |사용자는 비디오 배경을 흐리게 만들거나, 기본 이미지 집합에서 선택하거나, 배경으로 사용할 사용자 지정 이미지를 업로드할 수 있습니다. |

> [!IMPORTANT]
> 사용자가 업로드한 이미지는 Teams에서 화면이 표시되지 않습니다. **AllFilters** 설정을 사용하는 경우 사용자가 부적절하거나 부적절한 이미지를 업로드하지 못하게 하는 내부 조직 정책이 필요합니다. 조직에 Teams 모임 배경에 사용할 수 있는 권한은 없습니다.

> [!NOTE]
> 이러한 기능은 모든 Teams 클라이언트에서 사용할 수 없습니다. 자세한 내용은 모임  및 라이브 이벤트의 비디오 및 배경 [제목을 참조하세요.](https://support.microsoft.com/office/meetings-and-live-events-5c3e0646-dc37-45ad-84a4-1666fac62d4e)

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](assign-policies.md)
- [사용자에서 RestrictedAnonymousAccess Teams 모임 정책 제거](meeting-policies-restricted-anonymous-access.md)
