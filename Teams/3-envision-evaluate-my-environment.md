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
description: 사용자 및 네트워크 분석을 사용하여 조직의 준비 상태를 평가하고, 올바른 TCP 및 UDP 포트를 열고, 네트워크 수정을 수행합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b65e6f2f6db4f5e824e55368d0a7a097eb39ad9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094776"
---
# <a name="evaluate-my-environment"></a>내 환경 평가

이 문서에서는 클라우드 음성 서비스를 사용하는 현재 환경을 올바르게 평가하기 위한 요구 사항에 대한 개요를 제공합니다. 환경을 평가하여 전체 클라우드 음성 배포에 영향을 줄 위험 및 요구 사항을 식별합니다. 이러한 항목을 먼저 식별하여 계획을 조정하여 성공을 주도할 수 있습니다.

## <a name="introduction-to-evaluating-your-environment"></a>환경 평가 소개

객관적인 주요 결과(OKRS)를 달성하기 위해 이전에 주요 서비스 결정을 내렸다. 다음 단계는 환경 검색을 수행하여 IT 및 전화 통신 인프라, 네트워킹 및 작업과 관련된 모든 측면을 평가하여 조직이 솔루션을 구현할 준비가 됐는지 확인하는 것입니다.

환경 검색에는 네트워크 준비 평가가 포함되어야 네트워크가 통화 계획 서비스를 사용하여 오디오 회의 또는 전화 시스템 지원할 수 있습니다.

환경 평가 및 채택 준비 평가의 일부로 기술 위험을 식별하고 식별된 각 위험에 대한 완화 계획을 개발합니다.
이 정보를 위험 레지스터에 통합해야 합니다.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>현재 환경

환경 검색의 일부로 하드웨어 요구 사항에서 소프트웨어 요구 사항까지 전화 계획 비즈니스 사용 사례를 지원하기 위해 PC 및 모바일 디바이스의 준비 평가와 같은 최종 사용자 컴퓨팅과 관련된 모든 전화 시스템 포함됩니다.

