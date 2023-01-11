---
title: Microsoft Teams에서 스트리밍을 위한 인코더 설정
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
description: 이 문서에서는 Microsoft Teams 스트리밍 이벤트에 대한 인코더 기반 RTMP 설정에 대해 설명합니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8a31b8b0de30367401c998d17dbf59ea06fc5687
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767987"
---
# <a name="using-an-encoder-for-live-streaming-in-microsoft-teams"></a>Microsoft Teams에서 라이브 스트리밍에 인코더 사용

Teams 인코더를 사용하면 사용자가 Microsoft Teams를 사용하여 외부 하드웨어 또는 소프트웨어 기반 인코더에서 직접 라이브 이벤트를 생성할 수 있습니다.

## <a name="overview"></a>개요

인코더는 카메라, 마이크, 데스크톱 화면 캡처 등과 같은 라이브 이벤트 중에 사용하는 다양한 소스에서 오디오 및 비디오 콘텐츠를 가져옵니다. 해당 미디어를 압축하고 적절한 디지털 형식으로 변환한 다음, 라이브 스트리밍을 위해 Teams로 보냅니다. 외부 인코더와 함께 Teams 프로덕션 기술(예: NDI)을 사용하는 방법에 대한 자세한 내용은 [사용자 지정 프로덕션 플레이북](https://aka.ms/CustomProductionVEP) 을 참조하세요.

## <a name="production-workflow-when-using-an-encoder"></a>인코더를 사용하는 경우의 프로덕션 워크플로

Teams 라이브 이벤트를 생성하기 위한 워크플로는 다음과 같습니다.

라이브 이벤트는 Teams 또는 Yammer에서 예약되고 **Teams 인코더** 옵션이 선택됩니다. 이렇게 하면 RTMP(S) URL 및 해당 키와 함께 제공되는 RTMP 엔드포인트가 프로비전됩니다. URL 및 키는 인코더에서 예약된 라이브 이벤트에 대한 RTMP 엔드포인트에 연결하는 데 사용됩니다.

### <a name="common-encoders-user-with-live-events"></a>라이브 이벤트를 사용하는 일반 인코더 사용자

다음 두 목록의 인코더는 Microsoft에서 Teams를 사용한 라이브 스트리밍을 위해 테스트했습니다. 첫 번째 목록은 사용 편의성과 빠른 설정을 위해 제품으로 테스트된 이러한 인코더의 하위 집합입니다.

#### <a name="stream-ready-encoders"></a>스트림 준비 인코더

|인코더                                |웹 사이트  |세부 정보  |
|---------------------------------------|---------|---------|
|하이비전 (Haivision)                              |[Haivision Makito X](https://www.haivision.com/microsoft/stream) |RTMP의 강력한 대안인 Haivision Hub를 사용하여 고품질 HD 비디오를 제공합니다. |
|하이비전 (Haivision)                              |[Haivision KB](https://www.haivision.com/microsoft/stream) |H.264 및 HEV 비디오 인코더는 최대 4K 해상도의 고품질 ABR 비디오 연계를 제공합니다. |
|OBS Studio(Open Broadcaster Software) |[Open Broadcaster Software](https://obsproject.com/) |모든 스트리밍 플랫폼 등을 지원하는 고성능 실시간 비디오/오디오 캡처 및 혼합. |
|vMix                                   |[vMix](https://www.vmix.com/) |카메라, 비디오, 오디오 등의 녹화, 혼합 및 라이브 스트리밍을 제어하는 소프트웨어 비전 믹서입니다. |
|Wirecast                               |[Wirecast](https://www.telestream.net/wirecast) |모든 기본 사항 + 다중 카메라 프로덕션을 다루는 웹캐스팅 소프트웨어입니다. |
|Switcher Studio                        |[Switcher Studio](https://www.switcherstudio.com/microsoft-stream) |실시간 비디오 캡처 및 편집을 위해 하나 이상의 카메라와 여러 Apple 디바이스를 동기화합니다. |
|AWS Elemental Live                     |[AWS Elemental Live](https://www.elemental.com/products/aws-elemental-appliances-software/#elemental-live) |인터넷에 연결된 디바이스로 라이브 스트리밍을 위한 실시간 비디오 및 오디오 녹화 |
|XSplit 브로드캐스터                     |[XSplit 브로드캐스터](https://www.xsplit.com/) |라이브 스트리밍을 위한 게임 플레이를 포함하여 풍부한 비디오 콘텐츠를 생성, 혼합 및 제공합니다. |
|Ffmpeg                                 |[Ffmpeg](https://ffmpeg.org/) |비디오, 오디오 및 기타 멀티미디어 파일 및 라이브 스트림을 처리하기 위한 오픈 소스 소프트웨어 제품군입니다. |
|프로덕션 트럭          |[프로덕션 트럭](https://www.blueframetech.com/productiontruck) |모바일 밴이나 트럭에서 위치에서 이벤트를 촬영하고 스트리밍합니다. |
|Live Arena AI 생산자                 |AI 생산자 |Microsoft Teams에 모임 앱으로 통합된 프로덕션 스튜디오.|
|StreamYard                             |StreamYard |브라우저의 라이브 스트리밍 스튜디오.|
|사교적                              |사교적 |클라우드 비디오 프로덕션 플랫폼- 스튜디오 품질의 비디오 콘텐츠를 제작하고 배포하기 위한 올인원 환경을 제공합니다.|
|Brandlive                              |BrandLive |클라우드 기반 프로덕션 플랫폼.|

### <a name="haivision-makito-x-encoder-and-makito-kb-encoder"></a>Haivision Makito X 인코더 및 Makito KB 인코더

기존 Haivision X 또는 Makito KB 인코더가 있는 경우 드롭다운 목록에서 적절한 옵션을 선택하고 지침 목록을 따를 수 있습니다.

1. **설치 시작을** 선택하여 라이브 스트리밍을 위한 채널을 만듭니다. 설치가 완료되기를 기다립니다. 화면에 **연결 준비** 완료 메시지가 표시됩니다.
1. 완료되면 수집 URL 및 이벤트 이름을 포함하여 모든 인코딩 매개 변수가 포함된 사전 설정을 다운로드합니다. 사전 설정을 인코더로 가져오고 인코더를 시작합니다.
1. Teams에 돌아가기. 인코더에서 미리 보기를 볼 수 있으면 라이브로 전환할 **이벤트 시작을** 선택하여 대상 그룹이 라이브 이벤트를 볼 수 있도록 합니다.

> [!NOTE]
> RTMPS에 대한 Haivision KB 인코더 지원은 아직 테스트되지 않았습니다. Haivision Makito X 인코더는 RTMPS를 지원하지 않습니다. 두 인코더에 대해 다운로드한 사전 설정에는 RTMP 수집 URL이 포함됩니다.

### <a name="switcher-studio"></a>Switcher Studio

Switcher Studio를 사용하여 iPhone 또는 iPad를 사용하여 Teams로 스트리밍을 시작할 수 있습니다.

1. **설치 시작을** 선택하여 라이브 스트리밍을 위한 채널을 만듭니다. 설치가 완료되기를 기다립니다. 화면에 **연결 준비** 완료 메시지가 표시됩니다.
2. Switcher Studio는 Switcher Studio 대시보드를 열어 계정에 라이브 이벤트를 추가합니다.

> [!NOTE]
> Switcher Studio 계정이 아직 없는 경우 계정을 만들어야 합니다).

3. 이 작업이 완료되면 iPhone 또는 iPad의 Switcher Studio 앱으로 이동하여 출력 탭에서 Teams를 선택하고 Teams로 스트리밍을 시작할 수 있습니다.
4. Teams에 돌아가기. 인코더에서 미리 보기를 볼 수 있게 되면 이벤트 시작을 선택하여 라이브 **로** 전환하여 대상 그룹이 라이브 이벤트를 볼 수 있도록 합니다.

> [!NOTE]
> Switcher Studio는 RTMP 수집 URL을 사용합니다.

### <a name="wirecast"></a>Wirecast

Wirecast의 기존 사용자인 경우 드롭다운 목록에서 이 옵션을 선택하여 라이브 스트림을 Teams로 보낼 수 있습니다. Wirecast 버전 10 이상이 필요합니다.

1. **설치 시작을** 선택하여 라이브 스트리밍을 위한 채널을 만듭니다. 설치가 완료되기를 기다립니다. 화면에 **연결 준비** 완료 메시지가 표시됩니다.
1. 인코더는 올바른 인코딩 매개 변수를 사용하여 미리 구성된 컴퓨터에서 Wirecast 앱을 시작하고 해당 라이브 이벤트에 대한 URL을 수집합니다. 준비가 되면 Wirecast 앱에서 Teams 아이콘을 클릭하여 Teams로 스트리밍을 시작합니다.
1. Teams에 돌아가기. 인코더에서 미리 보기를 볼 수 있게 되면 이벤트 시작을 선택하여 라이브 **로** 전환하여 대상 그룹이 라이브 이벤트를 볼 수 있도록 합니다.

> [!NOTE]
> Wirecast 앱은 RTMPS 수집 URL이 미리 구성된 상태에서 시작됩니다.
