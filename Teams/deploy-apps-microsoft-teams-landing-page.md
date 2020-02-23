---
title: Microsoft Teams의 앱, 봇 및 커넥터
ms.reviewer: ''
description: 다음 배포 리소스를 사용하여 Microsoft에서 앱을 배포하는 데 도움을 주세요.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c2ef9f509f64e044567d9286704458b4dc91596
ms.sourcegitcommit: 7093388425b34c80e444a50d062290187b80047d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2020
ms.locfileid: "42229903"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a><span data-ttu-id="0c10b-103">Microsoft Teams의 앱, 봇 및 커넥터</span><span class="sxs-lookup"><span data-stu-id="0c10b-103">Apps, bots, & connectors in Microsoft Teams</span></span>

<span data-ttu-id="0c10b-104">앱을 사용하여 자주 사용하는 서비스에서 콘텐츠를 찾고 Teams에서 바로 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-104">Apps let you find content from your favorite services and share it right in Teams.</span></span> <span data-ttu-id="0c10b-105">앱을 통해 채널 상단에 있는 서비스를 고정하거나 봇과 채팅하거나 작업을 공유하고 지정하는 등의 작업을 수행 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-105">They help you do things such as pin services at the top of a channel, chat with bots, or share and assign tasks.</span></span> <span data-ttu-id="0c10b-106">자세한 내용은 [Teams의 앱 개요](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-106">To learn more, read [Overview of apps in Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).</span></span>

<span data-ttu-id="0c10b-107">초기 Teams 롤아웃을 진행 시 Planner와 같은 추천 앱을 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-107">We recommend that you include our featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="0c10b-108">Teams의 채택을 주도하면서 다른 앱, 봇 및 커넥터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-108">Add other apps, bots, & connectors as you drive Teams adoption.</span></span>

<span data-ttu-id="0c10b-109">자신만의 사용자 지정 앱을 만드는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-109">You also have the option of creating your own custom apps.</span></span> <span data-ttu-id="0c10b-110">자세한 내용은 [개발자 설명서](/microsoftteams/platform/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-110">See our [developer documentation](/microsoftteams/platform/overview) for more information.</span></span>

## <a name="apps-deployment-decisions"></a><span data-ttu-id="0c10b-111">앱 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="0c10b-111">Apps deployment decisions</span></span>

<span data-ttu-id="0c10b-112">Teams는 조직을 위해 즉시 사용 가능한 뛰어난 공동 작업 환경을 제공하고 대부분의 조직에 그 기본 설정이 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-112">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="0c10b-113">이 문서에서는 조직의 프로필 및 비즈니스 요구 사항에 따라 기본 설정을 변경할지 여부를 결정 하는데 도움을 주고 각 변경 내용에 대해 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-113">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="0c10b-114">당사는 사용자가 [변경할 가능성이 큰](#core-deployment-decisions) 변경 내용의 핵심 집합에서 시작하여 설정을 두 그룹으로 나누었습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-114">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="0c10b-115">두 번째 그룹은 조직의 요구 사항에 따라 구성하고자 하는 [추가 설정](#additional-deployment-decisions)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-115">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="0c10b-116">핵심 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="0c10b-116">Core deployment decisions</span></span>

<span data-ttu-id="0c10b-117">대부분의 조직이 변경하려는 앱 설정입니다 (Teams의 기본 설정이 적합하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="0c10b-117">These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).</span></span>

### <a name="app-availability-settings"></a><span data-ttu-id="0c10b-118">앱 가용성 설정</span><span class="sxs-lookup"><span data-stu-id="0c10b-118">App availability settings</span></span> 

<span data-ttu-id="0c10b-119">Teams는 사용자를 참여시키고 생산성을 지원하며 일반적으로 사용되는 비즈니스 서비스를 Teams로 통합하기 위한 Microsoft 및 타사에서 게시한 앱을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-119">Teams provides a number of apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="0c10b-120">Teams 스토어에서 앱을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-120">Get apps from the Teams Store.</span></span> <span data-ttu-id="0c10b-121">기본적으로 [Teams 스토어 승인 프로세스](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)를 통해 제출한 사용자 지정 앱을 포함하여 모든 앱이 모든 사용자에게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-121">By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users.</span></span> <span data-ttu-id="0c10b-122">예를 들어, 사용자는 Planner 앱을 사용하여 Teams에서 팀 작업을 구축하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-122">For example, users can use the Planner app to build and manage team tasks in Teams.</span></span>

<span data-ttu-id="0c10b-123">기본적으로 모든 Microsoft 제공 앱 및 사용자 지정 앱을 사용할 수 있으며 개별적으로 앱을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-123">By default, all Microsoft-provided and custom apps are available, and you can turn individual apps on or off.</span></span> <span data-ttu-id="0c10b-124">전체 조직에 대해 모든 사용자 지정 앱을 설정하거나 해제할 수 있는 조직 전체 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-124">There's an org-wide setting that lets you turn all custom apps on or off for your entire organization.</span></span>

| <span data-ttu-id="0c10b-125">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="0c10b-125">Ask yourself</span></span> | <span data-ttu-id="0c10b-126">작업</span><span class="sxs-lookup"><span data-stu-id="0c10b-126">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="0c10b-127">기본 Teams 앱 설정을 변경하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="0c10b-127">Will you change the default Teams apps settings?</span></span> | <span data-ttu-id="0c10b-128">조직에서 앱을 관리하는 데 사용할 수 있는 정책과 설정에 대한 자세한 내용은 [Microsoft Teams에서 앱 관리 설정](admin-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-128">For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="app-permissions-and-other-considerations"></a><span data-ttu-id="0c10b-129">앱 사용 권한 및 기타 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0c10b-129">App permissions and other considerations</span></span>

<span data-ttu-id="0c10b-130">앱은 사용자가 동의하고 정책을 통해 관리자나 IT 전문가가 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-130">Apps are consented to by users and managed by the admin or IT pro through policies.</span></span> <span data-ttu-id="0c10b-131">그러나 대부분의 경우 앱의 사용 권한 및 위험 프로필이 앱 자체에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-131">However, for the most part, an app's permissions and risk profile are defined in the app itself.</span></span> 

| <span data-ttu-id="0c10b-132">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="0c10b-132">Ask yourself</span></span> | <span data-ttu-id="0c10b-133">작업</span><span class="sxs-lookup"><span data-stu-id="0c10b-133">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="0c10b-134">액세스를 허용하려는 앱은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="0c10b-134">Which apps do I want to allow access to?</span></span> <span data-ttu-id="0c10b-135">액세스를 허용하지 않으려는 앱은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="0c10b-135">Which ones do I not want to allow access to?</span></span>  | <ul><li><span data-ttu-id="0c10b-136">앱, 봇, 탭 또는 커넥터에 대한 액세스를 허용할 때 고려해야 할 사항의 목록을 보려면 [Microsoft Teams 앱 사용 권한과 고려 사항](app-permissions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-136">See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</span></span></li><li><span data-ttu-id="0c10b-137">조직의 사용자가 앱을 사용할 수 있도록 하는 방법에 대한 자세한 내용은 [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-137">See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</span></span></li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a><span data-ttu-id="0c10b-138">개인 채팅 및 채널을 위한 봇</span><span class="sxs-lookup"><span data-stu-id="0c10b-138">Bots for private chats and channels</span></span>

<span data-ttu-id="0c10b-139">봇은 사용자가 흥미를 느끼거나 정보를 얻고자 하는 세부 정보에 대해 쿼리에 응답하거나 업데이트 및 알림을 제공하는 자동화된 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-139">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="0c10b-140">봇은 Teams 채팅을 통해 사용자가 클라우드 서비스(예: 작업 관리, 일정 관리 및 설문조사 등)와 상호 작용할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-140">Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat.</span></span> <span data-ttu-id="0c10b-141">Teams는 개인 채팅 및 채널을 통해 봇을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-141">Teams supports bots in private chats and channels.</span></span> <span data-ttu-id="0c10b-142">관리자는 Office 365 테넌트에서 봇의 사용을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-142">Administrators can control whether the use of bots is allowed in an Office 365 tenant.</span></span>

| <span data-ttu-id="0c10b-143">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="0c10b-143">Ask yourself</span></span> | <span data-ttu-id="0c10b-144">작업</span><span class="sxs-lookup"><span data-stu-id="0c10b-144">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="0c10b-145">Office 365 테넌트에 사용자 지정 봇을 허용하고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="0c10b-145">Do I want to allow custom bots in my Office 365 tenant?</span></span>|<span data-ttu-id="0c10b-146">봇 추가에 대한 자세한 내용은 [Microsoft Teams에서 개인 채팅 및 채널을 위한 봇 추가](add-bots.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-146">For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](add-bots.md).</span></span> <span data-ttu-id="0c10b-147">사용자 지정 봇을 켜거나 끄는 방법에 대한 자세한 내용은 [Microsoft Teams에서 앱 관리 설정](admin-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-147">For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="built-in-and-custom-tabs"></a><span data-ttu-id="0c10b-148">기본 제공 및 사용자 지정 탭</span><span class="sxs-lookup"><span data-stu-id="0c10b-148">Built-in and custom tabs</span></span>

<span data-ttu-id="0c10b-149">소유자와 팀 구성원은 채널, 비공개 채팅 및 그룹 채팅에 탭을 추가하여 클라우드 서비스와 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-149">Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services.</span></span> <span data-ttu-id="0c10b-150">사용자가 필요로 하거나 가장 많이 사용하는 데이터에 액세스하고 관리하는 데 도움이 되는 탭을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-150">Add tabs to help users access and manage the data they need or use the most.</span></span> <span data-ttu-id="0c10b-151">채널에서는 대화 및 파일 탭이 기본적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-151">In channels, the Conversations and Files tabs are created by default.</span></span> <span data-ttu-id="0c10b-152">모든 개인 채팅에서 대화, 파일, 조직 및 활동 탭이 기본적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-152">In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default.</span></span> <span data-ttu-id="0c10b-153">이러한 기본 제공 탭 외에도 사용자 지정 탭을 디자인하고 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-153">In addition to these built-in tabs, you can design and add custom tabs.</span></span> <span data-ttu-id="0c10b-154">조직에서 Teams 앱을 켜거나 끄는 방법에 대해 알아보려면 [Team에서 앱에 대한 관리 설정](admin-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-154">To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).</span></span>

| <span data-ttu-id="0c10b-155">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="0c10b-155">Ask yourself</span></span> | <span data-ttu-id="0c10b-156">작업</span><span class="sxs-lookup"><span data-stu-id="0c10b-156">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="0c10b-157">Office 365 테넌트에 사용자 지정 탭을 허용하고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="0c10b-157">Do I want to allow custom tabs in my Office 365 tenant?</span></span>|<span data-ttu-id="0c10b-158">자세한 내용은 [Teams에서 기본 제공 및 사용자 지정 탭 사용](built-in-custom-tabs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-158">For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).</span></span>|
|||

### <a name="office-365-and-custom-connectors"></a><span data-ttu-id="0c10b-159">Office 365 및 사용자 지정 커넥터</span><span class="sxs-lookup"><span data-stu-id="0c10b-159">Office 365 and custom connectors</span></span>

<span data-ttu-id="0c10b-160">커넥터는 자주 사용하는 서비스의 콘텐츠와 업데이트를 채널에 직접 제공하여 팀을 최신 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-160">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="0c10b-161">커넥터를 사용하면 Teams 사용자는 Teams 채팅에서 Twitter, Trello, Wunderlist, GitHub 및 Azure DevOps 서비스와 같은 인기 서비스로부터 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-161">With connectors, your Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.</span></span>

| <span data-ttu-id="0c10b-162">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="0c10b-162">Ask yourself</span></span> | <span data-ttu-id="0c10b-163">작업</span><span class="sxs-lookup"><span data-stu-id="0c10b-163">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="0c10b-164">사용자가 사용자 지정 커넥터를 만들 수 있도록 허용하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0c10b-164">Do I want to allow users to create custom connectors?</span></span>|<span data-ttu-id="0c10b-165">자세한 내용은 [Teams에서 Office 365 및 사용자 지정 커넥터 사용](office-365-custom-connectors.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-165">For more information, see [Use Office 365 and custom connectors in Teams](office-365-custom-connectors.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="0c10b-166">추가 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="0c10b-166">Additional deployment decisions</span></span>

<span data-ttu-id="0c10b-167">조직의 요구 사항 및 구성에 따라 이러한 설정을 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-167">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="activity-reports"></a><span data-ttu-id="0c10b-168">활동 보고서</span><span class="sxs-lookup"><span data-stu-id="0c10b-168">Activity reports</span></span>

<span data-ttu-id="0c10b-169">활동 보고서를 사용하여 조직의 사용자가 Teams를 어떻게 사용하고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-169">You can use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="0c10b-170">예를 들어, 아직 Teams를 사용하고 있지 않은 경우 Teams를 사용하여 생산성과 공동 작업을 향상 시키는 방법을 모를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-170">For example, if some don’t use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="0c10b-171">조직에서 활동 보고서를 사용하여 교육 및 커뮤니케이션 노력에 대한 우선 순위를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-171">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> <span data-ttu-id="0c10b-172">활동 보고서를 보려면 Office 365의 전역 관리자, Teams 서비스 관리자 또는 비즈니스용 Skype 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-172">To view activity reports, you must be a global admin in Office 365, Teams service admin, or Skype for Business admin.</span></span>

| <span data-ttu-id="0c10b-173">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="0c10b-173">Ask yourself</span></span> | <span data-ttu-id="0c10b-174">작업</span><span class="sxs-lookup"><span data-stu-id="0c10b-174">Action</span></span> |
|--------------|--------|
| <br><span data-ttu-id="0c10b-175">활동 보고서를 확인해야 하는 사용자는 누구이고 그들은 보고서를 볼 수 있는 올바른 권한을 보유하고 있나요?</span><span class="sxs-lookup"><span data-stu-id="0c10b-175">Who needs to see the activity reports, and do they have the correct permissions to view them?</span></span> |<ul><li><span data-ttu-id="0c10b-176">사용자에게 관리자 역할을 할당하고 싶지 않은 경우 [보고서 읽기 역할을 할당](teams-activity-reports.md#reports-reader-role)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-176">If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="0c10b-177">Azure Active Directory에서 관리자 역할을 할당하는 방법에 대한 자세한 내용은 [역할 및 사용 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)과 [역할 보기 및 할당](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-177">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</span></span></li></ul> |
|||

### <a name="app-templates"></a><span data-ttu-id="0c10b-178">앱 서식 파일</span><span class="sxs-lookup"><span data-stu-id="0c10b-178">App templates</span></span>

<span data-ttu-id="0c10b-179">앱 서식 파일은 커뮤니티 중심의 오픈 소스이며 GitHub에서 사용할 수 있는 Microsoft Teams용 프로덕션 준비 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-179">App templates are production-ready apps for Microsoft Teams that are community driven, open-source, and available on GitHub.</span></span> <span data-ttu-id="0c10b-180">각각에는 조직에 해당 앱을 배포 및 설치하는 방법에 대한 자세한 지침이 포함되어 있으며, 즉시 설치하고 사용할 수 있는 바로 사용 가능한 앱을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-180">Each contains detailed instructions for deploying and installing that app for your organization, providing a ready-to-use app that you can install and begin using immediately.</span></span> <span data-ttu-id="0c10b-181">전체 소스 코드도 제공되므로 세부 정보를 살펴보고 코드를 포크하여 특정 요구 사항에 맞게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c10b-181">The complete source code is available as well, so you can explore it in detail,or fork the code and alter it to meet your specific needs.</span></span>

| <span data-ttu-id="0c10b-182">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="0c10b-182">Ask yourself</span></span> | <span data-ttu-id="0c10b-183">작업</span><span class="sxs-lookup"><span data-stu-id="0c10b-183">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="0c10b-184">Icebreaker와 같은 Teams 앱 서식 파일을 설치하고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="0c10b-184">Do I want to install any Teams app templates, such as Icebreaker?</span></span> |<span data-ttu-id="0c10b-185">자세한 내용을 보려면 [Teams용 앱 서식 파일](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="0c10b-185">To learn more, read [App templates for Teams](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="0c10b-186">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0c10b-186">Next steps</span></span>
- <span data-ttu-id="0c10b-187">Planner와 같은 추천 앱의 [도입을 주도](adopt-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="0c10b-187">[Drive adoption](adopt-microsoft-teams-landing-page.md) of featured apps, such as Planner.</span></span>
- [<span data-ttu-id="0c10b-188">모임 및 회의 출시</span><span class="sxs-lookup"><span data-stu-id="0c10b-188">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="0c10b-189">클라우드 음성 출시</span><span class="sxs-lookup"><span data-stu-id="0c10b-189">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)


