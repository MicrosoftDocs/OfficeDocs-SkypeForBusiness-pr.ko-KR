---
title: Microsoft 365 정부의 GCC 배포 계획-Microsoft 팀
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 미국 정부의 규정에 따라 데이터를 처리 하는 엔터티에서 Office 365 배포를 구동 하는 IT 전문가를 위한 지침
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4228210fa7b6d9518fa060b2bdd555f434ed6f2
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069309"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="b73f6-103">Microsoft 365 정부의 GCC 배포 계획</span><span class="sxs-lookup"><span data-stu-id="b73f6-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="b73f6-104">이 지침은 Microsoft를 사용 하는 미국 연방, 주, tribal 또는 territorial 정부 기관 또는 정부 규정에 따른 데이터를 처리 하는 기타 엔터티에서 제공 하는 IT 365 전문가를 위한 것입니다. 365 정부-GCC는 이러한 요구 사항을 충족 하는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="b73f6-105">조직이 Microsoft 365 정부 자격 요건을 충족 하 여 프로그램에 적용 한 경우에는 1 ~ 2 단계를 건너뛰고 3 단계로 바로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-105">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="b73f6-106">1 단계.</span><span class="sxs-lookup"><span data-stu-id="b73f6-106">Step 1.</span></span> <span data-ttu-id="b73f6-107">조직에 Microsoft 365 정부 GCC가 필요 하며 자격 요건을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-107">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="b73f6-108">Microsoft 365 정부-GCC 환경은 FedRAMP 중간을 포함 하 여 클라우드 서비스에 대 한 미국 정부 요구 사항과 범죄 규정 및 납세 정보 시스템 (CJI 및 FTI 데이터 형식)에 대 한 요구 사항을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-108">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="b73f6-109">Office 365의 기능과 기능을 활용할 수 있을 뿐만 아니라, Microsoft 365 정부-GCC에는 다음과 같은 기능이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="b73f6-110">조직의 고객 콘텐츠는 Microsoft의 상업용 Office 365 서비스에 있는 고객 콘텐츠에서 논리적으로 분리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="b73f6-111">조직의 고객 콘텐츠는 미국 내에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-111">Your organization’s customer content is stored within the United States.</span></span>
-   <span data-ttu-id="b73f6-112">조직의 고객 콘텐츠에 대 한 액세스는 차단 된 Microsoft 담당자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="b73f6-113">Microsoft 365 정부-GCC는 미국 공공 부문 고객에 게 필요한 인증 및 accreditations을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-113">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="b73f6-114">[자격 요건](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)을 포함 하 여 [Office 365 정부 계획](https://products.office.com/government/compare-office-365-government-plans)에서 미국 정부의 고객을 위한 Microsoft 365 정부 GCC 제공에 대 한 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-114">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="b73f6-115">[Office 365 미국 정부의 서비스 설명은](https://technet.microsoft.com/library/mt774581.aspx) 미국 내의 모임 준수 요구 사항을 중심으로 하는 플랫폼의 이점에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-115">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform’s benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="b73f6-116">서비스 설명의 정보 테이블을 Excel 통합 문서로 전송 하 고 **조직 y/n과 관련** 된 두 개의 열을 추가 하 고 **조직 y/n의 요구를 충족 하는**것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="b73f6-117">그런 다음 동료와이 목록을 검토 하 여이 서비스가 조직의 요구 사항에 맞는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b73f6-119">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="b73f6-119">Decision points</span></span>|<ul><li><span data-ttu-id="b73f6-120">Microsoft 365 정부-GCC가 조직에 적합 한지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-120">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="b73f6-121">조직이 자격 요건을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="b73f6-122">Microsoft 365 정부-GCC는 미국 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-122">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="b73f6-123">미국 정부의 고객이 아닌 사용자는 다양 한 [Office 365 정부 계획](https://products.office.com/en/government/compare-office-365-government-plans)중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="b73f6-124">2 단계.</span><span class="sxs-lookup"><span data-stu-id="b73f6-124">Step 2.</span></span> <span data-ttu-id="b73f6-125">Microsoft 365 정부 에디션 (GCC)에 적용</span><span class="sxs-lookup"><span data-stu-id="b73f6-125">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="b73f6-126">이 서비스가 조직에 적합 하다 고 결정 한 경우 [여기에서이 서비스에 적용](https://products.office.com/government/eligibility-validation)하는 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-126">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="b73f6-127">3 단계.</span><span class="sxs-lookup"><span data-stu-id="b73f6-127">Step 3.</span></span> <span data-ttu-id="b73f6-128">Microsoft 365 정부의 GCC 기본 보안 설정에 대해 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-128">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="b73f6-129">[관리 및 보안 설정을](enable-features-office-365.md) 수정 하기 전에 신중 하 게 검토 하 고 기본 보안 설정을 변경 하기 전에 준수에 영향을 주는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![결정 지점을 가리키는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b73f6-131">판단 요점</span><span class="sxs-lookup"><span data-stu-id="b73f6-131">Decision point</span></span>|<ul><li><span data-ttu-id="b73f6-132">기본 Microsoft 365 정부-GCC 보안 설정 중 어떤 것을 수정 하 고 있는지 확인 하 고, 먼저 변경 사항에 대 한 영향을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-132">Decide whether you’ll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="b73f6-133">4 단계.</span><span class="sxs-lookup"><span data-stu-id="b73f6-133">Step 4.</span></span> <span data-ttu-id="b73f6-134">기본적으로 현재 사용할 수 없거나 사용 불가능 한 기능을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-134">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="b73f6-135">귀하의 정부 클라우드 고객의 요구 사항을 충족 하기 위해 Microsoft 365 정부-GCC 및 Enterprise 요금제 간에는 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-135">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="b73f6-136">사용할 수 있는 기능을 확인 하려면 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b73f6-136">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="b73f6-137">기능</span><span class="sxs-lookup"><span data-stu-id="b73f6-137">Feature</span></span>                     | <span data-ttu-id="b73f6-138">GCC</span><span class="sxs-lookup"><span data-stu-id="b73f6-138">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="b73f6-139">기반의</span><span class="sxs-lookup"><span data-stu-id="b73f6-139">Base</span></span> | <span data-ttu-id="b73f6-140">로그인</span><span class="sxs-lookup"><span data-stu-id="b73f6-140">Login</span></span> | <span data-ttu-id="b73f6-141">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-141">Available</span></span> |
| | <span data-ttu-id="b73f6-142">현재 상태</span><span class="sxs-lookup"><span data-stu-id="b73f6-142">Presence</span></span> | <span data-ttu-id="b73f6-143">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-143">Available</span></span> |
| | <span data-ttu-id="b73f6-144">통합 현재 상태 (비즈니스용 Skype 및 팀 통합)</span><span class="sxs-lookup"><span data-stu-id="b73f6-144">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="b73f6-145">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-145">Available</span></span> |
| <span data-ttu-id="b73f6-146">작동이</span><span class="sxs-lookup"><span data-stu-id="b73f6-146">Activity</span></span> | <span data-ttu-id="b73f6-147">피드</span><span class="sxs-lookup"><span data-stu-id="b73f6-147">Feed</span></span> | <span data-ttu-id="b73f6-148">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-148">Available</span></span> |
|  | <span data-ttu-id="b73f6-149">내 활동</span><span class="sxs-lookup"><span data-stu-id="b73f6-149">My Activity</span></span> | <span data-ttu-id="b73f6-150">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-150">Available</span></span> |
| <span data-ttu-id="b73f6-151">채팅</span><span class="sxs-lookup"><span data-stu-id="b73f6-151">Chat</span></span> | <span data-ttu-id="b73f6-152">주제별로</span><span class="sxs-lookup"><span data-stu-id="b73f6-152">Conversation</span></span> | <span data-ttu-id="b73f6-153">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-153">Available</span></span> |
| | <span data-ttu-id="b73f6-154">파일</span><span class="sxs-lookup"><span data-stu-id="b73f6-154">Files</span></span> | <span data-ttu-id="b73f6-155">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-155">Available</span></span> |
| | <span data-ttu-id="b73f6-156">조직도</span><span class="sxs-lookup"><span data-stu-id="b73f6-156">Org chart</span></span> | <span data-ttu-id="b73f6-157">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-157">Available</span></span> |
| | <span data-ttu-id="b73f6-158">작동이</span><span class="sxs-lookup"><span data-stu-id="b73f6-158">Activity</span></span> | <span data-ttu-id="b73f6-159">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-159">Available</span></span> |
| | <span data-ttu-id="b73f6-160">InterOp (1:1 팀-비즈니스용 Skype 채팅)</span><span class="sxs-lookup"><span data-stu-id="b73f6-160">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="b73f6-161">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-161">Available</span></span> |
| <span data-ttu-id="b73f6-162">Teams</span><span class="sxs-lookup"><span data-stu-id="b73f6-162">Teams</span></span> | <span data-ttu-id="b73f6-163">채널 메시지</span><span class="sxs-lookup"><span data-stu-id="b73f6-163">Channel message</span></span> | <span data-ttu-id="b73f6-164">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-164">Available</span></span> |
| | <span data-ttu-id="b73f6-165">채널 파일</span><span class="sxs-lookup"><span data-stu-id="b73f6-165">Channel files</span></span> | <span data-ttu-id="b73f6-166">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-166">Available</span></span> |
| | <span data-ttu-id="b73f6-167">OneNote 탭</span><span class="sxs-lookup"><span data-stu-id="b73f6-167">OneNote tab</span></span> | <span data-ttu-id="b73f6-168">정부 백로그</span><span class="sxs-lookup"><span data-stu-id="b73f6-168">On the Government backlog</span></span> |
| | <span data-ttu-id="b73f6-169">채널을 전자 메일로 보내기</span><span class="sxs-lookup"><span data-stu-id="b73f6-169">Email a channel</span></span> | <span data-ttu-id="b73f6-170">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="b73f6-170">Not available</span></span> |
| | <span data-ttu-id="b73f6-171">구성원 추가</span><span class="sxs-lookup"><span data-stu-id="b73f6-171">Add member</span></span> | <span data-ttu-id="b73f6-172">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-172">Available</span></span> |
| | <span data-ttu-id="b73f6-173">게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="b73f6-173">Guest access</span></span> | <span data-ttu-id="b73f6-174">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-174">Available</span></span> |
| <span data-ttu-id="b73f6-175">모임</span><span class="sxs-lookup"><span data-stu-id="b73f6-175">Meetings</span></span> | <span data-ttu-id="b73f6-176">모임 예약</span><span class="sxs-lookup"><span data-stu-id="b73f6-176">Schedule meeting</span></span> | <span data-ttu-id="b73f6-177">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-177">Available</span></span> |
| | <span data-ttu-id="b73f6-178">모임 참가</span><span class="sxs-lookup"><span data-stu-id="b73f6-178">Join meeting</span></span> | <span data-ttu-id="b73f6-179">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-179">Available</span></span> |
| | <span data-ttu-id="b73f6-180">VoIP 모임</span><span class="sxs-lookup"><span data-stu-id="b73f6-180">VoIP meeting</span></span> | <span data-ttu-id="b73f6-181">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-181">Available</span></span> |
| | <span data-ttu-id="b73f6-182">데스크톱 공유</span><span class="sxs-lookup"><span data-stu-id="b73f6-182">Desktop sharing</span></span> | <span data-ttu-id="b73f6-183">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-183">Available</span></span> |
| | <span data-ttu-id="b73f6-184">공유 하 고 제어권을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-184">Give and take control in sharing</span></span> | <span data-ttu-id="b73f6-185">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-185">Available</span></span> |
| | <span data-ttu-id="b73f6-186">회의실에서 연결</span><span class="sxs-lookup"><span data-stu-id="b73f6-186">Connect from a conference room</span></span> | <span data-ttu-id="b73f6-187">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-187">Available</span></span> |
| | <span data-ttu-id="b73f6-188">익명 참가</span><span class="sxs-lookup"><span data-stu-id="b73f6-188">Anonymous join</span></span> | <span data-ttu-id="b73f6-189">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-189">Available</span></span> |
| | <span data-ttu-id="b73f6-190">클라우드 기록</span><span class="sxs-lookup"><span data-stu-id="b73f6-190">Cloud recording</span></span> | <span data-ttu-id="b73f6-191">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-191">Available</span></span> |
| | <span data-ttu-id="b73f6-192">모임 메모</span><span class="sxs-lookup"><span data-stu-id="b73f6-192">Meeting notes</span></span> | <span data-ttu-id="b73f6-193">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-193">Available</span></span> |
| | <span data-ttu-id="b73f6-194">라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="b73f6-194">Live Events</span></span> | <span data-ttu-id="b73f6-195">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-195">Available</span></span> |
| | <span data-ttu-id="b73f6-196">페더레이션된 모임</span><span class="sxs-lookup"><span data-stu-id="b73f6-196">Federated meetings</span></span> | <span data-ttu-id="b73f6-197">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-197">Available</span></span> |
| | <span data-ttu-id="b73f6-198">Surface Hub 지원</span><span class="sxs-lookup"><span data-stu-id="b73f6-198">Surface Hub support</span></span> | <span data-ttu-id="b73f6-199">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-199">Available</span></span> |
| <span data-ttu-id="b73f6-200">전화가</span><span class="sxs-lookup"><span data-stu-id="b73f6-200">Calls</span></span> | <span data-ttu-id="b73f6-201">연락처</span><span class="sxs-lookup"><span data-stu-id="b73f6-201">Contacts</span></span> | <span data-ttu-id="b73f6-202">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-202">Available</span></span> |
| | <span data-ttu-id="b73f6-203">역사</span><span class="sxs-lookup"><span data-stu-id="b73f6-203">History</span></span> | <span data-ttu-id="b73f6-204">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-204">Available</span></span> |
| | <span data-ttu-id="b73f6-205">음성 메일</span><span class="sxs-lookup"><span data-stu-id="b73f6-205">Voicemail</span></span> | <span data-ttu-id="b73f6-206">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-206">Available</span></span> |
| | <span data-ttu-id="b73f6-207">VoIP 통화</span><span class="sxs-lookup"><span data-stu-id="b73f6-207">VoIP call</span></span> | <span data-ttu-id="b73f6-208">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-208">Available</span></span> |
| | <span data-ttu-id="b73f6-209">비즈니스용 Skype-팀 전화</span><span class="sxs-lookup"><span data-stu-id="b73f6-209">Skype for Business - Teams calling</span></span> | <span data-ttu-id="b73f6-210">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-210">Available</span></span> |
| | <span data-ttu-id="b73f6-211">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="b73f6-211">Calling Plans</span></span> | <span data-ttu-id="b73f6-212">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-212">Available</span></span> |
| | <span data-ttu-id="b73f6-213">오디오 회의 (모임 참가자가 PSTN을 통해 참가 하도록 허용)</span><span class="sxs-lookup"><span data-stu-id="b73f6-213">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="b73f6-214">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-214">Available</span></span> |
| | <span data-ttu-id="b73f6-215">Microsoft 전화 시스템 다이렉트 라우팅</span><span class="sxs-lookup"><span data-stu-id="b73f6-215">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="b73f6-216">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-216">Available</span></span> |
| | <span data-ttu-id="b73f6-217">PSTN 호출자 용 대기실</span><span class="sxs-lookup"><span data-stu-id="b73f6-217">Lobby for PSTN callers</span></span> | <span data-ttu-id="b73f6-218">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-218">Available</span></span> |
| | <span data-ttu-id="b73f6-219">통화 대기열</span><span class="sxs-lookup"><span data-stu-id="b73f6-219">Call queue</span></span> | <span data-ttu-id="b73f6-220">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-220">Available</span></span> |
| | <span data-ttu-id="b73f6-221">상사 및 대리인 지원</span><span class="sxs-lookup"><span data-stu-id="b73f6-221">Boss and delegate support</span></span> | <span data-ttu-id="b73f6-222">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-222">Available</span></span> |
| | <span data-ttu-id="b73f6-223">Consultative 및 안전한 전송</span><span class="sxs-lookup"><span data-stu-id="b73f6-223">Consultative and safe transfer</span></span> | <span data-ttu-id="b73f6-224">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-224">Available</span></span> |
| | <span data-ttu-id="b73f6-225">혁신을 방해 하지 않음</span><span class="sxs-lookup"><span data-stu-id="b73f6-225">Do not disturb breakthrough</span></span> | <span data-ttu-id="b73f6-226">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-226">Available</span></span> |
| | <span data-ttu-id="b73f6-227">특수 전화 벨 소리</span><span class="sxs-lookup"><span data-stu-id="b73f6-227">Distinctive ring</span></span> | <span data-ttu-id="b73f6-228">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-228">Available</span></span> |
| | <span data-ttu-id="b73f6-229">팀, 비즈니스용 Skype, PSTN 참가자와의 그룹 통화 확대 1:1</span><span class="sxs-lookup"><span data-stu-id="b73f6-229">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="b73f6-230">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-230">Available</span></span> |
| | <span data-ttu-id="b73f6-231">그룹으로 전달</span><span class="sxs-lookup"><span data-stu-id="b73f6-231">Forward to group</span></span> | <span data-ttu-id="b73f6-232">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-232">Available</span></span> |
| | <span data-ttu-id="b73f6-233">PSTN 통화로 전송</span><span class="sxs-lookup"><span data-stu-id="b73f6-233">Transfer to PSTN call</span></span> | <span data-ttu-id="b73f6-234">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-234">Available</span></span> |
| | <span data-ttu-id="b73f6-235">비상 전화 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="b73f6-235">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="b73f6-236">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-236">Available</span></span> |
| | <span data-ttu-id="b73f6-237">기존 인증 된 SIP 전화 지원</span><span class="sxs-lookup"><span data-stu-id="b73f6-237">Support for existing certified SIP phones</span></span> | <span data-ttu-id="b73f6-238">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-238">Available</span></span> |
| | <span data-ttu-id="b73f6-239">USB HID</span><span class="sxs-lookup"><span data-stu-id="b73f6-239">USB HID</span></span> | <span data-ttu-id="b73f6-240">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-240">Available</span></span> |
| | <span data-ttu-id="b73f6-241">통화 및 모임 모두에 대해 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b73f6-241">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="b73f6-242">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-242">Available</span></span> |
| | <span data-ttu-id="b73f6-243">조직 자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="b73f6-243">Organization auto attendant</span></span> | <span data-ttu-id="b73f6-244">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-244">Available</span></span> |
| | <span data-ttu-id="b73f6-245">Skype 소비자-팀 전화 지원</span><span class="sxs-lookup"><span data-stu-id="b73f6-245">Skype consumer - Teams call support</span></span> | <span data-ttu-id="b73f6-246">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-246">Available</span></span> |
| <span data-ttu-id="b73f6-247">파일</span><span class="sxs-lookup"><span data-stu-id="b73f6-247">Files</span></span> | <span data-ttu-id="b73f6-248">최근</span><span class="sxs-lookup"><span data-stu-id="b73f6-248">Recent</span></span> | <span data-ttu-id="b73f6-249">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-249">Available</span></span> |
| | <span data-ttu-id="b73f6-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b73f6-250">Microsoft Teams</span></span> | <span data-ttu-id="b73f6-251">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-251">Available</span></span> |
| <span data-ttu-id="b73f6-252">스토어</span><span class="sxs-lookup"><span data-stu-id="b73f6-252">Store</span></span> | <span data-ttu-id="b73f6-253">App Store</span><span class="sxs-lookup"><span data-stu-id="b73f6-253">App Store</span></span> | <span data-ttu-id="b73f6-254">정부 백로그</span><span class="sxs-lookup"><span data-stu-id="b73f6-254">On the Government backlog</span></span> |
| <span data-ttu-id="b73f6-255">찾아</span><span class="sxs-lookup"><span data-stu-id="b73f6-255">Search</span></span> | <span data-ttu-id="b73f6-256">보내는</span><span class="sxs-lookup"><span data-stu-id="b73f6-256">Messages</span></span> | <span data-ttu-id="b73f6-257">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-257">Available</span></span> |
| | <span data-ttu-id="b73f6-258">사용자</span><span class="sxs-lookup"><span data-stu-id="b73f6-258">People</span></span> | <span data-ttu-id="b73f6-259">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-259">Available</span></span> |
| | <span data-ttu-id="b73f6-260">파일</span><span class="sxs-lookup"><span data-stu-id="b73f6-260">Files</span></span> | <span data-ttu-id="b73f6-261">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-261">Available</span></span> |
| | <span data-ttu-id="b73f6-262">슬래시 명령</span><span class="sxs-lookup"><span data-stu-id="b73f6-262">Slash commands</span></span> | <span data-ttu-id="b73f6-263">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-263">Available</span></span> |
| <span data-ttu-id="b73f6-264">충족</span><span class="sxs-lookup"><span data-stu-id="b73f6-264">Compliance</span></span> | <span data-ttu-id="b73f6-265">콘텐츠 검색 준수</span><span class="sxs-lookup"><span data-stu-id="b73f6-265">Compliance content search</span></span> | <span data-ttu-id="b73f6-266">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-266">Available</span></span> |
| | <span data-ttu-id="b73f6-267">보관</span><span class="sxs-lookup"><span data-stu-id="b73f6-267">Retention</span></span> | <span data-ttu-id="b73f6-268">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-268">Available</span></span> |
| | <span data-ttu-id="b73f6-269">감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="b73f6-269">Audit log search</span></span> | <span data-ttu-id="b73f6-270">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-270">Available</span></span> |
| | <span data-ttu-id="b73f6-271">법률 보류</span><span class="sxs-lookup"><span data-stu-id="b73f6-271">Legal hold</span></span> | <span data-ttu-id="b73f6-272">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-272">Available</span></span> |
| | <span data-ttu-id="b73f6-273">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b73f6-273">eDiscovery</span></span> | <span data-ttu-id="b73f6-274">공간이</span><span class="sxs-lookup"><span data-stu-id="b73f6-274">Available</span></span> |

> [!Note]

> <span data-ttu-id="b73f6-275">다른 작업을 GCC 클라우드에서 완전히 사용할 수 있게 되 면 모든 추가 통합 작업이 완료 되 면 팀에서 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-275">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![결정 지점을 가리키는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b73f6-277">판단 요점</span><span class="sxs-lookup"><span data-stu-id="b73f6-277">Decision point</span></span>|<ul><li><span data-ttu-id="b73f6-278">팀 기능 집합이 조직의 요구 사항에 맞는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-278">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="b73f6-279">5 단계.</span><span class="sxs-lookup"><span data-stu-id="b73f6-279">Step 5.</span></span> <span data-ttu-id="b73f6-280">관리 계획</span><span class="sxs-lookup"><span data-stu-id="b73f6-280">Plan for governance</span></span>

<span data-ttu-id="b73f6-281">관리에 대 한 요구 사항과이를 충족 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-281">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="b73f6-282">자세한 내용은 [팀의 관리 계획](plan-teams-governance.md) 으로 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="b73f6-282">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![결정 지점을 가리키는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b73f6-284">판단 요점</span><span class="sxs-lookup"><span data-stu-id="b73f6-284">Decision point</span></span>|<ul><li><span data-ttu-id="b73f6-285">[팀의 관리 계획에 대 한](plan-teams-governance.md)지침에 따라 관리 요구 사항을 결정 하 고 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-285">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="b73f6-286">6 단계.</span><span class="sxs-lookup"><span data-stu-id="b73f6-286">Step 6.</span></span> <span data-ttu-id="b73f6-287">공동 작업을 위해 팀 배포</span><span class="sxs-lookup"><span data-stu-id="b73f6-287">Deploy Teams for collaboration</span></span>

<span data-ttu-id="b73f6-288">Microsoft 365 정부-GCC에 onboarded 한 후에 Microsoft 팀을 배포 하 [는 방법](How-to-roll-out-teams.md)에 대해 설명 하는 권장 구축 경로를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b73f6-288">After you’ve been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="b73f6-289">채택 및 변경 관리 팀과 팀이 챔피언을 사용 하 여 참여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-289">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="b73f6-290">[Fasttrack](https://www.microsoft.com/fasttrack) 또는 선택한 파트너를 통해 서비스를 온보드 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-290">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="b73f6-291">7 단계.</span><span class="sxs-lookup"><span data-stu-id="b73f6-291">Step 7.</span></span> <span data-ttu-id="b73f6-292">모임 및 음성 용 팀 배포</span><span class="sxs-lookup"><span data-stu-id="b73f6-292">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="b73f6-293">또한 더 광범위 한 관련자 그룹의 팀을 사용 하 여 모임 및 [클라우드 음성 기능](cloud-voice-deployment.md)롤아웃 계획을 시작 하는 데는 상당한 시간이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73f6-293">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

