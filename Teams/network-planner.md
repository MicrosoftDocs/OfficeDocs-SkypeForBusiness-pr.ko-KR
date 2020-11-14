---
title: Microsoft 팀을 위한 네트워크 planner 사용
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 관리자는 네트워크 Planner를 사용 하 여 Microsoft 팀에 대 한 네트워크 요구 사항을 결정 하는 방법을 배울 수 있습니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14bdc08656cdce18fc25b38ca8d226ac0e70cf27
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030624"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="8fb96-103">Microsoft 팀을 위한 네트워크 planner 사용</span><span class="sxs-lookup"><span data-stu-id="8fb96-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="8fb96-104">네트워크 Planner는 팀 관리 센터에서 사용할 수 있는 새로운 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="8fb96-105">**Planner**  >  **네트워크 planner** 로 이동한 후이를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-105">It can be found by going to **Planner** > **Network planner**.</span></span> <span data-ttu-id="8fb96-106">네트워크 Planner를 사용 하 여 조직 내에서 Microsoft 팀 사용자를 연결 하는 데 필요한 네트워크 요구 사항을 확인 하 고 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="8fb96-107">네트워크 세부 정보 및 팀 사용량을 제공 하는 경우 네트워크 계획자는 조직의 실제 위치에서 팀 및 클라우드 음성을 배포 하기 위한 네트워크 요구 사항을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![네트워크 planner 스크린샷](media/network-planner.png)

<span data-ttu-id="8fb96-109">네트워크 planner를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-109">Network planner allows you to:</span></span>

- <span data-ttu-id="8fb96-110">사이트와 Microsoft 권장 가상 사용자 (office worker, 원격 작업자, 팀 대화방 시스템)를 사용 하 여 조직의 표현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="8fb96-111">권장 가상 사용자는 팀의 데이터에 가장 적합 한 시나리오 및 일반적인 사용 패턴을 기준으로 개발 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="8fb96-112">그러나 권장 되는 세 개의 가상 사용자 외에도 최대 3 명의 사용자 지정 가상을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="8fb96-113">팀 사용에 대 한 보고서를 생성 하 고 대역폭 요구 사항을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="8fb96-114">네트워크 planner를 사용 하려면 전역 관리자, 팀 서비스 관리자 또는 팀 통신 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-114">To use Network planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="8fb96-115">사용자 지정 가상 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="8fb96-115">Create a custom persona</span></span>

<span data-ttu-id="8fb96-116">다음 단계에 따라 사용자 지정 가상 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="8fb96-117">Microsoft 팀 관리 센터의 네트워크 planner로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="8fb96-118">**가상 사용자** 탭에서 **+ 사용자 가상 사용자** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="8fb96-119">**새 사용자 지정 가상** 사용자 창에서 새 가상 사용자에 대 한 이름과 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="8fb96-120">이 가상 사용자가 조직 내에서 사용할 사용 권한을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="8fb96-121">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="8fb96-122">계획 수립</span><span class="sxs-lookup"><span data-stu-id="8fb96-122">Build your plan</span></span>

<span data-ttu-id="8fb96-123">네트워크 계획 만들기를 시작 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="8fb96-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="8fb96-124">Microsoft 팀 관리 센터의 네트워크 planner로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="8fb96-125">**네트워크 계획** 탭에서 **네트워크 계획 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="8fb96-126">네트워크 계획의 이름과 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="8fb96-127">사용할 수 있는 계획 목록에 네트워크 계획이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="8fb96-128">계획 이름을 클릭 하 여 새 계획을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="8fb96-129">사이트를 추가 하 여 조직의 네트워크 설정에 대 한 표현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="8fb96-130">조직의 네트워크에 따라 사이트를 사용 하 여 건물, 사무실 위치 등을 나타내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="8fb96-131">사이트는 인터넷 및/또는 PSTN 연결 공유를 허용 하기 위해 WAN에 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="8fb96-132">최상의 결과를 위해서는 인터넷 이나 PSTN에 원격으로 연결 하는 사이트를 만들기 전에 로컬 연결을 사용 하 여 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="8fb96-133">사이트를 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-133">To create a site:</span></span>

    1. <span data-ttu-id="8fb96-134">사이트의 이름 및 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="8fb96-135">**네트워크 설정** 에서 해당 사이트에 있는 네트워크 사용자의 수를 추가 합니다 (필수).</span><span class="sxs-lookup"><span data-stu-id="8fb96-135">Under **Network settings** , add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="8fb96-136">네트워크 세부 정보 추가: WAN 사용 가능, WAN 용량, 인터넷 송신 ( **로컬** 또는 **원격** ), PSTN egress (없음, 로컬 또는 원격)</span><span class="sxs-lookup"><span data-stu-id="8fb96-136">Add network details: WAN-enabled, WAN capacity, internet egress ( **Local** or **Remote** ), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="8fb96-137">보고서를 생성할 때 특정 대역폭 권장 사항을 보려면 WAN 및 인터넷 용량 번호를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="8fb96-138">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="8fb96-139">보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="8fb96-139">Create a report</span></span>

<span data-ttu-id="8fb96-140">모든 사이트를 추가한 후 다음과 같이 보고서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="8fb96-141">**보고서 탭에서** **보고서 시작** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="8fb96-142">만드는 각 사이트에 대해 사용 가능한 가상 사용자 수를 분산 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="8fb96-143">Microsoft 권장 가상 사용자를 사용 하는 경우 번호가 자동으로 배포 됩니다 (80% office worker 및 20% 원격 작업자).</span><span class="sxs-lookup"><span data-stu-id="8fb96-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="8fb96-144">배포를 완료 한 후 **보고서 생성** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="8fb96-145">생성 된 보고서에는 출력을 명확 하 게 이해할 수 있도록 여러 가지 보기의 대역폭 요구 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="8fb96-146">개별 계산이 있는 테이블에는 허용 된 각 활동에 대 한 대역폭 요구 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="8fb96-147">추가 보기에는 권장 사항이 포함 된 전반적인 대역폭 요구 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="8fb96-148">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-148">Click **Save**.</span></span> <span data-ttu-id="8fb96-149">나중에 보기 위해 보고서를 보고서 목록에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb96-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="8fb96-150">예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="8fb96-150">Example scenario</span></span>

<span data-ttu-id="8fb96-151">네트워크 planner를 사용 하 여 네트워크 계획을 설정 하 고이 단계를 사용 하 여 보고서를 생성 하는 방법에 대 한 예를 보려면 [네트워크 planner How-To PowerPoint 데크](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (영어만 해당)로 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fb96-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
