---
title: Teams에 대한 조직의 네트워크 준비
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 네트워크 요구 사항, 네트워크 최적화, 대역폭 요구 사항을 포함하여 Microsoft Teams를 사용하기 위해 조직의 네트워크를 준비하는 방법을 자세히 알아봅니다.
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 13bc12d5df1139bc76afa48751e7a7cb3c6197c0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621970"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft Teams를 사용하기 위한 조직의 네트워크 준비 

## <a name="network-requirements"></a>네트워크 요구 사항

[Microsoft 365 또는 Office 365에 대한 네트워크를 이미 최적화했다면](/Office365/Enterprise/assessing-network-connectivity) Microsoft Teams를 사용할 준비가 된 것입니다. 어떤 경우든, 특히 **원격 작업자** 를 지원하기 위해 첫 Microsoft 365 또는 Office 365 워크로드로서 Teams를 빠르게 배포하는 경우, Teams 배포를 시작하기 전에 다음을 확인하세요.

1.  모든 위치에서 인터넷에 액세스할 수 있나요(Microsoft 365 또는 Office 365에 연결할 수 있도록)? 일반적인 웹 트래픽 외에도 [Office 365 URL 및 IP 주소 범위](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)에 있는 Teams에 대해 나열된 TCP 포트와 IP 주소를 열었는지 확인하세요.

    > [!IMPORTANT]
    > 온-프레미스 또는 온라인에서 비즈니스용 Skype와 페더레이션해야 하는 경우 추가 DNS 레코드를 구성해야 합니다.
    >
    >|DNS 레코드  |서비스  |프로토콜  |우선 순위  |가중치  |포트  |대상  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|SRV     |sipfederationtls     |TCP     |100     |1     |5061     |sipfed.online.lync.com     |
    
2.  Microsoft 365 또는 Office 365에 대한 확인된 도메인이 있나요(예: contoso.com)?
    
    - 조직에서 Microsoft 365 또는 Office 365를 배포하지 않은 경우 [시작](/microsoft-365/admin/admin-overview/get-started-with-office-365)을 참조하세요.
    - 조직에서 Microsoft 365 또는 Office 365에 대해 확인된 도메인을 추가하거나 구성하지 않은 경우 [도메인 FAQ](/microsoft-365/admin/setup/domains-faq)를 참조하세요.

3.  조직에서 Exchange Online 및 SharePoint Online을 배포했나요?
    
    - 조직에 Exchange Online이 없는 경우 [Exchange와 Microsoft Teams의 상호 작용 방법](exchange-teams-interact.md)을 참조하세요. 
    - 조직에 SharePoint Online이 없는 경우 [SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)을 참조하세요.

이러한 네트워크 요구 사항을 충족하는지 확인했다면 [Teams를 배포](./deploy-overview.md)할 준비가 된 것입니다. 대규모 다국적 기업이거나 네트워크 제한 사항이 있음을 알고 있는 경우 Teams를 사용하기 위해 네트워크를 평가하고 최적화하는 방법을 알아보도록 계속 읽으세요.

> [!IMPORTANT]
> **교육 기관**: 조직이 교육 기관이고 SIS(학생 정보 시스템)를 사용하는 경우 Teams를 배포하기 전에 [학교 데이터 동기화를 배포](/schooldatasync/)합니다.
>  
> **온-프레미스 비즈니스용 Skype 서버 실행**: 조직에서 온-프레미스 비즈니스용 Skype 서버(또는 Lync Server)를 실행하는 경우 [Azure Active Directory Connect를 구성](/skypeforbusiness/hybrid/configure-azure-ad-connect)하여 온-프레미스 디렉터리를 Microsoft 365 또는 Office 365와 동기화해야 합니다.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>모범 사례: CQD 및 통화 분석을 사용하여 네트워크 모니터링 

[CQD(통화 품질 대시보드)](turning-on-and-using-call-quality-dashboard.md)를 사용하여 Teams의 통화 및 모임의 품질을 파악할 수 있습니다. CQD를 사용하면 품질, 안정성 및 사용자 환경을 세밀하게 확인하여 네트워크를 최적화하는 데 도움이 될 수 있습니다. CQD는 전체 패턴이 명백해질 수 있는 전체 조직에 대한 집계 원격 분석을 살펴보아 문제를 식별하고 수정을 계획하도록 합니다. 또한, CQD는 전체 품질, 안정성 및 사용자 환경을 파악할 수 있는 풍부한 메트릭 보고서를 제공합니다. 

[통화 분석](set-up-call-analytics.md)을 사용하여 개별 사용자의 통화 및 모임 문제를 조사합니다.