또한 환경 검색을 통해 Microsoft로 전화 번호를 전송해야 하는지 [여부를 규명할 수 있습니다.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
이를 알면 조직에서 프로젝트 계획을 그에 따라 조정하고 번호 포터링에 필요한 정보를 준비하는 데 도움이 됩니다. 환경 검색을 [](environmental-discovery-for-microsoft-teams-rollout.md) 사용하여 환경 Microsoft Teams 수행할 수 있습니다.

<table>
<tr><td>제목</td><td>설명</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>Who 평가를 완료할 책임이 있나요?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>환경 평가 결과를 문서화합니다.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>관리 평가 기능 채택 및 변경

배포는 사용자의 손끝에 새로운 기술을 제공하지만 비즈니스 결과는 사용자가 진정으로 해당 솔루션을 자신의 솔루션으로 채택한 후에만 실현됩니다. 새 솔루션의 지속적인 채택을 보장하려면 사용자 준비 및 변경 관리에 노력을 집중해야 합니다. 최적의 결과를 위해 기술 준비 활동에 병렬 작업 스트림으로 사용자 준비 계획을 수행하고 다음 활동을 통합합니다.

-   **조직 및 사용자 프로파일링:** 사용 사례 및 인물 분석 외에도 변경될 조직의 받아들이기 분석

-   **준비 및 리소스 준비:** 사용자 구매를 가속화하기 위한 포커스가 있는 가치 메시징을 포함하여 대상 및 광범위한 도달 인식, 교육 및 지원 리소스 만들기

다음 고려 사항을 사용하여 조직의 준비 상태를 평가하여 사용자 변경 관리를 해결합니다.

<table>
<tr><td>제목</td><td>설명</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>소프트웨어 또는 서비스의 사용자 채택을 통해 이전의 성공을 거쳤나요?</li><li>사용 현황을 추적할 수 있나요?</li><li>초기 및 지속적인 채택 캠페인(인식, 교육 및 지원)을 디자인하고 관리할 리소스가 &mdash; &mdash; 있나요?</li><li>전용 사용자 채택/변경 관리 팀이 있나요, 아니면 비즈니스 성과를 보장하기 위해 해당 리소스에 투자할 수 있나요?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>위의 모든 질문에 예에 응답한 경우 올바른 사용자 변경 관리 이해 관계자를 식별하고 사용자 준비 계획을 &quot; &quot; 시작합니다.</li><li>위의 일부 또는 전체에 대해 아니요에 응답한 경우 조직에 대한 변경 관리 및 채택 관련 활동을 구동하는 데 도움을 주기 위해 외부 리소스 참여를 &quot; &quot; 고려합니다.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>네트워크 준비

Teams 적응할 수 있는 오디오 및 비디오 기술(코덱)을 사용하므로 대부분의 네트워크 조건에서 더 나은 작업을 수행할 수 있습니다. 최적화되고 일관된 성능을 보장하기 위해 네트워크를 준비해야 Teams.

![품질의 세 가지 구성 요소를 설명하는 다이어그램](media/evaluate-my-environment-image1.png "품질의 세 가지 구성 요소와 서비스 관리가 세 구성 요소를 모두 겹치는 방법을 설명하는 다이어그램입니다. 네트워크에 포커스가 있습니다.")

## <a name="key-takeaways"></a>주요 인계

다음은 이 지침의 주요 인계입니다. 해야 해:

-   클라이언트에서 TCP 포트 80 및 443을 열고 Teams.

-   UDP 포트 3478~3481을 사용하여 클라이언트에서 UDP 포트를 Teams.

-   배포할 대역폭이 충분한지 Teams.

-   네트워크 [평가 도구를](https://www.microsoft.com/download/details.aspx?id=53885) 실행하고 에지 세그먼트와 클라이언트 세그먼트 모두에서 미디어 품질 및 네트워크 연결 성능에 설명된 요구 사항을 충족하는지 확인합니다. [](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

## <a name="why-should-you-prepare-your-network"></a>네트워크를 준비해야 하는 이유는 무엇입니까?

수행될 단계를 살펴보기 전에 사용자 만족도와 만족도에 영향을 줄 수 있는 Teams 이해하는 것이 중요합니다.
세 가지 주요 위험 영역은 사용자가 네트워크 품질을 인식하는 방식에 영향을 줄 수 있습니다.

-   사용 가능한 대역폭 부족

-   방화벽 및 프록시 차단기

-   지터 및 패킷 손실과 같은 네트워크 장애

아래 설명된 단계는 배포가 이러한 요소의 영향을 받을 수 있는지 여부를 결정하는 데 도움이 며 해결을 진행하는 데 도움이 됩니다.
네트워크를 준비하지 못하면 사용자가 불만을 하게 됐고 비용이 많이 드는 추가 수정이 발생할 수 있습니다. 네트워크 및 조직을 준비하여 Teams 성공 확률을 크게 늘려야 합니다.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>대역폭 계획

네트워크 준비를 위한 첫 번째 단계는 네트워크에 사용자에게 제공할 모달에 사용할 수 있는 충분한 대역폭을 Teams 것입니다. 충분한 대역폭을 계획하는 것은 매우 간단한 작업과 매우 낮은 장벽 시작으로 사용자에게 고품질의 환경을 Teams 합니다.

### <a name="local-internet-egress"></a>로컬 인터넷을 Egress

많은 네트워크는 허브 및 스포크 토폴로지 사용을 위해 디자인됩니다. 이 토폴로지에서 인터넷 트래픽은 일반적으로 WAN을 중앙 데이터 센터로 트래버스하여 인터넷으로(egresses)가 나타났습니다. 일반적으로 이는 전체 비용을 절감하기 위해 네트워크 보안 디바이스를 중앙 집중화하기 위해 수행됩니다.

WAN 전체에서 백-링 트래픽은 대기 시간을 증가하고 품질 및 사용자 환경에 부정적인 영향을 미치게 됩니다. Microsoft Microsoft Teams 글로벌 네트워크에서 실행하기 때문에 사용자와 가까운 네트워크 피어링 위치가 종종 있습니다. 사용자는 가능한 한 빨리 해당 위치에 가까운 로컬 인터넷 지점을 에그리제이트의 음성 최적화 네트워크로 이동하여 더 나은 성능을 얻을 수 있습니다. 일부 워크로드의 경우 DNS 요청은 가장 가까운 프런트 엔드 서버에 트래픽을 보내는 데 사용됩니다. 이러한 경우 로컬 시작 지점을 사용할 때 로컬 DNS 확인과 페어링됩니다.

Microsoft의 글로벌 네트워크에 대한 네트워크 경로를 최적화하면 성능이 향상되고 궁극적으로 사용자에게 최상의 환경을 제공할 수 있습니다. 자세한 내용은 에서 최상의 연결 및 성능 보기 블로그 [게시물을 Office 365.](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)

### <a name="vpn"></a>VPN

VPN은 많은 조직에 유용한 서비스를 제공합니다. 안타깝게도 일반적으로 실시간 미디어를 지원하도록 설계되거나 구성되지 않습니다. 일부 VPN은 UDP를 지원하지 않을 수도 있습니다. 또한 VPN은 이미 암호화되어 있는 미디어 트래픽 위에 추가 암호화 계층을 도입합니다. 또한 VPN Teams 트래픽을 고정하기 때문에 네트워크 서비스에 대한 연결이 효율적이지 않을 수 있습니다.
또한 필요한 예상 부하를 수용하기 위해 용량 관점에서 반드시 Teams 없습니다.

권장되는 것은 트래픽에 대한 VPN을 우회하는 대체 경로를 Teams 것입니다. 일반적으로 분할 터널 *VPN으로 알려져 있습니다.* 분할 터널링은 Microsoft 365 또는 Office 365 트래픽이 VPN을 트래버스하지 않고 직접 Microsoft 365 또는 Office 365. 이 변경은 품질에 긍정적인 영향을 주지만 VPN 디바이스 및 조직의 네트워크에서 부하를 줄이는 보조 이점도 제공합니다.

분할 터널을 구현하려면 구성 세부 정보를 VPN 공급업체에 문의하세요.

### <a name="wi-fi"></a>Wi-Fi

VPN과 Wi-Fi 네트워크는 반드시 실시간 미디어를 지원하도록 설계되거나 구성되지는 않습니다. 네트워크를 지원하기 위한 Wi-Fi 또는 최적화하는 것은 Teams 배포에 대한 중요한 고려 사항입니다.

네트워크 최적화를 위해 몇 가지 요소가 Wi-Fi 있습니다.

-   미디어 트래픽이 네트워크에서 Wi-Fi 우선 순위가 지정되도록 QoS 또는 WMM(멀티미디어)Wi-Fi 구현합니다.

-   대역 및 액세스 Wi-Fi 계획하고 최적화합니다. 2.4GHz 범위는 액세스 지점 배치에 따라 적절한 환경을 제공할 수 있지만 액세스 지점은 해당 범위에서 작동하는 다른 소비자 디바이스의 영향을 받는 경우가 종종 있습니다. 5GHz 범위는 밀도가 높기 때문에 실시간 미디어에 더 적합하지만 충분한 범위를 확보하려면 더 많은 액세스 지점이 필요합니다. 또한 엔드포인트는 해당 범위를 지원하고 그에 따라 해당 대역을 활용하도록 구성해야 합니다.

-   듀얼 밴드 Wi-Fi 네트워크가 배포되는 경우 밴드 스티어링을 구현하는 것이 고려됩니다. 밴드 스티어링은 5GHz 범위를 Wi-Fi 듀얼 밴드 클라이언트에 영향을 미치기 위해 공급업체가 구현한 기술입니다.

-   동일한 채널의 액세스 지점이 너무 가까이 있는 경우 신호가 겹치고 의도치 않은 경쟁이 발생할 수 있으며, 이로 인해 사용자에게 나쁜 환경이 발생할 수 있습니다. 옆에 있는 액세스 포인트가 서로 겹치지 않는 채널에 있는지 확인합니다.

각 무선 공급업체에는 무선 솔루션을 배포하는 것에 대한 권장 사항이 있습니다. 특정 지침은 공급업체에 문의하는 것이 좋습니다.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>방화벽 및 프록시 요구 사항

Microsoft Teams 연결하고 Microsoft Online Services 인터넷 연결이 필요합니다. Teams 제대로 작동하려면 클라이언트에서 인터넷으로 TCP 포트 80 및 443을 열고 클라이언트에서 인터넷으로 UDP 포트 3478~3481을 열어야 합니다. TCP 포트는 온라인, SharePoint, Exchange Online 채팅 서비스와 같은 웹 기반 콘텐츠에 Teams 사용됩니다.
플러그 인 및 커넥터도 이러한 TCP 포트를 통해 연결합니다. 4개의 UDP 포트는 오디오 및 비디오와 같은 미디어에 사용되어 올바르게 흐르는지 확인합니다.

이러한 포트를 여는 것은 안정적인 배포를 위해 Teams 중요합니다. 이러한 포트를 차단하는 것은 비지원적이기 때문에 미디어 품질에 영향을 미치게 됩니다.

조직에서 이러한 포트를 열 수 있는 정확한 IP 주소 범위 및 도메인을 지정해야 하는 경우 이러한 포트에 대한 대상 IP 범위 및 도메인을 제한할 수 있습니다. 정확한 포트, 프로토콜 및 IP 범위 목록은 URL 및 IP Microsoft 365 Office 365 [참조하세요.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)
대상 IP 주소 범위 및 도메인을 제한하도록 선택하는 경우 포트 및 범위 목록을 변경될 수 있기 때문에 최신으로 유지해야 합니다. 변경 사항이 발생할 때 업데이트할 [이 RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) 피드를 구독할 수 있습니다. 또한 네트워크 평가 도구를 정기적으로 실행하여 모든 포트를 비즈니스용 Skype 테스트하는 [것이](https://www.microsoft.com/download/details.aspx?id=53885) 좋습니다. 이 도구의 기능에 대한 자세한 내용은 다음 섹션에서 찾을 수 있습니다.

프록시 서버가 배포되는 경우 모든 서비스에서 프록시 서버를 Teams 것이 좋습니다. 프록시를 사용하는 것이 작동할 수 있습니다. UDP 대신 TCP를 강제로 사용하는 미디어로 인해 품질이 감소할 가능성이 매우 높습니다. 프록시 서버 및 우회에 대한 자세한 내용은 URL Microsoft 365 또는 Office 365 URL 및 IP 주소 범위를 [참조하세요.](./office-365-urls-ip-address-ranges.md)

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>네트워크 테스트

대역폭 업그레이드 및 방화벽에서 포트 열기 등 계획 및 네트워크 준비를 완료한 후 네트워크 성능을 테스트해야 합니다. 이 테스트의 결과는 통화 계획 구현을 통해 오디오 회의 또는 오디오 회의의 성공에 필요한 네트워크 최적화 또는 전화 시스템 더 명확한 그림을 그릴 것입니다.

네트워크 평가 [](https://www.microsoft.com/download/details.aspx?id=53885) 도구를 비즈니스용 Skype 네트워크가 준비되어 있는지 여부를 테스트할 수 Teams. 이 도구는 두 가지 기능을 제공합니다. 올바른 포트가 모두 열렸다는 여부를 테스트할 수 있으며 네트워크 손상을 테스트할 수 있습니다.

도구를 다운로드하고 설치한 후 C: 프로그램 파일 Microsoft 네트워크 평가 도구에서 비즈니스용 Skype \\ \\ 있습니다. 도구를 사용하는 방법에 대한 자세한 Usage.docx 디렉터리에 포함되어 있습니다.

### <a name="test-for-opened-ports"></a>열어진 포트에 대한 테스트

명령 프롬프트 창을 열고 cd C: 프로그램 파일 Microsoft 비즈니스용 Skype 네트워크 평가 도구 를 입력하여 **\\ 네트워크 평가 도구 \\ 디렉터리로 이동합니다.** 명령 프롬프트에서 **/connectivitycheck을** 입력하여networkassessmenttool.exe 시작

검사를 실행한 후 도구는 "확인이 성공적으로 완료되었습니다"라는 메시지를 표시하거나 차단된 포트에 대한 보고를 표시합니다.
또한 도구의 출력을 포함하는 Connectivity_results.txt 파일을 생성하고 비즈니스 네트워크 평가 도구 디렉터리의 %userprofile% appdata 로컬 microsoft skype 디렉터리에 \\ \\ \\ \\ 저장합니다.

포트가 열리고 올바르게 작동하고 있는지 확인하려면 정기적으로 연결 검사를 실행하는 것이 좋습니다.

### <a name="test-for-network-impairments"></a>네트워크 장애 테스트

사용자 만족도를 높이기 위해 네트워크의 장애를 제한해야 합니다.
가장 일반적인 네트워크 장애는 지연(대기 시간), 패킷 손실 및 지터입니다.

-   **대기 시간:** 네트워크에서 A 지점에서 B를 지점으로 IP 패킷을 수신하는 데 걸리는 시간입니다. 이 네트워크 전파 지연은 기본적으로 두 지점 사이의 물리적 거리와 그 사이에 있는 다양한 라우터에서 취한 추가 오버헤드를 포함하여 빛의 속도와 연결됩니다.
    대기 시간은 단면 또는 왕복 시간으로 측정됩니다.

-   **패킷 손실**: 종종 특정 기간에 손실되는 패킷의 백분율로 정의됩니다. 패킷 손실은 오디오를 완전히 차단하는 백-백 버스트 손실에 거의 영향을 주지 않고 작고 개별 손실된 패킷에서 오디오 품질에 직접적으로 영향을 미치게 됩니다.

-   **패킷 간 도착 지터 또는 간단히 지터:** 연속 패킷 간의 평균 지연 변경입니다. 대부분의 최신 VoIP 소프트웨어는 비즈니스용 Skype 통해 일부 수준의 지터에 적응할 수 있습니다. 지터가 버퍼링을 초과하는 경우만 참가자가 지터의 효과를 알 수 있습니다.

이러한 장애에 대한 최대 값은 미디어 품질 및 네트워크 [연결 성능에 설명되어 있습니다.](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)
이러한 장애를 테스트할 때 다음 두 세그먼트를 구분합니다.

-   *에지 세그먼트는* 라우터가 있는 세그먼트입니다. 각 위치에서 인터넷에 연결된 가장 가까운 논리 네트워크 세그먼트입니다. 대부분의 경우 라우터의 연결 지점 또는 경계 네트워크(DMZ, 비무장 영역 및 스크린된 *서브넷)입니다.*  라우터가 다른 디바이스에 영향을 주는 추가 트래픽은 이 세그먼트와 인터넷 간에 발생하지 않습니다.

-   클라이언트 *세그먼트는* 클라이언트가 있는 논리적 네트워크 세그먼트입니다.

네트워크 평가 도구를 사용하여 두 세그먼트를 테스트해야 합니다. 세그먼트를 테스트하기 위해 디렉터리로  이동하고 명령 프롬프트에networkassessmenttool.exe입력합니다. 결과는 Results.tsv라는 파일에 기록됩니다. 각 세그먼트의 요구 [](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 사항과 비교할 수 있습니다.

두 세그먼트 모두 고품질 배포에 대한 요구 사항을 충족해야 합니다. 네트워크의 성능을 잘 표시하려면 1시간 동안 여러 번 실행하는 것이 좋습니다.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>네트워크 수정

대역폭 계획, 포트 테스트 또는 네트워크 요구 사항 테스트의 결과가 현재 네트워크에서 배포하기 전에 수정이 Teams 경우 다음 여러 가지 방법으로 이 작업을 수행할 수 있습니다.

-   대역폭이 부족하면 트래픽이 방해를 Microsoft 365 Office 365 연결을 업그레이드합니다.

-   차단된 포트의 경우 방화벽 규칙을 변경하고 포트를 다시 시도합니다.

-   네트워크 장애의 경우 항상 근본 원인 분석을 수행합니다.

QoS(서비스 품질)는 트래픽의 우선 순위를 지정하고 구분하여 장애를 전투하는 데 사용할 수 있습니다. 일부 조직에서는 대역폭 문제를 극복하거나 트래픽 흐름의 양을 제한하기 위해 QoS를 배포하기로 합니다. 이렇게 하면 품질이 향상되지 못하고 새로운 문제가 발생할 수 있습니다. 네트워크 손상이 요구 사항을 초과하는 경우 근본 원인 분석을 항상 수행해야 합니다. QoS는 솔루션일 수 있습니다.
자세한 내용은 에서 서비스 [품질을 Microsoft Teams.](./qos-in-teams.md)

>[!NOTE]
>업그레이드, 확장 또는 기타 비즈니스 요구 사항으로 인해 시간이 지날 때 많은 네트워크가 진화합니다. 서비스 관리 계획의 일부로 이러한 영역을 유지 관리하기 위한 운영 프로세스가 준비되도록 합니다.


<table>
<tr><td>제목</td><td>설명</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>Who 모든 네트워크 세그먼트 및 조직 위치에서 적절한 네트워크 평가를 완료할 책임이 있나요?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>네트워크가 배포할 준비가 되도록 자세한 네트워크 평가를 Microsoft Teams 있습니다.</li><li>모든 네트워크 세그먼트에 대한 평가 결과에 따라 네트워크 수정을 수행합니다.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->