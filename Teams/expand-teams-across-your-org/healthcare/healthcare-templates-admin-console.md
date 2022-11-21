---
title: 팀 의료 서식 파일 사용
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Teams 관리 센터와 Microsoft Graph에서 의료 팀 템플릿을 관리하고 사용하여 의료 조직을 위한 팀을 빠르고 쉽게 만드는 방법을 알아보세요.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a80d36b51d3f45ca906525d93e502dbfbba1cb6d
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131077"
---
# <a name="use-healthcare-team-templates"></a>팀 의료 서식 파일 사용

Microsoft Teams의 팀 템플릿을 사용하면 설정, 채널 및 사전 설치된 앱의 미리 정의된 팀 구조를 제공하여 팀을 빠르고 쉽게 만들 수 있습니다.

의료 조직의 경우 팀 템플릿은 조직 전체에 일관된 팀을 신속하게 배포하는 데 도움이 되므로 특히 강력할 수 있습니다. 템플릿은 또한 직원이 Teams를 효과적으로 사용하는 방법에 대해 방향을 잡는 데 도움이 됩니다.

Teams에는 의료 기관을 위해 특별히 설계된 템플릿이 포함되어 있습니다. 이러한 미리 빌드된 템플릿을 사용하여 직원이 환자 치료 또는 운영 요구 사항에 대해 의사 소통하고 협업할 팀을 빠르게 만들 수 있습니다. 이 게시물에서는 이러한 각 템플릿을 소개하고 사용 방법을 권장합니다.

팀 템플릿을 관리하고 사용하는 방법은 관리자인지 개발자인지에 따라 다릅니다.

