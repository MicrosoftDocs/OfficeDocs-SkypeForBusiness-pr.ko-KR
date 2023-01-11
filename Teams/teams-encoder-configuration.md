---
title: Microsoft Teams에서 스트리밍을 위한 인코더 구성
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft Teams 스트리밍 이벤트에 대한 인코더 기반 RTMP 구성에 대해 설명합니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8fd5feffe328083d9e7d5fa6e14cdbdac2ae5ffc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767982"
---
# <a name="configuring-encoders-for-live-event-streaming-in-microsoft-teams"></a>Microsoft Teams에서 라이브 이벤트 스트리밍을 위한 인코더 구성

Teams는 RTMP 또는 RTMPS를 출력하는 다양한 인코더의 라이브 피드를 허용합니다. 각 인코더는 다르므로 Teams로 보낼 때 인코더 구성에 대한 지침을 따라야 합니다.

Teams에서 라이브 이벤트를 설정하는 방법을 알아보려면 라이브 이벤트 만들기에 대해 읽어보세요. Teams와 통합된 인코더를 이미 사용하고 있는 경우 [라이브 스트리밍을 위한 인코더 구성](teams-encoder-setup.md)에 대해 읽어보세요.

## <a name="configuration-steps"></a>구성 단계

Teams 또는 Yammer를 사용하여 라이브 이벤트를 예약하고 **Teams 인코더** 옵션을 선택한 후에는 모임 초대에서 RTMP URL 및 키를 검색하고 이를 사용하여 피드를 Teams 생산자 UI로 보낼 수 있습니다.

### <a name="gather-the-rtmp-information"></a>RTMP 정보 수집

#### <a name="scheduled-in-teams"></a>Teams에서 예약됨

1. Teams 클라이언트를 열고 **일정** 으로 이동합니다.
1. 예약된 라이브 이벤트를 선택하고 이중 화살표 단추를 선택하여 초대 세부 정보를 확인합니다.
1. 세부 정보 섹션의 **RTMP로** 이동합니다.
1. **RTMP 가져오기 링크를 선택하여 RTMP** 수집 URL을 클립보드에 복사합니다.
1. **RTMP 키 가져오기** 를 선택하여 RTMP 키를 클립보드에 복사합니다.

#### <a name="scheduled-in-yammer"></a>Yammer에서 예약됨

1. 이벤트가 예약된 Yammer 커뮤니티로 이동합니다.
1. **이벤트** 탭을 선택하여 예정된 예약된 이벤트를 확인합니다.
1. 원하는 이벤트를 선택하여 세부 정보 페이지를 표시합니다.
1. 오른쪽의 **생성** 에서 **RTMP 정보 링크를 선택하여 RTMP** URL 및 키를 노출합니다.

## <a name="encoder-setup"></a>인코더 설정

1. RTMP 정보를 수집한 후에는 아래 권장 인코더 설정에 따라 인코더가 올바른 설정으로 구성되어 있는지 확인합니다.
1. 인코더의 스트리밍 설정에 RTMP URL 및 키를 입력합니다(자세한 내용은 제조업체 설명서 참조).
1. 원하는 오디오 및 비디오 원본으로 인코더를 구성합니다.
1. Teams 클라이언트를 열고 라이브 통풍구를 생산자로 조인합니다.
1. 인코더에서 Teams RTMP 수집 URL로 스트리밍을 시작합니다.
1. Teams 생산자 창에서 몇 초 후에 인코더의 RTMP 피드가 발표자 영역에 표시됩니다.
1. 발표자 영역에서 RTMP 피드를 클릭하여 왼쪽의 큐에 배치합니다.
1. 피드에 만족하면 **라이브 보내기** 를 선택합니다. 그러면 피드도 생산자 창의 오른쪽에 표시됩니다.
1. **시작을** 선택하여 스트림을 시작합니다.

## <a name="recommended-encoder-settings"></a>권장 인코더 설정

### <a name="ingest-protocols"></a>프로토콜 수집

- 단일 비트 전송률 RTMPS 또는 RTMP

### <a name="video-format"></a>비디오 형식

- 코덱: H.264
- 프로필: 높음(수준 4.0)
- 비트 전송률: 최대 5Mbps(5000kbps)
- CBR(Strict Constant Bitrate)
- 키 프레임/GOP: 2초
  - 각 GOP의 시작 부분에 IDR 프레임이 있어야 합니다.
  - 프레임 속도: 29.97fps 또는 30fps
  - 해상도: 1280 x 720(720P)
  - 인터레이스 모드: 프로그레시브

### <a name="audio-format"></a>오디오 형식

- 코덱: AAC(LC)
- 비트 전송률: 192kbps
- 샘플 속도: 48kHz 또는 44.1kHz(권장 48kHz)

### <a name="playback-requirements"></a>재생 요구 사항

- Teams에서 콘텐츠를 재생하려면 오디오 및 비디오 스트림이 모두 있어야 합니다.

### <a name="configuration-tips"></a>구성 팁

- 가능하면 하드 와이어 인터넷 연결을 사용합니다.
- 대역폭 요구 사항을 결정할 때 스트리밍 비트 전송률을 두 배로 늘리기 위한 것입니다. 필수 요구 사항은 아니지만 네트워크 정체의 영향을 완화하는 데 도움이 됩니다.
- 소프트웨어 기반 인코더를 사용하는 경우 불필요한 프로그램을 닫습니다.
- 푸시를 시작한 후에는 인코더 구성을 변경하지 마세요. 이벤트에 부정적인 영향을 미치며 이벤트가 불안정해질 수 있습니다. 이벤트가 시작되기 전에 이 작업을 수행하려면 Teams에서 생산자 컨트롤을 사용하여 연결을 끊고 설정을 다시 시작해야 합니다.
- 라이브 이벤트 중에 인코더의 연결이 끊어진 경우 동일한 프로세스의 타임스탬프를 유지하여 다시 연결합니다. 불연속성으로 인해 특정 브라우저 및 디바이스에서 오디오 또는 비디오 문제가 발생할 수 있습니다.
- 이벤트를 설정할 충분한 시간을 주세요. 대규모 이벤트의 경우 이벤트 한 시간 전에 설정을 시작하는 것이 좋습니다.
