---
title: Microsoft Teams 룸 계획
ms.author: dstrome
author: dstrome
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
description: 이 문서에서는 차세대 Skype 채팅방 시스템인 Microsoft Teams Room을 배포하기 위한 관련 계획 고려 사항을 설명하고 있습니다.
ms.openlocfilehash: ccc24aea1a45d2aa75c3b1a5de668b520483c2bd
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662473"
---
# <a name="plan-microsoft-teams-rooms"></a>Microsoft Teams 회의실 계획

이 문서에서는 전체 모임 및 회의실 전략의 일부로 Microsoft Teams 회의실을 계획, 전달 및 운영하는 종단 간 접근 방식을 소개합니다.

지원 기술 정보에 대한 링크와 함께 권장되는 방법 및 결정해야 하는 주요 결정에 대한 계획 정보는 아래에서 찾을 수 있습니다. 이미 완전히 배포된 경우에도 계획, 배포 및 관리 섹션을 검토하는 것이 좋습니다.

## <a name="overview-of-microsoft-teams-rooms"></a>Microsoft Teams 회의실 개요

Microsoft Teams 회의실은 HD 비디오, 오디오 및 콘텐츠 공유를 작은 안장 영역에서 대형 회의실까지 모든 크기의 모임에 제공하는 완벽한 모임 환경을 제공합니다.

![회의실 벽에 탑재된 본체, 마이크 및 대형 화면은 Microsoft Teams 회의실 설정 예제의 요소를 보여 주는 것입니다.](../media/room-systems-image1.png "회의실 벽에 탑재된 본체, 마이크 및 대형 화면은 Microsoft Teams 회의실 설정 예제의 요소를 보여 주는 것입니다.")

