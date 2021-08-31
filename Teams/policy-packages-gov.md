---
title: Teams 정책 패키지
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: medium
search.appverid: MET150
description: 정부 조직에 대한 Teams 정책 패키지를 사용 및 관리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 8f0b998540121e05f4113b298446dffefc832cb5
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731987"
---
# <a name="teams-policy-packages-for-government"></a>Teams 정책 패키지

> [!NOTE]
> 정책 패키지는 현재 고가 또는 DoD Microsoft 365 정부 GCC 사용할 수 없습니다.

## <a name="overview"></a>개요

Microsoft Teams의 [정책 패키지](manage-policy-packages.md)는 조직에서 유사한 역할을 가진 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 모음입니다. 정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다. 사용자의 요구 사항에 맞게 패키지의 정책 설정을 사용자 정의할 수 있습니다. 정책 패키지의 정책 설정을 변경하면 해당 패키지에 할당된 모든 사용자에게 업데이트된 설정이 제공됩니다. Microsoft Teams 관리자 센터 또는 PowerShell을 사용하여 정책 패키지를 관리할 수 있습니다.

정책 패키지는 패키지에 따라 다음에 대한 정책을 미리 정의합니다.

- 메시지
- 모임
- 통화
- 앱 설정
- 라이브 이벤트

Teams 정부에 대한 다음 정책 패키지가 포함되어 있습니다.

|Microsoft Teams 관리 센터의 패키지 이름|최적 용도|설명 |
|---------|---------|---------|
|공공 안전 책임자  |정부 조직의 공공 안전 책임자  |조직의 공공 안전 책임자에 적용되는 정책 및 정책 설정 집합을 만듭니다. |
|프런트라인 관리자  |정부 조직의 프런트라인 관리자 |정책 집합을 만들고 해당 설정을 조직의 Frontline Manager에 적용합니다.|
|프런트라인 작업자  |정부 조직의 프런트라인 작업자 |정책 집합을 만들고 해당 설정을 조직의 Frontline Workers에 적용합니다.|

![의료 정책 패키지 스크린샷.](media/policy-packages-gov.png)

각 개별 정책은 정책 패키지의 이름이 지정되며 정책 패키지에 연결된 정책을 쉽게 식별할 수 있습니다. 예를 들어 조직의 사용자에게 공용 안전 책임자 정책 패키지를 할당하면 패키지의 각 PublicSafety_Officer 정책이 만들어집니다.

![Healthcare 임상근로자 패키지의 정책 스크린샷.](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>정책 패키지 관리

### <a name="view"></a>보기

패키지를 할당하기 전에 정책 패키지에서 각 정책의 설정을 확인합니다. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지** 를 선택하고 패키지 이름을 선택한 다음 정책 이름을 선택합니다.

미리 정의된 값이 조직에 적합한지 또는 조직의 요구 사항에 따라 더 엄격하거나 관대하게 사용자 지정해야하는지 결정합니다.

### <a name="customize"></a>사용자 지정

필요한 경우, 조직의 요구 사항에 맞게 정책 패키지에서 정책의 설정을 사용자 지정합니다. 정책 설정에 대한 모든 변경 내용은 패키지가 할당된 사용자에게 자동으로 적용됩니다. 정책 패키지에서 정책 설정을 편집하려면 Microsoft Teams 관리 센터에서 정책 패키지를 선택하고 편집하려는 정책 이름을 선택한 다음 **편집** 을 선택합니다.

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
