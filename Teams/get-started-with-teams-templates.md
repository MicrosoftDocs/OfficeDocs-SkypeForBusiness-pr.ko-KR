---
title: Microsoft Graph
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft에서만 사용할 수 있는 팀 템플릿에 대해 Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e570faff4ec7138457f7cd52e101a0a3632d64d2
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991117"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Microsoft Graph

> [!NOTE]
> 팀 템플릿은 현재 개인 채널 만들기를 지원하지 않습니다. 개인 채널 만들기는 템플릿 정의에 포함되지 않습니다.

팀 템플릿은 Microsoft Teams 필요 또는 프로젝트를 중심으로 디자인된 팀 구조의 정의입니다. 팀 템플릿을 사용하면 미리 정의된 설정, 채널 및 앱을 사용하여 다양한 공동 작업 공간을 빠르고 쉽게 만들 수 있습니다. 팀 템플릿을 사용하면 조직 전체에 일관된 팀을 배포할 수 있습니다.

Microsoft Graph 팀 템플릿에 포함된 미리 작성된 팀 템플릿을 사용하여 팀을 Teams 수 있습니다. 이 문서에서는 템플릿에서 정의할 수 있는 속성 및 Microsoft에서만 사용할 수 있는 템플릿에 대해 Graph.

이 문서는 다음을 위한 것입니다.

- 조직 전체에서 여러 팀을 계획, 배포 및 관리하는 책임<br>
- 프로그래밍식으로 미리 정의된 채널 및 앱을 사용하여 팀을 만들고자 하는 개발자

## <a name="team-template-capabilities"></a>팀 템플릿 기능

팀의 대부분의 속성은 템플릿에 의해 포함 및 지원됩니다. 그러나 현재 지원되지 않는 몇 가지 속성 및 기능이 있습니다. 여기에 포함된 내용과 팀 템플릿에 포함되지 않은 내용에 대한 간소한 요약이 있습니다.

| **팀 템플릿에서 지원하는 팀 속성** | **팀 템플릿에서 아직 지원되지 않는 팀 속성** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 템플릿 유형 | 팀 구성원 |
| 팀 이름 | 팀 사진 |
| 팀 설명 | 채널 설정 |
| 팀 가시성(공개 또는 비공개) | 커넥터 |
| 팀 설정(예: 멤버, 게스트, @ 언급) | 파일 및 내용 |
| 자동 즐겨찾기 채널 | |
| 설치된 앱 | |
| 고정된 탭 | |

> [!NOTE]
> 지원되는 속성에 대한 최신 정보를 확인하여 향후 Microsoft Teams 서식 파일 기능을 추가할 예정입니다.

## <a name="pre-built-templates"></a>미리 작성된 템플릿

미리 작성된 팀 템플릿은 특정 산업에 대해 만든 템플릿입니다. Microsoft에서만 사용할 수 있는 미리 작성된 템플릿은 Graph.

| 템플릿 유형 | TemplateId | 이 템플릿과 함께 있는 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 표준 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 추가 앱 및 속성 없음 |
| 교육 -<br>수업 팀 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | 앱:<ul><li>OneNote 수업용 전자 필기장(일반 탭에 **고정)** </li><li>할당 앱(일반 탭에 **고정)**</li></ul> 팀 속성:<ul><li>Team 가시성을 **HiddenMembership으로** 설정(다시 설정할 수 없습니다)</li></ul> |
| 교육 -<br>직원 팀 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | 앱:<ul><li>OneNote 직원 전자 필기장(일반 탭에 **고정)**</li></ul> |
|교육 -<br>PLC 팀 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 앱:<ul><li>OneNote PLC 전자 필기장(일반 탭에 **고정)**</ul></li>|

> [!NOTE]
> 클라이언트 및 Microsoft Teams 사용할 수 있는 미리 작성된 템플릿 목록은 Graph 관리 센터에서 팀 템플릿 시작을 Teams [참조하세요.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="related-articles"></a>관련 문서

- [관리 센터에서 팀 템플릿 Teams 시작](get-started-with-teams-templates-in-the-admin-console.md)
- [팀 만들기(미리](/graph/api/team-post?view=graph-rest-beta) 보기)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
