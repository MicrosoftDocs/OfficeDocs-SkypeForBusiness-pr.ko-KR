---
title: EDU용 Microsoft Teams 낮은 대역폭 지침
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: 낮은 대역폭과 관련된 모임 및 비디오 문제를 해결하는 데 유용한 EDU용 Microsoft Teams 문서입니다. 부모, 교사 또는 IT 관리자는 Teams 사용 환경을 개선할 수 있는 방안이 있습니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f34ea2e65906c648081a019d6acf8a3f8a5cd5
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43034078"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="d3f78-104">EDU용 Teams의 낮은 대역폭 상황을 위한 지원</span><span class="sxs-lookup"><span data-stu-id="d3f78-104">Help for low bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="d3f78-105">Microsoft Teams를 사용하면서 성능에 영향을 줄 수 있는 많은 네트워크 요소를 만나게 되며, 낮은 대역폭은 사용자가 완전히 제어할 수 없는 상황 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-105">There are a lot of network elements when it comes to working with Microsoft Teams that can affect performance, and low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="d3f78-106">다음과 같은 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-106">Consider the following:</span></span>

- <span data-ttu-id="d3f78-107">학교용 저속 인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="d3f78-107">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="d3f78-108">한 명 이상의 학생을 위한 저속 인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="d3f78-108">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="d3f78-109">해당 영역의 네트워크 사용률로 인해 대역폭이 낮게 유지되는 하루 중 시간</span><span class="sxs-lookup"><span data-stu-id="d3f78-109">Times of the day when there is low bandwidth due to network usage in an area.</span></span>
- <span data-ttu-id="d3f78-110">학교 및 학생 입장에서 지역적인 것은 아니지만 성능에 영향을 미칠 수 있는 중단 상황으로 인한 낮은 대역폭 기간</span><span class="sxs-lookup"><span data-stu-id="d3f78-110">Low bandwidth periods due to outages local to neither the school nor to students, but which impact performance nonetheless.</span></span>
- <span data-ttu-id="d3f78-111">낮은 대역폭 문제로 오인되는 대역폭 이외 문제(예: 하드웨어 문제)</span><span class="sxs-lookup"><span data-stu-id="d3f78-111">Non-bandwidth issues (for example, issues with hardware) that masquerade as low bandwidth issues.</span></span>

<span data-ttu-id="d3f78-112">이 문서에서는 낮은 대역폭 문제가 발생하는 경우에는 다양한 Teams 작업에 권장되는 모범 사례를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-112">This article will give you best practices to follow for a variety of Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3f78-113">낮은 대역폭 문제 외에, 리소스 문제가 디바이스에 있을 수 있으므로 [Microsoft Teams에서 메모리를 사용하는 방법](teams-memory-usage-perf.md)에 대한 정보도 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-113">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="d3f78-114">Microsoft Teams에 대한 네트워크 지침을 원할 경우 [Microsoft Teams에 대한 조직의 네트워크 준비](prepare-network.md)를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="d3f78-114">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a><span data-ttu-id="d3f78-115">IT 관리자의 낮은 대역폭 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d3f78-115">Resolving low bandwidth issues for ITAdmins</span></span>

<span data-ttu-id="d3f78-116">유념해야 할 중요한 사항은 IT 관리자 입장에서 널리 확장되어 있는 낮은 대역폭을 위한 해결 방안이 있으며 이를 통해 문제를 빠르게 해결할 수 있지만, 일부 문제는 교사나 학생/학부모 수준에서 좀 더 신중히 해결해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-116">The important thing to remember, as an ITAdmin, is that while you have solutions for low bandwidth issues that are wide-spread that will resolve problems quickly, this should be considered carefully, as some issues may be able to resolved with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="d3f78-117">간단히 말해서, 방대한 학생 그룹을 대상으로 낮은 대역폭 문제가 발생하는 경우 IT 관리자가 조치를 취해야 하며, 학생/교사 수준에서 취하는 조치는 도움이 되지 않을 수도 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-117">In short, if the low bandwidth issue occurs for a wide group of students, taking action as an ITAdmin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="d3f78-118">투자 수익을 거두는 데 시간이 오래 걸리는 경우 [QoE(체감 품질) 검토 가이드](quality-of-experience-review-guide.md)(EDU에 국한된 내용은 아니지만 유용할 수 있음)를 읽어보면 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-118">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="d3f78-119">이를 통해 경험 있는 IT 관리자는 교사와 학생을 위한 환경을 심도 깊이 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-119">This will allow experienced ITAdmins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="d3f78-120">모임 및 비디오</span><span class="sxs-lookup"><span data-stu-id="d3f78-120">Meetings and video</span></span>

<span data-ttu-id="d3f78-121">낮은 대역폭 문제를 해결해야 하는 기본적인 측면은 모임이며, 특히 화상 모임에서 이러한 문제가 있는지 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-121">A primary focus for low bandwidth issues are meetings, and specifically video in meetings.</span></span> <span data-ttu-id="d3f78-122">Microsoft는 교육 관련 설정에서 최고의 모임 환경을 구축하는 것과 관련해서 학생 또는 교사가 보고하는 문제를 처리할 때 IT 관리자가 고려해야 하는 다음과 같은 작업을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-122">We have some of the actions below that an ITAdmin should consider when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="d3f78-123">모임 정책</span><span class="sxs-lookup"><span data-stu-id="d3f78-123">Meeting policies</span></span>

