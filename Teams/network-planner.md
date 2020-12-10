---
title: Microsoft Teams용 Network Planner 사용
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 관리자는 Network Planner를 사용하여 Microsoft Teams에 대한 네트워크 요구 사항을 확인하는 방법을 배울 수 있습니다.
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
ms.openlocfilehash: 9351c37c96e4bc11f0e5f93041f7e024158d7564
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611802"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="88709-103">Microsoft Teams용 Network Planner 사용</span><span class="sxs-lookup"><span data-stu-id="88709-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="88709-104">Network Planner는 Teams 관리 센터에서 사용할 수 있는 새로운 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="88709-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="88709-105">Network Planner 계획으로 가면 찾을  >  **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="88709-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="88709-106">네트워크 플래너는 몇 단계만 수행하면 조직 전체에서 Microsoft Teams 사용자를 연결하기 위한 네트워크 요구 사항을 결정하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="88709-107">네트워크 세부 정보 및 Teams 사용량을 제공하면 Network Planner는 조직의 실제 위치에 Teams 및 클라우드 음성을 배포하기 위한 네트워크 요구 사항을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Network Planner 스크린샷](media/network-planner.png)

<span data-ttu-id="88709-109">Network Planner를 사용하면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-109">Network planner allows you to:</span></span>

- <span data-ttu-id="88709-110">사이트 및 Microsoft 추천 사용자(사무실 작업자, 원격 작업자 및 Teams 방 시스템)를 사용하여 조직의 표현을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="88709-111">권장되는 사용자들은 Teams 최고의 사용 시나리오 및 일반적인 사용 패턴의 데이터를 기반으로 개발되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="88709-112">그러나 권장되는 세 개의 사용자 지정 사용자 외에도 최대 3개의 사용자 지정 사용자 지정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="88709-113">보고서를 생성하고 Teams 사용에 대한 대역폭 요구 사항을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="88709-114">Network Planner를 사용하려면 전역 관리자, Teams 서비스 관리자 또는 Teams 통신 관리자해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-114">To use Network planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="88709-115">사용자 지정 사용자 지정 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="88709-115">Create a custom persona</span></span>

<span data-ttu-id="88709-116">다음 단계에 따라 사용자 지정 Persona를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="88709-117">Microsoft Teams 관리 센터의 Network Planner로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="88709-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="88709-118">Personas **탭에서** **+ 사용자 지정 사용자 지정 사용자 지정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="88709-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="88709-119">새 사용자 **지정 사용자 지정 창에서** 새 사용자에 대한 이름 및 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="88709-120">이 사용자가 조직 내에서 사용할 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="88709-121">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="88709-122">계획 빌드</span><span class="sxs-lookup"><span data-stu-id="88709-122">Build your plan</span></span>

<span data-ttu-id="88709-123">다음 단계에 따라 네트워크 계획 구축을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="88709-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="88709-124">Microsoft Teams 관리 센터의 Network Planner로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="88709-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="88709-125">네트워크 계획 **탭에서** 네트워크 계획 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="88709-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="88709-126">네트워크 계획에 대한 이름 및 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="88709-127">네트워크 계획이 사용 가능한 계획 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="88709-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="88709-128">계획 이름을 클릭하여 새 계획을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="88709-129">사이트를 추가하여 조직의 네트워크 설정에 대한 표현을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="88709-130">조직의 네트워크에 따라 사이트를 사용하여 건물, 사무실 위치 또는 다른 것을 나타내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="88709-131">사이트는 인터넷 및/또는 PSTN 연결 공유를 허용하기 위해 WAN에 의해 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="88709-132">최상의 결과를 얻하려면 인터넷 또는 PSTN에 원격으로 연결하는 사이트를 만들기 전에 로컬 연결을 사용하여 사이트를 만드면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88709-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="88709-133">사이트를 만들 경우:</span><span class="sxs-lookup"><span data-stu-id="88709-133">To create a site:</span></span>

    1. <span data-ttu-id="88709-134">사이트에 대한 이름 및 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="88709-135">네트워크 **설정 아래에서** 해당 사이트의 네트워크 사용자 수를 추가합니다(필수).</span><span class="sxs-lookup"><span data-stu-id="88709-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="88709-136">WAN 사용, WAN 용량, 인터넷(로컬 또는 원격) 및 PSTN(없음, 로컬 또는 원격) 등 네트워크 세부 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="88709-137">보고서를 생성할 때 특정 대역폭 권장 사항을 표시하려면 WAN 및 인터넷 용량 번호를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="88709-138">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="88709-139">보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="88709-139">Create a report</span></span>

<span data-ttu-id="88709-140">모든 사이트를 추가한 후 다음과 같이 보고서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="88709-141">보고서 **탭에서** 보고서 **시작을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="88709-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="88709-142">만드는 각 사이트에 대해 사용 가능한 사용자 수를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="88709-143">Microsoft 권장 사용자 수를 사용하는 경우 번호가 자동으로 배포됩니다(사무실 작업자 80%, 원격 작업자 20%).</span><span class="sxs-lookup"><span data-stu-id="88709-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="88709-144">배포를 완료한 후 보고서 **생성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="88709-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="88709-145">생성된 보고서는 출력을 명확하게 이해할 수 있도록 여러 다른 보기에서 대역폭 요구 사항을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="88709-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="88709-146">개별 계산이 있는 테이블에는 허용되는 각 활동에 대한 대역폭 요구 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="88709-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="88709-147">추가 보기에는 권장 사항과 함께 전체 대역폭 요구 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="88709-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="88709-148">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="88709-148">Click **Save**.</span></span> <span data-ttu-id="88709-149">보고서는 나중에 볼 수 있도록 보고서 목록에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88709-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="88709-150">예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="88709-150">Example scenario</span></span>

<span data-ttu-id="88709-151">Network Planner를 사용하여 네트워크 계획을 설정하고 이러한 단계를 사용하여 보고서를 생성하는 방법에 대한 예제는 PowerPoint 데크에서 [Network Planner를 How-To(영어만](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) 해당)</span><span class="sxs-lookup"><span data-stu-id="88709-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
