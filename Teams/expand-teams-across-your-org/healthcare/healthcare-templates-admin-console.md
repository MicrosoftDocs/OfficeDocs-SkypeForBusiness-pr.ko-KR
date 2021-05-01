---
title: Teams 의료 서식 파일을 사용하여 팀 만들기
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 관리 센터 또는 Microsoft Graph에서 Microsoft Teams 서식 파일을 사용하여 설정, 채널 및 앱의 미리 정의된 서식 파일을 제공함으로써 팀을 쉽고 빠르게 만들 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13b85818101e1c3d42ae6dc715274ac23453e178
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117876"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Teams 의료 서식 파일을 사용하여 팀 만들기

Microsoft Teams 서식 파일을 사용하면 미리 정의된 설정, 채널 및 미리 설치된 앱 서식 파일을 제공하여 팀을 쉽고 빠르게 만들 수 있습니다.

서식 파일은 사용자가 Teams를 효과적으로 사용하는 방법을 통해 방향을 정할 수 있는 구조를 제공하기 때문에 특히 강력할 수 있습니다. 또한 관리자는 서식 파일을 사용하여 조직 전체에 일관된 팀을 배포할 수 있습니다. 이 문서는 의료 조직 전반에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우 사용할 수 있습니다.

다음과 같은 Teams 의료 서식 파일을 사용하여 팀을 만드는 방법을 선택합니다.

