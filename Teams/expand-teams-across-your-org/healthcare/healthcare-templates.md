---
title: 의료 조직을 위한 Teams 서식 파일 시작
author: kenwith
ms.author: kenwith
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
description: 의료 조직을 위한 Teams 서식 파일 시작
ms.openlocfilehash: 756f9a50dac14575250a521750f80dbe8d1242b8
ms.sourcegitcommit: 9ae5dadaab999acd061cc9418dbd55d98b82980e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2019
ms.locfileid: "38702319"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="bc6ee-103">의료 조직을 위한 Teams 서식 파일 시작</span><span class="sxs-lookup"><span data-stu-id="bc6ee-103">Get started with Teams templates for Healthcare organizations</span></span>

<span data-ttu-id="bc6ee-104">Microsoft 팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="bc6ee-105">건강 보험 조직의 경우, 사용자가 팀을 효과적으로 활용 하는 방법에 대 한 구조를 제공 하는 것 처럼 서식 파일을 사용 하는 것이 특히 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="bc6ee-106">또한 서식 파일을 사용 하면 관리자가 조직 간에 일관 된 팀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="bc6ee-107">이 문서는 의료 기관에서 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="bc6ee-108">현재 다양 한 상황에 활용할 수 있는 첫 번째 파티 건강 보험 템플릿을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-108">We currently offer two first party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="bc6ee-109">팀 서식 파일에 대 한 일반적인 내용은 [팀 서식 파일 시작](../../get-started-with-teams-templates.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-109">To learn more about team templates in general, please see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="bc6ee-110">서식 파일</span><span class="sxs-lookup"><span data-stu-id="bc6ee-110">Ward template</span></span>

<span data-ttu-id="bc6ee-111">통합 서식 파일은 통합, pod 또는 부서 내에서 통신 및 공동 작업을 위해 고안 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="bc6ee-112">이 서식 파일을 사용 하 여 환자 관리를 비롯 하 여 한 가지 작업에 대 한 운영 요구를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="bc6ee-113">예를 들어, *팀*알림은 *공지 사항* 채널에 게시 될 수 있으며, 교대 근무를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="bc6ee-114">팔 로우 작업을 합리화 하려는 경우이 서식 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-114">If you’re looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="bc6ee-115">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="bc6ee-115">Base Template Type</span></span> |<span data-ttu-id="bc6ee-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="bc6ee-116">baseTemplateId</span></span> |<span data-ttu-id="bc6ee-117">기준 서식 파일 채널</span><span class="sxs-lookup"><span data-stu-id="bc6ee-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="bc6ee-118">건강 보험</span><span class="sxs-lookup"><span data-stu-id="bc6ee-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="bc6ee-119">알림에서\*</span><span class="sxs-lookup"><span data-stu-id="bc6ee-119">Announcements\*</span></span> <br> <span data-ttu-id="bc6ee-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="bc6ee-120">Huddles\*</span></span> <br> <span data-ttu-id="bc6ee-121">소수\*</span><span class="sxs-lookup"><span data-stu-id="bc6ee-121">Rounds\*</span></span> <br> <span data-ttu-id="bc6ee-122">자원\*</span><span class="sxs-lookup"><span data-stu-id="bc6ee-122">Staffing\*</span></span> <br> <span data-ttu-id="bc6ee-123">관한\*</span><span class="sxs-lookup"><span data-stu-id="bc6ee-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="bc6ee-124">\*자동 즐겨찾기에</span><span class="sxs-lookup"><span data-stu-id="bc6ee-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="bc6ee-125">병원 서식 파일</span><span class="sxs-lookup"><span data-stu-id="bc6ee-125">Hospital template</span></span>

<span data-ttu-id="bc6ee-126">병원 서식 파일은 병원의 여러 wards, pods, 부서 간의 통신과 공동 작업을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="bc6ee-127">이 서식 파일에는 *공지 사항*, *Custodial*, *Pharmacy*를 포함 하 여 여러 가지 작동 채널이 포함 되어 있으며,이를 통해 서식 파일을 다양 한 추가 부서나 특별 중심 채널을 통해 확장 하 여 원하는 대로 추가, 삭제 또는 편집할 수 있는 스크립트를 제공 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="bc6ee-128">예를 들어 *Endocrinology* 부서가 있지만 *Ophthalmology*에 대 한 채널이 필요 하지 않은 경우 *Endocrinology* 채널을 포함 하 여 *Ophthalmology* 채널을 제거 하도록 스크립트를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-128">For example, if you have an *Endocrinology* department, but don’t need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="bc6ee-129">이러한 특수 또는 즐겨찾기에 모델 채널은 알림 채도를 방지 하기 위해 자동으로 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="bc6ee-130">일반적으로 사용자는 관련 된 채널을 즐겨 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="bc6ee-131">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="bc6ee-131">Base Template Type</span></span> |<span data-ttu-id="bc6ee-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="bc6ee-132">baseTemplateId</span></span> |<span data-ttu-id="bc6ee-133">기준 서식 파일 채널</span><span class="sxs-lookup"><span data-stu-id="bc6ee-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="bc6ee-134">건강 보험-병원</span><span class="sxs-lookup"><span data-stu-id="bc6ee-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="bc6ee-135">알림에서\*</span><span class="sxs-lookup"><span data-stu-id="bc6ee-135">Announcements\*</span></span> <br> <span data-ttu-id="bc6ee-136">충족\*</span><span class="sxs-lookup"><span data-stu-id="bc6ee-136">Compliance\*</span></span> <br> <span data-ttu-id="bc6ee-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="bc6ee-137">Custodial</span></span> <br> <span data-ttu-id="bc6ee-138">인적 자원</span><span class="sxs-lookup"><span data-stu-id="bc6ee-138">Human Resources</span></span> <br> <span data-ttu-id="bc6ee-139">Pharmacy</span><span class="sxs-lookup"><span data-stu-id="bc6ee-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="bc6ee-140">\*자동 즐겨찾기에</span><span class="sxs-lookup"><span data-stu-id="bc6ee-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="bc6ee-141">자사 서식 파일을 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="bc6ee-141">How to use first party templates</span></span>

<span data-ttu-id="bc6ee-142">이 템플릿을 사용 하려면 요청 본문의 ' template@odata. ' 속성을 ' standard '에서 위의 TemplateIDs로 변경 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-142">To use these templates, simply change the ‘template@odata.bind’ property in the request body from ‘standard’ to the TemplateIDs above.</span></span>  <span data-ttu-id="bc6ee-143">팀 템플릿을 배포 하는 방법에 대 한 자세한 내용은 [팀을 만드는](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)방법에 대 한 Microsoft Graph 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="bc6ee-144">서식 파일의 채널이 일반 탭 아래에 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ee-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="bc6ee-145">예: 병원 서식 파일 확장명 스크립트</span><span class="sxs-lookup"><span data-stu-id="bc6ee-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="bc6ee-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bc6ee-146">Related topics</span></span>

[<span data-ttu-id="bc6ee-147">Teams 서식 파일 시작</span><span class="sxs-lookup"><span data-stu-id="bc6ee-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="bc6ee-148">의료 조직을 위한 Teams 시작</span><span class="sxs-lookup"><span data-stu-id="bc6ee-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
