---
title: 참가자 및 게스트에 대한 모임 정책 관리
ms.author: mabond
author: mkbond007
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
description: 참가자 및 게스트에 대한 Teams에서 모임 정책 설정을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 42321eb1edadeda928ab0cb9e78e166478b73ed9
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436674"
---
# <a name="meeting-policy-settings---participants--guests"></a>모임 정책 설정 - 참가자 및 게스트

<a name="bkmeetingparticipants"> </a>

이러한 설정은 모임 참가자가 모임에 참가하기 전에 대기하는 모임 참가자와 모임에 참가할 수 있는 수준을 제어합니다.

- [익명 사용자가 모임에 참가하도록 허용](#let-anonymous-people-join-a-meeting)
- [익명 사용자의 모임 시작 허용](#let-anonymous-people-start-a-meeting)
- [모임에 참석할 수 있는 사람](#who-can-present-in-meetings)
- [자동으로 사용자 입장](#automatically-admit-people)
- [전화 접속 사용자는 로비를 우회할 수 있습니다.](#dial-in-users-can-bypass-the-lobby)
- [비공개 모임에서 지금 모임](#meet-now-in-private-meetings)
- [라이브 캡션](#live-captions)
- [모임에서 채팅](#chat-in-meetings)
- [Teams Q&A](#teams-qa)
- [모임 반응](#meeting-reactions)

이러한 설정은 참가자 & 게스트 섹션 **의** > **모임 모임 정책** 아래 Teams 관리 센터에서 **찾을 수 있습니다** .

> [!NOTE]
> 모임 참가 옵션은 각 Teams 그룹의 설정 및 연결 방법에 따라 다릅니다. 그룹에 오디오 회의 옵션이 있고 해당 옵션을 사용하여 연결하는 경우 [오디오 회의](/microsoftteams/audio-conferencing-in-office-365)를 참조하세요. Teams 그룹에 오디오 회의 옵션이 없는 경우 [Teams에서 모임 참가](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)를 참조하세요.

## <a name="let-anonymous-people-join-a-meeting"></a>익명 사용자가 모임에 참가하도록 허용

이 이끌이별 설정을 사용하면 누구나 모임 초대에서 링크를 선택하여 익명 사용자로 모임에 참가할 수 있습니다. 자세한 내용은 [Teams 계정 없이 모임에 참가](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)를 참조하세요. 익명 사용자의 모임 참가 기능도 조직 수준에서 제어되므로 더 제한적인 설정이 효과적입니다. 자세한 내용은 [Microsoft Teams 관리 센터를 사용하여 조직 전체 정책 구성을](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings) 참조하세요.

## <a name="let-anonymous-people-start-a-meeting"></a>익명 사용자의 모임 시작 허용

이 설정은 리더리스 전화 접속 회의 모임을 허용하는 이끌이별 정책입니다. 이 설정은 익명 사용자와 전화 접속 발신자가 조직의 인증된 사용자 없이 모임에 참가할 수 있는지 여부를 제어합니다. 기본적으로 이 설정은 꺼져 있습니다. 즉, 익명 사용자와 전화 접속 발신자는 조직의 인증된 사용자가 모임에 참가할 때까지 대기실에서 대기합니다.

> [!NOTE]
> 이 설정이 꺼져 있고 전화 접속 사용자가 먼저 모임에 참가하고 로비에 배치된 경우 조직 사용자는 Teams 클라이언트와 모임에 참가하여 로비에서 사용자를 허용해야 합니다. 전화 접속 사용자는 대기실 컨트롤을 사용할 수 없습니다.

## <a name="who-can-present-in-meetings"></a>모임에 참석할 수 있는 사람

사용자별 정책에 해당합니다. 이 설정으로 Teams 클라이언트의 **모임 옵션** 에서 **발표할 수 있는 사람** 설정 기본값을 변경합니다. 이 정책 설정은 지금 모임 시작 모임을 비롯한 모든 모임에 영향을 미칩니다.

**발표할 수 있는 사람** 설정을 통해 모임 이끌이는 모임의 발표자 역할을 할 수 있는 사람을 선택합니다. 자세한 내용은 [Teams 모임의 참가자 설정 변경](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e) 및 [Teams 모임에서의 역할](https://support.microsoft.com/office/c16fa7d0-1666-4dde-8686-0a0bfe16e019)을 참조하세요.

Teams에서 **누가 표시할 수 있나요?** 설정의 기본값을 지정하려면 정책에서 다음 설정 중 하나로 설정합니다.

- **이끌이는 재정의할 수 있지만 사용자는 재정의할 수 있습니다**. 모임 이끌이만 발표자가 될 수 있으며 모든 모임 참가자는 참석자로 지정됩니다. 이 매개 변수는 Teams의 **나만** 설정에 해당합니다.
- **조직의 모든 사용자가 재정의할 수 있습니다**. 게스트 사용자를 포함하여 조직의 인증된 사용자는 발표자가 될 수 있습니다. 이 설정은 Teams에서 **조직의 사람** 설정에 해당합니다.
- **사용자가 재정의할 수 있는 모든 사용자**: 모든 모임 참가자는 발표자가 될 수 있습니다. 이 값은 기본값입니다. 이 설정은 Teams의 **모든 사용자** 설정에 해당합니다.

기본값을 설정한 후에도 모임 이끌이는 여전히 Teams에서 이 설정을 변경하고 본인이 예약하는 모임에서 발표할 수 있는 사용자를 선택할 수 있습니다.

## <a name="automatically-admit-people"></a>자동으로 사용자 입장

이 설정은 이끌이별 정책입니다. 이 설정은 사용자가 직접 모임에 참가할지 아니면 인증된 사용자가 입장할 때까지 로비에서 대기할지를 제어합니다. 이 설정은 전화 접속 사용자에게는 적용되지 않습니다.

![사용자가 대기실에 있는 모임을 보여주는 스크린샷](media/meeting-policies-lobby.png)

 모임 이끌이는 모임 초대에서 **모임 옵션을** 클릭하여 예약하는 각 모임에 대해 이 설정을 변경할 수 있습니다.

> [!NOTE]
> In the meeting options the setting is labeled "Who can bypass the lobby". If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.
  
|설정값  |참가 동작 |
|---------|---------|
|**모든 사용자**   |모든 모임 참가자가 대기실에서 기다리지 않고 바로 모임에 참가합니다. 여기에는 인증된 사용자, 신뢰할 수 있는 조직의 사용자, 게스트 및 익명 사용자가 포함됩니다.     |
|**내 조직의 사용자 및 게스트**     |게스트를 포함하여 조직 내에서 인증된 사용자는 로비에서 기다리지 않고 직접 모임에 참가합니다. 신뢰할 수 있는 조직의 사용자와 익명 사용자는 대기실에서 기다립니다. 기본 설정입니다.    |
|**내 조직의 사용자, 신뢰할 수 있는 조직 및 게스트**     |게스트 및 신뢰할 수 있는 조직의 사용자를 포함하여 조직 내에서 인증된 사용자는 로비에서 기다리지 않고 직접 모임에 참가합니다.  익명 사용자는 대기실에서 기다립니다.   |
|**내 조직의 사용자**    |조직 내의 인증된 사용자는 로비에서 기다리지 않고 직접 모임에 참가합니다.  신뢰할 수 있는 조직, 게스트 및 익명 사용자의 사용자가 로비에서 대기합니다.          |
|**모임 이끌이만**    |모임 이끌이만 대기실에서 기다리지 않고 바로 모임에 참가할 수 있습니다. 조직 내의 인증된 사용자, 게스트, 신뢰할 수 있는 조직의 사용자 및 익명 사용자를 포함한 다른 모든 사용자는 로비에서 기다려야 합니다. Teams 클라이언트 모임 옵션 페이지에서 "나만"으로 표시됩니다.          |
|**초대된 사용자만**    |초대된 사용자 및 모임 이끌이만 로비에서 기다리지 않고 직접 모임에 참가할 수 있습니다. 조직 내의 인증된 사용자, 게스트, 신뢰할 수 있는 조직의 사용자 및 익명 사용자를 포함한 다른 모든 사용자는 로비에서 기다려야 합니다. Teams 클라이언트 모임 옵션 페이지에서 "초대할 사람"로 표시됩니다. 메일 그룹의 일부로 추가된 사용자는 로비를 통과해야 합니다.      |

 > [!NOTE]
> 신뢰할 수 있는 조직은 Teams에서 페더레이션된 통신을 허용하는 도메인입니다. Teams 관리 센터에서 외부 액세스에 **대한 모든 외부 도메인** 허용을 사용하도록 설정하면 Teams 조직 내의 모든 인증된 사용자를 신뢰할 수 있습니다. 허용되는 외부 도메인을 지정하고 다른 모든 도메인을 차단하도록 선택하면 허용된 도메인이 신뢰할 수 있는 조직이 됩니다. 차단된 도메인은 신뢰할 수 있는 조직이 아닌 것으로 간주됩니다.

## <a name="dial-in-users-can-bypass-the-lobby"></a>전화 접속 사용자는 로비를 우회할 수 있습니다.

이 설정은 이끌이별 정책입니다. 이 설정으로 전화 접속한 참가자가 **자동으로 사용자 입장** 설정과 관계없이 바로 모임에 참가할지 아니면 대기실에서 기다릴지를 제어합니다. 기본적으로 이 설정은 꺼져 잇습니다. 이 설정을 끄면 전화 접속 사용자는 조직 사용자가 Teams 클라이언트에서 모임에 참가하여 입장을 허락할 때까지 대기실에서 기다립니다. 이 설정이 켜져 있으면 조직 사용자가 Teams 클라이언트와 모임에 참가할 때 전화 접속 사용자가 자동으로 모임에 참가합니다.

> [!NOTE]
> 조직 사용자가 모임에 참가하기 전에 전화 접속 사용자가 모임에 참가하는 경우 조직 사용자가 Teams 클라이언트를 사용하여 모임에 참가한 다음 해당 전화 접속 사용자를 인정할 때까지 대기실에 배치됩니다. 아무 사용자에 대해서든 기본 설정을 변경하는 경우 해당 사용자가 이끄는 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 변경된 설정이 적용됩니다.

## <a name="meet-now-in-private-meetings"></a>비공개 모임에서 지금 모임

이 정책은 사용자별 정책에 해당하며 모임이 시작되기 전에 적용됩니다. 이 설정은 사용자가 계획되지 않은 비공개 모임을 시작할 수 있는지 여부를 제어합니다. 이 설정은 기본적으로 켜져 있습니다.

## <a name="live-captions"></a>라이브 캡션

이 설정은 사용자별 정책이며 모임 중에 적용됩니다. 이 설정으로 사용자가 참석하는 모임에서 사용자가 라이브 캡션을 설정 및 해제하는 데 **라이브 캡션 켜기** 옵션을 사용할 수 있는지 여부를 제어합니다.  

![라이브 캡션 켜기 옵션을 보여주는 스크린샷](media/meeting-policies-live-captions.png)

|설정값 |동작  |
|---------|---------|
|**사용하도록 설정되지 않았지만 사용자가 재정의할 수 있습니다.**     | 라이브 캡션 기능은 모임 중인 사용자에 대해 자동으로 설정되어 있지 않습니다. 사용자가 기능을 켜도록 넘침 단추(**...**) 메뉴에서 **라이브 캡션 켜기** 옵션이 보입니다. 기본 설정입니다. |
|**사용 안 함**     | 라이브 캡션 기능이 모임 중인 사용자에 대해 비활성화되었습니다. 사용자에게 이 기능을 켜는 옵션이 없습니다.          |

최종 사용자가 **라이브 캡션** 을 켜는 방법에 대한 자세한 내용은 [Teams 모임에서 라이브 캡션 사용을 참조하세요](https://support.microsoft.com/office/4be2d304-f675-4b57-8347-cbd000a21260).

### <a name="live-translated-captions"></a>라이브 번역 캡션

> [!NOTE]
> 이 기능은 공개 미리 보기에서 일시적으로 사용할 수 있습니다. 미리 보기가 끝나면 모임 이끌이는 참석자가 라이브 번역 캡션을 사용할 수 있는 Teams Premium 라이선스가 있어야 합니다.

기본적으로 **라이브 캡션은** 모임 중에 사용되는 언어로 표시됩니다. **라이브 번역 캡션을** 사용하면 사용자가 가장 편안한 언어로 번역된 캡션을 볼 수 있습니다.

**라이브 번역 캡션을** 사용하도록 설정하려면 **라이브 캡션을** 사용 안 됨으로 설정해야 하지만 사용자는 Teams 관리 센터에서 재정의할 **수 있습니다**. **라이브 번역 캡션을** 끄려면 이 캡션을 **사용 안** 됨으로 설정합니다.

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>모임에서 채팅

사용자별 및 이끌이별 정책입니다. 이 설정으로 사용자 모임에서 모임 채팅을 허용할지 여부를 제어합니다. 이 설정은 채널 모임에 적용되지 않습니다.

|설정값 |동작  |
|---------|---------|
|**모든 사용자에 대해 켜기**     | 모든 참가자는 채팅 메시지를 작성하고 볼 수 있습니다. |
|**모든 사용자에 대해 끄기**     | 모든 참가자에 대해 모임 채팅이 꺼져 있습니다.  |
|**익명 사용자를 제외한 모든 사용자에 대해 켜기**     | 익명 참가자에 대해서만 모임 채팅 쓰기 액세스가 해제됩니다.  |

**모임에서 이 채팅** 정책이 사용자에게 적용되면 이끌이는 **모임 옵션을** 통해 이 정책을 재정의할 수 없습니다.

모임 이끌이에 적용된 정책은 모임의 다른 사용자에게 영향을 줄 수 있습니다. 예를 들면 다음과 같습니다.

- 이끌이가 **모임에서 채팅** 을 **모든 사용자에 대해 켜** 기로 설정하거나 **익명 사용자를 제외한 모든 사용자에 대해 켜** 기로 설정한 경우 사용자의 개별 정책이 적용되고 모든 사용자가 모임에서 채팅을 할  수 없습니다.
- 이끌이가 **모임에서 채팅** 을 **모든 사용자에 대해 끄** 기로 설정한 경우 이끌이의 정책이 적용되고 아무도 모임에서 채팅할 수 없습니다.

<a name="bkparticipantsandguests"> </a>

## <a name="teams-qa"></a>Teams Q&A

이 설정은 이끌이별 정책입니다. 이 설정은 질문 & 답변 환경(Q&A)을 켜거나 끕니다.

이 설정은 모임을 만들거나 이끌이가 업데이트할 때 적용됩니다. 기본적으로 이 설정은 꺼져 있습니다. [Teams 모임의 Q&A에](/manage-qna-for-teams) 대해 자세히 알아보세요.

QnAEngagementMode 매개 변수는 PowerShell에서 이 정책을 제어합니다. Q&A는 Teams 관리 센터 내에서도 조정할 수 있습니다.

|설정값 |동작  |
|---------|---------|
|**설정**     | 이끌이는 모임을 만들 때 Q&A를 추가할 수 있습니다. |
|**해제**     | 이끌이는 모임을 만들 때 Q&A를 추가할 수 있는 옵션이 없습니다.  |

## <a name="meeting-reactions"></a>모임 반응

모임 반응은 기본적으로 켜집니다. 사용자의 반응 설정을 꺼도 사용자는 본인이 예약한 모임에서 반응을 사용할 수 있습니다. 모임 이끌이는 기본 설정에 관계없이 계속 모임 옵션 페이지에서 반응을 켤 수 있습니다.

## <a name="enable-meeting-policy-settings"></a>모임 정책 설정 사용

모임 정책 설정을 사용하도록 설정하려면 [Teams 관리 센터](https://admin.teams.microsoft.com/policies/meetings)(**모임 정책** >  참가자 **&** **정책** >  편집) 또는 Teams PowerShell의 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용할 수 있습니다. 

이 예제에서는 PowerShell을 사용하여 모든 사용자가 모임을 시작하거나 참가할 수 있도록 전역 모임 정책을 수정합니다.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

정책을 설정한 후에는 사용자에게 적용해야 합니다. 전역(조직 전체 기본값) 정책을 수정한 경우 사용자에게 자동으로 적용됩니다. 정책 변경 내용이 적용되려면 4시간 이상 기다려야 하지만 최대 24시간이 걸릴 수 있습니다.


## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
- [사용자의 RestrictedAnonymousAccess Teams 모임 정책 삭제](meeting-policies-restricted-anonymous-access.md)
