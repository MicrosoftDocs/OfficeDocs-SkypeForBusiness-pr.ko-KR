---
title: 라이브 이벤트 기록 정책
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 라이브 이벤트 기록 정책에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9fd67ce67d31effdba0d152a3d5920bb17f23b25
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615177"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Microsoft Teams의 라이브 이벤트 기록 정책

Microsoft Teams 라이브 이벤트를 기록하기 위한 몇 가지 옵션이 있습니다. 기록 옵션은 기록 정책을 사용하여 설정됩니다. 이 문서에서는 다양한 설정을 설명합니다.

PowerShell 명령 [Set-CsTeamsMeetingBroadcastPolicy를](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps) 사용하여 녹음 옵션이 설정됩니다.

## <a name="scheduling-and-option-behaviors"></a>설정 및 옵션 동작

라이브 이벤트 녹화를 진행하는 동안 두 가지 이끌이 옵션이 있습니다.

- 생산자 및 발표자에 사용할 수 있는 녹화

  - 녹음 파일: 이벤트가 끝났을 때 생산자 및 발표자가 다운로드할 수 있는 녹음 파일을 제공합니다.

- 참석자에 사용할 수 있는 기록

  - DVR: DVR(디지털 비디오 레코더)을 사용하면 참석자들이 이벤트 중에 되감기 및 일시 중지를 할 수 있습니다.

  - VOD: VOD(VoD) 비디오로 참석자들이 이벤트가 끝났을 때 시청할 수 있습니다.

## <a name="broadcast-recording-policy-setting"></a>브로드캐스트 녹화 정책 설정

브로드캐스트 정책의 일부로 라이브 이벤트에 대해 녹화를 켜거나 끄기 위해 전환할 수 있는 설정이 있습니다.

|                                 | 생산자 및 발표자에 사용할 수 있는 녹화 | 참석자에 사용할 수 있는 기록 |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| 항상 레코드               | 사용하지 않도록 설정되어 선택되었습니다.                                | 사용하지 않도록 설정되어 선택되었습니다.         |
| 이끌이가 기록할 수 있습니다. | 사용하도록 설정되어 있으며 기본적으로 선택되지 않았습니다.                  | 사용하도록 설정되어 있으며 기본적으로 선택되지 않았습니다.   |
| 기록 안 합니다.               | 사용하지 않도록 설정되어 선택되지 않았습니다.                            | 사용하지 않도록 설정되어 선택되지 않았습니다.      |

정책이 **Always record로** 설정되면 정책 페이지에는 다음과 같은 옵션이 선택되어 있습니다.

![라이브 이벤트 정책 설정](../media/live-event-recording-policy.png "Microsoft Teams 관리 센터의 라이브 이벤트 정책 설정 스크린샷입니다.")

## <a name="storage-and-persistence-behavior"></a>저장소 및 지속성 동작

| 옵션                                       | 상태   | DVR                                                   | VOD                                                     | 녹음/녹화                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| 생산자 및 발표자가 사용할 수 있는 녹화 | 선택된     | DVR을 사용할 수 있으며 AMS(Azure Media Services) 자산은 180일 동안 저장됩니다. | 참석자 는 이벤트에 액세스하고 볼 수 있습니다.                     |                              |
|                                                  | 선택되지 않았습니다. | DVR을 사용할 수 있으며 AMS 자산은 180일 동안 저장됩니다. | 참석자들은 이벤트가 끝났을 때 이벤트에 액세스할 수 없습니다. |                              |
||사용하지 않도록 설정(선택되지 않았습니다)|DVR을 사용할 수 있으며 이벤트 후 AMS 자산이 삭제됩니다.|참석자들은 이벤트가 끝났을 때 이벤트에 액세스할 수 없습니다.||
| 생산자 및 발표자가 사용할 수 있는 녹화 | 선택된     |                                                           |                                                             | MP4가 만들어지며 저장됩니다. |
|                                                  | 선택되지 않았습니다. |                                                           |                                                             | 파일이 생성되지 않습니다.           |

### <a name="related-topics"></a>관련 항목

- [Teams 라이브 이벤트란?](what-are-teams-live-events.md)
- [Teams 라이브 이벤트 계획](plan-for-teams-live-events.md)
- [Teams에서 라이브 이벤트 설정 구성하기](configure-teams-live-events.md)
- [Teams 클라우드 모임 녹화](../cloud-recording.md)