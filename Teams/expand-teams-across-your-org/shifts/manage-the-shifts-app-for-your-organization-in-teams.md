---
title: 조직의 교대 근무 앱 관리
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 조직의 최전방 직원를 위해 Teams에서 교대 근무 앱을 설정하고 관리하는 방법을 학습합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909092"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="94f63-103">Microsoft Teams에서 조직의 교대 근무s 앱 관리</span><span class="sxs-lookup"><span data-stu-id="94f63-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94f63-104">2020년 6월 30일부터 Microsoft StaffHub는 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="94f63-105">Microsoft Teams에 StaffHub 기능을 구축하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="94f63-106">현재 Teams에는 일정 관리를 위한 교대 근무 앱이 포함되어 있으며 시간이 지날 때 추가 기능이 배포될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="94f63-107">2020년 6월 30일 StaffHub에서 모든 사용자에 대해 작동이 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="94f63-108">StaffHub를 여는 모든 사용자에게 Teams를 다운로드하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="94f63-109">자세한 내용은 [Microsoft StaffHub는 사용 중지됨](microsoft-staffhub-to-be-retired.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94f63-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="94f63-110">교대 근무 개요</span><span class="sxs-lookup"><span data-stu-id="94f63-110">Overview of Shifts</span></span>

<span data-ttu-id="94f63-111">Microsoft Teams의 교대 근무 앱은 최전방 직원을 연결하고 동기화된 상태를 유지합니다. 팀을 위한 빠르고 효과적인 시간 관리 및 통신을 위해 모바일 형태로 먼저 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="94f63-112">교대 근무를 사용하면 최전방 직원과 관리자가 모바일 장치를 사용하여 일정을 관리하고 연락을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="94f63-113">관리자는 팀의 교대 근무 일정을 만들고 업데이트하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="94f63-114">관리자는 한 사람에게 메시지(“바닥에 액체가 흘러 있네요.”)를 보내거나 전체 팀에 메시지(“지역 GM이 20분 후에 도착합니다.”)를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="94f63-115">이뿐만 아니라 정책 문서, 뉴스 게시판 및 비디오를 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="94f63-116">직원은 예정된 교대 근무를 보고, 그날에 예정된 다른 사람을 확인하고, 교대 근무를 변경하거나 제안하고, 휴가를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="94f63-117">교대 근무는 현재 게스트 사용자를 지원하지 않는다는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="94f63-118">즉, 팀의 게스트는 Teams에서 게스트 액세스가 켜져 있을 때 교대 근무 일정을 추가하거나 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="94f63-119">다른 플랫폼의 교대 근무 기능에 대한 자세한 내용은 [플랫폼별 Teams 기능](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94f63-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="94f63-120">교대 근무의 가용성</span><span class="sxs-lookup"><span data-stu-id="94f63-120">Availability of Shifts</span></span>

<span data-ttu-id="94f63-121">교대 근무는 Teams를 사용할 수 있는 모든 엔터프라이즈 SKU에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="94f63-122">교대 근무 데이터의 위치</span><span class="sxs-lookup"><span data-stu-id="94f63-122">Location of Shifts data</span></span>

<span data-ttu-id="94f63-123">교대 근무 데이터는 현재 북아메리카, 서유럽 및 아시아 태평양에 위치한 데이터 센터의 Azure에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="94f63-124">데이터가 저장되는 위치에 대한 자세한 내용은 [내 데이터는 어디에 있나요](http://o365datacentermap.azurewebsites.net/)?를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94f63-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="94f63-125">교대 근무 설정</span><span class="sxs-lookup"><span data-stu-id="94f63-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="94f63-126">조직에서 교대 근무를 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="94f63-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="94f63-127">교대 근무는 조직의 모든 Teams 사용자에 대해 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="94f63-128">Microsoft Teams 관리자 센터의 [앱 관리](../../manage-apps.md) 페이지에서 조직 수준에서 앱을 끄거나 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="94f63-129">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="94f63-130">앱 목록에서 다음 작업 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="94f63-131">조직에서 교대 근무를 사용 해제하려면 교대 근무 앱을 검색하고 선택한 다음 **차단** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="94f63-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="94f63-132">조직에 대해 교대 근무를 설정하려면 교대 근무 앱을 검색하고 선택한 다음 **허용** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="94f63-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="94f63-133">조직의 특정 사용자에 대해 교대 근무를 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="94f63-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="94f63-134">조직의 특정 사용자가 교대 근무를 사용할 수 없도록 허용하거나 차단하려면 [앱 관리](../../manage-apps.md) 페이지에서 조직에 대해 교대 근무가 설정되어 있는지 확인한 다음 사용자 지정 앱 권한 정책을 만들어 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="94f63-135">자세한 내용은 Teams 에서 [앱 사용 권한 정책 관리](../../teams-app-permission-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94f63-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="94f63-136">최전방 직원 앱 설치 정책을 사용하여 Teams에 교대 근무 고정</span><span class="sxs-lookup"><span data-stu-id="94f63-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="94f63-137">앱 설정 정책을 사용하면 Teams를 사용자 지정하여 조직의 사용자에게 가장 중요한 앱을 강조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="94f63-138">정책에 설정한 앱은 Teams 데스크톱 클라이언트의 측면&mdash;표시줄에 있는 앱 모음과 Teams 데스크톱 클라이언트의 하단에 고정되어 있어, &mdash;사용자가 빠르고 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="94f63-139">Teams에는 조직의 최전방 직원에 할당할 수 있는 기본 제공 최전방 직원 앱 설정 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="94f63-140">기본적으로 이 정책에는 활동, 교대 근무, 채팅 및 통화 앱이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="94f63-141">최전방 직원 정책을 보려면, Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 설정 정책** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="94f63-142">![최전방 직원 앱 설정 정책 스크린샷](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 관리 센터의 최전방 직원 앱 설정 정책 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="94f63-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="94f63-143">사용자에게 최전방 직원 앱 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="94f63-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="94f63-144">교대 근무 이벤트에 대한 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="94f63-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="94f63-145">**(미리 보기 중)**</span><span class="sxs-lookup"><span data-stu-id="94f63-145">**(in preview)**</span></span>

<span data-ttu-id="94f63-146">감사 로그를 검색하여 조직의 교대 근무 활동을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="94f63-147">감사 로그를 검색하는 방법과 감사 로그에 기록된 [교대 근무 활동](../../audit-log-events.md#shifts-in-teams-activities) 목록을 확인하는 방법에 대한 자세한 내용은 [Teams에서 이벤트에 대한 감사 로그 검색](../../audit-log-events.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94f63-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="94f63-148">감사 로그를 검색하려면 먼저 [보안 및 준수 센터](https://protection.office.com)에서 감사를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="94f63-149">자세한 내용은 [감사 로그 검색 설정 및 해제](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94f63-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="94f63-150">감사 데이터는 감사가 켜진 시점부터만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f63-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="94f63-151">관련 주제</span><span class="sxs-lookup"><span data-stu-id="94f63-151">Related topics</span></span>

- [<span data-ttu-id="94f63-152">최전방 직원용 교대 근무 도움말</span><span class="sxs-lookup"><span data-stu-id="94f63-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="94f63-153">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="94f63-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
