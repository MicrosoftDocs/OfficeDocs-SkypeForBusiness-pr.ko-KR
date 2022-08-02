---
title: 읽기 진행률 권장 사항에 대한 인사이트 이해
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 읽기 진행률에서 Insights 데이터를 사용하여 학생의 읽기 능력을 향상시키는 방법을 알아봅니다.
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30a98c9ccda13635a6c3fccaae41e8869b8cfce5
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67157886"
---
# <a name="understand-insights-for-reading-progress-recommendations"></a>읽기 진행률 권장 사항에 대한 인사이트 이해

이 문서는 Insights 데이터를 읽기 진행률 권장 사항에 사용하는 방법을 이해하려는 교육 IT 관리자를 위한 것입니다.

Insights를 사용하면 교육자가 큰 소리로 읽는 학생을 기록하고 오류를 자동으로 감지하는 도구인 읽기 진행률을 사용하여 학생의 읽기 유창성을 추적할 수 있습니다.

읽기 진행률에서는 다음과 같은 유형의 읽기 챌린지 할당을 제공합니다.

- **상황별 단어**: 학생들이 과거 읽기 진행 과제에서 잘못 발음한 단어에 따라 권장되는 연습 단어입니다.
- **상관 관계가 있는 단어**: 읽기 챌린지 유형이 동일한 학생에게 공통적인 실수에 따라 권장되는 연습 단어입니다.

읽기 진행률에 Insights를 사용하는 방법에 대한 교육자 지침은 [Insights를 사용하여 읽기 진행률 과제 만들기를 참조하세요](https://support.microsoft.com/topic/c2f8f4c0-69d5-4302-b3a5-ee4dfb7a8ffe).

## <a name="how-does-microsoft-recommend-correlated-words"></a>상관 관계가 있는 단어는 어떻게 권장하나요?

상관 관계가 있는 단어는 비슷한 읽기 패턴을 공유하는 다른 학생에게 어려운 것으로 확인된 Insights for Education의 권장되는 개인 설정된 단어입니다.

상호 관련된 단어는 **공동 작업 필터링** 이라는 기계 학습 기술을 기반으로 합니다.

- Insights는 지리적 영역과 언어를 공유하는 수업에서 학생의 읽기 데이터를 분석하여 학생들에게 어려운 단어 클러스터를 식별합니다.

- 어려운 단어 집합을 감안할 때 Insights는 유사한 클러스터를 식별하고 이를 사용하여 대상 연습을 위해 학생들에게 다른 단어를 추천합니다.

## <a name="does-microsoft-keep-students-data-private-and-secure"></a>Microsoft는 학생의 데이터를 비공개로 안전하게 유지하나요?

Microsoft는 책임감 있고 윤리적으로 데이터를 사용하기 위해 최선을 다하고 있습니다.

이 기능을 빌드하기 위해 수행된 몇 가지 조치는 다음과 같습니다.

- 학생 데이터 분석은 눈에 보이지 않는 방식으로 빌드됩니다. 즉, Microsoft는 분석 결과에만 학생의 읽기 데이터에 액세스할 수 없습니다.

- 테넌트 관리자는 [고급 유추 토글을](class-insights.md#turn-on-and-off-advanced-inferences-in-insights) 해제하여 데이터 분석 프로세스에서 옵트아웃할 수 있습니다.

- 부적절한 단어는 **상관 관계 단어** 권장 사항 목록에서 필터링됩니다. 이 작업은 데이터 과학 기술과 알려진 문제가 있는 단어의 차단을 조합하여 수행됩니다. 그러나 이 프로세스는 오류 증명이 아닙니다. 교육자는 권장 사항을 검토해야 합니다.

## <a name="what-are-the-limitations-of-insights-word-recommendations"></a>Insights의 단어 권장 사항의 제한 사항은 무엇인가요?

- 읽기 진행률에 대한 Word 권장 사항은 현재 [이러한 언어](https://support.microsoft.com/topic/getting-started-with-reading-progress-in-teams-7617c11c-d685-4cb7-8b75-3917b297c407#ID0EDD=Supported_Languages)로 지원됩니다.

- 상관 관계가 있는 단어는 읽기 진행 과제에 제출한 학생 5명 이상이 있는 수업에서만 제공됩니다.

- 인사이트는 유사하지만 동일하지 않은 실수 패턴을 가진 학생이 없는 경우 새 단어를 권장하지 않을 수 있습니다.
