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
description: 팀에서 모임 정책 설정을 관리 하 고이를 사용 하 여 사용자가 예약한 모임의 모임 참가자가 사용할 수 있는 기능을 제어 하는 방법을 알아봅니다.
ms.openlocfilehash: a2d1cf256829cccd27bde2dce311145b8861ae84
ms.sourcegitcommit: 8395f91205bde549a0a92999ef00c5f5fb03fb80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44583501"
---
# <a name="manage-meeting-policies-in-teams"></a>팀에서 모임 정책 관리

::: zone target="docs"
모임 정책은 조직에서 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다. 정책을 만들고 변경한 후에 사용자를 정책에 할당할 수 있습니다. Microsoft 팀 관리 센터에서 또는 [PowerShell](teams-powershell-overview.md)을 사용 하 여 모임 정책을 관리할 수 있습니다.

> [!NOTE]
> 역할을 사용 하 여 모임 발표자 및 참석자의 사용 권한을 관리 하는 방법에 대 한 자세한 내용은 [팀 모임에서 역할](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)을 참조 하세요.

모임 시작, 모임 중 또는 모임 이후 사용자의 모임 환경에 영향을 주는 다음과 같은 방법으로 정책을 구현할 수 있습니다.

|구현 형식  |설명  |
|---------|---------|
|이끌이 별    |이끌이 별 정책을 구현 하는 경우 모든 모임 참가자는 해당 이끌이의 정책을 상속 합니다. 예를 들어 사용자가 **자동으로** 허용 이끌이 정책 이며 사용자가 모임에 직접 참가 하는지 여부를 제어 하 고 정책에 할당 된 사용자가 예약한 모임에 대해 대기실에서 대기 합니다.          |
|사용자별    |사용자별 정책을 구현할 때, 이끌이 및/또는 모임 참가자에 대 한 특정 기능을 제한 하는 사용자별 정책만 적용 됩니다. 예를 들어 **채널에서 모임** 시작을 허용 하는 것은 사용자별 정책입니다.     |
|이끌이와 사용자 단위     |이끌이 및 사용자별 정책 조합을 구현 하는 경우 특정 기능은 해당 정책 및 이끌이의 정책에 따라 모임 참가자에 대해 제한 됩니다. 예를 들어 **클라우드 기록은 허용** -이끌이 및 사용자별 정책입니다. 이 설정을 사용 하 여 모임 이끌이 및 참가자가 녹음/녹화를 시작 하 고 중지할 수 있습니다.

기본적으로 Global (조직 전체 기본값) 이라는 정책이 만들어집니다. 조직의 모든 사용자는 기본적으로 전역 모임 정책에 할당 됩니다. 이를 변경 하거나 하나 이상의 사용자 지정 정책을 만들어 사용자를 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당 하지 않으면 사용자가 글로벌 정책을 받습니다. 사용자 지정 정책을 만들 때 사용자가 특정 기능을 사용할 수 있도록 허용 하거나 금지할 수 있으며 설정을 적용할 사용자 하나 이상에 게 할당 합니다.

> [!NOTE]
> 모임 세부 정보 단추는 사용자가 음성 회의 라이선스를 사용 하도록 설정 했거나 사용자가 오디오 회의를 허용 하는 경우 모임 세부 정보를 사용할 수 없는 경우 사용할 수 있습니다.

## <a name="change-or-create-a-meeting-policy"></a>모임 정책 변경 또는 만들기

모임 정책을 변경하거나 만들려면 Microsoft Teams 관리 센터 > **모임** > **모임 정책**으로 이동합니다. 목록에서 정책을 선택하거나 **추가**를 선택합니다. 새 정책을 만들려면 이름과 설명을 추가합니다. 이름은 특수 문자가 포함될 수 없으며 64자를 초과할 수 없습니다. 설정을 선택 하 고 **저장**을 선택 합니다.

예를 들어, 사용자 수가 많은데 모임에 필요한 대역폭의 양을 제한하려고 한다고 가정해 보겠습니다. "제한된 대역폭"이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용하지 않도록 설정합니다.

**오디오 및 비디오**에서:
- 클라우드 녹음/녹화 허용을 끕니다.
- IP 비디오 허용을 끕니다.

**콘텐츠 공유**에서:
- 화면 공유 모드를 사용하지 않도록 설정합니다.
- 화이트보드 허용을 끕니다.
- 공유 노트 허용을 끕니다.

그 다음 사용자에게 정책을 할당합니다.

> [!NOTE]
> 사용자는 한 번에 하나의 모임 정책만 할당할 수 있습니다.

