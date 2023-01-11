---
title: Microsoft Teams에서 비디오 배달 크기 조정
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
description: 이 문서에서는 Microsoft Teams 스트리밍 이벤트에 대한 크기 조정 비디오 배달 및 eCDN(엔터프라이즈 콘텐츠 배달 네트워크)에 대해 설명합니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 9475ac8a99a7858221c062ccedb0bd1327f37e4c
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767978"
---
# <a name="scale-video-delivery-and-monitor-network-traffic-by-using-ecdns-with-microsoft-teams"></a>Microsoft Teams에서 eCDN을 사용하여 비디오 배달 크기 조정 및 네트워크 트래픽 모니터링

Microsoft Teams 및 "외부 앱 또는 디바이스" 라이브 이벤트(이전의 "외부 인코더" 프로덕션)의 비디오 재생은 유니캐스트 스트림으로 제공되는 적응 비트 전송률 스트리밍(ABR)을 사용합니다. 즉, 모든 뷰어는 인터넷에서 자체 비디오 스트림을 가져옵니다. 조직의 많은 부분으로 전송되는 라이브 이벤트 또는 비디오의 경우 시청자가 사용하는 상당한 양의 네트워크 및 인터넷 대역폭이 있을 수 있습니다.

조직은 라이브 이벤트 및 인기 있는 비디오에 대한 이 네트워크 트래픽을 이해하고 줄일 수 있습니다. 그렇다면 Teams는 자체 관리 배달 기술, 실시간 모니터링 및 심층 네트워크 분석을 포함하는 eCDN(엔터프라이즈 콘텐츠 배달 네트워크) 솔루션을 제공하는 신뢰할 수 있는 Microsoft 파트너와 통합할 수 있습니다. 이러한 eCDN 플랫폼을 통해 조직은 엔터프라이즈 네트워크에서 비디오 스트림(때로는 다른 콘텐츠 형식)의 배포를 모니터링, 크기 조정 및 최적화할 수 있습니다.

## <a name="acquire-and-set-up-your-ecdn-solution-outside-of-teams"></a>Teams 외부에서 eCDN 솔루션 획득 및 설정

신뢰할 수 있는 Microsoft eCDN 파트너와 협력하여 비디오 배달 모니터링 및 크기 조정에 대한 전문가의 도움을 받으세요.

Teams에서 eCDN 솔루션을 사용하도록 설정하려면 먼저 해당 eCDN 솔루션을 구매하여 Teams 외부와 별도로 설정해야 합니다. 솔루션이 요구 사항을 충족하도록 하기 위해 일부 파트너는 콘텐츠 배달 및 네트워크 분석 기술에 대한 평가판을 제공합니다.

여러 eCDN 솔루션은 미리 통합되어 있으며 Teams에서 사용할 수 있습니다. 아래 공급자의 정보를 참조하세요.

### <a name="hive-streaming"></a>Hive 스트리밍

**Hive 스트리밍 비디오 환경 플랫폼** 은 세 가지 핵심 제품으로 구성됩니다.

- **Hive 비디오 최적화** 는 특허받은 소프트웨어 전용 제로 구성 알고리즘을 기반으로 합니다. 최적화는 전체 조직에 대한 VOD(라이브 및 주문형 비디오)의 품질과 도달 범위를 자동으로 최대화합니다.
- **Hive Video Analytics를** 사용하면 고객이 라이브 이벤트 및 주문형 비디오 성능의 추세를 이해하여 시간이 지남에 따라 뷰어 참여를 개선할 수 있습니다. 참여가 개선됨에 따라 회사 전체에서 비디오 채택도 향상됩니다.
- **Hive Video Operations** 는 라이브 비디오 이벤트 전후에 스트리밍 비디오 성공을 사전에 보호하는 것을 목표로 하는 강력한 기능을 제공합니다. 운영 도구는 비디오 스트리밍 및 UC 팀이 문제가 발생하기 전에 문제를 찾고 수정할 수 있도록 합니다.

