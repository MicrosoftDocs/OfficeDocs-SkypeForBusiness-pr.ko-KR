---
title: 의료 조직의 팀 템플릿 시작 하기
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 의료 조직의 팀 템플릿 시작 하기
ms.openlocfilehash: df917c3a6f1cbf20c9226dd58e4706c4c0e3bc2c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570350"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>의료 조직의 팀 템플릿 시작 하기

Microsoft 팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.

건강 보험 조직의 경우, 사용자가 팀을 효과적으로 활용 하는 방법에 대 한 구조를 제공 하는 것 처럼 서식 파일을 사용 하는 것이 특히 좋을 수 있습니다. 또한 서식 파일을 사용 하면 관리자가 조직 간에 일관 된 팀을 배포할 수 있습니다. 이 문서는 의료 기관에서 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 적합 합니다.

현재 다양 한 상황에 활용할 수 있는 첫 번째 파티 건강 보험 템플릿을 제공 합니다. 팀 서식 파일에 대 한 일반적인 내용은 [팀 서식 파일 시작](../../get-started-with-teams-templates.md)을 참조 하세요.

## <a name="ward-template"></a>서식 파일

통합 서식 파일은 통합, pod 또는 부서 내에서 통신 및 공동 작업을 위해 고안 되었습니다. 이 서식 파일을 사용 하 여 환자 관리를 비롯 하 여 한 가지 작업에 대 한 운영 요구를 활용할 수 있습니다. 예를 들어, *팀*알림은 *공지 사항* 채널에 게시 될 수 있으며, 교대 근무를 관리할 수 있습니다. 팔 로우 작업을 합리화 하려는 경우이 서식 파일을 사용할 수 있습니다.

|기본 서식 파일 형식 |baseTemplateId |기준 서식 파일 채널|
|:--- |:---|:---|
|건강 보험 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 알림에서\* <br> Huddles\* <br> 소수\* <br> 자원\* <br> 관한\* |
|     | |         |

\*자동 즐겨찾기에

## <a name="hospital-template"></a>병원 서식 파일

병원 서식 파일은 병원의 여러 wards, pods, 부서 간의 통신과 공동 작업을 위한 것입니다. 이 서식 파일에는 *공지 사항*, *Custodial*, *Pharmacy*를 포함 하 여 여러 가지 작동 채널이 포함 되어 있지만, 아래에는 다양 한 추가 부서나 함께 서식 파일을 확장 하는 스크립트도 나와 있습니다. 원하는 대로 추가, 삭제 또는 편집할 수 있는 전문 중앙 채널 예를 들어 *Endocrinology* 부서가 있지만 *Ophthalmology*에 대 한 채널이 필요 하지 않은 경우 *Endocrinology* 채널을 포함 하 여 *Ophthalmology* 채널을 제거 하도록 스크립트를 적용할 수 있습니다. 이러한 특수 또는 즐겨찾기에 모델 채널은 알림 채도를 방지 하기 위해 자동으로 하지 않는 것이 좋습니다. 일반적으로 사용자는 관련 된 채널을 즐겨 찾는 것입니다.

|기본 서식 파일 형식 |baseTemplateId |기준 서식 파일 채널|
|:--- |:---|:---|
|건강 보험-병원 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 알림에서\* <br> 충족\* <br> Custodial <br> 인적 자원 <br> Pharmacy |
| | |  |

\*자동 즐겨찾기에 

## <a name="how-to-use-first-party-templates"></a>자사 서식 파일을 사용 하는 방법

이 서식 파일을 사용 하려면 요청 본문의 ' template@odata.bind ' 속성을 ' standard '에서 위의 TemplateIDs으로 변경 하면 됩니다.  팀 템플릿을 배포 하는 방법에 대 한 자세한 내용은 [팀을 만드는](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)방법에 대 한 Microsoft Graph 문서를 참조 하세요.

> [!NOTE]
> 서식 파일의 채널이 일반 탭 아래에 자동으로 생성 됩니다.

### <a name="example-hospital-template-extension-script"></a>예: 병원 서식 파일 확장명 스크립트

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
              "displayName": "Women’s Health",
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

[팀 서식 파일 시작 하기](../../get-started-with-teams-templates.md)

[건강 조직의 팀 시작 하기](teams-in-hc.md)
