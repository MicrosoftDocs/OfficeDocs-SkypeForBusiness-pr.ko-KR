---
title: EDU용 Microsoft Teams 낮은 대역폭 지침
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: 낮은 대역폭과 관련된 모임 및 비디오 문제를 해결하는 데 유용한 EDU용 Microsoft Teams 문서입니다. 부모, 교사 또는 IT 관리자는 Teams 사용 환경을 개선할 수 있는 방안이 있습니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17520645f23500550c6bc991c9d25ad2f72b2b6e
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598427"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>EDU용 Teams의 낮은 대역폭 상황을 위한 지원

성능에 영향을 줄 수 있는 Microsoft Teams를 이용한 작업에서는 다양한 네트워크 요소가 있습니다. 낮은 대역폭은 통제권이 전혀 없는 것처럼 느낄 수 있는 경우 중 하나입니다. 다음과 같은 상황을 고려해 보세요.

- 학교용 저속 인터넷 연결
- 한 명 이상의 학생을 위한 저속 인터넷 연결
- 해당 영역의 네트워크 사용률로 인해 대역폭이 낮게 유지되는 하루 중 시간
- 학교 및 학생 입장에서 지역적인 것은 아니지만 성능에 영향을 미칠 수 있는 중단 상황으로 인한 낮은 대역폭 기간
- 낮은 대역폭 문제로 오인되는 대역폭 이외 문제(예: 하드웨어 문제)

이 문서에서는 낮은 대역폭 문제가 발생하는 경우에는 다양한 Teams 작업에 권장되는 모범 사례를 제공합니다.

> [!IMPORTANT]
> 낮은 대역폭 문제 외에, 리소스 문제가 디바이스에 있을 수 있으므로 [Microsoft Teams에서 메모리를 사용하는 방법](teams-memory-usage-perf.md)에 대한 정보도 제공됩니다. Microsoft Teams에 대한 네트워크 지침을 원할 경우 [Microsoft Teams에 대한 조직의 네트워크 준비](prepare-network.md)를 검토하세요.

## <a name="resolving-low-bandwidth-issues-for-admins"></a>IT 관리자의 낮은 대역폭 문제 해결

IT 관리자로서 기억해야 할 중요한 점은 문제를 신속하게 해결할 수 있는 광범위한 저대역폭 문제에 대한 솔루션이 있지만 솔루션을 신중하게 고려해야 한다는 것입니다. 일부 문제는 교사 또는 학생/부모 수준에서 좀 더 좁게 집중하여 해결할 수 있습니다.

간단히 말해서, 방대한 학생 그룹을 대상으로 낮은 대역폭 문제가 발생하는 경우 IT 관리자가 조치를 취해야 하며, 학생/교사 수준에서 취하는 조치는 도움이 되지 않을 수도 있다는 것입니다.

> [!NOTE]
> 투자 수익을 거두는 데 시간이 오래 걸리는 경우 [QoE(체감 품질) 검토 가이드](quality-of-experience-review-guide.md)(EDU에 국한된 내용은 아니지만 유용할 수 있음)를 읽어보면 도움이 될 수 있습니다. 이 가이드를 통해 경험 있는 IT 관리자는 교사와 학생을 위한 환경을 심도 깊이 알아볼 수 있습니다.

### <a name="meetings-and-video"></a>모임 및 비디오

낮은 대역폭 문제를 해결해야 하는 기본적인 측면은 모임이며, 특히 화상 모임에서 이러한 문제가 있는지 파악해야 합니다. IT 관리자는 교육 환경에서 최고의 모임 환경을 구축하는 것과 관련하여 학생 또는 교육자가 보고한 문제를 처리할 때 아래의 조치를 고려해야 합니다.

#### <a name="meeting-policies"></a>모임 정책