## <a name="assign-a-meeting-policy-to-users"></a>사용자에게 모임 정책 할당

모임 정책을 한 사용자에게 할당하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.
2. 사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.
3. **모임 정책**에서 할당하려는 정책을 선택한 후 **적용**을 클릭합니다.

한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
2. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.
3. **설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.  

또는 다음을 수행할 수도 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **모임**  >  **모임 정책**으로 이동 합니다.
2. 정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.
3. **사용자 관리**를 선택합니다.
4. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요. 추가할 각 사용자에 대해 이 단계를 반복합니다.
5. 사용자 추가를 마쳤으면 **저장**을 선택 합니다.

> [!NOTE]
> 사용자가 할당 된 정책은 삭제할 수 없습니다. 먼저 영향을 받는 모든 사용자에 게 다른 정책을 할당 한 다음 원래 정책을 삭제할 수 있습니다.

## <a name="meeting-policy-settings"></a>모임 정책 설정

**모임 정책** 페이지에서 기존 정책을 선택 하거나 **추가** 를 선택 하 여 새 정책을 추가 하면 다음에 대 한 설정을 구성할 수 있습니다.

- [일반](#meeting-policy-settings---general)
- [오디오 & 비디오](#meeting-policy-settings---audio--video)
- [콘텐츠 공유](#meeting-policy-settings---content-sharing)
- [참가자가 게스트를 &](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>모임 정책 설정-일반

- [채널에서 모임 시작 허용](#allow-meet-now-in-channels)
- [Outlook 추가 기능 허용](#allow-the-outlook-add-in)
- [채널 모임 예약 허용](#allow-channel-meeting-scheduling)
- [개인 모임 예약 허용](#allow-scheduling-private-meetings)
- [비공개 모임에서 모임 시작 허용](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a>채널에서 모임 시작 허용

이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다. 이 설정은 사용자가 팀 채널에서 임시 모임을 시작할 수 있는지 여부를 제어 합니다. 이 기능을 설정 하면 사용자가 팀 채널에서 메시지를 게시할 때 작성 **상자 아래에 있는 모임 시작** 을 클릭 하 여 채널에서 특별 모임을 시작할 수 있습니다. 기본값은 True입니다.

![메시지 아래에 모임 시작 아이콘을 표시 하는 스크린샷](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a>Outlook 추가 기능 허용

이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다. 이 설정은 Outlook (Windows, Mac, 웹, 모바일)에서 팀 모임을 예약할 수 있는지 여부를 제어 합니다.

![새 모임 예약 기능을 보여 주는 스크린샷](media/meeting-policies-outlook-add-in.png)

이 기능을 해제 하면 사용자가 Outlook에서 새 모임을 만들 때 팀 회의를 예약할 수 없습니다. 예를 들어 Windows의 Outlook에서는 **새 팀 모임** 옵션이 리본 메뉴에 표시 되지 않습니다.

### <a name="allow-channel-meeting-scheduling"></a>채널 모임 예약 허용

이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다. 이 설정은 사용자가 팀 채널에서 모임을 예약할 수 있는지 여부를 제어 합니다.  이 기능을 해제 하면 사용자가 팀 채널에서 모임을 시작할 때 **모임 예약** 옵션을 사용할 수 없으며, 팀의 사용자에 대해 **채널 추가** 옵션이 비활성화 됩니다. 기본값은 True입니다.

![팀의 모임 예약 옵션을 보여 주는 스크린샷](media/meeting-policies-schedule-a-meeting.png)

![모임에 적용할 채널 선택 옵션을 보여 주는 스크린샷](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>개인 모임 예약 허용

이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다. 이 설정은 사용자가 팀에서 비공개 모임을 예약할 수 있는지 여부를 제어 합니다. 모임이 팀의 채널에 게시 되지 않은 경우 비공개 모임입니다.

**개인 모임 예약 허용** 을 해제 하 고 **채널 모임 예약을 허용**하는 경우 팀의 사용자는 **필수 참석자 추가** 및 **채널 추가** 옵션을 사용할 수 없습니다. 기본값은 True입니다.

### <a name="allow-meet-now-in-private-meetings"></a>비공개 모임에서 모임 시작 허용

이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다. 이 설정은 사용자가 임시 비공개 모임을 시작할 수 있는지 여부를 제어 합니다.  기본값은 True입니다.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>모임 정책 설정-오디오 & 비디오

- [내용 허용](#allow-transcription)
- [클라우드 기록 허용](#allow-cloud-recording)
- [IP 비디오 허용](#allow-ip-video)
- [미디어 비트 전송률 (Kbs)](#media-bit-rate-kbs)

### <a name="allow-transcription"></a>내용 허용

이는 구성 단위 및 사용자별 정책 조합입니다. 이 설정은 모임 녹음/녹화를 재생 하는 동안 캡션과 기록 기능을 사용할 수 있는지 여부를 제어 합니다. 이 기능을 해제 하면 모임 녹음/녹화를 재생 하는 동안 **검색** 및 **참조** 옵션을 사용할 수 없습니다. 녹음/녹화를 시작한 사람에 게는 녹음/녹화가 포함 되도록이 설정이 켜져 있어야 합니다. 

기록 된 모임에 대 한 정보는 현재 팀의 언어를 영어로 설정한 경우와 모임에서 영어를 사용 하 고 있는 사용자만 지원 합니다.

![모임의 기록 옵션을 보여 주는 스크린샷](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>클라우드 기록 허용

이는 구성 단위 및 사용자별 정책 조합입니다. 이 설정은 사용자의 모임을 녹화할 수 있는지 여부를 제어 합니다. 참가자에 대해 정책 설정이 설정 된 경우와 다른 모임 참가자가 같은 조직의 인증 된 사용자 인 경우 기록을 시작할 수 있습니다.

페더레이션 및 익명 사용자 등 조직 외부의 사용자가 녹음/녹화를 시작할 수 없습니다. 게스트 사용자는 녹음/녹화를 시작 하거나 중지할 수 없습니다. 

![기록 옵션을 보여 주는 스크린샷](media/meeting-policies-recording.png)

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |클라우드 기록 허용 |
|---------|---------|---------|
|Daniela | 전역   | 해제 |
|Amanda | Location1MeetingPolicy | False|
|John (외부 사용자) | 해당 사항 없음 | 해당 사항 없음|

Daniela에서 구성한 모임은 기록 하 고 Amanda 수 있으며, 정책 설정을 사용 하도록 설정한 경우 Daniela로 구성 된 모임을 녹화할 수 없습니다. Amanda에서 구성한 모임은 녹화할 수 있지만, Daniela는 정책 설정을 사용 하지 않도록 설정 하 고 외부 사용자 인 John은 Amanda으로 구성 된 모임을 기록할 수 없습니다.

클라우드 모임 기록에 대해 자세히 알아보려면 [팀 클라우드 모임 기록을](cloud-recording.md)참조 하세요.

### <a name="allow-ip-video"></a>IP 비디오 허용

이는 구성 단위 및 사용자별 정책 조합입니다. 비디오는 모임에 대 한 주요 구성 요소입니다. 일부 조직에서는 관리자가 어떤 사용자의 모임이 비디오를 보유 하 고 있는지 더 자세히 관리할 수 있습니다. 이 설정은 사용자가 호스트 하는 모임 및 사용자가 시작한 1:1 통화 및 그룹 통화에서 비디오를 켤 수 있는지 여부를 제어 합니다. 이 정책을 사용 하도록 설정한 사용자가 구성한 모임에는 모임 참가자가 정책을 사용 하도록 설정한 경우 모임 참가자가 모임에서 비디오 공유를 사용할 수 있습니다. 배정 된 정책이 없는 모임 참가자 (예: 익명 및 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.

![오디오 및 비디오 설정을 사용 하 여 모임을 보여 주는 스크린샷](media/meeting-policies-audio-video-settings.png)

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |IP 영상 허용 |
|---------|---------|---------|
|Daniela   | 전역   | False        |
|Amanda    | Location1MeetingPolicy        | 해제      |

Daniela에서 호스팅하는 모임은 영상 통화를 켤 수 있습니다. Daniela 모임에 참가 하 고 비디오를 켤 수 있습니다. Amanda의 정책이 비디오를 허용 하지 않도록 설정 되어 있기 때문에 Daniela 모임에서 비디오를 켤 수 없습니다 Amanda. Amanda는 모임의 다른 참가자가 공유 하는 비디오를 볼 수 있습니다.

Amanda에서 호스팅하는 모임에서 할당 된 비디오 정책에 관계 없이 비디오를 켤 수 없습니다. 이는 Daniela에서 Amanda의 모임에서 비디오를 켤 수 없음을 의미 합니다.  

Daniela에서 비디오를 사용 하 여 Amanda를 호출 하는 경우 Amanda는 오디오 만으로 전화를 받을 수 있습니다.  통화가 연결 되 면 Amanda에서 Daniela의 비디오를 볼 수 있지만 영상 통화는 켜지 지 않습니다. Amanda에서 Daniela를 호출 하는 경우 Daniela는 비디오 및 오디오로 전화를 받을 수 있습니다. 통화가 연결 되 면 필요에 따라 Daniela에서 비디오를 켜거나 끌 수 있습니다.

### <a name="media-bit-rate-kbs"></a>미디어 비트 전송률 (Kbs)

이것은 사용자별 정책입니다. 이 설정에 따라 사용자에 대 한 통화 및 모임에서 오디오, 비디오 및 비디오 기반 앱 공유 전송의 미디어 비트 전송률이 결정 됩니다. 통화 또는 모임에서 사용자의 업링크 및 다운 링크 미디어 트래버스 둘 다에 적용 됩니다. 이 설정을 사용 하면 조직의 대역폭을 관리 하는 방법을 세부적으로 제어할 수 있습니다. 사용자에 게 필요한 모임 시나리오에 따라 좋은 품질 환경을 위해 적절 한 대역폭을 확보 하는 것이 좋습니다. 최소값은 30kbps이 고 최대값은 모임 시나리오에 따라 달라 집니다. 팀에서 좋은 음질의 모임, 통화, 라이브 이벤트에 권장 되는 최소 대역폭에 대해 자세히 알아보려면 [대역폭 요구 사항을](prepare-network.md#bandwidth-requirements)참조 하세요.

모임에 대 한 대역폭이 충분 하지 않은 경우 참가자는 네트워크 품질이 좋지 않다는 메시지가 표시 됩니다.

CEO 보드 모임 및 팀 라이브 이벤트와 같이 고품질의 비디오 환경을 필요로 하는 모임의 경우 대역폭을 10mbps로 설정 하는 것이 좋습니다. 최대 환경이 설정 된 경우에도 시나리오에 따라 특정 네트워크 조건이 감지 되는 경우 팀 미디어 스택이 낮은 대역폭 조건에 적응 합니다. 

## <a name="meeting-policy-settings---content-sharing"></a>모임 정책 설정-콘텐츠 공유

- [화면 공유 모드](#screen-sharing-mode)
- [참가자가 제어권을 부여 하거나 요청할 수 있도록 허용](#allow-a-participant-to-give-or-request-control)
- [외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용](#allow-an-external-participant-to-give-or-request-control)
- [PowerPoint 공유 허용](#allow-powerpoint-sharing)
- [화이트 보드 허용](#allow-whiteboard)
- [공유 메모 허용](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>화면 공유 모드

이는 구성 단위 및 사용자별 정책 조합입니다. 이 설정은 사용자의 모임에서 데스크톱 및/또는 창 공유를 허용할지 여부를 제어 합니다. 배정 된 정책이 없는 모임 참가자 (예: 익명, 게스트, B2B, 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.

|값 설정 |결과가  |
|---------|---------|
|**전체 화면**    | 모임에서 전체 데스크톱 공유 및 응용 프로그램 공유를 허용 합니다. |
|**단일 응용 프로그램**   | 모임에서 응용 프로그램 공유가 허용 됨        |
|**비활성화**     |모임에서 화면 공유 및 응용 프로그램 공유 기능을 해제 했습니다.       |

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책 |화면 공유 모드 |
|---------|---------|---------|
|Daniela  | 전역   | 전체 화면 |
|Amanda   | Location1MeetingPolicy  | 비활성화 |

Daniela에서 호스팅하는 모임은 모임 참가자가 전체 화면 또는 특정 응용 프로그램을 공유할 수 있습니다. Amanda 참가 Daniela의 모임이 Amanda, 화면을 공유할 수 없거나, 정책 설정에 따라 특정 응용 프로그램을 사용 하지 않는 것입니다. Amanda에서 호스트 하는 모임에서는 자신에 게 할당 된 화면 공유 모드 정책에 관계 없이 화면 또는 단일 응용 프로그램을 공유할 수 없습니다. 즉, Daniela는 Amanda 모임의 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.  

현재 사용자는 Google Chrome을 사용 하는 경우 팀 모임에서 비디오를 재생 하거나 화면을 공유할 수 없습니다.

### <a name="allow-a-participant-to-give-or-request-control"></a>참가자가 제어권을 부여 하거나 요청할 수 있도록 허용

이것은 사용자별 정책입니다. 이 설정은 사용자가 공유 데스크톱 또는 창을 다른 모임 참가자에 게 제어권을 부여할 수 있는지 여부를 제어 합니다. 컨트롤을 제공 하려면 화면 위쪽을 마우스로 가리킵니다. 

사용자에 대해이 설정이 설정 된 경우 **제어권 제공** 옵션이 공유 세션의 위쪽 표시줄에 표시 됩니다. 

![제어권 제공 옵션을 보여 주는 스크린샷](media/meeting-policies-give-control.png)

사용자에 대해 설정이 꺼져 있으면 **제어권 제공** 옵션을 사용할 수 없습니다.

![제어권 부여 옵션을 사용할 수 없음을 보여 주는 스크린샷](media/meeting-policies-give-control-not-available.png)

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |참가자가 제어권을 부여 하거나 요청할 수 있도록 허용 |
|---------|---------|---------|
|Daniela   | 전역   | False       |
|Babek    | Location1MeetingPolicy        | 해제   |

Daniela는 다른 참가자에 게 제어권을 부여할 수 없기 때문에 Babek에서 구성한 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어 합니다.

PowerShell을 사용 하 여 제어권을 제공 하거나 제어권 요청을 받을 수 있는 사람을 제어 하려면 AllowParticipantGiveRequestControl cmdlet을 사용 합니다.

> [!NOTE]
> 공유 중 공유 콘텐츠를 관리 하 고 제어 하려면 두 파티 모두 팀 데스크톱 클라이언트를 사용 해야 합니다. 컨트롤은 어느 쪽이든 브라우저에서 Teams를 실행 중인 경우 지원되지 않습니다. 이것은 해결하려고 하는 기술적 제한 때문입니다. 

### <a name="allow-an-external-participant-to-give-or-request-control"></a>외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용

이것은 사용자별 정책입니다. 이 설정은 모임의 외부 참가자가 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어할 수 있는지 여부를 제어 합니다. 팀 회의의 외부 참가자는 다음과 같이 분류할 수 있습니다.  

- 익명 사용자
- 게스트 사용자  
- B2B 사용자
- 페더레이션 사용자  

공유 된 사용자가 외부 참가자가 조직에서 **제어권을 부여 하거나 요청할 수 있도록 허용을** 제어 하도록 설정 되어 있는 동안 페더레이션 사용자가 해당 사용자에 게 제어권을 부여할 수 있는지 여부

PowerShell을 사용 하 여 외부 참가자가 제어권을 제공 하거나 제어권 요청을 수락할 수 있는지 여부를 제어 하려면 AllowExternalParticipantGiveRequestControl cmdlet을 사용 합니다.

### <a name="allow-powerpoint-sharing"></a>PowerPoint 공유 허용

이것은 사용자별 정책입니다. 이 설정은 사용자가 모임에서 PowerPoint 슬라이드 데크를 공유할 수 있는지 여부를 제어 합니다. 익명, 게스트, 페더레이션 사용자를 비롯 한 외부 사용자가 모임 이끌이의 정책을 상속 합니다.

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |PowerPoint 공유 허용 |
|---------|---------|---------|
|Daniela   | 전역   | False       |
|Amanda   | Location1MeetingPolicy        | 해제   |

Amanda 모임 이끌이 인 경우에도 모임에서 PowerPoint 슬라이드 데크를 공유할 수 없습니다. Daniela는 모임이 Amanda으로 구성 된 경우에도 PowerPoint 슬라이드 데크를 공유할 수 있습니다. Amanda는 PowerPoint 슬라이드 데크를 공유할 수는 없지만 모임에서 다른 사용자가 공유한 PowerPoint 슬라이드 데크를 볼 수 있습니다.

### <a name="allow-whiteboard"></a>화이트 보드 허용

이것은 사용자별 정책입니다. 이 설정은 사용자가 모임에서 화이트 보드를 공유할 수 있는지 여부를 제어 합니다. 익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다. 

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |화이트 보드 허용|
|---------|---------|---------|
|Daniela   | 전역   | False       |
|Amanda   | Location1MeetingPolicy        | 해제   |

Amanda 모임 이끌이 인 경우에도 모임에서 화이트 보드를 공유할 수 없습니다. Daniela는 모임이 Amanda으로 구성 된 경우에도 화이트 보드를 공유할 수 있습니다.  

### <a name="allow-shared-notes"></a>공유 메모 허용

이것은 사용자별 정책입니다. 이 설정은 사용자가 모임에서 노트를 만들고 공유할 수 있는지 여부를 제어 합니다. 익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다. **모임 메모** 탭은 현재 20 명 미만의 참가자가 있는 모임 에서만 지원 됩니다.

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |공유 메모 허용 |
|---------|---------|---------|
|Daniela   | 전역   | False       |
|Amanda   | Location1MeetingPolicy | 해제 |

Daniela는 Amanda의 모임에 메모를 기록 하 고 모든 모임에서 메모를 찍을 수 없습니다.

## <a name="meeting-policy-settings---participants--guests"></a>모임 정책 설정-게스트 & 참가자

이 설정은 모임에 참가 하기 전에 대기실에서 대기 하는 모임 참가자와 모임에서 허용 되는 참여 수준을 제어 합니다.

- [익명 사용자가 모임을 시작 하도록 허용](#let-anonymous-people-start-a-meeting)
- [자동으로 사람들의 입장](#automatically-admit-people)
- [전화 접속 사용자가 대기실를 우회할 수 있도록 허용](#allow-dial-in-users-to-bypass-the-lobby)
- [라이브 캡션 사용](#enable-live-captions)
- [모임에서 채팅 허용](#allow-chat-in-meetings)

> [!NOTE]
>모임에 참가 하는 옵션은 각 팀 그룹의 설정 및 연결 방법에 따라 달라 집니다. 그룹에 오디오 회의가 있고이를 사용 하 여 연결 하는 경우 [Office 365의 오디오 회의](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)를 참조 하세요. 팀 그룹에 오디오 회의가 없는 경우 [팀에서 모임 참가](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)를 참조 하세요.

### <a name="let-anonymous-people-start-a-meeting"></a>익명 사용자가 모임을 시작 하도록 허용

회의 모임에서 leaderless 전화 걸기를 허용 하는 이끌이 별 정책입니다. 이 설정은 사용자가 전화 접속을 통해 조직에서 인증 된 사용자 없이 모임에 참가할 수 있는지 여부를 제어 합니다. 기본값은 False 이며, 사용자의 전화 접속은 조직의 인증 된 사용자가 모임에 참가할 때까지 대기실에서 대기 합니다. 

**참고** False 인 경우 전화 접속 사용자가 모임에 먼저 참가 하 고 대기실에 배치 된 경우 조직 사용자는 팀 클라이언트와 모임에 참가 하 여 사용자가 대기실에서 작업을 허용 해야 합니다. 사용자에 게 전화를 걸 수 있는 로비 컨트롤이 없습니다. 


### <a name="automatically-admit-people"></a>자동으로 사람들의 입장

이는 이끌이 별 정책입니다. 이 설정은 사용자가 인증 된 사용자가 참여 하 게 될 때까지 자신이 모임에 직접 참가 하거나 대기실에서 대기할지 여부를 제어 합니다. 이 설정은 사용자의 전화 접속에는 적용 되지 않습니다. 

![대기실에 사용자가 있는 모임을 보여 주는 스크린샷](media/meeting-policies-lobby.png)

 모임 이끌이는 모임 초대에서 **모임 옵션** 을 클릭 하 여 자신이 예약한 각 모임에 대해이 설정을 변경할 수 있습니다.
 
 **참고** 모임 옵션에 "대기실를 무시할 수 있는 사람" 이라고 표시 된 설정
  
|값 설정  |조인 동작 |
|---------|---------|
|**모든 사용자**   |모든 모임 참가자는 대기실에서 대기 하지 않고 바로 모임에 참가 합니다. 여기에는 인증 된 사용자, 신뢰할 수 있는 조직 (페더레이션된)의 외부 사용자, 게스트 및 익명 사용자가 포함 됩니다.     |
|**조직 및 페더레이션된 조직의 모든 사용자**     |게스트 사용자와 신뢰할 수 있는 조직의 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.  익명 사용자가 대기실에서 대기 합니다.   |
|**조직의 모든 사용자**    |게스트 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.  신뢰할 수 있는 조직과 익명 사용자의 사용자가 대기실에서 대기 합니다. 기본 설정입니다.           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>전화 접속 사용자가 대기실를 우회할 수 있도록 허용

이는 이끌이 별 정책입니다. 이 설정은 전화를 통해 전화를 거는 사용자가 모임에 직접 참가 하거나 **자동으로** 허용 되는 사용자 설정에 관계 없이 대기실에서 대기할지 여부를 제어 합니다. 기본값은 False입니다. False 인 경우 전화 접속 사용자는 조직 사용자가 팀 클라이언트와 모임에 참가 하 고 입장할 때까지 대기실에서 대기 합니다. True 인 경우 사용자의 전화 접속은 조직 사용자가 모임에 참가할 때 자동으로 모임에 참가 합니다. 

**참고** 조직 사용자가 모임에 참가 하기 전에 전화 접속 사용자가 모임에 참가 하는 경우 조직 사용자가 팀 클라이언트를 사용 하 여 모임에 참가 하 고 입장할 때까지 로비에 배치 됩니다. 


### <a name="enable-live-captions"></a>라이브 캡션 사용

이것은 사용자별 정책으로 모임 중에 적용 됩니다. 이 설정은 사용자가 참석할는 모임에서 실시간 **캡션 켜기** 옵션을 사용 하 여 live 캡션을 켜고 끌 것인지 여부를 제어 합니다.  

![라이브 캡션 켜기 옵션을 보여 주는 스크린샷](media/meeting-policies-live-captions.png)

|값 설정 |결과가  |
|---------|---------|
|**사용 하지 않도록 설정 되어 있지만 사용자가 무시할 수 있음**     | Live 캡션은 모임 중에 사용자에 대해 자동으로 설정 되지 않습니다. 사용자는 오버플로 (**...**) 메뉴에서 **라이브 캡션 켜기** 옵션을 표시 하 여 설정 합니다. 기본 설정입니다. |
|**비활성화**     | 모임 중에는 사용자가 실시간 캡션을 사용할 수 없습니다. 사용자는이 옵션을 켤 수 없습니다.          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>모임에서 채팅 허용

이는 이끌이 별 정책입니다. 이 설정은 사용자의 모임에서 모임 채팅을 허용할지 여부를 제어 합니다.

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a>모임 정책 설정-지정 된 발표자 역할 모드

이것은 사용자별 정책입니다. 이 설정을 사용 하면 팀 클라이언트의 **모임 옵션** 에서 설정할 **수 있는 사용자** 의 기본값을 변경할 수 있습니다. 이 정책 설정은 모임 시작 모임을 포함 하 여 모든 모임에 영향을 줍니다.

**누가 발표할 수 있나요?** 모임 이끌이가 모임에 발표자가 될 수 있는 사용자를 선택 하면이 설정을 사용 합니다. 자세히 알아보려면 [팀 모임에서](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019) [팀 모임 및 역할에 대 한 참가자 설정 변경을](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 참조 하세요.

현재는 PowerShell을 사용 하 여이 정책 설정을 구성할 수만 있습니다. [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용 하 여 기존 팀 모임 정책을 편집할 수 있습니다. 또는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용 하 여 새 팀 모임 정책을 만들고 사용자에 게 할당 합니다.

**표시할 수 있는 사용자** 의 기본값을 지정 하려면 팀에서 **DesignatedPresenterRoleMode** 매개 변수를 다음 중 하나로 설정 합니다.

- **EveryoneUserOverride**: 모든 모임 참가자는 발표자가 될 수 있습니다. 기본값입니다. 이 매개 변수는 팀의 **모든 사용자** 설정에 해당 합니다.
- **EveryoneInCompanyUserOverride**: 게스트 사용자를 포함 하 여 조직에서 인증 된 사용자가 발표자가 될 수 있습니다. 이 매개 변수는 팀의 **조직 내 사용자** 설정에 해당 합니다.
- **EveryoneInSameAndFederatedCompanyUserOverride**: 게스트 사용자 및 페더레이션된 조직의 사용자를 포함 하 여 조직에서 인증 된 사용자가 발표자가 될 수 있습니다. 이 매개 변수는 **조직의 사용자 및 팀의 신뢰할 수 있는 조직** 설정에 해당 합니다.
- **OrganizerOnlyUserOverride**: 모임 이끌이만 발표자가 될 수 있으며 모든 모임 참가자가 참석자로 지정 됩니다. 이 매개 **변수는 팀의 자신만 설정** 에 해당 합니다.

기본값을 설정한 후에도 모임 이끌이는 팀에서이 설정을 변경 하 고 자신이 예약한 모임에 발표할 수 있는 사람을 선택할 수 있다는 점에 유의 하세요.

## <a name="meeting-policy-settings---meeting-attendance-report"></a>모임 정책 설정-모임 참석 보고서

이것은 사용자별 정책입니다. 이 설정은 모임 이끌이가 [모임 참석 보고서](teams-analytics-and-reports/meeting-attendance-report.md)를 다운로드할 수 있는지 여부를 제어 합니다.

현재는 PowerShell을 사용 하 여이 정책 설정을 구성할 수만 있습니다. [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용 하 여 기존 팀 모임 정책을 편집할 수 있습니다. 또는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용 하 여 새 팀 모임 정책을 만들고 사용자에 게 할당 합니다.

모임 이끌이가 모임 참석 보고서를 다운로드 하도록 설정 하려면 **AllowEngagementReport** 매개 변수를 **Enabled**로 설정 합니다. 이 설정을 사용 하면 **참가자** 창에 보고서를 다운로드 하는 옵션이 표시 됩니다.

모임 이끌이가 보고서를 다운로드 하지 못하도록 하려면 매개 변수를 **Disabled**로 설정 합니다. 기본적으로이 설정은 비활성화 되어 있으며 보고서를 다운로드 하는 옵션을 사용할 수 없습니다.

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a>모임 정책 설정-제도 모드의 모임 공급자

이것은 사용자별 정책입니다. 이 설정은 *아일랜드 모드에 있는 사용자*에 게 어떤 Outlook 모임 추가 기능을 사용 하는 지를 제어 합니다. 사용자가 팀 모임 추가 기능을 사용할 수 있는지, 팀 모임이 나 비즈니스용 Skype 모임 추가 기능을 모두 사용 하 여 Outlook에서 모임을 예약할 수도 있습니다.

이 정책은 아일랜드 모드에 있는 사용자 에게만 적용할 수 있으며 팀 모임 정책에서 **AllowOutlookAddIn** 매개 변수를 **True** 로 설정 합니다.

현재는 PowerShell을 사용 하 여이 정책을 설정할 수 있습니다. [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용 하 여 기존 팀 모임 정책을 편집할 수 있습니다. 또는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용 하 여 새 팀 모임 정책을 만들고 사용자에 게 할당 합니다.

사용자에 게 제공 하려는 모임 추가 기능을 지정 하려면 다음과 같이 **PreferredMeetingProviderForIslandsMode** 매개 변수를 설정 합니다.

- Outlook에서 팀 모임 추가 기능 및 비즈니스용 Skype 추가 기능을 모두 사용 하도록 매개 변수를 **TeamsAndSfB** 로 설정 합니다. 기본값입니다.
- Outlook에서 팀 모임 추가 기능만 사용 하도록 매개 변수를 **Teamsonly** 설정 합니다. 이 정책 설정은 이후의 모든 모임에 팀 모임 참가 링크가 있는지 확인 합니다. 팀에 대 한 기존 비즈니스용 Skype 모임 참가 링크는 마이그레이션하지 않습니다. 이 정책 설정은 현재 상태, 채팅, PSTN 통화 또는 비즈니스용 Skype의 기타 기능에는 영향을 주지 않으며,이는 사용자가 이러한 기능을 위해 계속 해 서 비즈니스용 Skype를 사용 하는 것을 의미 합니다.

  매개 변수를 **Teamsonly**으로 설정한 다음 **TeamsAndSfB**로 다시 전환 하면 두 모임 추가 기능이 모두 사용 됩니다. 그러나 기존 팀 모임 참가 링크는 비즈니스용 Skype로 마이그레이션되지 않습니다. 변경 후에 예약 된 비즈니스용 Skype 모임에는 비즈니스용 Skype 모임 참가 링크가 있습니다.

## <a name="meeting-policy-settings---video-filters-mode"></a>모임 정책 설정-비디오 필터 모드

이것은 사용자별 정책입니다. 이 설정은 사용자가 모임에서 비디오 배경을 사용자 지정할 수 있는지 여부를 제어 합니다.

현재는 PowerShell을 사용 하 여이 정책을 설정할 수 있습니다. [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용 하 여 기존 팀 모임 정책을 편집할 수 있습니다. 또는 [새 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용 하 여 새 팀 모임 정책을 만든 다음 사용자에 게 정책을 할당 합니다.

사용자가 모임에서 비디오 배경을 사용자 지정할 수 있는지 여부를 지정 하려면 다음과 같이 **VideoFiltersMode** 매개 변수를 설정 합니다.

|PowerShell에서 값 설정 |결과가  |
|---------|---------|
|**NoFilters**     |사용자가 비디오 배경을 사용자 지정할 수 없습니다.|
|**BlurOnly**     |사용자가 비디오 배경을 흐리게 하는 옵션을 선택할 수 있습니다. |
|**BlurandDefaultBackgrounds**     |사용자는 비디오 배경을 흐리게 하거나 배경으로 사용할 이미지 집합 중에서 선택할 수 있습니다. |
|**AllFilters**     |사용에는 비디오 배경을 흐리게 하거나, 이미지 집합에서 선택 하거나, 배경으로 사용할 사용자 지정 이미지를 업로드 하는 옵션이 있습니다. |

> [!NOTE]
> 사용자가 업로드 한 이미지는 팀에 의해 차단 되지 않습니다. **Allfilters** 설정을 사용 하는 경우 사용자가 공격적인 또는 부적절 한 이미지를 업로드 하거나 조직에 팀 모임 배경에 사용할 권한이 없는 이미지를 보호 하기 위한 내부 조직 정책이 있어야 합니다.

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [팀에서 사용자에 게 정책 할당](assign-policies.md)
