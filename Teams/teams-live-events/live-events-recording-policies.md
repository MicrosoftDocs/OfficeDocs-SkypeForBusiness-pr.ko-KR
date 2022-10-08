---
title: 라이브 이벤트 기록 정책
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 라이브 이벤트 기록 정책에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: abe4cb004ada98021e74823495e6208fc31c28fb
ms.sourcegitcommit: fcedb958bf555d870215ae84fb83752304944716
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68486558"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Microsoft Teams의 라이브 이벤트 기록 정책

Microsoft Teams 라이브 이벤트를 기록하기 위한 몇 가지 옵션이 있습니다. 녹음/녹화 옵션은 기록 정책을 사용하여 설정됩니다. 이 문서에서는 다양한 설정을 설명합니다.

녹음/녹화 옵션은 PowerShell 명령 [Set-CsTeamsMeetingBroadcastPolicy를](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy) 사용하여 설정됩니다.

## <a name="scheduling-and-option-behaviors"></a>일정 및 옵션 동작

라이브 이벤트 기록을 예약하는 동안 다음 두 가지 이끌이 옵션이 있습니다.

- 프로듀서 및 발표자가 사용할 수 있는 녹음/녹화

  - 기록 파일: 이벤트가 끝난 후 생산자와 발표자가 다운로드할 수 있는 녹음 파일을 제공합니다.

- 참석자가 사용할 수 있는 녹음/녹화

  - DVR: DVR(디지털 비디오 레코더)을 사용하면 참석자가 이벤트 중에 되들이고 일시 중지할 수 있습니다.

  - VOD: VOD(주문형 비디오)를 사용하면 참석자가 이벤트가 끝난 후 시청할 수 있습니다.

## <a name="broadcast-recording-policy-setting"></a>브로드캐스트 녹음/녹화 정책 설정

브로드캐스트 정책의 일부로 라이브 이벤트에 대한 녹화를 켜거나 끄도록 토글할 수 있는 설정이 있습니다.

| &nbsp;| 프로듀서 및 발표자가 사용할 수 있는 녹음/녹화 | 참석자가 사용할 수 있는 녹음/녹화 |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| 항상 레코드               | 사용 안 함 및 선택됨                                | 사용 및 선택됨         |
| 이끌이는 기록 가능 여부 | 기본적으로 사용하도록 설정 및 선택됨                  | 기본적으로 사용하도록 설정 및 선택됨   |
| 기록 안 하세요               | 사용 안 함 및 선택 안 함                            | 사용 안 함 및 선택 안 함      |

## <a name="storage-and-persistence-behavior"></a>스토리지 및 지속성 동작

| 옵션                                       | 상태   | Dvr                                                   | Vod                                                     | 녹음/녹화                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| 참석자가 사용할 수 있는 녹음/녹화 | 선택한     | DVR을 사용할 수 있으며 AMS(Azure Media Services) 자산은 180일 동안 저장됩니다. | 참석자는 이벤트에 액세스하고 볼 수 있습니다.                     |                              |
|                                                  | 선택되지 않음 | DVR을 사용할 수 있으며 AMS 자산은 180일 동안 저장됩니다. | 참석자는 이벤트가 끝난 후 이벤트에 액세스할 수 없습니다. |                              |
||사용 안 함(선택되지 않음)|DVR을 사용할 수 있으며 이벤트 후 AMS 자산이 삭제됩니다.|참석자는 이벤트가 끝난 후 이벤트에 액세스할 수 없습니다.||
| 프로듀서 및 발표자가 사용할 수 있는 녹음/녹화 | 선택한     |                                                           |                                                             | MP4가 만들어지고 180일 동안 저장됩니다. |
|                                                  | 선택되지 않음 |                                                           |                                                             | 파일이 만들어지지 않음           |

### <a name="related-topics"></a>관련 항목

- [Teams 라이브 이벤트란?](what-are-teams-live-events.md)
- [Teams 라이브 이벤트 계획](plan-for-teams-live-events.md)
- [Teams에서 라이브 이벤트 설정 구성하기](configure-teams-live-events.md)
- [Teams 클라우드 모임 녹음/녹화](../cloud-recording.md)
