---
title: 조직의 Shifts 앱 관리
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
description: 조직의 일선 작업자용 Teams에서 Shifts 앱을 설정하고 관리하는 방법을 배워야 합니다.
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
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909092"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="f5348-103">Microsoft Teams에서 조직의 Shifts 앱 관리</span><span class="sxs-lookup"><span data-stu-id="f5348-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5348-104">2020년 6월 30일부로 Microsoft StaffHub가 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="f5348-105">Microsoft Teams에 StaffHub 기능을 구축하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="f5348-106">현재 Teams에는 일정 관리를 위한 Shifts 앱이 포함되어 있으며 시간이 지날 때 추가 기능이 출시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="f5348-107">StaffHub는 2020년 6월 30일 모든 사용자에 대한 작업을 중지했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="f5348-108">StaffHub를 열려고 하는 모든 사람이 Teams를 다운로드할 수 있는 메시지를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="f5348-109">자세한 내용은 [Microsoft StaffHub가 사용 중지된 것을 참조합니다.](microsoft-staffhub-to-be-retired.md)</span><span class="sxs-lookup"><span data-stu-id="f5348-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="f5348-110">Shifts 개요</span><span class="sxs-lookup"><span data-stu-id="f5348-110">Overview of Shifts</span></span>

<span data-ttu-id="f5348-111">Microsoft Teams의 Shifts 앱은 일선 작업자를 연결하고 동기화합니다. 팀을 위한 빠르고 효과적인 시간 관리 및 커뮤니케이션을 위한 모바일이 먼저 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="f5348-112">Shifts를 사용하면 일선 직원들과 관리자가 모바일 장치를 사용하여 일정을 관리하고 연락을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="f5348-113">관리자는 팀의 교대 근무 일정을 만들고, 업데이트하고, 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="f5348-114">한 사람("바닥에 유출이 있습니다") 또는 전체 팀("지역 GM이 20분 내 도착")으로 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="f5348-115">정책 문서, 뉴스 게시판 및 비디오를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="f5348-116">직원은 예정된 교대 근무를 보고, 그 날에 예약된 다른 사람, 교대 근무 바꾸기 또는 제안 요청 및 근무 시간 요청</span><span class="sxs-lookup"><span data-stu-id="f5348-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="f5348-117">Shifts는 현재 게스트 사용자를 지원하지 않는다는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="f5348-118">즉, Teams에서 게스트 액세스가 설정되어 있는 경우 팀의 게스트를 추가하거나 교대 근무 일정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="f5348-119">다양한 플랫폼의 Shifts 기능에 대한 자세한 내용은 플랫폼에 따라 [Teams 기능을 참조하세요.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="f5348-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="f5348-120">Shifts의 가용성</span><span class="sxs-lookup"><span data-stu-id="f5348-120">Availability of Shifts</span></span>

<span data-ttu-id="f5348-121">Shifts는 Teams를 사용할 수 있는 모든 Enterprise SKUS에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="f5348-122">Shifts 데이터의 위치</span><span class="sxs-lookup"><span data-stu-id="f5348-122">Location of Shifts data</span></span>

<span data-ttu-id="f5348-123">Shifts 데이터는 현재 북아메리카, 서유럽 및 아시아 태평양의 데이터 센터에 Azure에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="f5348-124">데이터가 저장되는 위치에 대한 자세한 내용은 내 데이터가 어디에 [있나요?](http://o365datacentermap.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="f5348-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="f5348-125">Shifts 설정</span><span class="sxs-lookup"><span data-stu-id="f5348-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="f5348-126">조직에서 Shifts 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f5348-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="f5348-127">Shifts는 조직의 모든 Teams 사용자에 대해 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="f5348-128">Microsoft Teams 관리 센터의 앱 관리 페이지에서 구성 [](../../manage-apps.md) 수준에서 앱을 끄거나 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="f5348-129">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 **관리**  >  **앱으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f5348-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="f5348-130">앱 목록에서 다음 작업 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="f5348-131">조직에 대한 Shifts를 해제하려면 Shifts 앱을 검색하고 선택한 다음 차단을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f5348-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="f5348-132">조직에 대한 Shifts를 설정하려면 Shifts 앱을 검색하고 선택한 다음 허용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f5348-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="f5348-133">조직의 특정 사용자에 대해 Shifts 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f5348-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="f5348-134">조직의 특정 사용자가 Shifts를 사용할 수 있도록 허용하거나 차단하려면 앱 관리 [](../../manage-apps.md) 페이지에서 조직에 대해 Shifts가 켜져 있는지 확인한 다음 사용자 지정 앱 사용 권한 정책을 만들고 해당 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="f5348-135">자세한 내용은 [Teams에서 앱 사용 권한 정책 관리를 참조하세요.](../../teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f5348-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="f5348-136">FrontlineWorker 앱 설정 정책을 사용하여 Teams에 Shifts 고정</span><span class="sxs-lookup"><span data-stu-id="f5348-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="f5348-137">앱 설정 정책을 사용하면 Teams를 사용자 지정하여 조직의 사용자에게 가장 중요한 앱을 강조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="f5348-138">정책에 설정된 앱은 Teams 데스크톱 클라이언트의 측면 및 사용자가 빠르고 쉽게 액세스할 수 있는 Teams 모바일 클라이언트의 아래쪽에 있는 앱 바에 &mdash; &mdash; 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="f5348-139">Teams에는 조직의 Frontline Workers에 할당할 수 있는 기본 제공 FrontlineWorker 앱 설정 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="f5348-140">기본적으로 정책에는 활동, Shifts, 채팅 및 통화 앱이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="f5348-141">FrontlineWorker 정책을 보기 위해 Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams** 앱 설정  >  **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f5348-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="f5348-142">![FrontlineWorker 앱 설정 정책의 스크린샷](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 관리 센터의 FrontlineWorker 앱 설정 정책 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="f5348-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="f5348-143">사용자에게 FrontlineWorker 앱 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f5348-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="f5348-144">Shifts 이벤트에 대한 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="f5348-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="f5348-145">**(미리 보기)**</span><span class="sxs-lookup"><span data-stu-id="f5348-145">**(in preview)**</span></span>

<span data-ttu-id="f5348-146">감사 로그를 검색하여 조직의 Shifts 활동을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="f5348-147">감사 로그를 검색하고 감사 로그에 기록된 [Shifts](../../audit-log-events.md#shifts-in-teams-activities) 활동 목록을 보는 방법에 대한 자세한 내용은 Teams에서 이벤트에 대한 감사 로그 검색을 [참조하세요.](../../audit-log-events.md)</span><span class="sxs-lookup"><span data-stu-id="f5348-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="f5348-148">감사 로그를 검색하려면 먼저 Security & 준수 센터에서 감사를 [켜야 합니다.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="f5348-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="f5348-149">자세한 내용은 감사 로그 검색 설정 [또는 해제를 참조합니다.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)</span><span class="sxs-lookup"><span data-stu-id="f5348-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="f5348-150">감사 데이터는 감사를 설정한 시점에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5348-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f5348-151">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f5348-151">Related topics</span></span>

- [<span data-ttu-id="f5348-152">일선 작업자를 위한 교대 근무 도움말</span><span class="sxs-lookup"><span data-stu-id="f5348-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="f5348-153">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f5348-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
