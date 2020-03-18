---
title: Microsoft 팀을 위한 네트워크 준비 |  포트 방화벽 요구 사항
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: 이 지침을 사용 하 여 팀 배포 및 출시에 대 한 네트워크 준비
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d58613bc3455d5467e9e6c6589f73d498c6e1e3b
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706908"
---
# <a name="prepare-your-network-for-upgrading-to-teams"></a>팀으로 업그레이드 하기 위한 네트워크 준비

![여행 다이어그램 업그레이드, 기술 준비 단계 강조](media/upgrade-banner-tech-readiness.png "기술 준비 단계에 중점을 두어 업그레이드 여행 단계")

이 문서는 사용자 준비 단계와 병행 하 여 완료 한 활동 인 업그레이드 여행에 대 한 기술 준비 단계의 일부입니다. 계속 하기 전에 이전 단계에서 다음 활동을 완료 했는지 확인 합니다.

- [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

> [!Tip]
> 팀에서 네트워크를 활용 하는 방법과 최적의 네트워크 연결을 계획 하는 방법에 대 한 자세한 내용은 다음 세션을 시청 하세요. [팀 네트워크 계획](https://aka.ms/teams-networking)

오디오, 비디오 또는 모임을 배포 하는 경우 몇 가지 추가 단계를 수행 하 여 해당 기능에 맞게 네트워크를 최적화할 수 있습니다. 팀은 변화 시킬 수 있는 오디오 및 비디오 기술 (코덱)을 사용 하므로 대부분의 네트워크 상태에서 더 잘 수행 됩니다. 최적의 성능을 유지 하려면 팀을 위해 네트워크를 준비 해야 합니다.

![품질의 세 가지 구성 요소를 설명 하는 다이어그램](media/evaluate-my-environment-image1.png "품질의 세 가지 구성 요소와 서비스 관리가 세 구성 요소를 모두 겹치는 방법을 설명 하는 다이어그램입니다. 네트워크에 포커스를 둔 상태")

## <a name="why-should-you-prepare-your-network"></a>네트워크를 준비 해야 하는 이유는 무엇 인가요?

수행 해야 하는 단계를 살펴보기 전에 팀의 성능에 영향을 미칠 수 있는 요소와 사용자 만족도와 만족도를 이해 하는 것이 중요 합니다. 세 가지 주요 위험 영역은 사용자가 네트워크 품질을 어떻게 향상 시킬 수 있는지에 영향을 줍니다.

- 사용할 수 있는 대역폭 부족

- 방화벽 및 프록시 차단

- 지터 및 패킷 손실 등의 네트워크 장애

아래 설명 된 단계는 배포에 이러한 요인의 영향을 미치는지 여부를 확인 하는 데 도움이 되며 해결 방법으로 이동 하는 데 도움이 될 수 있습니다. 네트워크 준비에 실패 하면 사용자와 비용이 많이 드는 특별 한 수정이 발생할 수 있습니다. 팀에 대 한 네트워크 및 조직을 준비 하면 성공할 가능성을 대폭 높일 수 있습니다.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>대역폭 계획

Microsoft 팀은 네트워크 상태에 관계 없이 최상의 오디오, 비디오 및 콘텐츠 공유 환경을 제공 합니다. 변수 코덱에는 최소한의 영향으로 제한 된 대역폭 환경에서 미디어를 협상할 수 있습니다. 그러나 대역폭이 문제가 되지 않는 경우에는 최대 1080p 비디오 해상도, 최대 30fps, 콘텐츠의 경우 15fps, 고화질 오디오 등의 품질에 대해 경험을 최적화할 수 있습니다.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]

### <a name="local-internet-egress"></a>로컬 인터넷 송신

많은 네트워크는 허브 및 스포크 토폴로지를 사용 하도록 설계 되었습니다. 이 토폴로지에서 인터넷 트래픽은 일반적으로 WAN을 인터넷에 소개 (egresses) 하기 전에 중앙 집중화 된 데이터 센터로 트래버스 합니다. 이는 전반적인 비용 절감을 목표로 하는 네트워크 보안 장치를 중앙 집중화 하는 데 주로 사용 됩니다.

WAN을 통한 후면 hauling 소통량이 지연 되 고, 품질과 사용자 환경에 부정적인 영향을 줍니다. Microsoft 팀은 Microsoft의 대규모 전역 네트워크에서 실행 되므로 사용자에 게 가까이 있는 네트워크 피어 링 위치를 사용 하는 경우가 많습니다. 사용자는 로컬 인터넷 지점이 해당 위치와 가까운 곳에서 가능한 한 빨리 음성 최적화 네트워크로 이동 하 여 더 나은 성능을 얻을 수 있습니다. 일부 작업 부하의 경우 DNS 요청을 사용 하 여 가장 가까운 프런트 엔드 서버로 트래픽을 보냅니다. 이러한 경우 로컬 송신 지점을 사용 하는 경우 로컬 DNS 확인과 쌍을 이루는 것이 중요 합니다.

Microsoft 글로벌 네트워크에 대 한 네트워크 경로를 최적화 하면 성능이 개선 되 고 궁극적으로 사용자에 게 최상의 환경을 제공할 수 있습니다. 자세한 내용은 Office 365에서 블로그 게시물을 통해 [최상의 연결성 및 성능을 얻을 것](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)을 참고 하세요.

Microsoft 팀 내에서 실시간 미디어를 사용 하 여 최적의 경험을 얻으려면 Office 365의 네트워킹 요구 사항을 충족 해야 합니다. 자세한 내용은 [비즈니스용 Skype Online의 미디어 품질과 네트워크 연결 성능을](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)참조 하세요.

두 가지 네트워크 세그먼트 (클라이언트에서 Microsoft edge 및 고객 Edge에서 Microsoft Edge로)를 정의 하려면 다음 요구 사항을 충족 해야 합니다.

|**값** |**클라이언트에서 Microsoft Edge로** |**고객 Edge에서 Microsoft Edge로** |
|---|---|---|
|**대기 시간 (단방향)** |< 50 ms |< 30 밀리초 |
|**지연 (왕복 시간 또는 RTT)** |< 100 ms |< 60 ms |
|**버스트 패킷 손실** |200 밀리초 간격 중 10% < |200 밀리초 간격 중 1% < |
|**패킷 손실** |15 초 간격으로 1% < |15 초 간격으로 0.1% < |
|**패킷 간 도착 지터** |15 초 간격으로 30 밀리초 < |15 초 간격으로 15 밀리초 < |
|**패킷 순서 다시 매기기** |<0.05% 주문 종료 패킷 |<0.01% 주문 종료 패킷 |

두 네트워크 세그먼트를 모두 테스트 하려면 [네트워크 평가 도구](https://go.microsoft.com/fwlink/?linkid=855799)를 사용 하면 됩니다. 이 도구는 고객 네트워크에 지에 연결 된 PC와 직접 클라이언트 PC에 배포할 수 있습니다. 이 도구에는 제한 된 설명서가 포함 되어 있지만,이 도구를 사용 하는 방법에 대 한 더 깊은 문서는 [네트워크 준비 상태 평가](https://go.microsoft.com/fwlink/?linkid=855800)에서 찾을 수 있습니다. 이 네트워크 준비 평가를 실행 하 여 네트워크의 준비 상태를 확인 하 여 Microsoft 팀과 같은 실시간 미디어 응용 프로그램을 실행할 수 있습니다.

> [!NOTE]
> 이는 비즈니스용 Skype를 성공적으로 배포 하려고 하는 고객이 실행할 것을 권장 하는 것과 동일한 네트워크 준비 평가입니다.

### <a name="vpn"></a>VPN

Vpn은 여러 조직에 게 귀중 한 서비스를 제공 합니다. 불행 하 게도 일반적으로 실시간 미디어를 지원 하도록 디자인 되지 않았거나 구성 되어 있지 않습니다. 일부 Vpn에서는 UDP가 지원 되지 않을 수도 있습니다. Vpn은 이미 암호화 된 미디어 트래픽 위에 추가 암호화 계층을 도입 하기도 합니다. 또한 VPN 장치를 통해 헤어 고정 트래픽 때문에 팀 서비스에 대 한 연결이 효율적이 지 않을 수 있습니다. 또한 팀이 필요로 하는 예상 부하를 수용할 수 있도록 용량 측면에서 디자인 되지 않았습니다.

팀 트래픽용 VPN을 우회 하는 대체 경로를 제공 하는 것이 좋습니다. 이는 일반적으로 *분할 터널 VPN*이라고 합니다. 분할 터널링은 Office 365에 대 한 트래픽이 VPN을 통과 하지는 않지만 Office 365로 바로 이동 한다는 것을 의미 합니다. 이 변경은 품질에 긍정적인 영향을 주지만, VPN 장치 및 조직의 네트워크에서 로드를 줄이는 두 번째 이점을 제공 합니다.

분할 터널을 구현 하려면 VPN 공급 업체에 구성 세부 정보를 문의 하세요.

### <a name="wi-fi"></a>Wi-fi

VPN과 마찬가지로 Wi-fi 네트워크는 실시간 미디어를 지원 하도록 설계 또는 구성 되지 않습니다. 팀을 지원 하기 위해 Wi-fi 네트워크를 계획 하거나 최적화 하는 것은 고품질 배포를 위한 중요 한 고려 사항입니다.

Wi-fi 네트워크를 최적화 하기 위해 다음과 같은 몇 가지 요소를 재생할 수 있습니다.

- 미디어 소통량이 Wi-fi 네트워크를 통해 우선 순위를 유지 하도록 QoS 또는 Wi-fi 멀티미디어 (WMM)를 구현 합니다.

- Wi-fi 밴드 및 액세스 지점의 위치를 계획 하 고 최적화 합니다. 2.4 GHz 범위는 액세스 지점 배치에 따라 적절 한 환경을 제공할 수 있지만 액세스 지점은 해당 범위에서 작동 하는 다른 소비자 장치에 영향을 받는 경우가 많습니다. 5ghz 범위는 해당 집적형 범위로 인해 실시간 미디어에 더 적합 하지만, 충분 한 서비스를 얻으려면 더 많은 액세스 포인트가 필요 합니다. 또한 끝점은 해당 범위를 지원 하 고 그에 따라 이러한 대역을 활용 하도록 구성 해야 합니다.

- 듀얼 밴드 Wi-fi 네트워크를 배포 하는 경우에는 밴드 조절을 구현 하는 것이 좋습니다. _밴드 조종_ 은 듀얼 밴드 클라이언트에 게 5ghz 범위를 사용 하는 데 영향을 주는 wi-fi 공급 업체에서 구현한 기술입니다.

- 같은 채널의 액세스 지점이 너무 가까이 있으면 신호가 겹치고 실수로 인해 경합 하 여 사용자에 게 좋지 않은 환경이 생성 될 수 있습니다. 서로 인접 한 연결점이 겹치지 않는 채널에 있는지 확인 합니다.

각 무선 공급 업체에는 해당 무선 솔루션을 배포 하기 위한 고유한 권장 사항이 있습니다. 특정 지침을 보려면 공급 업체에 문의 하는 것이 좋습니다.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>방화벽 및 프록시 요구 사항

Microsoft 팀은 Microsoft 온라인 서비스에 연결 되며 인터넷에 연결 되어 있어야 합니다. 팀이 제대로 작동 하려면 클라이언트에서 인터넷으로 TCP 포트 80 및 443을 열고 클라이언트에서 인터넷에 대 한 UDP 포트 3478 ~ 3481을 표시 해야 합니다. TCP 포트는 SharePoint Online, Exchange Online, 팀 채팅 서비스 등의 웹 기반 콘텐츠에 연결 하는 데 사용 됩니다. 또한 플러그 인 및 커넥터는 이러한 TCP 포트를 통해 연결 됩니다. 오디오 및 비디오 등의 미디어에 4 개의 UDP 포트를 사용 하 여 올바르게 흐를 수 있도록 합니다.

이러한 포트를 여는 것은 안정적인 팀 배포에 필수적입니다. 이러한 포트 차단은 지원 되지 않으며 미디어 품질에 영향을 줍니다.

조직에서 이러한 포트를 열어야 하는 정확한 IP 주소 범위 및 도메인을 지정 해야 하는 경우 이러한 포트에 대 한 대상 IP 범위 및 도메인을 제한할 수 있습니다. 정확한 포트, 프로토콜 및 IP 범위 목록은 [Office 365 url 및 ip 주소 범위](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)를 참조 하세요. 대상 IP 주소 범위와 도메인을 제한 하도록 선택 하는 경우 포트와 범위 목록을 변경 하는 데 문제가 있을 수 있으므로이를 반드시 유지 해야 합니다. 변경 내용이 있을 때 [이 RSS 피드](https://go.microsoft.com/fwlink/p/?linkid=236301) 를 업데이트 하도록 구독할 수 있습니다. 또한, 정기적으로 [비즈니스용 Skype 네트워크 평가 도구](https://www.microsoft.com/download/details.aspx?id=53885) 를 실행 하 여 모든 포트가 열려 있는지 테스트 하는 것이 좋습니다. 이 도구의 기능에 대 한 자세한 내용은 다음 섹션에서 확인할 수 있습니다.

프록시 서버를 배포 하는 경우 모든 팀 서비스에 대 한 프록시 서버를 우회 하는 것이 좋습니다. 프록시를 사용 하는 것이 가능 하지만, UDP 대신 TCP를 강제로 사용 하도록 미디어가 작동 하기 때문에 품질이 저하 될 가능성이 높습니다. 프록시 서버 및 바이패스에 대 한 자세한 내용은 [Office 365 url 및 IP 주소 범위](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)를 참조 하세요.

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>추가 네트워크 고려 사항

### <a name="external-name-resolution"></a>외부 이름 확인

팀 클라이언트를 실행 하는 모든 클라이언트 컴퓨터에서 외부 DNS 쿼리를 확인 하 여 Office 365에서 제공 하는 서비스를 검색할 수 있는지 확인 합니다.

### <a name="nat-pool-size"></a>NAT 풀 크기

여러 사용자와 장치가 NAT (Network Address Translation) 또는 PAT (Port Address Translation)를 사용 하 여 Office 365에 액세스 하는 경우, 공개적으로 라우팅할 수 있는 각 IP 주소 뒤에 숨겨진 장치가 지원 되는 번호를 초과 하지 않는지 확인 해야 합니다.

이 위험을 줄이려면 포트 소모를 방지 하기 위해 적절 한 공용 IP 주소가 NAT 풀에 할당 되어 있는지 확인 합니다. 포트 소모를 통해 Office 365 서비스에 연결할 때 내부 최종 사용자 및 장치가 문제를 발생 시킬 수 있습니다. 자세한 내용은 [Office 365의 NAT 지원을](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365)참조 하세요.

### <a name="intrusion-detection-and-prevention-guidance"></a>침입 감지 및 예방 지침

아웃 바운드 연결에 대 한 추가 보안 계층에 대 한 침입 감지 시스템 및/또는 침입 방지 시스템을 보유 하 고 있는 경우, 해당 대상으로 Office 365 Url이 있는 트래픽이 허용 목록 확인 합니다.

## <a name="test-the-network"></a>네트워크 테스트

방화벽에서 대역폭 업그레이드 및 포트 열기를 포함 하 여 계획 및 네트워크 준비를 완료 한 후 네트워크 성능을 테스트 해야 합니다. 이 테스트 결과는 팀 구현의 성공에 필요한 네트워크 최적화 또는 재구성에 대 한 명확한 그림을 칠합니다.

[비즈니스용 Skype 네트워크 평가 도구](https://www.microsoft.com/download/details.aspx?id=53885) 를 다운로드 하 여 네트워크가 팀을 위한 준비가 되었는지 테스트할 수 있습니다. 이 도구는 모든 올바른 포트가 열려 있는지 여부를 테스트 하 고 네트워크 장애를 테스트할 수 있는 듀얼 기능을 제공 합니다.

이 도구를 다운로드 하 여 설치한 후에는 C:\Program Files (x86) \Microsoft 비즈니스용 Skype 네트워크 평가 도구에서 찾을 수 있습니다. 이 도구를 사용 하는 방법에 대 한 자세한 안내서는 해당 디렉토리에 포함 되어 있습니다.

### <a name="test-for-opened-ports"></a>열린 포트 테스트

명령 프롬프트 창을 열고 **cd C:\Program files (x86) \Microsoft 비즈니스용 Skype 네트워크 평가 도구**를 입력 하 여 네트워크 평가 도구 디렉터리로 이동 합니다. 명령 프롬프트에서 networkassessmenttool를 입력 하 여 열려 있는 포트 테스트를 시작 합니다 **/connectivitycheck**

검사를 실행 한 후에는 도구가 "확인 완료 됨" 메시지를 표시 하거나 차단 된 포트에 대 한 보고를 받습니다. 또한 도구의 출력을 포함\\하는 appdata\\Connectivity_results 라는 파일을 생성 하 고이 를% userprofile%, 비즈니스용 로컬\\microsoft 비즈니스용 skype 네트워크 평가 도구\\ 디렉터리에 저장 합니다.

연결 검사를 정기적으로 실행 하 여 포트가 열려 있고 올바르게 작동 하는지 확인 하는 것이 좋습니다.

### <a name="test-for-network-impairments"></a>네트워크 장애 테스트

사용자 만족도를 높이려면 네트워크에서 장애를 제한 해야 합니다. 가장 일반적인 네트워크 장애는 지연 (대기 시간), 패킷 손실 및 지터입니다.

- **대기 시간:** 네트워크의 A 점에서 B 지점의 IP 패킷을 가져오는 데 걸리는 시간입니다. 이 네트워크 전파 지연은 본질적으로 두 점과 라이트의 속도 사이에서 다양 한 라우터가 차지 하는 추가 오버 헤드를 포함 하 여 실제 거리에 연결 됩니다. 대기 시간은 단방향 또는 왕복 시간으로 측정 됩니다.

- **패킷 손실**:이는 특정 시간 창에서 손실 되는 패킷의 백분율로 정의 되는 경우가 많습니다. 패킷 손실은 오디오 품질에 직접적인 영향을 주며,이는 오디오가 완전히 잘리는 문제를 일으키는 후면 버스트 손실에 거의 영향을 주지 않는 작은 개인 패킷

- **패킷 간 도착 지터 또는 간단히 지터:** 연속 된 패킷 간의 지연 시간 변경입니다. 비즈니스용 Skype를 포함 하 여 대부분의 최신 VoIP 소프트웨어는 버퍼링을 통해 일부 지터 수준에 맞게 조정할 수 있습니다. 이는 지터가 지터의 효과를 알리는 버퍼링을 초과 하는 경우에만 해당 됩니다.

이러한 장애에 대 한 최대 값은 [미디어 품질과 네트워크 연결 성능](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)에 설명 되어 있습니다. 이러한 장애인을 테스트 하는 경우 두 개의 개별 세그먼트를 구분 합니다.

- *Edge 세그먼트* 는 라우터가 살아 있는 세그먼트입니다. 이는 각 위치에서 인터넷에 연결 된 가장 가까운 논리 네트워크 세그먼트입니다. 대부분의 경우이는 라우터의 연결 지점이 고, 경계 네트워크 ( *DMZ*, *완충 영역*및 *스크린 된 서브넷*이 라고도 함) 인 경우도 있습니다. 이 세그먼트와 인터넷 사이에 라우터 이외의 장치에 영향을 주는 소통량이 없습니다.

- *클라이언트 세그먼트* 는 클라이언트가 상주 하는 논리적 네트워크 세그먼트입니다.

네트워크 평가 도구를 사용 하 여 두 세그먼트를 모두 테스트 해야 합니다. 세그먼트를 테스트 하려면 디렉터리로 이동 하 고 명령 프롬프트에 **networkassessmenttool** 를 입력 합니다. 결과는 tsv 이라는 파일에 기록 되므로 각 세그먼트에 대 한 [요구 사항과](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 비교할 수 있습니다.

두 세그먼트가 고품질 배포에 대 한 요구 사항을 충족 해야 한다는 점에 유의 하세요. 한 시간에 여러 번 도구를 실행 하 여 네트워크 성능을 올바르게 표시 하는 것이 좋습니다.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>네트워크 재구성

팀을 배포 하기 전에 대역폭 계획, 포트 테스트 또는 네트워크 요구 사항 테스트 결과에서 현재 네트워크를 수정 해야 하는 경우 다음과 같은 여러 가지 방법으로이 작업을 수행할 수 있습니다.

- 대역폭 부족으로 연결을 업그레이드 하 여 Office 365에 대 한 트래픽이 unhindered 흐를 수 있도록 합니다.

- 차단 된 포트의 경우 방화벽 규칙을 변경 하 고 포트를 다시 테스트 합니다.

- 네트워크 장애인은 항상 근본 원인 분석을 수행 합니다.

QoS (서비스 품질)를 사용 하 여 트래픽 우선 순위를 매기기 및 구분 하 여 장애를 이동할 수 있습니다. 일부 조직에서는 대역폭 문제를 해결 하기 위해 QoS를 배포 하거나 트래픽 흐름의 양을 제한 하도록 선택 합니다. 이렇게 하면 품질이 개선 되지 않으며 새로운 문제가 발생할 수 있습니다. 네트워크 장애가 요구 사항을 초과할 경우 항상 근본 원인 분석을 수행 해야 합니다. QoS는 해결책이 될 수 있습니다. 자세한 내용은 [Microsoft 팀의 서비스 품질](qos-in-teams.md)을 참조 하세요.

>[!NOTE]
>많은 네트워크는 업그레이드, 확장 또는 기타 비즈니스 요구 사항으로 인해 시간에 따라 발전 했습니다. 이러한 영역을 서비스 관리 계획의 일부로 유지할 수 있도록 운영 프로세스가 준비 되어 있는지 확인 합니다.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>판단 요점</td><td><ul><li>모든 네트워크 세그먼트와 조직 위치에서 적절 한 네트워크 평가를 완료 해야 하는 사람은 누구 입니까?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>네트워크를 Microsoft 팀 배포에 사용할 수 있도록 자세한 네트워크 평가를 수행할 수도 있습니다. </li><li>모든 네트워크 세그먼트에 대 한 네트워크 준비 평가 결과에 따라 네트워크 수정을 수행 합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>키 takeaways

이 설명서의 주요 takeaways. 해야 해:

- 팀을 사용 하는 클라이언트에서 보내는 TCP 포트 80 및 443을 엽니다.

- 팀을 사용 하는 클라이언트에서 나가는 UDP 포트 3478 ~ 3481을 엽니다.

- 팀 배포에 필요한 대역폭이 충분 한지 확인 합니다.

- [네트워크 평가 도구](https://www.microsoft.com/download/details.aspx?id=53885) 를 실행 하 고 edge 세그먼트와 클라이언트 세그먼트 모두에서 [미디어 품질과 네트워크 연결 성능](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 에 설명 된 요구 사항을 충족 하는지 확인 합니다.

## <a name="related-topics"></a>관련 항목

[비디오: 네트워크 계획](https://aka.ms/teams-networking)
