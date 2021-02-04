---
title: Teams에 대한 조직의 네트워크 준비
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 네트워크 요구 사항, 네트워크 최적화 및 대역폭 요구 사항을 포함하여 Microsoft Teams에 대한 조직의 네트워크를 준비하는 방법을 배워야 합니다.
localization_priority: Normal
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
ms.openlocfilehash: 9212c096323eb57754e0a8a47b61649bec42de87
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099579"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft Teams에 대한 조직의 네트워크 준비 

## <a name="network-requirements"></a>네트워크 요구 사항

[Microsoft 365 또는 Office 365에](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)대한 네트워크를 이미 최적화한 경우 Microsoft Teams를 사용할 준비가 된 것입니다. 어떤 경우에든, 특히 원격 작업자를 지원하기 위해 첫 번째 Microsoft 365 또는 Office  365 워크로드로 Teams를 신속하게 롤아웃하는 경우 Teams 롤아웃을 시작하기 전에 다음을 확인하십시오.

1.  모든 위치에서 인터넷에 액세스할 수 있나요(Microsoft 365 또는 Office 365에 연결할 수 있나요) 최소한 일반 웹 트래픽 외에도 Teams의 모든 위치에 대해 다음을 열고 있는지를 확인하세요.

    |  |  |
    |---------|---------|
    |포트     |UDP 포트 <strong>3478~3481</strong> <strong></strong>        |
    |[IP 주소](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18,</strong> <strong>52.112.0.0/14</strong>및 <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > 비즈니스용 Skype(온라인)와 페더러티해야 하는 경우 몇 가지 추가 DNS 레코드를 구성해야 합니다.
    >
    >|CNAME 레코드/호스트 이름  |TTL  |주소 또는 값에 대한 포인트  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  Microsoft 365 또는 Office 365에 대한 확인된 도메인이 있나요(예: contoso.com)
    
    - 조직에서 Microsoft 365 또는 Office 365를 롤아웃하지 않은 경우 [시작을 참조합니다.](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)
    - 조직에서 Microsoft 365 또는 Office 365에 대해 확인된 도메인을 추가하거나 구성하지 않은 경우 도메인 [FAQ를 참조합니다.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)

3.  조직에서 Exchange Online 및 SharePoint Online을 배포한 경우
    
    - 조직에 Exchange Online이 없는 경우 Exchange 및 Microsoft Teams가 상호 작용하는 방법 [이해를 참조하세요.](exchange-teams-interact.md)
    - 조직에 SharePoint Online이 없는 경우 SharePoint Online 및 [비즈니스용 OneDrive가 Microsoft Teams와](sharepoint-onedrive-interact.md)상호 작용하는 방식 이해를 참조하세요.

이러한 네트워크 요구 사항을 충족하는지 확인한 후 Teams를 롤아웃할 [준비가 된 것일 수 있습니다.](How-to-roll-out-teams.md) 다국적 기업인 경우 또는 네트워크 제한 사항이 있는 경우 Teams에 대한 네트워크를 평가하고 최적화하는 방법을 알아보세요.

> [!IMPORTANT]
> **교육 기관의 경우:** 조직이 교육 기관인 경우 SIS(학생 정보 시스템)를 사용하는 경우 Teams를 배포하기 전에 [School Data Sync를](https://docs.microsoft.com/schooldatasync/) 배포합니다.
>  
> **온-프레미스 비즈니스용 Skype 서버** 실행: 조직에서 온-프레미스 비즈니스용 Skype Server(또는 Lync Server)를 실행하는 경우 온-프레미스 디렉터리를 Microsoft 365 또는 Office 365와 동기화하도록 Azure AD [Connect를](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) 구성해야 합니다.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>모범 사례: CQD를 사용하여 네트워크 모니터링 및 통화 분석 

[CQD(통화](turning-on-and-using-call-quality-dashboard.md) 품질 대시보드)를 사용하여 Teams에서 통화 및 모임의 품질에 대한 정보를 얻을 수 있습니다. CQD는 품질, 안정성 및 사용자 환경을 세밀하게 확인하여 네트워크를 최적화하는 데 도움이 될 수 있습니다. CQD는 전체 패턴이 분명해질 수 있는 전체 조직에 대한 집계 원격 분석 데이터를 확인하여 문제를 식별하고 수정을 계획할 수 있습니다. 또한 CQD는 전체 품질, 안정성 및 사용자 경험에 대한 인사이트를 제공하는 풍부한 메트릭 보고서를 제공합니다. 

통화 분석을 [사용하여](set-up-call-analytics.md) 개별 사용자의 통화 및 모임 문제를 조사합니다.

## <a name="network-optimization"></a>네트워크 최적화

다음 작업은 선택 사항이며 Teams를 롤아웃할 필요는 없습니다. 특히 중소기업에 이미 Microsoft 365 또는 Office 365를 배포한 경우입니다. 네트워크 및 Teams 성능을 최적화하거나 네트워크 제한 사항이 있는 경우 이 지침을 사용하세요.

다음 경우 추가 네트워크 최적화를 수행할 수 있습니다.

  - Teams가 느리게 실행됩니다(대역폭이 부족할 수 있습니다).
  - 호출이 계속 삭제됩니다(방화벽 또는 프록시 차단 때문일 수 있습니다).
  - 호출에는 정적 및 잘라내거나 로봇과 같은 음성이 들리며(지터 또는 패킷 손실일 수 있습니다)

네트워크 장애 식별 및 수정 지침을 포함하여 네트워크 최적화에 대한 자세한 논의는 [Microsoft 365 및 Office 365](https://aka.ms/pnc)네트워크 연결 원칙을 읽어보아야 합니다.

<table>
<thead>
<tr class="header">
<th><strong>네트워크 최적화 작업</strong></th>
<th><strong>세부 정보</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Network Planner</td>
<td><p>대역폭 계산 및 네트워크 요구 사항을 포함하여 네트워크를 평가하는 데 도움이 필요한 경우 Teams 관리 센터에서 <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> 도구를 <a href="https://admin.teams.microsoft.com">확인합니다.</a> 네트워크 세부 정보 및 Teams 사용량을 제공하면 Network Planner는 조직의 실제 위치에 Teams 및 클라우드 음성을 배포하기 위한 네트워크 요구 사항을 계산합니다.</p>
<p>예제 시나리오는 Network Planner 사용 <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">- 예제 시나리오를 참조합니다.</a></p></td>
</tr>
<tr class="even">
<td>Teams용 Advisor</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Teams 관리자는</a> Teams 관리 <a href="https://admin.teams.microsoft.com">센터의 일부입니다.</a> Advisor for Teams(미리 보기)는 Microsoft 365 또는 Office 365 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다.</td>
</tr>
<tr class="odd">
<td>외부 이름 확인</td>
<td>Teams 클라이언트를 실행하는 모든 컴퓨터에서 외부 DNS 쿼리를 확인하여 Microsoft 365 또는 Office 365에서 제공하는 서비스를 검색할 수 있으며 방화벽이 액세스를 차단하지 않도록 합니다. 방화벽 포트 구성에 대한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 및 Office 365 URL 및 IP 범위로 이동하세요.</a></td>
</tr>
<tr class="odd">
<td>세션 지속성 유지 관리</td>
<td>방화벽이 UDP에 대해 매핑된 NAT(Network Address Translation) 주소 또는 포트를 변경하지 않는지 확인합니다.</td>
</tr><tr class="odd">
<td>NAT 풀 크기 유효성 검사</td>
<td>사용자 연결에 필요한 NAT(네트워크 주소 변환) 풀 크기의 유효성을 검사합니다. 여러 사용자와 장치가 <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">NAT(Network Address Translation) 또는 PAT(포트</a>주소 변환)를 사용하여 Microsoft 365 또는 Office 365에 액세스하는 경우 공개적으로 라우팅 가능한 각 IP 주소 뒤에 숨겨진 디바이스가 지원되는 번호를 초과하지 않도록 해야 합니다. 포트 고갈을 방지하기 위해 적절한 공용 IP 주소를 NAT 풀에 할당해야 합니다. 포트 소모는 Microsoft 365 또는 Office 365 서비스에 연결할 수 없는 내부 사용자 및 장치에 영향을 미치게 됩니다.</td>
</tr>
<tr class="even">
<td>Microsoft 데이터 센터로 라우팅</td>
<td>Microsoft 데이터 센터에 대한 가장 효율적인 <a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">라우팅을 구현합니다.</a> 가능한 한 효율적으로 Microsoft 네트워크에 연결하기 위해 로컬 또는 지역별 지점을 사용할 수 있는 위치를 식별합니다.</td>
</tr>
<tr class="odd">
<td>침입 감지 및 방지 지침</td>
<td>아웃바운드 <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a> 연결에 대한 추가 보안 계층을 위해 배포된 침입 탐지 또는 방지 시스템(IDS/IPS)이 환경에 있는 경우 모든 Microsoft 365 또는 Office 365 URL을 허용해야 합니다.</td>
</tr>
<tr class="even">
<td>분할 터널 VPN 구성</td>
<td><p>일반적으로 분할 터널 VPN으로 알려진 VPN(가상 사설망)을 우회하는 Teams 트래픽에 대한 대체 경로를 제공하는 <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">것이 좋습니다.</a> 분할 터널링은 Microsoft 365 또는 Office 365에 대한 트래픽이 VPN을 통과하지 않고 대신 Microsoft 365 또는 Office 365로 직접 이동하는 것입니다. VPN을 무시하면 Teams 품질에 긍정적인 영향을 미치고 VPN 디바이스 및 조직의 네트워크에서 부하를 줄입니다. 분할 터널 VPN을 구현하기 위해 VPN 공급업체에 문의하세요.</p>
<p>VPN을 무시하는 것이 좋습니다.
<ul>
<li><p>VPN은 일반적으로 실시간 미디어를 지원하도록 설계되거나 구성되지 않습니다.</p></li> 
<li><p>일부 VPN은 UDP를 지원하지 않을 수도 있습니다(Teams에 필요).</p></li> 
<li><p>VPN은 이미 암호화된 미디어 트래픽 위에 추가 암호화 계층을 도입합니다.</p></li> 
<li><p>VPN 디바이스를 통한 트래픽 고정으로 인해 Teams에 대한 연결이 효율적이지 않을 수 있습니다.</p></li></td>
</tr>
<tr class="odd">
<td>QoS 구현</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">QoS(서비스</a> 품질)를 사용하여 패킷 우선 순위를 구성합니다. 이렇게 하면 Teams에서 통화 품질을 개선하고 통화 품질을 모니터링하고 문제를 해결하는 데 도움이 될 수 있습니다. QoS는 관리되는 네트워크의 모든 세그먼트에서 구현해야 합니다. 네트워크가 대역폭에 대해 적절하게 프로비전된 경우에도 QoS는 예상치 않은 네트워크 이벤트 발생 시 위험 완화를 제공합니다. QoS에서는 이러한 예상치 않은 이벤트가 품질에 부정적인 영향을 주지 않는 음성 트래픽의 우선 순위가 지정됩니다.</td>
</tr>
<tr class="even">
<td>WiFi 최적화</td>
<td><p>VPN과 마찬가지로 WiFi 네트워크는 반드시 실시간 미디어를 지원하도록 설계되거나 구성되지는 않습니다. Teams를 지원하기 위한 WiFi 네트워크 계획 또는 최적화는 고품질 배포에 대한 중요한 고려 사항입니다. 다음과 같은 요소를 고려합니다.</p>
<ul>
<li><p>QoS 또는 WMM(WiFi 멀티미디어)을 구현하여 미디어 트래픽이 WiFi 네트워크를 통해 적절하게 우선 순위를 지정하도록 합니다.</p></li>
<li><p>WiFi 밴드 및 액세스 지점 배치를 계획하고 최적화합니다. 2.4GHz 범위는 액세스 지점 배치에 따라 적절한 환경을 제공할 수 있지만 액세스 지점은 해당 범위에서 작동하는 다른 소비자 디바이스의 영향을 받는 경우가 종종 있습니다. 5GHz 범위는 조밀한 범위로 인해 실시간 미디어에 더 적합하지만 충분한 커버리지를 얻기 위해 더 많은 액세스 지점이 필요합니다. 또한 엔드포인트는 해당 범위를 지원하고 해당 대역을 그에 따라 활용하도록 구성해야 합니다.</p></li>
<li><p>이중 밴드 WiFi 네트워크를 사용하는 경우 밴드 스티어링 구현을 고려합니다. <em>밴드</em> 스티어링은 WiFi 공급업체가 5GHz 범위를 사용하기 위해 이중 대역 클라이언트에 영향을 주기 위해 구현된 기술입니다.</p></li>
<li><p>동일한 채널의 액세스 지점이 너무 가까이에 있는 경우 신호가 겹치고 의도치 않은 경쟁이 발생하여 사용자에게 좋지 않은 환경이 발생할 수 있습니다. 서로 옆에 있는 액세스 지점이 겹치지 않는 채널에 있도록 합니다.</p></li>
</ul>
<p>각 무선 공급업체에는 무선 솔루션을 배포하기 위한 자체 권장 사항이 있습니다. 특정 지침은 WiFi 공급업체에 문의하세요.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>대역폭 요구 사항

Teams는 네트워크 조건에 관계없이 최상의 오디오, 비디오 및 콘텐츠 공유 환경을 제공하도록 디자인되었습니다. 즉, 대역폭이 부족하면 Teams는 비디오 품질보다 오디오 품질에 우선 순위를 지정합니다.

대역폭이  제한되지 않는 경우 Teams는 최대 1080p 비디오 해상도, 비디오에 대해 최대 30fps, 콘텐츠 및 고화질 오디오를 포함하여 미디어 품질을 최적화합니다. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>관련 항목

[Microsoft 365 및 Office 365 네트워크 연결 원칙](https://aka.ms/pnc)

[전 세계 끝점: 비즈니스용 Skype Online 및 Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Teams용 프록시 서버](proxy-servers-for-skype-for-business-online.md)

[Teams의 미디어: 모임이 간단한 이유](https://aka.ms/teams-media)

[Teams의 미디어: 미디어 흐름 심층 파고들기](https://aka.ms/teams-media-flows)

[Teams의 ID 모델 및 인증](identify-models-authentication.md)

[Teams를 배포하는 방법](How-to-roll-out-teams.md)

[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
