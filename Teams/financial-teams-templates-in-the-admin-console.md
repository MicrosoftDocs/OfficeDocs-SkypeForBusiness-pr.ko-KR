---
title: 금융 팀 템플릿 사용
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Teams 관리 센터와 Microsoft Graph에서 금융 팀 템플릿을 관리하고 사용하여 금융 서비스 조직을 위한 팀을 빠르고 쉽게 만드는 방법을 알아보세요.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51ec855bc9065bb65c0f6eae14a3e41683cfbc6f
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046134"
---
# <a name="use-financial-team-templates"></a>금융 팀 템플릿 사용

Microsoft Teams의 팀 템플릿을 사용하면 설정, 채널 및 사전 설치된 앱의 미리 정의된 팀 구조를 제공하여 팀을 빠르고 쉽게 만들 수 있습니다.

금융 서비스 조직의 경우 팀 템플릿은 조직 전체에 일관된 팀을 신속하게 배포하는 데 도움이 되므로 특히 강력할 수 있습니다. 템플릿은 또한 직원이 Teams를 효과적으로 사용하는 방법에 대해 방향을 잡는 데 도움이 됩니다.

Teams에는 금융 서비스 조직을 위해 설계된 템플릿이 포함되어 있습니다. 이러한 미리 빌드된 서식 파일을 사용하여 직원들이 커뮤니케이션하고 공동 작업할 수 있는 팀을 빠르게 만들 수 있습니다. 이 게시물에서는 이러한 각 템플릿을 소개하고 사용 방법을 권장합니다.

팀 템플릿을 관리하고 사용하는 방법은 관리자인지 개발자인지에 따라 다릅니다.

|다음과 같은 경우: | 그렇다면 귀하는: |
| ---- | --------- |
| 관리자 또는 IT 전문가 |[Teams 관리자 센터에서 팀 템플릿을 관리합니다](#manage-team-templates-in-the-teams-admin-center). 팀 템플릿을 보고 템플릿 정책을 적용하여 직원이 팀을 만들기 위해 Teams에서 사용할 수 있는 템플릿을 제어합니다. |
| 개발자 | [Microsoft Graph를 사용](#use-team-templates-with-microsoft-graph)하여 팀 템플릿에서 팀을 만듭니다. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 관리 센터에서 팀 템플릿 관리

관리자는 Microsoft Teams 관리 센터에서 팀 템플릿을 관리할 수 있습니다. 여기에서 각 템플릿에 대한 세부 정보를 볼 수 있습니다. 또한 [템플릿 정책을 만들고 할당](templates-policies.md)하여 직원이 [팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)를 위해 Teams에서 보게 될 템플릿을 제어할 수 있습니다.

일반적인 팀 템플릿에 대한 자세한 내용은 [Teams 관리 센터에서 팀 템플릿 시작하기](get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.

현재 금융 서비스 조직을 위해 다음과 같은 미리 빌드된 팀 템플릿을 제공합니다. 이를 보려면 Teams 관리 센터의 왼쪽 탐색 메뉴에서 **팀** > **팀 템플릿** 으로 이동하세요.

### <a name="collaborate-within-a-bank-branch"></a>은행 지점 안에서 공동 작업

주택 담보 대출 공동 작업과 같은 허들, 고객 모임, 비즈니스 프로세스 전반에 걸쳐 사용자 은행 지점 직원들의 공동 작업을 중앙에 집중시키고 공지 사항 및 포상과 관련하여 모든 사용자들이 계속 진행 상황을 알 수 있도록 합니다.

| 서식 파일 유형 |TemplateId| 이 템플릿과 함께 제공되는 속성 |
| ------------------ |--|----------------------------------------------------- |
|은행 지점| `CollaborateWithinABankBranch`|채널 <ul><li>일반<li>공지 사항</li><li>장애 요소</li><li>고객 모임</li><li>승인 요청 </li><li>코칭</li><li>기술 개발</li><li>대출 처리</li><li>고객 불만 사항</li><li>쿠도스</li><li>재미있는 내용</li><li>규정 준수</li></ul>앱:<ul><li>칭찬 </li><li>문제 보고자</li><li>Wiki</li><li>일정</li><li>승인</li><li>게시판</li><li>아이디어</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>Microsoft Graph에서 팀 템플릿 사용

개발자는 Microsoft Graph를 사용해 미리 작성된 팀 템플릿을 사용해 팀을 만들 수 있습니다. Microsoft Graph에서 팀 템플릿을 사용하는 방법에 관한 자세한 내용은 [Microsoft Graph를 사용하여 팀 템플릿 시작하기](get-started-with-teams-templates.md), [Microsoft Teams API 개요](/graph/teams-concept-overview?view=graph-rest-1.0) 및 [teamsTemplate 리소스 유형](/graph/api/resources/teamstemplate?view=graph-rest-1.0)을 참조하세요.

### <a name="bank-branch"></a>은행 지점

주택 담보 대출 공동 작업과 같은 허들, 고객 모임, 비즈니스 프로세스 전반에 걸쳐 사용자 은행 지점 직원들의 공동 작업을 중앙에 집중시키고 공지 사항 및 포상과 관련하여 모든 사용자들이 계속 진행 상황을 알 수 있도록 합니다.

| 서식 파일 유형 |TemplateId| 템플릿 채널 |
| ------------------ |--|----------------------------------------------------- |
|은행 지점|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|일반<br>공지 사항<br>장애 요소<br>고객 모임<br>승인 요청<br>코칭<br>기술 개발<br>대출 처리<br>고객 불만 사항<br>쿠도스<br>재미있는 내용<br>규정 준수|
||||

> [!NOTE]
> 금융 서비스 조직에 적용되는 추가 팀 템플릿은 [중소기업용 Microsoft Graph에서 빌드된 팀 템플릿](smb-templates.md)을 참조하세요.

## <a name="related-articles"></a>관련 기사

- [Teams 관리 센터에서 팀 템플릿 시작하기](get-started-with-teams-templates-in-the-admin-console.md)
- [템플릿으로 팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Microsoft Graph를 사용하여 팀 템플릿 시작하기](get-started-with-teams-templates.md)