---
title: 네트워크 플래너를 사용하여 Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 관리자는 Network Planner를 사용하여 Microsoft Teams 대한 네트워크 요구 사항을 확인하는 방법을 알아볼 수 있습니다.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fba570bdd7a83c26d68d10e65f631a0d028d7408
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045557"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>네트워크 플래너를 사용하여 Microsoft Teams

Network Planner는 Teams 관리 센터에서 사용할 수 있는 새로운 도구입니다. **네트워크 플래너** **계획** > 으로 이동하여 찾을 수 있습니다. 몇 단계만 수행하면 Network Planner를 통해 조직 전체에서 Microsoft Teams 사용자를 연결하기 위한 네트워크 요구 사항을 확인하고 구성할 수 있습니다. 네트워크 세부 정보 및 Teams 사용을 제공하는 경우 네트워크 플래너는 조직에서 실제 위치에 Teams와 Cloud Voice를 배포하는데 필요한 네트워크 요구 사항을 계산합니다.

![네트워크 플래너의 스크린샷.](media/network-planner.png)

네트워크 플래너를 사용하면 다음을 수행할 수 있습니다.

- 사이트 및 Microsoft 권장 페르소나(사무실 근로자, 원격 작업자 및 Teams 회의실 시스템)를 사용하여 조직의 표현을 만듭니다.

    > [!NOTE]
    > 권장 가상 사용자는 Teams 가장 적합한 사용 시나리오 및 일반적인 사용 패턴의 데이터를 기반으로 개발되었습니다. 그러나 권장되는 3개의 가상 사용자 외에 최대 3개의 사용자 지정 가상 사용자를 만들 수 있습니다.

- 보고서를 생성하고 Teams 사용에 대한 대역폭 요구 사항을 계산합니다.

네트워크 플래너를 사용하려면 전역 관리자, Teams 관리자 또는 Teams 통신 관리자여야 합니다.

## <a name="create-a-custom-persona"></a>사용자 지정 가상 사용자 만들기

사용자 지정 가상 사용자를 만들려면 다음 단계를 수행합니다.

1. Microsoft Teams 관리 센터의 Network Planner로 이동합니다.

2. **가상 사용자** 탭에서 **+ 사용자 지정 가상 사용자를** 클릭합니다. 

3. **새 사용자 지정 가상 사용자** 창에서 새 가상 사용자의 이름과 설명을 추가합니다.

4. 이 가상 사용자가 조직 내에서 사용할 사용 권한을 선택합니다.

5. **저장** 을 클릭합니다.

## <a name="build-your-plan"></a>계획 빌드

다음 단계에 따라 네트워크 계획 빌드를 시작합니다.

1. Microsoft Teams 관리 센터의 Network Planner로 이동합니다.

2. **네트워크 계획** 탭에서 **네트워크 계획 추가를** 클릭합니다.

3. 네트워크 계획의 이름과 설명을 입력합니다. 네트워크 계획이 사용 가능한 계획 목록에 표시됩니다.

4. 계획 이름을 클릭하여 새 계획을 선택합니다.

5. 사이트를 추가하여 조직의 네트워크 설정 표현을 만듭니다.

    조직의 네트워크에 따라 사이트를 사용하여 건물, 사무실 위치 또는 기타 항목을 나타낼 수 있습니다. 인터넷 및/또는 PSTN 연결을 공유할 수 있도록 WAN에서 사이트를 연결할 수 있습니다. 최상의 결과를 위해 인터넷 또는 PSTN에 원격으로 연결하는 사이트를 만들기 전에 로컬 연결이 있는 사이트를 만듭니다.

    사이트를 만들려면 다음을 수행합니다.

    1. 사이트의 이름과 설명을 추가합니다.

    2. **네트워크 설정** 에서 해당 사이트의 네트워크 사용자 수를 추가합니다(필수).

    3. 네트워크 세부 정보 추가: WAN 사용, WAN 용량, 인터넷 송신(**로컬** 또는 **원격**) 및 PSTN 송신(없음, 로컬 또는 원격).

      > [!NOTE]
      > 보고서를 생성할 때 특정 대역폭 권장 사항을 보려면 WAN 및 인터넷 용량 번호를 추가해야 합니다.

    4. **저장** 을 클릭합니다.

## <a name="create-a-report"></a>보고서 만들기

모든 사이트를 추가한 후 다음과 같이 보고서를 만들 수 있습니다.

1. **보고서** 탭에서 **보고서 시작을** 클릭합니다.

2. 만든 각 사이트에 대해 사용 가능한 가상 사용자에 사용자 수를 분산합니다. Microsoft 권장 페르소나를 사용하는 경우 번호가 자동으로 배포됩니다(사무실 작업자 80%, 원격 작업자 20%).

3. 배포를 완료한 후 **보고서 생성** 을 클릭합니다.

    생성된 보고서는 출력을 명확하게 이해할 수 있도록 여러 다른 보기에서 대역폭 요구 사항을 표시합니다.
    - 개별 계산이 포함된 테이블에는 허용되는 각 작업에 대한 대역폭 요구 사항이 표시됩니다.
    - 추가 보기에는 권장 사항이 포함된 전체 대역폭 요구 사항이 표시됩니다.

4. **저장** 을 클릭합니다. 나중에 볼 수 있도록 보고서 목록에서 보고서를 사용할 수 있습니다.

## <a name="example-scenario"></a>시나리오 예

Network Planner를 사용하여 네트워크 계획을 설정하고 이러한 단계를 사용하여 보고서를 생성하는 방법에 대한 예제를 보려면 [Network Planner How-To PowerPoint 데크](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true)(영어만 해당)를 다운로드합니다.
