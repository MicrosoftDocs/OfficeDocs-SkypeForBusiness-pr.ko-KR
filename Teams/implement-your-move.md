---
title: Microsoft Teams로 이동 구현
author: Benny-54
ms.author: v-bshilpa
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 이 문서에서는 Microsoft Teams를 배포하고 구현하는 방법을 설명합니다.
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection: ''
ms.custom: ''
ms.openlocfilehash: 5647969ccbb19599efea062d94d88b79c2d8a6f4
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819485"
---
# <a name="implement-your-move-to-microsoft-teams"></a><span data-ttu-id="bd64f-103">Microsoft Teams로 이동 구현</span><span class="sxs-lookup"><span data-stu-id="bd64f-103">Implement your move to Microsoft Teams</span></span>

<span data-ttu-id="bd64f-104">이 문서에서는 다음 시나리오에 대한 Microsoft Teams의 배포 및 구현에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-104">This article provides your guidance on deployment and implementation of Microsoft Teams for the following scenarios:</span></span>

1. <span data-ttu-id="bd64f-105">Microsoft **Teams를 이미 사용하는 조직의 경우**</span><span class="sxs-lookup"><span data-stu-id="bd64f-105">For organizations **already using Microsoft Teams**</span></span>
2. <span data-ttu-id="bd64f-106">아직 **Microsoft Teams를 사용하지 않는 조직의 경우**</span><span class="sxs-lookup"><span data-stu-id="bd64f-106">For organizations **not yet using Microsoft Teams**</span></span>

## <a name="deploying-and-implementing-microsoft-teams-for-organizations-already-using-microsoft-teams"></a><span data-ttu-id="bd64f-107">Microsoft Teams를 사용하여 이미 조직에 대해 Microsoft Teams 배포 및 구현</span><span class="sxs-lookup"><span data-stu-id="bd64f-107">Deploying and implementing Microsoft Teams for organizations already using Microsoft Teams</span></span>
 
<span data-ttu-id="bd64f-108">계속하기 전에 다음 작업을 완료한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-108">Before proceeding, confirm that you've completed the following activities:</span></span> 

- <span data-ttu-id="bd64f-109">조직에 대한 구상된 팀워크</span><span class="sxs-lookup"><span data-stu-id="bd64f-109">Envisioned teamwork for your organization</span></span>  
- <span data-ttu-id="bd64f-110">식별된 챔피언 및 중요한 이해 관계자</span><span class="sxs-lookup"><span data-stu-id="bd64f-110">Identified champions and critical stakeholders</span></span> 
- <span data-ttu-id="bd64f-111">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="bd64f-111">Defined your project scope</span></span>  
- <span data-ttu-id="bd64f-112">파일럿된 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd64f-112">Piloted Microsoft Teams</span></span> 
- <span data-ttu-id="bd64f-113">조직 준비</span><span class="sxs-lookup"><span data-stu-id="bd64f-113">Prepared your organization</span></span> 

<span data-ttu-id="bd64f-114">이미 **Microsoft Teams가** 롤아웃되어 있으며 Kaizala에서 Microsoft Teams로 라이선스가 부여된 사용자를 이동하려는 경우 이 문서의 지침을 따르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-114">Follow the guidance in this article, if you **already have Microsoft Teams rolled out** and want to move your licensed users from Kaizala to Microsoft Teams.</span></span> 
   
<span data-ttu-id="bd64f-115">전환을 위해 다음 프레임워크를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-115">We recommend the following framework for transition:</span></span>  
   
<span data-ttu-id="bd64f-116">**전환 계획**</span><span class="sxs-lookup"><span data-stu-id="bd64f-116">**Plan for your transition**</span></span> 
   
