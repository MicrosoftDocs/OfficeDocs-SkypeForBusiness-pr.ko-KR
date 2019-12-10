---
title: Advisor for Teams(미리 보기)를 사용하여 Microsoft Teams 배포
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: Advisor for Teams(미리 보기)를 사용하여 Microsoft Teams 배포를 계획하고 완료할 수 있습니다.
ms.openlocfilehash: 63a3ae01dbe47323fd9227e65fa8c38a2d725ddf
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909474"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a><span data-ttu-id="1122f-103">Advisor for Teams를 사용하여 Microsoft Teams 배포</span><span class="sxs-lookup"><span data-stu-id="1122f-103">Use Advisor for Teams to help you roll out Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="1122f-104">Advisor for Teams(미리 보기)는 Microsoft 팀이 배포 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-104">Advisor for Teams (preview) walks you through your Microsoft Teams rollout.</span></span> <span data-ttu-id="1122f-105">Office 365 테넌트 환경을 평가하고 Teams를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-105">It assesses your Office 365 tenant environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span> <span data-ttu-id="1122f-106">그런 다음 Advisor for Teams는 배포하려는 각 워크로드에 대한 채널로 배포 팀(Teams에서)을 만듭니다. 서비스 관리 팀의 각 워크로드에는 각 워크로드에 대한 모든 롤아웃 작업이 포함된 포괄적인 Planner 플랜이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-106">Then, Advisor for Teams creates a Deployment team (in Teams), with channels for each workload you want to roll out. Each workload in the Deployment team comes with a comprehensive Planner plan that includes all the rollout tasks for each workload.</span></span>  <span data-ttu-id="1122f-107">이 Planner 플랜을 사용하여 프로젝트 관리자, Teams 및 Office 365 관리자, 지원자, 채택 및 사용자 준비 상태 팀 등의 각 롤아웃 단계를 담당하는 사용자에게 작업을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-107">Using this Planner plan, you'll assign tasks to the people responsible for each phase of the rollout - including the project manager, Teams and Office 365 admins, support people, and your adoption and user readiness team.</span></span> <span data-ttu-id="1122f-108">각 롤아웃 작업에는 해당 작업을 완료하는 데 필요한 모든 가이드 및 리소스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-108">Each rollout task contains all the guidance and resources you need to successfully complete the task.</span></span>

