---
title: 조직의 목록 앱 관리
author: LanaChin
ms.author: v-lanac
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 사용자를 위해 팀에서 목록 앱을 관리 하는 방법에 대해 알아봅니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 339f914ee1802fd4c9307e2a2f3e7faf20ac8eb4
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277289"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="928b3-103">Microsoft 팀에서 조직의 목록 앱 관리</span><span class="sxs-lookup"><span data-stu-id="928b3-103">Manage the Lists app for your organization in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview-of-lists"></a><span data-ttu-id="928b3-104">목록 개요</span><span class="sxs-lookup"><span data-stu-id="928b3-104">Overview of Lists</span></span>

<span data-ttu-id="928b3-105">Microsoft 팀의 목록 앱은 조직의 사용자가 정보를 추적 하 고, 작업을 구성 하 고, 워크플로를 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-105">The Lists app in Microsoft Teams helps users in your organization track information, organize work, and manage workflows.</span></span> <span data-ttu-id="928b3-106">사용자는 목록을 사용 하 여 문제점, 자산, 루틴, 연락처, 재고, 사건, 대출, 환자 등의 데이터를 추적 하 고, 사용자 지정 가능한 보기, 규칙 및 알림을 사용 하 여 팀의 모든 구성원을 동기화 된 상태로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-106">With Lists, users can track data such as issues, assets, routines, contacts, inventory, incidents, loans, patients, and more using customizable views, rules, and alerts to keep everyone on the team in sync.</span></span>

<span data-ttu-id="928b3-107">팀에서 사용자는 채널에서 목록을 탭으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-107">In Teams, users access Lists as a tab in a channel.</span></span> <span data-ttu-id="928b3-108">클릭 **+** 하 여 탭 갤러리를 열고 새 목록 앱 탭 인스턴스를 채널에 추가 하 여 시작 하세요.</span><span class="sxs-lookup"><span data-stu-id="928b3-108">Click **+** to open the tab gallery and add a new Lists app tab instance to a channel to get started.</span></span> 

![탭 갤러리의 목록 앱 스크린샷](media/lists-tab.png)

<span data-ttu-id="928b3-110">사용자가 새 목록을 만들거나 같은 팀 내에서 또는 액세스 권한이 있는 다른 SharePoint 사이트에서 기존 목록을 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-110">Users can create new lists or pin existing lists from within the same team or from a different SharePoint site that they have access to.</span></span> <span data-ttu-id="928b3-111">새 목록은 기본 제공 서식 파일에서 기존 목록의 구조를 기반으로 만들거나 Excel 통합 문서에서 데이터를 가져와 처음부터 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-111">New lists can be created from scratch, from built-in templates, based on the structure of an existing list, or by importing data from an Excel workbook.</span></span> <span data-ttu-id="928b3-112">목록 앱은 팀 데스크톱, 웹 및 모바일 클라이언트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-112">The Lists app is available in Teams desktop, web, and mobile clients.</span></span>

![목록 앱에서 목록을 만드는 방법에 대 한 스크린샷](media/lists-create-list.png)

## <a name="templates"></a><span data-ttu-id="928b3-114">템플릿과</span><span class="sxs-lookup"><span data-stu-id="928b3-114">Templates</span></span>

<span data-ttu-id="928b3-115">목록의 서식 파일은 사용자에 대 한 일반적인 정보 추적 시나리오에 맞게 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-115">Templates in Lists are tailored to common information tracking scenarios for users.</span></span> <span data-ttu-id="928b3-116">각 서식 파일에는 목록 보기 및 자세히 보기 수준에서 미리 정의 된 목록 구조, 양식 레이아웃 및 서식 옵션이 제공 되며,이를 통해 사용자가 빠르게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-116">Each template comes with a predefined list structure, form layouts, and formatting options at both a list view and a details view level to help users get started quickly.</span></span> <span data-ttu-id="928b3-117">서식 파일을 선택한 후 몇 가지 예제 데이터와 함께 목록이 표시 되는 모양에 대 한 미리 보기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-117">After selecting a template, users get a preview of what the list will look like, along with some sample data.</span></span> <span data-ttu-id="928b3-118">다음은 조직의 팀에서 목록에 미리 정의 된 서식 파일을 사용 하는 방법에 대 한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-118">Here's some examples of how teams in your organization can use the predefined templates in Lists:</span></span>

