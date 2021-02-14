---
title: 의료를 위한 Teams 정책 패키지
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
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 의료 조직의 Teams 정책 패키지를 사용 및 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: af6f5923d5c97fc03c77585ba94292264aacc027
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812858"
---
# <a name="teams-policy-packages-for-healthcare"></a>의료를 위한 Teams 정책 패키지

## <a name="overview"></a>개요

Microsoft [Teams의](manage-policy-packages.md) 정책 패키지는 조직에서 비슷한 역할이 있는 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 컬렉션입니다. 정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다. 사용자의 요구에 맞게 패키지의 정책 설정을 사용자 지정할 수 있습니다. 정책 패키지에서 정책 설정을 변경하면 해당 패키지에 할당된 모든 사용자가 업데이트된 설정을 얻습니다. Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 정책 패키지를 관리할 수 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

정책 패키지는 패키지에 따라 다음에 대한 정책을 미리 정의합니다.

- 메시징
- 모임
- 통화
- 앱 설정
- 라이브 이벤트

Teams에는 현재 다음과 같은 의료 정책 패키지가 포함되어 있습니다.

|Microsoft Teams 관리 센터의 패키지 이름|최적 용도|설명 |
|---------|---------|---------|
|의료 의료 의료진  |의료 조직의 의료 종사자  |등록된 간호사, 담당 간호사, 의사 및 소셜 작업자와 같은 의료 작업자에게 채팅, 통화, 교대 근무 관리 및 모임에 대한 모든 권한을 부여하는 정책 및 정책 설정 집합을 만듭니다. |
|의료 정보 작업자  |의료 조직의 정보 근로자 |IT 직원, 정보 보호 담당자, 재무 담당자 및 규정 준수 담당자와 같은 정보 근로자들에게 채팅, 통화 및 모임에 대한 모든 권한을 부여하는 정책 및 정책 설정 집합을 만듭니다.|
|의료 환자실  |환자실 장치|의료 조직의 환자 방에 적용되는 정책 및 정책 설정 집합을 만듭니다.|

![의료 정책 패키지 스크린샷](media/policy-packages-healthcare.png)

각 개별 정책에는 정책 패키지의 이름이 지정되어 정책 패키지에 연결된 정책을 쉽게 식별할 수 있습니다. 예를 들어 조직의 의료진에게 의료 의료진 정책 패키지를 할당하면 패키지의 각 정책에 대해 Healthcare_ClinicalWorker 정책이 만들어집니다.

![의료 의료 의료진 패키지의 정책 스크린샷](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>정책 패키지 시작

의료 정책 패키지를 시작하려면 Microsoft 관리 센터 온보더링 허브에서 **의료를** 선택한 다음 역할에 따라 정책 **설정 할당을 선택합니다.** 시작할 준비가 됐을 때 조직의 개인을 할당할 정책 패키지를 결정해야 합니다.

패키지의 **특정** 정책 및 해당 설정에 대해 자세히 알아보하려면 정책 세부 정보 보기를 선택합니다. Teams [관리 센터에서](manage-policy-packages.md#customize-policies-in-a-policy-package) 과제를 수행한 후 사용자 지정될 수 있습니다.

할당할 패키지를 하나 이상 선택하고 다음을 **클릭합니다.** 해당 역할에 가장 적합한 정책을 검색하고 정책 패키지에 추가할 수 있습니다. 한 번씩 여러 정책 패키지에 개인을 할당할 수 없습니다.

올바른 정책 패키지에 인원을 추가하면 **마침이** 선택을 완료합니다. Microsoft Teams 관리 센터에서 정책 패키지를 계속 사용자 지정하고 관리할 수 있습니다.

## <a name="manage-policy-packages"></a>정책 패키지 관리

### <a name="view"></a>보기

패키지를 할당하기 전에 정책 패키지에서 각 정책의 설정을 확인합니다. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **정책** 패키지로 이동하여 패키지 이름을 선택한 다음 정책 이름을 선택합니다.

미리 정의된 값이 조직에 적합한지 또는 조직의 요구 사항에 따라 더 엄격하거나 관대하게 사용자 지정해야하는지 결정합니다.

### <a name="customize"></a>사용자 지정

필요한 경우, 조직의 요구 사항에 맞게 정책 패키지에서 정책의 설정을 사용자 지정합니다. 정책 설정에 대한 모든 변경 내용은 패키지가 할당된 사용자에게 자동으로 적용됩니다. 정책 패키지에서 정책 설정을 편집하려면 Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 정책 패키지로 이동하여 정책 패키지를 선택하고 편집할 정책의 이름을 선택한 다음 **편집을** 선택합니다.

정책 패키지를 할당한 다음에도 패키지에서 정책 설정을 변경할 수 있다는 점을 잊지 마세요. 자세한 내용은 [정책 패키지에서 정책 사용자 지정](manage-policy-packages.md#customize-policies-in-a-policy-package)을 참조하세요.

### <a name="assign"></a>할당

사용자에게 정책 패키지를 할당합니다. 사용자에게 정책이 할당된 후 나중에 다른 정책을 할당하는 경우 가장 최근의 할당이 우선됩니다.

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>한 명의 사용자나 여러 사용자에게 정책 패키지 할당

한 명의 사용자나 여러 사용자에게 정책 패키지를 할당하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 **정책 패키지** 로 이동한 다음 **사용자 관리** 를 선택합니다.  

![관리 센터에서 정책 패키지를 할당하는 방법을 보여 주는 스크린샷](media/policy-packages-healthcare-assign.png)

자세한 내용은 [정책 패키지 할당](manage-policy-packages.md#assign-a-policy-package)을 참조하세요.

사용자에게 정책이 할당된 후 나중에 다른 정책을 할당하는 경우 가장 최근의 할당이 우선됩니다.

#### <a name="assign-a-policy-package-to-a-group"></a>그룹에 정책 패키지 할당

**이 기능은 비공개 리미 보기에 있습니다.**

그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다. 정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다. 그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다. 이 방법은 최대 50,000명의 사용자가 있는 그룹에 적합하지만, 더 큰 그룹에도 적용됩니다.

자세한 내용은 [그룹에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-group)을 참조하세요.

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>대규모 사용자 집합(배치)에 정책 패키지 할당

한 번에 많은 사용자에게 정책 패키지를 할당하려면 배치 정책 패키지를 사용합니다. [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet을 사용하여 대규모 사용자와 할당하려는 정책 패키지를 제출합니다. 할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.

배치에는 최대 5천 명의 사용자가 포함될 수 있습니다. 개체 ID, UPN, SIP 주소 또는 전자 메일 주소로 사용자를 지정할 수 있습니다. 자세한 내용은 [배치 사용자에게 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)을 참조하세요.

## <a name="related-topics"></a>관련 항목

[Teams에서 정책 패키지 관리](manage-policy-packages.md)

[Teams에서 사용자에게 정책 할당](assign-policies.md)
