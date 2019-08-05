---
title: 클라우드 음성 배포
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: Rowille
description: Microsoft 팀에서 클라우드 음성 기능을 배포 하기 위한 실용적인 지침입니다.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7cce1d8c6abfe3c71e9ac923899b9b8f18626cbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "36182144"
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="27354-103">클라우드 음성 배포</span><span class="sxs-lookup"><span data-stu-id="27354-103">Cloud voice deployment</span></span>

<span data-ttu-id="27354-104">Microsoft 팀, Office 365의 팀워크 및 통신을 위한 허브는 이제 오디오 회의, 전화 시스템, 통화 요금제 및 전화 시스템 다이렉트 라우팅 기능을 제공 하 여 팀 회의를 확장 하 여 추가 비즈니스 요구 사항에 부합 합니다. PSTN (공개 교환 전화 네트워크)을 통해 연결 된 외부 파티를 포함 하는 전화 경험.</span><span class="sxs-lookup"><span data-stu-id="27354-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing, Phone System with Calling Plans, and Phone System Direct Routing capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>


> [!Tip] 
> <span data-ttu-id="27354-105">전화 시스템 소개에 대 한 다음 세션을 시청 하세요. [Microsoft 팀의 전화 시스템 소개](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="27354-105">Watch the following session for an introduction to Phone Systems: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>
 
<span data-ttu-id="27354-106">이 페이지는 시간에 따라 팀에 대 한 추가 클라우드 음성 기능 출시로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27354-106">We’ll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="27354-107">Microsoft 팀의 오디오 회의</span><span class="sxs-lookup"><span data-stu-id="27354-107">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="27354-108">참가자는 Office 365의 오디오 회의를 통해 모든 전화기에서 팀 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27354-108">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="27354-109">Office 365에서 [오디오 회의](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) 를 통해 얻을 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="27354-109">Here’s what you get with [Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a><span data-ttu-id="27354-110">통화 요금제가 포함 되어 있는 전화 시스템 ("통화 계획")은 Microsoft 팀에서</span><span class="sxs-lookup"><span data-stu-id="27354-110">Phone System with Calling Plans (“Calling Plans”) in Microsoft Teams</span></span>

<span data-ttu-id="27354-111">전화 시스템은 통화 라우팅, 정책, 사용자 프로비저닝 관리 기능을 제공 하는 Office 365 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="27354-111">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="27354-112">여기에는 전화 통화 관리 시스템, 통화 라우팅 및 통화 제어가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27354-112">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="27354-113">통화 요금제는 비즈니스용 Skype Online을 통해 제공 되는 전화 시스템 기능에 대 한 추가 기능 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="27354-113">Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="27354-114">통화 계획을 사용 하려면 Microsoft 팀에서 작동 하려면 비즈니스용 Skype Online에서 해당 사용자를 홈으로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27354-114">Calling Plans requires that the user in question be homed in Skype for Business Online to work in Microsoft Teams.</span></span> <span data-ttu-id="27354-115">통화 요금제는 회사의 사용자에 게 기본 전화 번호를 제공 하 고 PSTN을 통해 조직 외부의 전화를 걸고 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="27354-115">Calling Plans provide the people in your business with a primary phone number, and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="27354-116">자세한 내용은 Office 365 및 [전화 시스템 및 통화 요금제](calling-plan-landing-page.md) [에서 전화 시스템을 사용 하 여 얻을 수 있는 기능](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) 을 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="27354-116">To learn more, read [Here’s what you get with Phone System in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) and [Phone System and Calling Plans](calling-plan-landing-page.md)</span></span>


## <a name="phone-system-direct-routing-direct-routing"></a><span data-ttu-id="27354-117">전화 시스템 직접 라우팅 ("직접 라우팅")</span><span class="sxs-lookup"><span data-stu-id="27354-117">Phone System Direct Routing (“Direct Routing”)</span></span>

<span data-ttu-id="27354-118">다이렉트 라우팅은 전화 시스템 기능을 사용 하 여 조직의 사용자에 게 PSTN을 통해 조직 외부의 전화를 걸고 받을 수 있는 기능을 제공 하며, PSTN 연결이 타사 서비스 공급자를 통해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27354-118">Direct Routing works with the Phone System feature to give people in your organization the ability make and receive phone calls outside of the organization over the PSTN, where PSTN connectivity is provided via third-party service providers.</span></span>

<span data-ttu-id="27354-119">자세한 내용은 [직접 라우팅 계획](direct-routing-plan.md) 및 [직접 라우팅 구성을](direct-routing-configure.md)참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="27354-119">To learn more, read [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a><span data-ttu-id="27354-120">Microsoft 팀의 오디오 회의, 통화 요금제 및 직접 라우팅에 대 한 실용적인 지침</span><span class="sxs-lookup"><span data-stu-id="27354-120">Practical guidance for Audio Conferencing, Calling Plans, and Direct Routing in Microsoft Teams</span></span>

<span data-ttu-id="27354-121">이 실용적인 지침은 Office 365 FastTrack 고객 여행 프레임 워크 및 세 가지 단계&mdash;구상, 온보드 및 드라이브 값을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27354-121">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="27354-122">이는 성공적인 오디오 회의, 통화 계획 또는 다이렉트 라우팅 구현에 대 한 계획, 제공 및 운영에 도움을 주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="27354-122">It’s intended to help you plan, deliver, and operate a successful Audio Conferencing, Calling Plans, or Direct Routing implementation.</span></span>

> [!div class="mx-tableFixed"]
> |<span data-ttu-id="27354-123">구상</span><span class="sxs-lookup"><span data-stu-id="27354-123">Envision</span></span>  |<span data-ttu-id="27354-124">등록</span><span class="sxs-lookup"><span data-stu-id="27354-124">Onboard</span></span>  |<span data-ttu-id="27354-125">드라이브 값</span><span class="sxs-lookup"><span data-stu-id="27354-125">Drive Value</span></span>  |
> |---------|---------|---------|
> |[<span data-ttu-id="27354-126">성공 정의</span><span class="sxs-lookup"><span data-stu-id="27354-126">Define my success</span></span>](1-envision-define-my-success-cloud-voice.md) <br> <span data-ttu-id="27354-127">내 서비스 결정 하기</span><span class="sxs-lookup"><span data-stu-id="27354-127">Make my service decisions for</span></span> <br><span data-ttu-id="27354-128">&nbsp;&nbsp;[오디오 회의](2-envision-make-my-service-decisions-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="27354-128">&nbsp;&nbsp;[Audio Conferencing](2-envision-make-my-service-decisions-audio-conferencing.md),</span></span><br><span data-ttu-id="27354-129">&nbsp;&nbsp;[통화 요금제](2-envision-make-my-service-decisions-phone-system.md)또는 [직접 라우팅](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="27354-129">&nbsp;&nbsp;[Calling Plans](2-envision-make-my-service-decisions-phone-system.md), or [Direct Routing](2-envision-make-my-service-decisions-direct-routing.md)</span></span> <br> [<span data-ttu-id="27354-130">내 환경 평가</span><span class="sxs-lookup"><span data-stu-id="27354-130">Evaluate my environment</span></span>](3-envision-evaluate-my-environment.md) <br> [<span data-ttu-id="27354-131">내 서비스 관리 계획</span><span class="sxs-lookup"><span data-stu-id="27354-131">Plan my service management</span></span>](4-envision-plan-my-service-management.md) <br> [<span data-ttu-id="27354-132">내 사용자 환경 계획</span><span class="sxs-lookup"><span data-stu-id="27354-132">Plan my users’ experience</span></span>](5-envision-plan-my-users-experience.md) <br> [<span data-ttu-id="27354-133">내 성공 계획 문서화</span><span class="sxs-lookup"><span data-stu-id="27354-133">Document my success plan</span></span>](6-envision-document-my-success-plan.md)    | [<span data-ttu-id="27354-134">내 서비스 준비</span><span class="sxs-lookup"><span data-stu-id="27354-134">Prepare my service</span></span>](1-onboard-prepare-my-service.md) <br> [<span data-ttu-id="27354-135">사용자 준비</span><span class="sxs-lookup"><span data-stu-id="27354-135">Prepare my users</span></span>](2-onboard-prepare-my-users.md) <br> [<span data-ttu-id="27354-136">내 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="27354-136">Deploy my service</span></span>](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [<span data-ttu-id="27354-137">내 서비스 운영</span><span class="sxs-lookup"><span data-stu-id="27354-137">Operate my service</span></span>](1-drive-value-operate-my-service.md) <br> [<span data-ttu-id="27354-138">내 서비스 향상</span><span class="sxs-lookup"><span data-stu-id="27354-138">Enhance my service</span></span>](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

<span data-ttu-id="27354-139">콘텐츠는 순서가 지정 된 방식으로 제공 되며, 처음부터 끝까지 종단간 배포를 여행 하는 과정을 안내 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27354-139">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="27354-140">이미 배포 중인 경우에도 해당 콘텐츠 영역을 참조 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="27354-140">If you’re already actively deploying, we still encourage you to reference the applicable content areas.</span></span>


> [!TIP]
> <span data-ttu-id="27354-141">이 실제 지침에서는 각 활동에 대 한 예제 출력과 키 토론을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27354-141">In this practical guidance, we provide example outputs for each activity and key discussion.</span></span> <span data-ttu-id="27354-142">이 문서의 예제는 Tip 설명선 안에 포함 되어 있으며 다시 사용할 수 있는 서식 파일 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="27354-142">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="27354-143">계획 프로세스의 일부로 완료 해야 하는 정보에 대 한 "TBA" (추가 예정)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27354-143">You’ll see “TBA” (to be added) for information that you need to complete as part of your planning process.</span></span>
