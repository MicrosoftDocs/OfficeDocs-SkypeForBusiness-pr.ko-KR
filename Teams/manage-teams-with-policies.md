---
title: 정책으로 Teams 관리
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Teams 정책에 대해 숙지합니다.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f06e9aa87cc0c1af758bf0c8c9abad6641debbd
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460498"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="f2aec-103">정책으로 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="f2aec-103">Manage Teams with policies</span></span>

<span data-ttu-id="f2aec-104">정책은 Teams 관리의 중요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="f2aec-105">이 문서를 사용하여 정책을 사용하여 조직에 혜택을 주는 방법을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="f2aec-106">정책 사용</span><span class="sxs-lookup"><span data-stu-id="f2aec-106">What you use policies for</span></span>

<span data-ttu-id="f2aec-107">정책은 메시징, 모임 및 애플리케이션과 같은 다양한 영역에서 조직에서 많은 작업을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="f2aec-108">사용자가 팀 채널에서 모임을 예약할 수 있도록 허용하고, 사용자가 보낸 메시지를 편집할 수 있도록 허용하고, 사용자가 Teams 앱 표시줄에 앱을 고정할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="f2aec-109">정책을 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="f2aec-109">How to assign policies</span></span>

<span data-ttu-id="f2aec-110">조직에서 수행하려는 방식에 따라 여러 가지 방법으로 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="f2aec-111">Teams 관리 센터에서 과제를 수행하고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-111">You can make and view assignments in the Teams admin center.</span></span>

![그룹 정책 할당 스크린샷.](media/group-policy-assignment.png)

<span data-ttu-id="f2aec-113">정책 할당에 대한 자세한 내용은 여기를 [클릭하세요.](assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f2aec-113">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="f2aec-114">정책을 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="f2aec-114">How to manage policies</span></span>

<span data-ttu-id="f2aec-115">정책은 Microsoft Teams 관리 센터 또는 [PowerShell을 사용하여 관리됩니다.](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="f2aec-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span></span>

<span data-ttu-id="f2aec-116">예를 들어 앱 설정 정책을 사용하면 사용자가 사용자 지정 앱을 업로드하고, 사용자를 대신하여 앱을 설치하고, Teams 앱 표시줄에 앱을 고정할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="f2aec-117">이러한 정책은 Teams 관리 센터에 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-117">These policies are configured in the Teams admin center.</span></span>

![앱 설정 정책 스크린샷.](media/app-setup-policy.png)

<span data-ttu-id="f2aec-119">또한 모임 정책을 사용하여 전사, 클라우드 녹음 및 IP 오디오/비디오와 같은 Teams 모임에서 오디오 및 비디오 설정을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![모임 정책 스크린샷.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="f2aec-121">교육용 Teams</span><span class="sxs-lookup"><span data-stu-id="f2aec-121">Teams for Education</span></span>

<span data-ttu-id="f2aec-122">또한 교육용 [Teams 정책](easy-policy-setup-edu.md) 마법사를 사용하여 학습 환경에 대한 정책을 쉽게 설정하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![교육용 Teams 정책 마법사의 스크린샷.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="f2aec-124">정책 유형</span><span class="sxs-lookup"><span data-stu-id="f2aec-124">Types of policies</span></span>

<span data-ttu-id="f2aec-125">Microsoft Teams에서 다음 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="f2aec-126">정책 유형</span><span class="sxs-lookup"><span data-stu-id="f2aec-126">Policy type</span></span> | <span data-ttu-id="f2aec-127">설명</span><span class="sxs-lookup"><span data-stu-id="f2aec-127">Description</span></span>
------------|------------
[<span data-ttu-id="f2aec-128">정책 패키지</span><span class="sxs-lookup"><span data-stu-id="f2aec-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="f2aec-129">Microsoft Teams의 정책 패키지는 조직에서 비슷한 역할을 하는 사용자에게 할당할 수 있는 미리 정의된 정책 및 설정의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="f2aec-130">모임 정책</span><span class="sxs-lookup"><span data-stu-id="f2aec-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="f2aec-131">모임 정책은 조직의 사용자가 예약한 모임에 대해 모임 참가자에게 사용할 수 있는 기능을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="f2aec-132">모임 정책에는 다음 토픽이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="f2aec-133">- 오디오 및 비디오 정책</span><span class="sxs-lookup"><span data-stu-id="f2aec-133">- Audio and video policies</span></span><br> <span data-ttu-id="f2aec-134">- 콘텐츠 및 화면 공유 정책</span><span class="sxs-lookup"><span data-stu-id="f2aec-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="f2aec-135">- 참가자, 게스트 및 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="f2aec-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="f2aec-136">- 일반 정책</span><span class="sxs-lookup"><span data-stu-id="f2aec-136">- General policies</span></span>
[<span data-ttu-id="f2aec-137">음성 및 통화 정책</span><span class="sxs-lookup"><span data-stu-id="f2aec-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="f2aec-138">음성 및 통화 정책은 긴급 통화, 통화 라우팅 및 발신자 ID와 같은 팀을 통해 이러한 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="f2aec-139">앱 정책</span><span class="sxs-lookup"><span data-stu-id="f2aec-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="f2aec-140">앱 정책은 Microsoft Teams의 애플리케이션을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="f2aec-141">관리자는 사용자가 설치할 수 있는 앱을 허용하거나 차단하고, 사용자의 Teams 앱 표시줄에 애플리케이션을 고정하고, 사용자를 대신하여 애플리케이션을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="f2aec-142">메시징 정책</span><span class="sxs-lookup"><span data-stu-id="f2aec-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="f2aec-143">메시징 정책은 채팅 및 채널 기능 가용성을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f2aec-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2aec-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f2aec-144">Related topics</span></span>

* [<span data-ttu-id="f2aec-145">Microsoft Teams에서 피드백 정책 관리</span><span class="sxs-lookup"><span data-stu-id="f2aec-145">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="f2aec-146">Microsoft Teams에서 팀 정책 관리</span><span class="sxs-lookup"><span data-stu-id="f2aec-146">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="f2aec-147">활동 로그에서 정책 할당 보기</span><span class="sxs-lookup"><span data-stu-id="f2aec-147">View policy assignments in the Activity Log</span></span>](activity-log.md)
* [<span data-ttu-id="f2aec-148">Microsoft Teams에서 실시간 이벤트 설정</span><span class="sxs-lookup"><span data-stu-id="f2aec-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="f2aec-149">교육 정책 및 정책 패키지에 대한 팀</span><span class="sxs-lookup"><span data-stu-id="f2aec-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)
