---
title: 클라우드 음성 워크로드에 대한 환경 평가
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 사용자 및 네트워크 분석을 사용하여 조직의 준비 상태를 평가하고, 올바른 TCP 및 UDP 포트를 열고, 네트워크 수정을 수행할 수 있습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 350af8c004f44205c6228b0dc734da25602062d0
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739326"
---
# <a name="evaluate-my-environment"></a>내 환경 평가

이 문서에서는 클라우드 음성 서비스를 사용하려면 현재 환경을 제대로 평가하기 위한 요구 사항에 대해 간략하게 소개합니다. 환경을 평가하여 전체 클라우드 음성 배포에 영향을 주는 위험 및 요구 사항을 식별합니다. 이러한 항목을 먼저 식별하여 계획을 조정하여 성공을 주도할 수 있습니다.

## <a name="introduction-to-evaluating-your-environment"></a>환경 평가 소개

목표 주요 결과(OKRS)를 달성하기 위해 이전에 주요 서비스 결정을 내렸다. 다음 단계는 환경 검색을 수행하여 IT 및 전화 통신 인프라, 네트워킹 및 운영과 관련된 모든 측면을 평가하여 조직이 솔루션을 구현할 준비가 됐는지 확인하는 것입니다.

환경 검색에는 네트워크가 통화 계획 서비스를 사용하여 오디오 회의 또는 전화 시스템의 구현을 지원할 수 있도록 네트워크 준비 평가가 포함되어야 합니다.

환경 평가 및 채택 준비 평가의 일부로 기술 위험을 식별하고 식별된 각 위험에 대한 완화 계획을 개발합니다.
이 정보를 위험 레지스터에 통합해야 합니다.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>현재 환경

환경 검색의 일부로 하드웨어 요구 사항에서 소프트웨어 요구 사항까지 PC 및 모바일 디바이스의 준비 평가와 같은 최종 사용자 컴퓨팅과 관련된 모든 사항을 포함합니다.

