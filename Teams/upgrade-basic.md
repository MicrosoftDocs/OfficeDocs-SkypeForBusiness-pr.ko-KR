---
title: 업그레이드 검사 목록 | Skype에서 Teams로 업그레이드 | 기본 단계
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 이 가속화된 10단계 실행 계획을 따라 기본 비즈니스용 Skype 설정에서 Microsoft Teams 설정으로 전환합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- seo-marvel-apr2020
- Teams-upgrade-guidance
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-in
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37cc9f3940eb08a4df092042c016b194b01c64e6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809088"
---
# <a name="upgrade-basic"></a><span data-ttu-id="c66fc-103">기본 업그레이드</span><span class="sxs-lookup"><span data-stu-id="c66fc-103">Upgrade Basic</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="c66fc-104">소규모 조직이나 IM(채팅) 및 모임용으로만 비즈니스용 Skype Online을 사용하는 사용자용으로 설계된 업그레이드 기본 검사 목록은 비즈니스용 Skype에서 Teams로의 성공적인 이동을 구현하기 위한 핵심, 권장 활동 및 관련 리소스를 포함하는 가속화된 작업 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-104">Designed for smaller organizations or those using Skype for Business Online for IM (chat) and meetings only, the Upgrade Basic checklist is an accelerated action plan that includes core, recommended activities and associated resources for implementing a successful move from Skype for Business to Teams.</span></span>

<span data-ttu-id="c66fc-105">이 10단계는 성공적인 업그레이드에 필요한 모든 것을 제공하는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-105">These ten easy steps provide everything you need for a successful upgrade.</span></span> <span data-ttu-id="c66fc-106">약 30~45일 후 완료하도록 설계되지만 조직의 업그레이드 일정에 따라 작업 완료 날짜를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-106">They're designed to be completed in about 30 to 45 days, but you should adjust task completion dates based on your organization's upgrade schedule.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c66fc-107">비즈니스용 Skype Online은 2021년 7월 31일 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-107">Skype for Business Online will be retired on July 31, 2021.</span></span> <span data-ttu-id="c66fc-108">그 이후에는 비즈니스용 Skype Online 서비스에 더 이상 액세스하거나 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-108">After that time, the Skype for Business Online service will no longer be accessible or supported.</span></span> <span data-ttu-id="c66fc-109">혜택 구현을 극대화하고 조직이 업그레이드를 구현할 수 있는 적절한 시간을 확보하려면 지금 Microsoft Teams로의 여정을 시작하는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-109">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span>

<span data-ttu-id="c66fc-110">업그레이드 후 비즈니스용 Skype는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="c66fc-110">What happens to Skype for Business after the upgrade?</span></span> <span data-ttu-id="c66fc-111">사용자를 Teams로 업그레이드한 후(**Teams 전용** 모드):</span><span class="sxs-lookup"><span data-stu-id="c66fc-111">After your users are upgraded to Teams (**Teams Only** mode):</span></span>

- <span data-ttu-id="c66fc-112">비즈니스용 Skype 클라이언트가 비활성화되어 있으며 모든 채팅 및 통화가 Teams로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-112">Their Skype for Business client is disabled, and all chat and calls go to Teams.</span></span> <span data-ttu-id="c66fc-113">이 경우 데스크톱에서 클라이언트가 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-113">Note that this will not uninstall the client on their desktops.</span></span>
- <span data-ttu-id="c66fc-114">업그레이드가 계획된 것으로 작동하기 전에 예약된 비즈니스용 Skype 모임이지만 모든 새 모임은 Teams에서 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-114">Any Skype for Business meetings that were scheduled before the upgrade work as designed, but all new meetings are scheduled in Teams.</span></span> <span data-ttu-id="c66fc-115">비즈니스용 Skype 플러그 인은 Outlook에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-115">The Skype for Business plugin will no longer be available in Outlook.</span></span> 
- <span data-ttu-id="c66fc-116">사용자가 비즈니스용 Skype에 로그인하려고 시도하면 클라이언트로부터 Teams로 업그레이드했다는 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-116">If users try to sign in to Skype for Business, they get a notification from their client that they've been upgraded to Teams.</span></span>
- <span data-ttu-id="c66fc-117">사용자는 모바일 장치에서 비즈니스용 Skype 클라이언트를 수동으로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-117">Users need to manually uninstall the Skype for Business client on their mobile devices.</span></span>