- <span data-ttu-id="928b3-119">문제를 추적 하 고 문제 추적기 서식 파일을 사용 하 여 클로저로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-119">Track issues and bring them to closure using the Issue tracker template.</span></span>
- <span data-ttu-id="928b3-120">이벤트 여행 서식 파일을 사용 하 여 모든 이벤트 세부 정보를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-120">Organize all your event details with the Event itinerary template.</span></span>
- <span data-ttu-id="928b3-121">환자 서식 파일을 사용 하 여 의료 기관에 팀의 요구 사항과 상태를 기록 하 여 주의를 모니터링 하 고 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-121">Use the Patients template to record the needs and status of patients for care teams in your healthcare organization to monitor and coordinate care.</span></span>
- <span data-ttu-id="928b3-122">대출금 서식 파일을 사용 하 여 대출 응용 프로그램의 상태를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-122">Track the status of loan applications with the Loans template.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="928b3-123">예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="928b3-123">Example scenario</span></span>

<span data-ttu-id="928b3-124">지역 우체국은 학구에서 메일을 정렬 하 고 배달 하는 업무를 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-124">A local post office is responsible for sorting and delivering mail in their district.</span></span> <span data-ttu-id="928b3-125">우체국에는 매일 목표를 검토 하 고, 공지 사항을 공유 하 고, 알려진 사고에 대해 토론할 수 있는 팀 huddle 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-125">Each morning, the post office has a team huddle to review daily goals, share announcements, and discuss known incidents.</span></span>

<span data-ttu-id="928b3-126">Huddle 후 메일 캐리어가 메일을 선택 하 고 배달 경로를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-126">After the huddle, mail carriers pick up their mail and start their delivery route.</span></span> <span data-ttu-id="928b3-127">사고는 경로 (예: 차량 사고, 강아지 관련 문제점 또는 소셜 unrest protest)에 따라 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-127">Incidents can occur along a route, for example, a vehicle accident, dog-related issue, or social unrest protest.</span></span> <span data-ttu-id="928b3-128">메일 캐리어가 인시던트를 발생 하면 모바일 장치에서 팀을 사용 하 여 팀 채널의 목록에서 추적 되는 인시던트 세부 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-128">When mail carriers encounter an incident, they use Teams on their mobile devices to record the incident details, which are tracked in a list in the team channel.</span></span> <span data-ttu-id="928b3-129">필드의 메일 통신 회사를 포함 하 여 팀의 모든 사용자가이 정보를 보고 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-129">Everyone on the team, including mail carriers in the field, can see this information and stay informed.</span></span>

<span data-ttu-id="928b3-130">팀으로 이동 하기 전에 메일 캐리어가 다시 우체국으로 돌아가 Excel 스프레드시트에 입력 된 인시던트를 보고 하기 위해 하드 카피 양식을 완료 해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-130">Before moving to Teams, mail carriers had to go back to the post office to complete a hard-copy form to report an incident which was entered in an Excel spreadsheet.</span></span> <span data-ttu-id="928b3-131">팀은 메일 통신 회사를 사용 하 여 먼저 필드에 인시던트를 보고할 수 있는 모바일 기능을 제공 하 고, 팀 구성원과 사고 세부 정보를 공유 하 고, 채널에서 해당 항목에 대 한 대화를 주고, 문제 해결을 위한 처리를 할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-131">Teams gives mail carriers a mobile first, experience where they can use Lists to report incidents in the field as they happen, share incident details with team members, have conversations about them on the channel, and drive incidents to resolution.</span></span>

## <a name="what-you-need-to-know-about-lists"></a><span data-ttu-id="928b3-132">목록에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="928b3-132">What you need to know about Lists</span></span>

### <a name="lists-is-available-in-every-team-and-channel"></a><span data-ttu-id="928b3-133">목록은 모든 팀과 채널에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-133">Lists is available in every team and channel</span></span>

<span data-ttu-id="928b3-134">목록은 모든 팀 사용자를 위해 미리 설치 되어 있으며 모든 팀과 채널의 탭 갤러리에서 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-134">Lists is pre-installed for all Teams users and is available directly in the tab gallery of every team and channel.</span></span> <span data-ttu-id="928b3-135">즉, 사용자가 설치 하기 위해 팀 app store로 이동할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-135">This means that users don't have to go to the Teams app store to install it.</span></span>

### <a name="lists-and-sharepoint"></a><span data-ttu-id="928b3-136">목록 및 SharePoint</span><span class="sxs-lookup"><span data-stu-id="928b3-136">Lists and SharePoint</span></span>

<span data-ttu-id="928b3-137">목록 데이터는 SharePoint Online 팀 사이트에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-137">Lists data is stored in the SharePoint Online team site.</span></span> <span data-ttu-id="928b3-138">SharePoint Online이 팀과 상호 작용 하는 방법에 대 한 자세한 내용은 [Sharepoint online 및 비즈니스용 OneDrive가 팀과 상호 작용 하는 방법](SharePoint-OneDrive-interact.md)에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="928b3-138">To learn more about how SharePoint Online interacts with Teams, see [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md).</span></span>