## <a name="network-optimization"></a>네트워크 최적화

다음 작업은 선택 사항이며 특히 중소기업이거나 Microsoft 365 또는 Office 365를 이미 배포한 경우 Teams를 배포하는 데 필요하지 않습니다. 네트워크 및 Teams 성능을 최적화하거나 네트워크 제한 사항이 있는 경우 이 지침을 사용하세요.

다음의 경우 추가 네트워크 최적화를 수행하는 것이 좋습니다.

  - Teams가 느리게 실행됩니다(대역폭이 부족할 수 있음).
  - 통화가 계속 끊깁니다(방화벽 또는 프록시 차단 때문일 수 있음).
  - 통화 중 잡음이 들리고 끊기거나 음성이 로봇처럼 들립니다(지터 또는 패킷 손실일 수 있음).

네트워크 장애를 식별하고 수정하기 위한 지침을 비롯한 네트워크 최적화에 대한 자세한 논의는 [Microsoft 365 및 Office 365 네트워크 연결 원칙](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)을 참조하세요.

<table>
<thead>
<tr class="header">
<th>네트워크 최적화 작업</th>
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>네트워크 플래너</td>
<td><p>조직의 물리적 위치에서 대역폭 계산 및 네트워크 요구 사항을 포함하여 네트워크를 평가하는 데 도움이 필요한 경우 <a href="https://admin.teams.microsoft.com">Teams 관리 센터</a>의 <a href="/microsoftteams/network-planner">네트워크 플래너</a> 도구를 확인하세요. 네트워크 세부 정보 및 Teams 사용을 제공하는 경우 네트워크 플래너는 조직에서 실제 위치에 Teams와 Cloud Voice를 배포하는데 필요한 네트워크 요구 사항을 계산합니다.</p>
<p>예제 시나리오는 <a href="/microsoftteams/tutorial-network-planner-example">네트워크 플래너 사용 - 예제 시나리오</a>를 참조하세요.</p></td>
</tr>
<tr class="even">
<td>Teams용 어드바이저</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">Teams용 어드바이저</a>는 <a href="https://admin.teams.microsoft.com">Teams 관리 센터</a>의 일부입니다. Advisor for Teams(미리 보기)는 Microsoft 365 또는 Office 365 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다.</td>
</tr>
<tr class="odd">
<td>외부 이름 확인</td>
<td>Teams 클라이언트를 실행하는 모든 컴퓨터가 외부 DNS 쿼리를 확인하여 Microsoft 365 또는 Office 365에서 제공하는 서비스를 검색할 수 있고 방화벽이 액세스를 차단하지 않는지 확인합니다. 방화벽 포트 구성에 대한 자세한 내용은 <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 및 Office 365 URL 및 IP 범위</a>로 이동하세요.</td>
</tr>
<tr class="odd">
<td>세션 지속성 유지</td>
<td>방화벽에서 UDP에 대해 매핑된 NAT(Network Address Translation) 주소 또는 포트를 변경하지 않는지 확인합니다.</td>
</tr><tr class="odd">
<td>NAT 풀 크기 확인</td>
<td>사용자 연결에 필요한 NAT(network address translation) 풀 크기를 확인합니다. 여러 사용자와 장치가 <a href="/office365/enterprise/nat-support-with-office-365">NAT(Network Address Translation) 또는 PAT(Port Address Translation)</a>를 사용하여 Microsoft 365 또는 Office 365에 액세스하는 경우, 공개적으로 라우팅할 수 있는 각 IP 주소 뒤에 숨어 있는 장치가 지원되는 수를 초과하지 않는지 확인해야 합니다. 포트 소진을 방지하도록 NAT 풀에 적절한 공용 IP 주소를 할당해야 합니다. 포트 소진은 내부 사용자와 장치가 Microsoft 365 또는 Office 365 서비스에 연결할 수 없게 합니다.</td>
</tr>
<tr class="even">
<td>Microsoft 데이터 센터로 라우팅</td>
<td><a href="/office365/enterprise/client-connectivity">가장 효율적인 Microsoft 데이터 센터로의 라우팅을 구현합니다</a>. 로컬 또는 국가별 송신 지점을 사용하여 최대한 효율적으로 Microsoft 네트워크에 연결할 수 있는 위치를 식별합니다.</td>
</tr>
<tr class="odd">
<td>침입 탐지 및 예방 지침</td>
<td>아웃바운드 연결에 대한 추가 보안 계층을 위해 배포된 <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">침입 탐지</a> 또는 예방 시스템(IDS/IPS)이 있는 경우 모든 Microsoft 365 또는 Office 365 URL을 허용해야 합니다.</td>
</tr>
<tr class="even">
<td>분할 터널 VPN 구성</td>
<td><p>일반적으로 <a href="/windows/security/identity-protection/vpn/vpn-routing">분할 터널 VPN</a>이라고 알려진 VPN(가상 사설망)을 우회하는 Teams 트래픽에 대한 대체 경로를 제공하는 것이 좋습니다. 분할 터널링은 Microsoft 365 또는 Office 365의 트래픽이 VPN을 통과하지 않고 대신 Microsoft 365 또는 Office 365로 직접 이동함을 의미합니다. VPN을 우회하면 Teams 품질에 긍정적인 영향을 미치며 VPN 장치와 조직의 네트워크의 부하가 줄어듭니다. 분할 터널 VPN을 구현하기 위해 VPN 공급업체와 협력하세요.</p>
<p>VPN 우회를 권장하는 다른 이유:
<ul>
<li><p>일반적으로 VPN은 실시간 미디어를 지원하도록 설계되거나 구성되지 않습니다.</p></li> 
<li><p>일부 VPN은 UDP를 지원하지 않을 수도 있습니다(Teams에 필요함).</p></li> 
<li><p>또한 VPN은 이미 암호화되어 있는 미디어 트래픽 위에 추가 암호화 계층을 도입합니다.</p></li> 
<li><p>VPN 장치를 통한 헤어핀 트래픽으로 인해 Teams에 대한 연결이 효율적이지 않을 수 있습니다.</p></li></td>
</tr>
<tr class="odd">
<td>QoS 구현</td>
<td><a href="/microsoftteams/qos-in-teams">QoS(서비스 품질)를 사용하여</a> 패킷 우선순위를 구성합니다. 이렇게 하면 Teams의 통화 품질이 향상될 수 있으며 통화 품질을 모니터링하고 문제를 해결하는 데 도움이 될 수 있습니다. QoS는 관리 네트워크의 모든 세그먼트에 구현해야 합니다. 네트워크가 대역폭에 적절하게 프로비전된 경우에도 QoS에서는 예상하지 않은 네트워크 이벤트가 발생하면 위험을 완화합니다. QoS를 사용하여 이러한 예상치 않은 이벤트가 품질에 부정적인 영향을 주지 있도록 음성 트래픽이 우선시됩니다.</td>
</tr>
<tr class="even">
<td>WiFi 최적화</td>
<td><p>VPN과 마찬가지로 WiFi 네트워크는 실시간 미디어를 지원하도록 설계되거나 구성되지 않을 수 있습니다. Teams를 지원하기 위해 WiFi 네트워크를 계획하거나 최적화하는 것은 고품질 배포를 하기 위한 중요한 고려 사항입니다. 다음 요인들을 고려합니다.</p>
<ul>
<li><p>QoS 또는 WMM(WiFi 멀티미디어)를 구현하여 미디어 트래픽이 WiFi 네트워크보다 적절하게 우선되도록 합니다.</p></li>
<li><p>WiFi 대역과 액세스 지점 배치를 계획하고 최적화합니다. 2.4GHz 범위는 액세스 지점 배치에 따라 적절한 환경을 제공할 수 있지만 액세스 지점은 종종 해당 범위에서 작동하는 다른 소비자 장치의 영향을 받습니다. 5GHz 범위는 조밀한 범위 때문에 실시간 미디어에 더 적합하지만, 충분한 범위를 확보하려면 액세스 지점이 더 필요합니다. 또한 엔드포인트는 해당 범위를 지원하고 그에 따라 해당 대역을 활용하도록 구성해야 합니다.</p></li>
<li><p>이중 대역 WiFi 네트워크를 사용 중이면 대역 조정을 구현하는 것을 고려하세요. <em>대역 조정</em>은 5GHz 범위를 사용하도록 이중 대역 클라이언트에 영향을 미치기 위해 WiFi 공급업체에서 구현한 기술입니다.</p></li>
<li><p>같은 채널의 액세스 지점이 너무 가깝게 있는 경우 신호가 겹치거나 의도치 않게 경합하여 사용자에게 좋지 않은 환경이 발생할 수 있습니다. 옆에 있는 액세스 포인트가 서로 겹치지 않는 채널에 있는지 확인합니다.</p></li>
</ul>
<p>각 무선 공급업체에는 무선 솔루션을 배포하는 것에 대한 권장 사항이 있습니다. 자세한 지침은 Wi-Fi 공급업체에 문의하세요.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>대역폭 요구 사항

