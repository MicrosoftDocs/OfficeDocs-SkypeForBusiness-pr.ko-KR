---
title: 의료 조직용 템플릿
author: serdarsoysal
ms.author: serdars
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
description: Microsoft Graph와 함께 Microsoft Teams 서식 파일을 사용하여 설정, 채널 및 앱의 미리 정의된 서식 파일을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX
ms.openlocfilehash: e288bc68c8160fb80d4e56a6477437e0a79fea0a
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260340"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>의료 조직용 Teams 서식 파일 시작

Microsoft Teams 서식 파일을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 서식 파일을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.

의료 조직의 경우 템플릿은 사용자가 Teams를 효과적으로 사용하는 방법을 주도할 수 있는 구조를 제공하기에 특히 강력할 수 있습니다. 또한 템플릿을 사용하면 관리자가 조직 전체에 일관된 팀을 배포할 수 있습니다. 이 문서는 의료 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.

현재 다양한 상황에 사용할 수 있는 두 개의 첫 번째 의료 템플릿을 제공합니다. 일반적으로 팀 서식 파일에 대한 자세한 내용은 Teams 서식 [파일 시작을 참조합니다.](../../get-started-with-teams-templates.md)

## <a name="ward-template"></a>Ward 서식 파일

와드 서식 파일은 구, Pod 또는 부서 내에서 통신 및 공동 작업을 위한 것입니다. 이 템플릿은 환자 관리뿐만 아니라 구의 운영 요구를 용이하게 하는 데 사용할 수 있습니다. 예를 들어, 공지사항 채널에 와드  공지 사항을 게시할 수 있으며 교대 근무는 직원 관리에서 관리할 *수 있습니다.* 구 작업을 간소화하고자 하는 경우 이 템플릿을 사용할 수 있습니다.

|기본 템플릿 유형 |baseTemplateId |기준 템플릿 채널|
|:--- |:---|:---|
|의료 - Ward | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 공지\* <br> Huddles\* <br> 라운드\* <br> 직원 직원\* <br> 교육\* |
|     | |         |

\* 자동 즐겨찾기

## <a name="hospital-template"></a>병원 서식 파일

병원 템플릿은 여러 구, Pod 및 병원 내의 부서 간의 통신 및 공동 작업을 위한 것입니다. 이 템플릿에는 공지, 관리 및  *약국을* 비롯한 여러 운영 채널이 포함되어 있지만, 아래에는 원하는 채널에 추가, 삭제 또는 편집할 수 있는 다양한 부서 또는 특수 중심 채널로 템플릿을 확장하는 스크립트가 제공됩니다. 예를 들어, 내분비학 부서가 있지만 *Ophthalmology에* 대한 채널이 필요하지 않은 경우 스크립트를 조정하여 내분비 채널을 포함하고 *Ophthalmology* 채널을 제거할 수 있습니다.   알림 포화 방지를 위해 이러한 전문 채널 또는 구 모델링 채널을 자동으로 즐겨찾기하지 않는 것이 좋습니다. 사용자는 일반적으로 관련성이 있는 채널을 즐겨찾기합니다.

|기본 템플릿 유형 |baseTemplateId |기준 템플릿 채널|
|:--- |:---|:---|
|의료 - 병원 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 공지\* <br> 규정 준수\* <br> Custodial <br> 인적 자원 <br> 약국 |
| | |  |

\* 자동 즐겨찾기 

## <a name="how-to-use-first-party-templates"></a>첫 번째 파티 템플릿을 사용하는 방법

이러한 템플릿을 사용하기 위해 요청 본문의 'template@odata.bind' 속성을 'standard'에서 위의 TemplateID로 변경하면 됩니다.  Teams 템플릿을 배포하는 방법에 대한 자세한 내용은 팀을 만드는 방법에 대한 Microsoft Graph [문서를 참조하세요.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> 템플릿의 채널은 일반 탭 아래에 자동으로 만들어집니다.

### <a name="example-hospital-template-extension-script"></a>예: 병원 템플릿 확장 스크립트

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

## <a name="related-topics"></a>관련 항목

[Teams 서식 파일 시작](../../get-started-with-teams-templates.md)

[의료 조직을 위한 Teams 시작](teams-in-hc.md)

[관리 콘솔에서 Teams 서식 파일 시작](../../get-started-with-teams-templates-in-the-admin-console.md)
