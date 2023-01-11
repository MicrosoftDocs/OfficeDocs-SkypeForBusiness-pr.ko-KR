---
title: Microsoft Teams에서 라이브 스트리밍 문제 해결
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
description: 이 문서에서는 Microsoft Teams 스트리밍 이벤트에 대한 문제 해결 옵션에 대해 설명합니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d88b8c0f356bcf59319f073c0e75c65a25361cf2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767997"
---
# <a name="troubleshooting-live-events-in-microsoft-teams"></a>Microsoft Teams에서 라이브 이벤트 문제 해결

> [!IMPORTANT]
> **중국**: 현재 이러한 앱이 의존하는 Azure CDN은 중국에서 액세스할 수 없으므로 중국에 있는 사용자는 Teams 또는 Yammer 라이브 이벤트를 설정하거나 참석하거나 주문형 비디오를 볼 수 없습니다.
>
> 관리자는 이러한 앱이 원활하게 작동하려면 회사 네트워크를 연결하도록 VPN을 설정해야 할 수 있습니다. 완료되면 조직의 사용자가 라이브 이벤트를 예약하고 참석할 수 있습니다.

## <a name="before-a-live-event"></a>라이브 이벤트 전

### <a name="make-sure-all-events-are-reachable-in-your-network"></a>네트워크에서 모든 이벤트에 연결할 수 있는지 확인

#### <a name="general-teams-endpoints"></a>일반 Teams 엔드포인트

Teams는 인터넷에 연결해야 합니다. [Teams용 Office 365 엔드포인트](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)에 나열된 모든 엔드포인트는 조직의 네트워크 내 Teams 사용자가 연결할 수 있어야 합니다.

#### <a name="teams-encoder-live-events---rmtp-ingest-endpoints"></a>Teams 인코더 라이브 이벤트 - RMTP 수집 엔드포인트

인코더에서 Teams로 전송된 Teams 인코더 라이브 이벤트에 대한 비디오 피드를 가져오려면 네트워크 방화벽에서 도메인 이름과 포트를 열어야 합니다.

- 도메인: *.rtmpingest.mcr.teams.microsoft.com
- 포트: 1935/1936(RTMP/RTMPS의 경우)

### <a name="make-sure-you-have-enough-upload-bandwidth"></a>업로드 대역폭이 충분한지 확인합니다.

RTMP를 통해 라이브 이벤트를 생성하거나 스트리밍하는 경우 라이브 스트림을 푸시하는 사이트의 인터넷 업로드 대역폭만으로는 충분하지 않을 수 있습니다. 업로드 대역폭이 낮으면 라이브 비디오 자체에서 프레임 또는 문제가 감소하여 시청자에게 재생 문제가 발생할 수 있습니다.

라이브 스트림을 푸시하는 컴퓨터 및 네트워크에 대한 업로드 속도가 라이브 스트림에 대해 설정한 비트 전송률보다 높은지 확인합니다. 인코더에서 5Mbps 스트림을 출력하지만 업로드 비트 전송률이 그보다 가깝거나 낮으면 스트림을 충분히 빠르게 업로드할 수 없는 문제가 발생할 수 있습니다.

업로드 대역폭 문제가 있는 경우 다음과 같은 몇 가지 작업을 시도해 볼 수 있습니다.

1. WiFi에서 낙하하지 않도록 스트림을 푸시하는 모든 컴퓨터에 하드 유선 이더넷 연결을 사용합니다.
1. 라이브 피드의 인코딩 비트 전송률을 최대 업로드 속도보다 훨씬 낮은 값으로 낮춥니다.

### <a name="preparing-your-network-for-many-concurrent-viewers"></a>많은 동시 뷰어를 위한 네트워크 준비

라이브 이벤트 중에는 많은 사람들이 참여하여 이벤트를 실시간으로 시청합니다. 이로 인해 네트워크 및 인터넷 다운로드 대역폭에 부담을 줄 수 있습니다. 현재 네트워크 인프라를 평가하고 회사 네트워크 내의 사용자에게 라이브 이벤트를 시청하는 데 필요한 대역폭이 있는지 확인해야 합니다. 라이브 이벤트에 필요한 인터넷 트래픽을 줄이기 위해 다음 두 가지 옵션이 있습니다.

1. 네트워크 내에서 기존 캐시 프록시를 구성하여 Teams의 비디오를 캐시합니다.
1. 타사 eCDN 비디오 배달 솔루션을 사용하여 비디오 트래픽을 최적화합니다.

### <a name="i-cant-create-a-live-event"></a>라이브 이벤트를 만들 수 없습니다.

Microsoft Teams 및 Yammer에는 라이브 이벤트에 사용하는 서비스에 따라 사용자가 라이브 이벤트를 만들 수 있어야 하는 권한이 있습니다.

