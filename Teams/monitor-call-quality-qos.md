---
title: Microsoft 팀의 통화 품질 모니터링 및 개선
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: QoS (서비스 품질) 설정을 사용한 다음 Microsoft 팀에서 분석 및 통화 품질 대시보드를 호출 합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085943"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Microsoft 팀의 통화 품질 모니터링 및 개선

이 문서에서는 Microsoft 팀에서 통화 품질을 모니터링, 문제 해결, 관리 및 개선 하는 데 사용할 수 있는 세 가지 주요 도구에 대해 설명 합니다. 

- **CQD (통화 품질 대시보드)**: 조직 전체에 걸친 추세 또는 문제를 분석 하는 데 드라이브 성능이 향상 되었습니다.

- **통화 분석**: 개별 사용자의 통화 및 모임 품질을 분석 하는 방법

- **QoS (서비스 품질)**: 중요 한 네트워크 트래픽 우선 순위 지정



## <a name="monitor-and-troubleshoot-call-quality"></a>통화 음질 모니터링 및 문제 해결
사용자 단위 **통화 분석** 및 **통화 품질 대시보드** 를 사용 하 여 진행 중인 작업 중에 발생 하는 통화 품질 문제를 찾고 해결 합니다. 이렇게 하면 네트워크에서 성능을 향상 시킬 수 있습니다. 이러한 도구는 모두 팀 관리 센터에 있습니다.

 - **통화 분석** 은 팀의 각 사용자에 대 한 ***특정 통화 및 모임*** 과 관련 된 장치, 네트워크 및 연결에 대 한 자세한 정보를 보여 줍니다. 팀 관리자 및 헬프데스크 상담원은이 정보를 사용 하 여 특정 전화의 통화 품질 및 연결 문제를 해결할 수 있습니다. 자세한 내용은 통화 [분석 설정](set-up-call-analytics.md) 및 통화 [분석을 사용 하 여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)을 참고 하세요.
 
 - **CQD (통화 품질 대시보드)** 는 조직의 ***네트워크 전체*** 에 걸친 통화 품질 보기를 제공 합니다. 모든 문제를 식별 하 고 해결 하는 데 도움이 되는 CQD 정보를 사용 합니다. 먼저 [CQD를 설정](turning-on-and-using-call-quality-dashboard.md)합니다. 그런 다음 [팀에서 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)를 읽어 보세요.

 통화 분석 및 CQD는 병렬로 실행 되며 독립적으로 또는 함께 사용할 수 있습니다. 예를 들어 통신 지원 전문가에 게 사용자의 통화 문제 해결에 대 한 추가 지원이 필요한 것으로 판단 되는 경우 통화를 통신 지원 엔지니어에 게 전달 하 고, 사용자는 통화에 대 한 자세한 정보에 액세스할 수 있습니다. 그러면 통신 지원 엔지니어가 전화 분석에서 발견 되는 사이트 관련 문제에 대 한 네트워크 엔지니어를 알립니다. 네트워크 엔지니어는 전체 사이트 관련 문제가 사용자의 통화 문제를 일으킬 수 있는지 확인 하기 위해 CQD를 검사 합니다.


## <a name="prioritize-important-network-traffic-using-qos"></a>QoS를 사용 하 여 중요 한 네트워크 트래픽 우선 순위 지정
사용자가 팀을 사용 하 여 통화 및 모임을 시작 하면 통화 또는 모임에서 발신자의 음성이 발생 하거나 절삭 될 수 있습니다. 공유 비디오가 중지 또는 pixelate 수도 있고 모두 실패할 수 있습니다. 이는 네트워크 혼잡이 발생 하 고 순서에 도달 하지 않은 음성 및 비디오 트래픽을 나타내는 IP 패킷으로 인해 발생 합니다. 이 문제가 발생 하는 경우 (또는 처음에이를 발생 하지 않도록 하려면) **서비스 품질 (QoS)** 을 사용 합니다. 

QoS를 사용 하는 경우에는 지연 되는 네트워크 트래픽 (예: 음성 또는 비디오 스트림)의 우선 순위를 지정 하 여 중요 하지 않은 트래픽 앞 (즉, 다운로드가 시작 되는 추가 초가 큰 문제가 아닌 경우 새 앱 다운로드)에 "줄에서 잘라내기"를 허용 합니다. QoS는 실시간 스트림의 모든 패킷을 식별 하 고 표시 하며, Windows 그룹 정책 개체와 포트 기반 액세스 제어 목록 이라는 라우팅 기능을 사용 하 여 네트워크에 음성, 비디오, 화면 공유를 제공 하 여 자신의 전용 네트워크 대역폭을 공유할 수 있도록 합니다.

이상적으로는 팀 롤아웃을 준비 하는 동안 내부 네트워크에 QoS를 구현 하지만 언제 든 지이 작업을 수행할 수 있습니다. 충분히 작은 경우 QoS가 필요 하지 않을 수 있습니다.

준비가 되 면 [Microsoft 팀에서 QoS (서비스 품질)](QoS-in-Teams.md)를 읽어 보세요.

QoS를 사용 하 여 모임 트래픽을 관리 하려면 [팀 모임에 대 한 실시간 미디어 트래픽을 처리 하는 방법 설정을](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)읽습니다.


## <a name="related-topics"></a>관련 항목

[통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용하여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[CQD 설정](turning-on-and-using-call-quality-dashboard.md)

[팀에서 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

