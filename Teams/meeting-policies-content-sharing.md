---
title: 콘텐츠 공유를 위한 모임 정책 관리
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
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: 콘텐츠 공유를 위해 Teams 모임 정책 설정을 관리하는 방법을 알아보겠습니다.
ms.openlocfilehash: 6c713800aa0f95c7adfd6655455e6ff332f91595
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205318"
---
# <a name="meeting-policy-settings---content-sharing"></a>모임 정책 설정 - 콘텐츠 공유

<a name="bkcontentsharing"> </a>

이 문서에서는 콘텐츠 공유와 관련된 다음 모임 정책 설정을 설명합니다.

- [화면 공유 모드](#screen-sharing-mode)
- [참가자가 제어권을 주거나 요청하도록 허용](#allow-a-participant-to-give-or-request-control)
- [외부 참가자가 제어권을 주거나 요청하도록 허용](#allow-an-external-participant-to-give-or-request-control)
- [PowerPoint 공유](#powerpoint-sharing)
- [Whiteboard](#whiteboard)
- [공유 노트](#shared-notes)

## <a name="screen-sharing-mode"></a>화면 공유 모드

이 설정은 이끌이 및 사용자당 정책의 조합입니다. 이 설정은 사용자의 모임에서 데스크톱 및 창 공유가 허용되는지 여부를 제어합니다. 정책이 할당되지 않은 모임 참가자(예: 익명, 게스트, B2B 및 페더레이션 참가자)는 모임 이끌이의 정책을 이어 받습니다.

|설정값 |동작  |
|---------|---------|
|**전체 화면**    | 모임에서 전체 바탕화면 공유 및 응용 프로그램 공유가 허용됩니다. |
|**단일 응용 프로그램**   | 모임에서 응용 프로그램 공유가 허용됩니다.        |
|**사용 안 함**     |모임에서 화면 공유 및 응용 프로그램 공유가 해제되어 있습니다.       |

다음 예를 살펴봅시다.

|사용자 |모임 정책 |화면 공유 모드 |
|---------|---------|---------|
|Daniela  | 전역   | 전체 화면 |
|Amanda   | Location1MeetingPolicy  | 사용 안 함 |

Daniela가 호스트하는 모임에서는 모임 참가자가 그의 전체 화면 또는 특정 응용 프로그램을 공유할 수 있도록 허용합니다. Amanda가 Daniela의 모임에 참가하더라도 Amanda는 그녀의 정책 설정이 비활성화되어 있으므로 해당 화면이나 특정 응용 프로그램을 공유할 수 없습니다. Amanda가 호스트하는 모임의 경우 화면 공유 모드 정책 할당에 관계없이 누구도 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.  따라서 Daniela는 Amanda의 모임에서 자신의 화면 또는 단일 애플리케이션을 공유할 수 없습니다.  

현재 사용자가 Google Chrome을 사용하는 경우 Teams 모임에서 비디오를 재생하거나 화면을 공유할 수 없습니다.

## <a name="allow-a-participant-to-give-or-request-control"></a>참가자가 제어권을 주거나 요청하도록 허용

이 설정은 사용자당 정책입니다. 이 설정으로 사용자가 다른 모임 참가자에게 공유 바탕화면 또는 창의 제어권을 줄 수 있는지 여부를 제어합니다. 제어권을 주려면 화면 위쪽으로 마우스를 가져갑니다.

이 설정이 사용자에 대해 켜져 있는 경우 공유 세션의 위쪽 막대에 **제어권 제공** 옵션이 표시됩니다.

![제어권 제공 옵션을 보여주는 스크린샷](media/meeting-policies-give-control.png)

사용자에 대해 설정이 꺼져 있는 경우 **제어권 제공** 옵션을 사용할 수 없습니다.

![제어권 제공 옵션을 사용할 수 없음을 표시하는 스크린샷](media/meeting-policies-give-control-not-available.png)

다음 예를 살펴봅시다.

|사용자 |모임 정책  |참가자가 제어권을 주거나 요청하도록 허용 |
|---------|---------|---------|
|Daniela   | 전역   | 설정       |
|Babek    | Location1MeetingPolicy        | 해제   |

Daniela는 Babek가 조직한 모임에서 다른 참가자에게 공유 데스크톱 또는 창을 제어할 수 있습니다. 그러나 Babek는 다른 참가자에게 제어를 줄 수 없습니다.

PowerShell을 사용하여 제어권을 주거나 제어권 요청을 수락할 수 있는 사용자를 제어하려면 AllowParticipantGiveRequestControl cmdlet을 사용합니다.

> [!NOTE]
> 공유하는 동안 공유 콘텐츠에 대한 제어권을 부여하거나 제어권을 차지하려면 양측이 Teams 데스크톱 클라이언트를 사용하고 있어야 합니다. 컨트롤은 어느 쪽이든 브라우저에서 Teams를 실행 중인 경우 지원되지 않습니다. 이것은 해결하려고 하는 기술적 제한 때문입니다.

## <a name="allow-an-external-participant-to-give-or-request-control"></a>외부 참가자가 제어권을 주거나 요청하도록 허용

이 설정은 사용자당 정책입니다. 조직이 사용자에 대해 이 정책을 설정한지 여부는 모임 이끌이가 설정한 대상에 관계없이 외부 참가자가 할 수 있는 작업을 제어하지 않습니다. 이 매개 변수는 공유자가 소속 조직의 모임 정책 내에서 설정한 정책에 따라 외부 참가자가 공유자 화면의 제어권을 받거나 제어권을 요청할 수 있는지 여부를 제어합니다. Teams 모임의 외부 참가자는 다음과 같이 분류할 수 있습니다.  

- 익명 사용자
- 게스트 사용자  
- B2B 사용자
- 페더레이션 사용자  

소속 조직의 **외부 참가자가 제어권을 주거나 요청하도록 허용** 설정으로 공유가 제어되는 동안 페더레이션 사용자가 외부 사용자에게 제어권을 제공할 수 있는지 여부입니다.

PowerShell을 사용하여 외부 참가자가 제어권을 주거나 제어권 요청을 수락할 수 있는지 여부를 제어하려면 AllowExternalParticipantGiveRequestControl cmdlet을 사용합니다.

### <a name="powerpoint-sharing"></a>PowerPoint 공유

사용자별 정책에 해당합니다. 이 설정으로 사용자가 모임에서 PowerPoint 슬라이드 데크를 공유할 수 있는지 여부를 제어합니다. 익명, 게스트 및 페더레이션 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 이어 받습니다.

다음 예를 살펴봅시다.

|사용자 |모임 정책  |PowerPoint 공유 |
|---------|---------|---------|
|Daniela   | 전역   | 설정       |
|Amanda   | Location1MeetingPolicy        | 해제   |

Amanda는 본인이 모임 이끌이인 경우에도 모임에서 PowerPoint 슬라이드 데크를 공유할 수 없습니다. Daniela는 모임을 Amanda가 이끄는 경우에도 PowerPoint 슬라이드 데크를 공유할 수 있습니다. Amanda는 본인이 PowerPoint 슬라이드 데크를 공유할 수 없는 경우에도 모임의 다른 참가자가 공유한 PowerPoint 슬라이드 데크를 볼 수 있습니다.

## <a name="whiteboard"></a>Whiteboard

이 설정은 사용자당 정책입니다. 이 설정으로 사용자가 모임에서 화이트보드를 공유할 수 있는지 여부를 제어합니다. 익명, B2B 및 페더레이션 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 이어 받습니다.

다음 예를 살펴봅시다.

|사용자 |모임 정책  |Whiteboard|
|---------|---------|---------|
|Daniela   | 전역   | 설정       |
|Amanda   | Location1MeetingPolicy        | 해제   |

Amanda는 본인이 모임 이끌이인 경우에도 모임에서 화이트보드를 공유할 수 없습니다. Daniela는 모임을 Amanda가 이끄는 경우에도 화이트보드를 공유할 수 있습니다.  

## <a name="shared-notes"></a>공유 노트

이 설정은 사용자당 정책입니다. 이 설정으로 사용자가 모임에서 메모를 작성하고 공유할 수 있는지 여부를 제어합니다. 익명, B2B 및 페더레이션 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 이어 받습니다. 모임 **노트** 탭은 현재 20명 미만의 참가자가 있는 모임에서만 지원됩니다.

다음 예를 살펴봅시다.

|사용자 |모임 정책  |공유 노트 |
|---------|---------|---------|
|Daniela   | 전역   | 설정       |
|Amanda   | Location1MeetingPolicy | 해제 |

Daniela는 Amanda의 모임에서 메모를 작성할 수 있고 Amanda는 어떤 모임에서도 메모를 작성할 수 없습니다.




## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
- [사용자의 RestrictedAnonymousAccess Teams 모임 정책 삭제](meeting-policies-restricted-anonymous-access.md)
