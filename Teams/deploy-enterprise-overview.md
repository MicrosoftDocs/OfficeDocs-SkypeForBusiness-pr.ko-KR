---
title: Microsoft Teams 엔터프라이즈 배포 개요
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Microsoft Teams의 엔터프라이즈 기능을 배포하는 방법을 알아봅니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b751ccebfd553f59b6144ea6b6f28db515e9c1d
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395430"
---
# <a name="teams-enterprise-deployment-overview"></a><span data-ttu-id="96339-103">Teams 엔터프라이즈 배포 개요</span><span class="sxs-lookup"><span data-stu-id="96339-103">Teams enterprise deployment overview</span></span>

<span data-ttu-id="96339-104">중소 기업인 경우, 사용자에게 서비스를 배포할 방법, Microsoft Teams 클라이언트를 배포할 방법, 네트워크 디자인이 실시간 커뮤니케이션에 미치는 영향 등을 생각해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-104">If you're a medium or large business, you need to think about how you're going to roll out the service to your users, how you're going to deploy the Microsoft Teams client to them, how your network design could impact the quality of real-time communication, and so on.</span></span> <span data-ttu-id="96339-105">조직에서 Teams를 계획하는 데 도움이 되는 문서 포인터는 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-105">Check out the following sections for pointers to articles that'll help you plan for Teams in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="96339-106">아직 완료하지 않은 경우, Teams 배포 파일럿을 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="96339-106">If you haven't done so already, we strongly suggest that you begin your Teams deployment with a pilot.</span></span> <span data-ttu-id="96339-107">파일럿을 통해 사용자와 일부 얼리어답터는 계획 및 최종 배포 전에 Teams와 Teams의 기능에 익숙해질 수 있습니다. 파일럿을 시작하는 방법에 대한 자세한 내용은 [Microsoft Teams 시작](get-started-with-teams-quick-start.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-107">A pilot will allow you and a few early adopters to get familiar with Teams and its features before your planning and eventual roll out. For more information about how to start your pilot, check out [Get started with Microsoft Teams](get-started-with-teams-quick-start.md).</span></span>

<span data-ttu-id="96339-108">섹션을 읽고 조직에 Teams 배포를 시작할 준비가 되었다면 [기업에서 Microsoft Teams 설정](deploy-enterprise-setup.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-108">After you've read the sections below and are ready to start deploying Teams in your organization, see [Set up Microsoft Teams in your enterprise](deploy-enterprise-setup.md).</span></span>

## <a name="architecture"></a><span data-ttu-id="96339-109">아키텍처</span><span class="sxs-lookup"><span data-stu-id="96339-109">Architecture</span></span>

<span data-ttu-id="96339-110">Teams는 Microsoft 365와 긴밀하게 통합되어 있으며 채팅, 파일 공유, 모임, 전화, 비디오 스트리밍 등 다양한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96339-110">Teams is tightly integrated into Microsoft 365 and uses many features to power chat, file sharing, meetings, telephony, video streaming, and more.</span></span> <span data-ttu-id="96339-111">Teams를 배포하기 전에 [Microsoft Teams IT 아키텍처 및 전화 솔루션 포스터](teams-architecture-solutions-posters.md)를 확인하여 Teams가 다른 Microsoft 365 앱과 작동하는 방식을 확인하여 사용자를 위한 완벽한 공동 작업 환경을 만드세요.</span><span class="sxs-lookup"><span data-stu-id="96339-111">Before you roll out Teams, check out [Microsoft Teams IT architecture and telephony solutions posters](teams-architecture-solutions-posters.md) to get familiar with how Teams works with the rest of Microsoft 365 to create a complete collaboration experience for your users.</span></span>

## <a name="workloads"></a><span data-ttu-id="96339-112">워크로드</span><span class="sxs-lookup"><span data-stu-id="96339-112">Workloads</span></span>

<span data-ttu-id="96339-113">Teams에는 서로 독립적으로 구현할 수 있는 세 가지 워크로드(**채팅, 팀 및 채널**, **모임 및 회의**, **전화 시스템 및 공중 전화망(PSTN) 연결)** 이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96339-113">Teams has three workloads that can be deployed independently of each other: **chat, teams, and channels**; **meetings and conferencing**; and **Phone System and PSTN (public switched telephone network) connectivity**.</span></span> <span data-ttu-id="96339-114">각 워크로드에는 해당 워크로드에 대한 정보를 더 쉽게 찾을 수 있도록 문서에 자체 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96339-114">Each workload has its own section in our documentation to make it easier to find information about that workload.</span></span> <span data-ttu-id="96339-115">여기에는 배포 계획 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96339-115">This includes deployment planning information.</span></span>

<span data-ttu-id="96339-116">배포하려는 워크로드에 대한 배포 계획 정보를 확인하려면 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-116">To see deployment planning information for the workload you want to deploy, see the following articles:</span></span>

- [<span data-ttu-id="96339-117">채팅, 팀 및 채널</span><span class="sxs-lookup"><span data-stu-id="96339-117">Chat, teams, and channels</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [<span data-ttu-id="96339-118">모임 및 회의</span><span class="sxs-lookup"><span data-stu-id="96339-118">Meetings and conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="96339-119">전화 시스템 및 공중 전화망(PSTN) 연결</span><span class="sxs-lookup"><span data-stu-id="96339-119">Phone System and PSTN connectivity</span></span>](cloud-voice-landing-page.md)

## <a name="network-planner"></a><span data-ttu-id="96339-120">네트워크 플래너</span><span class="sxs-lookup"><span data-stu-id="96339-120">Network planner</span></span>

<span data-ttu-id="96339-121">Teams에 대한 네트워크 계획은 사용자 수가 많거나, 네트워크 규모가 복잡하거나 또는 둘 다에 해당하는 경우 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-121">Network planning for Teams is extremely important when you have large numbers of users, complex networks, or both.</span></span> <span data-ttu-id="96339-122">Teams는 음성 통화 및 화상 회의를 지원하며, 두 팀 모두 실시간 통신을 통해 사용자에게 최상의 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-122">Teams supports voice calling and video conferencing, both of which rely on real-time communications to provide the best experience possible for users.</span></span> <span data-ttu-id="96339-123">네트워크는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-123">Networks must:</span></span>

- <span data-ttu-id="96339-124">동시 음성 통화, 화상 회의, 모임, 화면 공유 수를 수용할 수 있는 충분한 대역폭양이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-124">Have sufficient bandwidth capacity to accommodate the number of concurrent voice calls, video conferences, meetings, screen sharing, and so on.</span></span>
- <span data-ttu-id="96339-125">실시간 통신 프로토콜을 지원하는 네트워크 하드웨어가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-125">Have network hardware that supports real-time communication protocols.</span></span>
- <span data-ttu-id="96339-126">네트워크의 장치, Microsoft 365 서비스 및 외부 사용자 간에 필요한 네트워크 포트를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-126">Allow the required network ports between devices on your networks, Microsoft 365 services, and external users.</span></span>

<span data-ttu-id="96339-127">Teams 네트워크 요구 사항을 이해하는 데 도움이 되는 문서는 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-127">See the following articles to help you understand Teams network requirements:</span></span>

- [<span data-ttu-id="96339-128">Microsoft Teams에 대한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="96339-128">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)
- [<span data-ttu-id="96339-129">Teams 또는 비즈니스용 Skype Online 용 프록시 서버</span><span class="sxs-lookup"><span data-stu-id="96339-129">Proxy servers for Teams or Skype for Business Online</span></span>](proxy-servers-for-skype-for-business-online.md)

<span data-ttu-id="96339-130">계획에 도움을 줄 수 있도록 Teams에는 네트워크 플래너가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96339-130">To help you with your planning, Teams includes the Network planner.</span></span> <span data-ttu-id="96339-131">네트워크 플래너는 사용자가 있는 사용자의 수와 유형, 조직에 있는 사이트 수, 네트워크 연결의 대역폭양 등에 대해 질문합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-131">The Network planner asks you questions about the number and types of users you have, how many sites your organization has, the bandwidth capacity of your network links, and more.</span></span> <span data-ttu-id="96339-132">네트워크 플래너는 이 정보를 사용하여 각 활동에 대한 대역폭 요구 사항과 권장 사항을 표시하는 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96339-132">Using this information, the Network planner creates a report that shows the bandwidth requirements for each activity, along with the recommendations.</span></span>

 > [!div class="nextstepaction"]
> [<span data-ttu-id="96339-133">네트워크 플래너로 이동</span><span class="sxs-lookup"><span data-stu-id="96339-133">Go to Network planner</span></span>](https://admin.teams.microsoft.com/networkplanner/organization)

<span data-ttu-id="96339-134">(네트워크 플래너를 열려는 경우, [Microsoft 365 전역 관리자](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles)여야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="96339-134">(You must be a [Microsoft 365 global admin](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Network planner.)</span></span>

<span data-ttu-id="96339-135">네트워크 플래너 작동 방식에 대한 자세한 내용은 [Microsoft Teams용 네트워크 플래너 사용](network-planner.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-135">For details about how the Network planner works, see [Use the Network planner for Microsoft Teams](network-planner.md).</span></span>

<span data-ttu-id="96339-136">네트워크 플래너가 네트워크를 계획하는 방법에 대한 예제를 확인하려면 [네트워크 플래너 사용 - 예제 시나리오](tutorial-network-planner-example.yml)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-136">To see an example of how Network planner can plan your network, see [Using Network Planner - example scenario](tutorial-network-planner-example.yml).</span></span>

## <a name="teams-advisor"></a><span data-ttu-id="96339-137">Teams 어드바이저</span><span class="sxs-lookup"><span data-stu-id="96339-137">Teams advisor</span></span>

<span data-ttu-id="96339-138">Teams 어드바이저는 팀, 채널, 파일 공유 및 Planner를 모아 조직의 배포 프로젝트를 만드는 Teams 내 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="96339-138">The Teams advisor is a solution within Teams that brings together teams, channels, file sharing, and Planner, to create a deployment project for your organization.</span></span> <span data-ttu-id="96339-139">Teams 어드바이저는 사용자가 선택한 워크로드(예: 채팅, 팀 및 채널)와 관련된 프로젝트 계획을 작성합니다. 이 작업에는 배포 중에 수행해야 하는 권장 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96339-139">Teams advisor creates project plan, specific to the workload you select (such as chat, teams, and channels), that includes the recommended tasks you should perform during your deployment.</span></span> <span data-ttu-id="96339-140">각 작업에는 프로세스를 안내하는 지침, 제안 및 관련 문서에 대한 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96339-140">Each task contains instructions, suggestions, and links to relevant articles, to guide you through the process.</span></span> <span data-ttu-id="96339-141">한 개 이상의 사용자에게 작업을 쉽게 할당하고 각 작업에 대한 시작 및 종료 날짜를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96339-141">You can easily assign tasks to one or more individuals, and specify start and end dates for each task.</span></span>

> [!TIP]
> <span data-ttu-id="96339-142">Microsoft Learn에서 [Teams Advisor를 사용하여 원격 설치](https://docs.microsoft.com/learn/modules/m365-teams-rollout-using-advisor/) 모듈을 완료하여 Teams 어드바이저를 사용하여 Teams 배포를 계획하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-142">See how you can use Teams advisor to help you plan your Teams deployment by completing the [Roll out using the Teams advisor](https://docs.microsoft.com/learn/modules/m365-teams-rollout-using-advisor/) module on Microsoft Learn.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="96339-143">Teams 어드바이저로 이동</span><span class="sxs-lookup"><span data-stu-id="96339-143">Go to Teams advisor</span></span>](https://admin.teams.microsoft.com/teams-deployment)

<span data-ttu-id="96339-144">(Teams 어드바이저를 열려는 경우, [Microsoft 365 전역 관리자](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles)여야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="96339-144">(You must be a [Microsoft 365 global admin](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Teams advisor.)</span></span>

<span data-ttu-id="96339-145">Teams 어드바이저의 작동 방법에 대한 자세한 내용은 [Teams 어드바이저를 사용하여 Microsoft Teams 배포](use-advisor-teams-roll-out.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-145">For details about how the Teams advisor works, see [Use Advisor for Teams to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span>

## <a name="lifecycle-and-governance-planning"></a><span data-ttu-id="96339-146">수명 주기 및 거버넌스 계획</span><span class="sxs-lookup"><span data-stu-id="96339-146">Lifecycle and governance planning</span></span>

<span data-ttu-id="96339-147">Teams 배포를 계획할 때 조직의 팀, 채널, 파일 수명 주기 등을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-147">As you plan your Teams deployment, you need to consider the lifecycle of teams, channels, files, and so on, in your organization.</span></span> <span data-ttu-id="96339-148">또한 저장할 정보 유형에 대해 고민해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-148">You should also think about what types of information will be stored in them.</span></span> <span data-ttu-id="96339-149">Teams는 특정 프로젝트나 부서에 대해 만들어지거나 전체 조직의 중앙 리소스로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96339-149">Teams may be created for a specific project, for a department, or they might be used as a central resource for the entire organization.</span></span> <span data-ttu-id="96339-150">다른 요구 사항을 가진 사용에는 다음과 같은 질문이 제기될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96339-150">Each of these uses have different requirements, which drive questions like the following:</span></span>

- <span data-ttu-id="96339-151">팀이 얼마나 유지될 것인가?</span><span class="sxs-lookup"><span data-stu-id="96339-151">How long will the teams remain active?</span></span>
- <span data-ttu-id="96339-152">누가 팀과 채널을 소유하고 관리해야 하나?</span><span class="sxs-lookup"><span data-stu-id="96339-152">Who should own and manage the teams and their channels?</span></span>
- <span data-ttu-id="96339-153">일부 팀에 적용되는 특정 규정 준수 요구 사항을 다른 팀에도 적용해야 하나?</span><span class="sxs-lookup"><span data-stu-id="96339-153">Should certain compliance requirements apply to some teams, but not others?</span></span>
- <span data-ttu-id="96339-154">사용자가 올바른 팀을 식별하는 데 도움이 되는 이름 정책이 있어야 하나?</span><span class="sxs-lookup"><span data-stu-id="96339-154">Should there be a naming policy to help users identify the right team?</span></span>

<span data-ttu-id="96339-155">초기 배포의 일부로 정책 및 지침을 만들면 사용자가 필요한 정보를 찾을 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96339-155">Creating policies and guidelines as part of your initial deployment will help ensure that your users can find the information they need.</span></span> <span data-ttu-id="96339-156">그러나 적절한 정책은 정보 누출로부터 조직을 보호하고, 규정 요구 사항을 준수하고, 보관 목적으로 필요한 정보를 보존하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96339-156">Just as importantly, however, appropriate policies will help protect your organization from information leakage, help you conform to regulatory requirements, and help you retain information as needed for archival purposes.</span></span>

<span data-ttu-id="96339-157">Teams의 수명 주기 관리 및 거버넌스에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-157">To learn more about lifecycle management and governance in Teams, see the following:</span></span>

- [<span data-ttu-id="96339-158">Teams에서 수명 주기 관리 계획</span><span class="sxs-lookup"><span data-stu-id="96339-158">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
- [<span data-ttu-id="96339-159">Teams에서 거버넌스 계획</span><span class="sxs-lookup"><span data-stu-id="96339-159">Plan for governance in Teams</span></span>](plan-teams-governance.md)

## <a name="adoption"></a><span data-ttu-id="96339-160">채택</span><span class="sxs-lookup"><span data-stu-id="96339-160">Adoption</span></span>

<span data-ttu-id="96339-161">조직과 사용자가 Teams를 최대한 활용하려면 채택 프로그램이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-161">To ensure that your organization and your users get the most out of Teams, you need an adoption program.</span></span> <span data-ttu-id="96339-162">효과적인 채택 프로그램은 다음을 수행할 수 있는 얼리어답터를 동원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96339-162">An effective adoption program can mobilize early adopters who can:</span></span>

- <span data-ttu-id="96339-163">동료와 비즈니스 또는 그룹 리더에게 Teams의 이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-163">Articulate the benefits of Teams to their colleagues and to business or group leaders.</span></span>
- <span data-ttu-id="96339-164">Teams가 어떻게 공동 작업을 개선하고 서로 더 쉽게 연결할 수 있는지 보는 다른 사람들에게 흥미를 유발합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-164">Spark excitement in others who see how Teams improves collaboration and makes it easier to connect with each other.</span></span>
- <span data-ttu-id="96339-165">기존 비즈니스 프로세스를 평가하고 Teams가 여기에 통합될 수 있는 방법을 추천할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-165">Help evaluate existing business processes and make recommendations for how Teams can be integrated into them.</span></span>
- <span data-ttu-id="96339-166">채택 프로세스를 개선하는 데 도움이 되는 개선 사항과 문제를 배포 팀에 다시 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="96339-166">Report back to the deployment team both successes and difficulties to help improve the adoption process.</span></span>

<span data-ttu-id="96339-167">채택 프로그램 설정에 대한 자세한 내용은 [Microsoft Teams 채택](adopt-microsoft-teams-landing-page.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96339-167">For details about setting up an adoption program, see [Adopt Microsoft Teams](adopt-microsoft-teams-landing-page.md).</span></span>