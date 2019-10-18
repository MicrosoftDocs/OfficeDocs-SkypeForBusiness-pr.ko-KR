---
title: Microsoft 팀을 위한 조직의 네트워크 준비
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
audience: admin
description: Microsoft 팀 네트워크를 준비 하 고 관리 하는 방법을 알아보세요. 정보에는 네트워크 요구 사항, 대역폭 요구 사항, 추가 고려 사항 등이 포함 됩니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9013eb1048d022244166906edb1737b01757ed6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573225"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft 팀을 위한 조직의 네트워크 준비


팀은 다음 세 가지 트래픽 형태를 결합 합니다.

-   Office 365 온라인 환경과 팀 클라이언트 간의 데이터 트래픽 (신호, 현재 상태, 채팅, 파일 업로드 및 다운로드, OneNote 동기화).

-   피어 투 피어 실시간 통신 트래픽 (오디오, 비디오, 데스크톱 공유).

-   회의 실시간 통신 트래픽 (오디오, 비디오, 데스크톱 공유).

이는 두 가지 수준의 네트워크에 영향을 주고 피어 투 피어 시나리오에 대 한 트래픽이 Microsoft 팀 클라이언트 간에 직접 전달 되며, 트래픽은 Office 365 환경과 모임 시나리오에 대 한 Microsoft 팀 클라이언트 간에 전달 됩니다. 트래픽 흐름을 최적화 하려면 내부 네트워크 세그먼트 (예: WAN을 통해 사이트 간)와 네트워크 사이트와 Office 365 사이에 모두 흐름을 허용 해야 합니다. 올바른 포트를 열지 않거나 특정 포트를 능동적으로 차단 하면 성능이 저하 될 수 있습니다.


Microsoft 팀 내에서 실시간 미디어를 사용 하 여 최적의 환경을 얻으려면 네트워크가 Office 365의 네트워킹 요구 사항을 충족 해야 합니다. 자세한 내용은 [비즈니스용 Skype Online의 미디어 품질과 네트워크 연결 성능을](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)참조 하세요.

두 가지 네트워크 세그먼트 (클라이언트에서 Microsoft edge 및 고객에 게 Microsoft Edge에 대 한)를 정의 하려면 다음 권장 사항을 고려 하세요.


|값  |클라이언트에서 Microsoft Edge로  |고객 Edge에서 Microsoft Edge로  |
|:--- |:--- |:--- |
|**대기 시간 (단방향)**\*  |< 50ms          |< 30ms         |
|**지연 (RTT 또는 왕복 시간)**\* |< 100ms   |< 60ms |
|**버스트 패킷 손실**    |200ms 간격 중 10% <         |200ms interval 동안 1% <         |
|**패킷 손실**     |15s 간격 중 1% <          |15s 기간 동안 0.1% <         |
|**패킷 간 도착 지터**    |15s 간격 중 30ms <         |모든 15s 기간 동안 15ms <         |
|**패킷 순서 다시 매기기**    |<0.05% 주문 종료 패킷         |<0.01% 주문 종료 패킷         |

\*대기 시간 메트릭 대상은 회사 사이트 또는 사이트를 가정 하 고 Microsoft의 경계는 동일한 대륙에 있습니다.

Microsoft 네트워크에 지에 대 한 회사 사이트 연결에는 WiFi 또는 다른 무선 기술인 첫 번째 홉 네트워크 액세스가 포함 되어 있습니다.

네트워크 성능 대상은 적절 한 대역폭과/또는 [QoS 계획](QoS-in-Teams.md)을 가정 합니다. 즉, 네트워크 연결이 최대 부하에 도달 했을 때 요구 사항이 팀의 실시간 미디어 트래픽에 직접적으로 적용 됩니다.

