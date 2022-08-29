---
title: Teams에 대한 낮은 대역폭 시나리오 문제 해결
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Teams의 낮은 대역폭 문제와 관련된 모임 및 비디오 문제에 대한 도움을 받으세요. 부모, 교육자 또는 IT 관리 관계없이 Teams 환경을 개선할 수 있는 옵션이 있습니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f60095f20d62ed14b19d7c23493553efc39b872
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426815"
---
# <a name="troubleshoot-low-bandwidth-scenarios-for-teams"></a>Teams에 대한 낮은 대역폭 시나리오 문제 해결

이 문서에서는 TEAMS에서 낮은 대역폭 문제를 처리할 때 IT 관리자에게 모범 사례를 제공합니다.

수많은 네트워크 요소는 Microsoft Teams로 작업할 때 성능에 영향을 줄 수 있습니다.

- 학교에 대한 고속 인터넷 연결.
- 하나 이상의 학생에 대한 고속 인터넷 연결.
- 해당 영역의 네트워크 사용률로 인해 대역폭이 낮게 유지되는 하루 중 시간
- 중단은 학교 또는 학생에게 국한되지 않지만 성능에 영향을 미칩니다.
- 낮은 대역폭 문제를 일으키는 하드웨어 관련 문제입니다.

> [!IMPORTANT]
> Microsoft Teams에서 디바이스의 리소스 제한에 [메모리를 사용하는 방법을](teams-memory-usage-perf.md) 읽어 보세요.
>
>Teams 네트워크 지침은 [Microsoft Teams에 대한 조직의 네트워크 준비를 참조하세요](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-it-admins"></a>IT 관리자에 대한 낮은 대역폭 문제 해결

일부 문제는 개별 사용자 수준에서 좁은 포커스로만 해결할 수 있습니다.

많은 사용자에 대해 대역폭 문제가 발생하거나 사용자 수준에서 수행된 작업이 유용하지 않은 경우 학교 차원의 작업이 다음 단계입니다.

> [!NOTE]
> [또한 경험의 품질 검토 가이드](quality-of-experience-review-guide.md)를 읽을 수 있습니다. EDU 관련 정보는 아니지만 중요한 정보를 가지고 있습니다.

### <a name="meetings-and-video"></a>모임 및 비디오

낮은 네트워크 대역폭과 관련된 모임 문제를 처리할 때 아래 작업을 고려합니다.

#### <a name="meeting-video-policies"></a>모임 비디오 정책

Teams는 자동으로 모임 품질을 사용자의 검색된 대역폭으로 조정합니다. 그러나 대역폭을 유지하기 위해 추가 제한을 설정할 수 있습니다.

정책을 통해 설정할 수 있는 몇 가지 제한 사항은 다음과 같습니다.

- 아무도 비디오를 사용할 수 없도록 비디오를 완전히 끕니다.
- 사용자별로 설정된 미디어 비트 전송률 제한

모임 및 비디오에 대해 설정해야 하는 추가 정책을 보려면 [Teams: 오디오 및 비디오에서 모임 정책 설정을](meeting-policies-audio-and-video.md) 읽어보세요.

#### <a name="screen-sharing-policies"></a>화면 공유 정책

Teams에서 사용자는 전체 화면 또는 개별 창을 공유할 수 있습니다.

전체 화면을 공유하려면 창을 공유하는 것보다 더 많은 대역폭을 사용합니다.

- 사용자가 정책을 통해 전체 화면을 공유하지 못하도록 제한합니다.
- 교육자는 전체 화면이 아닌 애플리케이션만 공유하도록 지시합니다.

[Teams: 오디오 및 비디오의 모임 정책 설정에서](meeting-policies-audio-and-video.md) 화면 공유 정책에 대해 알아봅니다.

#### <a name="dial-in-number-for-meetings"></a>모임에 대한 전화 접속 연결 번호

일부 학생이 교실 세션에 전화하는 것이 더 쉬울 수 있습니다.

- 비디오 모임에 참석하는 대신 Teams 모임에 대한 전화 접속 번호를 제공합니다.

자세한 내용은 [Microsoft Teams의 초대에 포함된 전화 번호 설정을 참조하세요](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>교사 대상의 낮은 대역폭 시나리오

교육자를 통해 대역폭 문제를 해결하는 것이 다음과 같은 상황에서 IT 작업보다 더 나은 선택이 될 수 있습니다.

- 문제는 간헐적입니다.
- 문제가 있을 것으로 예상할 수 있는 특정 시간이 있습니다.

교육자에서 대역폭 문제를 해결하기 위해 수행할 수 있는 단계는 [대역폭이 낮은 경우 학교 작업에 Teams를 사용](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)하세요.

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>부모 또는 학생 대상의 낮은 대역폭 시나리오

때로는 대역폭 문제가 학생의 편에 있습니다.

- 그들의 집은 높은 대역폭에 액세스 할 수 없습니다.
- 그들은 또한 대역폭을 소비 하는 그들의 직접 지역에 많은 사람들이 있을 수 있습니다.
- 인터넷 불안정이 있을 수 있습니다.

대역폭이 학부모와 학생 [을 위한 낮은 문서인 경우 학교 업무용 Teams 사용에](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) 대한 지침을 정리했습니다.