1. <span data-ttu-id="bd64f-117">먼저 채팅 그룹을 Microsoft Teams로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-117">First, move your chat groups to Microsoft Teams.</span></span>
1. <span data-ttu-id="bd64f-118">다음으로 Teams의 앱을 사용하여 Kaizala 작업 카드를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-118">Next, use apps in Teams to replace Kaizala action cards.</span></span>
1. <span data-ttu-id="bd64f-119">프런트라인 작업자가 갖추어지 않도록 Teams Frontline Worker 기능으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-119">To ensure that frontline workers are equipped, upgrade to Teams Frontline Worker functionality.</span></span> <span data-ttu-id="bd64f-120">Teams Frontline Worker에 대한 빠른 시작 가이드는 [Frontline Worker 빠른 시작 가이드 를 참조하세요.](https://docs.microsoft.com/microsoftteams/flw-quickstart)</span><span class="sxs-lookup"><span data-stu-id="bd64f-120">For a quick start guide on Teams Frontline Worker, see [Frontline Worker Quick Start Guide](https://docs.microsoft.com/microsoftteams/flw-quickstart).</span></span>
1. <span data-ttu-id="bd64f-121">Teams에서 게스트로 초대할 공급업체 및 파트너를 온보드하는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-121">Consider Onboarding suppliers and partners to invite as guests in Teams.</span></span>  
  
<span data-ttu-id="bd64f-122">**변경 관리**</span><span class="sxs-lookup"><span data-stu-id="bd64f-122">**Manage change**</span></span>  
   
1. <span data-ttu-id="bd64f-123">전환 프로젝트에 대한 인식을 높이기 위해 통신 캠페인을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-123">Create a communication campaign to raise awareness on the transition project.</span></span> 
1. <span data-ttu-id="bd64f-124">변경 내용을 조직에 알리고 챔피언을 식별하여 Microsoft Teams 채택을 주도합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-124">Notify your organization of the change and identify champions to drive adoption of Microsoft Teams.</span></span> 
1. <span data-ttu-id="bd64f-125">무료 교육을 통해 사용자에게 Microsoft Teams에 대해 자세히 알아보는 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-125">Empower your users to learn more about Microsoft Teams through free training.</span></span> 
   
<span data-ttu-id="bd64f-126">자세한 내용은 [Microsoft Teams 비디오 교육 을 참조합니다.](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?ui=en-us&rs=en-us&ad=us)</span><span class="sxs-lookup"><span data-stu-id="bd64f-126">To learn more, see [Microsoft Teams video training](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?ui=en-us&rs=en-us&ad=us).</span></span>   
 
## <a name="deploying-and-implementing-microsoft-teams-for-organizations-not-yet-using-microsoft-teams"></a><span data-ttu-id="bd64f-127">아직 Microsoft Teams를 사용하지 않는 조직에 대해 Microsoft Teams 배포 및 구현</span><span class="sxs-lookup"><span data-stu-id="bd64f-127">Deploying and implementing Microsoft Teams for organizations not yet using Microsoft Teams</span></span>
 
<span data-ttu-id="bd64f-128">Kaizala를 사용하고 있으며 사용자를 Kaizala에서 Microsoft Teams로 이동하려는 경우 이 섹션의 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="bd64f-128">Follow the guidance in this section, if you're using Kaizala and want to move your users from Kaizala to Microsoft Teams.</span></span>
   
<span data-ttu-id="bd64f-129">계속하기 전에 다음 작업을 **완료한지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="bd64f-129">**Before proceeding, confirm that you've completed the following activities**:</span></span> 
   
- <span data-ttu-id="bd64f-130">조직에 대한 구상된 팀워크</span><span class="sxs-lookup"><span data-stu-id="bd64f-130">Envisioned teamwork for your organization</span></span> 
- <span data-ttu-id="bd64f-131">식별된 챔피언 및 중요한 이해 관계자</span><span class="sxs-lookup"><span data-stu-id="bd64f-131">Identified champions and critical stakeholders</span></span> 
- <span data-ttu-id="bd64f-132">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="bd64f-132">Defined your project scope</span></span>  
- <span data-ttu-id="bd64f-133">파일럿된 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd64f-133">Piloted Microsoft Teams</span></span>
- <span data-ttu-id="bd64f-134">조직 준비</span><span class="sxs-lookup"><span data-stu-id="bd64f-134">Prepared your organization</span></span>  
   