<span data-ttu-id="1122f-109">Advisor for Teams는 [Teams 관리 센터](https://admin.teams.microsoft.com)의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-109">Advisor for Teams is part of the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="1122f-110">Advisor for Teams를 처음 사용하려면 대시보드의 **팀 워크로드 배포** 위젯에서 **시작** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-110">To use Advisor for Teams the first time, click the **Start** button in the **Deploying Teams workload** widget on the Dashboard.</span></span> <span data-ttu-id="1122f-111">또는 **계획** > **관리자**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-111">Or go to **Planning** > **Advisor**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1122f-112">Advisor for Teams는 Microsoft 365 정부 기관, GCC High 또는 DoD 배포에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-112">Advisor for Teams isn't available for Microsoft 365 Government - GCC High or DoD deployments.</span></span>

<span data-ttu-id="1122f-113">이 [Teams 배포 및 구성 소개](https://youtu.be/o2mlsUubIO4?t=44) 동영상 (Advisor for Teams는 0:50-3:15 분)에서 Advisor for Teams를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1122f-113">Check out Advisor for Teams in this [Deploy & Configure Teams Intro](https://youtu.be/o2mlsUubIO4?t=44) video (Advisor for Teams is at 0:50-3:15 minutes).</span></span>

## <a name="using-advisor-for-teams-preview"></a><span data-ttu-id="1122f-114">Advisor for Teams 사용(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1122f-114">Using Advisor for Teams (preview)</span></span>

<span data-ttu-id="1122f-115">Advisor for Teams를 사용하기 위해 Teams 관리자가 될 필요는 없습니다. 조직 내 누구나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-115">You don't have to be a Teams admin to use Advisor for Teams - anybody in your organization can use it.</span></span> <span data-ttu-id="1122f-116">Advisor for Teams가 Teams 관리 센터에 있어도 관리자가 아닌 사용자가 액세스할 수 있도록 특별 권한을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-116">We've set up special permissions so non-admin users can get to Advisor for Teams, even though it's in the Teams admin center.</span></span> <span data-ttu-id="1122f-117">테넌트 준비 상태 평가를 열려면 Teams 관리자, Teams 서비스 관리자 또는 전역 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-117">You DO have to be a Teams admin, Teams Service Administrator, or Global Administrator to open the tenant readiness assessments.</span></span>

<span data-ttu-id="1122f-118">Advisor for Teams를 처음으로 사용하는 경우 Teams에서 사용자를 위한 배포 팀이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-118">The first time you use Advisor for Teams, it'll create a Deployment team for you in Teams.</span></span> <span data-ttu-id="1122f-119">여기에 배포하려는 각 워크로드의 채널이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-119">It adds channels for each workload you want to roll out.</span></span> 


## <a name="available-advisor-for-teams-plans"></a><span data-ttu-id="1122f-120">사용 가능한 Advisor for Teams 계획</span><span class="sxs-lookup"><span data-stu-id="1122f-120">Available Advisor for Teams plans</span></span>

<span data-ttu-id="1122f-121">Advisor for Teams가 미리 보기에 있는 동안에는 다음과 같은 두 가지 플랜이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-121">While Advisor for Teams is in preview, we're providing these two plans:</span></span>

1. <span data-ttu-id="1122f-122">채팅, 팀, 채널 및 앱</span><span class="sxs-lookup"><span data-stu-id="1122f-122">Chat, teams, channels, and apps</span></span>
    - <span data-ttu-id="1122f-123">테넌트 평가</span><span class="sxs-lookup"><span data-stu-id="1122f-123">Tenant assessment</span></span>
    - <span data-ttu-id="1122f-124">채택 작업을 포함한 Planner 플랜</span><span class="sxs-lookup"><span data-stu-id="1122f-124">Planner plan, including adoption tasks</span></span>
    - <span data-ttu-id="1122f-125">Forms 사용자 설문 조사</span><span class="sxs-lookup"><span data-stu-id="1122f-125">Forms user survey</span></span>
1. <span data-ttu-id="1122f-126">모임 및 회의</span><span class="sxs-lookup"><span data-stu-id="1122f-126">Meetings and conferencing</span></span>
    - <span data-ttu-id="1122f-127">테넌트 평가</span><span class="sxs-lookup"><span data-stu-id="1122f-127">Tenant assessment</span></span>
    - <span data-ttu-id="1122f-128">채택 작업을 포함한 Planner 플랜</span><span class="sxs-lookup"><span data-stu-id="1122f-128">Planner plan, including adoption tasks</span></span>
    - <span data-ttu-id="1122f-129">Forms 사용자 설문 조사</span><span class="sxs-lookup"><span data-stu-id="1122f-129">Forms user survey</span></span>

<span data-ttu-id="1122f-130">채팅, 팀, 채널 및 앱 플랜부터 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-130">We recommend that you start with the Chat, teams, channels, and apps plan.</span></span> <span data-ttu-id="1122f-131">해당 워크로드 배포가 완료되면 관리자로 돌아가 **채널 추가**를 클릭하여 다음 워크로드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-131">When you're done deploying that workload, go back to Advisor and click **Add channel** to start the next workload.</span></span> 

## <a name="tenant-assessment"></a><span data-ttu-id="1122f-132">테넌트 평가</span><span class="sxs-lookup"><span data-stu-id="1122f-132">Tenant assessment</span></span>
<span data-ttu-id="1122f-133">각 플랜에는 Teams를 배포하기 전에 환경의 모든 결함을 확인하고 수정하는 데 사용할 수 있는 테넌트 준비 상태 평가가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-133">Each plan includes a tenant readiness assessment that you can use to identify and remediate any deficiencies in your environment before you roll out Teams.</span></span> <span data-ttu-id="1122f-134">각 평가에서 검사하는 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-134">Here's what each assessment checks:</span></span>

### <a name="chat-teams-channels-and-apps"></a><span data-ttu-id="1122f-135">채팅, 팀, 채널 및 앱</span><span class="sxs-lookup"><span data-stu-id="1122f-135">Chat, teams, channels, and apps</span></span>


|<span data-ttu-id="1122f-136">평가</span><span class="sxs-lookup"><span data-stu-id="1122f-136">Assessment</span></span>  |<span data-ttu-id="1122f-137">알리는 내용</span><span class="sxs-lookup"><span data-stu-id="1122f-137">What it tells you</span></span>  |
|---------|---------|
|<span data-ttu-id="1122f-138">Teams 라이선스</span><span class="sxs-lookup"><span data-stu-id="1122f-138">Teams licenses</span></span>     |<span data-ttu-id="1122f-139">사용 가능한 Teams 라이선스가 포함된 활성 구독이 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-139">Whether you have an active subscription with available Teams licenses</span></span> |
|<span data-ttu-id="1122f-140">Exchange 라이선스</span><span class="sxs-lookup"><span data-stu-id="1122f-140">Exchange licenses</span></span>     |<span data-ttu-id="1122f-141">사용 가능한 Exchange Online 라이선스가 포함된 활성 구독이 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-141">Whether you have an active subscription with available Exchange Online licenses.</span></span> <span data-ttu-id="1122f-142">기본 Teams 기능을 사용하는 데는 Exchange가 필요하지 않지만 Exchange와 통합하면 최상의 Teams 환경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-142">While Exchange isn't required for basic Teams functionality, integration with Exchange provides an optimal Teams experience.</span></span>         |
|<span data-ttu-id="1122f-143">SharePoint Online 라이선스</span><span class="sxs-lookup"><span data-stu-id="1122f-143">SharePoint Online licenses</span></span>     | <span data-ttu-id="1122f-144">사용 가능한 SharePoint Online 라이선스가 포함된 활성 구독이 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-144">Whether you have an active subscription with available SharePoint Online licenses.</span></span> <span data-ttu-id="1122f-145">파일 저장, 채널 공동 작업 및 채팅을 위해 사용자당 하나의 SharePoint Online 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-145">You need one SharePoint Online license per user for file storage, channel collaboration, and chat.</span></span> 
|<span data-ttu-id="1122f-146">게스트 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="1122f-146">Guest access enabled</span></span>     |<span data-ttu-id="1122f-147">게스트 액세스가 Teams에서 켜져 있는 경우</span><span class="sxs-lookup"><span data-stu-id="1122f-147">If guest access is turned on in Teams.</span></span> <span data-ttu-id="1122f-148">게스트 액세스에 대한 Azure Active Directory 설정은 검토되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-148">Azure Active Directory settings for guest access are not reviewed.</span></span>   |
|<span data-ttu-id="1122f-149">베니티 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="1122f-149">Vanity domain configured</span></span>     |<span data-ttu-id="1122f-150">테넌트에 대해 @onmicrosoft.com이 아닌 도메인이 구성되어 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-150">Whether there's a non-@onmicrosoft.com domain configured for your tenant</span></span>  |
|<span data-ttu-id="1122f-151">Office 365 그룹 이름 지정 표준 구성</span><span class="sxs-lookup"><span data-stu-id="1122f-151">Office 365 Group naming standard configured</span></span>     | <span data-ttu-id="1122f-152">Office 365 그룹에 이름 지정 표준이 구성되어 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-152">Whether naming standards have been configured for Office 365 Groups</span></span>        |
|<span data-ttu-id="1122f-153">Office 365 그룹 만료 구성</span><span class="sxs-lookup"><span data-stu-id="1122f-153">Office 365 Group expiration configured</span></span>     |  <span data-ttu-id="1122f-154">Office 365 그룹에 그룹 만료 정책이 정의되어 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-154">Whether a Group expiration policy has been defined for Office 365 Groups.</span></span> <span data-ttu-id="1122f-155">그렇지 않은 경우에는 값이 만료되지 않음으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-155">If not, the value is set to never.</span></span>        |
|<span data-ttu-id="1122f-156">외부 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="1122f-156">External access configured</span></span>     |<span data-ttu-id="1122f-157">외부 액세스가 켜져 있는 경우 Teams에서 외부 조직과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-157">If external access is turned on so you can communicate with external organizations in Teams.</span></span>          |

### <a name="meetings-and-conferencing"></a><span data-ttu-id="1122f-158">모임 및 회의</span><span class="sxs-lookup"><span data-stu-id="1122f-158">Meetings and conferencing</span></span>


|<span data-ttu-id="1122f-159">평가</span><span class="sxs-lookup"><span data-stu-id="1122f-159">Assessment</span></span>  |<span data-ttu-id="1122f-160">알리는 내용</span><span class="sxs-lookup"><span data-stu-id="1122f-160">What it tells you</span></span>  |
|---------|---------|
|<span data-ttu-id="1122f-161">Teams 라이선스</span><span class="sxs-lookup"><span data-stu-id="1122f-161">Teams licenses</span></span>     |<span data-ttu-id="1122f-162">사용 가능한 Teams 라이선스가 포함된 활성 구독이 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-162">Whether you have an active subscription with available Teams licenses</span></span> |
|<span data-ttu-id="1122f-163">Exchange 라이선스</span><span class="sxs-lookup"><span data-stu-id="1122f-163">Exchange licenses</span></span>     |<span data-ttu-id="1122f-164">사용 가능한 Exchange Online 라이선스가 포함된 활성 구독이 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-164">Whether you have an active subscription with available Exchange Online licenses.</span></span> <span data-ttu-id="1122f-165">기본 Teams 기능을 사용하는 데는 Exchange가 필요하지 않지만 Exchange와 통합하면 최상의 Teams 환경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-165">While Exchange isn't required for basic Teams functionality, integration with Exchange provides an optimal Teams experience.</span></span> |
|<span data-ttu-id="1122f-166">오디오 회의 라이선스</span><span class="sxs-lookup"><span data-stu-id="1122f-166">Audio conferencing licenses</span></span>    |<span data-ttu-id="1122f-167">오디오 회의 라이선스가 포함된 활성 구독이 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-167">Whether you have an active subscription with Audio conferencing licenses</span></span> |
|<span data-ttu-id="1122f-168">Stream 라이선스</span><span class="sxs-lookup"><span data-stu-id="1122f-168">Stream licenses</span></span>     |<span data-ttu-id="1122f-169">모임 녹음/녹화를 원하는 경우에 사용할 수 있는 Stream 라이선스가 포함된 활성 구독이 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-169">Whether you have an active subscription with Stream licenses, which can used should Meeting Recording be desired.</span></span> |
|<span data-ttu-id="1122f-170">게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="1122f-170">Guest access</span></span>     |<span data-ttu-id="1122f-171">게스트 액세스가 Teams에서 켜져 있는 경우</span><span class="sxs-lookup"><span data-stu-id="1122f-171">If guest access is turned on in Teams.</span></span> <span data-ttu-id="1122f-172">게스트 액세스에 대한 Azure Active Directory 설정은 검토되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-172">Azure Active Directory settings for guest access are not reviewed.</span></span>|
|<span data-ttu-id="1122f-173">베니티 도메인</span><span class="sxs-lookup"><span data-stu-id="1122f-173">Vanity domain</span></span>     |<span data-ttu-id="1122f-174">테넌트에 대해 @onmicrosoft.com이 아닌 도메인이 구성되어 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="1122f-174">Whether there's a non-@onmicrosoft.com domain configured for your tenant.</span></span>  |
|<span data-ttu-id="1122f-175">외부 액세스</span><span class="sxs-lookup"><span data-stu-id="1122f-175">External access</span></span>     |<span data-ttu-id="1122f-176">외부 액세스가 켜져 있는 경우 Teams에서 외부 조직과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-176">If external access is turned on so you can communicate with external organizations in Teams.</span></span> |


### <a name="advisor-bot"></a><span data-ttu-id="1122f-177">관리자 봇</span><span class="sxs-lookup"><span data-stu-id="1122f-177">Advisor bot</span></span>
<span data-ttu-id="1122f-178">관리자가 배포 팀을 만들면 관리자 봇에서 다음 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-178">Once Advisor creates your Deployment team, the Advisor bot delivers the following message.</span></span>

><span data-ttu-id="1122f-179">**Microsoft Teams의 배포 팀에 오신 것을 환영합니다!**</span><span class="sxs-lookup"><span data-stu-id="1122f-179">**Welcome to your Deployment team for Microsoft Teams!**</span></span>
>  
><span data-ttu-id="1122f-180">이 팀의 목적은 필요한 모든 리소스를 제공하고 프로젝트 팀을 위한 공동 작업 공간을 제공하여 조직의 Teams 롤아웃 과정을 안내하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-180">The purpose of this team is to walk you through your organization's Teams rollout by giving you all the resources you need and providing a collaboration space for the project team.</span></span> <span data-ttu-id="1122f-181">Advisor for Teams를 사용하여 만든 각 채널에는 단계별 Planner 플랜 및 롤아웃 전체에서 사용할 수 있는 Forms 사용자 설문 조사 등 기타 리소스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-181">Each channel created using Advisor for Teams includes a step-by-step Planner plan and other resources such as a Forms users survey that can be used throughout your rollout.</span></span> <span data-ttu-id="1122f-182">언제든지 Teams 관리 센터를 사용하여 테넌트 준비 상태 평가로 돌아가 검토하거나 추가 워크로드 플랜을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-182">At any point, you can you go back and review the tenant readiness assessment or add additional workload plans using the Teams admin center.</span></span> 
> 
><span data-ttu-id="1122f-183">**조치 사항**</span><span class="sxs-lookup"><span data-stu-id="1122f-183">**Call to action**</span></span> 
>- <span data-ttu-id="1122f-184">Teams 또는 Planner를 처음 사용할 경우 [Teams 안내](https://teamsdemo.office.com/)를 확인하고 [Planner 빠른 시작 비디오](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)를 시청하십시오.</span><span class="sxs-lookup"><span data-stu-id="1122f-184">If you're new to Teams or Planner, check out our [Teams walkthrough](https://teamsdemo.office.com/) and watch the [Planner quick-start videos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).</span></span> 
>- <span data-ttu-id="1122f-185">Teams의 배포 팀에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="1122f-185">Head over to your Deployment team in Teams.</span></span> <span data-ttu-id="1122f-186">워크로드 채널(예: 채팅, 팀, 채널 및 앱)을 선택하고 **Planner** 탭을 선택하여 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-186">Select your workload channel (for example, Chat, teams, channels, and apps), and select the **Planner** tab to get started.</span></span>
> 
><span data-ttu-id="1122f-187">Advisor for Teams에 대해 자세히 알아보려면 [Advisor for Teams를 사용하여 Microsoft Teams 배포](use-advisor-teams-roll-out.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1122f-187">To learn more about Advisor for Teams, read [Use Advisor for Teams to roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span>
>
> [!IMPORTANT]
> <span data-ttu-id="1122f-188">Advisor for Teams 봇은 배포 팀에 환영 메시지를 보내는 데만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-188">The Advisor for Teams Bot is only used to send a welcome message to your Deployment team.</span></span> <span data-ttu-id="1122f-189">추가 데이터가 수집되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-189">No additional data is collected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1122f-190">Advisor for Teams 봇은 기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-190">The Advisor for Teams bot is enabled by default.</span></span> <span data-ttu-id="1122f-191">Advisor for Teams를 사용하거나 여기에서 계획할 경우 사용하지 않도록 설정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1122f-191">Do not disable it if you use or plan on using Advisor for Teams.</span></span>


## <a name="frequently-asked-questions"></a><span data-ttu-id="1122f-192">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="1122f-192">Frequently asked questions</span></span>
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a><span data-ttu-id="1122f-193">Advisor for Teams에 대한 라이선스 요구 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="1122f-193">What are the licensing requirements for Advisor for Teams?</span></span>
<span data-ttu-id="1122f-194">Teams에 대한 라이선싱 외애에 다른 추가 라이선스 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-194">There are no additional licensing requirements other than being licensed for Teams.</span></span>

### <a name="can-i-delete-the-deployment-team"></a><span data-ttu-id="1122f-195">배포 팀을 삭제할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1122f-195">Can I delete the Deployment team?</span></span>
<span data-ttu-id="1122f-196">Advisor for Teams에서 배포 팀을 만든 이후 삭제 기능을 포함해 다른 모든 팀과 같이 팀을 관리하십시오.</span><span class="sxs-lookup"><span data-stu-id="1122f-196">After Advisor for Teams has created your Deployment team, manage the team like any other team - including the ability to delete it.</span></span> <span data-ttu-id="1122f-197">Teams 관리 센터를 사용하여 팀을 삭제하지 않는 경우 팀이 존재하는 것으로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-197">Be aware that, if you don't delete the team by using the Teams admin center, it will be reported that the team exists.</span></span>

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a><span data-ttu-id="1122f-198">배포 팀에서 채널을 추가하거나 제거할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1122f-198">Can I add or remove channels in the Deployment team?</span></span>
<span data-ttu-id="1122f-199">예. 배포 팀이 만들어졌으면 다른 모든 팀과 동일한 방식으로 채널을 관리하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-199">Yes, once the Deployment team has been created, you'll manage the channels the same way as any other team.</span></span>

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a><span data-ttu-id="1122f-200">배포 팀에서 프로젝트 팀 구성원을 추가하거나 제거할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1122f-200">Can I add or remove project team members in the Deployment team?</span></span>
<span data-ttu-id="1122f-201">예. 배포 팀이 만들어지고 나면 다른 모든 팀과 동일한 방식으로 관리하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-201">Yes, once the Deployment team has been created, you'll manage it the same way as any other team.</span></span>

### <a name="can-i-modify-the-planner-plans"></a><span data-ttu-id="1122f-202">Planner 플랜을 수정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1122f-202">Can I modify the Planner plans?</span></span>
<span data-ttu-id="1122f-203">예, Advisor for Teams에서 배포 팀을 만든 후에는 Teams 배포를 최상으로 지원하도록 Planner 플랜을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-203">Yes, after Advisor for Teams has created your Deployment team, you should update the Planner plan so it best supports your Teams rollout.</span></span> <span data-ttu-id="1122f-204">버킷, 작업, 작업 세부 정보 등 다른 Planner 플랜처럼 모든 요소를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-204">You can modify anything - buckets, tasks, task details - just like any other Planner plan.</span></span>


### <a name="can-i-modify-the-forms-survey"></a><span data-ttu-id="1122f-205">Forms 설문 조사를 수정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1122f-205">Can I modify the Forms survey?</span></span>
<span data-ttu-id="1122f-206">예, Advisor for Teams에서 배포 팀을 만든 후에는 필요에 따라 Forms 설문 조사를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-206">Yes, after Advisor for Teams has created your Deployment team, you can modify the Forms survey as needed.</span></span>

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a><span data-ttu-id="1122f-207">내 조직에 대해 Advisor for Teams에서 어떤 정보를 수집하나요?</span><span class="sxs-lookup"><span data-stu-id="1122f-207">What information is Advisor for Teams collecting about my organization?</span></span>
<span data-ttu-id="1122f-208">Advisor for Teams에서는 EUII(최종 사용자 식별 정보) 이외의 정보를 수집하는 데 사용자의 동의를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-208">Advisor for Teams requests your agreement to collecting non-EUII (end user identifying information).</span></span> <span data-ttu-id="1122f-209">수집된 정보는 Advisor for Teams에서 어떻게 효과적으로 성공적인 결과를 유도하고 있는지, 그리고 향상해야 할 부분은 무엇인지에 대해 Microsoft에 피드백을 제공하는 원격 분석 양식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-209">The information that is collected is in the form of telemetry that provides feedback to Microsoft on how well Advisor for Teams is driving successful outcomes and where it may need to be improved.</span></span> <span data-ttu-id="1122f-210">이와 같은 데이터는 Microsoft가 배포를 지원하기 위한 노력의 일환으로 사용자의 조직에 적극적으로 관여할 기회를 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-210">This same data is used to identify opportunities for Microsoft to proactively engage with your organization in an effort to assist with your deployment.</span></span>

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a><span data-ttu-id="1122f-211">Advisor for Teams를 FastTrack과 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1122f-211">Can I use Advisor for Teams with FastTrack?</span></span>
<span data-ttu-id="1122f-212">예, FastTrack에서는 Teams을 배포하려는 모든 고객을 위해 Advisor for Teams를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-212">Yes, FastTrack leverages Advisor for Teams for all customers looking to deploy Teams.</span></span> <span data-ttu-id="1122f-213">Advisor for Teams(필요할 경우)를 사용하여 배포 팀 초기 설정을 지원하고 Teams 롤아웃 중 특정 주제에 대해 필요할 경우 지원을 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-213">They can assist with the initial setup of your Deployment team using Advisor for Teams (if required) and also provide as-needed support on specific topics during your Teams rollout.</span></span>

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a><span data-ttu-id="1122f-214">Advisor for Teams를 파트너와 함께 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1122f-214">Can I use Advisor for Teams with a partner?</span></span>
<span data-ttu-id="1122f-215">예, Teams 배포를 위해 배포 파트너를 사용하는 중에도 Advisor for Teams를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-215">Yes, you can use Advisor for Teams while also using a deployment partner for your Teams deployment.</span></span> <span data-ttu-id="1122f-216">파트너가 CSP이고 사용자의 테넌트를 대신 관리할 경우 Advisor for Teams를 사용하여 배포 팀을 만들고 전체 프로젝트 이행을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-216">If your partner is a CSP and manages your tenant on your behalf, they can use Advisor for Teams to create your Deployment team and assist you with executing the overall project.</span></span> <span data-ttu-id="1122f-217">또한 배포 팀에서 해당 사용자를 게스트로 추가하여 모든 파트너와 함께 작업하여 전체 프로젝트 팀원으로서 참여하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122f-217">Additionally, you can work with any partner by adding those individuals as guests in your Deployment team, to allow them to participate as a member of the overall project team.</span></span>

### <a name="how-do-i-use-planner"></a><span data-ttu-id="1122f-218">Planner를 사용하려면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="1122f-218">How do I use Planner?</span></span>
<span data-ttu-id="1122f-219">[Microsoft Planner 도움말](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) 및 [Planner 빠른 시작 비디오](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="1122f-219">Check out [Microsoft Planner help](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) and the [Planner quick-start videos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).</span></span> 

### <a name="how-do-i-use-forms"></a><span data-ttu-id="1122f-220">Forms를 사용하려면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="1122f-220">How do I use Forms?</span></span>
<span data-ttu-id="1122f-221">[Forms 도움말 센터](https://support.office.com/forms)로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="1122f-221">Go to the [Forms help center](https://support.office.com/forms).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1122f-222">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1122f-222">Related topics</span></span>

[<span data-ttu-id="1122f-223">Teams를 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="1122f-223">How to roll out Teams</span></span>](How-to-roll-out-teams.md)