Teams는 네트워크 조건과 상관없이 최상의 오디오, 비디오, 콘텐츠 공유 환경을 제공하도록 설계되었습니다. 즉, 대역폭이 부족하면 Teams에서는 비디오 품질보다 오디오 품질을 우선합니다.

대역폭이 제한되지 않는 경우, Teams에서는 고해상도 오디오, 최대 1080p 비디오 해상도, 최대 30fps(초당 프레임 수)의 비디오 및 컨텐츠를 포함한 미디어 품질을 최적화합니다.

이 표는 Teams에서 대역폭을 사용하는 방법에 대해 설명합니다. Teams는 항상 대역폭 사용에 대해 보수적이며 1.5Mbps 미만에서 HD 비디오 품질을 제공할 수 있습니다. 각 오디오/비디오 통화 또는 모임에서 실제 대역폭 소비량은 비디오 레이아웃, 비디오 해상도, 비디오 프레임 등 여러 요인에 따라 달라집니다. 더 많은 대역폭을 사용할 수 있게 되면 최상의 환경을 제공하기 위해 품질이 향상되고 사용량이 늘어납니다.

:::row:::
   :::column span="":::
      **형식**
   :::column-end:::
   :::column span="3":::
      **대역폭 요구 사항(비트 전송률 KB/ 업/다운)**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      **최소**
   :::column-end:::
   :::column span="":::
      **권장**
   :::column-end:::
   :::column span="":::
      **최고의 성능**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **오디오**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        일대일
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        모임
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **비디오**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        일대일
   :::column-end:::
   :::column span="":::
        150/150
   :::column-end:::
   :::column span="":::
        1,500/1,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        모임
   :::column-end:::
   :::column span="":::
        150/200
   :::column-end:::
   :::column span="":::
        2,500/4,000
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **화면 공유.**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        일대일
   :::column-end:::
   :::column span="":::
        200/200
   :::column-end:::
   :::column span="":::
        1,500/1,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        모임
   :::column-end:::
   :::column span="":::
        250/250
   :::column-end:::
   :::column span="":::
        2,500/2,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **함께 모드**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        일대일
   :::column-end:::
   :::column span="":::
        해당 없음
   :::column-end:::
   :::column span="":::
        해당 없음
   :::column-end:::
   :::column span="":::
        해당 없음
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        모임
   :::column-end:::
   :::column span="":::
        1,000/1,500
   :::column-end:::
   :::column span="":::
        1,500/2,500
   :::column-end:::
   :::column span="":::
        2,500/4,000
   :::column-end:::
