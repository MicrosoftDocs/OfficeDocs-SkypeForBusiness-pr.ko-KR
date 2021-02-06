---
title: 관리 센터에서 Teams 서식 파일 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 관리 센터에서 Teams 서식 파일을 관리하는 방법 배우기
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ef765013541ae740211cc5666da3544f1cd5b528
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125905"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a>관리 센터에서 Teams 서식 파일 만들기 및 관리

[!INCLUDE [preview-feature](includes/preview-feature.md)]

관리 센터에서 서식 파일 정책을 만들어 최종 사용자에게 표시되는 Teams 서식 파일을 관리합니다. 각 템플릿 정책 내에서 표시되거나 숨겨진 템플릿을 지정합니다.
사용자가 지정된 Teams 템플릿의 하위 집합만 볼 수 있도록 다른 서식 파일 정책에 다른 사용자를 할당합니다.

## <a name="create-template-policies-and-assign-available-templates"></a>템플릿 정책 만들기 및 사용 가능한 템플릿 할당

1. Teams 관리 센터에 로그인합니다.

2. **Teams 서식 파일** 정책을  >  **확장합니다.**

3. **추가** 를 선택합니다.

    ![템플릿 정책이 선택되어 추가가 강조 표시](media/template-policies-1.png)

1. 템플릿 **정책 설정 섹션에서** 다음 필드를 완료합니다.

    - 템플릿 정책 이름

    - 템플릿 정책 간략한 설명

2. 보기 가능한 **서식** 파일 테이블에서 숨기고 싶은 서식 파일을 선택하고 숨기기 를 **선택합니다.**

    ![숨기기 강조 표시된 선택한 서식 파일](media/template-policies-2.png)

    숨겨진 서식 파일 테이블에서 숨기기 위해 선택한 서식 파일을 볼 **수** 있습니다.

1. 특정 템플릿의 숨기기를 숨기지하려면 숨겨진 서식 파일 **테이블로 스크롤합니다.**

1. 서식 파일을 선택하여 표시를 선택하지 않은 다음 **표시를 선택합니다.**

   ![숨기기 강조 표시된 선택한 서식 파일](media/template-policies-3.png)

   선택한 서식 파일은 보기 가능한 서식 파일 **테이블에** 표시됩니다.
3. 저장을 **선택합니다.**

   새 템플릿 정책이 템플릿 정책 **목록에** 표시됩니다.

## <a name="assign-users-to-the-template-policies"></a>템플릿 정책에 사용자 할당

정책에 할당된 사용자는 해당 정책 내에서만 볼 수 있는 템플릿을 볼 수 있습니다.

1. 템플릿 **정책에서** 정책을 선택한 다음 사용자 관리를 **선택합니다.**

2. 이 정책에 할당할 사용자를 입력합니다.

   ![숨기기 강조 표시된 선택한 서식 파일](media/template-policies-4.png)

3. 적용을 **선택합니다.**

> [!Note]
> 새 정책이 최종 사용자에게 적용될 경우 최대 24시간이 걸릴 수 있습니다.

## <a name="size-limits-for-template-policies"></a>템플릿 정책에 대한 크기 제한

정책당 최대 100개 템플릿을 숨길 수 있습니다. 주어진 **정책에** 이미 100개 템플릿이 숨겨져 있는 경우 숨기기 단추가 비활성화됩니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**Q: 사용자를 팀 템플릿 정책에 일괄 할당할 수 있나요?**
  
A: 예, PowerShell에서 템플릿 정책에 대한 일괄 처리 할당을 지원합니다. 이 작업의 정책 유형은 TeamsTemplatePermissionPolicy입니다. [더 알아보세요](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

**Q: 그룹을 팀 템플릿 정책에 할당할 수 있나요?**

A: 현재는 아니요. 이 기능은 향후 제공될 예정입니다.

**Q: 새 템플릿을 만든 경우 템플릿이 내 정책에 포함하나요?**

A: 새 템플릿은 기본적으로 표시됩니다. 템플릿 정책 섹션의 관리 센터에서 템플릿을 숨기기 위해 선택할 수 있습니다.

**Q: 서식 파일을 삭제하면 어떻게 하나요?**

A: 삭제된 템플릿은 더 이상 템플릿 정책에 존재하지 않습니다.

**Q: Teams 관리 센터의 서식 파일 정책에 여러 사용자를 할당할 수 있나요?**

A: 예.

1. 관리 센터에서 사용자로 **이동**
1. 사용자 목록 테이블에서 특정 템플릿 정책에 할당할 사용자를 선택합니다.
1. 설정 편집을 선택하고 템플릿 정책 필드를 변경합니다.
1. 적용을 선택합니다.
   Microsoft [Teams - Microsoft Teams \| Microsoft Docs에서](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)사용자에게 정책 할당에 대해 자세히 배정합니다.

**Q: 특정 정책에 할당된 모든 사용자를 어떻게 볼 수 있나요?**

A: 관리 센터에서:

1. 사용자 **섹션으로** 이동
2. 사용자 목록 테이블에서 필터를 선택하고 팀 템플릿 정책을 필터링합니다.
3. 적용을 **선택합니다.**

![숨기기 강조 표시된 선택한 서식 파일](media/template-policies-5.png)

**Q: PowerShell을 통해 템플릿 정책을 관리할 수 있나요?**

A: 아니요, 지원되지 않습니다.

**Q: 템플릿 정책이 EDU에 적용 가능한가요?**

A: 아니요, 지원되지 않습니다.

## <a name="related-topics"></a>관련 항목

- [관리 센터에서 팀 서식 파일 시작](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [사용자 지정 팀 서식 파일 만들기](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [기존 팀에서 서식 파일 만들기](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [기존 팀 서식 파일에서 팀 서식 파일 만들기](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [Microsoft Teams에서 사용자에게 정책 할당 - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies)

- [TeamsTemplatePermissionPolicy](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)