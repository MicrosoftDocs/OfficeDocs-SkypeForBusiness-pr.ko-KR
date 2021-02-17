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
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="5201d-103">의료 조직용 Teams 서식 파일 시작</span><span class="sxs-lookup"><span data-stu-id="5201d-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="5201d-104">Microsoft Teams 서식 파일을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 서식 파일을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="5201d-105">의료 조직의 경우 템플릿은 사용자가 Teams를 효과적으로 사용하는 방법을 주도할 수 있는 구조를 제공하기에 특히 강력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="5201d-106">또한 템플릿을 사용하면 관리자가 조직 전체에 일관된 팀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="5201d-107">이 문서는 의료 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="5201d-108">현재 다양한 상황에 사용할 수 있는 두 개의 첫 번째 의료 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="5201d-109">일반적으로 팀 서식 파일에 대한 자세한 내용은 Teams 서식 [파일 시작을 참조합니다.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="5201d-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="5201d-110">Ward 서식 파일</span><span class="sxs-lookup"><span data-stu-id="5201d-110">Ward template</span></span>

<span data-ttu-id="5201d-111">와드 서식 파일은 구, Pod 또는 부서 내에서 통신 및 공동 작업을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="5201d-112">이 템플릿은 환자 관리뿐만 아니라 구의 운영 요구를 용이하게 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="5201d-113">예를 들어, 공지사항 채널에 와드  공지 사항을 게시할 수 있으며 교대 근무는 직원 관리에서 관리할 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="5201d-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="5201d-114">구 작업을 간소화하고자 하는 경우 이 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="5201d-115">기본 템플릿 유형</span><span class="sxs-lookup"><span data-stu-id="5201d-115">Base Template Type</span></span> |<span data-ttu-id="5201d-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5201d-116">baseTemplateId</span></span> |<span data-ttu-id="5201d-117">기준 템플릿 채널</span><span class="sxs-lookup"><span data-stu-id="5201d-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="5201d-118">의료 - Ward</span><span class="sxs-lookup"><span data-stu-id="5201d-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="5201d-119">공지\*</span><span class="sxs-lookup"><span data-stu-id="5201d-119">Announcements\*</span></span> <br> <span data-ttu-id="5201d-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="5201d-120">Huddles\*</span></span> <br> <span data-ttu-id="5201d-121">라운드\*</span><span class="sxs-lookup"><span data-stu-id="5201d-121">Rounds\*</span></span> <br> <span data-ttu-id="5201d-122">직원 직원\*</span><span class="sxs-lookup"><span data-stu-id="5201d-122">Staffing\*</span></span> <br> <span data-ttu-id="5201d-123">교육\*</span><span class="sxs-lookup"><span data-stu-id="5201d-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="5201d-124">\* 자동 즐겨찾기</span><span class="sxs-lookup"><span data-stu-id="5201d-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="5201d-125">병원 서식 파일</span><span class="sxs-lookup"><span data-stu-id="5201d-125">Hospital template</span></span>

<span data-ttu-id="5201d-126">병원 템플릿은 여러 구, Pod 및 병원 내의 부서 간의 통신 및 공동 작업을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="5201d-127">이 템플릿에는 공지, 관리 및  *약국을* 비롯한 여러 운영 채널이 포함되어 있지만, 아래에는 원하는 채널에 추가, 삭제 또는 편집할 수 있는 다양한 부서 또는 특수 중심 채널로 템플릿을 확장하는 스크립트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="5201d-128">예를 들어, 내분비학 부서가 있지만 *Ophthalmology에* 대한 채널이 필요하지 않은 경우 스크립트를 조정하여 내분비 채널을 포함하고 *Ophthalmology* 채널을 제거할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="5201d-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="5201d-129">알림 포화 방지를 위해 이러한 전문 채널 또는 구 모델링 채널을 자동으로 즐겨찾기하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="5201d-130">사용자는 일반적으로 관련성이 있는 채널을 즐겨찾기합니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="5201d-131">기본 템플릿 유형</span><span class="sxs-lookup"><span data-stu-id="5201d-131">Base Template Type</span></span> |<span data-ttu-id="5201d-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5201d-132">baseTemplateId</span></span> |<span data-ttu-id="5201d-133">기준 템플릿 채널</span><span class="sxs-lookup"><span data-stu-id="5201d-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="5201d-134">의료 - 병원</span><span class="sxs-lookup"><span data-stu-id="5201d-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="5201d-135">공지\*</span><span class="sxs-lookup"><span data-stu-id="5201d-135">Announcements\*</span></span> <br> <span data-ttu-id="5201d-136">규정 준수\*</span><span class="sxs-lookup"><span data-stu-id="5201d-136">Compliance\*</span></span> <br> <span data-ttu-id="5201d-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="5201d-137">Custodial</span></span> <br> <span data-ttu-id="5201d-138">인적 자원</span><span class="sxs-lookup"><span data-stu-id="5201d-138">Human Resources</span></span> <br> <span data-ttu-id="5201d-139">약국</span><span class="sxs-lookup"><span data-stu-id="5201d-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="5201d-140">\* 자동 즐겨찾기</span><span class="sxs-lookup"><span data-stu-id="5201d-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="5201d-141">첫 번째 파티 템플릿을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="5201d-141">How to use first-party templates</span></span>

<span data-ttu-id="5201d-142">이러한 템플릿을 사용하기 위해 요청 본문의 'template@odata.bind' 속성을 'standard'에서 위의 TemplateID로 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="5201d-143">Teams 템플릿을 배포하는 방법에 대한 자세한 내용은 팀을 만드는 방법에 대한 Microsoft Graph [문서를 참조하세요.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="5201d-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="5201d-144">템플릿의 채널은 일반 탭 아래에 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5201d-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="5201d-145">예: 병원 템플릿 확장 스크립트</span><span class="sxs-lookup"><span data-stu-id="5201d-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="5201d-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5201d-146">Related topics</span></span>

[<span data-ttu-id="5201d-147">Teams 서식 파일 시작</span><span class="sxs-lookup"><span data-stu-id="5201d-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="5201d-148">의료 조직을 위한 Teams 시작</span><span class="sxs-lookup"><span data-stu-id="5201d-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="5201d-149">관리 콘솔에서 Teams 서식 파일 시작</span><span class="sxs-lookup"><span data-stu-id="5201d-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
