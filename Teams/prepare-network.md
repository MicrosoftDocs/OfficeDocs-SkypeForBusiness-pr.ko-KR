---
title: Microsoft Teams에 대한 조직의 네트워크 준비
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Microsoft 팀을 롤아웃 하기 전에 네트워크를 평가 하 고 팀에 맞게 준비 되어 있는지 확인 합니다. 정보에는 네트워크 요구 사항, 대역폭 요구 사항, 네트워크 최적화 지침이 포함 됩니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd27dfd6fccba5c7e9db52d58f7a6253849bea54
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862908"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft Teams에 대한 조직의 네트워크 준비 

## <a name="network-requirements"></a>네트워크 요구 사항

[Office 365에 대 한 네트워크](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)를 이미 최적화 한 경우 Microsoft 팀에 대 한 준비가 되었을 수 있습니다. 경우에 따라 팀 롤아웃을 시작 하기 전에 다음을 확인 하세요.

1.  모든 위치에서 인터넷에 액세스할 수 있는지 확인 (Office 365에 연결 가능) 최소한 일반 웹 소통량 외에도 팀에서 미디어의 모든 위치에 대해 다음을 열었는지 확인 하세요.

    |  |  |
    |---------|---------|
    |139     |UDP 포트 <strong>3478</strong> ~ <strong>3481</strong>        |
    |[IP 주소](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong> 및 <strong>52.112.0.0/14</strong>        |
    
2.  Office 365에 대해 확인 된 도메인이 있습니까 (예: contoso.com)?
    
      - 조직에서 Office 365를 배포 하지 않은 경우 [비즈니스용 office 365 시작](https://docs.microsoft.com/office365/admin/admin-overview/get-started-with-office-365)을 참조 하세요.
      - 조직이 Office 365에 대해 확인 된 도메인을 추가 하거나 구성 하지 않은 경우 [office 365 도메인 확인](https://docs.microsoft.com/office365/admin/setup/domains-faq)을 참조 하세요.

3.  조직에서 Exchange Online 및 SharePoint Online을 배포 했습니까?
    
      - 조직에 Exchange Online이 없는 경우 [exchange 및 Microsoft 팀의 상호 작용 방법 이해](exchange-teams-interact.md)를 참조 하세요.
      - 조직에 SharePoint Online이 없는 경우 [Sharepoint online 및 비즈니스용 OneDrive For Business가 Microsoft 팀과 어떻게 상호 작용 하는지 이해](sharepoint-onedrive-interact.md)를 참조 하세요.

이러한 네트워크 요구 사항을 충족 하는 것으로 확인 되 면 [팀을 롤아웃할](How-to-roll-out-teams.md)준비가 되었을 수 있습니다. 다국적 대기업 이거나 몇 가지 네트워크 제한 사항이 있는 경우에는 팀을 위해 네트워크를 평가 하 고 최적화 하는 방법에 대해 알아보세요.

> [!IMPORTANT]
> **교육 기관**: 조직이 교육 기관 이거나 SIS (학생 정보 시스템)를 사용 하는 경우 팀을 롤아웃하기 전에 [School Data Sync를 배포](https://docs.microsoft.com/schooldatasync/) 해야 합니다.
>  
> 온 **-프레미스 비즈니스용 Skype server**: 조직이 온-프레미스 비즈니스용 skype server (또는 Lync Server)를 실행 하는 경우 [Azure AD Connect를 구성](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) 하 여 온-프레미스 디렉터리를 Office 365와 동기화 해야 합니다.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>모범 사례: CQD 및 call analytics을 사용 하 여 네트워크 모니터링 

[CQD (통화 품질 대시보드)](turning-on-and-using-call-quality-dashboard.md) 를 사용 하 여 팀에서 통화 및 모임 품질에 대 한 통찰력을 얻을 수 있습니다. CQD는 품질, 안정성 및 사용자 경험을 가까이 유지 하 여 네트워크를 최적화 하는 데 도움이 될 수 있습니다. CQD는 전체적인 패턴이 명확 하 게 표시 될 수 있는 전체 조직에 대 한 집계 원격 분석을 살펴보고 문제를 식별 하 고 업데이트를 계획 하는 방법을 보여 줍니다. 또한 CQD는 전반적인 품질, 안정성 및 사용자 환경에 대 한 통찰력을 제공 하는 풍부한 메트릭 보고서를 제공 합니다. 

[통화 분석](set-up-call-analytics.md) 을 사용 하 여 개별 사용자의 통화 및 모임 문제를 조사 합니다.

## <a name="network-optimization"></a>네트워크 최적화

다음 작업은 선택 사항이 며 팀 롤아웃에 필요 하지 않으며 특히, 소규모 기업과 이미 Office 365를 출시 한 경우 이 지침을 사용 하 여 네트워크 및 팀 성능을 최적화 하거나 네트워크 제한 사항이 있을 수 있습니다.

다음과 같은 경우 추가 네트워크 최적화를 수행할 수 있습니다.

  - 팀이 느리게 실행 됨 (대역폭이 부족할 수도 있음)
  - 통화 보관 (방화벽 또는 프록시 차단 때문일 수 있음)
  - 통화는 정적-y, 오려내기 또는 로봇이 같은 음성 사운드 (지터 또는 패킷 손실이 될 수 있음)입니다.

네트워크 장애를 식별 하 고 해결 하는 지침을 비롯 한 네트워크 최적화에 대 한 자세한 내용은 [Office 365 네트워크 연결 원칙](https://aka.ms/pnc)을 참조 하세요.

<table>
<thead>
<tr class="header">
<th><strong>네트워크 최적화 작업</strong></th>
<th><strong>세부적인</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>네트워크 planner</td>
<td><p>조직의 실제 위치에서 대역폭 계산과 네트워크 요구 사항을 비롯 한 네트워크를 평가 하는 데 도움이 필요한 경우 <a href="https://admin.teams.microsoft.com">팀 관리 센터</a>에서 <a href="https://docs.microsoft.com/microsoftteams/network-planner">네트워크 Planner</a> 도구를 확인 하세요. 네트워크 세부 정보 및 팀 사용량을 제공 하는 경우 네트워크 계획자는 조직의 실제 위치에서 팀 및 클라우드 음성을 배포 하기 위한 네트워크 요구 사항을 계산 합니다.</p>
<p>예제 시나리오는 <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">네트워크 Planner 사용-예제 시나리오</a>를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td>팀 관리자</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">팀</a> 관리자는 <a href="https://admin.teams.microsoft.com">팀 관리 센터</a>의 일부입니다. Advisor for Teams(미리 보기)는 Office 365 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다.</td>
</tr>
<tr class="odd">
<td>외부 이름 확인</td>
<td>팀 클라이언트를 실행 하는 모든 컴퓨터에서 외부 DNS 쿼리를 확인 하 여 Office 365에서 제공 하는 서비스를 검색 하 고 방화벽이 액세스를 차단 하지 않는지 확인 합니다. 방화벽 포트를 구성 하는 방법에 대 한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Office 365 url 및 IP 범위로</a>이동 하세요.</td>
</tr>
<tr class="odd">
<td>유효성 검사 (NAT) 풀 크기</td>
<td>사용자 연결에 필요한 NAT (network address translation) 풀 크기의 유효성을 검사 합니다. 여러 사용자와 장치가 <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">NAT (Network Address translation) 또는 PAT (Port Address translation)</a>를 사용 하 여 Office 365에 액세스 하는 경우, 공개적으로 라우팅할 수 있는 각 IP 주소 뒤에 숨겨진 장치가 지원 되는 번호를 초과 하지 않는지 확인 해야 합니다. 포트 소모를 방지 하기 위해 적절 한 공용 IP 주소가 NAT 풀에 할당 되었는지 확인 합니다. 포트 소모는 내부 사용자와 장치가 Office 365 서비스에 연결할 수 없는 경우에 기여 합니다.</td>
</tr>
<tr class="even">
<td>Microsoft 데이터 센터로 라우팅</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Microsoft 데이터 센터에 가장 효율적인 라우팅을 구현</a>합니다. 로컬 또는 지역 송신 지점을 사용 하 여 가능한 한 효율적으로 Microsoft 네트워크에 연결할 수 있는 위치를 식별 합니다.</td>
</tr>
<tr class="odd">
<td>침입 감지 및 예방 지침</td>
<td>아웃 바운드 연결에 대 한 추가 보안 계층에 대 한 <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">침입 감지</a> 또는 방지 시스템 (ID/i p)이 환경에 있는 경우 모든 Office 365 url을 허용 목록 해야 합니다.</td>
</tr>
<tr class="even">
<td>분할 터널 VPN 구성</td>
<td><p>일반적으로 [분할 터널 VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing)이라고 하는 vpn (가상 사설망)을 우회 하는 팀 트래픽에 대 한 대체 경로를 제공 하는 것이 좋습니다. 분할 터널링은 Office 365에 대 한 트래픽이 VPN을 거치지 않고 대신 Office 365에 직접 전달 한다는 의미입니다. VPN을 건너뛰면 팀 품질에 긍정적인 영향을 미칠 수 있으며, VPN 장치 및 조직의 네트워크에서의 로드를 줄여줍니다. 분할 터널 VPN을 구현 하려면 VPN 공급 업체와 협력 하세요.</p>
<p>VPN을 우회 하는 것이 권장 되는 다른 이유는 다음과 같습니다.
<ul>
<li><p>Vpn은 일반적으로 실시간 미디어를 지원 하도록 설계 또는 구성 되지 않았습니다.</p></li> 
<li><p>일부 Vpn은 UDP (팀에 필요 함)를 지원 하지 않을 수도 있습니다.</p></li> 
<li><p>Vpn은 이미 암호화 된 미디어 트래픽 위에 추가 암호화 계층을 도입 하기도 합니다.</p></li> 
<li><p>VPN 장치를 통해 헤어 고정 트래픽 때문에 팀에 대 한 연결이 효율적이 지 않을 수 있습니다.</p></li></td>
</tr>
<tr class="odd">
<td>QoS 구현</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">QoS (서비스 품질)를 사용</a> 하 여 패킷 우선 순위를 구성 합니다. 이렇게 하면 팀에서 통화 품질을 개선 하 고 통화 품질을 모니터링 하 고 문제를 해결 하는 데 도움이 됩니다. QoS는 관리 되는 네트워크의 모든 세그먼트에서 구현 해야 합니다. 네트워크가 대역폭에 적절 하 게 프로 비전 된 경우에도 QoS는 예기치 않은 네트워크 이벤트가 발생할 경우 위험 경감을 제공 합니다. QoS를 사용 하면 이러한 예기치 않은 이벤트가 품질에 부정적인 영향을 주지 않도록 음성 트래픽이 우선 순위가 지정 됩니다.</td>
</tr>
<tr class="even">
<td>WiFi 최적화</td>
<td><p>VPN과 유사 하 게, WiFi 네트워크는 실시간 미디어를 지원 하도록 설계 또는 구성 되어 있지 않을 수도 있습니다. 팀을 지원 하기 위해 WiFi 네트워크를 계획 하거나 최적화 하는 것은 고품질 배포를 위한 중요 한 고려 사항입니다. 다음과 같은 요인을 고려 합니다.</p>
<ul>
<li><p>WiFi 네트워크를 통해 미디어 트래픽이 적절 하 게 우선 순위를 유지 하도록 QoS 또는 WMM (WiFi 멀티미디어)를 구현 합니다.</p></li>
<li><p>WiFi 밴드 및 액세스 지점의 위치를 계획 하 고 최적화 합니다. 2.4 GHz 범위는 액세스 지점 배치에 따라 적절 한 환경을 제공할 수 있지만 액세스 지점은 해당 범위에서 작동 하는 다른 소비자 장치에 영향을 받는 경우가 많습니다. 5ghz 범위는 조밀 범위 때문에 실시간 미디어에 더 적합 하지만, 충분 한 서비스를 얻으려면 더 많은 액세스 포인트가 필요 합니다. 또한 끝점은 해당 범위를 지원 하 고 그에 따라 이러한 대역을 활용 하도록 구성 해야 합니다.</p></li>
<li><p>이중 대역 WiFi 네트워크를 사용 하는 경우에는 밴드 조절을 구현 하는 것이 좋습니다. <em>밴드 조종</em> 은 듀얼 밴드 클라이언트에 게 5ghz 범위를 사용 하는 데 영향을 주는 WiFi 공급 업체에서 구현한 기술입니다.</p></li>
<li><p>같은 채널의 액세스 지점이 너무 가까이 있으면 신호가 겹치고 그에 따른 경합으로 인해 사용자에 게 좋지 않은 환경이 제공 될 수 있습니다. 서로 인접 한 연결점이 겹치지 않는 채널에 있는지 확인 합니다.</p></li>
</ul>
<p>각 무선 공급 업체에는 해당 무선 솔루션을 배포 하기 위한 고유한 권장 사항이 있습니다. WiFi 공급 업체에 문의 하 여 특정 지침을 확인 하세요.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>대역폭 요구 사항

팀은 네트워크 상태에 관계 없이 최상의 오디오, 비디오, 콘텐츠 공유 환경을 제공 하도록 디자인 되었습니다. 대역폭을 충분히 사용할 수 없는 경우에는 팀이 비디오 품질 보다 오디오 품질에 우선 순위를 둘 것 이라고 합니다.

대역폭이 제한 *되지* 않는 경우, 팀은 최대 1080p 비디오 해상도, 최대 30fps, 콘텐츠의 경우 15fps, 고화질 오디오를 비롯 한 미디어 품질을 최적화 합니다. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>관련 항목

[Office 365 네트워크 연결 원칙](https://aka.ms/pnc)

[전세계 끝점: 비즈니스용 Skype Online 및 팀](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[팀의 프록시 서버](proxy-servers-for-skype-for-business-online.md)

[팀의 미디어: 모임이 간단한 이유](https://aka.ms/teams-media)

[팀의 미디어: 전체 미디어 흐름에 대해 자세히 알아보고](https://aka.ms/teams-media-flows)

[Teams의 ID 모델 및 인증](identify-models-authentication.md)

[Teams를 배포하는 방법](How-to-roll-out-teams.md)