모든 작업은 계획에서 실행 및 분석에 이르기까지 전체 범위의 비디오 환경을 만들기 위해 작동합니다. 비디오 통신 스트리밍 환경을 극대화하는 것은 직원 참여와 회사 업무 조정에 매우 중요합니다. 자세한 내용은 [이 링크를](https://www.hivestreaming.com/partners/microsoft) 확인하세요.

### <a name="kollective"></a>Kollective

**Kollective Technology** 는 지능형 피어링을 활용하여 라이브 및 주문형 엔터프라이즈 비디오를 제공하는 클라우드 기반 콘텐츠 배포 플랫폼으로, 대역폭의 1%에 불과한 100% 비디오 품질과 100% 참여를 제공합니다. Kollective가 Teams 라이브 이벤트와 통합되면 전역적으로 분산된 직원이 비디오를 쉽게 사용하고, 직원 커뮤니케이션을 개선하고, 전반적인 참여를 촉진하고, 교육 및 보존 기회를 늘릴 수 있습니다.

**Kollective IQ** 는 Microsoft Stream 위한 정교하고 사용자에게 친숙한 분석 플랫폼입니다. 사용자 지정 가능한 보고, 시각화 및 대시보드를 사용하면 복잡한 글로벌 엔터프라이즈 네트워크에서 사용자 환경과 참여를 쉽게 정량화하고 소화할 수 있습니다. 통신 관리자 및 네트워크 관리자는 실시간 이벤트 및 네트워크 활동을 시청할 수 있으므로 병목 상태를 신속하게 해결하여 네트워크 성능을 최대화할 수 있습니다.

이러한 옵션에 대해 자세히 알아보려면 [이 링크를](https://kollective.com/microsoft-live-events/) 확인하세요.

### <a name="microsoft-ecdn"></a>Microsoft eCDN

**Microsoft eCDN** 은 모든 손 모임과 같은 대규모 회사 가상 이벤트 중에 발생하는 네트워크 정체 문제를 해결합니다. Microsoft eCDN은 LAN을 통해 메시 네트워크를 형성하여 부하를 95% 줄이고 네트워크 문제를 제거합니다. Microsoft eCDN은 WebRTC를 기본으로 사용하는 최초의 eCDN으로, 소프트웨어 또는 하드웨어 설치가 필요하지 않음을 의미합니다. 포춘지 선정 500대 고객은 네트워킹 문제를 완화하고 가장 큰 기업 이벤트에 대해 Peer5를 신뢰합니다.

- Microsoft eCDN에 대한 제로 설정 네트워크 구성은 원격 작업자 및/또는 비디오 트래픽이 많으면 네트워크에 부담을 주거나 비용이 많이 드는 인프라에 투자할 의무가 없습니다. 여기에는 자동 사이트 검색, 자동 VPN 검색 및 자동 NAT/방화벽 순회가 포함됩니다. [이 링크](/ecdn/how-to/enable-microsoft-ecdn-for-your-tenant)에서 자세히 알아보세요.
- Microsoft eCDN을 사용한 자동 테스트를 사용하면 IT 관리자가 회사 네트워크에서 대규모 라이브 이벤트를 시뮬레이션하여 실제 이벤트 전에 철저하고 중단 없는 테스트 및 문제 해결을 허용할 수 있습니다. [이 링크](/ecdn/how-to/perform-silent-test)에서 자세히 알아보세요.
- Microsoft eCDN의 업계 최고의 분석은 세분화된 분석을 제공하고 관리자가 스트리밍 문제의 근본 원인을 신속하게 찾을 수 있도록 합니다. 도구 키트에는 배달 및 UX 메트릭, 고급 드릴다운, 사용자별 분석 및 백 엔드 API가 포함됩니다. [이 링크](/ecdn/technical-documentation/analytics)에서 자세히 알아보세요.

### <a name="ramp"></a>램프

**Ramp eCDN** 은 라이브 이벤트 및 VOD(주문형 비디오)를 스트리밍할 때 네트워크 대역폭 소비를 90% 이상 줄입니다. Ramp를 사용하여 멀티캐스트, 캐싱 및 피어 투 피어 네트워킹과 같은 eCDN 기술의 조합을 혼합하고 일치시킬 수 있습니다. 중앙 집중식 관리, 모니터링 및 통찰력 있는 분석을 통해 네트워크 성능에 대한 가시성과 제어를 확보하여 최고 품질의 뷰어 환경을 만듭니다.

- **램프 멀티캐스트+** 는 라이브 비디오를 스트리밍하는 가장 효율적인 방법입니다. 멀티캐스트 프로토콜을 사용하면 100, 10,000 또는 100,000명의 뷰어가 있는지 여부에 관계없이 하나의 뷰어에 필요한 대역폭만 사용합니다. [이 링크](https://www.rampecdn.com/altitudecdn/multicast/)에서 자세히 알아보세요.
- **Ramp OmniCache™** 는 로컬 캐시를 사용하여 가까운 대상에게 라이브 및 VOD 비디오를 제공하는 비디오 관련 캐싱 소프트웨어로, 인터넷 연결 및 WAN 링크를 통해 이동하는 비디오 스트림의 수를 크게 줄입니다. [이 링크](https://www.rampecdn.com/altitudecdn/video-cache/)에서 자세히 알아보세요.
- **램프 P2P(피어 투 피어)** 를 사용하면 인프라가 제한된 위치에서도 대역폭을 최적화할 수 있습니다. P2P는 동일한 콘텐츠를 시청하는 클라이언트 디바이스의 피어 네트워크를 빌드하여 비디오 스트림을 한 보기 디바이스에서 다른 보기 디바이스로 재배포합니다. [이 링크](https://www.rampecdn.com/altitudecdn/p2p/)에서 자세히 알아보세요.

### <a name="riverbed"></a>Riverbed

네트워크 최적화 업계 표준인 **Riverbed** 는 가속 솔루션을 Teams로 확장했습니다. Microsoft 365 고객은 Teams를 포함한 Microsoft 365 트래픽과 다양한 주요 엔터프라이즈 SaaS 서비스를 자신 있게 가속화하여 어디서나 인력 생산성을 높일 수 있습니다. Riverbed의 세계적 수준의 지원과 지속적인 투자에 대한 모든 보증과 함께 제공되는 손쉽게 설정을 통해 Teams 가속을 사용할 수 있습니다. [이 링크](https://www.riverbed.com/office365)에서 자세히 알아보세요.

> [!NOTE]
> 선택한 eCDN 솔루션은 선택한 파트너 eCDN 공급자의 서비스 약관 및 개인 정보 취급 방침의 적용을 받으며, 이 정책은 eCDN 공급자의 솔루션 사용을 제어합니다. eCDN 공급자 솔루션의 사용은 Microsoft 볼륨 라이선스 조건 또는 온라인 서비스 약관의 적용을 받지 않습니다. 타사 공급자의 약관에 동의하지 않는 경우 Microsoft Teams에서 eCDN 솔루션을 사용하도록 설정하지 마세요.

## <a name="configure-stream-encoder-type-events-for-your-ecdn-solution"></a>eCDN 솔루션에 대한 Stream 인코더 형식 이벤트 구성

eCDN 솔루션을 구매하고 설정한 후 Microsoft Teams 또는 Yammer를 통해 생성된 Stream encoder 라이브 이벤트를 포함하여 Microsoft Stream 사용할 수 있도록 설정할 수 있습니다.

1. Microsoft 365 전역 관리자 또는 Teams 관리자로 Teams 관리 센터를 열고 [라이브 이벤트 설정](https://admin.teams.microsoft.com/broadcasts/settings) 페이지로 이동합니다.
1. **비디오 배포 공급자** 를 켜기로 전환 **합니다**.
1. **비디오 배포 공급자** 드롭다운 목록에서 **eCDN/SDN 공급자** 를 선택합니다.
1. 솔루션 공급자의 지시에 따라 다른 필드를 채웁니다(모든 솔루션 공급자가 모든 필드를 사용하는 것은 아님).
1. **저장** 을 선택합니다.
1. 설정이 올바른지 확인하려면 **설치 확인을** 선택합니다.
    - 유효성을 검사할 조직의 비디오를 검색합니다.
    - eCDN 공급자가 올바르게 설정된 경우 설치 확인 도구에 **성공** 메시지가 표시됩니다.
    - 올바르게 설정되지 않은 경우 **실패** 메시지가 표시됩니다. 문제 해결을 위해 공급자와 공유할 이벤트 메시지를 복사합니다.

eCDN 솔루션에 대해 Teams를 구성한 후 Teams에서 재생되는 모든 비디오 또는 라이브 이벤트는 해당 솔루션을 자동으로 활용합니다.

## <a name="configure-teams-production-type-events-through-teams-and-yammer-for-your-ecdn-solution"></a>eCDN 솔루션에 대한 Teams 및 Yammer를 통해 Teams 프로덕션 유형 이벤트 구성

Teams 또는 Yammer를 통해 Teams 라이브 이벤트를 만들려는 경우 [Microsoft Teams와 통합되도록 eCDN 공급자를 구성](teams-live-events/what-are-teams-live-events.md#enterprise-content-delivery-network-ecdn) 해야 합니다.

### <a name="get-to-video-analytics-reports-for-your-ecdn-solution"></a>eCDN 솔루션에 대한 비디오 분석 보고서 가져오기

위에서 설명한 것처럼 일부 eCDN 솔루션은 재생 세션, 뷰어 및 서비스 품질에 대한 심층적인 정보를 제공하는 분석 보고서도 제공합니다. 공급자가 Teams 관리 센터에서 공급자를 설정할 때 구성할 분석 보고서 URL 템플릿을 제공한 경우 비디오 또는 이벤트의 소유자는 특정 비디오 또는 이벤트에 대한 분석 보고서에 쉽게 도착할 수 있습니다.

비디오 소유자는 비디오 바로 아래에 분석 탭을 볼 수 있습니다. 이 탭에는 소유자가 eCDN 공급자 시스템에서 이 특정 비디오에 대한 분석 보고서에 액세스할 수 있는 링크가 있습니다.

Teams 관리자인 경우 라이브 이벤트 또는 비디오의 소유자가 아니더라도 액세스 권한을 상승하여 분석 탭을 보고 eCDN 분석 보고서 링크에 액세스할 수도 있습니다.

1. Teams 관리자로 비디오 플레이어 페이지로 이동합니다.
1. **설정을** 선택합니다.
1. **관리 모드에서 보기를** 선택합니다.
1. 분석 탭 **을** 선택합니다.

## <a name="troubleshooting-issues"></a>문제 해결

eCDN 솔루션이 네트워크에서 올바르게 설정되어 있고 해당 지침 및 특정 구성 문자열에 따라 공급자를 사용하도록 Teams를 올바르게 구성했는지 확인합니다. 여전히 문제가 있는 경우 아래 정보 중 일부가 도움이 될 수 있습니다.

### <a name="verify-setup-tool"></a>설치 도구 확인

eCDN 솔루션에 문제가 있는 경우 항상 돌아와 **서 설치 확인** 도구를 실행할 수 있습니다. 테스트 비디오에 대해 표시된 eCDN 공급자 이벤트 메시지는 사용자와 eCDN 공급자에게 작동하지 않는 항목에 대한 자세한 정보를 제공할 수 있습니다.

- **설정** > **관리 설정** > **eCDN 공급자** > **설정 확인** 으로 이동합니다.

### <a name="disable-ecdn-for-a-specific-session-via-url-query-string"></a>URL 쿼리 문자열을 통해 특정 세션에 대해 eCDN 사용 안 함

eCDN 솔루션 또는 Teams에서 발생하는 문제가 있는지 확인하려면 쿼리 문자열을 통해 특정 재생 세션에 대해 eCDN 솔루션을 쉽게 사용하지 않도록 설정할 수 있습니다.

- 재생 URL에 물음표가 이미 있는 경우 **&disableSDN=true** 를 추가합니다. 
- 재생 URL에 물음표가 없는 경우 **?**, 그 안에 **?disableSDN=true** 를 추가합니다.

### <a name="view-ecdn-info-in-browser-console"></a>브라우저 콘솔에서 eCDN 정보 보기

eCDN 솔루션 공급자가 지원하는 경우 솔루션을 통해 재생을 초기화하는 동안 디버그 정보를 인쇄할 수 있습니다. 이 추가 정보는 무엇이 잘못되는지 확인하는 데 도움이 될 수 있습니다. 쿼리 문자열을 통해 추가 콘솔 디버그 메시지를 사용하도록 설정할 수 있습니다.

- 재생 URL에 물음표가 이미 있는 경우&**isSDNDebug=true** 를 추가합니다.
- 재생 URL에 물음표가 없으면 **?**, 그 안에 **?isSDNDebug=true** 를 추가합니다.

브라우저가 활성화되어 있을 때 키보드에서 **F12** 를 선택하고 **콘솔** 탭으로 전환하여 재생 URL에 isSDNDebug=true 쿼리 문자열이 설정된 페이지를 로드하는 동안 인쇄된 모든 정보를 확인합니다.
