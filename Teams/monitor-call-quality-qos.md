---
title: Microsoft Teams의 통화 품질 모니터링 및 개선
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: QoS(서비스 품질) 설정을 사용하여 Microsoft Teams에서 분석 및 통화 품질 대시보드를 호출합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 107bbf867c410a556e02d76eb991cf5f04730efa
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46587635"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Microsoft Teams의 통화 품질 모니터링 및 개선

이 문서에서는 Microsoft Teams에서 통화 품질을 모니터링, 문제 해결, 관리 및 개선하는 데 사용할 수 있는 세 가지 주요 도구를 소개합니다. 

- **CQD(통화** 품질 대시보드) : 전체적인 추세 또는 문제를 분석하기 위해 성능 향상을 주도합니다.

- **통화 분석:** 개별 사용자의 통화 및 모임 품질을 분석하기 위해

- **QoS(서비스 품질)**: 중요한 네트워크 트래픽의 우선 순위를 지정합니다.



## <a name="monitor-and-troubleshoot-call-quality"></a>통화 품질 모니터링 및 문제 해결
사용자당 통화 분석  및 통화  품질 대시보드를 사용하여 진행 중 발생할 통화 품질 문제를 찾아서 해결합니다. 이렇게 하면 네트워크 전체에서 성능 향상을 구동할 수 있습니다. 이러한 도구는 모두 Teams 관리 센터에 있습니다.

 - **통화 분석은** Teams에서 각 사용자의 특정 통화 및  모임과 관련된 장치, 네트워크 및 연결에 대한 자세한 정보를 보여줍니다. Teams 관리자 및 지원팀 상담원은 이 정보를 사용하여 특정 통화에서 통화 품질 및 연결 문제를 해결합니다. 자세한 내용은 통화 [](set-up-call-analytics.md) 분석 설정 및 통화 분석을 사용하여 통화 품질 문제를 [해결하세요.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **CQD(통화** 품질 대시보드)는 조직 전체의 통화 품질에 대한 네트워크 전체 보기를 제공합니다.  CQD 정보를 사용하여 문제를 식별하고 해결하는 데 도움이 됩니다. 먼저 [CQD를 설정합니다.](turning-on-and-using-call-quality-dashboard.md) 그런 다음 [Teams에서 통화 및 모임 품질 관리를 읽습니다.](quality-of-experience-review-guide.md)

 호출 분석 및 CQD는 병렬로 실행하며 독립적으로 또는 함께 사용할 수 있습니다. 예를 들어 통신 지원 전문가가 사용자의 통화 문제를 해결하는 데 도움이 더 필요하다고 판단하면 통화에 대한 추가 정보에 액세스할 수 있는 통신 지원 엔지니어에게 전화를 에스컬링합니다. 차례로 통신 지원 엔지니어는 네트워크 엔지니어에게 호출 분석에서 발견된 가능한 사이트 관련 문제로 경고합니다. 네트워크 엔지니어는 CQD를 검사하여 전체 사이트 관련 문제가 사용자의 통화 문제의 원인일 수 있는지 확인합니다.


## <a name="prioritize-important-network-traffic-using-qos"></a>QoS를 사용하여 중요한 네트워크 트래픽 우선 순위 지정
사용자가 통화 및 모임에 Teams를 사용할 때 발신자 음성이 통화나 모임에서 끊기거나 끊어지거나 끊어지게 될 수 있습니다. 공유 비디오는 중지 또는 픽셀화하거나 모두 실패할 수 있습니다. 이는 네트워크 정체가 발생하고 순서를 늦게 도착하거나 아치 않는 음성 및 비디오 트래픽을 나타내는 IP 패킷 때문입니다. 이 경우(또는 처음에 발생하지 못하게) **QoS(서비스** 품질)를 사용 합니다. 

QoS를 사용하면 지연에 민감한 네트워크 트래픽(예: 음성 또는 비디오 스트림)의 우선 순위를 지정하여 덜 민감하지 않은 트래픽(예: 다운로드할 추가 초가 큰 거래가 아닌 새 앱 다운로드)에서 "줄에서 잘라 내기"할 수 있습니다. QoS는 Windows 그룹 정책 개체 및 포트 기반 Access Control Lists라는 라우팅 기능을 사용하여 실시간 스트림의 모든 패킷을 식별하고 표시합니다. 이 기능은 네트워크에서 자신의 전용 네트워크 대역폭을 공유하는 음성, 비디오 및 화면을 제공하게 합니다.

이상적으로는 Teams를 롤아웃할 준비를 하면서 내부 네트워크에 QoS를 구현하지만 언제든지 구현할 수 있습니다. 충분히 작은 경우 QoS가 필요하지 않을 수 있습니다.

준비가 됐을 때 [Microsoft Teams에서 QoS(서비스 품질 구현)를 읽어 읽습니다.](QoS-in-Teams.md)

QoS를 사용하여 모임 트래픽을 관리하려는 경우 Teams 모임에 대한 실시간 미디어 트래픽을 처리하는 방법 [집합을 읽어 읽습니다.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>관련 항목

[통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용하여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[CQD 설정](turning-on-and-using-call-quality-dashboard.md)

[Teams에서 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

