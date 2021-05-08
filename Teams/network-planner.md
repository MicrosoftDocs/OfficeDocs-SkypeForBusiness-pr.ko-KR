---
title: 네트워크 플래너를 사용하여 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 관리자는 네트워크 플래너를 사용하여 네트워크 요구 사항을 확인하는 방법을 Microsoft Teams.
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
ms.openlocfilehash: 1f05be30158cf934459f26965d7cef2dafbc708f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240481"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="1ab4f-103">네트워크 플래너를 사용하여 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ab4f-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="1ab4f-104">Network Planner는 관리 센터에서 사용할 수 있는 Teams 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="1ab4f-105">계획 네트워크 플래너로   >  **가면 찾을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1ab4f-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="1ab4f-106">네트워크 플래너는 몇 단계만 수행하면 조직 전체에서 사용자 연결에 Microsoft Teams 네트워크 요구 사항을 결정하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="1ab4f-107">네트워크 세부 정보 및 Teams 사용을 제공하는 경우 네트워크 플래너는 조직에서 실제 위치에 Teams와 Cloud Voice를 배포하는데 필요한 네트워크 요구 사항을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![네트워크 플래너 스크린샷](media/network-planner.png)

<span data-ttu-id="1ab4f-109">네트워크 플래너를 사용하면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-109">Network planner allows you to:</span></span>

- <span data-ttu-id="1ab4f-110">사이트 및 Microsoft 권장 사용자(사무실 근로자, 원격 근로자 및 Teams 시스템)를 사용하여 조직의 표현을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ab4f-111">권장되는 인물은 사용 시나리오 및 일반적인 사용 Teams 데이터를 기반으로 개발되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="1ab4f-112">그러나 권장되는 세 개의 사용자 지정 사용자 외에 최대 3개의 사용자 지정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="1ab4f-113">보고서 생성 및 사용량에 Teams 요구 사항을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="1ab4f-114">네트워크 플래너를 사용하려면 전역 관리자, Teams 관리자 또는 Teams 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-114">To use Network planner, you must be a Global Administrator, Teams Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="1ab4f-115">사용자 지정 persona 만들기</span><span class="sxs-lookup"><span data-stu-id="1ab4f-115">Create a custom persona</span></span>

<span data-ttu-id="1ab4f-116">다음 단계를 수행하여 사용자 지정 persona를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="1ab4f-117">관리 센터의 네트워크 Microsoft Teams 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="1ab4f-118">**Personas 탭에서** **+ 사용자 지정 persona 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ab4f-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="1ab4f-119">새 사용자 **지정 persona 창에서 새 persona에** 대한 이름 및 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="1ab4f-120">이 persona가 조직 내에서 사용할 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="1ab4f-121">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="1ab4f-122">계획 빌드</span><span class="sxs-lookup"><span data-stu-id="1ab4f-122">Build your plan</span></span>

<span data-ttu-id="1ab4f-123">다음 단계를 수행하여 네트워크 계획 구축을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="1ab4f-124">관리 센터의 네트워크 Microsoft Teams 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="1ab4f-125">네트워크 계획 **탭에서** 네트워크 계획 **추가 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ab4f-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="1ab4f-126">네트워크 계획에 대한 이름 및 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="1ab4f-127">네트워크 계획은 사용 가능한 계획 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="1ab4f-128">계획 이름을 클릭하여 새 계획을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="1ab4f-129">사이트를 추가하여 조직의 네트워크 설정의 표현을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="1ab4f-130">조직의 네트워크에 따라 사이트를 사용하여 건물, 사무실 위치 또는 다른 것을 나타내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="1ab4f-131">사이트는 인터넷 및/또는 PSTN 연결 공유를 허용하도록 WAN에 의해 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="1ab4f-132">최상의 결과를 얻기 위해 인터넷 또는 PSTN에 원격으로 연결하는 사이트를 만들기 전에 로컬 연결이 있는 사이트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="1ab4f-133">사이트를 만들 경우:</span><span class="sxs-lookup"><span data-stu-id="1ab4f-133">To create a site:</span></span>

    1. <span data-ttu-id="1ab4f-134">사이트에 대한 이름 및 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="1ab4f-135">네트워크 **설정에서** 해당 사이트의 네트워크 사용자 수를 추가합니다(필수).</span><span class="sxs-lookup"><span data-stu-id="1ab4f-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="1ab4f-136">네트워크 세부 정보 추가: WAN 사용, WAN 용량, 인터넷egress(로컬 또는 **원격)** 및 PSTN(없음, 로컬 또는 원격)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="1ab4f-137">보고서를 생성할 때 특정 대역폭 권장 사항을 표시하려면 WAN 및 인터넷 용량 번호를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="1ab4f-138">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="1ab4f-139">보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="1ab4f-139">Create a report</span></span>

<span data-ttu-id="1ab4f-140">모든 사이트를 추가한 후 다음과 같이 보고서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="1ab4f-141">보고서 **탭에서** 보고서 **시작 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ab4f-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="1ab4f-142">만드는 각 사이트에 대해 사용 가능한 사용자 수를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="1ab4f-143">Microsoft 권장 인물인 경우 수가 자동으로 분산됩니다(사무실 작업자 80%, 원격 작업자 20%).</span><span class="sxs-lookup"><span data-stu-id="1ab4f-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="1ab4f-144">배포를 완료한 후 보고서 **생성 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ab4f-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="1ab4f-145">생성된 보고서는 출력을 명확하게 이해할 수 있도록 여러 다른 보기에서 대역폭 요구 사항을 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="1ab4f-146">개별 계산이 있는 테이블은 허용되는 각 활동에 대한 대역폭 요구 사항을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="1ab4f-147">추가 보기는 권장 사항과 함께 전체 대역폭 요구 사항을 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="1ab4f-148">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-148">Click **Save**.</span></span> <span data-ttu-id="1ab4f-149">보고서는 나중에 볼 수 있도록 보고서 목록에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="1ab4f-150">시나리오 예</span><span class="sxs-lookup"><span data-stu-id="1ab4f-150">Example scenario</span></span>

<span data-ttu-id="1ab4f-151">네트워크 플래너를 사용하여 네트워크 계획을 설정하고 이러한 단계를 사용하여 보고서를 생성하는 방법에 대한 예제는 네트워크 플래너 How-To PowerPoint [데크(영어만)를](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab4f-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