팀을 위해 네트워크를 준비 하는 방법에 대 한 자세한 내용은 [네트워크 Planner](https://docs.microsoft.com/microsoftteams/network-planner)를 참조 하세요.


## <a name="bandwidth-requirements"></a>대역폭 요구 사항
Microsoft 팀은 네트워크 상태에 관계 없이 최상의 오디오, 비디오 및 콘텐츠 공유 환경을 제공 합니다. 변수 코덱에는 최소한의 영향으로 제한 된 대역폭 환경에서 미디어를 협상할 수 있습니다. 그러나 대역폭이 문제가 되지 않는 경우에는 최대 1080p 비디오 해상도, 최대 30fps, 콘텐츠의 경우 15fps, 고화질 오디오 등의 품질에 대해 경험을 최적화할 수 있습니다.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a>추가 네트워크 고려 사항
---------------

#### <a name="external-name-resolution"></a>외부 이름 확인

팀 클라이언트를 실행 하는 모든 클라이언트 컴퓨터가 Office 365에서 제공 하는 서비스를 검색 하기 위해 외부 DNS 쿼리를 확인할 수 있으며 방화벽이 액세스를 차단 하지 않는지 확인 합니다. 방화벽 포트를 구성 하는 방법에 대 한 자세한 내용은 [Office 365 url 및 IP 범위로](office-365-urls-ip-address-ranges.md)이동 하세요.

#### <a name="nat-pool-size"></a>NAT 풀 크기

여러 사용자/장치가 NAT (Network Address Translation) 또는 PAT (Port Address Translation)를 사용 하 여 Office 365에 액세스 하는 경우, 각 공용 라우팅 가능 IP 주소 뒤에 숨겨진 장치가 지원 되는 번호를 초과 하지 않는지 확인 해야 합니다.

이 위험을 줄이려면 포트 소모를 방지 하기 위해 적절 한 공용 IP 주소가 NAT 풀에 할당 되어 있는지 확인 합니다. 포트 소모를 통해 Office 365 서비스에 연결할 때 내부 최종 사용자 및 장치가 문제를 발생 시킬 수 있습니다. 자세한 내용은 [Office 365의 NAT 지원을](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)참조 하세요.

#### <a name="intrusion-detection-and-prevention-guidance"></a>**침입 감지 및 예방 지침**

아웃 바운드 연결에 대 한 추가 보안 계층에 대 한 침입 감지 및/또는 방지 시스템 (ID/i p)이 환경에 있는 경우 목적지에서 Office 365 Url을 사용 하는 모든 트래픽이 허용 목록 확인 해야 합니다.

<a name="network-health-determination"></a>네트워크 상태 결정
-----------------

네트워크 내에서 Microsoft 팀을 구현 하는 경우 필요한 대역폭을 확보 하 고, 필요한 모든 IP 주소와 열려 있는 올바른 포트를 액세스 하 고, 실시간 미디어에 대 한 성능 요구 사항을 만족 하 고 있는지 확인 해야 합니다. .

이러한 조건을 충족 하지 못하는 경우에는 최종 사용자가 통화와 모임 중 품질이 좋지 않아 팀에서 최적의 환경을 얻을 수 없습니다.

이러한 조건을 충족 하지 않으면 계속 하기 전에 기준에 맞는지 프로젝트를 일시 중지 하는 것이 좋습니다.


|  |  |  |
|---------|---------|---------|
|![결정 지점을 나타내는 아이콘](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |판단 요점         |실시간 미디어 지원에 대 한 네트워크 기능을 평가 했습니까?<br></br>네트워크가 제대로 평가 되지 않았거나 리얼 시간 미디어를 지원 하지 않는 경우에는 네트워크 영향과 낮은 팀 환경을 줄이기 위해 영상 및 화면 공유 기능을 사용 하지 않도록 설정 해야 하나요?         |
|![다음 단계를 나타내는 아이콘](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |다음 단계         |알 수 없는 네트워크 품질: 네트워크가 실시간 미디어에 대 한 준비가 되었는지 확인 하기 위해 네트워크 준비 평가를 수행 합니다.<br></br>네트워크 품질 저하: 네트워크 재구성 단계를 수행 하 여 고품질 실시간 미디어에 적합 한 환경을 제공 합니다.<br></br>네트워크 만족: 모든 IP 주소 및 포트에 대 한 액세스가 적절 한지 확인 합니다.           |

## <a name="related-topics"></a>관련 항목

[비디오: 네트워크 계획](https://aka.ms/teams-networking)
