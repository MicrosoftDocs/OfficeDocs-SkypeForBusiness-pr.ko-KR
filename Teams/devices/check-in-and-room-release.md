---
title: Microsoft Teams 패널의 체크인 및 객실 릴리스
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: gary.lai
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.topic: reference
search.appverid: MET150
description: 이 문서에서는 체크인 및 회의실 릴리스 Teams 패널 디바이스를 사용하도록 설정하는 방법에 대한 지침을 제공합니다.
ms.openlocfilehash: 31cdab94ddb6a5c6fdc017b537f446e58aa1c2c5
ms.sourcegitcommit: 6e677c7d0dfe9e380d70adaca748eea88ca95705
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2022
ms.locfileid: "67298328"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Microsoft Teams 패널의 체크인 및 객실 릴리스

체크 인 및 회의실 릴리스를 사용하도록 설정하면 사용자는 모임 시작 시 예약한 회의실의 Teams 패널에서 체크 인합니다. 사용자가 모임 시작 시간 이후에 설정된 시간 내에 체크 인하지 않으면 회의실에서 모임 초대를 거절하고 모임 이끌이에게 취소 메시지를 보내며 다른 사용자가 회의실을 예약할 수 있게 됩니다.  

## <a name="requirements"></a>요구 사항 

이 기능은 독립 실행형 Teams 패널 배포에서 사용할 수 있습니다. 체크 인 알림과 같은 추가 기능을 위해 Android의 Teams 룸 Teams 패널을 앱 버전 1449/1.0.96.202011305 이상과 페어링할 수도 있습니다.

이 기능이 올바르게 작동하려면 Teams 패널 연결된 공유 사서함에 올바른 표준 시간대가 설정되어 있어야 합니다. 공유 사서함의 표준 시간대를 설정하는 방법에 대한 자세한 내용은 [웹용 Outlook 공유 사서함에 대한 표준 시간대 설정을](/exchange/troubleshoot/outlook-on-the-web-issues/shared-mailboxes-time-zone-setting) 참조하세요.

## <a name="enable-check-in-and-room-release"></a>체크인 및 회의실 릴리스 사용 

체크인 및 객실 릴리스는 기본적으로 꺼져 있습니다. 켜려면  

1. Teams 패널 관리자 자격 증명을 사용하여 로그인합니다.  

2. **설정 > 디바이스 설정 > 관리 설정 > Teams 관리자 설정 > 모임으로** 이동합니다.

3. 아무도 체크 인하지 않으면 릴리스 공간을 켭니다.

4. 회의실이 해제되기 전에 사용자가 체크 인해야 하는 시간을 조정하려면 **다음 후 릴리스** 로 이동하여 드롭다운에서 옵션을 선택합니다.  

Teams 패널이 Android의 Teams 룸과 쌍을 이루는 경우 사용자는 Teams 룸에서 모임에 참가하는 것을 체크 인할 수 있습니다.  

## <a name="turn-on-check-in-notifications"></a>체크 인 알림 켜기

> [!NOTE]
> 이 기능은 현재 Android의 Teams 룸과 쌍을 이루는 Teams 패널에서만 사용할 수 있습니다. Teams 패널 및 Teams 룸은 동일한 리소스 계정에 로그인해야 합니다. 자세한 내용은 [Android의 Microsoft Teams 룸과 Teams 패널 페어링](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)을 참조하세요.  

모임이 예약된 시간 슬롯을 계속 지나면 체크 인 알림이 전송됩니다. 다음 모임의 사용자가 체크 인하면 예약된 모임 시작 시간에 회의실 전면에 알림이 표시되어 이전 모임 참가자가 예약이 끝났으며 사람들이 공간을 기다리고 있음을 알 수 있습니다.  

체크 인 알림을 켜려면  

1. Teams 패널 관리자 자격 증명을 사용하여 로그인합니다. 

2. **설정 > 디바이스 설정 > 관리 설정 > Teams 관리자 설정 > 모임으로** 이동합니다.

3. **체크 인** 으로 이동하여 **체크 인 알림 보내기를** 켭니다.

## <a name="related-topics"></a>관련 주제

- [Microsoft Teams 패널을 사용하는 방법](use-teams-panels.md)

- [Microsoft Teams 패널](teams-panels.md)