<span data-ttu-id="d3f78-124">모임과 관련해서 낮은 대역폭이 가장 우려되는 영역 중 하나는 비디오와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-124">In regards to meetings, one of the most concerning areas for low bandwidth situations has to do with videos.</span></span> <span data-ttu-id="d3f78-125">다행히 Teams에서 IT 관리자는 검색된 대역폭으로 자동으로 확장할 수 있을 뿐만 아니라, 이끌이 및/또는 사용자별 수준에서 정책 옵션을 설정하여 특정 시간에 사용해야 하는 대역폭 측면에서 최고의 환경을 모든 사용자에게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-125">Fortunately, in addition to Teams being able to scale to detected bandwidth automatically, you as an ITAdmin have policy options you can set at the per-organizer and/or per-user level to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="d3f78-126">정책에 따라 설정할 수 있는 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-126">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="d3f78-127">누구도 사용할 수 없게 비디오를 모두 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="d3f78-127">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="d3f78-128">미디어 비트 전송률(사용자별로 설정)</span><span class="sxs-lookup"><span data-stu-id="d3f78-128">Media bit rate (this is set per-user).</span></span>

<span data-ttu-id="d3f78-129">옵션에 대해 자세히 알아보고 모임 및 비디오와 관련해서 설정해야 하는 정책에 대한 자세한 내용을 보려면 [Teams의 모임 정책 설정: 오디오 및 비디오](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video)에서 자세한 단계별 정보를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d3f78-129">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video) for detailed walk-through information.</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="d3f78-130">화면 공유 정책</span><span class="sxs-lookup"><span data-stu-id="d3f78-130">Screen sharing policies</span></span>

<span data-ttu-id="d3f78-131">경우에 따라 교사는 담당 과목에 관련된 응용 프로그램으로 공유를 제한해야 하는 경우 학생들과 전체 화면을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-131">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="d3f78-132">교사가 개별적으로 해당 설정을 선택하는 것보다 이렇게 하는 것이 더 바람직한 경우 정책을 통해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-132">This can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="d3f78-133">정책 설정을 통해 화면 공유를 제한하는 경우 수행할 수 있는 작업에 대한 자세한 내용은 [Teams의 모임 정책 설정: 화면 공유](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3f78-133">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Screen sharing](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="d3f78-134">모임에 대한 전화 접속 연결 번호</span><span class="sxs-lookup"><span data-stu-id="d3f78-134">Dial-in number for meetings</span></span>

<span data-ttu-id="d3f78-135">일부 학생의 경우 일부 교실 세션에 전화 접속을 시도하는 것이 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-135">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="d3f78-136">Teams 모임을 위한 전화 접속 번호를 제공할 수 있으므로 문제가 있는 학생은 화상 모임에 참석하는 대신 전화로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-136">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="d3f78-137">이에 대한 자세한 내용은 [Microsoft Teams에서 초대에 전화 번호를 포함하도록 설정](set-the-phone-numbers-included-on-invites-in-teams.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="d3f78-137">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="d3f78-138">교사 대상의 낮은 대역폭 시나리오</span><span class="sxs-lookup"><span data-stu-id="d3f78-138">Low bandwidth scenarios as an educator</span></span>

<span data-ttu-id="d3f78-139">교사는 낮은 대역폭 문제를 해결하기 위해 조치를 취해야 한다고 생각할 수 있으며 다음과 같은 경우 IT 관리자가 이러한 조치를 위하는 것이 적절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-139">Educators should feel empowered to take steps to resolve low bandwidth issues, and may be a superior choice to ITAdmin action in the following situations:</span></span>

- <span data-ttu-id="d3f78-140">문제가 간헐적이거나 비교적 일시적으로 나타나는 경우</span><span class="sxs-lookup"><span data-stu-id="d3f78-140">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="d3f78-141">문제가 예상되는 특정 시간이 있거나 낮은 대역폭 기간을 어느 정도 예측할 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="d3f78-141">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="d3f78-142">이러한 경우에는 몇 가지 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-142">In these situations, you can take some actions.</span></span>

<span data-ttu-id="d3f78-143">자세한 내용은 [대역폭이 낮은 경우 수업에 Teams 사용](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3f78-143">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="d3f78-144">부모 또는 학생 대상의 낮은 대역폭 시나리오</span><span class="sxs-lookup"><span data-stu-id="d3f78-144">Low bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="d3f78-145">경우에 따라 대역폭 문제가 학생 측면에서 발생할 수 있는 경우(예: 다수의 학생은 문제 없이 비디오를 볼 수 있지만, 소수의 학생에게는 어려움이 있는 경우) 교사와 사전에 논의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-145">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="d3f78-146">많은 부모들이 이러한 문제를 해결할 수 있을 것으로 예상하는 것은 타당하지 않으며, 낮은 대역폭 문제를 학생 또는 부모는 해결하지 못할 수 있습니다(가정에서 높은 대역폭에 액세스할 수 없거나, 인접한 영역에 많은 사람들이 대역폭을 사용하거나 수행할 수 있는 작업에 영향을 미치거나, 인터넷이 불안정할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="d3f78-146">It's not reasonable to expect many parents to be able to troubleshoot these issues, and low bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have a lot of people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="d3f78-147">[대역폭이 낮은 경우 수업에 Teams 사용](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) 문서에서 부모와 학생을 위한 지침을 제공하고 있으며, 문제가 있는 경우 이러한 권장 사항을 검토하고 시도해볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f78-147">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>
