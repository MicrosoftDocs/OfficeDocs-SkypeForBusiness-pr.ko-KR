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
ms.openlocfilehash: 62e687de154fadffd6ac95bd628fec6f9454cc51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162694"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Microsoft Teams의 통화 품질 모니터링 및 개선

이 문서에서는 Microsoft Teams에서 통화 품질을 모니터링, 문제 해결, 관리 및 개선하는 데 사용할 수 있는 세 가지 주요 도구를 소개합니다. 

- **CQD(품질 대시보드)** 호출 : 전체 추세 또는 문제를 분석하기 위해 성능 향상을 주도합니다.

- **통화 분석**: 개별 사용자의 통화 및 모임 품질을 분석하기 위해

- **QoS(서비스 품질)**: 중요한 네트워크 트래픽의 우선 순위를 지정합니다.



## <a name="monitor-and-troubleshoot-call-quality"></a>통화 품질 모니터링 및 문제 해결
사용자당 통화 분석  및 통화 **품질** 대시보드를 사용하여 진행 중 발생할 호출 품질 문제를 찾고 해결합니다. 이렇게 하면 네트워크 전체에서 성능 향상을 구동할 수 있습니다. 이러한 도구는 모두 Teams 관리 센터에 있습니다.

 - **통화 분석은** Teams의 각 사용자에 대한 특정 **** 호출 및 모임과 관련된 디바이스, 네트워크 및 연결에 대한 자세한 정보를 보여줍니다. Teams 관리자 및 헬프데스크 에이전트는 이 정보를 사용하여 특정 통화에서 통화 품질 및 연결 문제를 해결합니다. 자세한 내용은 통화 [](set-up-call-analytics.md) 분석 설정 및 통화 분석 사용 을 읽고 통화 품질이 좋지 않은 [문제를 해결합니다.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **CQD(통화** 품질 대시보드)는 조직 전체에서 통화 품질에 대한 네트워크 전체 보기를 제공합니다. **** CQD 정보를 사용하여 문제를 식별하고 해결하는 데 도움이 됩니다. 먼저 [CQD를 설정합니다.](turning-on-and-using-call-quality-dashboard.md) 그런 다음 Teams에서 통화 [및 모임 품질 관리를 읽습니다.](quality-of-experience-review-guide.md)

 호출 분석 및 CQD 실행을 병렬로 실행하고 독립적으로 또는 함께 사용할 수 있습니다. 예를 들어 통신 지원 전문가가 사용자의 통화 문제를 해결하는 데 도움이 더 필요하다고 판단하면 통화에 대한 추가 정보에 액세스할 수 있는 통신 지원 엔지니어에게 전화를 에스컬레이터합니다. 통신 지원 엔지니어는 통화 분석에서 발견한 가능한 사이트 관련 문제를 네트워크 엔지니어에게 경고합니다. 네트워크 엔지니어는 CQD를 검사하여 전체 사이트 관련 문제가 사용자의 호출 문제의 원인일 수 있는지 확인합니다.


## <a name="prioritize-important-network-traffic-using-qos"></a>QoS를 사용하여 중요한 네트워크 트래픽 우선 순위 지정
사용자가 Teams를 사용하여 통화 및 모임을 시작할 때 통화 또는 모임에서 발신자 음성이 깨지거나 끊어지거나 끊어지게 될 수 있습니다. 공유 비디오는 동결되거나 픽셀화되거나 모두 실패할 수 있습니다. 이는 음성 및 비디오 트래픽이 네트워크 혼잡을 발생하고 순서가 늦거나 아는 경우를 나타내는 IP 패킷에 기인합니다. 이 경우(또는 처음에 발생하는 것을 방지하기 위해) **QoS(서비스** 품질)를 사용 합니다. 

QoS를 사용하면 지연에 민감한 네트워크 트래픽(예: 음성 또는 비디오 스트림)의 우선 순위를 지정하여 덜 민감하지 않은 트래픽 앞에서 "줄을 끊습니다"(새 앱 다운로드와 같이 다운로드할 추가 초가 큰 중요하지 않은 경우)를 허용합니다. QoS는 Windows 그룹 정책 개체 및 포트 기반 액세스 제어 목록이라는 라우팅 기능을 사용하여 실시간 스트림의 모든 패킷을 식별하고 표시합니다. 이 기능은 네트워크에서 고유의 전용 네트워크 대역폭을 공유하는 음성, 비디오 및 화면 공유를 지시합니다.

이상적으로는 Teams를 롤아웃할 준비를 하는 동안 내부 네트워크에 QoS를 구현하지만 언제든지 이 작업을 할 수 있습니다. 충분히 작은 경우 QoS가 필요하지 않을 수 있습니다.

준비가되면 [Microsoft Teams에서 QoS(서비스 품질 구현)를 읽습니다.](QoS-in-Teams.md)

QoS를 사용하여 모임 트래픽을 관리하기 위해 Teams 모임에 대한 실시간 미디어 트래픽을 처리하는 방법 [설정 을 읽습니다.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>관련 항목

[통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용하여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[CQD 설정](turning-on-and-using-call-quality-dashboard.md)

[Teams에서 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)