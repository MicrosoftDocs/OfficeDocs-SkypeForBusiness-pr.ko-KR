---
title: Walkie Talkie 사용량 및 성능 보고서
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: admin
ms.topic: article
ms.service: microsoft-365-frontline
ms.reviewer: prastogi
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
- tier2
description: Microsoft Teams 관리 센터에서 Walkie Talkie 사용 현황 및 성능 보고서를 사용하여 조직의 Walkie Talkie 사용 활동에 대한 개요를 가져오는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 85f92e715efe2b9608691151a08d006816658095
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69846057"
---
# <a name="walkie-talkie-usage-and-performance-report"></a>Walkie Talkie 사용량 및 성능 보고서

Microsoft Teams 관리 센터의 Walkie Talkie 사용량 및 성능 보고서는 조직의 [Walkie Talkie](../walkie-talkie.md) 활동에 대한 개요를 제공합니다. 이 보고서는 PTT(푸시 투 토크) 전송 수, 채널 활동, 전송 기간, 디바이스 및 참가자 세부 정보와 같은 정보를 제공합니다.

이 보고서를 사용하여 조직의 Walkie Talkie 사용 추세 및 성능에 대한 인사이트를 얻을 수 있습니다. 보고서에 액세스하려면 전역 관리자, Teams 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자여야 합니다.

## <a name="download-and-view-the-report"></a>보고서 다운로드 및 보기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **분석 & 보고서****사용 현황 보고서를** >  선택합니다. **보고서 보기** 탭의 **보고서에서** **Walkie Talkie 사용량을** 선택합니다.
1. **날짜 범위** 에서 7일 또는 30일의 날짜 범위를 선택합니다. 그런 다음 **보고서 실행을** 선택합니다.
1. **보고서 생성을** 선택합니다.
1. **다운로드** 탭의 **상태** 아래에서 **다운로드** 를 선택하여 CSV 형식으로 보고서를 다운로드합니다.

## <a name="interpret-the-report"></a>보고서 해석

이 보고서는 선택한 날짜 범위 동안 이루어진 각 전송에 대한 분석을 제공합니다. 보고서에 포함된 정보는 다음과 같습니다.

|열 이름 |설명 |
|---------|---------|
|TenantId|테넌트 ID입니다.|
|Userid|사용자 ID입니다.|
|DeviceId|디바이스 ID입니다.|
|ChannelId|통신이 발생하는 워키 토키 채널입니다.|
|clientCallStatus | 디바이스가 문제 없이 전송을 받을 수 있었는지를 나타냅니다.|
|ConversationId|각 PTT 전송의 ID입니다.|
|TeamId|사용자가 연결하는 Walkie Talkie 채널에 해당하는 팀의 ID입니다.|
|UnreachableParticipantsCount|지난 5번의 전송을 받을 수 없었기 때문에 연결할 수 없고 명단에서 숨겨진 참가자 수입니다.|
|TransmissionDuration|서비스에서 한 참가자가 전송을 시작하려고 한다는 알림을 받는 시점 사이의 시간(밀리초)은 서비스에서 해당 전송의 마지막 패키지를 배달할 때로 이동합니다.|
|TotalParticipantsCount|Walkie Talkie 채널에 연결된 총 참가자 수입니다.|
|PacketCount|오디오 전송을 보내는 데 사용되는 패킷 수입니다.|
|NotifiedParticipants|전송이 시작될 때 푸시 알림이 전송되는 참가자입니다. 디바이스와 서비스 간의 연결이 끊어지는 시나리오에서는 전송이 오고 있기 때문에 가능한 한 빨리 연결을 다시 설정하라는 알림이 디바이스로 전송됩니다.|
|AudioDurationMilliseconds|전송 기간(밀리초)입니다.|
|ConnectionId|디바이스에서 설정한 Walkie Talkie 채널에 대한 각 연결의 ID입니다.|
|TransmissionStartTime |서비스에서 첫 번째 오디오 패킷을 받은 날짜 및 시간입니다.
|TransmissionEndTime|서비스에서 마지막 오디오 패킷을 받은 날짜 및 시간입니다.|
|참가자 목록|전송이 전송될 때 채널에 연결된 디바이스의 반콜론으로 구분된 ID 목록입니다.|
|CallTimedOut|전송이 기간 제한을 초과했는지 여부입니다. 부울 값입니다.|
|플랫폼|디바이스 운영 체제.|
|ParticipantType|참가자가 전송기의 송신기인지 또는 수신자인지 여부입니다.|
|WebSocketState|전송이 시작될 때 디바이스와 서비스 간의 연결 상태가 이미 설정되었는지 여부입니다.|
|AppVersion|디바이스에 설치된 Teams 앱의 버전입니다.|

## <a name="related-articles"></a>관련 기사

- [Teams의 워키 토키 앱](../walkie-talkie.md)
- [워키 토키 시작](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)