1. Teams 관리자가 라이브 이벤트를 만들 수 있는지 확인합니다.
1. 라이브 이벤트를 만들 수 있는 유효한 Teams 라이선스가 있는지 관리자에게 확인합니다.

### <a name="make-sure-viewers-have-permission-to-watch-the-event"></a>뷰어에게 이벤트를 시청할 수 있는 권한이 있는지 확인

Microsoft Teams 라이브 이벤트에는 이벤트 자체에 대한 권한(이끌이, 생산자, 발표자, 참석자)에 대한 몇 가지 역할이 있습니다.

자세한 내용은 [Microsoft Teams 이벤트 그룹 역할을](https://support.office.com/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a#bkmk_roles) 참조하세요.

## <a name="producing-a-live-event"></a>라이브 이벤트 생성

### <a name="i-dont-know-how-to-set-up-my-encoder"></a>인코더를 설정하는 방법을 모릅니다.

시작하는 가장 쉬운 방법은 [Microsoft Teams에서 라이브 스트리밍에 인코더 사용](teams-encoder-setup.md) 문서에서 설명한 지침을 따르는 것입니다.

### <a name="my-encoder-isnt-connecting-to-the-server-ingest-url"></a>내 인코더가 서버 수집 URL에 연결되지 않음

- RTMP URL이 인코더의 출력으로 올바르게 입력되었는지 확인합니다.
- RTMP 키가 인코더의 출력으로 올바르게 입력되었는지 확인합니다.
- 인터넷 연결 상태를 확인하여 인코더가 올바르게 연결되어 있고 온라인 상태인지 확인합니다.
- 연결 출력을 차단할 수 있는 네트워크 보안 또는 방화벽 관련 설정이 있을 수 있습니다.
- 인코더는 Teams에서 지원되지 않을 수 있습니다. [Microsoft Teams에서 라이브 스트리밍에 인코더 사용에서 테스트된 인코더](teams-encoder-setup.md) 목록을 확인하세요.

### <a name="i-cant-get-rtmps-to-work"></a>RTMP가 작동하도록 할 수 없습니다.

- 일부 인코더는 Teams에서 지원하지 않는 다른 구현을 지원할 수 있습니다. Microsoft Teams에서 라이브 스트리밍에 인코더 사용에서 Teams와 함께 작동하는 테스트된 [인코더](teams-encoder-setup.md) 목록을 확인하세요.
- 모든 인코더 또는 버전이 RTMP를 지원하는 것은 아닙니다. 제조업체 또는 소프트웨어 작성자가 지원하는 내용을 확인하세요.

### <a name="i-tried-to-start-setup-and-its-taking-a-long-time"></a>설치를 시작하려고 했는데 시간이 오래 걸리고 있습니다.

일반적으로 인코더 푸시를 시작하기 전에 설정을 진행하는 데 몇 분 정도 걸릴 수 있습니다. 서비스가 사용 중일 때 이 작업을 진행하는 데 시간이 더 오래 걸릴 수 있으므로 예약된 라이브 이벤트 전에 설정을 시작하는 데 충분한 시간을 주는 것이 좋습니다.

### <a name="i-tried-to-start-setup-but-there-are-too-many-events-happening"></a>설정을 시작하려고 했지만 이벤트가 너무 많습니다.

이벤트를 시작할 때 최대 이벤트 수에 도달했다는 메시지가 표시되면 다른 이벤트를 중지하여 우선 순위가 높은 이벤트를 위한 공간을 마련할 수 있는 Teams 관리자에게 문의하세요.

### <a name="i-cant-see-producer-view"></a>생산자 보기를 볼 수 없습니다.

1. 인코더에서 스트리밍을 시작한 후 생산자 미리 보기가 표시되는 데 몇 초 정도 걸릴 수 있습니다.
1. 인코더가 Teams에 연결되어 있는지 확인합니다.
1. Teams에서 페이지를 새로 고치는 데 도움이 될 수 있습니다. 페이지를 나갈지 묻는 메시지가 표시될 수 있습니다. 라이브 이벤트에는 영향을 미치지 않습니다.
1. 일부 네트워크는 콘텐츠에 대한 액세스를 차단할 수 있습니다. 네트워크 보안 및 방화벽 설정에서 RTMP 프로토콜을 허용하고 [필요한 도메인이](/microsoft-365/enterprise/urls-and-ip-address-ranges) 허용 목록에 있는지 확인합니다. 회사 네트워크, VPN 또는 잠긴 네트워크와 독립적으로 다른 네트워크 환경에서 작동하는지 확인하는 데 도움이 될 수 있습니다.

### <a name="my-feed-looks-bad-has-poor-quality-or-is-glitchy"></a>피드가 나빠 보이거나, 품질이 좋지 않거나, 결함이 있습니다.

1. 라이브 스트림을 푸시하는 컴퓨터에서 업로드 대역폭을 확인합니다. 대역폭이 낮으면 프레임이 떨어지거나 품질이 저하되거나 비디오 스트림이 글리치될 수 있습니다. 스트리밍하는 비트 전송률보다 높은 업로드 대역폭이 필요합니다.
1. Teams에 권장되는 인코더 설정을 사용하고 있는지 확인합니다. 자세한 내용은 [Microsoft Teams에서 라이브 이벤트 스트리밍을 위한 인코더 수동 구성](teams-encoder-configuration.md) 을 참조하세요.
1. 인코더에 들어오는 오디오/비디오에 문제가 없는지 확인합니다. 인코더로 라우팅된 원본 오디오 또는 비디오 피드에는 문제 자체가 있을 수 있으며, 이로 인해 시청자에게 잘못된 환경이 전송될 수 있습니다.
1. 인코더에서 CPU 부하를 확인합니다. 원본 콘텐츠 및/또는 푸시하려는 비트 전송률로 CPU를 최대화할 수 있습니다. CPU 부하가 너무 높은 경우 라이브 피드 오버레이/콘텐츠의 복잡성을 줄이거나 스트리밍 중인 비트 전송률을 줄입니다.
1. 인코더가 최신 상태인지 확인합니다. 하드웨어 인코더인 경우 최신 펌웨어 업데이트가 있는지 확인합니다. 소프트웨어 인코더인 경우 최신 버전을 실행하고 있는지 확인합니다.
1. 인코더를 다시 설정하거나 다시 시작해 보세요. 라이브 스트림 중에 이 작업을 수행하면 인코더가 다시 시작되는 동안 재생 중에 뷰어에 오류가 표시됩니다. 인코더에서 라이브 스트리밍을 다시 시작한 후 뷰어는 라이브 스트림을 다시 가져오기 위해 페이지를 다시 로드해야 합니다.

### <a name="i-ended-my-live-event-from-my-encoder-but-viewers-are-seeing-an-error"></a>인코더에서 라이브 이벤트를 종료했지만 시청자가 오류를 보고 있습니다.

인코더 연결을 끊기 전에 **이벤트 중지** 를 선택합니다. 인코더의 연결을 이미 끊은 경우에도 **이벤트 중지** 를 선택할 수 있지만 뷰어에 오류가 표시될 수 있습니다.

### <a name="my-viewers-are-seeing-issues"></a>시청자가 문제를 보고 있습니다.

- 단일 뷰어가 문제를 보고하는 경우 뷰어가 충분한 대역폭을 가지고 있고 이벤트를 시청하기에 좋은 인터넷 연결에 있는지 확인합니다.
- 동일한 네트워크 내의 여러 사용자에게 문제가 있는 경우 네트워크 정체 관련 문제가 발생할 수 있습니다. [Microsoft Teams에서 eCDN을 사용하여 비디오 배달 크기 조정 및 네트워크 트래픽 모니터링](teams-stream-ecdn.md)을 검토하여 문제에 대한 솔루션을 식별할 수 있는지 확인합니다.
- 여러 뷰어에 문제가 표시되면 실제로 인코더 피드와 관련된 경우가 많습니다.
  - 인코더가 인코더 설정에 설명된 사양으로 올바르게 설정되고 올바르게 구성되었는지 확인합니다.
  - 스트리밍할 수 있는 업로드 대역폭이 충분한지 확인합니다. 인코더 출력에서 대역폭을 줄일 수 있습니다.
  - 경우에 따라 인코더를 다시 설정하면 도움이 되지만 다시 연결할 때 동일한 설정을 유지해야 합니다. 대상 그룹 구성원이 라이브 이벤트에서 오류 또는 결함을 볼 수 있습니다.

### <a name="i-or-my-viewers-cant-hear-the-video"></a>나 또는 내 시청자가 비디오를 들을 수 없음

1. 인코더가 오디오를 보내고 있는지 확인합니다.
1. 오디오 디바이스가 연결되어 있는지 확인합니다.
1. Windows에서 올바른 오디오 디바이스가 선택되고 제거되었는지 확인합니다.
1. 인코더 중단이 있는 경우 일부 브라우저 또는 디바이스가 오디오를 올바르게 복구하고 재생하지 못할 수 있습니다.

> [!NOTE]
> 라이브 이벤트에 대한 비디오 배포 공급자로 Microsoft eCDN을 배포한 경우 발생할 수 있는 [eCDN 성능 문제 해결에 대한 자세한 내용은 eCDN 성능](/ecdn/troubleshooting/troubleshoot-ecdn-performance-issues) 문제 해결을 참조하세요.