:::row-end:::

**최소**, **권장** 및 **최고의 성능** 대역폭 요구 사항은 엔드포인트별 사용량을 기준으로 합니다. 일반적으로 사용자당 하나의 엔드포인트가 있습니다(예: 컴퓨터 또는 모바일 장치). 그러나 사용자가 시스템 *과* 모바일 장치 *모두* 에서 Teams 모임에 참여하는 경우 두 개의 엔드포인트가 해당 사용자와 연결됩니다.

- 비디오 호출에 필요한 **최소** 대역폭 요구 사항은 최대 240p 해상도, 화면 공유 컨텐츠 프레임률이 적응형 1.875~7.5fps, 함께 모드/대형 갤러리 비디오 해상도가 최대 540p입니다.  

- 비디오 호출에 **권장되는** 대역폭 요구 사항은 최대 1080p 해상도 <sup>\*</sup>, 화면 공유 컨텐츠 프레임률 적응형 7.5~30fps 및 함께 모드/대형 갤러리 비디오 해상도 최대 1080p입니다.<sup>\*</sup>  

- **최고의 성능** 지침은 15~30fps의 화면 공유 콘텐츠 프레임률을 통해 대규모 참석자 모임, 고손실 환경 및 고 모션 콘텐츠를 보다 충실하게 저장할 수 있도록 지원합니다.

<sup>\*</sup>최대 1080p의 화질을 기대하지만 네트워크 상태에 따라 비디오 해상도와 화질이 최적화됩니다.  

## <a name="related-topics"></a>관련 항목

[Microsoft 365 및 Office 365 네트워크 연결 원칙](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[전 세계 엔드포인트: 비즈니스용 Skype Online 및 Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Teams용 프록시 서버](proxy-servers-for-skype-for-business-online.md)

[Teams의 미디어: 모임이 간단한 이유](https://aka.ms/teams-media)

[Teams의 미디어: 미디어 흐름에 대한 심층 분석](https://aka.ms/teams-media-flows)

[Teams의 ID 모델 및 인증](identify-models-authentication.md)

[Teams를 배포하는 방법](./deploy-overview.md)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
