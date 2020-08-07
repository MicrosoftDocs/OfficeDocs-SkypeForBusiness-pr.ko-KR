---
title: Microsoft 팀의 공유 선 모양
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Microsoft 팀의 오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일을 보내는 방법에 대해 알아봅니다.
ms.openlocfilehash: 7750f85e959f332832c24b60b4efafd784218f61
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583837"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="47178-103">Microsoft 팀의 공유 선 모양</span><span class="sxs-lookup"><span data-stu-id="47178-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="47178-104">공유 선 모양은 사용자가 자신을 대신 하 여 통화에 응답 하거나 처리할 대리인을 선택할 수 있는 위임 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="47178-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="47178-105">이 기능은 사용자가 사용자의 통화를 정기적으로 처리 하는 관리 도우미가 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47178-105">This feature is helpful if a user has an administrative assistant who regularly handles the user's calls.</span></span> <span data-ttu-id="47178-106">공유 선 모양의 컨텍스트에서 관리자는 자신을 대신 하 여 전화를 걸거나 받을 대리인에 게 권한을 부여 하 고 대리인이 다른 사람을 대신 하 여 전화를 걸고 받을 수 있는 사람을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="47178-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47178-107">이 기능은 팀 전용 배포 모드 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47178-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="47178-108">팀 배포 모드에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47178-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="47178-109">라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="47178-109">License required</span></span>

