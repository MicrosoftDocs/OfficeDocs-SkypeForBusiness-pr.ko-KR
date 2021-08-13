---
title: Microsoft Teams에서 메모리를 사용하는 방법
author: msdmaguire
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 시스템 Microsoft Teams 사용량 및 메모리 사용량이 데스크톱 애플리케이션과 웹 애플리케이션 간에 동일한 이유에 대해 자세히 알아보습니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 84a6b7fa894ead7d0504c768adc2eedc47b20f3b88efae88c9fd1fbdc9c7119f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296495"
---
# <a name="how-microsoft-teams-uses-memory"></a>Microsoft Teams에서 메모리를 사용하는 방법

일부 Microsoft Teams 사용자가 메모리를 사용하는 방법에 Teams 있습니다. 이 문서에서는 메모리가 Teams 방법을 설명하고, Teams 데스크톱 애플리케이션(앱) 및 Teams 웹앱이 동일한 컴퓨터의 다른 앱 및 워크로드가 최적으로 실행되지 않도록 방지하지 않는 이유를 설명합니다. Teams 웹 기술을 사용할 수 있도록 디자인되어 있습니다. 이를 위해 Teams 데스크톱 클라이언트는 전자에서 개발되어 렌더링에 Chromium 있습니다. 이 엔진은 Edge 및 Chrome을 포함하여 오늘날 가장 인기 있는 많은 브라우저 뒤에 있는 동일한 렌더링 엔진입니다.

## <a name="how-teams-works"></a>작동 Teams 방법

Teams 설계되어 더 빠르게 개발할 수 있으며, 다른 운영 체제(Teams, Mac 및 Linux)Windows 버전 간에 패리티를 유지 관리합니다. 이 패리티는 전자 및 Chromium 모든 버전에서 유사한 코드 기반을 유지 관리하기 때문에 가능합니다. 이 아키텍처의 또 다른 장점은 웹앱과 데스크톱 버전 간에 비슷한 Teams 프로필이 있습니다. 웹앱과 데스크톱 버전 모두 브라우저에서 사용하는 방식과 유사한 방식으로 메모리를 사용합니다. Electron에 대한 자세한 내용은 해당 웹 사이트에서 [사용할 수 있습니다.](https://electronjs.org/)

자세한 [Chromium](https://www.chromium.org/developers/memory-usage-backgrounder) Chrome [Memory의](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) 메모리 사용량 및 주요 개념을 참조하세요.

다음 이미지는 웹용 Teams 데스크톱 앱 및 Windows 웹앱의 Teams 메모리 사용량을 나란히 보여 줍니다(이 예제에서는 Google Chrome에서 실행).

![Teams 앱 및 웹앱에 대한 메모리 사용 현황](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>메모리 사용 Teams

시스템 메모리와 관련해 Teams 시스템 메모리 문제의 증상을 파악하는 것이 중요합니다. 

### <a name="expected-memory-usage-by-teams"></a>예상 메모리 사용량 Teams

데스크톱 앱 또는 Teams 웹앱을 Teams, Chromium 얼마나 많은 시스템 메모리를 사용할 수 있는지를 감지하고 해당 메모리를 충분히 활용하여 렌더링 환경을 최적화합니다. 다른 앱 또는 서비스에 시스템 메모리가 필요한 Chromium 프로세스에 메모리를 제공합니다. Chromium 다른 Teams 영향을주지 않고도 성능을 최적화하기 위해 Teams 메모리 사용량을 줄입니다.

이러한 방식으로 유사한 Chromium 사용할 수 있는 시스템 메모리의 양에 따라 다양한 양의 메모리를 활용할 수 있습니다.

다음 그래프는 각각 사용 가능한 Teams 서로 다른 4개의 개별 시스템에서 메모리 사용량을 보여줍니다. 각 시스템은 비슷한 워크로드를 처리하고 있습니다(열고 실행되는 동일한 앱).

![Teams 메모리 사용 현황](media/teams-memory-usage.png)

컴퓨터에 메모리가 더 많은 경우 Teams 메모리를 사용합니다. 메모리가 부족한 시스템에서는 Teams 덜 사용합니다.

### <a name="symptoms-of-system-memory-issues"></a>시스템 메모리 문제의 증상

컴퓨터에 다음 증상 중 하나 이상이 표시될 경우 심각한 시스템 메모리 문제가 있을 수 있습니다.

- 여러 대규모 애플리케이션이 동시에 실행되는 경우 높은 메모리 사용.
- 시스템 성능 또는 애플리케이션이 중단됩니다.
- 모든 앱에서 전체 시스템 메모리 사용량이 90% 이상 지속됩니다. 이 양의 메모리 사용량을 Teams 다른 앱 및 워크로드에 메모리를 다시 제공해야 합니다. 90%의 지속적인 메모리 사용량은 Teams 시스템에 메모리를 다시 제공하지 않는다는 의미일 수 있습니다. 이는 문제를 나타냅니다.

다음 이미지는 시스템 메모리 사용량이 비정상적으로 높은 경우 Task Manager의 보기 예제를 보여 줍니다.

![Teams 메모리 사용 현황 보기](media/teams-memory-high-mem-process-list.png)

![Teams 메모리 사용량 그래프](media/teams-memory-high-mem-process-list2.png)
