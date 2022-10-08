---
title: 모든 참가자를 위한 포괄적인 Teams 모임 환경 만들기
ms.author: dstrome
author: dstrome
f1.keywords:
- Teams hybrid
- remote work
- Teams meetings
manager: serdars
audience: ITPro
description: Teams를 사용하여 하이브리드 작업 인력에 대한 포괄적인 모임 환경을 만드는 방법을 알아봅니다.
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
ms.collection:
- m365solution-teamshybrid
- m365solution-scenario
ms.custom: ''
keywords: ''
ms.openlocfilehash: 7c9083242ea08e36b31f97abfbf3ff895fca549f
ms.sourcegitcommit: 1be178dc3b34575e1914e629f004f897c02e0097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68138591"
---
# <a name="create-an-inclusive-teams-meeting-experience-for-all-participants"></a>모든 참가자를 위한 포괄적인 Teams 모임 환경 만들기

Microsoft Teams 모임은 사람들이 모여 아이디어를 교환하고 어려운 문제를 해결하는 장소입니다. 직장 환경이 크게 변화하고 있는 시대에는 사람들을 하나로 모으고 효과적인 모임을 가능하게 하는 것이 어려울 수 있습니다. 이 솔루션은 Microsoft Teams, Teams 룸 장치, 회의실 디자인, 모임 원칙 및 비즈니스 사례를 결합하여 포괄적인 모임 환경을 만드는 방법을 보여 줍니다. 포용적 환경을 사용하면 회의실에 있든, 원격인지, 장애가 있든 관계없이 모든 받는 사람 간에 통신 및 공동 작업을 수행할 수 있습니다.

Microsoft Teams는 Microsoft 전체에서 하이브리드 작업의 중심입니다. Teams, Microsoft 365, Azure 및 기타 Microsoft 제품과 조직 전체에서 하이브리드 작업 사고 방식을 통합하는 방법을 보려면 [Microsoft 하이브리드 작업 센터를](https://www.microsoft.com/hybridwork/) 방문하세요.

이 짧은 비디오에서는 하이브리드 모임에 대한 Microsoft의 비전을 Teams 룸 공유합니다. 현재 앞줄과 같은 많은 기능을 사용할 수 있으며 이 솔루션에서 설명합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEB5U]
>

하이브리드 작업 환경을 지원하도록 인프라를 준비하는 방법에 대한 자세한 내용은 [Microsoft 365를 사용하여 하이브리드 작업을 위한 인프라 설정을 참조하세요](/microsoft-365/solutions/empower-people-to-work-remotely).

Teams 모임 환경 설계 및 설정을 시작하기 전에 [Teams 하이브리드 모임 원칙을 확인하세요](hybrid-meetings-principles.md). 이러한 원칙을 사용하여 현재 상태나 위치에 관계없이 모든 참가자가 동등하게 참여할 수 있는 포괄적인 모임 환경을 만들 수 있습니다.

## <a name="audiences"></a>관객

이 솔루션의 단계를 수행해야 하는 세 가지 다른 사용자 그룹이 있습니다. 단계를 수행해야 하는 그룹을 확인하려면 다음 문서에서 다음 식별자를 찾습니다.


|식별자  |그룹 책임  |
|---------|---------|
|:::image type="content" source="media/hybrid-audience-audiovisual-small.png" alt-text="오디오 시각적 개체 대상 그룹" border="false":::    | 오디오 시각적 개체 그룹: <ul><li> 모임 공간에서 카메라, 스피커, 마이크 및 디스플레이를 가져오고 설정하고 구성합니다.</li><li>배포 후 모임 참가자의 지원 요청에 응답합니다.        |
|:::image type="content" source="media/hybrid-audience-facilities-small.png" alt-text="시설 대상 그룹" border="false":::     | 시설 그룹: <ul><li> 필요한 경우 오디오 시각적 개체 그룹과 협의하여 결정된 사양으로 모임 공간을 구성하거나 수정합니다.</li><li> 테이블, 의자, 화이트보드 및 프로젝션 화면과 같은 가구를 가져오고 설정합니다.</li><li>다양한 Teams 룸 구성 요소 간에 케이블 연결을 실행하고 네트워크 및 오디오 시각적 포트를 설치합니다.</li><li>모든 Teams 룸 구성 요소에 대한 전원 지점을 설치합니다.</li></ul>       |
|:::image type="content" source="media/hybrid-audience-itpro-small.png" alt-text="IT 전문가 대상 그룹" border="false":::     | IT 전문가 그룹: <ul><li>회사 또는 부서 리더와 협의하여 기능 요구 사항과 함께 만들 모임 공간 유형을 결정합니다.</li><li>오디오 시각적 개체 그룹과 협의하여 모임 공간에서 사용할 Teams 룸 구성 요소를 선택하고 가져옵니다.</li><li>Teams 및 Teams 룸 기능, 원칙 및 모범 사례를 전도합니다.</li><li>Teams 및 Teams 룸 기능 및 정책을 구성합니다.</li><li>배포 후 Teams 및 Teams 룸 상태를 관리하고 모니터링합니다.</ul>        | 