<span data-ttu-id="bd64f-135">전환을 위해 다음 프레임워크를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-135">We recommend the following framework for transition:</span></span> 
   
- <span data-ttu-id="bd64f-136">**조직에 대한 구상 팀워크**</span><span class="sxs-lookup"><span data-stu-id="bd64f-136">**Envision teamwork for your organization**</span></span> 
   
   <span data-ttu-id="bd64f-137">Kaizala가 사용되는 현재 시나리오를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-137">List the current scenarios in which Kaizala is used.</span></span> <span data-ttu-id="bd64f-138">다음으로, Microsoft Teams를 통해 위와 그 이상의 시나리오를 구상합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-138">Next, envision scenarios above and beyond with Microsoft Teams.</span></span>  

- <span data-ttu-id="bd64f-139">**파일럿 팀**</span><span class="sxs-lookup"><span data-stu-id="bd64f-139">**Pilot Teams**</span></span>

   <span data-ttu-id="bd64f-140">우선 순위가 높은 시나리오 집합이 있는 파일럿 사용자 그룹에 Teams를 롤아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-140">Roll out Teams to a Pilot group of users with a prioritized scenario set.</span></span> 

- <span data-ttu-id="bd64f-141">**Teams 배포**</span><span class="sxs-lookup"><span data-stu-id="bd64f-141">**Deploy Teams**</span></span> 

   <span data-ttu-id="bd64f-142">파일럿 그룹에서 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-142">Learn from the pilot group.</span></span> <span data-ttu-id="bd64f-143">전체 조직에 롤아웃할 준비를 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-143">Prepare to roll out to the complete organization.</span></span>  

- <span data-ttu-id="bd64f-144">**Kaizala 및 Teams 사용**</span><span class="sxs-lookup"><span data-stu-id="bd64f-144">**Use Kaizala and Teams**</span></span>  

   <span data-ttu-id="bd64f-145">비즈니스에 적합한 Microsoft Teams를 찾으신 경우 Microsoft Teams Online 옵션 비교를 [| Microsoft Teams](https://www.microsoft.com/microsoft-teams/compare-microsoft-teams-options).</span><span class="sxs-lookup"><span data-stu-id="bd64f-145">To find the right Microsoft Teams for your business, see [Compare Microsoft Teams Online Options | Microsoft Teams](https://www.microsoft.com/microsoft-teams/compare-microsoft-teams-options).</span></span> 

- <span data-ttu-id="bd64f-146">**변경 관리**</span><span class="sxs-lookup"><span data-stu-id="bd64f-146">**Manage change**</span></span> 

   <span data-ttu-id="bd64f-147">채택을 구동하기 위해 최종 사용자 교육을 통해 조직에 변경을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-147">Prepare your organization for change through end-user training to drive adoption.</span></span> <span data-ttu-id="bd64f-148">IT 관리자 및 챔피언은 이동 시 긍정적인 변경 관리에 영향을 미치기 위해 노력을 기울일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-148">IT Admins and Champions can drive efforts to influence positive change management on the move.</span></span>  

- <span data-ttu-id="bd64f-149">**Teams 채택 계획**</span><span class="sxs-lookup"><span data-stu-id="bd64f-149">**Plan for your adoption of Teams**</span></span>

    <span data-ttu-id="bd64f-150">Kaizala에서 Teams로 사용자 지정 솔루션을 이동(예: 사용자 지정 작업 카드)를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="bd64f-150">Prepare to move custom solutions from Kaizala to Teams, for example, Custom Action cards.</span></span> 
     
- <span data-ttu-id="bd64f-151">**조직을 Teams로 이동**</span><span class="sxs-lookup"><span data-stu-id="bd64f-151">**Move your organization to Teams**</span></span> 

    <span data-ttu-id="bd64f-152">CEO에서 최전선으로의 통신을 위한 간소화된 도구를 사용하여 조직에 권한을 부여하세요!</span><span class="sxs-lookup"><span data-stu-id="bd64f-152">Empower your organization with a streamlined tool for communication from CEO to the frontline!</span></span> 
