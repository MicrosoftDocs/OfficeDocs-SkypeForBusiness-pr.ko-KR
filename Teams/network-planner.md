---
title: Microsoft 팀을 위한 네트워크 Planner 사용
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 네트워크 Planner를 사용 하 여 Microsoft 팀의 네트워크 요구 사항을 결정 하는 방법을 알아봅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e27979bc4f440fee58f97ffb647cdd5465fb326
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832708"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Microsoft 팀을 위한 네트워크 Planner 사용

네트워크 Planner는 팀 관리 센터에서 사용할 수 있는 새로운 도구입니다. **Planner** > **네트워크 planner**로 이동한 후이를 찾을 수 있습니다. 네트워크 Planner를 사용 하 여 조직 내에서 Microsoft 팀 사용자를 연결 하는 데 필요한 네트워크 요구 사항을 확인 하 고 구성 하는 방법에 대해 설명 합니다. 네트워크 세부 정보 및 팀 사용량을 제공 하는 경우 네트워크 계획자는 조직의 실제 위치에서 팀 및 클라우드 음성을 배포 하기 위한 네트워크 요구 사항을 계산 합니다.

![네트워크 Planner 스크린샷](media/network-planner.png)

네트워크 Planner를 사용 하 여 다음을 수행할 수 있습니다.

- 사이트와 Microsoft 권장 가상 사용자 (office worker, 원격 작업자, 팀 대화방 시스템)를 사용 하 여 조직의 표현을 만듭니다.

    > [!NOTE]
    > 권장 가상 사용자는 팀의 데이터에 가장 적합 한 시나리오 및 일반적인 사용 패턴을 기준으로 개발 되었습니다. 그러나 권장 되는 세 개의 가상 사용자 외에도 최대 3 명의 사용자 지정 가상을 만들 수 있습니다.

- 팀 사용에 대 한 보고서를 생성 하 고 대역폭 요구 사항을 계산 합니다.

네트워크 Planner를 사용 하려면 전역 관리자, 팀 서비스 관리자 또는 팀 통신 관리자 여야 합니다.

## <a name="create-a-custom-persona"></a>사용자 지정 가상 사용자 만들기

다음 단계에 따라 사용자 지정 가상 사용자를 만듭니다.

1. Microsoft 팀 관리 센터의 네트워크 Planner로 이동 합니다.

2. **가상 사용자** 탭에서 **+ 사용자 가상 사용자**를 클릭 합니다. 

3. **새 사용자 지정 가상** 사용자 창에서 새 가상 사용자에 대 한 이름과 설명을 추가 합니다.

4. 이 가상 사용자가 조직 내에서 사용할 사용 권한을 선택 합니다.

5. **저장**을 클릭 합니다.

## <a name="build-your-plan"></a>계획 수립

네트워크 계획 만들기를 시작 하려면 다음 단계를 따르세요.

1. Microsoft 팀 관리 센터의 네트워크 Planner로 이동 합니다.

2. **네트워크 계획** 탭에서 **네트워크 계획 추가**를 클릭 합니다.

3. 네트워크 계획의 이름과 설명을 입력 합니다. 사용할 수 있는 계획 목록에 네트워크 계획이 표시 됩니다.

4. 계획 이름을 클릭 하 여 새 계획을 선택 합니다.

5. 사이트를 추가 하 여 조직의 네트워크 설정에 대 한 표현을 만듭니다.

    조직의 네트워크에 따라 사이트를 사용 하 여 건물, 사무실 위치 등을 나타내는 것이 좋습니다. 사이트는 인터넷 및/또는 PSTN 연결 공유를 허용 하기 위해 WAN에 연결 될 수 있습니다. 최상의 결과를 위해서는 인터넷 이나 PSTN에 원격으로 연결 하는 사이트를 만들기 전에 로컬 연결을 사용 하 여 사이트를 만듭니다.

    사이트를 만들려면 다음을 수행 합니다.

    1. 사이트의 이름 및 설명을 추가 합니다.

    2. **네트워크 설정**에서 해당 사이트에 있는 네트워크 사용자의 수를 추가 합니다 (필수).

    3. 네트워크 세부 정보 추가: WAN 사용 가능, WAN 용량, 인터넷 송신 (**로컬** 또는 **원격**), PSTN egress (없음, 로컬 또는 원격)

      > [!NOTE]
      > 보고서를 생성할 때 특정 대역폭 권장 사항을 보려면 WAN 및 인터넷 용량 번호를 추가 해야 합니다.

    4. **저장**을 클릭 합니다.

## <a name="create-a-report"></a>보고서 만들기

모든 사이트를 추가한 후 다음과 같이 보고서를 만들 수 있습니다.

1. **보고서 탭에서** **보고서 시작**을 클릭 합니다.

2. 만드는 각 사이트에 대해 사용 가능한 가상 사용자 수를 분산 합니다. Microsoft 권장 가상 사용자를 사용 하는 경우 번호가 자동으로 배포 됩니다 (80% office worker 및 20% 원격 작업자).

3. 배포를 완료 한 후 **보고서 생성**을 클릭 합니다.

    생성 된 보고서에는 출력을 명확 하 게 이해할 수 있도록 여러 가지 보기의 대역폭 요구 사항이 표시 됩니다.
    - 개별 계산이 있는 테이블에는 허용 된 각 활동에 대 한 대역폭 요구 사항이 표시 됩니다.
    - 추가 보기에는 권장 사항이 포함 된 전반적인 대역폭 요구 사항이 표시 됩니다.

4. **저장**을 클릭 합니다. 나중에 보기 위해 보고서를 보고서 목록에서 사용할 수 있습니다.

## <a name="example-scenario"></a>예제 시나리오

네트워크 Planner를 사용 하 여 네트워크 계획을 설정 하 고 이러한 단계를 사용 하 여 보고서를 생성 하는 방법에 대 한 예는 [네트워크 Planner 방법 PowerPoint 데크](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) 를 다운로드 하세요 (영어만 해당).