| Who | 사용 방법: |
| ---- | --------- |
| 관리자 및 IT 전문가 | [Teams 관리 센터를 사용](#use-the-teams-templates-in-the-teams-admin-center)하여 의료 팀 서식 파일을 기반으로 팀을 만드세요.|
| 개발자 및 시스템 통합자 | [Microsoft Graph를 사용](#use-the-teams-templates-with-the-microsoft-graph)하여 의료 팀 서식 파일을 기반으로 팀을 만들 수 있습니다. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Teams 관리 센터에서 Teams 서식 파일 사용

Microsoft Teams 관리자는 Teams 서식 파일이 있는 Teams 관리 센터를 사용하여 팀을 만들 수 있습니다. Microsoft는 현재 다양한 상황에서 사용할 수 있는 두 가지 일선 의료 서식 파일을 제공합니다. 일반적인 팀 서식 파일에 대한 자세한 내용은 [관리 센터에서 Teams 서식 파일 시작하기](../../get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.

### <a name="collaborate-on-patient-care"></a>환자 관리 공동 작업

 병동, 병실 또는 부서 내에서 의료 커뮤니케이션 및 공동 작업을 간소화합니다. 이 서식 파일을 사용하여 병동의 환자 관리 및 운영 요구 사항을 용이하게 만들 수 있습니다.

| 기본 서식 파일 형식 |baseTemplateId| 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------ |---|----------------------------------------------------- |
| 환자 관리 공동 작업 |`healthcareWard` | 채널<ul><li>일반</li><li>공지 사항</li><li>장애 요소</li><li>라운드</li><li>직원</li><li>교육</li></ul> 앱: <ul><li>Wiki</li><li>목록</li></ul>|
||||

### <a name="hospital"></a>병원

병원 내에서 여러 병동, 병실, 부서 간 의사소통과 공동 작업을 간소화할 수 있습니다. 이 템플릿은 병원 운영을 위한 기본 채널 집합을 포함하며, 자체 확장을 통해 관계, 특별 업무를 포함할 수 있습니다.

| 기본 서식 파일 형식 |baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------|-- |----------------------------------------------------- |
|병원|`healthcareHospital`|채널 <ul><li>일반</li><li>공지 사항</li><li>규정 준수</li><li>보호</li><li>인적 리소스</li><li>약국</li></ul> 앱: <ul><li>Wiki</li><li>목록 </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Microsoft Graph에서 Teams 서식 파일 사용

개발자는 Teams 서식 파일가 포함된 Microsoft Graph를 사용하여 팀을 만들 수 있습니다. Microsoft는 현재 다양한 상황에서 사용할 수 있는 두 가지 일선 의료 서식 파일을 제공합니다. 일반적인 팀 서식 파일에 대한 자세한 내용은 [Teams 서식 파일 시작하기](../../get-started-with-teams-templates.md)를 참조하세요. Teams 서식 파일과 Microsoft Graph에 대한 자세한 내용은 [Microsoft Teams API 개요](/graph/teams-concept-overview?view=graph-rest-1.0) 및 [Teams 서식 파일 리소스 유형](/graph/api/resources/teamstemplate?view=graph-rest-1.0)을 참조하세요.

### <a name="ward-template"></a>병동 서식 파일

병동 서식 파일은 병동, 병실 또는 부서 내에서 의사소통과 공동 작업을 하기 위한 서식 파일입니다. 이 서식 파일을 사용하여 병동의 환자 관리 및 운영 요구 사항을 용이하게 만들 수 있습니다. 예를 들어, 병동 공지 사항을 *공지 사항* 채널에서 게시하고 *직원* 에서 교대 근무를 관리할 수 있습니다. 병동 작업을 간소화하고자 하는 경우, 이 서식 파일이 매우 적합합니다.

|기본 서식 파일 형식 |baseTemplateId |기준 서식 파일 채널|
|:--- |:---|:---|
|의료 - 병동 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 공지 사항\* <br> 장애 요소\* <br> 라운드\* <br> 직원\* <br> 교육\* |
|     | |         |

\*자동 즐겨찾기 지정

### <a name="hospital-template"></a>병원 서식 파일

이 병원 서식 파일은 병원 내에서 여러 병동, 병실, 부서 간 의사소통과 공동 작업을 수행하기 위해 제작되었습니다. 이 서식 파일에는 *공지 사항*, *보호* 및 *약국* 을 비롯한 여러 운영 채널이 포함되어 있지만, 또한 원하는 대로 추가, 삭제 또는 편집할 수 있는 다양한 추가 부서 또는 전문 중심 채널로 템플릿을 확장하는 아래의 스크립트도 제공합니다. 예를 들어, *내분비학과* 가 있지만 *안과* 용 채널은 필요하지 않은 경우 스크립트를 조정하여 *내분비학과* 채널을 포함하고 *안과* 채널을 제거할 수 있습니다. 알림 포화 상태를 방지하기 위해 이러한 특수 또는 병동 모델의 채널은 자동 즐겨찾기하지 않는 것이 좋습니다. 사용자는 일반적으로 관련이 있는 모든 채널을 즐겨찾습니다.

|기본 서식 파일 형식 |baseTemplateId |기준 서식 파일 채널|
|:--- |:---|:---|
|의료 - 병원 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 공지 사항\* <br> 규정 준수\* <br> 보호 <br> 인적 리소스 <br> 약국 |
| | |  |

\*자동 즐겨찾기 지정 

### <a name="how-to-use-first-party-templates"></a>기본 서식 파일을 사용하는 방법

이러한 서식 파일을 사용하려면 요청 본문의 'template@odata.bind' 속성을 '표준'에서 위의 TemplateID로 변경하면 됩니다.  Teams 서식 파일을 배포하는 방법에 대한 자세한 내용은 [팀을 만드는](/graph/api/team-post?view=graph-rest-beta) 방법에 대한 Microsoft Graph 문서를 참조하세요.

> [!NOTE]
> 서식 파일에서 채널은 일반 탭 아래에 자동으로 만들어집니다.

#### <a name="example-hospital-template-extension-script"></a>예: 병원 서식 파일 확장 스크립트

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

### <a name="related-topics"></a>관련 주제

[Teams 서식 파일 시작](../../get-started-with-teams-templates.md)

[의료 조직을 위한 Teams 시작](teams-in-hc.md)