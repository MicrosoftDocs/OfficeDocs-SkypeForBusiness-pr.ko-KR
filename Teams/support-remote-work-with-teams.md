---
title: Microsoft Teams를 사용하여 원격 작업자 지원하기
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: dansteve
localization_priority: Priority
search.appverid: MET150
description: >
  조직의 원격 작업자가 특히 COVID-19(코로나 바이러스) 발생에 대응하여 재택 근무(WFH)를 하는 경우 이 가이드를 읽고 Microsoft Teams를 사용하여 생산성을 높일 수 있습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80af76906697ef2510fe75d8764e8908cdbbd976
ms.sourcegitcommit: ed0ecb3b1250a23d3b91a5a33256aee1c3119db1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374315"
---
# <a name="support-remote-workers-using-microsoft-teams"></a><span data-ttu-id="58c46-103">Microsoft Teams를 사용하여 원격 작업자 지원하기</span><span class="sxs-lookup"><span data-stu-id="58c46-103">Support remote workers using Microsoft Teams</span></span>

<span data-ttu-id="58c46-104">이 문서의 모범 사례를 사용하여 원격으로 또는 집에서 일하는 사용자를 지원하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-104">Use the best practices in this article to support your users who work remotely or from home.</span></span>

## <a name="technical"></a><span data-ttu-id="58c46-105">기술 관련</span><span class="sxs-lookup"><span data-stu-id="58c46-105">Technical</span></span>

1.  <span data-ttu-id="58c46-106">[모든 사용자에 대해 Teams가 설정](assign-teams-licenses.md)되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-106">Make sure [Teams is turned on for everyone](assign-teams-licenses.md)</span></span>
    
      - <span data-ttu-id="58c46-107">[Teams E1 평가판](e1-trial-license.md) 또는 [Teams Exploratory](teams-exploratory.md) 또는 [Teams 무료](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)를 살펴보고 회사의 모든 구성원이 Teams를 사용할 수 있도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-107">Look at the [Teams E1 Trial](e1-trial-license.md), [Teams Exploratory](teams-exploratory.md), or [Teams free](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c) to make Teams available to everybody in your company.</span></span>

      - <span data-ttu-id="58c46-108">원격 직원은 모임 및 오디오 회의에 더 많이 의존하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-108">Remote employees rely more heavily on meetings and audio conferencing.</span></span> <span data-ttu-id="58c46-109">아직 이 작업을 롤아웃하지 않은 경우 [Teams에서 모임 및 회의](deploy-meetings-microsoft-teams-landing-page.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-109">If you haven't yet rolled out these workloads, check out [Meetings and conferencing in Teams](deploy-meetings-microsoft-teams-landing-page.md).</span></span>

2.  <span data-ttu-id="58c46-110">사용자에게 Teams에 대해 알립니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-110">Tell your users about Teams.</span></span> <span data-ttu-id="58c46-111">[Teams 고객 성공 키트](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip)를 다운로드하여 프레젠테이션, 샘플 전자 메일, 포스터, 시작 가이드를 받으세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-111">Download the [Teams Customer Success Kit](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) to get presentations, sample emails, posters, and getting-started guides.</span></span>


