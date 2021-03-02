---
title: 보기 전용 모임 환경
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 관리자, 발표자 및 참석자에 대한 Teams 보기 전용 모임 경험에 대해 자세히 알아보기
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed7221192fdc3588856755b8be651065fdbf15ab
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397563"
---
# <a name="teams-view-only-meeting-experience"></a>Teams 보기 전용 모임 환경

> [!Note]
> 보기 전용 모임 환경은 2021년 3월 초에 제공됩니다. 이 기능은 2021년 3월 1일을 기본 OFF로 사용하도록 설정됩니다. 이 기능을 기본값으로 설정하려면 해당 날짜 이후에 기본 정책을 변경해야 합니다. PowerShell을 사용하여 정책을 사용하도록 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled` 설정합니다.

> [!Note]
> 20,000명 참석자에 대한 보기 전용 환경이 일시적으로 증가했지만 2021년 6월 30일에는 10,000명으로 지원이 되감습니다.

Microsoft Teams를 사용하면 최대 10,000명이 Teams 모임에 참가할 수 있습니다. 주 모임의 용량에 도달하면 추가 참석자는 보기 전용 환경과 함께 참가합니다.

모임에 먼저 참가하는 참석자는 모임 용량까지 전체 Teams 모임 환경을 얻을 수 있습니다. 오디오 및 비디오를 공유하고, 공유 비디오를 보고, 모임 채팅에 참여할 수 있습니다.

주 모임 용량에 도달한 후에 참가하는 참석자는 보기 전용 환경을 하게 됩니다.

참석자에 대한 전체 Android 및 iOS 모바일 지원이 있습니다.

> [!Note]
> 모임에 채팅하고 전화를 걸 수 있는 사용자 수에 대한 현재 제한은 WW에서 300, GCC, GCC High 및 DoD에서는 250입니다.

뷰 전용 환경은 기본적으로 E3/E5/A3/A5 SKU가 있는 모든 이끌이에 대해 비활성화됩니다. 추가 구성 또는 설정이 필요하지 않습니다.

## <a name="disable-teams-view-only-experience"></a>Teams 보기 전용 환경 사용 안 하세요

관리자는 PowerShell을 사용하여 보기 전용 환경을 사용하지 않도록 설정할 수 있습니다.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

앞으로 관리자는 Teams 관리 센터에서 보기 전용 환경을 사용하지 않도록 설정할 수도 있습니다.

## <a name="impact-to-users"></a>사용자에게 미치는 영향

사용자의 환경은 여러 요인에 따라 달라집니다.

주 모임의 용량에 도달하면 다음 중 한 가지가 true인 경우 참석자는 모임에 참가할 수 없습니다.

- 관리자가 Teams 보기 전용 환경을 사용하지 않도록 설정했습니다.
- 참석자에 로비를 무시할 수 있는 권한이 없습니다.

주 모임의 용량에 도달하면 모임 이끌이와 발표자가 모임 용량에 도달하고 새 참석자가 보기 전용 참석자에 참가할 것임이 알리는 배너가 표시됩니다.

  ![이끌이 및 발표자에 대한 Teams 클라이언트 및 배너 message](media/chat-and-banner-message.png)

주 모임의 용량에 도달하면 모임 참석자는 참가 전 화면에서 보기 전용 모드로 참가하고 있는 것으로 알려 갑니다.

  ![Teams 사전 참가 화면 및 참가자가 보기 전용 모드로 참가할 것 을 알려준 메시지](media/view-only-pre-join-screen.png)

공백이 있는 경우 사용자는 항상 주 모임에 참가합니다. 주 모임이 용량에 도달하고 하나 이상의 참석자들이 주 모임을 나가면 주 모임에 사용 가능한 용량이 있습니다. 모임에 참가(또는 다시 참가)하는 참석자는 용량에 다시 도달할 때까지 주 모임에 참가합니다. 보기 전용 환경인 참석자들은 자동으로 주 모임으로 승격되지 않습니다. 현재는 주 모임으로 수동으로 승격할 수 없습니다.

발표자/참석자 역할이 설정되지 않은 경우 주 모임의 공백은 선착반으로 채워집니다. 모임 용량에 도달하면 다른 모든 사용자가 보기 전용 환경과 함께 참가합니다.

## <a name="impact-to-meeting-presenters"></a>모임 발표자에 미치는 영향

모임 발표자에 대한 제한은 다음과 같습니다.

- 보기 전용 참석자에 대한 정보가 없습니다. 보기 전용 참석자에 대한 E-discovery는 지원하지 않습니다.
- 보기 전용 참석자만 볼 수 없습니다.
- 모임에서 보기 전용 참석자만 제거할 수 있습니다.

> [!Note]
> 참석자 수는 오버플로 룸의 사람이 아니라 모임에 있는 사람만 반영합니다. 따라서 발표자는 보기 전용 환경의 정확한 수를 얻을 수 있습니다.

## <a name="experience-for-view-only-attendees"></a>보기 전용 참석자 환경

Teams 보기 전용 환경을 통해 참석자들은 다음을 할 수 있습니다.

- 주 Teams 모임의 참가자를 들어 듣습니다.
- 활성 화자에 대한 비디오 피드를 참조하세요(활성 스피커가 비디오를 공유하는 경우).
- 공유 데스크톱 기능을 사용하여 공유되는 콘텐츠를 참조하세요.

보기 전용 참석자들은 모임에서 다음 옵션을 경험할 수 없습니다.

- 참석자 설정 로비 정책 또는 옵션에 따라 로비를 우회할 수 있는 권한이 없는 경우 모임에 참가합니다.
- 오디오 회의를 통해 오버플로 룸에 참가합니다.
- Microsoft Teams Room 시스템 또는 CVI(Cloud Video Interop) 서비스를 통해 오버플로 룸에 참가합니다.
- 오디오 또는 비디오를 공유합니다.
- 모임 채팅을 보거나 참가합니다.
- 참가자가 활성 발표자인 경우를 위해 모임 참가자의 비디오 피드를 참조하세요.
- 기본 공유 PowerPoint 기능 또는 개별 애플리케이션 공유(데스크톱 공유 외)를 사용하여 공유되는 PowerPoint 파일을 참조합니다.

## <a name="view-only-feature-limitations"></a>보기 전용 기능 제한 사항

- 보기 전용 참석자는 해당 모임에 대한 라이브 캡션 설정에 관계없이 항상 라이브 캡션을 볼 수 있습니다. 현재 영어 캡션만 지원됩니다.
- 보기 전용 참석자는 스트리밍 기술을 통해 지원됩니다.
- 보기 전용 참석자는 참석 보고서에 포함되지 않습니다.
- 보기 전용 참석자는 단일 비디오 환경을 하게 됩니다. 활성 스피커 또는 공유되는 콘텐츠를 볼 수 있지만 둘 다 볼 수 없습니다.
- 현재는 보기 전용 참석자에 대한 **갤러리,** 큰 갤러리 **또는** 함께 모드 레이아웃을 지원하지 않습니다.   
- 보기 전용 참석자에는 일반 참석자와 동일한 대기 시간이 없습니다. <sup>1</sup>

  <sup>1</sup> 보기 전용 참석자는 모임의 30초 비디오 및 오디오 지연에 있습니다.  

## <a name="related-topics"></a>관련 항목

- [Teams용 고급 통신 추가 기능](teams-add-on-licensing/advanced-communications.md)
- [Teams의 제한과 사양](limits-specifications-teams.md)