[Microsoft Teams 회의실](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 도움말은 Microsoft Teams 회의실에 대한 자세한 정보를 찾고 배포의 일부로 가치를 추가하는 방법에 대한 훌륭한 리소스입니다. 또한 이 개요 비디오를 [시청하는 것이 좋습니다.](https://youtu.be/tNey5KZVCl0) 

## <a name="microsoft-teams-rooms-components"></a>Microsoft Teams 회의실 구성 요소

Microsoft Teams 회의실에는 뛰어난 사용자 환경을 제공하는 다음과 같은 주요 구성 요소가 포함되어 있습니다.

- 터치 스크린 제어판
- Compute
- Microsoft Teams Rooms 응용 프로그램
- Dock/extender
- 주변 장치(카메라, 마이크, 스피커)
- 외부 화면(최대 2개)
- HDMI 입력

이러한 구성 요소를 여러 공급업체에서 미리 설치한 번들로 조달하거나 이 문서에 설명된 요구 사항에 따라 지원되는 구성 요소를 개별적으로 구입할 [수 있습니다.](requirements.md)

Surface Pro/dock 조합 외에도 터치 스크린 제어판, 컴퓨팅, 도크 및 주요 주변 장치가 통합된 Microsoft Teams 회의실을 구입할 수도 있습니다. 

일반적으로 번들 및 통합 단위에는 미리 설치된 소프트웨어가 포함되어 있는 반면 Surface Pro 시스템에 대해 지원되는 구성 요소를 개별적으로 구입하는 경우 소프트웨어를 설치해야 합니다. 지침은 디바이스에 소프트웨어를 설치하는 방법에 대한 이 [문서를 참조하세요.](rooms-scale.md) 

Microsoft Teams, 비즈니스용 Skype Online 또는 비즈니스용 Skype 하이브리드 또는 프레미스 배포를 사용하여 Microsoft Teams 회의실을 배포할 수 있습니다.  필요한 [라이선스에](rooms-licensing.md) 대한 자세한 내용은 Teams 회의실 라이선스 업데이트를 참조하세요.

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>조직에 Microsoft Teams 회의실을 배포하나요? </li><li>번들, 별도 구성 요소 또는 통합 단위로 Microsoft Teams 회의실 시스템을 어떻게 조달하나요?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계 | <ul><li>배포 전체에서 주요 활동을 진행할 사용자 식별</li><li>Microsoft Teams 회의실을 배포할 위치와 회의실 크기에 적합한 주변 장치를 배포하려는 위치를 이해하기 위해 현재 있는 회의실(및 설정 계획)을 검토합니다.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>배포 전체에서 주요 활동을 진행할 사용자 식별

아래 설명된 접근 방식을 사용하여 배포를 안내하고 조직에 필요한 대로 이러한 문서 전체에 제공된 샘플 출력을 사용자 지정합니다.

현재 사용하는 회의실을 이해하고 향후 가장 적합한 것을 구상하는 것으로 시작한 다음, 필요한 장비 선택 및 조달, 사이트 준비, 서비스 구성 및 배포, 변경 및 사용자 채택 관리, 운영 및 유지 관리 절차 개발을 진행합니다.

![먼저 사용자에게 가장 적합한 것을 이해하고 가장 적합한 것을 구상한 다음, 필요한 장비 선택 및 조달, 사이트 준비, 서비스 구성 및 배포, 변경 및 사용자 채택 관리, 운영 및 유지 관리 절차 개발을 진행합니다.](../media/room-systems-image2.png "먼저 사용자에게 가장 적합한 것을 이해하고 가장 적합한 것을 구상한 다음, 필요한 장비 선택 및 조달, 사이트 준비, 서비스 구성 및 배포, 변경 및 사용자 채택 관리, 운영 및 유지 관리 절차 개발을 진행합니다.")

여러 팀에서 이러한 활동을 조정해야 할 수 있습니다. 다루고자 하는 주요 활동에 대한 개관적인 보기와 일반적으로 회의실 시스템 배포 및 관리와 관련된 팀에 대한 제안을 제공하여 작업할 사용자 결정에 도움을 줄 수 있습니다.

| 작업                        | 작업을 수행한 사람           | 할당된 | 이 콘텐츠에 대한 링크 |
|----------------------------|----------------------------------------|-------------|-----------------------|
| 인벤토리 회의실            | 시설/AV 팀/IT 프로젝트 팀 |             | [방 인벤토리 및 기능 계획](#room-inventory-and-capability-planning)        |
| 계획 기능          | IT 프로젝트 팀                        |             | [방 인벤토리 및 기능 계획](#room-inventory-and-capability-planning)                       |
| 디바이스 선택           | IT 프로젝트 팀/AV 팀              |             | [디바이스 선택](#device-selection)                      |
| 조달                | IT 프로젝트 팀/AV 팀              |             | [조달](#procurement)                      |
| 사이트 준비             | 시설/AV 팀/IT 프로젝트 팀 |             | [사이트 준비](rooms-deploy.md#site-readiness)                      |
| 서비스 준비          | IT 프로젝트 팀                        |             | [서비스 준비](rooms-deploy.md#service-readiness)                      |
| 구성              | IT 프로젝트 팀                        |             | [구성 및 배포](rooms-deploy.md#configuration-and-deployment)                      |
| Deployment                 | 시설/AV 팀/IT 프로젝트 팀 |             | [배포 검사 목록](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| 채택                   | 시설/AV 팀/IT 프로젝트 팀 |             | [채택](#plan-for-adoption-and-change-management)                      |
| 유지 관리 및 운영 | AV 팀/IT 프로젝트 팀              |             | [관리 개요](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>방 인벤토리 및 기능 계획

첫 번째 단계는 조직의 기존 모임 및 회의실을 인벤토리에 인벤토리하여 환경, 회의실 크기, 레이아웃 및 용도를 이해하고, 향후 회의실에서 사용할 다양한 공동 작업 기능 등 범위 내 각 회의실이 원하는 기능을 식별하는 것입니다. 

각 기존 방에 장비 및 기능의 인벤토리를 만든 후 해당 방에 대한 요구 사항이 장치 선택 계획에 피드되어 풍부한 회의 솔루션을 만들 수 있습니다. 각 방에 필요한 모토(오디오, 비디오)는 방 크기 및 용도 외에도 각 방에 가장 적합한 솔루션을 결정하기 위해 중요한 역할을 합니다. 

검색의 일부로 방 음향 및 레이아웃을 고려하는 것이 중요합니다. 예를 들어 방의 의자가 카메라 보기를 차단하지 않는지 확인할 수 있습니다. 방에 과도한 에코 또는 시동이 울리거나 시동이 오는 공조가 없는지, 화면 및 Microsoft Teams 회의실에 충분한 전원이 있는지를 확인해야 합니다. AV(오디오-시각) 팀 또는 파트너가 조언할 수 있는 요인이 많이 있습니다. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>이 배포의 범위에 있는 회의실은 무엇입니까?</li><li>배포 범위에 있는 사이트는 무엇입니까?</li><li>회의실 인벤토리를 진행할 사람이 누구인가요?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>범위에서 회의실을 검토하고 Microsoft Teams 회의실 구성을 정의합니다.</li></ul>|

_샘플 모임/회의실 인벤토리_

| 사이트  | 방 이름 | 방 유형 | 사람 수  | 범위에 있나요? | 현재 방 기능       | 향후 방 기능     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| London HQ | Curie         | 중형        | 6 &ndash; 12                  | 예          | 스피커폰                        | 1 화면, 오디오 및 비디오 및 프레젠테이션<br>PSTN 액세스 |
| 시드니 HQ | Hill          | 대형         | 12 &ndash; 16                 | 예          | 레거시 AV 장치, 1개 화면 및 카메라 | 2개 화면, 오디오 및 비디오 및 프레젠테이션<br>PSTN 액세스 |

## <a name="device-selection"></a>디바이스 선택 

방에 대해 원하는 향후 기능에 따라 각 방에 가장 적합한 Microsoft Teams 회의실 솔루션을 평가합니다. 방 크기 및 레이아웃에 따라 가장 적합한 AV 주변 장치를 결정할 수 있습니다. 

회의실 유형 및 크기에 따라 시스템 및 주변 장치 유형에 대한 지침은 Microsoft Teams 회의실 요구 사항 [문서를 참조하세요.](requirements.md) 

원하는 공급업체에 따라 요구 사항 문서에 제공된 정보를 사용하여 Microsoft Teams 회의실 및 회의실 유형별로 지원되는 주변 장치 구성을 정의하고 배포를 위한 템플릿으로 사용합니다. 

**Pro 팁** – 일부 공간 유형은 배포에 적용되지 않을 수 있습니다.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>인벤토리에서 배포 범위에 있는 회의실 유형은 무엇입니까?</li><li>각 방 유형에 어떤 시스템을 배포할까요?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>선택한 시스템에 대한 주요 운영 자료를 수집하고 조달 팀에 참여합니다.</li></ul>|

_조직에 대한 샘플 Microsoft Teams Rooms 배포 템플릿_

| **방 유형/크기** | **사람 수**  | **Microsoft Teams 회의실 시스템** | **주변 장치**  | **디스플레이** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| 포커스 10' by 9'      | 2 &ndash; 4                   |                                  |                         |                 |
| Small 16'by 16'     | 4 &ndash; 6                   |                                  |                         |                 |
| Medium 18'by 20'    | 6 &ndash; 12                  |                                  |                         |                 |
| Large 15' by 32'     | 12 &ndash; 16                 |                                  |                         |                 |

**Pro 팁 –** 이제 선택한 Microsoft Teams 회의실 솔루션에 대한 정보 수집을 시작할 수 있습니다.

## <a name="procurement"></a>조달 

디바이스 파트너를 통해 선택한 시스템을 번들 또는 통합 솔루션으로 조달할 수 있습니다. 또한 Surface Pro 장치 및 지원되는 기존 _AV_ 주변 장치를 사용하여 파트너 장치 도크를 획득하고 자체 Microsoft Teams Rooms 솔루션을 준비할 수도 있습니다. 

요구 사항 문서에 나열된 여러 파트너로부터 Microsoft Teams 회의실을 획득할 [수 있습니다.](requirements.md) 이러한 솔루션 및 조달 옵션에 대한 자세한 내용은 파트너의 웹 사이트를 방문하세요. 

배포 규모 및 접근 방식에 따라 Microsoft Teams 회의실 및 지원되는 주변 장치를 초기 구성 및 할당을 위한 중앙 위치에 배송하기로 결정할 수 있습니다. 이는 여러 사이트에 걸쳐 준비된 롤아웃에 좋은 접근 방식일 수 있습니다. 또는 번들을 사이트에 직접 배송할 수도 있습니다. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>구성 요소를 사이트 또는 스테이징 시설로 직접 배송하나요?</li><li>스테이징 시설은 누가 관리하나요(사용하기로 결정한 경우)?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>작업에 대한 계획입니다.</li><li>채택 및 변경 관리를 계획합니다.</li></ul>|

## <a name="plan-for-operations"></a>작업 계획 

조직은 지속적인 모니터링, 관리 및 관리 작업을 실행해야 하며 배포 초기에 이러한 작업을 수행할 사용자에 동의하는 것이 중요합니다. 

대부분의 조직에는 회의실 및 장치를 관리하는 AV 팀 또는 파트너가 있습니다. 이 팀은 성능을 모니터링하고 소프트웨어 업데이트 및 핫픽스를 배포하기 위해 앞으로 Microsoft Teams 회의실 장치를 관리하는 사용자에 동의해야 합니다. 

Microsoft Teams와 관련된 Rooms֪ 라우팅할 기술 지원팀 큐를 고려하고 지원팀 팀에 FAQ를 제공하면 Microsoft Teams 회의실을 사용하는 방법과 해당 팀이 취할 수 있는 주요 문제 해결 단계를 더 잘 이해할 수 있습니다. 이 FAQ의 좋은 시작점은 사용자 도움말 및 [알려진](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) [문제입니다.](known-issues.md)

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>Microsoft Teams 회의실을 관리할 사용자 결정</li><li>Microsoft Teams 회의실 관련 호출을 라우팅할 기술 지원팀 큐를 결정할 수 있습니다.</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>계정을 호스트할 준비를 합니다. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>채택 및 변경 관리 계획

Microsoft Teams 회의실 시스템은 사용자에게 새로운 기능을 도입합니다. 이는 사용자에 대한 변경이 되도록 인식하는 것이 중요합니다. 캠페인에서 새 시스템이 사용자에게 부여할 이점과 잠재 고객이 팀과 논의하는 데 사용할 수 있는 주요 이점을 식별해야 합니다. 

각 사이트에서 이벤트 및 포스터 드롭을 예약하여 사용자에게 새로운 기능을 알릴 수 있습니다. 방에서 "빠른 시작 가이드"를 만들 수도 있습니다. 다른 사람이 디바이스 사용을 빠르게 시작하고 시작하는 데 도움을 줄 수 있는 각 사이트에서 모임 챔피언을 찾는 것이 좋습니다.