5.  <span data-ttu-id="58c46-112">직원들이 Teams에 적합한 인터넷 액세스와 대역폭을 보유하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-112">Make sure your employees have adequate internet access and bandwidth for Teams.</span></span> <span data-ttu-id="58c46-113">[Teams에 대한 조직의 네트워크 준비](prepare-network.md)의 지침을 사용하여 이 작업을 수행하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-113">Use the guidance in [Prepare your organization's network for Teams](prepare-network.md) to learn how to do this.</span></span>
    - <span data-ttu-id="58c46-114">제한된 대역폭은 Teams 모임의 오디오 품질에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-114">Limited bandwidth can affect audio quality in Teams meetings.</span></span> <span data-ttu-id="58c46-115">저대역폭 조건 하에서 최고의 모임을 경험하기 위해, 사용자에게 비디오를 제한하고 통화 및 모임 오디오에 PSTN을 사용하도록 장려합니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-115">To ensure the best meeting experience under low-bandwidth conditions, encourage users to limit video and use PSTN for calls and meeting audio.</span></span> 

    - <span data-ttu-id="58c46-116">통화 또는 모임 품질 문제를 해결하는 데 도움이 필요한 경우에는 이 문서의 맨 아래에 있는 [알려진 문제: 비즈니스용 Skype/Teams 회의에 전화 걸기](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids)에 관한 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-116">If you need help troubleshooting or fixing problems with call or meeting quality, follow the guidance in [Known issue: Dialing into Skype for Business/Teams conference IDs](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids) at the bottom of this article.</span></span>

2.  <span data-ttu-id="58c46-117">직원들이 Teams를 최대한 활용할 수 있도록 [교육 링크를 보내세요](enduser-training.md).</span><span class="sxs-lookup"><span data-stu-id="58c46-117">[Send out links to training](enduser-training.md) to help your employees get the most out of Teams.</span></span>
    
3. <span data-ttu-id="58c46-118">원격 작업에 대한 새로운 내용을 읽고 사용자와 공유하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-118">Read our new content about working remotely and share it with your users:</span></span>
        
      - <span data-ttu-id="58c46-119">Teams 블로그 (2020년 2월 28일): [Microsoft Teams로 집에서 작업하는 4가지 팁](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)</span><span class="sxs-lookup"><span data-stu-id="58c46-119">Teams blog (Feb 28, 2020): [4 tips for working from home with Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)</span></span>

      - [<span data-ttu-id="58c46-120">Office 365로 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="58c46-120">Collaborate with Office 365</span></span>](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [<span data-ttu-id="58c46-121">Teams과 Office 365로 원격 작업하기</span><span class="sxs-lookup"><span data-stu-id="58c46-121">Working remotely with Teams and Office 365</span></span>](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  <span data-ttu-id="58c46-122">모든 사람이 모바일 앱을 [설치](get-clients.md#mobile-clients)하고 사용하도록 장려하기: [iOS](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)</span><span class="sxs-lookup"><span data-stu-id="58c46-122">Encourage everyone to [install](get-clients.md#mobile-clients) and use the mobile app: [iOS](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)</span></span>

    > [!NOTE]
    > <span data-ttu-id="58c46-123">중국에 있는 경우, 여기에 있는 [중국에서 Android용 Teams 받기](get-teams-android-in-china.md)로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-123">If you're in China, go here to [Get Teams for Android in China](get-teams-android-in-china.md)</span></span>

4.  <span data-ttu-id="58c46-124">사용자 문의를 처리하기 위해 [헬프데스크](troubleshoot-installation.md) 직원을 고용하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-124">Staff up your [helpdesk](troubleshoot-installation.md) to deal with user inquiries.</span></span>


## <a name="communications"></a><span data-ttu-id="58c46-125">커뮤니케이션</span><span class="sxs-lookup"><span data-stu-id="58c46-125">Communications</span></span>

<span data-ttu-id="58c46-126">Teams를 사용하여 직원들과 지속적으로 소통하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-126">Use Teams to stay in touch with your employees:</span></span>
- <span data-ttu-id="58c46-127">[조직 전체 팀](create-an-org-wide-team.md) 및 [회사 커뮤니케이터](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator) 앱 템플릿</span><span class="sxs-lookup"><span data-stu-id="58c46-127">[Org-wide teams](create-an-org-wide-team.md) and [Company Communicator](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator) app template</span></span>
    
- <span data-ttu-id="58c46-128">조직의 재택 근무 및 건강 및 안전 정책에 대한 정보를 보내세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-128">Send out information about your org’s work-from-home and health and safety policies.</span></span>
    
- <span data-ttu-id="58c46-129">회사 전체의 모임 및 지원 활동에 [라이브 이벤트](teams-live-events/what-are-teams-live-events.md)를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-129">Use [Live events](teams-live-events/what-are-teams-live-events.md) for company-wide meetings and outreach.</span></span> <span data-ttu-id="58c46-130">250명 이상의 참석자가 있는 모든 모임을 라이브 이벤트로 만드세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-130">For any meeting of more than 250 participants, make it a live event.</span></span> 

## <a name="personal-considerations"></a><span data-ttu-id="58c46-131">개인적 고려 사항</span><span class="sxs-lookup"><span data-stu-id="58c46-131">Personal considerations</span></span>

<span data-ttu-id="58c46-132">다음은 집에서 효과적으로 작업하기 위한 몇 가지 팁입니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-132">Here are some tips for successfully working from home:</span></span>

- <span data-ttu-id="58c46-133">좋은 조명과 적절히 인체 공학적으로 구성된 물리적 작업 공간을 확보하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-133">Have a defined physical work space with good lighting and proper ergonomics.</span></span>

- <span data-ttu-id="58c46-134">근무 시간과 작업에 명확한 경계를 설정하고, 자리에 없는 경우 Teams의 [현재 상태](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e)를 사용하여 이를 표시하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-134">Set clear boundaries on your work hours and commitments, and use the Teams [presence status](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e) to indicate when you're away.</span></span>

- <span data-ttu-id="58c46-135">계획적으로 재택 근무 사무실로 “출퇴근”하세요. 재택 근무를 휴식이 보장되지 않는 근무로 여기지 않도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-135">“Commute” to and from your work-from-home office deliberately; don’t turn work-from-home into home-equals-work.</span></span>

- <span data-ttu-id="58c46-136">수시로 일어나 휴식을 취하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-136">Get up and take a break periodically.</span></span> <span data-ttu-id="58c46-137">걷거나 스트레칭하고 차를 한 잔 마시세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-137">Go for a walk, stretch, make yourself a cup of tea.</span></span>

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a><span data-ttu-id="58c46-138">알려진 문제: 비즈니스용 Skype 또는 Teams 회의 ID에 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="58c46-138">Known issue: Dialing into Skype for Business or Teams conference IDs</span></span>

<span data-ttu-id="58c46-139">다음은 2020년 2월 7일 메시지 센터 게시물(MC203397)에 대한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-139">The following is a summary of a Feb 7, 2020 Message center post (MC203397):</span></span>

<span data-ttu-id="58c46-140">Microsoft는 중국 지역의 일부 사용자가 비즈니스용 Skype 또는 Teams 회의 ID로 전화를 거는 데 문제가 있음을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-140">Microsoft is aware that some users in the China region are experiencing issues dialing into Skype for Business or Teams conference IDs.</span></span> <span data-ttu-id="58c46-141">대부분의 경우 이러한 문제는 당사가 제어하는 시스템의 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-141">In most cases, these problems are external to systems under our control.</span></span> <span data-ttu-id="58c46-142">종종 로컬 모바일 및 전화 통신 사업자에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-142">Often, the issue is with local mobile and telephony carriers.</span></span> 

<span data-ttu-id="58c46-143">오디오 회의를 하는 데 문제가 있는 경우 다음을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-143">We recommend the following if you're having audio conferencing problems:</span></span>

- <span data-ttu-id="58c46-144">호출자 또는 모임 이끌이에게 PSTN 또는 휴대폰 번호로 전화하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-144">Ask the caller or meeting organizer to call your PSTN or mobile number</span></span>
- <span data-ttu-id="58c46-145">VoIP를 사용하여 데스크톱 또는 모바일 클라이언트에서 통화 또는 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="58c46-145">Join the call or meeting from the desktop or mobile clients, using VoIP</span></span>

<span data-ttu-id="58c46-146">지원 티켓을 기록해야 하는 경우 다음을 포함하세요.</span><span class="sxs-lookup"><span data-stu-id="58c46-146">If you need to log a support ticket, please include the following:</span></span>
    
- <span data-ttu-id="58c46-147">정확한 통화 시간</span><span class="sxs-lookup"><span data-stu-id="58c46-147">Exact time of call</span></span>
- <span data-ttu-id="58c46-148">전화를 건 전화 회의 브리지 번호</span><span class="sxs-lookup"><span data-stu-id="58c46-148">Conference bridge number dialed</span></span>
- <span data-ttu-id="58c46-149">호출자 전화 네트워크</span><span class="sxs-lookup"><span data-stu-id="58c46-149">Caller phone network</span></span>
- <span data-ttu-id="58c46-150">호출자 전화 번호</span><span class="sxs-lookup"><span data-stu-id="58c46-150">Caller Phone Number</span></span>
