---
title: Microsoft 팀에서 정책 패키지 관리
author: lanachin
ms.author: v-lanac
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
description: Microsoft 팀에서 정책 패키지를 사용 하 고 관리 하 여 사용자 그룹에 대 한 정책을 관리할 때 일관성을 간소화 하 고 간소화 하 고 해결 하는 방법을 알아봅니다.
ms.openlocfilehash: 140b67ae8df01d29b8e6d37c6fe1a36afebbd949
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48488414"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Microsoft 팀에서 정책 패키지 관리

> [!NOTE]
> 이 문서에서 설명 하는 [사용자 지정 정책 패키지](#custom-policy-packages)의 기능 중 하나는 현재 비공개 미리 보기 상태입니다.

Microsoft 팀의 정책 패키지는 조직에서 유사한 역할을 갖는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정의 모음입니다. 조직의 사용자 그룹에 대 한 정책을 관리할 때 일관성을 단순화 하 고 합리화 하 고 사용할 수 있도록 하는 정책 패키지를 작성 했습니다.  

[팀에 포함 된 정책 패키지](#policy-packages-included-in-teams) 를 사용 하거나 [고유한 사용자 지정 정책 패키지](#custom-policy-packages) (비공개 미리 보기)를 만들 수 있습니다.

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="관리 센터의 정책 패키지 페이지 스크린샷":::

사용자의 요구에 맞게 정책 패키지의 정책 설정을 사용자 지정할 수 있습니다. 패키지의 정책 설정을 변경 하면 해당 패키지에 할당 된 모든 사용자가 업데이트 된 설정을 받습니다. Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책 패키지를 관리 합니다.

## <a name="what-is-a-policy-package"></a>정책 패키지 란?

정책 패키지를 사용 하 여 조직 내 특정 사용자 집합에 허용 하거나 제한할 팀 기능을 제어할 수 있습니다. 팀의 각 정책 패키지는 사용자 역할을 중심으로 설계 되며, 해당 역할에 일반적으로 사용 되는 공동 작업 및 통신 작업을 지 원하는 미리 정의 된 정책 및 정책 설정이 포함 되어 있습니다.

정책 패키지는 다음 팀 정책 유형을 지원 합니다.

- 메시징 정책
- 모임 정책
- 앱 설정 정책
- 통화 정책
- 라이브 이벤트 정책

## <a name="policy-packages-included-in-teams"></a>팀에 포함 된 정책 패키지

현재 팀에는 다음 정책 패키지가 포함 되어 있습니다.

|**패키지 이름**  |**설명** |
|---------|---------|
|교육 (고급 교육 학생)    |높은 교육 학생 들에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.|
|교육 (주 학교 학생)   |기본 학생에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.|
|교육 (보조 학교 학생)    |보조 학생에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.         |
|교육 (교사)    |교사에 게 적용할 정책 및 정책 설정 집합을 만듭니다.      |
|교육 (원격 학습을 사용 하 여 기본 학교 교사)    |초등학교 교사에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.      |
|교육 (원격 학습을 사용 하는 기본 학교 학생)    |초등학교 학생에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.      |
|Firstline manager |조직의 Firstline 관리자에 게 정책 집합을 만들고 해당 설정을 적용 합니다. |
|Firstline worker |정책 집합을 만들고 조직의 Firstline Worker에 해당 설정을 적용 합니다. |
|의료 임상 근로자  |등록 된 nurses, 청구 nurses, 의사, 소셜 작업자에 게 채팅, 통화, 교대 관리, 모임에 대 한 전체 액세스 등의 임상 근로자를 제공 하는 정책 및 정책 설정 집합을 만듭니다. |
|의료 정보 근로자  |IT 직원, informatics 스태프, 재무 담당자, 규정 준수 관리자, 채팅, 통화, 모임에 대 한 모든 액세스 권한을 제공 하는 정책 및 정책 설정 집합을 만듭니다.|
|의료 환자 실  |건강 관리 조직의 환자 방에 해당 하는 정책 및 정책 설정 집합을 만듭니다.|
|중소 기업 사용자 (비즈니스 음성) |비즈니스 음성 환경에 대 한 앱을 포함 하는 앱 설치 정책을 만듭니다.|
|중소 규모 비즈니스 사용자 (비즈니스 보이스 필요 없음) |중소 규모의 비즈니스 팀 사용자 (비 비즈니스 음성 환경)와 관련 된 앱 설치 정책을 만듭니다.
|공개 안전 책임자   |조직의 공개 보안 책임자에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.|

> [!NOTE]
> 팀의 향후 릴리스에서 정책 패키지를 더 추가 하 게 되므로 최신 정보를 다시 확인 하세요.  

정책 패키지에 연결 된 정책을 쉽게 식별할 수 있도록 각 개별 정책에 정책 패키지의 이름이 지정 됩니다.
예를 들어 학교에 교사 (교육) 정책 패키지를 할당 하는 경우 패키지의 각 정책에 대해 Education_Teacher 이라는 정책이 만들어집니다.

![교사 (교육) 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>사용자 지정 정책 패키지

**이 기능은 비공개 미리 보기에 있습니다.**

사용자 지정 정책 패키지를 사용 하 여 조직에서 비슷한 역할을 갖는 사용자에 대해 자신만의 정책 집합을 번들로 만들 수 있습니다. 필요한 정책 유형 및 정책을 추가 하 여 고유한 정책 패키지를 만듭니다.

새 사용자 지정 정책 패키지를 만들려면 다음을 수행 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지**를 선택한 다음 **추가**를 클릭 합니다.
    :::image type="content" source="media/policy-packages-add.png" alt-text="관리 센터의 정책 패키지 페이지에 있는 추가 단추 스크린샷":::
2. 패키지의 이름과 설명을 입력 합니다.
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="새 사용자 지정 정책 패키지 추가 스크린샷":::
3. 패키지에 포함할 정책 유형 및 정책 이름을 선택 합니다.
4. **저장**을 클릭합니다.

## <a name="how-to-use-policy-packages"></a>정책 패키지를 사용 하는 방법

다음 개요에는 조직에서 정책 패키지를 사용 하는 방법이 나와 있습니다.

![정책 패키지 사용 방법 개요](media/manage-policy-packages-overview.png)

- **[보기](#view-the-settings-of-a-policy-in-a-policy-package)**: 정책 패키지의 정책을 봅니다. 그런 다음 패키지를 할당 하기 전에 패키지의 각 정책에 대 한 설정을 확인 합니다. 각 설정을 이해 하 고 있는지 확인 합니다. 미리 정의 된 값이 조직에 적합 한지 아니면 조직의 요구 사항에 따라 더 엄격 하 게 또는 lenient 변경 해야 하는지 여부를 결정 합니다.

    정책이 삭제 된 경우에도 설정을 볼 수 있지만 설정을 변경할 수는 없습니다. 정책 패키지를 할당할 때 미리 정의 된 설정을 사용 하 여 삭제 된 정책이 다시 만들어집니다.

- **[사용자 지정](#customize-policies-in-a-policy-package)**: 조직의 요구에 맞게 정책 패키지의 정책 설정을 사용자 지정 합니다.

- **[Assign](#assign-a-policy-package)**: 사용자에 게 정책 패키지를 할당 합니다.  

> [!NOTE]
> 패키지를 할당 한 후에는 정책 패키지의 정책 설정을 변경할 수도 있습니다. 정책 설정에 대 한 변경 내용은 패키지를 할당 한 사용자에 게 자동으로 적용 됩니다.

Microsoft 팀 관리 센터에서 정책 패키지를 보고 할당 하 고 사용자 지정 하는 방법에 대 한 단계는 다음과 같습니다.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>정책 패키지의 정책 설정 보기

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지**를 선택한 다음 패키지 이름 왼쪽을 클릭 하 여 정책 패키지를 선택 합니다.
2. 보려는 정책을 클릭 합니다.

### <a name="customize-policies-in-a-policy-package"></a>정책 패키지의 정책 사용자 지정

정책 **패키지** 페이지를 통해 또는 Microsoft 팀 관리 센터의 정책 페이지로 직접 이동 하 여 정책의 설정을 편집할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 다음 중 하나를 수행 합니다.
    - **정책 패키지**를 클릭 한 다음 패키지 이름 왼쪽을 클릭 하 여 정책 패키지를 선택 합니다.
    - 정책 유형을 클릭 합니다.  예를 들어 **메시지 정책을**클릭 합니다.
2. 편집 하려는 정책을 선택 합니다. 정책 패키지에 연결 된 정책에는 정책 패키지와 동일한 이름이 사용 됩니다.
3. 원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.

### <a name="assign-a-policy-package"></a>정책 패키지 할당

#### <a name="assign-a-policy-package-to-one-user"></a>한 사용자에 게 정책 패키지 할당

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.
2. 사용자의 페이지에서 **정책을**클릭 한 다음 **정책 패키지**옆에 있는 **편집**을 클릭 합니다.
3. **정책 패키지 할당** 창에서 할당할 패키지를 선택 하 고 **저장**을 클릭 합니다.

#### <a name="assign-a-policy-package-to-multiple-users"></a>여러 사용자에 게 정책 패키지 할당

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **정책 패키지로**이동한 다음 패키지 이름 왼쪽을 클릭 하 여 할당 하려는 정책 패키지를 선택 합니다.
2. **사용자 관리**를 클릭 합니다.
3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가**를 클릭합니다. 추가할 각 사용자에 대해 이 단계를 반복합니다.
4. 사용자 추가를 마쳤으면 **저장**을 클릭 합니다.

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>사용자의 대규모 집합 (일괄 처리)에 정책 패키지 할당

일괄 처리 정책 패키지 할당을 사용 하 여 한 번에 대규모 사용자 집합에 정책 패키지를 할당 합니다. [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet을 사용 하 여 할당 하려는 사용자 및 정책 패키지의 일괄 처리를 제출할 수 있습니다. 할당이 백그라운드 작업으로 처리 되 고 각 일괄 처리에 대 한 작업 ID가 생성 됩니다.

일괄 처리에는 최대 5000 명의 사용자를 포함할 수 있습니다. 개체 Id, UPN, SIP 주소 또는 전자 메일 주소로 사용자를 지정할 수 있습니다. 자세한 내용은 [사용자 일괄 처리에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)을 참조 하세요.

## <a name="troubleshooting"></a>문제 해결

**정책 패키지를 할당할 때 오류가 표시 되는 경우**

패키지에서 하나 이상의 정책이 성공적으로 만들어지거나 적용 되지 않은 경우이 문제가 발생할 수 있습니다. 정책 패키지를 사용자에 게 다시 할당 합니다. 작업을 다시 시도 하면 일반적으로이 문제가 해결 됩니다.

## <a name="related-topics"></a>관련 항목

[팀에서 사용자에 게 정책 할당](assign-policies.md)

[.EDU 관리자를 위한 팀 정책 패키지](policy-packages-edu.md)

[의료에 대 한 팀 정책 패키지](policy-packages-healthcare.md)

[정부용 팀 정책 패키지](policy-packages-gov.md)