다음 섹션에서는 이 시나리오의 주요 단계를 간략하게 설명합니다.

## <a name="step-1---get-familiar-with-teams-meeting-features"></a>1단계 - Teams 모임 기능 숙지

이 단계는 모임을 보다 포괄적이고 효과적으로 만드는 데 도움이 되는 Teams에서 사용할 수 있는 기능을 이해하는 데 도움이 됩니다.

## <a name="step-2---evangelize-meeting-best-practices"></a>2단계 - 모임 모범 사례 전파

과거의 모임은 일반적으로 원격 참가자가 회의 전화를 통해 주기적으로 전화하는 회의실에서 열렸습니다. 대화는 주로 원격 참가자가 수신 대기하는 방에있는 사람들 사이에 있었습니다. 모임이 온라인인 경우 콘텐츠가 원격 참가자와 공유될 수 있지만, 여전히 회의실에 있는 사람들이 토론을 많이 지배했습니다. 원격 참가자와 객실 내 참가자 간에 상당한 불균형이 있었습니다.

모임의 평등과 포용성은 위치나 능력에 관계없이 모든 참가자가 모임에 참여할 수 있도록 하는 것을 의미합니다. 이렇게 하려면 이끌이, 발표자, 원격 참가자 또는 회의실에 있는 모든 참가자가 "모임에 참석"하고 다른 사용자와 상호 작용하는 방법을 알고 있어야 합니다. 이 단계에서는 이러한 각 그룹에 대한 모범 사례를 제공하여 더 나은 참가자가 될 수 있도록 지원합니다.

## <a name="step-3---design-or-enhance-a-meeting-space"></a>3단계 - 모임 공간 디자인 또는 향상

새 모임 공간을 만들거나 기존 모임 공간을 개선하려고 할 수 있습니다. 이 단계는 약 6-10명의 회의실 내 참가자와 원격 참가자가 있는 모임을 지원하는 모임 공간을 설계하는 데 도움이 됩니다. 어떤 가구가 가장 좋은지, 참가자와 사용하려는 장치를 지원하기 위해 배치해야 하는 위치와 같은 것들.

## <a name="step-4---select-devices-for-your-space"></a>4단계 - 공간에 대한 디바이스 선택

사용 가능한 옵션으로 인해 공간에 적합한 디바이스를 선택하는 것이 약간 어려울 수 있습니다. 이 단계에서는 공간 및 참가자의 요구 사항에 맞게 적합한 디바이스를 선택하는 과정을 안내합니다.

## <a name="step-5---build-your-meeting-space"></a>5단계 - 모임 공간 빌드

공간을 설계하고 디바이스를 선택한 후에는 모든 항목을 함께 배치할 차례입니다. 이 단계는 사용자와 참가자에게 훌륭한 모임 환경을 제공하기 위해 장치와 가구를 배치할 위치를 결정하는 데 도움이 됩니다.

## <a name="step-6---set-up-your-devices"></a>6단계 - 디바이스 설정

공간을 빌드한 후에는 디바이스를 설정해야 합니다. 이 단계는 디바이스를 구성하고 첫 번째 모임을 위한 공간을 준비하는 데 도움이 됩니다.

## <a name="step-7---manage-and-monitor-your-space-and-its-devices"></a>7단계 - 공간 및 해당 디바이스 관리 및 모니터링

모든 것이 설정되면 모임 공간 및 해당 디바이스를 사용하는 방법에 대한 정책을 설정하고 디바이스 상태 및 모임 환경을 계속 유지할 수 있도록 모니터링을 설정해야 합니다. 이 단계는 모임 및 디바이스 정책을 구성하는 데 도움이 되며 Teams 모니터링 도구를 사용하여 통화 품질을 모니터링하는 방법을 보여 줍니다.

> [!div class="nextstepaction"]
> [다음 단계](hybrid-meetings-principles.md)
