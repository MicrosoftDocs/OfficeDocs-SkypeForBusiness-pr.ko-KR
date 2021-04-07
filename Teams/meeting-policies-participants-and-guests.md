---
title: 참가자 및 게스트에 대한 모임 정책 관리
author: CarolynRowe
ms.author: crowe
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 참가자 및 게스트에 대한 Teams에서 모임 정책 설정을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598754"
---
# <a name="meeting-policy-settings---participants--guests"></a>모임 정책 설정 - 참가자 & 게스트

<a name="bkmeetingparticipants"> </a>

이러한 설정은 모임에 참가하기 전에 로비에서 대기하는 모임 참가자와 모임에서 허용되는 참여 수준을 제어합니다.

- [익명의 사용자가 모임을 시작할 수 있습니다.](#let-anonymous-people-start-a-meeting)
- [자동으로 인원을 인정합니다.](#automatically-admit-people)
- [전화 접속 사용자가 로비를 우회할 수 있도록 허용](#allow-dial-in-users-to-bypass-the-lobby)
- [라이브 캡션 사용](#enable-live-captions)
- [모임에서 채팅 허용](#allow-chat-in-meetings)

> [!NOTE]
>모임에 참가하는 옵션은 각 Teams 그룹의 설정 및 연결 방법에 따라 달라집니다. 그룹에 오디오 회의가 있으며 연결에 사용하는 경우 오디오 회의 [를 참조합니다.](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365) Teams 그룹에 오디오 회의가 없는 경우 Teams에서 모임 [참가를 참조합니다.](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)

## <a name="let-anonymous-people-start-a-meeting"></a>익명의 사용자가 모임을 시작할 수 있습니다.

이 설정은 지시자가 없는 전화 접속 회의 모임을 허용하는 조직자당 정책입니다. 이 설정은 전화 접속 사용자가 조직의 인증된 사용자가 참석하지 않고 모임에 참가할 수 있는지 여부를 제어합니다. 기본적으로 이 설정은 해제되어 전화 접속 사용자가 조직의 인증된 사용자가 모임에 참가할 때까지 로비에서 대기합니다.

> [!NOTE]
> 이 설정을 해제하고 전화 접속 사용자가 모임에 먼저 참가하고 로비에 배치되는 경우 조직 사용자는 Teams 클라이언트와 모임에 참가하여 로비에서 사용자를 인정해야 합니다. 사용자가 전화를 걸 때 사용할 수 있는 로비 컨트롤은 없습니다.

## <a name="automatically-admit-people"></a>자동으로 인원을 인정합니다.

구성자당 정책입니다. 이 설정은 인증된 사용자가 모임에 직접 참가할지 아니면 로비에서 대기할지 여부를 제어합니다. 이 설정은 전화 접속 사용자에게는 적용되지 않습니다.

![로비에서 사용자와의 모임을 보여주는 스크린샷](media/meeting-policies-lobby.png)

 모임 이끌이는  모임 초대에서 모임 옵션을 클릭하여 예약한 각 모임에 대해 이 설정을 변경할 수 있습니다.

> [!NOTE]
> 모임 옵션에서 설정에는 "로비를 무시할 수 있는 사용자"가 표시됩니다. 모든 사용자에 대한 기본 설정을 변경하면 해당 사용자가 구성한 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 적용됩니다.
  
|값 설정  |조인 동작 |
|---------|---------|
|**모든 사용자**   |모든 모임 참가자는 로비에서 대기하지 않고 직접 모임에 참가합니다. 여기에는 인증된 사용자, 신뢰할 수 있는 조직의 외부 사용자(페더리화), 게스트 및 익명 사용자가 포함됩니다.     |
|**조직 및 페더리드 조직의 모든 사용자**     |게스트 사용자 및 신뢰할 수 있는 조직의 사용자를 포함하여 조직 내의 인증된 사용자는 로비에서 대기하지 않고 직접 모임에 참가합니다.  익명 사용자는 로비에서 대기합니다.   |
|**조직의 모든 사용자**    |게스트 사용자를 포함하여 조직 내에서 인증된 사용자가 로비에서 대기하지 않고 직접 모임에 참가합니다.  신뢰할 수 있는 조직의 사용자 및 익명 사용자들이 로비에서 대기합니다. 기본 설정입니다.           |
|**이끌이만 해당**    |로비에서 대기하지 않고 모임 이끌이만 모임에 직접 참가할 수 있습니다. 조직 내의 인증된 사용자, 게스트 사용자, 신뢰할 수 있는 조직의 사용자 및 익명 사용자를 비롯한 다른 모든 사용자는 로비에서 대기해야 합니다.           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>전화 접속 사용자가 로비를 우회할 수 있도록 허용

구성자당 정책입니다. 이 설정은 전화로 전화로 전화 접속하는 사람이 모임에 직접 참가할지 아니면 자동으로 사용자 설정에 관계 없이 로비에서 대기하는지 여부를 **제어합니다.** 기본적으로 이 설정은 해제됩니다. 이 설정을 해제하면 조직 사용자가 Teams 클라이언트로 모임에 참가하고 이를 인정할 때까지 전화 접속 사용자는 로비에서 대기합니다. 이 설정이 설정되어 있는 경우 전화 접속 사용자는 조직 사용자가 모임에 참가할 때 자동으로 모임에 참가합니다.

> [!NOTE]
> 조직 사용자가 모임에 참가하기 전에 모임에 참가하는 경우 조직 사용자가 Teams 클라이언트를 사용하여 모임에 참가하고 해당 모임을 인정할 때까지 로비에 배치됩니다. 모든 사용자에 대한 기본 설정을 변경하면 해당 사용자가 구성한 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 적용됩니다.

## <a name="enable-live-captions"></a>라이브 캡션 사용

이 설정은 사용자당 정책으로 모임 중에 적용됩니다. 이 설정은 사용자가  참석하는 모임에서 라이브 캡션을 켜고 끄는 데 사용할 수 있는지 여부를 제어합니다.  

![라이브 캡션 켜기 옵션을 보여주는 스크린샷](media/meeting-policies-live-captions.png)

|값 설정 |동작  |
|---------|---------|
|**사용 안 했지만 사용자가 을재지할 수 있습니다.**     | 모임 중에 사용자에 대해 라이브 캡션이 자동으로 켜져 있지 않습니다. 사용자는 오버플로(...**)** 메뉴에서 라이브 캡션 켜기 옵션을 보고 해당 캡션을 켜는 옵션을 볼 수 있습니다.  기본 설정입니다. |
|**사용하지 않도록 설정**     | 모임 중에 사용자에 대해 라이브 캡션을 사용하지 않도록 설정됩니다. 사용자에게 설정하는 옵션이 없습니다.          |

<a name="bkcontentsharing"> </a>

## <a name="allow-chat-in-meetings"></a>모임에서 채팅 허용

이 설정은 참가자당 설정입니다. 이 설정은 사용자의 모임에서 모임 채팅이 허용되는지 여부를 제어합니다.

<a name="bkparticipantsandguests"> </a>






## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](assign-policies.md)
- [사용자로부터 RestrictedAnonymousAccesss Teams 모임 정책 제거](meeting-policies-restricted-anonymous-access.md)
