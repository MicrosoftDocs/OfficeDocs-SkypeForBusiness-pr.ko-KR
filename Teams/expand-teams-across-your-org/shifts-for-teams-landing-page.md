---
title: Teams의 교대 근무
description: Teams에서 Shifts(일정 관리 도구)를 설정하고 관리하는 데 필요한 관리자 지침을 얻습니다.
ms.topic: conceptual
author: cichur
ms.author: v-cichur
audience: admin
manager: serdars
f1.keywords:
- NOCSH
ms.date: 03/29/2019
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: f699b60bddba6bcf5ffa884760540e5c20378f81
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909222"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="e3f93-103">Teams의 교대 근무</span><span class="sxs-lookup"><span data-stu-id="e3f93-103">Shifts for Teams</span></span>

<span data-ttu-id="e3f93-104">Teams는 조직 내 일선 근로자가 효과적으로 통신하고 공동 작업하는 데 필요한 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f93-104">Teams gives Frontline Workers in your organization the tools they need to communicate and collaborate effectively.</span></span> <span data-ttu-id="e3f93-105">이 문서에서는 설정 및 관리 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3f93-105">This article shows you how to set up and manage.</span></span> <span data-ttu-id="e3f93-106">Teams에서 일정 관리 도구를 교대하고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f93-106">Shifts and use the schedule management tool in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="e3f93-107">조직의 Shifts 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="e3f93-107">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![task-checklist-planning-teams](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="e3f93-109">**[조직의 Shifts 관리](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span><span class="sxs-lookup"><span data-stu-id="e3f93-109">**[Manage Shifts in your organization](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span></span> |![디자인](../media/Help-small.svg)  | <span data-ttu-id="e3f93-111">**[일선 작업자를 위한 교대 근무 도움말](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="e3f93-111">**[Shifts Help for Frontline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="e3f93-112">Shifts 확장</span><span class="sxs-lookup"><span data-stu-id="e3f93-112">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![api](../media/api-small.svg) | <span data-ttu-id="e3f93-114">**[Shift Graph API](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph API를 사용하면 Shifts 데이터를 외부 인력 관리 시스템과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f93-114">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems.</span></span> <span data-ttu-id="e3f93-115">사용자는 Teams에서 풍부한 프런트 엔드 환경을 제공하면서 백 엔드에서 사용자 지정 Shifts 환경을 유연하게 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f93-115">You'll have the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![api](../media/api-small.svg) | <span data-ttu-id="e3f93-117">**[Workforce 관리 통합](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** Kronos 및 JDA와 같은 타사 인력 관리 시스템을 사용하여 예정, 시간 및 참석을 위해 사용하는 경우 Shifts Graph API 및 SDK를 통해 오픈 소스 통합을 통해 Shifts와 직접 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f93-117">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![api](../media/process-flow-teams-small.svg) | <span data-ttu-id="e3f93-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate를 사용하면 Shifts에서 정보를 받아 다른 앱으로 사용자 지정 워크플로를 만들고 대규모 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f93-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="e3f93-120">코드가 거의 없는 키 프로세스를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f93-120">Automate key processes with little to no code.</span></span> <span data-ttu-id="e3f93-121">트리거 및 템플릿은 관리자의 승인이 필요하지 않은 경우 교대 근무 요청에 대한 자동 승인을 사용하도록 설정하는 등의 다양한 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f93-121">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="e3f93-122">추천 교육</span><span class="sxs-lookup"><span data-stu-id="e3f93-122">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![화살표 오른쪽 2-teams](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="e3f93-124">비디오: Shifts란?</span><span class="sxs-lookup"><span data-stu-id="e3f93-124">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![clock-teams](../media/clock-teams-small.svg)  |  [<span data-ttu-id="e3f93-126">비디오: Shifts란?</span><span class="sxs-lookup"><span data-stu-id="e3f93-126">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![blocks-teams](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="e3f93-128">비디오: Shifts 일정 관리</span><span class="sxs-lookup"><span data-stu-id="e3f93-128">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
