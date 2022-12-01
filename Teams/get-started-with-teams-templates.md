---
title: Microsoft Graph를 사용하여 팀 템플릿 시작하기
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
- m365-frontline
- tier2
- highpri
description: Microsoft Graph에서만 사용할 수 있는 팀 템플릿에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc753913c90703295180765d7961c3747063011f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198300"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Microsoft Graph를 사용하여 팀 템플릿 시작하기

> [!NOTE]
> 팀 템플릿은 현재 비공개 채널 만들기를 지원하지 않습니다. 프라이빗 채널 만들기는 템플릿 정의에 포함되지 않습니다.

Microsoft Teams의 팀 템플릿은 비즈니스 요구 사항 또는 프로젝트를 중심으로 설계된 팀 구조의 정의입니다. 팀 템플릿을 사용하면 미리 정의된 설정, 채널 및 앱을 사용하여 풍부한 공동 작업 공간을 빠르고 쉽게 만들 수 있습니다. 팀 템플릿은 조직 전체에 일관된 팀을 배포하는 데 도움이 될 수 있습니다.

Microsoft 그래프를 사용하면 [고유한 템플릿을 만들](/graph/api/resources/teamtemplate?view=graph-rest-beta&preserve-view=true)거나 Teams에 포함된 미리 빌드된 팀 템플릿을 사용하여 팀을 만들 수 있습니다. 이 문서에서는 템플릿에서 정의할 수 있는 속성과 Microsoft Graph에서만 사용할 수 있는 미리 빌드된 템플릿에 대해 알아봅니다.

이 문서는 다음과 같은 경우에 적합합니다.

- 조직 전체에서 여러 팀 계획, 배포 및 관리 담당<br>
- 미리 정의된 채널 및 앱을 사용하여 프로그래밍 방식으로 팀을 만들려는 개발자

## <a name="team-template-capabilities"></a>팀 템플릿 기능

팀의 대부분의 속성은 템플릿에서 포함되고 지원됩니다. 그러나 현재 지원되지 않는 몇 가지 속성과 기능이 있습니다. 다음은 포함된 항목과 팀 템플릿에 포함되지 않은 항목에 대한 간략한 요약입니다.

| **팀 템플릿에서 지원하는 팀 속성** | **팀 템플릿에서 아직 지원되지 않는 팀 속성** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 서식 파일 유형 | 팀 구성원 |
| 팀 이름 | 팀 사진 |
| 팀 설명 | 채널 설정 |
| 팀 가시성(퍼블릭 또는 프라이빗) | 커넥터 |
| 팀 설정(예: 멤버, 게스트, @ 멘션) | 파일 및 내용 |
| 자동 즐겨찾기 채널 | |
| 앱 설치됨 | |
| 고정된 탭 | |

> [!NOTE]
> Microsoft Teams의 향후 릴리스에서 더 많은 템플릿 기능을 추가할 예정이므로 지원되는 속성에 대한 최신 정보를 다시 확인하세요.

## <a name="pre-built-templates"></a>미리 빌드된 템플릿

미리 빌드된 팀 템플릿은 특정 산업을 위해 만든 템플릿입니다. 다음은 Microsoft Graph에서만 사용할 수 있는 미리 빌드된 템플릿입니다.

| 서식 파일 유형 | TemplateId | 이 템플릿과 함께 제공되는 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 표준 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 추가 앱 및 속성 없음 |
| 교육-<br>수업 팀 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | 앱:<ul><li>OneNote 수업용 전자 필기장( **일반** 탭에 고정) </li><li>할당 앱( **일반** 탭에 고정됨)</li></ul> 팀 속성:<ul><li>**HiddenMembership** 으로 설정된 팀 표시 유형(재정의할 수 없음)</li></ul> |
| 교육-<br>교직원 팀 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | 앱:<ul><li>OneNote 교직원용 전자 필기장( **일반** 탭에 고정)</li></ul> |
|교육-<br>PLC 팀 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 앱:<ul><li>OneNote PLC Notebook( **일반** 탭에 고정됨)</ul></li>|

> [!NOTE]
> Teams 클라이언트 및 Microsoft Graph에서 사용할 수 있는 미리 빌드된 템플릿 목록은 [Teams 관리 센터에서 팀 템플릿 시작을](get-started-with-teams-templates-in-the-admin-console.md) 참조하세요.

## <a name="related-articles"></a>관련 기사

- [Teams 관리 센터에서 팀 템플릿 시작하기](get-started-with-teams-templates-in-the-admin-console.md)
- [팀 만들기](/graph/api/team-post?view=graph-rest-beta&preserve-view=true) (미리 보기)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps&preserve-view=true)
