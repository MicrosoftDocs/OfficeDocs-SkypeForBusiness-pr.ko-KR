---
title: 정책 패키지를 Microsoft Teams
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: 사용자 그룹에 대한 정책을 관리할 때 일관성을 Microsoft Teams, 간소화 및 지원하기 위해 정책 패키지를 사용 및 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 2fd892bc440996c7c1f000402122ad268a402ebb6bf382672813efa296de819f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341791"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>정책 패키지를 Microsoft Teams

정책 패키지는 Microsoft Teams 역할이 비슷한 사용자에게 할당할 수 있는 미리 정의한 정책 및 정책 설정의 모음입니다. 조직 전체의 사용자 그룹에 대한 정책을 관리할 때 일관성을 제공하기 위해 정책 패키지를 구축했습니다.  

에 포함된 [](#policy-packages-included-in-teams) 정책 패키지를 Teams 사용자 지정 정책 [패키지를 만들 수 있습니다.](#custom-policy-packages)

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="관리 센터의 정책 패키지 페이지 스크린샷":::

사용자의 요구에 맞게 정책 패키지의 정책 설정을 사용자 지정할 수 있습니다. 패키지에서 정책 설정을 변경하면 해당 패키지에 할당된 모든 사용자에게 업데이트된 설정이 제공됩니다. 관리 센터 또는 PowerShell을 사용하여 Microsoft Teams 패키지를 관리합니다.

> [!NOTE]
> 각 사용자는 사용자 지정 정책 패키지 할당을 받기 위해 고급 통신 추가 기능을 필요로 합니다. 자세한 내용은 에 대한 고급 통신 추가 [Microsoft Teams.](/microsoftteams/teams-add-on-licensing/advanced-communications)

## <a name="what-is-a-policy-package"></a>정책 패키지란 무엇인가요?

정책 패키지를 사용하면 조직 전체의 특정 Teams 허용하거나 제한하려는 모든 기능을 제어할 수 있습니다. Teams 각 정책 패키지는 사용자 역할을 중심으로 설계되어 있으며 해당 역할에 일반적인 공동 작업 및 통신 활동을 지원하는 미리 정의된 정책 및 정책 설정을 포함합니다.

정책 패키지는 다음과 같은 정책 Teams 지원됩니다.

- 메시징 정책
- 모임 정책
- 앱 설정 정책
- 통화 정책
- 라이브 이벤트 정책

## <a name="policy-packages-included-in-teams"></a>정책 패키지에 Teams

Teams 현재 다음 정책 패키지가 포함되어 있습니다.

| 패키지 이름 | 설명 |
|---------|---------|
|Education(고등 교육 학생)    |고등 교육 학생에게 적용되는 정책 및 정책 설정 집합을 만듭니다.|
|Education(초등 학생)   |초등 학생에게 적용되는 정책 및 정책 설정 집합을 만듭니다.|
|Education(중등 학생)    |중등 학생에게 적용되는 정책 및 정책 설정 집합을 만듭니다.         |
|교육(교사)    |교사에게 적용되는 정책 및 정책 설정 집합을 만듭니다.      |
|교육(원격 학습을 사용하는 초등학교 교사)    |기본 교사에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생 안전 및 공동 작업을 극대화합니다.      |
|Education(원격 학습을 사용하는 초등 학생)    |초등 학생에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생 안전 및 공동 작업을 극대화합니다.      |
|프런트라인 관리자 |정책 집합을 만들고 이러한 설정을 조직의 프런트라인 관리자에게 적용합니다. |
|일선 작업자 |정책 집합을 만들고 이러한 설정을 조직의 일선 근로자에 적용합니다. |
|의료 의료 의료원  |등록된 간호사, 간호사, 담당 의사 및 사회 근로자가 채팅, 통화, 교대 관리 및 모임에 대한 모든 권한을 부여하는 정책 및 정책 설정 집합을 만듭니다. |
|의료 정보부서원  |IT 담당자, 정보 담당자, 재무 담당자 및 규정 준수 담당자와 같은 정보 근로자가 채팅, 통화 및 모임에 대한 모든 권한을 부여하는 정책 및 정책 설정 집합을 만듭니다.|
|의료 환자 방  |의료 조직의 환자실에 적용되는 정책 및 정책 설정 집합을 만듭니다.|
|중소기업 사용자(Business Voice) |비즈니스 음성 환경용 앱을 포함하는 앱 설정 정책을 만듭니다.|
|중소기업 사용자(Business Voice가 없는 사용자) |중소기업 사용자와 관련된 앱 설정 정책을 Teams(비 Business Voice 환경).
|공공 안전 책임자   |조직의 공공 안전 책임자에 적용되는 정책 및 정책 설정 집합을 만듭니다.|

> [!NOTE]
> 향후 릴리스의 Teams 추가될 예정이기 때문에 최신 정보를 다시 확인하겠습니다.  

각 개별 정책에는 정책 패키지의 이름이 지정되어 정책 패키지에 연결된 정책을 쉽게 식별할 수 있습니다.
예를 들어 학교의 교사에게 교육(교사) 정책 패키지를 할당하면 패키지의 각 정책에 대해 Education_Teacher 정책이 만들어집니다.

![교육(교사) 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>사용자 지정 정책 패키지

**사용자 지정 정책 패키지를 아직 사용자 지정 정책 패키지에 사용할 수 정부 커뮤니티 클라우드(GCC)**

사용자 지정 정책 패키지를 사용하면 조직에서 역할이 비슷한 사용자에 대한 자체 정책 집합을 번들로 만들 수 있습니다. 필요한 정책 유형 및 정책을 추가하여 자체 정책 패키지를 만들 수 있습니다.

새 사용자 지정 정책 패키지를 만들 수 있습니다.

1. Microsoft Teams 센터의 왼쪽 탐색에서 정책 패키지를 선택하고 추가를 **클릭합니다.**

    :::image type="content" source="media/policy-packages-add.png" alt-text="관리 센터의 정책 패키지 페이지에 있는 추가 단추 스크린샷":::

2. 패키지의 이름과 설명을 입력합니다.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="새 사용자 지정 정책 패키지 추가 스크린샷":::

3. 패키지에 포함할 정책 유형 및 정책 이름을 선택합니다.

4. **저장** 을 클릭합니다.

## <a name="how-to-use-policy-packages"></a>정책 패키지를 사용하는 방법

다음은 조직에서 정책 패키지를 사용하는 방법을 간략하게 설명하는 예제입니다.

![정책 패키지 사용 방법 개요](media/manage-policy-packages-overview.png)

- **[보기:](#view-the-settings-of-a-policy-in-a-policy-package)** 정책 패키지에서 정책을 볼 수 있습니다. 그런 다음 패키지를 할당하기 전에 패키지의 각 정책 설정을 확인합니다. 각 설정을 이해해야 합니다. 미리 정의한 값이 조직에 적합한지 또는 조직의 요구에 따라 더 제한적으로 변경할지 또는 고지 사항을 변경해야 하는지 여부를 결정하십시오.

    정책이 삭제된 경우 설정을 볼 수 있지만 설정을 변경할 수 없습니다. 삭제된 정책은 정책 패키지를 할당할 때 미리 정의한 설정으로 다시 만들어집니다.

- **[사용자](#customize-policies-in-a-policy-package)** 지정: 정책 패키지의 정책 설정을 조직의 요구에 맞게 사용자 지정합니다.

- **[할당](#assign-a-policy-package)**: 사용자에게 정책 패키지를 할당합니다.  

> [!NOTE]
> 패키지를 할당한 후 정책 패키지에서 정책 설정을 변경할 수 있습니다. 정책 설정을 변경하면 패키지가 할당된 사용자에게 자동으로 적용됩니다.

다음은 Microsoft Teams 관리 센터에서 정책 패키지를 보고, 할당하고, 사용자 지정하는 Microsoft Teams 단계입니다.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>정책 패키지에서 정책 설정 보기

1. Microsoft Teams 센터의 왼쪽 탐색에서 정책 패키지를 선택한 다음 패키지 이름 왼쪽을 클릭하여 정책 패키지를 선택합니다. 

2. 보하려는 정책을 클릭합니다.

### <a name="customize-policies-in-a-policy-package"></a>정책 패키지에서 정책 사용자 지정

정책 패키지 페이지를 통해 또는  정책 관리 센터의 정책 페이지로 직접 이동하여 정책 설정을 Microsoft Teams 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 다음 지침을 따릅니다.
    - 정책 **패키지 를** 클릭한 다음 패키지 이름 왼쪽을 클릭하여 정책 패키지를 선택합니다.
    - 정책 유형을 클릭합니다.  예를 들어 메시징 정책을 **클릭합니다.**

2. 편집할 정책을 선택합니다. 정책 패키지에 연결된 정책은 정책 패키지와 같은 이름을 가지고 있습니다.

3. 원하는 내용을 변경한 다음 저장을 **클릭합니다.**

### <a name="assign-a-policy-package"></a>정책 패키지 할당

개별 사용자, 그룹 또는 사용자 일괄 처리에 정책 패키지를 할당할 수 있습니다. 정책 패키지를 할당하는 방법에 대한 자세한 내용은 사용자 및 그룹에 정책 패키지 [할당을 참조하세요.](assign-policy-packages.md)

## <a name="related-topics"></a>관련 항목

- [정책 패키지 할당](assign-policy-packages.md)
- [Teams EDU 관리자를 위한 정책 패키지](policy-packages-edu.md)
- [Teams 위한 정책 패키지](policy-packages-healthcare.md)
- [Teams 정책 패키지](policy-packages-gov.md)
