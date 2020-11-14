---
title: Microsoft Teams 룸 계획
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 이 문서에서는 차세대 Skype 대화방 시스템인 Microsoft 팀 회의실을 배포 하기 위한 관련 계획 고려 사항에 대해 설명 합니다.
ms.openlocfilehash: f91d1ab8eeb3a89207f78fc37b9924f411a1edc1
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031444"
---
# <a name="plan-microsoft-teams-rooms"></a>Microsoft 팀 회의실 계획

이 문서에서는 전체 모임 및 회의실 전략의 일부로 Microsoft 팀 대화방을 계획 하 고 제공 하 고 운영 하는 종단 간 접근 방식을 소개 합니다.

기술 정보 지원에 대 한 링크를 통해 권장 접근 방법 및 주요 의사 결정 사항에 대해 아래에서 계획 정보를 확인 하세요. 이미 완벽 하 게 배포 된 경우에도 섹션 계획, 배포 및 관리를 검토 하는 것이 좋습니다.

## <a name="overview-of-microsoft-teams-rooms"></a>Microsoft 팀 대화방 개요

Microsoft 팀 대화방은 작은 huddle 영역에서 대용량 회의실으로 모든 크기의 모임에 HD 영상, 오디오, 콘텐츠 공유를 제공 하는 완전 한 모임 환경을 제공 합니다.

![회의실 벽면에 탑재 된 콘솔, 마이크 및 큰 화면은 Microsoft 팀 회의실 설정의 예를 보여 줍니다.](../media/room-systems-image1.png "회의실 벽면에 탑재 된 콘솔, 마이크 및 큰 화면은 Microsoft 팀 회의실 설정의 예를 보여 줍니다.")

