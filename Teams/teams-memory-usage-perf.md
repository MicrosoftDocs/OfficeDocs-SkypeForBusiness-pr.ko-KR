---
title: Microsoft Teams에서 메모리를 사용하는 방법
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Microsoft Teams 시스템 메모리 사용량과 데스크톱 애플리케이션과 웹 애플리케이션 간에 메모리 사용량이 동일한 이유에 대해 알아봅니다.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 0d55caf2a1642b28ccc63e3be1cf3eccc69bb260
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605677"
---
# <a name="how-microsoft-teams-uses-memory"></a>Microsoft Teams에서 메모리를 사용하는 방법

일부 Microsoft Teams 사용자에게는 Teams에서 메모리를 사용하는 방법에 대한 질문이 있습니다. 이 문서에서는 Teams에서 메모리를 사용하는 방법과 Teams 데스크톱 응용 프로그램(앱) 및 Teams 웹앱이 동일한 컴퓨터의 다른 앱과 워크로드가 메모리를 충분히 갖출 수 없도록 하는 이유를 설명합니다. Teams는 최신 웹 기술을 사용하도록 설계되었습니다. 이를 위해 Teams 데스크톱 클라이언트는 렌더링에 Chromium 사용하는 Electron에서 개발되었습니다. 이는 Edge 및 Chrome을 포함하여 오늘날 가장 인기 있는 많은 브라우저 뒤에 있는 동일한 렌더링 엔진입니다.

## <a name="how-teams-works"></a>Teams 작동 방식

Electron에서 설계된 Teams를 사용하면 개발 속도가 빨라지고 여러 운영 체제(Windows, Mac 및 Linux)에서 Teams 버전 간의 패리티도 유지됩니다. 이 패리티는 Electron 및 Chromium 모든 버전에서 유사한 코드 베이스를 유지 관리하기 때문에 가능합니다. 이 아키텍처의 또 다른 장점은 Teams 웹앱과 데스크톱 버전 간에 유사한 메모리 사용 프로필이 있다는 것입니다. 웹앱과 데스크톱 버전 모두 브라우저에서 메모리를 사용하는 방법과 비슷한 방식으로 메모리를 사용합니다. Electron에 대한 자세한 내용은 [해당 웹 사이트에서](https://electronjs.org/) 확인할 수 있습니다.

자세한 내용은 [Chrome 메모리의 Chromium 메모리 사용량](https://www.chromium.org/developers/memory-usage-backgrounder) 및 [주요 개념을](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) 참조하세요.

다음 이미지는 Windows용 Teams 데스크톱 앱 및 Teams 웹앱(이 예제에서는 Google Chrome에서 실행)의 병렬 메모리 사용량을 보여 줍니다.

![데스크톱 앱 및 웹앱에 대한 Teams 메모리 사용량입니다.](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Teams의 메모리 사용량

시스템 메모리와 관련하여 Teams의 *예상* 동작을 이해하고 실제로 문제가 있는 시스템 메모리 문제의 증상을 파악하는 것이 중요합니다.

### <a name="expected-memory-usage-by-teams"></a>Teams의 예상 메모리 사용량

Teams 데스크톱 앱 또는 Teams 웹앱을 실행하든 관계없이 Chromium 사용 가능한 시스템 메모리의 양을 감지하고 해당 메모리를 충분히 활용하여 렌더링 환경을 최적화합니다. 다른 앱 또는 서비스에 시스템 메모리가 필요한 경우 Chromium 해당 프로세스에 메모리를 포기합니다. Chromium 현재 실행 중인 다른 항목에 영향을 주지 않고 Teams 성능을 최적화하기 위해 Teams 메모리 사용량을 지속적으로 조정합니다.

이러한 방식으로 유사한 Chromium 워크로드는 사용 가능한 시스템 메모리 양에 따라 다양한 양의 메모리를 활용할 수 있습니다.

다음 그래프는 각각 사용 가능한 메모리 양이 서로 다른 4개의 개별 시스템에서 Teams의 메모리 사용량을 보여 줍니다. 각 시스템은 유사한 워크로드(동일한 앱 열기 및 실행)를 처리하고 있습니다.

![여러 시스템에서 Teams 메모리 사용량](media/teams-memory-usage.png)

컴퓨터에 더 많은 메모리가 있는 경우 Teams는 해당 메모리를 사용합니다. 메모리가 부족한 시스템에서 Teams는 더 적게 사용합니다.

### <a name="symptoms-of-system-memory-issues"></a>시스템 메모리 문제의 증상

컴퓨터에 다음 증상 중 하나 이상이 표시되면 심각한 시스템 메모리 문제가 발생할 수 있습니다.

- 여러 대규모 애플리케이션이 동시에 실행되는 경우 높은 메모리 사용
- 시스템 성능이 느리거나 애플리케이션이 중단됩니다.
- 모든 앱에서 전체 시스템 메모리 사용량이 90% 이상 지속되었습니다. 이 메모리 사용량으로 Teams는 다른 앱 및 워크로드에 메모리를 다시 제공해야 합니다. 90%의 지속적인 메모리 사용량은 Teams가 시스템에 메모리를 다시 제공하지 않음을 의미할 수 있으며 이는 문제를 나타냅니다.

다음 이미지는 시스템 메모리 사용량이 비정상적으로 높은 경우 작업 관리자의 보기 예제를 보여 줍니다.

![작업 관리자의 Teams 메모리 사용량 보기](media/teams-memory-high-mem-process-list.png)

![작업 관리자의 Teams 메모리 사용 그래프입니다.](media/teams-memory-high-mem-process-list2.png)
