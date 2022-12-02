---
title: Teams에서 정책 패키지 관리
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams에서 정책 패키지를 사용, 관리 및 사용자 지정하여 사용자 그룹에 대한 정책을 관리할 때 일관성을 단순화, 간소화 및 제공하는 방법을 알아봅니다.
ms.openlocfilehash: 138b1cada469a71cf844c8a73b1cb12511fc68b2
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245695"
---
# <a name="managing-policy-packages-in-teams"></a>Teams에서 정책 패키지 관리

Microsoft Teams의 정책 패키지는 조직에서 유사한 역할을 가진 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 모음입니다. 조직 전체의 사용자 그룹에 대한 정책을 관리할 때 일관성을 제공하고 간소화하고 일관성을 제공하도록 정책 패키지를 빌드했습니다.  

[Teams에 포함된 정책 패키지를](#policy-packages-included-in-teams) 사용하거나 [사용자 지정 정책 패키지를 만들 수 있습니다](#custom-policy-packages).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="관리 센터의 정책 패키지 페이지 스크린샷" lightbox="media/policy-packages-admin-center.png":::

사용자의 요구에 맞게 정책 패키지에서 정책 설정을 사용자 지정할 수 있습니다. 패키지에서 정책 설정을 변경하면 해당 패키지에 할당된 모든 사용자가 업데이트된 설정을 가져옵니다. Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 정책 패키지를 관리합니다.

## <a name="what-is-a-policy-package"></a>정책 패키지란?

정책 패키지를 사용하면 조직 전체의 특정 사용자 집합에 대해 허용하거나 제한하려는 Teams 기능을 제어할 수 있습니다. Teams의 각 정책 패키지는 사용자 역할을 중심으로 설계되었으며 해당 역할에 일반적인 공동 작업 및 통신 활동을 지원하는 미리 정의된 정책 및 정책 설정을 포함합니다.

정책 패키지는 다음 Teams 정책 유형을 지원합니다.

- 메시징 정책
- 모임 정책
- 앱 설정 정책
- 통화 정책
- 라이브 이벤트 정책

## <a name="policy-packages-included-in-teams"></a>Teams에 포함된 정책 패키지

Teams에는 현재 다음 정책 패키지가 포함되어 있습니다.

| 패키지 이름 | 설명 |
|---------|---------|
|교육(고등 교육 학생)    |고등 교육 학생에게 적용되는 정책 및 정책 설정 집합을 만듭니다.|
|교육(초등학생)   |초등학생에게 적용되는 정책 및 정책 설정 집합을 만듭니다.|
|교육(중등학생)    |중등 학생에게 적용되는 정책 및 정책 설정 집합을 만듭니다.         |
|교육(교사)    |교사에게 적용되는 정책 및 정책 설정 집합을 만듭니다.      |
|교육(원격 학습을 사용하는 초등학교 교사)    |초등학교 교사에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.      |
|교육(원격 학습을 사용하는 초등학생)    |초등학교 학생에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.      |
|최전방 관리자 |정책 집합을 만들고 해당 설정을 조직의 최전방 관리자에게 적용합니다. |
|최전방 작업자 |정책 집합을 만들고 해당 설정을 조직의 최전방 작업자에게 적용합니다. |
|의료 임상 연구원  |등록된 간호사, 유료 간호사, 의사 및 사회복지사와 같은 의료진에게 채팅, 통화, 이동 관리 및 회의에 대한 완전한 액세스를 제공하는 정책 및 정책 설정을 만듭니다. |
|의료 정보 직원  |IT 직원, 정보 전문가, 재무 담당자 및 규정 준수 담당자와 같은 정보 직원에게 채팅, 통화 및 모임에 대한 전체 액세스 권한을 부여하는 정책 및 정책 설정 집합을 만듭니다.|
|의료 환자실  |의료 조직의 환자실에 적용되는 정책 및 정책 설정 집합을 만듭니다. |
|공공 안전 책임자   |조직의 공공 안전 책임자에게 적용되는 정책 및 정책 설정 집합을 만듭니다.|
|중소기업 사용자(Business Voice) |사용자를 위한 비즈니스 음성 환경용 앱을 포함하는 앱 설정 정책을 만듭니다.|
|중소기업 사용자(Business Voice 제외) |비즈니스 음성 기능이 없는 중소기업 Teams 사용자와 관련된 앱 설정 정책을 만듭니다.

> [!NOTE]
> Teams의 향후 릴리스에서 더 많은 정책 패키지를 추가할 예정이므로 최신 정보를 다시 확인하세요.  

각 개별 정책은 정책 패키지의 이름이 지정되며 정책 패키지에 연결된 정책을 쉽게 식별할 수 있습니다.
예를 들어 학교의 교사에게 교육(교사) 정책 패키지를 할당하면 패키지의 각 정책에 대해 Education_Teacher 라는 정책이 만들어집니다.

:::image type="content" source="media/teams-policy-packages-education.png" alt-text="교육(교사) 정책 패키지의 스크린샷" lightbox="media/teams-policy-packages-education.png":::

## <a name="custom-policy-packages"></a>사용자 지정 정책 패키지

> [!NOTE]
> 사용자 지정 정책 패키지 기능은 미리 보기에서 사용할 수 있습니다. 미리 보기 후에 이 기능을 사용하려면 각 사용자에게 Teams Premium 라이선스가 필요합니다.

사용자 지정 정책 패키지를 사용하면 조직에서 비슷한 역할을 가진 사용자를 위해 고유한 정책 집합을 번들로 묶을 수 있습니다. 필요한 정책 유형 및 정책을 추가하여 고유한 정책 패키지를 만듭니다.

새 사용자 지정 정책 패키지를 만들려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 창에서 **정책 패키지를** 선택한 다음 **추가** 를 클릭합니다.

    :::image type="content" source="media/policy-packages-add.png" alt-text="관리 센터의 정책 패키지 페이지에 있는 추가 단추의 스크린샷" lightbox="media/policy-packages-add.png":::

2. 패키지의 이름과 설명을 입력합니다.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="새 사용자 지정 정책 패키지를 추가하는 스크린샷" lightbox="media/policy-packages-add-custom.png":::

3. 패키지에 포함할 정책 유형 및 정책 이름을 선택합니다.

4. **저장** 을 선택합니다.

## <a name="how-to-use-policy-packages"></a>정책 패키지를 사용하는 방법

다음은 조직에서 정책 패키지를 사용하는 방법을 간략하게 설명합니다.

![정책 패키지를 사용하는 방법에 대한 개요입니다.](media/manage-policy-packages-overview.png)

- **[보기](#view-the-settings-of-a-policy-in-a-policy-package)**: 정책 패키지에서 정책을 봅니다. 그런 다음 패키지를 할당하기 전에 패키지에서 각 정책의 설정을 확인합니다. 각 설정을 이해해야 합니다. 미리 정의된 값이 조직에 적합한지 또는 조직의 요구 사항에 따라 더 제한적이거나 관대하도록 변경해야 하는지 여부를 결정합니다.

    정책이 삭제된 경우에도 설정을 볼 수 있지만 설정을 변경할 수는 없습니다. 정책 패키지를 할당할 때 미리 정의된 설정을 사용하여 삭제된 정책을 다시 만듭니다.

- **[사용자 지정](#customize-policies-in-a-policy-package)**: 조직의 요구에 맞게 정책 패키지의 정책 설정을 사용자 지정합니다.

- **[할당](#assign-a-policy-package)**: 사용자에게 정책 패키지를 할당합니다.  

> [!NOTE]
> 패키지를 할당한 후 정책 패키지에서 정책 설정을 변경할 수도 있습니다. 정책 설정에 대한 모든 변경 내용은 패키지가 할당된 사용자에게 자동으로 적용됩니다.

다음은 Microsoft Teams 관리 센터에서 정책 패키지를 보고, 할당하고, 사용자 지정하는 방법에 대한 단계입니다.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>정책 패키지에서 정책 설정 보기

1. Microsoft Teams 관리 센터의 왼쪽 창에서 **정책 패키지를** 선택한 다음 패키지 이름 왼쪽을 클릭하여 정책 패키지를 선택합니다.

2. 보려는 정책을 선택합니다.

### <a name="customize-policies-in-a-policy-package"></a>정책 패키지에서 정책 사용자 지정

**정책 패키지** 페이지를 통해 또는 Microsoft Teams 관리 센터의 정책 페이지로 직접 이동하여 정책 설정을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 창에서 다음 중 하나를 수행합니다.
    - **정책 패키지를** 선택한 다음 패키지 이름 왼쪽을 클릭하여 정책 패키지를 선택합니다.
    - 정책 유형을 선택합니다.  예를 들어 **메시징 정책을** 클릭합니다.

2. 편집할 정책을 선택합니다. 정책 패키지에 연결된 정책은 정책 패키지와 이름이 같습니다.

3. 원하는 대로 변경한 다음 **저장** 을 클릭합니다.

### <a name="assign-a-policy-package"></a>정책 패키지 할당

개별 사용자, 그룹 또는 사용자 일괄 처리에 정책 패키지를 할당할 수 있습니다. 정책 패키지를 할당하는 방법에 대한 자세한 내용은 [사용자 및 그룹에 정책 패키지 할당을 참조하세요](assign-policy-packages.md).

## <a name="related-topics"></a>관련 주제

- [정책 패키지 할당](assign-policy-packages.md)
- [EDU 관리자를 위한 Teams 정책 패키지](policy-packages-edu.md)
- [의료용 Teams 정책 패키지](policy-packages-healthcare.md)
- [정부용 Teams 정책 패키지](policy-packages-gov.md)
