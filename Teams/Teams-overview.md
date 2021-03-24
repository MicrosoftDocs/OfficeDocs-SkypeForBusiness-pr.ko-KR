---
title: Microsoft Teams에 오신 것을 환영합니다.
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: serdars
description: 조직에서 Microsoft Teams를 배포하기 위한 올바른 경로를 찾습니다. Teams 인프라 및 Microsoft 365 혹은 Office 365를 통한 Teams의 사용에 대해 알아보세요.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.allteamsdocuments
appliesto:
- Microsoft Teams
ms.openlocfilehash: e93e30c2c6eeffc2232b6d9049af8d1224f24532
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094404"
---
# <a name="welcome-to-microsoft-teams"></a><span data-ttu-id="19056-104">Microsoft Teams에 오신 것을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-104">Welcome to Microsoft Teams</span></span>
<span data-ttu-id="19056-105">조직에서 Microsoft Teams의 관리자인 경우 제대로 찾아오셨습니다.</span><span class="sxs-lookup"><span data-stu-id="19056-105">If you're the admin for Microsoft Teams in your organization, you're in the right place.</span></span> <span data-ttu-id="19056-106">Teams를 시작할 준비가 되면 [Teams 배포 방법](./deploy-overview.md)과 함께 시작해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="19056-106">When you're ready to get going with Teams, start with [How to roll out Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="19056-107">Teams를 새로 사용하는 사용자로서 자세히 알아보려면 당사의 짧은 [Teams에 오신 것을 환영합니다](https://www.youtube.com/embed/s3aQV3T0D6c) 비디오를 시청하세요(55초).</span><span class="sxs-lookup"><span data-stu-id="19056-107">If you're new to Teams and want to learn more, check out our short [Welcome to Teams](https://www.youtube.com/embed/s3aQV3T0D6c) video (55 seconds).</span></span>

<span data-ttu-id="19056-108">Teams 관리자를 위한 Teams에 오신 것을 환영합니다 비디오를 놓치지 마세요(3분 조금 초과).</span><span class="sxs-lookup"><span data-stu-id="19056-108">Don't miss our Welcome to Teams for the Teams admin video (just over 3 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE47cdp]

<span data-ttu-id="19056-109">최종 사용자 Teams 도움말을 찾고 있는 경우 앱의 왼쪽에 있는 **도움말** 을 클릭하거나 [Microsoft Teams 도움말 센터](https://support.office.com/teams)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-109">If you're looking for end user Teams Help, click **Help** on the left side of the app, or go to the [Microsoft Teams help center](https://support.office.com/teams).</span></span> <span data-ttu-id="19056-110">교육을 받으려면 [Microsoft Teams 교육](training-microsoft-teams-landing-page.md)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-110">For training, go to [Microsoft Teams Training](training-microsoft-teams-landing-page.md).</span></span> 

## <a name="teams-architecture"></a><span data-ttu-id="19056-111">Teams 아키텍처</span><span class="sxs-lookup"><span data-stu-id="19056-111">Teams architecture</span></span>

<span data-ttu-id="19056-112">Teams는 Microsoft 365 그룹, Microsoft Graph, Microsoft 365 및 Office 365의 나머지와 동일한 엔터프라이즈 수준의 보안, 규정 준수 및 관리 용이성을 기반으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="19056-112">Teams is built on Microsoft 365 groups, Microsoft Graph, and the same enterprise-level security, compliance, and manageability as the rest of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="19056-113">Teams는 Azure Active Directory(Azure AD)에 저장 된 ID를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-113">Teams leverages identities stored in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="19056-114">Teams는 사용자가 오프라인 상태이거나 네트워크 상태가 불규칙해도 계속해서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-114">Teams keeps working even when you're offline or experiencing spotty network conditions.</span></span>

<span data-ttu-id="19056-115">Microsoft 365의 환경에서 Teams가 부합하는 위치를 확인하려면 이 아키텍처 포스터 [Microsoft 365의 일부로서의 Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-115">To see where Teams fits in the context of Microsoft 365, check out this architecture poster:  [Teams as part of Microsoft 365](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)</span></span>

<span data-ttu-id="19056-116">팀을 만들면 다음과 같은 항목이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="19056-116">When you create a team, here's what gets created:</span></span>
- <span data-ttu-id="19056-117">새 [Microsoft 365 그룹](office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="19056-117">A new [Microsoft 365 group](office-365-groups.md)</span></span>
- <span data-ttu-id="19056-118">팀 파일을 저장하는 [SharePoint Online](sharepoint-onedrive-interact.md) 사이트 및 문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="19056-118">A [SharePoint Online](sharepoint-onedrive-interact.md) site and document library to store team files</span></span>
- <span data-ttu-id="19056-119">[Exchange Online](exchange-teams-interact.md) 공유 사서함 및 일정</span><span class="sxs-lookup"><span data-stu-id="19056-119">An [Exchange Online](exchange-teams-interact.md) shared mailbox and calendar</span></span>
- <span data-ttu-id="19056-120">OneNote 전자 필기장</span><span class="sxs-lookup"><span data-stu-id="19056-120">A OneNote notebook</span></span>
- <span data-ttu-id="19056-121">Planner, Power BI 등과 같은 다른 Microsoft 365 및 Office 365 앱으로 연결</span><span class="sxs-lookup"><span data-stu-id="19056-121">Ties into other Microsoft 365 and Office 365 apps such as Planner and Power BI</span></span>

<span data-ttu-id="19056-122">기존의 그룹에서 팀을 만들면 해당 그룹의 구성원, 사이트, 사서함 및 전자 필기장이 Teams에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19056-122">When you create a team from an existing group, that group's membership, site, mailbox, and notebook are surfaced in Teams.</span></span> <span data-ttu-id="19056-123">자세한 내용은 [IT 설계자용 Microsoft 365의 그룹](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 포스터를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-123">To learn more, check out this poster: [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span></span>

<span data-ttu-id="19056-124">Teams를 사용자 지정하고 확장하려면 [앱, 봇 그리고 커넥터](deploy-apps-microsoft-teams-landing-page.md)를 통해 타사 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-124">To customize and extend Teams, add third-party apps through [apps, bots, and connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="19056-125">Teams를 사용하여 조직 외부의 사용자를 팀 또는 채널에 [게스트로 추가](guest-access.md)하여 포함시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19056-125">With Teams, you can include people from outside your organization by [adding them as a guest](guest-access.md) to a team or channel.</span></span> <span data-ttu-id="19056-126">Microsoft 365 및 Office 365의 일부로서 Teams는 조직에 필요한 팀워크 허브를 구축할 수 있는 견실한 [개발 플랫폼](/microsoftteams/platform)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-126">As part of Microsoft 365 and Office 365, Teams offers a robust [development platform](/microsoftteams/platform) so you can build the teamwork hub you need for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="19056-127">Teams 아키텍처에 대한 자세한 내용은 [Teams 플랫폼 아카데미](https://aka.ms/TeamsPlatformAcademy)에 있는 비디오를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-127">For a deep dive into Teams architecture, watch the videos on the [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy).</span></span>


## <a name="managing-teams"></a><span data-ttu-id="19056-128">Teams 관리하기</span><span class="sxs-lookup"><span data-stu-id="19056-128">Managing Teams</span></span>

<span data-ttu-id="19056-129">관리자는 Microsoft Teams 관리 센터를 통해 Teams를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-129">As the admin, you'll manage Teams through the Microsoft Teams admin center.</span></span> <span data-ttu-id="19056-130">빠르게 살펴보기 위해서는 Teams 관리 센터 비디오(3:03분)를 사용하여 Teams 관리를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-130">For a quick orientation, watch the Manage Teams using the Teams admin center video (3:03 min):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yi]

<span data-ttu-id="19056-131">자세한 정보:</span><span class="sxs-lookup"><span data-stu-id="19056-131">To learn more:</span></span>

- [<span data-ttu-id="19056-132">Teams 관리자 역할을 사용하여 Teams를 관리</span><span class="sxs-lookup"><span data-stu-id="19056-132">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="19056-133">Teams 관리 센터에서 Teams를 관리</span><span class="sxs-lookup"><span data-stu-id="19056-133">Manage Teams in the Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="19056-134">새로운 Teams 관리 센터로 전환하는 동안 Teams를 관리</span><span class="sxs-lookup"><span data-stu-id="19056-134">Manage Teams during the transition to the new Teams admin center</span></span>](manage-teams-in-modern-portal.md)
- [<span data-ttu-id="19056-135">Office 365 혹은 Microsoft 365에서 Teams 기능 관리</span><span class="sxs-lookup"><span data-stu-id="19056-135">Manage Teams features in your Microsoft 365 or Office 365</span></span>](enable-features-office-365.md)

<span data-ttu-id="19056-136">조직에서 Teams와 다른 모든 Microsoft 365 혹은 Office 365 제품 및 서비스에 대한 최신 정보를 확인하려면 [메시지 센터](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) 및 [Teams 로드맵](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)을 반드시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-136">To stay on top of what's coming for Teams and all other Microsoft 365 or Office 365 products and services in your organization, be sure to check [Message center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) and the [Teams roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams).</span></span> <span data-ttu-id="19056-137">사용자에게 계속해서 정보를 제공하고 준비된 상태로 유지를 시켜주는데 도움이 되는 새로운 기능과 업데이트된 기능, 계획된 변경 사항 그리고 문제에 대한 공지 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19056-137">You'll get announcements about new and updated features, planned changes, and issues to help keep you informed and prepared.</span></span> 

## <a name="upgrade-from-skype-for-business-to-teams"></a><span data-ttu-id="19056-138">비즈니스용 Skype에서 Teams로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="19056-138">Upgrade from Skype for Business to Teams</span></span>
<span data-ttu-id="19056-139">Teams는 Microsoft 365 및 Office 365에서의 지능형 커뮤니케이션을 위한 기본 클라이언트이며 결국 비즈니스용 Skype Online을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-139">Teams is the primary client for intelligent communications in Microsoft 365 and Office 365, and it'll eventually replace Skype for Business Online.</span></span> <span data-ttu-id="19056-140">Teams에 제공될 새로운 기능에 대한 최신 정보를 확인하려면 [Microsoft 365 로드맵](https://aka.ms/O365Roadmap)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-140">To stay on top of new features coming to Teams, see the [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap).</span></span> <span data-ttu-id="19056-141">지속적인 채팅 및 메시징 기능을 보완하기 위해 Teams는 완전히 통합된 기본으로 제공되는 음성 및 비디오를 통해 포괄적인 모임 및 통화 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-141">To complement persistent chat and messaging capabilities, Teams offers a comprehensive meeting and calling experience, with built in, fully integrated voice and video.</span></span> <span data-ttu-id="19056-142">Microsoft Teams 블로그에서 [Teams는 이제 완벽한 모임 및 통화 솔루션입니다](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-142">Check out [Teams is now a complete meeting and calling solution](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042) in the Microsoft Teams Blog.</span></span>

<span data-ttu-id="19056-143">비즈니스용 Skype를 실행 중이고 Teams로 업그레이드할 준비가 되었거나 비즈니스용 Skype 및 Teams를 함께 실행 중이고 Teams로 완전히 이동할 준비가 된 경우에 전환이 제대로 진행되도록 도움을 줄 수 있는 도구, 팁 및 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19056-143">If you're running Skype for Business and are ready to upgrade to Teams, or if you're running Skype for Business and Teams side-by-side and are ready to fully move to Teams, we have the tools, tips, and guidance to help make your transition successful.</span></span> <span data-ttu-id="19056-144">자세한 내용은 [Teams로 업그레이드](upgrade-start-here.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-144">To learn more, see [Upgrade to Teams](upgrade-start-here.md).</span></span>

## <a name="teamwork"></a><span data-ttu-id="19056-145">팀워크</span><span class="sxs-lookup"><span data-stu-id="19056-145">Teamwork</span></span>
<span data-ttu-id="19056-146">모든 팀은 상이합니다. 공동 작업을 수행하는 데 모든 접근 방식을 충족시킬 수 있는 단 한가지의 방식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19056-146">Every team is different; there's no one-size-fits-all approach to collaboration.</span></span> <span data-ttu-id="19056-147">Microsoft 365 및 Office 365는 모든 팀의 고유한 요구 사항을 충족하도록 설계되었으며 사용자가 목적에 맞도록 만들어진 통합된 응용 프로그램을 통해 통신, 공동 작업 그리고 더 많은 작업을 달성할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="19056-147">Microsoft 365 and Office 365 are designed to meet the unique needs of every team, empowering people to communicate, collaborate, and achieve more with purpose-built, integrated applications.</span></span>

<span data-ttu-id="19056-148">사용할 Microsoft 365 혹은 Office 365 앱과 서비스를 결정할 때는 조직에서 수행하는 작업 및 팀에서 필요한 대화의 유형에 대해서 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-148">When deciding which Microsoft 365 or Office 365 apps and services to use, think about the work your organization does and the types of conversations your teams need to have.</span></span> 

- <span data-ttu-id="19056-149">팀워크의 허브로서 **Teams** 는 조직 외부의 사용자를 포함하여 사용자들이 활발하게 실시간으로 연결하고 공동 작업을 하여 업무를 수행할 수 있는 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="19056-149">**Teams**, as the hub for teamwork, is where people - including people outside your organization - can actively connect and collaborate in real time to get things done.</span></span> <span data-ttu-id="19056-150">문서를 공동 작성하거나, 모임을 진행하고 있거나 혹은 다른 앱 및 서비스에서 함께 작업을 하던지에 상관없이 작업이 진행 중인 곳에서 바로 대화를 나누어보세요.</span><span class="sxs-lookup"><span data-stu-id="19056-150">Have a conversation right where the work is happening, whether coauthoring a document, having a meeting, or working together in other apps and services.</span></span> <span data-ttu-id="19056-151">Teams는 비공식적인 채팅을 하고, 프로젝트에서 신속히 반복 적용을 하고, 팀 파일을 사용하여 작업을 하고, 공유 결과물을 가지고 공동 작업을 할 수 있는 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="19056-151">Teams is the place to have informal chats, iterate quickly on a project, work with team files, and collaborate on shared deliverables.</span></span> 

- <span data-ttu-id="19056-152">친숙한 전자 메일 환경에서 더욱 공식적이고 구조적인 방식으로 공동 작업을 하거나 대상이 지정되고 및 직접 통신이 필요한 경우에 공동 작업을 하기 위한 **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="19056-152">**Outlook** for collaborating in the familiar environment of email and in a more formal, structured manner or when targeted and direct communication is required.</span></span>

- <span data-ttu-id="19056-153">사이트, 포털, 지능형 콘텐츠 서비스, 비즈니스 프로세스 자동화 그리고 엔터프라이즈 검색을 위한 **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="19056-153">**SharePoint** for sites, portals, intelligent content services, business process automation, and enterprise search.</span></span> <span data-ttu-id="19056-154">SharePoint는 팀들 간에 모든 유형의 콘텐츠를 쉽게 공유하고 액세스할 수 있도록 팀워크의 중앙에 콘텐츠를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="19056-154">SharePoint keeps content at the center of teamwork, making all types of content easily shareable and accessible across teams.</span></span> <span data-ttu-id="19056-155">Outlook, Yammer 및 Teams와의 긴밀한 통합을 통해 여러 대화 환경에서 원활한 콘텐츠 공동 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19056-155">Tight integration with Outlook, Yammer, and Teams enables seamless content collaboration across conversation experiences.</span></span>

- <span data-ttu-id="19056-156">사용자가 초대하는 사용자들과 파일을 저장하고 공유할 수 있는 **비즈니스용 OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="19056-156">**OneDrive for Business** for storing files and sharing them with people that a user invites.</span></span> <span data-ttu-id="19056-157">사용자가 비즈니스용 OneDrive에 저장하는 콘텐츠는 사용자가 다른 사용자와 공유할 때까지 비공개이기에 공유할 목적이 아니거나 공유할 준비가 되지 않은 개인 및 초안 문서를 저장하는 데 가장 적합한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="19056-157">Content that a user saves to OneDrive for Business is private until the user shares it with others, making it the best option for storing personal and draft documents that are not intended to be shared or not ready to be shared.</span></span>

- <span data-ttu-id="19056-158">조직 전체에서 사용자를 연결할 수 있는 **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="19056-158">**Yammer** to connect people across the organization.</span></span> <span data-ttu-id="19056-159">회사 전체의 이니셔티브를 주도하고 모범 사례를 공유하며 관심있는 공통 주제 혹은 업무 분야에 대한 커뮤니티를 구축하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-159">Drive company-wide initiatives, share best practices, and build communities around common topics of interest or areas of practice.</span></span> <span data-ttu-id="19056-160">아이디어를 크라우드 소싱하여 회사 전체 사용자들과의 공개 토론을 촉진하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-160">Crowdsource ideas to foster open discussions with people across the company.</span></span>

- <span data-ttu-id="19056-161">**Office 앱** 은 Word, Excel, PowerPoint 및 OneNote를 비롯하여 사용자가 알고 정기적으로 사용하는 모든 친숙한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="19056-161">**Office apps** are all the familiar tools that people know and use regularly, including Word, Excel, PowerPoint, and OneNote.</span></span> 

## <a name="teams-content-updates"></a><span data-ttu-id="19056-162">Teams 콘텐츠 업데이트</span><span class="sxs-lookup"><span data-stu-id="19056-162">Teams content updates</span></span>

<span data-ttu-id="19056-163">[업데이트된 Teams 주제의 주간 목록](teams-updates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-163">See a [weekly list of Teams topics that have been updated](teams-updates.md).</span></span>

## <a name="teams-known-issues"></a><span data-ttu-id="19056-164">Teams의 알려진 문제점</span><span class="sxs-lookup"><span data-stu-id="19056-164">Teams known issues</span></span>

<span data-ttu-id="19056-165">[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams). 참조</span><span class="sxs-lookup"><span data-stu-id="19056-165">See [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span>

## <a name="teams-client-release-notes"></a><span data-ttu-id="19056-166">Teams 클라이언트 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="19056-166">Teams client release notes</span></span>

<span data-ttu-id="19056-167">[Teams에서의 새로운 기능](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19056-167">See [What's new in Teams](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).</span></span>