|다음과 같은 경우: | 그렇다면 귀하는: |
| ---- | --------- |
| 관리자 또는 IT 전문가 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 개발자 | [Microsoft Graph를 사용](#use-team-templates-with-microsoft-graph)하여 팀 템플릿에서 팀을 만듭니다. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 관리 센터에서 팀 템플릿 관리

관리자는 Microsoft Teams 관리 센터에서 팀 템플릿을 관리할 수 있습니다. 여기에서 각 템플릿에 대한 세부 정보를 볼 수 있습니다. 또한 [템플릿 정책을 만들고 할당](../../templates-policies.md)하여 직원이 [팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)를 위해 Teams에서 보게 될 템플릿을 제어할 수 있습니다.

일반적인 팀 템플릿에 대한 자세한 내용은 [Teams 관리 센터에서 팀 템플릿 시작하기](../../get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.

현재 다음과 같은 미리 빌드된 의료 팀 템플릿을 제공합니다. 이를 보려면 Teams 관리 센터의 왼쪽 탐색 메뉴에서 **팀** > **팀 템플릿** 으로 이동하세요.
### <a name="patient-care"></a>환자 간호

 이 서식 파일은 병동, 병실 또는 부서 내에서 의사소통과 공동 작업을 하기 위한 서식 파일입니다. 이 템플릿을 사용하여 병동의 환자 관리 및 운영 요구 사항을 용이하게 할 수 있습니다. 예를 들어, *공지* 채널에 병동 공지를 게시하고 *직원* 채널에서 교대조를 관리합니다.

| 서식 파일 유형 |TemplateId| 이 템플릿과 함께 제공되는 속성 |
| ------------------ |---|----------------------------------------------------- |
| 환자 간호 |`healthcareWard` | 채널<ul><li>일반</li><li>공지 사항<ul><li>게시판&sup1;</li></ul></li><li>장애물<ul><li>목록(마지막 환자)&sup1;</li></ul></li><li>회진<ul><li>검사&sup1;</li></ul></li><li>직원</li><li>교육</li></ul> 앱: <ul><li>Wiki</li><li>목록</li><li>작업</li><li>승인</li><li>교대 근무</li><li>게시판</li><li>검사</li></ul>|
||||

&sup1;앱이 탭으로 채널에 추가되었습니다.
### <a name="hospital"></a>병원

이 서식 파일은 병원 내에서 여러 병동, 병실, 부서 간 의사소통과 공동 작업을 수행하기 위해 제작되었습니다. 이 서식 파일에는 병원 운영을 위한 채널 집합이 포함되어 있으며 추가 사용자 지정을 위해 확장할 수 있습니다.

| 서식 파일 유형 |TemplateId | 이 템플릿과 함께 제공되는 속성 |
| ------------------|-- |----------------------------------------------------- |
|병원|`healthcareHospital`|채널 <ul><li>일반<ul><li>목록&sup1;</li></ul></li><li>공지<ul><li>게시판&sup1;</li></ul></li><li>규정 준수</li><ul><li>검사&sup1;</li></ul></li><li>보호</li><li>인적 리소스<ul><li>아이디어&sup1;</li></ul></li><li>약국</li></ul> 앱: <ul><li>Wiki</li><li>작업</li><li>목록</li><li>승인</li><li>교대 근무</li><li>게시판</li><li>검사</li><li>아이디어</li></ul>|
||||

&sup1;앱이 탭으로 채널에 추가되었습니다.
## <a name="use-team-templates-with-microsoft-graph"></a>Microsoft Graph에서 팀 템플릿 사용

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](../../get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview), and [teamsTemplate resource type](/graph/api/resources/teamstemplate).

다음은 미리 빌드된 의료 팀 템플릿입니다.
### <a name="ward"></a>병동

병동 서식 파일은 병동, 병실 또는 부서 내에서 의사소통과 공동 작업을 하기 위한 서식 파일입니다. 이 서식 파일을 사용하여 병동의 환자 관리 및 운영 요구 사항을 용이하게 만들 수 있습니다. 예를 들어, 병동 공지 사항을 *공지 사항* 채널에서 게시하고 *직원* 에서 교대 근무를 관리할 수 있습니다. 병동 작업을 간소화하고자 하는 경우, 이 서식 파일이 매우 적합합니다.

|템플릿 유형 |TemplateId |템플릿 채널|
|:--- |:---|:---|
|의료 - 병동 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 일반<br>공지&sup2; <br> 장애요인&sup2; <br> 회진&sup2; <br> 직원관리&sup2; <br> 교육&sup2; |
|     | |         |

&sup2;자동 즐겨찾기 채널

### <a name="hospital"></a>병원

이 병원 서식 파일은 병원 내에서 여러 병동, 병실, 부서 간 의사소통과 공동 작업을 수행하기 위해 제작되었습니다. 이 템플릿에는 *공지*, *보호* 및 *약국* 과 같은 여러 운영 채널이 포함되어 있습니다. 또한 추가 부서 또는 전문 채널로 템플릿을 확장하는 데 사용할 수 있는 스크립트를 제공합니다. 필요에 맞게 편집할 수 있습니다.

예를 들어 *내분비학* 부서가 있지만 *안과* 채널이 필요하지 않은 경우 스크립트를 조정하여 *내분비학* 채널을 포함하고 *안과* 채널을 제거할 수 있습니다. 알림 포화 상태를 방지하기 위해 이러한 특수 또는 병동 모델의 채널은 자동 즐겨찾기하지 않는 것이 좋습니다. 사용자는 일반적으로 관련이 있는 모든 채널을 즐겨찾습니다.

|서식 파일 유형 |TemplateId |템플릿 채널|
|:--- |:---|:---|
|의료 - 병원 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 일반<br>공지&sup2; <br> 준수2; <br> 보호 <br> 인적 리소스 <br> 약국 |
| | |  |

&sup2;자동 즐겨찾기 채널

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Microsoft Graph에서 팀 템플릿을 사용하는 방법

이러한 템플릿을 사용하려면 요청 본문의 'template@odata.bind' 속성을 'standard'에서 위의 TemplateIds로 변경하세요. 팀 템플릿을 배포하는 방법에 대한 자세한 내용은 [팀 만들기](/graph/api/team-post?view=graph-rest-beta) 방법에 대한 Microsoft Graph 문서를 참조하세요.

> [!NOTE]
> 템플릿의 채널은 **일반** 탭 아래에 자동으로 생성됩니다.

#### <a name="example-hospital-template-extension-script"></a>예: 병원 템플릿 확장 스크립트

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-articles"></a>관련 기사

- [템플릿으로 팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Teams 관리 센터에서 팀 템플릿 시작하기](../../get-started-with-teams-templates-in-the-admin-console.md)
- [Microsoft Graph를 사용하여 팀 템플릿 시작하기](../../get-started-with-teams-templates.md)
- [의료 조직을 위한 Teams 시작](/microsoft-365/frontline/teams-in-hc?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)