<span data-ttu-id="928b3-139">SharePoint에 설정 된 사용 권한은 목록 앱에서 만든 목록에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-139">Permissions set in SharePoint apply to lists created in the Lists app.</span></span> <span data-ttu-id="928b3-140">기본적으로 목록은 자신이 속한 사이트의 사용 권한을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-140">By default, lists inherit permissions from the site to which they belong.</span></span> <span data-ttu-id="928b3-141">이러한 권한은 사용자가 목록을 만들거나 편집할 수 있는지 여부와 같이 수행할 수 있는 작업 유형을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-141">These permissions govern the types of actions that users can do, such as whether they can create or edit lists.</span></span> <span data-ttu-id="928b3-142">자세한 내용은 sharepoint Server의 [sharepoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) 및 [사용자 사용 권한 수준과 권한 수준을](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="928b3-142">To learn more, see [Permission levels in SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) and [User permissions and permission levels in SharePoint Server](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels).</span></span>

<span data-ttu-id="928b3-143">특정 시나리오에서 사용자가 목록에서 수행할 수 있는 작업을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-143">In certain scenarios, you may want restrict what actions users can do in lists.</span></span> <span data-ttu-id="928b3-144">예를 들어 팀의 사용자가 목록 보기를 편집 하 여 모든 팀 구성원에 대해이를 변경 하 고 팀 소유자나 특정 팀 구성원만 목록 보기를 편집할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-144">For example, a person on a team edits a list view, which changes it for all team members, and you want to allow only the team owner or certain team members to edit list views.</span></span> <span data-ttu-id="928b3-145">자세히 알아보려면 [SharePoint 목록 또는 라이브러리에 대 한 사용 권한 사용자 지정](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="928b3-145">To learn more, see [Customize permissions for a SharePoint list or library](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).</span></span>

> [!NOTE]
> <span data-ttu-id="928b3-146">이 시점에서 팀의 소유자 및 구성원 권한은 목록 또는 목록 앱의 동작을 제어 하는 팀 사이트의 사용 권한으로 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-146">At this point, owner and member permissions in a team aren't linked in any way to permissions in the team site that govern the behavior of lists or the Lists App.</span></span> <span data-ttu-id="928b3-147">그러나 고객 의견 및 사용에 따라이는 제품의 이후 반복에 대 한 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-147">However, based on customer feedback and usage, this will be considered for a future iteration of the product.</span></span>  

### <a name="limitations"></a><span data-ttu-id="928b3-148">따릅니다</span><span class="sxs-lookup"><span data-stu-id="928b3-148">Limitations</span></span>

<span data-ttu-id="928b3-149">목록이 있으면 사용자가 데스크톱, 웹, 모바일 환경을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-149">With Lists, users get a desktop, web, and mobile experience.</span></span> <span data-ttu-id="928b3-150">사용자가 새 목록을 만들거나 팀 모바일 클라이언트의 목록을 사용 하 여 기존 목록을 고정할 수는 없다는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-150">It's important to know that users can't create new lists or pin existing lists using Lists on the Teams mobile client.</span></span> <span data-ttu-id="928b3-151">팀 모바일 클라이언트에서 목록을 보거나 편집 하려면 먼저 팀 바탕 화면 또는 웹 클라이언트의 목록을 사용 하 여 목록을 만들거나 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-151">To view or edit a list on the Teams mobile client, a list must first be created or added using Lists on the Teams desktop or web client.</span></span>

<span data-ttu-id="928b3-152">게스트는 목록을 만들거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-152">Guests can't create or delete a list.</span></span> <span data-ttu-id="928b3-153">기존 목록에 목록 항목을 추가 하 고, 목록 항목에 대 한 새 대화를 시작 하 고, 목록 항목에 대 한 기존 대화에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-153">They can add list items to existing lists, start new conversations about list items, and reply to existing conversations about list items.</span></span>

### <a name="lists-and-the-sharepoint-app"></a><span data-ttu-id="928b3-154">목록 및 SharePoint 앱</span><span class="sxs-lookup"><span data-stu-id="928b3-154">Lists and the SharePoint app</span></span>

<span data-ttu-id="928b3-155">조직의 사용자가 SharePoint 앱을 사용 하 여 목록을 만든 경우 해당 목록은 사용자가 작업을 수행 하지 않고 목록으로 자동으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-155">If users in your organization created lists using the SharePoint app, those lists will be automatically moved to Lists without any action needed from the user.</span></span> <span data-ttu-id="928b3-156">팀의 최상의 통합 경험을 얻으려면 목록 앱을 사용 하 여 기존 목록을 고정 다양.</span><span class="sxs-lookup"><span data-stu-id="928b3-156">To get the best and richest lists integration experience in Teams, use the Lists app and pin your existing lists.</span></span>

## <a name="set-up-lists"></a><span data-ttu-id="928b3-157">목록 설정</span><span class="sxs-lookup"><span data-stu-id="928b3-157">Set up Lists</span></span>

### <a name="enable-or-disable-lists-in-your-organization"></a><span data-ttu-id="928b3-158">조직의 목록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="928b3-158">Enable or disable Lists in your organization</span></span>

<span data-ttu-id="928b3-159">목록은 조직의 모든 팀 사용자에 대해 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-159">Lists is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="928b3-160">Microsoft 팀 관리 센터에서 [앱 관리](manage-apps.md) 페이지의 조직 수준에서 앱을 끄거나 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-160">You can turn off or turn on the app at the org level on the [Manage apps](manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="928b3-161">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-161">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="928b3-162">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-162">Do one of the following:</span></span>

    - <span data-ttu-id="928b3-163">조직의 목록을 끄려면 목록 앱을 검색 하 여 선택한 다음 **차단을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-163">To turn off Lists for your organization, search for the Lists app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="928b3-164">조직에 대 한 목록을 설정 하려면 목록 앱을 검색 하 여 선택한 다음 **허용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-164">To turn on Lists for your organization, search for the Lists app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a><span data-ttu-id="928b3-165">조직의 특정 사용자에 대해 목록 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="928b3-165">Enable or disable Lists for specific users in your organization</span></span>

<span data-ttu-id="928b3-166">조직의 특정 사용자가 목록을 사용 하는 것을 허용 하거나 차단 하려면 [앱 관리](manage-apps.md) 페이지에서 조직에 대 한 목록이 설정 되어 있는지 확인 한 다음 사용자 지정 앱 사용 권한 정책을 만들어 해당 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-166">To allow or block specific users in your organization from using Lists, make sure Lists is turned on for your organization on the [Manage apps](manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="928b3-167">자세히 알아보려면 [팀에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="928b3-167">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="search-the-audit-log-for-list-events"></a><span data-ttu-id="928b3-168">목록 이벤트 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="928b3-168">Search the audit log for list events</span></span>

<span data-ttu-id="928b3-169">목록은 엔터프라이즈 수준의 감사를 사용 하 여 사용할 수 있으므로 보안 & 준수 센터의 감사 로그에서 목록 및 목록 항목 이벤트를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-169">Lists are enabled with enterprise-level auditing so you can search for lists and list item events in the audit log in the Security & Compliance Center.</span></span> <span data-ttu-id="928b3-170">자세히 알아보려면 [보안 & 준수 센터에서 감사 로그 검색](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="928b3-170">To learn more, see [Search the audit log in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

<span data-ttu-id="928b3-171">팀의 목록 앱과 관련 된 감사 이벤트 목록은 [SharePoint 목록 활동](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="928b3-171">For a list of audit events that are relevant to the Lists app in Teams, see [SharePoint list activities](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).</span></span>

<span data-ttu-id="928b3-172">감사 로그를 검색 하려면 먼저 [보안 & 준수 센터](https://protection.office.com)에서 감사를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-172">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="928b3-173">감사 데이터는 감사를 설정한 지점 에서만 사용할 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="928b3-173">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="power-automate-power-apps-and-graph-api"></a><span data-ttu-id="928b3-174">Power 자동화, Power Apps 및 Graph API</span><span class="sxs-lookup"><span data-stu-id="928b3-174">Power Automate, Power Apps, and Graph API</span></span>

<span data-ttu-id="928b3-175">목록은 목록 양식에 대 한 워크플로 및 [Power 앱](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) 의 [전원 자동화](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint) 를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-175">Lists supports [Power Automate](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint) for workflows and [Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) for list forms.</span></span> <span data-ttu-id="928b3-176">개발자는 목록 [API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) 를 사용 하 여 Microsoft Graph를 통해 목록의 데이터를 원본으로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-176">Developers can use the [Lists API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) to connect list data as a source through Microsoft Graph.</span></span>

## <a name="give-feedback-or-report-an-issue"></a><span data-ttu-id="928b3-177">피드백 제공 또는 문제 보고</span><span class="sxs-lookup"><span data-stu-id="928b3-177">Give feedback or report an issue</span></span>
  
<span data-ttu-id="928b3-178">의견을 보내거나 문제를 신고 하려면 팀에서 왼쪽 탐색의 아래쪽에 있는 **도움말** 을 클릭 한 다음 **문제 보고**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-178">To send us feedback or report an issue, click **Help** near the bottom of the left navigation in Teams, and then select **Report a problem**.</span></span> <span data-ttu-id="928b3-179">**목록을**선택 하 고 발생 한 문제에 대 한 피드백 또는 세부 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-179">Select **Lists**, and then enter your feedback or details about the issue you're experiencing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="928b3-180">관련 항목</span><span class="sxs-lookup"><span data-stu-id="928b3-180">Related topics</span></span>

- [<span data-ttu-id="928b3-181">도움말 문서를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="928b3-181">Lists help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
