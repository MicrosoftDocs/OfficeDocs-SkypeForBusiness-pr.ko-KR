---
title: 패널에서 체크인 및 Microsoft Teams 릴리스
ms.author: czawideh
author: cazawideh
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
ms.topic: reference
search.appverid: MET150
description: 이 문서에서는 패널 디바이스에서 체크인 및 방 릴리스를 사용하도록 Teams 지침을 제공합니다.
ms.openlocfilehash: 9e90916c5db4d5ec32a40f0e021f9bf7b294d09f
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "63689103"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>패널에서 체크인 및 Microsoft Teams 릴리스

체크인 및 회의실 릴리스를 사용하도록 설정하면 사용자가 모임이 Teams 예약한 회의실의 패널을 체크 인합니다. 사용자가 모임 시작 시간 이후에 정해진 시간 내에 체크인하지 않는 경우 회의실에서 모임 초대를 거부하고, 모임 이끌이에게 취소 메시지를 보내고, 다른 사용자가 예약할 수 있도록 회의실을 사용할 수 있습니다.  

## <a name="requirements"></a>요구 사항 

이 기능은 독립 실행형 패널 배포에서 Teams 수 있습니다. 또한 Teams 같은 추가 기능을 Teams 룸 버전 1449/1.0.96.202011305 이상과 Android에서 Teams 패널을 페어링할 수 있습니다.  

## <a name="enable-check-in-and-room-release"></a>체크인 및 방 릴리스 사용 

체크인 및 룸 릴리스는 기본적으로 해제됩니다. 켜기 위해  

1. Teams 패널에서 관리자 자격 증명을 사용하여 로그인합니다.  

2. 관리자 설정 > **설정 > 패널** 앱 설정 > 모임으로 설정 > 이동하세요.

3. 아무도 체크 인하지 아니하면 릴리스 룸을  켜야 합니다.

4. 사용자가 방을 릴리스하기 전에 체크 인해야 하는 시간을 조정하려면 다음 릴리스로 이동하고 드롭  다운에서 옵션을 선택합니다.  

Teams Android의 Teams 회의실과 페어링되는 경우 사용자는 회의실에서 모임에 Teams 있습니다.  

## <a name="turn-on-check-in-notifications"></a>체크인 알림 설정

> [!NOTE]
> 이 기능은 현재 Android의 Teams 룸과 페어링된 Teams 패널에서만 사용할 수 있습니다. Teams 패널 및 Teams 룸은 동일한 리소스 계정에 로그인해야 합니다. 자세한 [내용은 Teams](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android) Android의 Microsoft Teams 패널 쌍을 참조합니다.  

모임이 예약된 시간 슬롯을 계속 지날 때 체크인 알림이 전송됩니다. 다음 모임의 사용자가 체크 인하면 예약된 모임 시작 시간의 회의실 앞에 알림이 표시되고 이전 모임 참가자가 예약이 완료되고 사용자가 공간을 기다리는 것을 알 수 있습니다.  

체크인 알림을 켜기 위해  

1. Teams 패널에서 관리자 자격 증명을 사용하여 로그인합니다. 

2. 관리자 설정 > **설정 > 패널** 앱 설정 > 모임으로 설정 > 이동하세요.

3. 체크인으로 **이동** 하여 체크인 알림 보내 **기 를 켜면 됩니다**.

## <a name="related-topics"></a>관련 주제

- [패널을 Microsoft Teams 방법](use-teams-panels.md)

- [Microsoft Teams 패널](teams-panels.md)