모임과 관련해서 낮은 대역폭이 가장 우려되는 영역 중 하나는 비디오와 관련이 있습니다. Teams에서 자동으로 감지된 대역폭으로 확장할 수 있을 뿐만 아니라 IT 관리자로서 정책 옵션을 구성자 및/또는 사용자 수준별로 설정할 수 있습니다. 이러한 옵션을 사용하면 주어진 시간에 작업해야 하는 대역폭을 고려하여 모든 사용자에게 최상의 환경을 제공할 수 있습니다.

정책에 따라 설정할 수 있는 항목은 다음과 같습니다.

- 누구도 사용할 수 없게 비디오를 모두 사용하지 않도록 설정
- 미디어 비트 전송률(이 설정은 사용자별로 설정됨)

옵션에 대해 자세히 알아보고 모임 및 비디오와 관련해서 설정해야 하는 정책에 대한 구체적인 내용을 보려면 [Teams의 모임 정책 설정: 오디오 및 비디오](meeting-policies-audio-and-video.md)를 참조하세요.

#### <a name="screen-sharing-policies"></a>화면 공유 정책

경우에 따라 교사는 담당 과목에 관련된 응용 프로그램으로 공유를 제한해야 하는 경우 학생들과 전체 화면을 공유할 수 있습니다. 교사가 개별적으로 해당 설정을 선택하는 것보다 더 바람직한 방법이 있는 경우, 정책을 통해 이 설정을 지정할 수 있습니다.

정책 설정을 통해 화면 공유를 제한하는 경우 수행할 수 있는 작업에 대한 자세한 내용은 [Teams의 모임 정책 설정: 오디오 및 비디오](meeting-policies-audio-and-video.md)를 참조하세요.

#### <a name="dial-in-number-for-meetings"></a>모임에 대한 전화 접속 연결 번호

일부 학생의 경우 일부 교실 세션에 전화 접속을 시도하는 것이 더 쉬울 수 있습니다. Teams 모임을 위한 전화 접속 번호를 제공할 수 있으므로 문제가 있는 학생은 화상 모임에 참석하는 대신 전화로 연결할 수 있습니다.

이에 대한 자세한 내용은 [Microsoft Teams에서 초대에 전화 번호를 포함하도록 설정](set-the-phone-numbers-included-on-invites-in-teams.md)을 읽어보세요.

## <a name="low-bandwidth-scenarios-as-an-educator"></a>교사 대상의 낮은 대역폭 시나리오

교사는 낮은 대역폭 문제를 해결하기 위해 조치를 취해야 한다고 생각할 수 있으며 다음과 같은 경우 IT 관리자가 이러한 조치를 위하는 것이 적절할 수 있습니다.

- 문제가 간헐적이거나 비교적 일시적으로 나타나는 경우
- 문제가 예상되는 특정 시간이 있거나 낮은 대역폭 기간을 어느 정도 예측할 수 있는 경우

이러한 경우에는 몇 가지 작업을 수행할 수 있습니다.

자세한 내용은 [대역폭이 낮은 경우 수업에 Teams 사용](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)을 참조하세요.

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>부모 또는 학생 대상의 낮은 대역폭 시나리오

경우에 따라 대역폭 문제가 학생 측면에서 발생할 수 있는 경우(예: 다수의 학생은 문제 없이 비디오를 볼 수 있지만, 소수의 학생에게는 어려움이 있는 경우) 교사와 사전에 논의해야 합니다.

많은 부모가 이러한 문제를 해결할 수 있을 거라고 예상하는 것은 타당하지 않습니다. 낮은 대역폭 문제를 학생 또는 부모는 해결하지 못할 수 있습니다(가정에서 높은 대역폭에 액세스할 수 없거나, 인접한 영역에 많은 사람들이 대역폭을 사용하거나 수행할 수 있는 작업에 영향을 미치거나, 인터넷이 불안정할 수 있음).

[대역폭이 낮은 경우 수업에 Teams 사용](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) 문서에서 부모와 학생을 위한 지침을 제공하고 있으며, 문제가 있는 경우 이러한 권장 사항을 검토하고 시도해볼 수 있습니다.