<span data-ttu-id="c66fc-118">업그레이드에 [대한 추가 질문은 FAQ를](https://aka.ms/SkypeToTeams-FAQ) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c66fc-118">See our [FAQ](https://aka.ms/SkypeToTeams-FAQ) for additional questions about your upgrade.</span></span>

<span data-ttu-id="c66fc-119">Teams에 익숙하지 않은가요?</span><span class="sxs-lookup"><span data-stu-id="c66fc-119">Not familiar with Teams?</span></span> <span data-ttu-id="c66fc-120">[Teams가](https://products.office.com/microsoft-teams/group-chat-software) Microsoft 365 및 Office 365에서 팀워크를 위한 단일 허브를 제공하는 대화, 모임, 파일, Office 앱 및 타사 통합을 통합하는 방법을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-120">[Read about how Teams](https://products.office.com/microsoft-teams/group-chat-software) brings together conversations, meetings, files, Office apps, and third-party integrations—providing a single hub for teamwork in Microsoft 365 and Office 365.</span></span>

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a><span data-ttu-id="c66fc-121">1단계.</span><span class="sxs-lookup"><span data-stu-id="c66fc-121">Step 1.</span></span> <span data-ttu-id="c66fc-122">주요 이해 관계자에게 알림</span><span class="sxs-lookup"><span data-stu-id="c66fc-122">Notify your key stakeholders</span></span>

<span data-ttu-id="c66fc-123">*(업그레이드하기 약 4~6주 전)*</span><span class="sxs-lookup"><span data-stu-id="c66fc-123">*(About four to six weeks before the upgrade)*</span></span>

<span data-ttu-id="c66fc-124">선임 책임자에는 회사 성공에 대한 책임이 있습니다. 기술 변경에 대한 정보를 계속 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-124">Senior leaders are accountable for company success; be sure to keep them in the know about technology changes.</span></span> <span data-ttu-id="c66fc-125">모든 사람이 업그레이드 자격 알림을 받거나 읽지 않을 수 있기 때문에 업그레이드 계획을 시작하기 전에 이해 관계자(예: CEO, IT pros, Marketing 및 helpdesk 리드)에게 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-125">Because it's possible that not everyone received or read the notification of upgrade eligibility, you need to inform your stakeholders (for example, CEO, IT pros, Marketing, and helpdesk leads) before you begin planning your upgrade.</span></span>

<span data-ttu-id="c66fc-126">**리소스:**</span><span class="sxs-lookup"><span data-stu-id="c66fc-126">**Resources:**</span></span>

- [<span data-ttu-id="c66fc-127">샘플 전자 메일: 이해 관계자 통신</span><span class="sxs-lookup"><span data-stu-id="c66fc-127">Sample email: stakeholder communication</span></span>](upgrade-emails-surveys.md#step-1-email)

[<span data-ttu-id="c66fc-128">맨 위로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="c66fc-128">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a><span data-ttu-id="c66fc-129">2단계.</span><span class="sxs-lookup"><span data-stu-id="c66fc-129">Step 2.</span></span> <span data-ttu-id="c66fc-130">Teams를 사용하도록 조직 준비</span><span class="sxs-lookup"><span data-stu-id="c66fc-130">Prepare your organization for Teams</span></span>

<span data-ttu-id="c66fc-131">*(업그레이드하기 약 4~6주 전)*</span><span class="sxs-lookup"><span data-stu-id="c66fc-131">*(About four to six weeks before the upgrade)*</span></span>

<span data-ttu-id="c66fc-132">Teams는 IM(채팅) 및 모임과 같은 호환 가능한 비즈니스용 Skype 기능을 제공하지만 훨씬 더 많은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-132">Teams offers compatible Skype for Business functionality—such as IM (chat) and meetings—but it can also do so much more.</span></span> <span data-ttu-id="c66fc-133">팀워크를 위한 진정한 허브인 Teams를 사용하면 프로젝트, 파일, 대화 및 앱을 한 위치에서 모두 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-133">As a true hub for teamwork, Teams enables workgroups to manage projects, files, conversations, and apps all in one location.</span></span> <span data-ttu-id="c66fc-134">기본적으로 모든 조직에 Teams가 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-134">By default, Teams is turned on for all organizations.</span></span> <span data-ttu-id="c66fc-135">조직에서 Teams를 사용하는 방법을 결정하고 성공을 위해 환경을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-135">Decide how your organization will use Teams and configure your environment for success.</span></span> 

> [!Note]
> <span data-ttu-id="c66fc-136">기존 비즈니스용 Skype 고객은 현재 네트워크 인프라가 Teams에 대해 이미 구성되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-136">As an existing Skype for Business customer, your current network infrastructure is likely already configured for Teams.</span></span> <span data-ttu-id="c66fc-137">이를 확인하기 위해 아래와 연결된 "전체 기술 계획" 지침을 따를 수 있습니다(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="c66fc-137">To confirm this, you can follow the "Complete technical planning" guidance linked to below (this is optional).</span></span>

<span data-ttu-id="c66fc-138">**리소스:**</span><span class="sxs-lookup"><span data-stu-id="c66fc-138">**Resources:**</span></span>

- [<span data-ttu-id="c66fc-139">Teams 개요</span><span class="sxs-lookup"><span data-stu-id="c66fc-139">Overview of Teams</span></span>](Teams-overview.md)
- [<span data-ttu-id="c66fc-140">Microsoft Teams 시작하기</span><span class="sxs-lookup"><span data-stu-id="c66fc-140">Get started with Microsoft Teams</span></span>](get-started-with-teams-quick-start.md)

[<span data-ttu-id="c66fc-141">맨 위로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="c66fc-141">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a><span data-ttu-id="c66fc-142">3단계.</span><span class="sxs-lookup"><span data-stu-id="c66fc-142">Step 3.</span></span> <span data-ttu-id="c66fc-143">비즈니스용 Skype 사용자 확인</span><span class="sxs-lookup"><span data-stu-id="c66fc-143">Know your Skype for Business users</span></span>

<span data-ttu-id="c66fc-144">*(업그레이드 약 4주 전)*</span><span class="sxs-lookup"><span data-stu-id="c66fc-144">*(About four weeks before the upgrade)*</span></span>

<span data-ttu-id="c66fc-145">비즈니스용 Skype에 깊이 채택된 사용자는 Teams로 전환하는 데 약간의 시간이나 지원이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-145">Users who are deeply adopted on Skype for Business might need a little more time or assistance to make the transition to Teams.</span></span> <span data-ttu-id="c66fc-146">현재 비즈니스용 Skype 사용량을 검토하여 추가 지원이 필요한 상위 사용자를 식별하고 업그레이드 후 번호에 대해 추적할 수 있는 사용 기준을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="c66fc-146">Take time to review your current Skype for Business usage to identify your top users in need of additional support and to establish a usage baseline you can track against your post-upgrade numbers.</span></span>

<span data-ttu-id="c66fc-147">**리소스:**</span><span class="sxs-lookup"><span data-stu-id="c66fc-147">**Resources:**</span></span>

- [<span data-ttu-id="c66fc-148">관리 센터의 Microsoft 365 보고서</span><span class="sxs-lookup"><span data-stu-id="c66fc-148">Microsoft 365 reports in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports)

[<span data-ttu-id="c66fc-149">맨 위로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="c66fc-149">Return to top</span></span>](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a><span data-ttu-id="c66fc-150">4단계.</span><span class="sxs-lookup"><span data-stu-id="c66fc-150">Step 4.</span></span> <span data-ttu-id="c66fc-151">사용자에게 비즈니스용 Skype에서 Teams로 업그레이드된다고 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-151">Notify your users that they'll be upgrading from Skype for Business to Teams</span></span>

<span data-ttu-id="c66fc-152">*(업그레이드하기 약 2~3주 전)*</span><span class="sxs-lookup"><span data-stu-id="c66fc-152">*(About two to three weeks before the upgrade)*</span></span>

<span data-ttu-id="c66fc-153">사용자에게 알기 좋은 공지를 제공하면 생산성에 부정적인 영향을 주지 않고 Teams에 익숙해지면서 더 긍정적인 사용자 환경을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-153">Providing ample notice to your users will give them time to get familiar with Teams without negatively affecting their productivity, resulting in a more positive user experience.</span></span> <span data-ttu-id="c66fc-154">통신을 보내 변경된 변경, 변경 이유 및 준비 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-154">Send a communication to tell them what's changing, why it's changing, and how they can prepare for it.</span></span>

> [!Note]
> <span data-ttu-id="c66fc-155">필요한 경우 현재 Microsoft 365 관리 센터를 통해 사용자에 대해 Teams를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-155">If needed, you can enable Teams for your users via the Microsoft 365 admin center at this time.</span></span>

<span data-ttu-id="c66fc-156">**리소스:**</span><span class="sxs-lookup"><span data-stu-id="c66fc-156">**Resources:**</span></span>

- [<span data-ttu-id="c66fc-157">조직에서 Microsoft Teams 설정 관리</span><span class="sxs-lookup"><span data-stu-id="c66fc-157">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="c66fc-158">샘플 전자 메일: 사용자에게 비즈니스용 Skype에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="c66fc-158">Sample email: announcement to users about Skype for Business</span></span>](upgrade-emails-surveys.md#step-4-email)

[<span data-ttu-id="c66fc-159">맨 위로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="c66fc-159">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a><span data-ttu-id="c66fc-160">5단계.</span><span class="sxs-lookup"><span data-stu-id="c66fc-160">Step 5.</span></span> <span data-ttu-id="c66fc-161">사용자 업그레이드 알림 활성화</span><span class="sxs-lookup"><span data-stu-id="c66fc-161">Activate the user upgrade notification</span></span>

<span data-ttu-id="c66fc-162">*(업그레이드 약 1주 전)*</span><span class="sxs-lookup"><span data-stu-id="c66fc-162">*(About one week before the upgrade)*</span></span>

<span data-ttu-id="c66fc-163">관리 포털을 통해 사용자 업그레이드 알림을 사용하도록 설정하여 비즈니스용 Skype 클라이언트에서 사용자가 비즈니스용 Skype에서 Teams로 업그레이드되고 있는 시각적 알림을 제공하여 업그레이드 모멘텀을 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="c66fc-163">Maintain upgrade momentum by enabling the user upgrade notification via the admin portal, providing a visual alert in the Skype for Business client that users are being upgraded from Skype for Business to Teams.</span></span>

<span data-ttu-id="c66fc-164">**리소스:**</span><span class="sxs-lookup"><span data-stu-id="c66fc-164">**Resources:**</span></span>

- [<span data-ttu-id="c66fc-165">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="c66fc-165">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="c66fc-166">맨 위로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="c66fc-166">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a><span data-ttu-id="c66fc-167">6단계.</span><span class="sxs-lookup"><span data-stu-id="c66fc-167">Step 6.</span></span> <span data-ttu-id="c66fc-168">사용자에게 비즈니스용 Skype에서 Teams로 업그레이드할 것 을 미리 알림</span><span class="sxs-lookup"><span data-stu-id="c66fc-168">Remind your users that they'll be upgrading from Skype for Business to Teams</span></span>

<span data-ttu-id="c66fc-169">*(업그레이드 약 5일 전)*</span><span class="sxs-lookup"><span data-stu-id="c66fc-169">*(About five days before the upgrade)*</span></span>

<span data-ttu-id="c66fc-170">사용자는 일상적인 책임으로 바쁘게 일하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-170">Users are busy with their daily responsibilities.</span></span> <span data-ttu-id="c66fc-171">보류 중인 업그레이드를 상기하면 Teams를 준비하는 데 필요한 단계를 기억하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-171">Reminding them of the pending upgrade will help ensure they remember to take the steps they need to prepare for Teams.</span></span> <span data-ttu-id="c66fc-172">사용 가능한 교육 및 Teams를 시작하는 방법을 사용자에게 알리는 완벽한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-172">This is the perfect time to remind users about available training and how to get started with Teams.</span></span>

<span data-ttu-id="c66fc-173">**리소스:**</span><span class="sxs-lookup"><span data-stu-id="c66fc-173">**Resources:**</span></span>

- [<span data-ttu-id="c66fc-174">샘플 전자 메일: 사용자에게 Teams 시작 미리 알림</span><span class="sxs-lookup"><span data-stu-id="c66fc-174">Sample email: remind users to get started with Teams</span></span>](upgrade-emails-surveys.md#step-6-email)

[<span data-ttu-id="c66fc-175">맨 위로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="c66fc-175">Return to top</span></span>](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a><span data-ttu-id="c66fc-176">7단계.</span><span class="sxs-lookup"><span data-stu-id="c66fc-176">Step 7.</span></span> <span data-ttu-id="c66fc-177">사용자를 Teams로 업그레이드하세요!</span><span class="sxs-lookup"><span data-stu-id="c66fc-177">Upgrade users to Teams!</span></span>

<span data-ttu-id="c66fc-178">*(업그레이드 일)*</span><span class="sxs-lookup"><span data-stu-id="c66fc-178">*(Upgrade Day)*</span></span>

<span data-ttu-id="c66fc-179">오늘은 조직이 커뮤니케이션 및 공동 작업 솔루션으로 Teams로 공식적으로 업그레이드하는 날입니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-179">Today is the day your organization officially upgrades to Teams as your communication and collaboration solution.</span></span> <span data-ttu-id="c66fc-180">Microsoft Teams 관리 센터에서 공존 모드를 Teams 전용으로 설정하여 업그레이드 스위치를 **활성화합니다.**</span><span class="sxs-lookup"><span data-stu-id="c66fc-180">In the Microsoft Teams admin center, activate the upgrade switch by setting the coexistence mode to **Teams Only**.</span></span> <span data-ttu-id="c66fc-181">(관리 센터에서 전체 **설정으로 이동**  >  **Teams 업그레이드.)** 사용자는 비즈니스용 Skype 클라이언트에서 Teams로 업그레이드했다는 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-181">(In the admin center, go to **Org-wide Settings** > **Teams Upgrade**.) Users will receive a notification in their Skype for Business client that they've been upgraded to Teams.</span></span>

<span data-ttu-id="c66fc-182">모든 사람이 업그레이드된 후 Teams에 환영 전자 메일을 보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-182">We recommend that after everyone has been upgraded, you send an email welcoming them to Teams.</span></span>

<span data-ttu-id="c66fc-183">**리소스:**</span><span class="sxs-lookup"><span data-stu-id="c66fc-183">**Resources:**</span></span>

- [<span data-ttu-id="c66fc-184">공존 및 업그레이드 설정 지정</span><span class="sxs-lookup"><span data-stu-id="c66fc-184">Set your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)
- [<span data-ttu-id="c66fc-185">샘플 전자 메일: Teams에 대한 사용자 환영</span><span class="sxs-lookup"><span data-stu-id="c66fc-185">Sample email: welcome users to Teams</span></span>](upgrade-emails-surveys.md#step-7-email)

[<span data-ttu-id="c66fc-186">맨 위로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="c66fc-186">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a><span data-ttu-id="c66fc-187">8단계.</span><span class="sxs-lookup"><span data-stu-id="c66fc-187">Step 8.</span></span> <span data-ttu-id="c66fc-188">기준에 대한 Teams 사용량 모니터링</span><span class="sxs-lookup"><span data-stu-id="c66fc-188">Monitor Teams usage against your baseline</span></span>

<span data-ttu-id="c66fc-189">*(업그레이드 후 약 1~2주 후)*</span><span class="sxs-lookup"><span data-stu-id="c66fc-189">*(About one or two weeks after the upgrade)*</span></span>

<span data-ttu-id="c66fc-190">새 기술에 맞게 조정하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-190">Adjusting to a new technology can take some time.</span></span> <span data-ttu-id="c66fc-191">사용량을 확인하여 사용자가 비즈니스용 Skype와 동일한 수준 또는 그 이상으로 Teams를 사용하고 있는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-191">Check usage to verify that users are using Teams at the same—or greater—level as they did with Skype for Business.</span></span> <span data-ttu-id="c66fc-192">예상된 수준에서 Teams를 사용하지 않는 사용자로 체크 인합니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-192">Check in with users who aren't using Teams at expected levels.</span></span>

<span data-ttu-id="c66fc-193">**리소스:**</span><span class="sxs-lookup"><span data-stu-id="c66fc-193">**Resources:**</span></span>

- [<span data-ttu-id="c66fc-194">사용 현황 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="c66fc-194">See usage data</span></span>](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[<span data-ttu-id="c66fc-195">맨 위로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="c66fc-195">Return to top</span></span>](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a><span data-ttu-id="c66fc-196">9단계.</span><span class="sxs-lookup"><span data-stu-id="c66fc-196">Step 9.</span></span> <span data-ttu-id="c66fc-197">사용자 만족도 측정</span><span class="sxs-lookup"><span data-stu-id="c66fc-197">Measure user satisfaction</span></span>

<span data-ttu-id="c66fc-198">*(업그레이드 후 약 1~2주 후)*</span><span class="sxs-lookup"><span data-stu-id="c66fc-198">*(About one or two weeks after the upgrade)*</span></span>

<span data-ttu-id="c66fc-199">직원 만족도는 생산성, 보존 및 궁극적으로 비즈니스 결과에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-199">Employee satisfaction can influence productivity, retention, and—ultimately—business outcomes.</span></span> <span data-ttu-id="c66fc-200">사용자에게 도달하여 업그레이드에 대한 사용자 감정과 Teams에 대한 만족도를 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-200">Reach out to your users to gauge user sentiment about the upgrade and their satisfaction with Teams.</span></span>

<span data-ttu-id="c66fc-201">**리소스:**</span><span class="sxs-lookup"><span data-stu-id="c66fc-201">**Resources:**</span></span>

- <span data-ttu-id="c66fc-202">[샘플 전자 메일: 사용자 및](upgrade-emails-surveys.md#step-9-email)사용자 설문 조사 [체크](upgrade-emails-surveys.md#step-9-surveys) 인</span><span class="sxs-lookup"><span data-stu-id="c66fc-202">[Sample email: check in with users](upgrade-emails-surveys.md#step-9-email), plus [user surveys](upgrade-emails-surveys.md#step-9-surveys)</span></span>

[<span data-ttu-id="c66fc-203">맨 위로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="c66fc-203">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a><span data-ttu-id="c66fc-204">10단계.</span><span class="sxs-lookup"><span data-stu-id="c66fc-204">Step 10.</span></span> <span data-ttu-id="c66fc-205">Teams를 통해 ROI 최대화</span><span class="sxs-lookup"><span data-stu-id="c66fc-205">Maximize your ROI with Teams</span></span>

<span data-ttu-id="c66fc-206">*(진행 중)*</span><span class="sxs-lookup"><span data-stu-id="c66fc-206">*(Ongoing)*</span></span>

<span data-ttu-id="c66fc-207">사용자가 Teams에서 IM(채팅) 및 모임에 익숙해진 후 Teams 공동 작업 및 앱 통합을 사용하여 사용 사례를 확장하고 새 솔루션을 진정으로 최적화하고 투자 수익률을 극대화하도록 장려합니다.</span><span class="sxs-lookup"><span data-stu-id="c66fc-207">After users are comfortable with IM (chat) and meetings in Teams, encourage them to extend their use case by using Teams collaboration and app integration, truly optimizing their new solution and maximizing a return on your investment.</span></span>

<span data-ttu-id="c66fc-208">**리소스:**</span><span class="sxs-lookup"><span data-stu-id="c66fc-208">**Resources:**</span></span>

- [<span data-ttu-id="c66fc-209">샘플 전자 메일: 사용자가 Teams를 더 탐색하도록 장려</span><span class="sxs-lookup"><span data-stu-id="c66fc-209">Sample email: encourage users to explore Teams further</span></span>](upgrade-emails-surveys.md#step-10-email)

[<span data-ttu-id="c66fc-210">맨 위로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="c66fc-210">Return to top</span></span>](#about-upgrade-basic)
