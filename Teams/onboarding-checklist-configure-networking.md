---
title: Microsoft 팀의 네트워킹을 구성 하기 위한 온 보 딩 검사 목록
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 팀을 위해 네트워크를 구성할 때이 검사 목록의 핵심, 할 일 작업 및 활동을 따릅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a9a8c6eb4c015a1fc86f35fac72117766cab326
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239110"
---
# <a name="configure-networking"></a>네트워킹 구성

| 아니요 | 활동 또는 작업 | 설명 | 완료? | 추가 정보 |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| raid-1  | 팀에 대 한 네트워크 요구 사항 검토 | 네트워크 요구 사항을 전체적으로 확인 한 후에 네트워킹 세부 정보로 이동해 보세요. | | [Microsoft 팀을 위한 조직의 네트워크 준비](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| 2  | 네트워크 준비 워크숍 제공 | 네트워크 준비 평가를 수행 합니다. | |  |
| 3-4  | 네트워크 Planner 사용 | 네트워크 대역폭 계획을 수행 합니다. | | |
| 4(tcp/ipv4)  | 사용자 연결에 필요한 NAT 풀 크기 확인 | 포트 소모를 방지 하기 위해 적절 한 공용 IP 주소가 NAT 풀에 할당 되었는지 확인 합니다. 포트 소모는 내부 사용자와 장치가 Office 365 서비스에 연결할 수 없는 경우에 기여 합니다. <br/><br/>연결 문제는 클라우드 서비스에 대 한 사용자 인식 문제의 주요 원인입니다. | | [Office 365에 대 한 NAT 지원](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 5mb  | Microsoft 데이터 센터에 가장 효율적인 라우팅 구현 | 로컬 또는 지역 송신 지점을 사용 하 여 가능한 한 효율적으로 Microsoft 네트워크에 연결할 수 있는 위치를 식별 합니다. <br/><br/>**추가 정보** 열에 있는 문서는 클라이언트가 Office 365 이름 확인 및 IP 라우팅의 기능을 활용 하 여 가장 가까운 지역 데이터 센터에 효율적으로 연결 하는 방법에 대해 설명 합니다. | | [Office 365 클라이언트 연결](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 26  | 팀에 대 한 연결을 위해 요청 된 방화벽 포트 구성 | Office 365 Url 및 Ip를 검토 하 여 온-프레미스 클라이언트와 서버 및 Office 365 서비스 간의 연결에 필요한 방화벽 포트를 식별 하 고 테스트 합니다. <br/><br/>지원 되는 환경에서는 방화벽의 모든 포트를 열어야 합니다. 일부 포트나 범위를 열지 못하면 사용자 환경에 부정적인 영향을 줄 수 있습니다. **추가 정보** 열의 지침에 따라 방화벽에 미디어 포트를 구성 합니다. | | [Office 365 Url 및 IP 주소-Microsoft 팀](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| 7  | 프록시 서버 구성 | 프록시 서버를 우회 하 고 최적의 오디오 및 비디오 품질로 UDP를 사용 하 여 사용자를 Office 365에 직접 연결할 수 있도록 환경을 구성 합니다. 실시간 미디어를 강제로 프록시 서버를 통과 하는 경우 팀의 미디어 스택은 강제로 TCP로 장애 복구 되므로 품질에 부정적인 영향을 줍니다. <br/><br/>최고 품질의 사용자 환경에서는 항상 TCP를 통해 UDP를 사용 하는 것이 좋습니다. | | [서비스 관리 및 품질 계획](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) |
| 20cm(8  | 분할 터널 VPN 구성 | 일반적으로 *분할 터널 vpn*이라고 하는 vpn을 우회 하는 팀 트래픽에 대 한 대체 경로를 제공 하는 것이 좋습니다. 분할 터널링은 Office 365에 대 한 트래픽이 VPN을 통과 하지는 않지만 Office 365에 직접 전달 한다는 것을 의미 합니다. 이 변경은 품질에 긍정적인 영향을 주지만, VPN 장치 및 조직의 네트워크에서 로드를 줄이는 두 번째 이점을 제공 합니다. | | 분할 터널 VPN을 구현 하려면 VPN 공급 업체에 구성 세부 정보를 문의 하세요. |
| 되었는지  | QoS를 사용 하 여 패킷 우선 순위 구성 | QoS는 관리 되는 네트워크의 모든 세그먼트에서 구현 해야 합니다. 네트워크가 대역폭에 적절 하 게 프로 비전 된 경우에도 QoS는 예기치 않은 네트워크 이벤트가 발생할 경우 위험 경감을 제공 합니다. QoS가 구현 된 경우 이러한 예기치 않은 이벤트가 품질에 부정적인 영향을 주지 않도록 음성 트래픽이 우선 순위를 갖습니다. | | [서비스 관리 및 품질 계획](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) <br/><br/>[Microsoft 팀의 서비스 품질](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| 1천만 | 품질 및 성능을 위해 Wi-fi 네트워크 최적화 | Wi-fi 네트워크를 최적화할 때 다음과 같은 몇 가지 요인을 고려해 야 합니다. <ul><li>Wi-fi 네트워크를 통한 미디어 소통량의 우선 순위를 확인 하기 위해 QoS 또는 Wi-fi 멀티미디어 (WMM)를 구현 합니다.</li><li>Wi-fi 밴드 및 액세스 지점의 위치를 계획 하 고 최적화 합니다. 2.4 GHz 범위는 액세스 위치 배치에 따라 적절 한 성능을 제공할 것입니다.</li></ul> 특정 지침은 Wi-fi 공급 업체에 문의 하세요. | | [끝점에 대 한 wi-fi 권장 사항](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#wi-fi-recommendations-for-endpoints) |
| mb | 네트워크 평가 도구를 사용 하 여 네트워크 연결 확인 | 비즈니스용 Skype 및 팀에 대 한 네트워크 평가 도구를 사용 하 여 비즈니스용 Skype Online 및 팀 통화 및 모임에 사용 되는 모든 IP 주소 및 포트에 대 한 연결을 테스트 합니다. 도구를 다운로드 하 고이 도구를 사용 하 고 테스트 결과를 해석 하는 방법에 대 한 자세한 내용은 사용을 참조 하세요. 팀을 사용할 각 위치의 클라이언트 PC에서 도구를 실행 하는 것이 좋습니다. | | [비즈니스용 Skype 및 팀 네트워크 평가 도구](https://go.microsoft.com/fwlink/?linkid=855799) |
