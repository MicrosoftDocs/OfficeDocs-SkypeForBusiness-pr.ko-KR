---
title: 관리 센터에서 팀 템플릿 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 관리 센터에서 팀 템플릿을 관리하는 방법 알아보기
ms.openlocfilehash: 5370353b38813230ab4329f8a5ad7368efe6c916
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198310"
---
# <a name="manage-team-templates-in-the-admin-center"></a>관리 센터에서 팀 템플릿 관리

관리 센터에서 템플릿 정책을 만들어 최종 사용자가 볼 수 있는 팀 템플릿을 관리합니다. 각 템플릿 정책 내에서 표시되거나 숨겨진 템플릿을 지정할 수 있습니다.
사용자가 지정된 팀 템플릿의 하위 집합만 볼 수 있도록 다른 템플릿 정책에 다른 사용자를 할당합니다.

템플릿 정책을 관리하는 방법을 알아보려면 이 짧은 비디오를 시청하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-templates-policies-and-assign-available-templates"></a>템플릿 정책 만들기 및 사용 가능한 템플릿 할당

1. Teams 관리 센터에 로그인합니다.

2. **Teams** > **템플릿 정책으로** 이동합니다.

3. **추가** 를 선택합니다.

    ![템플릿 정책이 선택되고 추가가 강조 표시됩니다.](media/template-policies-1.png)

1. 정책 이름을 지정하고 간단한 설명을 추가합니다.

2. **보기 가능한 템플릿** 목록에서 숨기려는 템플릿을 선택한 다음 **숨기기** 를 선택합니다.

    ![숨기기가 강조 표시된 선택한 템플릿입니다.](media/template-policies-2.png)

    숨겨진 템플릿 목록에서 숨기도록 선택한 템플릿을 볼 수 **있습니다** .

1. 특정 템플릿의 숨기기를 취소하려면 **숨겨진 템플릿 목록으로** 이동합니다.

2. 숨기기를 취소할 템플릿을 선택한 다음 **표시** 를 선택합니다.

   ![숨겨지지 않은 선택한 템플릿입니다.](media/template-policies-3.png)

   선택한 템플릿이 **보기 가능한 템플릿** 목록에 표시됩니다.
3. **저장** 을 선택합니다.

   새 템플릿 정책이 **템플릿 정책** 목록에 표시됩니다.

## <a name="assign-templates-policies-to-users"></a>사용자에게 템플릿 정책 할당

일괄 할당을 통해 개별적으로 또는 대규모로 사용자에게 템플릿 정책을 직접 할당할 수 있습니다. 새 정책이 사용자에게 적용되는 데 최대 24시간이 걸릴 수 있습니다.

> [!Note]
> 현재 보안 그룹의 모든 사용자와 같은 그룹 멤버 자격에 따라 사용자에게 템플릿 정책을 할당하는 것은 지원되지 않습니다. 이 기능은 나중에 사용할 수 있습니다.

Teams에서 정책을 할당하는 방법에 대한 개요는 Teams [에서 정책 할당을 참조하세요](policy-assignment-overview.md).

### <a name="assign-a-templates-policy-to-individual-users"></a>개별 사용자에게 템플릿 정책 할당

Teams 관리 센터 또는 PowerShell을 사용하여 개별 사용자 또는 소수의 사용자에게 템플릿 정책을 한 번에 할당할 수 있습니다. 자세한 내용은 [개별 사용자에게 정책 할당을 참조하세요](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users).

### <a name="assign-a-templates-policy-to-a-batch-of-users"></a>사용자 일괄 처리에 템플릿 정책 할당

PowerShell을 사용하여 한 번에 많은 사용자 집합에 템플릿 정책을 할당할 수 있습니다. 이렇게 하려면 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 TeamsTemplatePermissionPolicy와 함께 으로 ```PolicyType``` 사용하여 사용자 일괄 처리 및 할당하려는 템플릿 정책을 제출합니다. 예를 들면 다음과 같습니다.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName <Any operation name> -PolicyType TeamsTemplatePermissionPolicy -PolicyName <policy name> -Identity <users identity | list of user identities>
```

할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다. 그런 다음 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 할당의 진행률 및 상태를 추적할 수 있습니다.

자세한 내용은 [PowerShell을 사용하여 사용자 일괄 처리에 정책 할당을](assign-policies-users-and-groups.md#use-powershell-method) 참조하세요.

## <a name="size-limits-for-templates-policies"></a>템플릿 정책에 대한 크기 제한

정책당 최대 100개의 템플릿을 숨길 수 있습니다. 지정된 정책에 이미 100개의 템플릿이 숨겨져 있으면 **숨기기** 단추가 비활성화됩니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**Q: 새 템플릿이 만들어지면 템플릿이 내 정책에 포함되나요?**

A: 모든 새 템플릿은 기본적으로 표시됩니다. 템플릿 정책 섹션의 관리 센터에서 템플릿을 숨기도록 선택할 수 있습니다.

**Q: 템플릿이 삭제되면 어떻게 되나요?**

A: 삭제된 템플릿은 더 이상 템플릿 정책에 존재하지 않습니다.

**Q: Teams 관리 센터의 템플릿 정책에 여러 사용자를 할당할 수 있나요?**

A: 예.

1. Teams 관리 센터에서 **사용자 관리 사용자** > 로 이동합니다.
1. 사용자 목록에서 템플릿 정책에 할당할 사용자를 선택합니다.
1. **설정 편집** 을 선택한 다음 **템플릿 정책** 에서 할당할 정책을 선택합니다.
1. **적용** 을 선택합니다.

자세한 내용은 [개별 사용자에게 정책 할당을 참조하세요](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users).

**Q: 특정 정책에 할당된 모든 사용자를 볼 어떻게 할까요? 있나요?**

A: Teams 관리 센터에서 다음을 수행합니다.

1. **사용자 관리 사용자** > 로 이동합니다.
2. **필터** 를 선택하고 템플릿 정책에 대한 필터를 설정한 다음 **적용** 을 선택합니다.

    ![선택한 템플릿 정책 및 보기 사용자입니다.](media/template-policies-5.png)

**Q: PowerShell을 통해 템플릿 정책을 관리할 수 있나요?**

A: 아니요, PowerShell에서 템플릿 정책 관리는 지원되지 않습니다. 그러나 PowerShell을 사용하여 사용자에게 [템플릿 정책을 할당](#assign-templates-policies-to-users) 할 수 있습니다.

**Q: 템플릿 정책이 EDU에 적용 가능합니까?**

A: 아니요, EDU에 대한 템플릿 정책은 지원되지 않습니다.

## <a name="related-articles"></a>관련 기사

- [관리 센터에서 팀 템플릿 시작](./get-started-with-teams-templates-in-the-admin-console.md)

- [사용자 지정 팀 템플릿 만들기](./create-a-team-template.md)

- [기존 팀에서 템플릿 만들기](./create-template-from-existing-team.md)

- [기존 팀 템플릿에서 팀 템플릿 만들기](./create-template-from-existing-template.md)

- [Microsoft Teams에서 사용자에게 정책 할당 - Microsoft Teams \| Microsoft Docs](./policy-assignment-overview.md)

- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