환경 검색은 전화 번호를 Microsoft로 이전해야 하는지 여부도 [발견할 수 있습니다.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
이를 알면 조직에서 프로젝트 계획을 그에 따라 조정하고 번호 포터링에 필요한 정보를 준비하는 데 도움이 됩니다. [Microsoft Teams](environmental-discovery-for-microsoft-teams-rollout.md) 롤아웃에 환경 검색을 사용하여 환경 검색을 수행할 수 있습니다.

<table>
<tr><td>제목</td><td>설명</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>환경 평가를 완료할 책임이 있는 사람이 누구인가요?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>환경 평가 결과를 문서화합니다.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>관리 평가 기능 채택 및 변경

배포는 사용자의 손 끝에 새로운 기술을 제공하지만 비즈니스 결과는 사용자가 해당 솔루션을 자신의 솔루션으로 진정으로 채택한 후에만 실현됩니다. 새 솔루션의 지속적인 도입을 보장하려면 사용자 준비 및 변경 관리에 집중해야 합니다. 최적의 결과를 위해 사용자 준비 계획을 기술 준비 활동에 대한 병렬 작업 스트림으로 수행하고 다음 활동을 통합합니다.

-   **조직 및 사용자 프로파일링:** 사용 사례 및 사용자 분석 외에도 변경될 조직의 인식도 분석

-   **준비 및 리소스 준비:** 사용자 구매를 가속화하기 위한 포커스가 있는 가치 메시징을 포함하여 대상 및 광범위한 범위 인식, 교육 및 지원 리소스 만들기

다음 고려 사항을 사용하여 사용자 변경 관리를 해결하기 위해 조직의 준비 상태를 평가합니다.

<table>
<tr><td>제목</td><td>설명</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>소프트웨어 또는 서비스의 사용자 채택에 성공한 이전이 있나요?</li><li>사용량 업케이크를 추적할 수 있나요?</li><li>초기 및 지속적인 채택 캠페인(인식, 교육 및 지원)을 디자인하고 관리하는 리소스가 &mdash; &mdash; 있나요?</li><li>전담 사용자 도입/변경 관리 팀이 있나요? 아니면 비즈니스 결과를 보장하기 위해 해당 리소스에 투자할 수 있나요?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>위의 모든 질문에 "예"라고 대답한 경우 올바른 사용자 변경 관리 이해 관계자를 식별하고 사용자 준비 계획을 &quot; &quot; 시작하십시오.</li><li>위의 일부 또는 전체에 응답하지 않았다면 조직에 대한 변경 관리 및 채택 관련 활동을 구동하는 데 도움이 될 수 있도록 외부 리소스에 &quot; &quot; 참여하는 것을 고려합니다.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>네트워크 준비

Teams는 적응할 수 있는 오디오 및 비디오 기술(코덱)을 사용하므로 대부분의 네트워크 조건에서 더 잘 수행됩니다. 최적의 성능을 보장하기 위해 Teams에 대한 네트워크를 준비해야 합니다.

![품질의 세 가지 구성 요소를 설명하는 다이어그램](media/evaluate-my-environment-image1.png "세 가지 품질 구성 요소 및 서비스 관리가 세 구성 요소 모두를 겹치는 방법을 설명하는 다이어그램입니다. 네트워크에 포커스가 있습니다.")

## <a name="key-takeaways"></a>키 찍기

이 지침의 주요 지침입니다. 해야 해:

-   Teams를 사용할 클라이언트에서 80 및 443의 TCP 포트를 여는 경우.

-   Teams를 사용할 클라이언트에서 발신하는 UDP 포트 3478~3481을 여는 경우

-   Teams를 배포하기에 충분한 대역폭이 필요한지 확인

-   네트워크 평가 [도구를 실행하고](https://www.microsoft.com/download/details.aspx?id=53885) 에지 세그먼트와 클라이언트 세그먼트의 미디어 품질 및 네트워크 연결 성능에 설명된 요구 사항을 충족하는지 확인합니다. [](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

## <a name="why-should-you-prepare-your-network"></a>네트워크를 준비해야 하는 이유는 무엇입니까?

수행될 단계를 살펴보기 전에 Teams의 성능에 영향을 줄 수 있는 것을 이해하여 사용자 만족도와 만족도를 높이는 것이 중요합니다.
세 가지 주요 위험 영역은 사용자가 네트워크 품질을 인식하는 방식에 영향을 줄 수 있습니다.

-   사용 가능한 대역폭 부족

-   방화벽 및 프록시 차단기

-   지터 및 패킷 손실과 같은 네트워크 장애

아래 설명된 단계는 배포가 이러한 요소의 영향을 받을 수 있는지 여부를 결정하는 데 도움이 며 해결 방법을 진행하는 데 도움이 됩니다.
네트워크를 준비하지 못하면 사용자에 불만이 있을 수 있으며 비용이 많이 드는 추가 수정이 발생할 수 있습니다. Teams를 위해 네트워크와 조직을 준비하여 성공 확률을 크게 늘려 줄 수 있습니다.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>대역폭 계획

네트워크 준비를 위한 첫 번째 단계는 네트워크가 사용자에게 제공할 수 있는 모달에 사용할 수 있는 대역폭을 확보하는 것입니다. 충분한 대역폭을 계획하는 것은 매우 간단한 작업으로, 사용자에게 고품질 Teams 환경을 제공하도록 매우 낮은 장벽이 시작됩니다.

### <a name="local-internet-egress"></a>로컬 인터넷 보안

많은 네트워크는 허브 및 스포크 토폴로지 사용을 위해 디자인됩니다. 이 토폴로지에서 인터넷 트래픽은 일반적으로 WAN을 중앙 데이터 센터로 트래버스한 후 인터넷으로(전송) 나타났습니다. 일반적으로 전체 비용을 절감하기 위해 네트워크 보안 디바이스를 중앙 집중화하기 위해 수행됩니다.

WAN에서 트래픽을 백-링하면 대기 시간이 늘어나고 품질 및 사용자 환경에 부정적인 영향을 미치게 됩니다. Microsoft Teams는 Microsoft의 대규모 글로벌 네트워크에서 실행하기 때문에 사용자와 가까운 네트워크 피어링 위치가 있는 경우가 종종 있습니다. 사용자는 해당 위치와 가까운 로컬 인터넷 지점에서 최대한 빨리 음성 최적화 네트워크로 이동하여 더 나은 성능을 얻을 수 있습니다. 일부 워크로드의 경우 DNS 요청은 가장 가까운 프런트 엔드 서버로 트래픽을 보내는 데 사용됩니다. 이러한 경우 로컬 시작 지점을 사용할 때 로컬 DNS 확인과 페어링하는 것이 중요합니다.

Microsoft의 글로벌 네트워크에 대한 네트워크 경로를 최적화하면 성능이 향상되고 궁극적으로 사용자에게 최상의 환경을 제공합니다. 자세한 내용은 [Office 365에서](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)최상의 연결 및 성능 향상 블로그 게시물을 참조하세요.

### <a name="vpn"></a>VPN

VPN은 많은 조직에 유용한 서비스를 제공합니다. 안타깝게도 일반적으로 실시간 미디어를 지원하도록 설계되거나 구성되지 않습니다. 일부 VPN은 UDP를 지원하지 않을 수도 있습니다. VPN은 이미 암호화된 미디어 트래픽 위에 추가 암호화 계층을 도입합니다. 또한 VPN 디바이스를 통한 트래픽 고정으로 인해 Teams 서비스에 대한 연결이 효율적이지 않을 수 있습니다.
또한 Teams에서 요구하는 예상되는 부하를 수용하기 위해 용량 관점에서 설계할 필요는 없습니다.

Teams 트래픽에 대한 VPN을 우회하는 대체 경로를 제공하는 것이 좋습니다. 이를 일반적으로 분할 터널 *VPN으로 알려져 있습니다.* 분할 터널링은 Microsoft 365 또는 Office 365에 대한 트래픽이 VPN을 트래버스하지 않고 Microsoft 365 또는 Office 365로 직접 이동하는 것입니다. 이 변경은 품질에 긍정적인 영향을 주지만 VPN 디바이스 및 조직의 네트워크에서 부하를 줄이는 보조 이점도 제공합니다.

분할 터널을 구현하려면 VPN 공급업체에 구성 세부 정보를 문의하세요.

### <a name="wi-fi"></a>Wi-Fi

VPN과 Wi-Fi 네트워크는 반드시 실시간 미디어를 지원하도록 설계되거나 구성되지는 않습니다. Teams를 지원하기 위한 Wi-Fi 네트워크 계획 또는 최적화는 고품질 배포에 대한 중요한 고려 사항입니다.

네트워크의 최적화를 위해 몇 가지 Wi-Fi 있습니다.

-   QoS 또는 Wi-Fi 멀티미디어(WMM)를 구현하여 미디어 트래픽이 네트워크에서 Wi-Fi 합니다.

-   Wi-Fi 및 액세스 지점 배치를 계획하고 최적화합니다. 2.4GHz 범위는 액세스 지점 배치에 따라 적절한 환경을 제공할 수 있지만 액세스 지점은 해당 범위에서 작동하는 다른 소비자 디바이스의 영향을 받는 경우가 종종 있습니다. 5GHz 범위는 조밀한 범위로 인해 실시간 미디어에 더 적합하지만 충분한 커버리지를 얻기 위해 더 많은 액세스 지점이 필요합니다. 또한 엔드포인트는 해당 범위를 지원하고 해당 대역을 그에 따라 활용하도록 구성해야 합니다.

-   이중 대역 Wi-Fi 네트워크가 배포된 경우 밴드 스티어링을 구현하는 것이 있습니다. 밴드 스티어링은 5GHz 범위를 사용하기 위해 Wi-Fi 공급 업체가 이중 대역 클라이언트에 영향을 주기 위해 구현하는 기술입니다.

-   동일한 채널의 액세스 지점이 너무 가깝게 닫히면 신호가 겹치고 의도치 않은 경쟁이 발생하여 사용자에게 좋지 않은 환경이 발생할 수 있습니다. 서로 옆에 있는 액세스 지점이 겹치지 않는 채널에 있도록 합니다.

각 무선 공급업체에는 무선 솔루션을 배포하기 위한 자체 권장 사항이 있습니다. 특정 지침은 공급업체에 문의하는 것이 좋습니다.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>방화벽 및 프록시 요구 사항

Microsoft Teams는 Microsoft Online Services 연결하고 이를 위해 인터넷 연결이 필요합니다. Teams가 올바르게 작동하려면 클라이언트에서 인터넷으로 TCP 포트 80 및 443을 열고 클라이언트에서 인터넷으로 3478~3481 UDP 포트를 열아야 합니다. TCP 포트는 SharePoint Online, Exchange Online 및 Teams 채팅 서비스와 같은 웹 기반 콘텐츠에 연결하는 데 사용됩니다.
플러그 인 및 커넥터도 이러한 TCP 포트를 통해 연결합니다. 4개의 UDP 포트는 오디오 및 비디오와 같은 미디어에 사용되어 올바르게 흐르게 합니다.

이러한 포트를 여는 것은 신뢰할 수 있는 Teams 배포에 필수적입니다. 이러한 포트를 차단하면 미디어 품질에 영향을 미치게 됩니다.

조직에서 이러한 포트를 열 정확한 IP 주소 범위 및 도메인을 지정해야 하는 경우 이러한 포트에 대한 대상 IP 범위 및 도메인을 제한할 수 있습니다. 정확한 포트, 프로토콜 및 IP 범위 목록은 [Microsoft 365 또는 Office 365 URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)및 IP 주소 범위를 참조하세요.
대상 IP 주소 범위 및 도메인을 제한하도록 선택하는 경우 변경될 수 있기 때문에 포트 및 범위 목록을 최신으로 유지해야 합니다. 변경이 발생하면 [이 RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) 피드를 구독하여 업데이트할 수 있습니다. 또한 정기적으로 비즈니스용 [Skype](https://www.microsoft.com/download/details.aspx?id=53885) 네트워크 평가 도구를 실행하여 모든 포트를 열 수 있는지 테스트하는 것이 좋습니다. 이 도구의 기능에 대한 자세한 내용은 다음 섹션에서 찾을 수 있습니다.

프록시 서버가 배포되는 경우 모든 Teams 서비스에 대한 프록시 서버를 무시하는 것이 좋습니다. 프록시 사용이 작동할 수 있는 경우 미디어가 UDP 대신 TCP를 강제로 사용하게 되어 품질이 감소할 가능성이 매우 좋습니다. 프록시 서버 및 무시에 대한 자세한 내용은 [Microsoft 365 또는 Office 365 URL 및 IP 주소 범위를 참조하세요.](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>네트워크 테스트

대역폭 업그레이드 및 방화벽에서 포트 열기 등 계획 및 네트워크 준비를 완료한 후 네트워크 성능을 테스트해야 합니다. 이 테스트의 결과는 통화 계획 구현을 통해 오디오 회의 또는 전화 시스템의 성공에 필요한 네트워크 최적화 또는 수정의 명확한 그림을 그릴 것입니다.

비즈니스용 Skype 네트워크 [평가](https://www.microsoft.com/download/details.aspx?id=53885) 도구를 다운로드하여 네트워크가 Teams에 대해 준비되어 있는지 테스트할 수 있습니다. 이 도구는 이중 기능을 제공합니다. 올바른 포트가 모두 열리면 테스트할 수 있으며 네트워크 장애를 테스트할 수 있습니다.

도구를 다운로드하여 설치한 후 C: 프로그램 파일 Microsoft 비즈니스용 Skype 네트워크 평가 도구에서 찾을 \\ \\ 수 있습니다. 이 디렉터리에 도구( Usage.docx)를 사용하는 방법에 대한 자세한 가이드가 포함되어 있습니다.

### <a name="test-for-opened-ports"></a>열어진 포트에 대한 테스트

명령 프롬프트 창을 열고 cd C: Program Files Microsoft 비즈니스용 Skype 네트워크 평가 도구를 입력하여 네트워크 평가 도구 **\\ \\ 디렉터리로 이동합니다.** 명령 프롬프트에서 **/connectivitycheck을** 입력하여networkassessmenttool.exe 시작

검사를 실행한 후 도구는 "확인 완료 완료" 메시지를 표시하거나 차단된 포트에 대한 보고서를 표시합니다.
또한 도구의 출력을 포함하는 Connectivity_results.txt 파일을 생성하고 %userprofile% appdata 로컬 비즈니스용 Microsoft Skype 네트워크 평가 도구 디렉터리에 \\ \\ \\ \\ 저장합니다.

포트가 열리고 올바르게 작동하도록 정기적으로 연결 검사를 실행하는 것이 좋습니다.

### <a name="test-for-network-impairments"></a>네트워크 장애 테스트

사용자 만족도를 높이기 위해 네트워크의 모든 장애를 제한해야 합니다.
가장 일반적인 네트워크 장애는 지연(대기 시간), 패킷 손실 및 지터입니다.

-   **대기 시간:** 네트워크의 지점 A에서 B 지점까지 IP 패킷을 수신하는 데 걸리는 시간입니다. 이 네트워크 전파 지연은 기본적으로 다양한 라우터에서 취한 추가 오버헤드를 포함하여 두 지점 간의 물리적 거리와 광속에 연결됩니다.
    대기 시간은 단방 또는 왕복 시간으로 측정됩니다.

-   **패킷 손실:** 이는 종종 특정 기간에 손실된 패킷의 백분율로 정의됩니다. 패킷 손실은 오디오를 완전히 잘라내는 백백 버스트 손실에 거의 영향을 주지 않고, 개별 손실된 작은 패킷에서 오디오 품질에 직접 영향을 미치게 됩니다.

-   **패킷 간 도착 지터 또는 간단히 지터:** 연속 패킷 간 지연의 평균 변경입니다. 비즈니스용 Skype를 비롯한 대부분의 최신 VoIP 소프트웨어는 버퍼링을 통해 일부 수준의 지터에 맞게 조정될 수 있습니다. 지터가 버퍼링을 초과하는 경우 참가자가 지터의 효과를 알 수 있습니다.

이러한 장애에 대한 최대값은 미디어 품질 및 네트워크 연결 [성능에 설명되어 있습니다.](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)
이러한 장애를 테스트할 때 두 개의 개별 세그먼트를 구분합니다.

-   *에지 세그먼트는* 라우터가 있는 세그먼트입니다. 각 위치에서 인터넷에 연결된 가장 가까운 논리 네트워크 세그먼트입니다. 대부분의 경우 라우터의 연결점 또는 경계 네트워크(DMZ, 비무장 영역 및 스크린된 서브넷)입니다.  라우터가 다른 디바이스에 영향을 주는 트래픽은 이 세그먼트와 인터넷 간에 발생하지 않습니다.

-   클라이언트 *세그먼트는* 클라이언트가 있는 논리적 네트워크 세그먼트입니다.

네트워크 평가 도구를 사용하여 두 세그먼트를 모두 테스트해야 합니다. 세그먼트를 테스트하기 위해 디렉터리로 이동하고 명령 **프롬프트에** networkassessmenttool.exe입력합니다. 결과는 Results.tsv라는 파일에 기록됩니다. 각 세그먼트의 요구 사항과 [비교할](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 수 있습니다.

두 세그먼트 모두 고품질 배포에 대한 요구 사항을 충족해야 합니다. 네트워크 성능을 잘 표시하려면 1시간 동안 도구를 여러 번 실행하는 것이 좋습니다.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>네트워크 수정

대역폭 계획, 포트 테스트 또는 네트워크 요구 사항 테스트의 결과가 Teams를 배포하기 전에 현재 네트워크에 수정이 필요하다고 표시되면 여러 가지 방법으로 이 작업을 수행할 수 있습니다.

-   대역폭이 부족한 경우 Microsoft 365 또는 Office 365로의 트래픽이 방해되지 않는 흐름을 할 수 있도록 연결을 업그레이드합니다.

-   차단된 포트의 경우 방화벽 규칙을 변경하고 포트를 다시 시도합니다.

-   네트워크 장애의 경우 항상 근본 원인 분석을 수행하십시오.

QoS(서비스 품질)는 트래픽의 우선 순위를 지정하고 구분하여 장애를 대면하는 데 사용할 수 있습니다. 일부 조직에서는 대역폭 문제를 해결하거나 트래픽 흐름의 양을 제한하기 위해 QoS를 배포하도록 선택하기도 합니다. 이로 인해 품질이 개선되지는 못하고 새로운 문제가 발생할 수 있습니다. 네트워크 장애가 요구 사항을 초과하는 경우 근본 원인 분석을 항상 수행해야 합니다. QoS는 솔루션이 될 수 있습니다.
자세한 내용은 [Microsoft Teams의 서비스 품질을 참조하세요.](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)

>[!NOTE]
>업그레이드, 확장 또는 기타 비즈니스 요구 사항으로 인해 시간이 지날 때 많은 네트워크가 발전합니다. 서비스 관리 계획의 일부로 이러한 영역을 유지 관리하기 위한 운영 프로세스가 준비되도록 합니다.


<table>
<tr><td>제목</td><td>설명</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>모든 네트워크 세그먼트 및 조직 위치에서 적절한 네트워크 평가를 완료할 책임은 누가 있나요?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>네트워크가 Microsoft Teams 배포에 사용할 준비가 되도록 자세한 네트워크 평가를 수행할 수 있습니다.</li><li>모든 네트워크 세그먼트에 대한 평가 결과에 따라 네트워크 수정을 수행합니다.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->
