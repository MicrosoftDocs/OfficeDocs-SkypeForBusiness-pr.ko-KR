---
title: 참가자 및 게스트에 대한 모임 정책 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 참가자 및 게스트의 모임 정책 설정을 Teams 자세히 알아보고
ms.openlocfilehash: b377c1c391f1fb3a82976db6d58e84c9eb2f9b94
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728637"
---
# <a name="meeting-policy-settings---participants--guests"></a>모임 정책 설정 - 참가자 및 게스트

<a name="bkmeetingparticipants"> </a>

이러한 설정은 참가자가 대기실에서 대기한 후에 모임 입장이 허락되는 모임과 모임에서 참가자에게 허용되는 참여 수준을 제어합니다.

- [익명 사용자의 모임 시작 허용](#let-anonymous-people-start-a-meeting)
- [자동으로 사용자 입장](#automatically-admit-people)
- [전화 접속 사용자의 대기실 우회 허용](#allow-dial-in-users-to-bypass-the-lobby)
- [라이브 캡션 사용](#enable-live-captions)
- [모임에서 채팅 허용](#allow-chat-in-meetings)

> [!NOTE]
>모임 참가 옵션은 각 Teams 그룹의 설정 및 연결 방법에 따라 다릅니다. 그룹에 오디오 회의 옵션이 있고 해당 옵션을 사용하여 연결하는 경우 [오디오 회의](/microsoftteams/audio-conferencing-in-office-365)를 참조하세요. Teams 그룹에 오디오 회의 옵션이 없는 경우 [Teams에서 모임 참가](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)를 참조하세요.

## <a name="let-anonymous-people-start-a-meeting"></a>익명 사용자의 모임 시작 허용

이 설정은 지시자가 없는 전화 접속 회의 모임을 허용하는 조직자당 정책입니다. 이 설정은 전화 접속 사용자가 조직의 인증된 사용자가 참석하지 않고 모임에 참가할 수 있는지 여부를 제어합니다. 기본적으로 이 설정은 해제되어 전화 접속 사용자가 조직의 인증된 사용자가 모임에 참가할 때까지 로비에서 대기합니다.

> [!NOTE]
> 이 설정을 해제하고 전화 접속 사용자가 모임에 먼저 참가하고 로비에 배치되는 경우 조직 사용자는 로비에서 사용자를 Teams 클라이언트와 모임에 참가해야 합니다. 전화 접속 사용자는 대기실 컨트롤을 사용할 수 없습니다.

## <a name="automatically-admit-people"></a>자동으로 사용자 입장

이 설정은 이끌이별 정책입니다. 이 설정으로 사용자가 바로 모임에 참가할지 아니면 인증된 사용자의 인정을 받을 때까지 대기실에서 대기하는지 여부를 제어합니다. 이 설정은 전화 접속 사용자에게는 적용되지 않습니다.

![로비에서 사용자와의 모임을 보여주는 스크린샷.](media/meeting-policies-lobby.png)

 모임 이끌이는  모임 초대에서 모임 옵션을 클릭하여 예약한 각 모임에 대해 이 설정을 변경할 수 있습니다.

> [!NOTE]
> 모임 옵션에서 설정에는 "대기실을 무시할 수 있는 사용자"라는 레이블이 지정됩니다. 아무 사용자에 대해서든 기본 설정을 변경하는 경우 해당 사용자가 이끄는 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 변경된 설정이 적용됩니다.
  
|설정값  |참가 동작 |
|---------|---------|
|**모든 사용자**   |모든 모임 참가자가 대기실에서 기다리지 않고 바로 모임에 참가합니다. 여기에는 인증된 사용자, 신뢰할 수 있는 조직의 외부 사용자(페더레이션), 게스트 및 익명 사용자도 포함됩니다.     |
|**내 조직의 사용자 및 게스트**     |게스트 사용자를 포함하여 조직 내에서 인증된 사용자는 로비에서 대기하지 않고 직접 모임에 참가합니다. 신뢰할 수 있는 조직의 사용자 및 익명 사용자가 로비에서 대기합니다. 기본 설정입니다.    |
|**내 조직의 사용자, 신뢰할 수 있는 조직 및 게스트**     |게스트 사용자 및 신뢰할 수 있는 조직의 사용자를 포함하여 조직 내 인증된 사용자는 대기실에서 기다리지 않고 바로 모임에 참가합니다.  익명 사용자는 대기실에서 기다립니다.   |
|**내 조직의 사용자**    |조직 내에서 인증된 사용자가 로비에서 대기하지 않고 직접 모임에 참가합니다.  신뢰할 수 있는 조직, 게스트 사용자 및 익명 사용자의 사용자가 로비에서 대기합니다.          |
|**모임 이끌이만**    |모임 이끌이만 대기실에서 기다리지 않고 바로 모임에 참가할 수 있습니다. 조직 내의 인증된 사용자, 게스트 사용자, 신뢰할 수 있는 조직의 사용자 및 익명 사용자를 포함하여 다른 모든 사용자는 로비에서 대기해야 합니다. 클라이언트 Teams 옵션 페이지에서 "나만"으로 표시됩니다.          |
|**초대된 사용자만**    |초대된 사용자 및 모임 이끌이만 로비에서 대기하지 않고 직접 모임에 참가할 수 있습니다. 조직 내의 인증된 사용자, 게스트 사용자, 신뢰할 수 있는 조직의 사용자 및 익명 사용자를 포함하여 다른 모든 사용자는 로비에서 대기해야 합니다. 클라이언트 Teams 옵션 페이지에서 "초대하는 사용자"로 표시됩니다.          |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>전화 접속 사용자의 대기실 우회 허용

이 설정은 이끌이별 정책입니다. 이 설정으로 전화 접속한 참가자가 **자동으로 사용자 입장** 설정과 관계없이 바로 모임에 참가할지 아니면 대기실에서 기다릴지를 제어합니다. 기본적으로 이 설정은 꺼져 잇습니다. 이 설정을 끄면 전화 접속 사용자는 조직 사용자가 Teams 클라이언트에서 모임에 참가하여 입장을 허락할 때까지 대기실에서 기다립니다. 이 설정이 켜져 있는 경우 전화 접속 사용자는 조직 사용자가 모임에 참가할 때 자동으로 모임에 참가합니다.

> [!NOTE]
> 조직 사용자가 모임에 참가하기 전에 전화 접속 사용자가 모임에 참가하는 경우 조직 사용자가 Teams 클라이언트를 사용하여 모임에 참가한 다음 해당 전화 접속 사용자를 인정할 때까지 대기실에 배치됩니다. 아무 사용자에 대해서든 기본 설정을 변경하는 경우 해당 사용자가 이끄는 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 변경된 설정이 적용됩니다.

## <a name="enable-live-captions"></a>라이브 캡션 사용

이 설정은 사용자당 정책으로 모임 중에 적용됩니다. 이 설정으로 사용자가 참석하는 모임에서 사용자가 라이브 캡션을 설정 및 해제하는 데 **라이브 캡션 켜기** 옵션을 사용할 수 있는지 여부를 제어합니다.  

![라이브 캡션 켜기 옵션을 보여주는 스크린샷입니다.](media/meeting-policies-live-captions.png)

|설정값 |동작  |
|---------|---------|
|**사용하지 않도록 설정되었지만 사용자 재정의 가능**     | 라이브 캡션 기능은 모임 중인 사용자에 대해 자동으로 설정되어 있지 않습니다. 사용자가 기능을 켜도록 넘침 단추(**...**) 메뉴에서 **라이브 캡션 켜기** 옵션이 보입니다. 기본 설정입니다. |
|**사용 안 함**     | 라이브 캡션 기능이 모임 중인 사용자에 대해 비활성화되었습니다. 사용자에게 이 기능을 켜는 옵션이 없습니다.          |

<a name="bkcontentsharing"> </a>

## <a name="allow-chat-in-meetings"></a>모임에서 채팅 허용

이 설정은 참가자당 설정입니다. 이 설정으로 사용자 모임에서 모임 채팅을 허용할지 여부를 제어합니다.

<a name="bkparticipantsandguests"> </a>






## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](assign-policies.md)
- [사용자의 RestrictedAnonymousAccess Teams 모임 정책 삭제](meeting-policies-restricted-anonymous-access.md)