<span data-ttu-id="47178-110">사용자에 게는 휴대폰 시스템 (통화 계획 라이선스 또는 다이렉트 라우팅 OnlineVoiceRoutingPolicy)이 대리인 이거나 위임을 설정 하 고 다른 사용자가 자신을 대신 하 여 전화를 걸거나 받을 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47178-110">A user must be have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy) to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="47178-111">관리자와 대리인 모두 PSTN 연결 (통화 계획 라이선스 또는 다이렉트 라우팅 OnlineVoiceRoutingPolicy)의 전화 시스템을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47178-111">Both managers and delegates need to have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy).</span></span> <span data-ttu-id="47178-112">공유 회선 환경은 위임의 일부 이며 전화 시스템에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47178-112">The shared line experience is part of delegation and is included with Phone System.</span></span> <span data-ttu-id="47178-113">라이선스 모델에 대 한 자세한 내용은 [Microsoft 팀 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47178-113">For additional details on the licensing model, See [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="47178-114">위임 및 공유 선 모양 구성</span><span class="sxs-lookup"><span data-stu-id="47178-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="47178-115">위임 및 공유 선 모양은 구성할 관리 설정이 없기 때문에 사용자 기반 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="47178-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="47178-116">이 기능을 사용 하는 방법에 대 한 자세한 내용은 [대리인과 전화 회선 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47178-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="47178-117">테 넌 트 관리자는이 기능을 사용 하기 위해 **Teamscallingpolicy AllowDelegation** 설정 또는 팀 관리 포털을 통해 위임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47178-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="47178-118">테 넌 트 관리자는 또한 팀 관리 센터에서 사용자에 대 한 위임 관계를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47178-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="47178-119">또한 최종 사용자는 팀에서 직접 위임 관계를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47178-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="47178-120">테 넌 트 관리자 또는 사용자는 서로에 대 한 구성을 차단할 수 없지만 팀 관리 센터 및 팀 클라이언트는이 관계를 두 위치에 정확 하 게 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47178-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="47178-121">테 넌 트 관리자가 사용자에 대 한 위임 기능을 해제 하면 (설정 된 후) 팀 관리 센터에서 해당 사용자에 대 한 위임 관계도 정리 하 여 잘못 된 통화 라우팅이 발생 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47178-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="47178-122">공유 선 모양 기능 가용성</span><span class="sxs-lookup"><span data-stu-id="47178-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="47178-123">현재 공유 선 모양은 다음 앱 및 장치에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47178-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="47178-124">기능</span><span class="sxs-lookup"><span data-stu-id="47178-124">Capability</span></span> | <span data-ttu-id="47178-125">팀 데스크톱</span><span class="sxs-lookup"><span data-stu-id="47178-125">Teams Desktop</span></span> | <span data-ttu-id="47178-126">팀 Mac 앱</span><span class="sxs-lookup"><span data-stu-id="47178-126">Teams Mac App</span></span> | <span data-ttu-id="47178-127">팀 웹 앱 (Edge)</span><span class="sxs-lookup"><span data-stu-id="47178-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="47178-128">팀 모바일 iOS/Android 앱</span><span class="sxs-lookup"><span data-stu-id="47178-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="47178-129">팀 IP 전화</span><span class="sxs-lookup"><span data-stu-id="47178-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="47178-130">대리인 설정</span><span class="sxs-lookup"><span data-stu-id="47178-130">Set up delegation</span></span> | <span data-ttu-id="47178-131">예</span><span class="sxs-lookup"><span data-stu-id="47178-131">Yes</span></span> | <span data-ttu-id="47178-132">예</span><span class="sxs-lookup"><span data-stu-id="47178-132">Yes</span></span> | <span data-ttu-id="47178-133">예</span><span class="sxs-lookup"><span data-stu-id="47178-133">Yes</span></span> | <span data-ttu-id="47178-134">아니요</span><span class="sxs-lookup"><span data-stu-id="47178-134">No</span></span> | <span data-ttu-id="47178-135">예</span><span class="sxs-lookup"><span data-stu-id="47178-135">Yes</span></span> |
| <span data-ttu-id="47178-136">다른 사람을 대신 하 여 전화 받기</span><span class="sxs-lookup"><span data-stu-id="47178-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="47178-137">예</span><span class="sxs-lookup"><span data-stu-id="47178-137">Yes</span></span> | <span data-ttu-id="47178-138">예</span><span class="sxs-lookup"><span data-stu-id="47178-138">Yes</span></span> | <span data-ttu-id="47178-139">예</span><span class="sxs-lookup"><span data-stu-id="47178-139">Yes</span></span> | <span data-ttu-id="47178-140">예</span><span class="sxs-lookup"><span data-stu-id="47178-140">Yes</span></span> | <span data-ttu-id="47178-141">예</span><span class="sxs-lookup"><span data-stu-id="47178-141">Yes</span></span> |
| <span data-ttu-id="47178-142">다른 사람을 대신 하 여 전화 번호 호출</span><span class="sxs-lookup"><span data-stu-id="47178-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="47178-143">예</span><span class="sxs-lookup"><span data-stu-id="47178-143">Yes</span></span> | <span data-ttu-id="47178-144">예</span><span class="sxs-lookup"><span data-stu-id="47178-144">Yes</span></span> | <span data-ttu-id="47178-145">예</span><span class="sxs-lookup"><span data-stu-id="47178-145">Yes</span></span> | <span data-ttu-id="47178-146">예</span><span class="sxs-lookup"><span data-stu-id="47178-146">Yes</span></span> | <span data-ttu-id="47178-147">예</span><span class="sxs-lookup"><span data-stu-id="47178-147">Yes</span></span> |
| <span data-ttu-id="47178-148">다른 사람을 대신 하 여 팀 사용자에 게 전화</span><span class="sxs-lookup"><span data-stu-id="47178-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="47178-149">예</span><span class="sxs-lookup"><span data-stu-id="47178-149">Yes</span></span> | <span data-ttu-id="47178-150">예</span><span class="sxs-lookup"><span data-stu-id="47178-150">Yes</span></span> | <span data-ttu-id="47178-151">예</span><span class="sxs-lookup"><span data-stu-id="47178-151">Yes</span></span> | <span data-ttu-id="47178-152">예</span><span class="sxs-lookup"><span data-stu-id="47178-152">Yes</span></span> | <span data-ttu-id="47178-153">예</span><span class="sxs-lookup"><span data-stu-id="47178-153">Yes</span></span> |
| <span data-ttu-id="47178-154">공유 된 회선의 관리 보기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47178-154">See the admin view of shared lines</span></span> | <span data-ttu-id="47178-155">예</span><span class="sxs-lookup"><span data-stu-id="47178-155">Yes</span></span> | <span data-ttu-id="47178-156">예</span><span class="sxs-lookup"><span data-stu-id="47178-156">Yes</span></span> | <span data-ttu-id="47178-157">예</span><span class="sxs-lookup"><span data-stu-id="47178-157">Yes</span></span> | <span data-ttu-id="47178-158">아니요</span><span class="sxs-lookup"><span data-stu-id="47178-158">No</span></span> | <span data-ttu-id="47178-159">아니요</span><span class="sxs-lookup"><span data-stu-id="47178-159">No</span></span> |
| <span data-ttu-id="47178-160">관리자의 통화 활동에 대 한 관리 보기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47178-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="47178-161">예</span><span class="sxs-lookup"><span data-stu-id="47178-161">Yes</span></span> | <span data-ttu-id="47178-162">예</span><span class="sxs-lookup"><span data-stu-id="47178-162">Yes</span></span> | <span data-ttu-id="47178-163">예</span><span class="sxs-lookup"><span data-stu-id="47178-163">Yes</span></span> | <span data-ttu-id="47178-164">아니요</span><span class="sxs-lookup"><span data-stu-id="47178-164">No</span></span> | <span data-ttu-id="47178-165">아니요</span><span class="sxs-lookup"><span data-stu-id="47178-165">No</span></span> |
| <span data-ttu-id="47178-166">대리인의 관리자 보기 참조</span><span class="sxs-lookup"><span data-stu-id="47178-166">See the manager view of delegates</span></span> | <span data-ttu-id="47178-167">예</span><span class="sxs-lookup"><span data-stu-id="47178-167">Yes</span></span> | <span data-ttu-id="47178-168">예</span><span class="sxs-lookup"><span data-stu-id="47178-168">Yes</span></span> | <span data-ttu-id="47178-169">예</span><span class="sxs-lookup"><span data-stu-id="47178-169">Yes</span></span> | <span data-ttu-id="47178-170">아니요</span><span class="sxs-lookup"><span data-stu-id="47178-170">No</span></span> | <span data-ttu-id="47178-171">아니요</span><span class="sxs-lookup"><span data-stu-id="47178-171">No</span></span> |
| <span data-ttu-id="47178-172">관리자 또는 관리자가 보류 또는 다시 시작 가능</span><span class="sxs-lookup"><span data-stu-id="47178-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="47178-173">예</span><span class="sxs-lookup"><span data-stu-id="47178-173">Yes</span></span> | <span data-ttu-id="47178-174">예</span><span class="sxs-lookup"><span data-stu-id="47178-174">Yes</span></span> | <span data-ttu-id="47178-175">예</span><span class="sxs-lookup"><span data-stu-id="47178-175">Yes</span></span> | <span data-ttu-id="47178-176">아니요</span><span class="sxs-lookup"><span data-stu-id="47178-176">No</span></span> | <span data-ttu-id="47178-177">아니요</span><span class="sxs-lookup"><span data-stu-id="47178-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="47178-178">따릅니다</span><span class="sxs-lookup"><span data-stu-id="47178-178">Limitations</span></span>

<span data-ttu-id="47178-179">관리자는 대리인을 최대 25 개까지 추가할 수 있으며 대리인은 최대 25 명의 관리자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47178-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="47178-180">테 넌 트에서 만들 수 있는 위임 관계의 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47178-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="47178-181">위임자와 대리인이 같은 지리적 위치에 있지 않은 경우 발신자 ID가 위임 됨 (대신) 통화에 대해 다른 지리적 위치에서 표시 되도록 하는 것은 PSTN 공급자에 게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47178-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="47178-182">추가 정보</span><span class="sxs-lookup"><span data-stu-id="47178-182">More information</span></span>

[<span data-ttu-id="47178-183">대리인과 전화 라인 공유</span><span class="sxs-lookup"><span data-stu-id="47178-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
