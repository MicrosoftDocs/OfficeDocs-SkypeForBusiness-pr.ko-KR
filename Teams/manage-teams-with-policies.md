---
title: 정책으로 Teams 관리
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 368e71820100ba8cfccb28eef63864f47cd8ce85
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421303"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="3253d-102">정책으로 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="3253d-102">Manage Teams with policies</span></span>

<span data-ttu-id="3253d-103">정책은 Teams 관리의 중요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-103">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="3253d-104">이 문서를 사용하여 정책을 사용하여 조직에 혜택을 주는 방법을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-104">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="3253d-105">정책 사용</span><span class="sxs-lookup"><span data-stu-id="3253d-105">What you use policies for</span></span>

<span data-ttu-id="3253d-106">정책은 메시징, 모임 및 애플리케이션과 같은 다양한 영역에서 조직에서 많은 작업을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-106">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="3253d-107">사용자가 팀 채널에서 모임을 예약할 수 있도록 허용하고, 사용자가 보낸 메시지를 편집할 수 있도록 허용하고, 사용자가 Teams 앱 표시줄에 앱을 고정할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-107">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="3253d-108">정책을 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="3253d-108">How to assign policies</span></span>

<span data-ttu-id="3253d-109">조직에서 수행하려는 방식에 따라 여러 가지 방법으로 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-109">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="3253d-110">Teams 관리 센터에서 과제를 수행하고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-110">You can make and view assignments in the Teams admin center.</span></span>

![그룹 정책 할당 스크린샷.](media/group-policy-assignment.png)

<span data-ttu-id="3253d-112">정책 할당에 대한 자세한 내용은 여기를 [클릭하세요.](assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3253d-112">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="3253d-113">정책을 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="3253d-113">How to manage policies</span></span>

<span data-ttu-id="3253d-114">정책은 Microsoft Teams 관리 센터 또는 [PowerShell을 사용하여 관리됩니다.](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="3253d-114">Policies are managed with the Microsoft Teams admin center or [using PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span></span>

<span data-ttu-id="3253d-115">예를 들어 앱 설정 정책을 사용하면 사용자가 사용자 지정 앱을 업로드하고, 사용자를 대신하여 앱을 설치하고, Teams 앱 표시줄에 앱을 고정할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-115">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="3253d-116">이러한 정책은 Teams 관리 센터에 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-116">These policies are configured in the Teams admin center.</span></span>

![앱 설정 정책 스크린샷.](media/app-setup-policy.png)

<span data-ttu-id="3253d-118">또한 모임 정책을 사용하여 전사, 클라우드 녹음 및 IP 오디오/비디오와 같은 Teams 모임에서 오디오 및 비디오 설정을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-118">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![모임 정책 스크린샷.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="3253d-120">교육용 Teams</span><span class="sxs-lookup"><span data-stu-id="3253d-120">Teams for Education</span></span>

<span data-ttu-id="3253d-121">또한 교육용 [Teams 정책](easy-policy-setup-edu.md) 마법사를 사용하여 학습 환경에 대한 정책을 쉽게 설정하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-121">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![교육용 Teams 정책 마법사의 스크린샷.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="3253d-123">정책 유형</span><span class="sxs-lookup"><span data-stu-id="3253d-123">Types of policies</span></span>

<span data-ttu-id="3253d-124">Microsoft Teams에서 다음 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-124">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="3253d-125">정책 유형</span><span class="sxs-lookup"><span data-stu-id="3253d-125">Policy type</span></span> | <span data-ttu-id="3253d-126">설명</span><span class="sxs-lookup"><span data-stu-id="3253d-126">Description</span></span>
------------|------------
[<span data-ttu-id="3253d-127">정책 패키지</span><span class="sxs-lookup"><span data-stu-id="3253d-127">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="3253d-128">Microsoft Teams의 정책 패키지는 조직에서 비슷한 역할을 하는 사용자에게 할당할 수 있는 미리 정의된 정책 및 설정의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-128">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="3253d-129">모임 정책</span><span class="sxs-lookup"><span data-stu-id="3253d-129">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="3253d-130">모임 정책은 조직의 사용자가 예약한 모임에 대해 모임 참가자에게 사용할 수 있는 기능을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-130">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="3253d-131">모임 정책에는 다음 토픽이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-131">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="3253d-132">- 오디오 및 비디오 정책</span><span class="sxs-lookup"><span data-stu-id="3253d-132">- Audio and video policies</span></span><br> <span data-ttu-id="3253d-133">- 콘텐츠 및 화면 공유 정책</span><span class="sxs-lookup"><span data-stu-id="3253d-133">- Content and screen sharing policies</span></span><br> <span data-ttu-id="3253d-134">- 참가자, 게스트 및 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="3253d-134">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="3253d-135">- 일반 정책</span><span class="sxs-lookup"><span data-stu-id="3253d-135">- General policies</span></span>
[<span data-ttu-id="3253d-136">음성 및 통화 정책</span><span class="sxs-lookup"><span data-stu-id="3253d-136">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="3253d-137">음성 및 통화 정책은 긴급 통화, 통화 라우팅 및 발신자 ID와 같은 팀을 통해 이러한 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-137">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="3253d-138">앱 정책</span><span class="sxs-lookup"><span data-stu-id="3253d-138">App policies</span></span>](app-policies.md)| <span data-ttu-id="3253d-139">앱 정책은 Microsoft Teams의 애플리케이션을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-139">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="3253d-140">관리자는 사용자가 설치할 수 있는 앱을 허용하거나 차단하고, 사용자의 Teams 앱 표시줄에 애플리케이션을 고정하고, 사용자를 대신하여 애플리케이션을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-140">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="3253d-141">메시징 정책</span><span class="sxs-lookup"><span data-stu-id="3253d-141">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="3253d-142">메시징 정책은 채팅 및 채널 기능 가용성을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3253d-142">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3253d-143">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3253d-143">Related topics</span></span>

* [<span data-ttu-id="3253d-144">Microsoft Teams에서 피드백 정책 관리</span><span class="sxs-lookup"><span data-stu-id="3253d-144">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="3253d-145">Microsoft Teams에서 팀 정책 관리</span><span class="sxs-lookup"><span data-stu-id="3253d-145">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="3253d-146">Microsoft Teams에서 실시간 이벤트 설정</span><span class="sxs-lookup"><span data-stu-id="3253d-146">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="3253d-147">교육 정책 및 정책 패키지에 대한 팀</span><span class="sxs-lookup"><span data-stu-id="3253d-147">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)
