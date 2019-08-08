---
title: Microsoft 팀에서 QoS를 구현 하 고 통화 분석을 모니터링
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: jambirk
description: QoS (서비스 품질) 설정을 사용한 다음 Microsoft 팀에서 분석 및 통화 품질 대시보드를 호출 합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 70e862adf2aad795a9ef1ab34eaa2de21240a388
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239256"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Microsoft 팀에서 QoS를 구현 하 고 통화 품질을 모니터링

## <a name="get-started"></a>시작 하기

사용자가 전화를 걸고 모임에 참가 하기 위해 팀을 사용 하기 시작 하면 통화 또는 모임에서 발신자의 음성이 발생 하거나 chopping 수 있습니다. 공유 비디오가 중지 또는 pixelate 수도 있고 모두 실패할 수 있습니다. 이는 네트워크 혼잡이 발생 하 고 순서에 도달 하지 않은 음성 및 비디오 트래픽을 나타내는 IP 패킷으로 인해 발생 합니다. 이러한 문제를 처리 하 고 반환 하는 것을 방지 하는 방법 (주로 QoS (서비스 품질)을 확인할 수 있는 방법이 있습니다.

**QoS (서비스 품질)** 는 네트워크 지연과 같은 중요 한 네트워크 트래픽 (예: 새 앱 다운로드 (예: 다운로드에 추가 초)을 사용 하는 것이 좋습니다. "음성 또는 비디오 스트림")을 "회선에서 잘라내기" 하는 것을 허용 하는 방법입니다. 큰 노력이 아닙니다. QoS는 Windows 그룹 정책 개체와 포트 기반 액세스 제어 목록 이라는 라우팅 기능을 사용 하 여 실시간 스트림의 모든 패킷을 식별 하 고 표시 하며, 이렇게 하면 네트워크에서 음성, 비디오 및 화면 공유를 통해 자신의 전용 부분을 쉽게 전달할 수 있습니다. 네트워크 대역폭.

 전자 메일을 통해 편지를 보내는 것과 같은 기능을 제공 하는 것이 좋습니다. 책 요금을 전송 하는 경우에는 시간이 매우 오래 걸릴 수 있으며, 첫 번째 수업을 보내는 것이 훨씬 더 빠르기 때문에 우선 순위 메일을 보내는 경우에도 마찬가지입니다. 2 일 이내에 있습니다. 많은 양의 네트워크는 메일 보다 빠르게 실행 되지만, 일부 응용 프로그램에 대해 속도가 중요 하 고 다른 사용자에 게는 중요 하지 않은 경우에도 계속 실행 됩니다. 이 주제는 본질적으로 기본적으로 자세 하 고 이해 하기 힘든 반면, 시간과 에너지 선행에 투자 하는 것이 가능 하도록 사용자 환경에 큰 차이를 줍니다. 자세한 내용은 [Microsoft 팀에서 서비스 품질 구현 (QoS)](QoS-in-Teams.md) 을 참조 하세요.

이상적으로는 팀을 설정 하는 동안 내부 네트워크에 QoS를 구현할 수 있지만,이 경우 선택 사항으로 충분 합니다. 이렇게 하면 지연 되는 음성 및 비디오 트래픽이 다른 트래픽에 대 한 우선 순위를 가질 수 있습니다. 모든 [클라이언트 장치](QoS-in-Teams-clients.md), [Microsoft 팀 관리 센터](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)및 네트워크의 스위치와 라우터에서이 우선 순위를 지정 합니다.

[**통화 분석 및 통화 품질 대시보드**](difference-between-call-analytics-and-call-quality-dashboard.md) 는 진행 중인 작업 중 발생 하는 문제를 찾아서 해결 하는 데 사용 됩니다.  

**통화 분석** 에서는 Microsoft 팀 또는 비즈니스용 Skype 계정의 각 사용자에 대 한 ***특정 통화 및 모임*** 과 관련 된 장치, 네트워크 및 연결에 대 한 자세한 정보를 보여 줍니다. Office 365 관리자는 통화 분석을 사용 하 여 특정 통화에서 발생 하는 통화 품질 및 연결 문제를 해결할 수 있습니다. 이는 문제를 식별 하 고 제거 하는 데 도움이 됩니다.

**콜 품질 대시보드 (CQD)** 는 관리자와 네트워크 엔지니어가 ***네트워크***를 최적화 하 고 단일 통화를 분석 하 고 문제를 해결할 수 있도록 설계 되었습니다. CQD는 특정 사용자 로부터 포커스를 이동 하 여 전체 조직에 대 한 집계 된 정보를 확인 합니다. 또한 문제를 식별 하 고 제거 하는 데 도움이 될 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 팀에서 QoS (서비스 품질) 구현](QoS-in-Teams.md)

[비디오: 통화 품질 개요](https://aka.ms/teams-quality)

[통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용 하 여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[통화 품질 대시보드 켜기 및 사용](turning-on-and-using-call-quality-dashboard.md)

[통화 품질 대시보드에서 사용할 수 있는 크기 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[통화 품질 대시보드의 스트림 분류](stream-classification-in-call-quality-dashboard.md)