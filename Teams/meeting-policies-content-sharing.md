---
title: 콘텐츠 공유를 위한 모임 정책 관리
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
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: 콘텐츠 공유를 위해 Teams에서 모임 정책 설정을 관리하는 방법을 알아보겠습니다.
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598775"
---
# <a name="meeting-policy-settings---content-sharing"></a>모임 정책 설정 - 콘텐츠 공유

<a name="bkcontentsharing"> </a>

이 문서에서는 콘텐츠 공유와 관련된 다음 모임 정책 설정을 설명합니다.

- [화면 공유 모드](#screen-sharing-mode)
- [참가자가 제어를 제공하거나 요청할 수 있도록 허용](#allow-a-participant-to-give-or-request-control)
- [외부 참가자가 제어를 제공하거나 요청하도록 허용](#allow-an-external-participant-to-give-or-request-control)
- [PowerPoint 공유 허용](#allow-powerpoint-sharing)
- [화이트보드 허용](#allow-whiteboard)
- [공유 노트 허용](#allow-shared-notes)

## <a name="screen-sharing-mode"></a>화면 공유 모드

이 설정은 이끌이 및 사용자당 정책의 조합입니다. 이 설정은 사용자의 모임에서 데스크톱 및 창 공유가 허용되는지 여부를 제어합니다. 할당된 정책이 없는 모임 참가자(예: 익명, 게스트, B2B 및 페더리드 참가자)는 모임 이끌이의 정책을 상속합니다.

|값 설정 |동작  |
|---------|---------|
|**전체 화면**    | 모임에서 전체 데스크톱 공유 및 애플리케이션 공유가 허용됩니다. |
|**단일 애플리케이션**   | 모임에서 애플리케이션 공유가 허용됩니다.        |
|**사용하지 않도록 설정**     |모임에서 화면 공유 및 애플리케이션 공유가 해제됩니다.       |

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책 |화면 공유 모드 |
|---------|---------|---------|
|Daniela  | 전역   | 전체 화면 |
|Amanda   | Location1MeetingPolicy  | 사용하지 않도록 설정 |

Daniela에서 호스팅하는 모임을 사용하면 모임 참가자가 전체 화면 또는 특정 애플리케이션을 공유할 수 있습니다. Amanda가 Daniela의 모임에 참가하는 경우 Amanda는 자신의 정책 설정이 비활성화되어 화면 또는 특정 애플리케이션을 공유할 수 없습니다. Amanda가 호스팅하는 모임에서 할당된 화면 공유 모드 정책에 관계없이 누구도 자신의 화면 또는 단일 애플리케이션을 공유할 수 없습니다.  따라서 Daniela는 Amanda의 모임에서 자신의 화면 또는 단일 애플리케이션을 공유할 수 없습니다.  

현재 사용자는 Google Chrome을 사용하는 경우 Teams 모임에서 비디오를 재생하거나 화면을 공유할 수 없습니다.

## <a name="allow-a-participant-to-give-or-request-control"></a>참가자가 제어를 제공하거나 요청할 수 있도록 허용

이 설정은 사용자당 정책입니다. 이 설정은 사용자가 공유 데스크톱 또는 창을 다른 모임 참가자에게 제어할 수 있는지 여부를 제어합니다. 컨트롤을 제공하기 위해 화면 맨 위에 마우스를 다.

사용자에 대해 이 설정이 켜져 있는 경우 공유 세션의 맨 위에 컨트롤 제공 옵션이 표시됩니다. 

![제어권 제공 옵션을 보여 주는 스크린샷](media/meeting-policies-give-control.png)

사용자에 대한 설정이 꺼져  있는 경우 제어권 제공 옵션을 사용할 수 없습니다.

![제어권 제공 옵션을 사용할 수 없는 경우를 보여 주는 스크린샷](media/meeting-policies-give-control-not-available.png)

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |참가자가 제어를 제공하거나 요청할 수 있도록 허용 |
|---------|---------|---------|
|Daniela   | 전역   | 에서       |
|Babek    | Location1MeetingPolicy        | 끄기   |

Daniela는 Babek가 조직한 모임에서 다른 참가자에게 공유 데스크톱 또는 창을 제어할 수 있습니다. 그러나 Babek는 다른 참가자에게 제어를 줄 수 없습니다.

PowerShell을 사용하여 제어 요청을 제어하거나 수락할 수 있는 사용자 제어를 위해 AllowParticipantGiveRequestControl cmdlet을 사용 합니다.

> [!NOTE]
> 공유하는 동안 공유 콘텐츠를 주고 제어하려면 두 당사자가 Teams 데스크톱 클라이언트를 사용해야 합니다. 컨트롤은 어느 쪽이든 브라우저에서 Teams를 실행 중인 경우 지원되지 않습니다. 이것은 해결하려고 하는 기술적 제한 때문입니다.

## <a name="allow-an-external-participant-to-give-or-request-control"></a>외부 참가자가 제어를 제공하거나 요청하도록 허용

이 설정은 사용자당 정책입니다. 조직이 사용자에 대해 이 정책을 설정한지 여부는 모임 이끌이가 설정한 대상에 관계없이 외부 참가자가 할 수 있는 작업을 제어하지 않습니다. 이 매개 변수는 외부 참가자가 조직의 모임 정책 내에서 설정한 공유자가 설정한 대상에 따라 공유자 화면의 제어 또는 요청 제어를 부여할 수 있는지 여부를 제어합니다. Teams 모임의 외부 참가자는 다음과 같이 분류할 수 있습니다.  

- 익명 사용자
- 게스트 사용자  
- B2B 사용자
- 페더리드 사용자  

페더링된 사용자가 공유하는 동안 외부 사용자에게 제어를  줄 수 있는지 여부는 외부 참가자가 조직에서 제어 설정을 제공하거나 요청할 수 있도록 허용에 의해 제어됩니다.

PowerShell을 사용하여 외부 참가자가 제어 요청을 제어하거나 수락할 수 있는지 여부를 제어하기 위해 AllowExternalParticipantGiveRequestControl cmdlet을 사용 합니다.

### <a name="allow-powerpoint-sharing"></a>PowerPoint 공유 허용

사용자당 정책입니다. 이 설정은 사용자가 모임에서 PowerPoint 슬라이드 데크를 공유할 수 있는지 여부를 제어합니다. 익명, 게스트 및 페더리드 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 상속합니다.

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |PowerPoint 공유 허용 |
|---------|---------|---------|
|Daniela   | 전역   | 에서       |
|Amanda   | Location1MeetingPolicy        | 끄기   |

Amanda는 모임 이끌이인 경우에도 모임에서 PowerPoint 슬라이드 데크를 공유할 수 없습니다. Daniela는 Amanda에서 모임을 구성하는 경우에도 PowerPoint 슬라이드 데크를 공유할 수 있습니다. Amanda는 PowerPoint 슬라이드 데크를 공유할 수 없는 경우에도 모임에서 다른 사람이 공유하는 PowerPoint 슬라이드 데크를 볼 수 있습니다.

## <a name="allow-whiteboard"></a>화이트보드 허용

이 설정은 사용자당 정책입니다. 이 설정은 사용자가 모임에서 화이트보드를 공유할 수 있는지 여부를 제어합니다. 익명, B2B 및 페더리드 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 상속합니다.

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |화이트보드 허용|
|---------|---------|---------|
|Daniela   | 전역   | 에서       |
|Amanda   | Location1MeetingPolicy        | 끄기   |

Amanda는 모임 이끌이인 경우에도 모임에서 화이트보드를 공유할 수 없습니다. Daniela는 모임이 Amanda에서 구성되어 있는 경우에도 화이트보드를 공유할 수 있습니다.  

## <a name="allow-shared-notes"></a>공유 노트 허용

이 설정은 사용자당 정책입니다. 이 설정은 사용자가 모임에서 노트를 만들고 공유할 수 있는지 여부를 제어합니다. 익명, B2B 및 페더리드 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 상속합니다. 모임 **노트** 탭은 현재 20명 미만의 참가자가 있는 모임에서만 지원됩니다.

다음 예제를 살펴보겠습니다.

|사용자 |모임 정책  |공유 노트 허용 |
|---------|---------|---------|
|Daniela   | 전역   | 에서       |
|Amanda   | Location1MeetingPolicy | 끄기 |

Daniela는 Amanda의 모임에서 메모를 작성할 수 있으며 Amanda는 모임에서 메모를 기록할 수 없습니다.




## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](assign-policies.md)
- [사용자로부터 RestrictedAnonymousAccesss Teams 모임 정책 제거](meeting-policies-restricted-anonymous-access.md)