Microsoft [팀 대화방 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 은 Microsoft 팀 대화방에 대 한 자세한 내용과 배포의 일부로 값을 추가 하는 방법에 대 한 자세한 정보를 얻을 수 있는 유용한 리소스입니다. 또한이 [개요 비디오](https://youtu.be/tNey5KZVCl0)를 시청 하는 것이 좋습니다. 

## <a name="microsoft-teams-rooms-components"></a>Microsoft 팀 대화방 구성 요소

Microsoft 팀 대화방에는 훌륭한 사용자 환경을 제공 하는 다음과 같은 주요 구성 요소가 포함 되어 있습니다.

- 터치 스크린 컨트롤 패널
- 계산
- Microsoft 팀 대화방 응용 프로그램
- Dock/extender
- 주변 기기 장치 (카메라, 마이크, 스피커)
- 외부 화면 (최대 2 개)
- HDMI 입력

이러한 구성 요소를 여러 공급 업체에서 사전 설치 된 번들으로 제공 하거나 [이 문서에 설명 된 요구 사항](requirements.md)에 따라 개별적으로 지원 되는 구성 요소를 구매할 수 있습니다.

Surface Pro/dock 조합 외에도, 통합 된 터치 스크린 제어판, 계산, 도킹, 키 주변 장치를 사용 하 여 Microsoft 팀 대화방을 구매할 수 있습니다. 

일반적으로 번들 및 통합 단위에는 사전 설치 된 소프트웨어를 포함 하는 반면, 지원 되는 구성 요소를 Surface Pro 시스템에 대해 개별적으로 구입 하는 경우에는 소프트웨어를 설치 해야 합니다. 자세한 내용은 [디바이스에 소프트웨어 설치에 대 한이 문서](rooms-scale.md)를 참조 하세요. 

Microsoft 팀원, 비즈니스용 Skype Online 또는 비즈니스용 Skype 하이브리드 또는 온-프레미스 배포를 사용 하 여 Microsoft 팀 대화방을 배포할 수 있습니다.  필요한 라이선스에 대 한 자세한 내용은 [팀 회의실 라이선스 업데이트](rooms-licensing.md) 를 참조 하세요.

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>조직의 Microsoft 팀 대화방을 배포 하나요? </li><li>Microsoft 팀 공간 시스템 (별도의 구성 요소로 번들로 제공 됨) 또는 통합 단위로 제공 하는 방법은 무엇 인가요?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계 | <ul><li>배포 전반에 걸쳐 주요 활동을 수행할 사용자를 식별 합니다.</li><li>보유 하 고 있는 회의실에 적합 한 Microsoft 팀 채팅방과 주변 장치를 배포 하려는 위치를 확인 하려면 사용 중인 회의실을 검토 하 고 설정 합니다.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>배포 전반에 걸쳐 주요 활동을 수행할 사용자 식별

아래 설명 된 방법을 사용 하 여 배포 과정을 안내 하 고 조직에 필요한 경우이 문서 전체에서 제공 되는 샘플 출력을 사용자 지정 합니다.

현재 보유 하 고 있는 회의실을 파악 하 고 향후에 가장 적합 한 장비를 선택 및 procuring, 사이트 readying, 서비스 구성 및 배포, 변경 및 사용자 채택을 관리, 운영 및 유지 관리 절차 개발 등을 통해 시작 합니다.

![먼저 사용자의 현재 상태를 파악 하 고, 필요한 장비를 선택 하 고 procuring,, 사이트 readying, 서비스 구성, 배포, 변경 및 사용자 채택을 관리, 운영 및 유지 관리 절차를 개발 하는 등의 작업을 진행 합니다.](../media/room-systems-image2.png "먼저 사용자의 현재 상태를 파악 하 고, 필요한 장비를 선택 하 고 procuring,, 사이트 readying, 서비스 구성, 배포, 변경 및 사용자 채택을 관리, 운영 및 유지 관리 절차를 개발 하는 등의 작업을 진행 합니다.")

이러한 활동을 여러 팀에서 조정 해야 할 수 있습니다. 여기서는 작업 해야 할 사용자를 결정 하는 데 도움이 되도록 사용자가 다루어야 하는 주요 작업 및 일반적으로 회의실 시스템을 배포 하 고 관리 하는 팀에 대 한 제안을 제공 합니다.

| 작업                        | 누가 작업을 수행할 것입니다.           | 할당 대상 | 이 콘텐츠의 링크 |
|----------------------------|----------------------------------------|-------------|-----------------------|
| 재고 공간            | 시설/AV 팀/IT 프로젝트 팀 |             | [방 재고 및 용량 계획](#room-inventory-and-capability-planning)        |
| 계획 기능          | IT 프로젝트 팀                        |             | [방 재고 및 용량 계획](#room-inventory-and-capability-planning)                       |
| 장치 선택           | IT 프로젝트 팀/AV 팀              |             | [장치 선택](#device-selection)                      |
| 얻은                | IT 프로젝트 팀/AV 팀              |             | [얻은](#procurement)                      |
| 사이트 준비             | 시설/AV 팀/IT 프로젝트 팀 |             | [사이트 준비](rooms-deploy.md#site-readiness)                      |
| 서비스 준비          | IT 프로젝트 팀                        |             | [서비스 준비](rooms-deploy.md#service-readiness)                      |
| 구성              | IT 프로젝트 팀                        |             | [구성 및 배포](rooms-deploy.md#configuration-and-deployment)                      |
| Deployment                 | 시설/AV 팀/IT 프로젝트 팀 |             | [배포 검사 목록](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| 도입할                   | 시설/AV 팀/IT 프로젝트 팀 |             | [도입할](#plan-for-adoption-and-change-management)                      |
| 유지 관리 및 운영 | AV 팀/IT 프로젝트 팀              |             | [관리 개요](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>방 재고 및 용량 계획

첫 번째 단계는 조직의 기존 모임 및 회의실을 사용 하 여 환경, 방 크기, 레이아웃, 용도를 파악 하 고, 룸에서 더 다양 한 공동 작업 기능을 사용할 수 있는 경우와 같이 범위 내에서 각 채팅방에 포함할 기능을 식별 하는 것입니다. 

각각의 기존 방에 장비 및 기능에 대 한 인벤토리를 만든 후에는 해당 방에 대 한 요구 사항이 장치 선택 계획에 공급 되므로 풍부한 회의 솔루션을 만들 수 있습니다. 공간 크기와 목적 외에, 각 방에 필요한 형식을 (오디오, 영상)는 각 방에 대해 가장 적합 한 솔루션을 결정 하는 데 중요 한 역할을 합니다. 

검색의 일부로 공간 acoustics 및 레이아웃을 고려 하는 것이 중요 합니다. 예를 들어 방에 있는의 자가 카메라 보기를 차단 하지 않았는지 확인 합니다. 채팅방에 과도 한 반향을 또는 소음이 없는지, 화면 및 Microsoft 팀 방에 대 한 충분 한 전력이 있는지 확인 합니다. 오디오-시각적 개체 (AV) 팀 또는 파트너가에 게 advise 할 수 있다는 것을 고려해 야 할 여러 요소가 있습니다. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>이 배포의 범위 내에 있는 채팅방은 무엇 인가요?</li><li>배포의 범위 내에 있는 사이트는 무엇 인가요?</li><li>회의실 재고는 누가 할 수 있나요?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>범위에서 회의실을 검토 하 고 Microsoft 팀 대화방 구성을 정의 합니다.</li></ul>|

_예제 모임/회의실 목록_

| 사이트  | 방 이름 | 방 종류 | 인원 수  | 범위 | 현재 채팅방 용량       | 향후 방 용량     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| 런던 사령부 | Curie         | 중형        | 6 &ndash; 12                  | 예          | 폰                        | 1 화면, 오디오 및 비디오 + 프레젠테이션<br>PSTN 액세스 |
| 시드니 사령부 | 지          | 대형         | 12 &ndash; 16                 | 예          | 레거시 AV 장치, 1 화면 및 카메라 | 2 개의 화면, 오디오 및 비디오와 프레젠테이션<br>PSTN 액세스 |

## <a name="device-selection"></a>장치 선택 

회의실에 대해 원하는 이후 기능을 기준으로 각 방에 대해 가장 적합 한 Microsoft 팀 대화방 솔루션을 평가 합니다. 방 크기 및 레이아웃에 따라 가장 적합 한 AV 주변 장치를 결정 합니다. 

방 유형과 크기에 따라 시스템 및 주변 장치 유형에 대 한 지침은 [Microsoft 팀 대화방 요구 사항](requirements.md) 문서를 참조 하세요. 

선호 하는 공급 업체에 따라, 요구 사항 문서에 제공 된 정보를 사용 하 여 회의실 유형별로 Microsoft 팀 회의실 및 지원 되는 주변 장치 구성을 정의 하 고이를 배포의 템플릿으로 사용 합니다. 

**Pro 팁** – 일부 방 유형도 배포에 적용 되지 않을 수 있습니다.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>인벤토리에서 어떤 유형의 채팅방이 배포에 대해 범위 내에 있습니까?</li><li>각 채팅방 유형에 대해 어떤 시스템을 배포 하 시겠습니까?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>선택한 시스템에 대 한 주요 작동 재료를 수집 하 고 조달 팀에 참여 하기 시작 합니다.</li></ul>|

_조직의 샘플 Microsoft 팀 공간 배포 서식 파일_

| **방 종류/크기** | **인원 수**  | **Microsoft 팀 대화방 시스템** | **주변 기기 장치**  | **개 표시** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| ' 10으로 9 ' 포커스      | 2 &ndash; 4                   |                                  |                         |                 |
| Small 16 ' x 16 '     | 4 &ndash; 6                   |                                  |                         |                 |
| 중간 18 ' 기준 20 '    | 6 &ndash; 12                  |                                  |                         |                 |
| 큰 15 개 ' 기준 32 '     | 12 &ndash; 16                 |                                  |                         |                 |

**Pro 팁 –** 이제 선택한 Microsoft 팀 회의실 솔루션에 대 한 정보 수집을 시작 하는 데 시간이 오래 걸리는 경우

## <a name="procurement"></a>얻은 

장치 파트너를 통해 선택 된 시스템을 번들 또는 통합 솔루션으로 사용할 수 있습니다. Surface Pro 장치 및 기존의 _지원 되_ 는 AV 주변 장치를 사용 하 여 파트너 장치 도크를 얻고 자신의 Microsoft 팀 공간 솔루션을 준비할 수도 있습니다. 

[요구 사항 문서](requirements.md)에 나열 된 여러 파트너의 Microsoft 팀 대화방을 받을 수 있습니다. 이러한 솔루션 및 조달 옵션에 대해 자세히 알아보려면 파트너 웹 사이트를 방문 하세요. 

배포 규모 및 접근 방식에 따라, 초기 구성 및 과제를 위해 Microsoft 팀 회의실 및 지원 되는 주변 장치를 중앙 위치로 제공 하도록 결정할 수 있습니다. 이는 여러 사이트에서 단계적 롤아웃에 좋은 접근 방법 일 수 있습니다. 또는 번들을 사이트에 직접 배송 하도록 선택할 수 있습니다. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트 또는 스테이징 시설에 구성 요소를 직접 제공 하나요?</li><li>스테이징 기능을 관리 하는 사용자 (하나를 사용 하기로 결정 한 경우)</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>작업을 계획 합니다.</li><li>채택 및 변경 관리 계획</li></ul>|

## <a name="plan-for-operations"></a>작업 계획 

조직에서 모니터링, 관리 및 관리 작업을 지속적으로 실행 해야 하며 배포 초기에 이러한 작업을 수행 하는 사용자에 게 동의 하는 것이 중요 합니다. 

대부분의 조직에는 회의실 및 장치를 관리 하는 AV 팀 또는 파트너가 있습니다. 이 팀은 Microsoft 팀 대화방 장치를 관리 하 여 성능을 모니터링 하 고 소프트웨어 업데이트 및 핫픽스를 배포 하는 사용자에 게 동의 해야 합니다. 

Microsoft 팀 회의실을 사용 하는 방법 및 Microsoft 팀원 들이 수행할 수 있는 주요 문제 해결 단계를 더 잘 이해 하 고 있는지 확인 하 고 헬프 데스크 팀에 대 한 질문과 대답을 제공 하는 헬프 데스크 전담팀에 대해 Rooms֪를 고려 합니다. 이 FAQ는 [사용자 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 및 [알려진 문제](known-issues.md)를 출발점으로 하는 것이 좋습니다.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>Microsoft 팀 회의실을 관리할 사용자를 결정 합니다.</li><li>Microsoft 팀 대화방 관련 통화를 라우팅할 헬프 데스크 대기열을 결정 합니다.</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>계정을 호스트할 준비를 합니다. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>채택 및 변경 관리 계획

Microsoft 팀 대화방 시스템은 사용자에 게 새로운 기능을 도입 합니다. 이는 사용자가 변경 될 것 이라는 것을 인식 하 고 있으며, 캠페인에서 사용자에 게 새 시스템의 이점과이 팀과 논의할 때 사용할 수 있는 핵심 통신 점수가 있는지를 확인 해야 합니다. 

사용자에 게 새 기능을 알리기 위해 각 사이트에 표시 및 알림 이벤트와 포스터를 예약 하는 것이 좋습니다. 룸에서 "빠른 시작 가이드"를 만들 수도 있습니다. 다른 사용자가 장치를 빠르게 사용 하 고 시작 하는 데 도움을 주는 각 사이트에서 모임 리더를 찾는 것이 좋습니다.
