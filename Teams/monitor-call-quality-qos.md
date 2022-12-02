---
title: Microsoft Teams의 통화 품질 모니터링 및 개선
author: CarolynRowe
ms.author: crowe
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: QoS(서비스 품질) 설정을 사용한 다음, Microsoft Teams에서 분석 및 통화 품질 대시보드를 호출합니다.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 969fc5645023bfcf4ad2bc0aadfe692f61b350f0
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245759"
---
# <a name="improve-call-quality-in-microsoft-teams"></a>Microsoft Teams에서 통화 품질 향상

이 문서에서는 Microsoft Teams에서 통화 품질을 모니터링, 문제 해결, 관리 및 개선하는 데 사용할 수 있는 세 가지 주요 도구를 소개합니다. 

- **CQD(통화 품질 대시보드)** : 조직 전체 추세 또는 문제를 분석하려면 성능 향상을 추진합니다.

- **통화 분석**: 개별 사용자의 통화 및 모임 품질을 분석하려면

- **QoS(서비스 품질)** : 중요한 네트워크 트래픽의 우선 순위를 지정하려면



## <a name="monitor-and-troubleshoot-call-quality"></a>통화 품질 모니터링 및 문제 해결
사용자별 **통화 분석** 및 **통화 품질 대시보드** 를 사용하여 진행 중인 작업 중에 발생하는 통화 품질 문제를 찾고 해결합니다. 이렇게 하면 네트워크 전체에서 성능 향상을 추진할 수 있습니다. 이러한 두 도구는 모두 Teams 관리 센터에 있습니다.

 - **통화 분석에는** Teams의 각 사용자에 대한  **_특정 통화 및 모임과_** 관련된 디바이스, 네트워크 및 연결에 대한 자세한 정보가 표시됩니다. Teams 관리자 및 기술 지원팀 에이전트는 이 정보를 사용하여 특정 통화에서 통화 품질 및 연결 문제를 해결합니다. 자세한 내용은 [통화 분석 설정](set-up-call-analytics.md) 및 [통화 분석을 사용하여 통화 품질 저하 문제 해결을 참조하세요](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - **CQD(통화 품질 대시보드)** 는 조직 전체의 통화 품질에 대한 **_네트워크 차원의 보기를_** 제공합니다. CQD 정보를 사용하여 문제를 식별하고 해결하는 데 도움이 됩니다. 먼저 [CQD를 설정합니다](turning-on-and-using-call-quality-dashboard.md). 그런 다음 [Teams에서 통화 및 모임 품질 관리를](quality-of-experience-review-guide.md) 읽어보세요.

 호출 분석 및 CQD는 병렬로 실행되며 독립적으로 또는 함께 사용할 수 있습니다. 예를 들어 통신 지원 전문가가 사용자의 통화 문제 해결에 더 많은 도움이 필요하다고 판단하는 경우 통화에 대한 추가 정보에 액세스할 수 있는 통신 지원 엔지니어에게 통화를 에스컬레이션합니다. 차례로 통신 지원 엔지니어는 네트워크 엔지니어에게 통화 분석에서 발견한 가능한 사이트 관련 문제에 대해 경고합니다. 네트워크 엔지니어는 CQD를 확인하여 전체 사이트 관련 문제가 사용자의 통화 문제의 원인일 수 있는지 확인합니다.


## <a name="prioritize-important-network-traffic-using-qos"></a>QoS를 사용하여 중요한 네트워크 트래픽 우선 순위 지정
사용자가 통화 및 모임에 Teams를 사용하기 시작하면 통화 또는 모임에서 발신자의 음성이 끊어지거나 끊어질 수 있습니다. 공유 비디오는 동결 또는 픽셀화되거나 완전히 실패할 수 있습니다. 이는 네트워크 정체가 발생하고 순서를 벗어나거나 전혀 도착하지 않는 음성 및 비디오 트래픽을 나타내는 IP 패킷 때문입니다. 이 경우(또는 처음부터 발생하지 않도록) **QoS(서비스 품질)를** 사용합니다. 

QoS를 사용하면 지연에 민감한 네트워크 트래픽(예: 음성 또는 비디오 스트림)의 우선 순위를 지정하여 덜 민감한 트래픽 앞에서 "줄 바꿈"할 수 있습니다(예: 다운로드할 추가 1초가 큰 문제가 아닌 새 앱 다운로드 등). QoS는 Windows 그룹 정책 개체 및 포트 기반 Access Control 목록이라는 라우팅 기능을 사용하여 실시간 스트림의 모든 패킷을 식별하고 표시하며, 이 기능은 네트워크에 고유한 전용 네트워크 대역폭을 공유하는 음성, 비디오 및 화면을 제공하도록 지시합니다.

Teams 출시를 준비하는 동안 내부 네트워크에서 QoS를 구현하는 것이 이상적이지만 언제든지 수행할 수 있습니다. 충분히 작으면 QoS가 필요하지 않을 수 있습니다.

준비가 되면 [Microsoft Teams에서 QoS(서비스 품질) 구현을 참조하세요](QoS-in-Teams.md).

QoS를 사용하여 모임 트래픽을 관리하려면 [Teams 모임에 대한 실시간 미디어 트래픽을 처리하는 방법 설정을 참조하세요](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>관련 항목

[통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용하여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[CQD 설정](turning-on-and-using-call-quality-dashboard.md)

[Teams에서 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
