---
title: 의료용 Teams 정책 패키지
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: medium
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 의료 조직의 Teams 정책 패키지를 사용하고 관리하는 방법에 대해 알아 보세요.
ms.openlocfilehash: d71945508055ddc7b6f6661d93e8918879d59d23
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731967"
---
# <a name="teams-policy-packages-for-healthcare"></a>의료용 Teams 정책 패키지

## <a name="overview"></a>개요

Microsoft Teams의 [정책 패키지](manage-policy-packages.md)는 조직에서 유사한 역할을 가진 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 모음입니다. 정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다. 사용자의 요구 사항에 맞게 패키지의 정책 설정을 사용자 정의할 수 있습니다. 정책 패키지의 정책 설정을 변경하면 해당 패키지에 할당된 모든 사용자에게 업데이트된 설정이 제공됩니다. Microsoft Teams 관리자 센터 또는 PowerShell을 사용하여 정책 패키지를 관리할 수 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

정책 패키지는 패키지에 따라 다음에 대한 정책을 미리 정의합니다.

- 메시지
- 모임
- 통화
- 앱 설정
- 라이브 이벤트

Teams는 현재 다음 의료 정책 패키지를 포함하고 있습니다.

|Microsoft Teams 관리 센터의 패키지 이름|최적 용도|설명 |
|---------|---------|---------|
|의료 임상 연구원  |의료 조직의 임상 연구원  |등록된 간호사, 유료 간호사, 의사 및 사회복지사와 같은 의료진에게 채팅, 통화, 이동 관리 및 회의에 대한 완전한 액세스를 제공하는 정책 및 정책 설정을 만듭니다. |
|의료 정보 직원  |의료 조직의 정보 연구원 |IT 직원, 정보 전문가, 재무 담당자 및 규정 준수 담당자와 같은 정보 직원에게 채팅, 통화 및 모임에 대한 전체 액세스 권한을 부여하는 정책 및 정책 설정 집합을 만듭니다.|
|의료 환자실  |환자실 장치|의료 조직의 환자실에 적용되는 정책 및 정책 설정 집합을 만듭니다.|

![의료 정책 패키지 스크린샷.](media/policy-packages-healthcare.png)

각 개별 정책은 정책 패키지의 이름이 지정되며 정책 패키지에 연결된 정책을 쉽게 식별할 수 있습니다. 예를 들어 조직의 임상 연구원에게 의료 임상 작업자 정책 패키지를 할당할 때 패키지의 각 정책에 대해 Healthcare_ClinicalWorker라는 정책이 생성됩니다.

![Healthcare 임상근로자 패키지의 정책 스크린샷.](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>정책 패키지로 시작

의료 정책 패키지를 시작하려면 Microsoft 관리 센터 온보드 허브에서 **의료** 를 선택한 다음 **역할별 정책 설정 할당** 을 선택하세요. 시작할 준비가 되었으면 조직의 개인을 할당할 정책 패키지를 결정합니다.

패키지의 특정 정책과 해당 설정에 대해 자세히 알아보려면 **정책 세부 정보 보기** 를 선택합니다. Teams 관리 센터에서 할당한 후 [사용자 정의할 수 있습니다](manage-policy-packages.md#customize-policies-in-a-policy-package).

할당할 패키지를 하나 또는 여러 개 선택하고 **다음** 을 누르세요. 역할에 가장 적합한 정책 패키지를 검색하여 추가할 수 있습니다. 개인은 한 번에 둘 이상의 정책 패키지에 할당할 수 없습니다.

올바른 정책 패키지에 사용자를 추가하면 선택사항이 **완료** 됩니다. Microsoft Teams 관리자 센터에서 정책 패키지를 계속 사용자 정의하고 관리할 수 있습니다.

## <a name="manage-policy-packages"></a>정책 패키지 관리

### <a name="view"></a>보기

패키지를 할당하기 전에 정책 패키지에서 각 정책의 설정을 확인합니다. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지** 로 이동하고 패키지 이름을 선택한 다음 정책 이름을 선택합니다.

미리 정의된 값이 조직에 적합한지 또는 조직의 요구 사항에 따라 더 엄격하거나 관대하게 사용자 지정해야하는지 결정합니다.

### <a name="customize"></a>사용자 지정

필요한 경우, 조직의 요구 사항에 맞게 정책 패키지에서 정책의 설정을 사용자 지정합니다. 정책 설정에 대한 모든 변경 내용은 패키지가 할당된 사용자에게 자동으로 적용됩니다. 정책 패키지의 정책 설정을 편집하려면 Microsoft Teams 관리자 센터의 왼쪽 탐색에서 **정책 패키지** 로 이동하여 정책 패키지를 선택하고 편집할 정책 이름을 선택한 다음 **편집** 을 선택하세요.

정책 패키지를 할당한 다음에도 패키지에서 정책 설정을 변경할 수 있다는 점을 잊지 마세요. 자세한 내용은 [정책 패키지에서 정책 사용자 지정](manage-policy-packages.md#customize-policies-in-a-policy-package)을 참조하세요.

### <a name="assign"></a>할당

정책 패키지를 사용자에 할당합니다. 사용자에게 정책이 할당된 후 나중에 다른 정책을 할당하는 경우 가장 최근의 할당이 우선됩니다.

> [!NOTE]
> 사용자 지정 정책 패키지 할당을 받으려면 각 사용자에게 고급 통신 추가 기능이 필요합니다. 자세한 내용은 [Microsoft Teams를 위한 고급 통신 추가 기능](/microsoftteams/teams-add-on-licensing/advanced-communications)을 참조하세요.

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>한 명의 사용자나 여러 사용자에게 정책 패키지 할당

한 명의 사용자나 여러 사용자에게 정책 패키지를 할당하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 **정책 패키지** 로 이동한 다음 **사용자 관리** 를 선택합니다.  

![관리 센터에서 정책 패키지를 할당하는 방법 스크린샷.](media/policy-packages-healthcare-assign.png)

자세한 내용은 [정책 패키지 할당](manage-policy-packages.md#assign-a-policy-package)을 참조하세요.

사용자에게 정책이 할당된 후 나중에 다른 정책을 할당하는 경우 가장 최근의 할당이 우선됩니다.

#### <a name="assign-a-policy-package-to-a-group"></a>그룹에 정책 패키지 할당

**이 기능은 비공개 리미 보기에 있습니다.**

그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다. 정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다. 그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다. 이 방법은 최대 50,000명의 사용자가 있는 그룹에 적합하지만, 더 큰 그룹에도 적용됩니다.

자세한 내용은 [그룹에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-group)을 참조하세요.

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>대규모 사용자 집합(배치)에 정책 패키지 할당

한 번에 많은 사용자에게 정책 패키지를 할당하려면 배치 정책 패키지를 사용합니다. [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet을 사용하여 대규모 사용자와 할당하려는 정책 패키지를 제출합니다. 할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.

배치에는 최대 5천 명의 사용자가 포함될 수 있습니다. 개체 ID, UPN, SIP 주소 또는 전자 메일 주소로 사용자를 지정할 수 있습니다. 자세한 내용은 [배치 사용자에게 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)을 참조하세요.

## <a name="related-topics"></a>관련 주제

[Teams에서 정책 패키지 관리](manage-policy-packages.md)

[사용자 및 그룹에 정책 패키지 할당](assign-policy-packages.md)
