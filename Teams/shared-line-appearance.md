---
title: Microsoft Teams의 공유 선 모양
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
description: Microsoft Teams에서 오디오 회의 정보가 있는 전자 메일을 사용자에게 보내는 방법에 대해 자세히 배워야 합니다.
ms.openlocfilehash: 7750f85e959f332832c24b60b4efafd784218f61
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583837"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="75d5a-103">Microsoft Teams의 공유 선 모양</span><span class="sxs-lookup"><span data-stu-id="75d5a-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="75d5a-104">공유 줄 모양은 사용자가 대리인을 선택해 대신 전화를 걸거나 처리할 수 있는 위임 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="75d5a-105">이 기능은 사용자의 통화를 정기적으로 처리하는 관리 도우미가 있는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-105">This feature is helpful if a user has an administrative assistant who regularly handles the user's calls.</span></span> <span data-ttu-id="75d5a-106">공유 줄 모양의 컨텍스트에서 관리자는 대리인을 대신하여 전화를 걸거나 받을 수 있는 권한을 위임하는 사람으로, 대리인은 다른 사람을 대신하여 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75d5a-107">이 기능은 Teams 전용 배포 모드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="75d5a-108">Teams 배포 모드에 대한 자세한 내용은 Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 연동성 [이해를 참조하세요.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="75d5a-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="75d5a-109">라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="75d5a-109">License required</span></span>

<span data-ttu-id="75d5a-110">사용자는 PSTN 연결(호출 계획 라이선스 또는 Direct Routing OnlineVoiceRoutingPolicy)이 있는 전화 시스템이 대리인이 되거나 위임이 설정되어 다른 사용자가 대신 전화를 걸거나 받을 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-110">A user must be have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy) to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="75d5a-111">관리자와 대리인 모두 PSTN 연결(호출 계획 라이선스 또는 직접 라우팅 OnlineVoiceRoutingPolicy)이 있는 전화 시스템이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-111">Both managers and delegates need to have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy).</span></span> <span data-ttu-id="75d5a-112">공유 선 환경은 위임의 일부로 전화 시스템에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-112">The shared line experience is part of delegation and is included with Phone System.</span></span> <span data-ttu-id="75d5a-113">라이선스 모델에 대한 자세한 내용은 Microsoft Teams 서비스 [설명을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="75d5a-113">For additional details on the licensing model, See [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="75d5a-114">위임 및 공유 줄 모양 구성</span><span class="sxs-lookup"><span data-stu-id="75d5a-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="75d5a-115">위임 및 공유 줄 모양은 사용자 기반 기능입니다. 구성할 관리자 설정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="75d5a-116">이 기능을 사용하는 방법에 대한 자세한 내용은 [대리인과 전화선 공유를 참조하세요.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="75d5a-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="75d5a-117">테넌트 관리자는 **TeamsCallingPolicy AllowDelegation** 설정을 통해 또는 Teams 관리 포털을 통해 위임이 작동하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="75d5a-118">테넌트 관리자는 Teams 관리 센터에서 사용자에 대한 위임 관계를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="75d5a-119">또한 최종 사용자는 Teams에서 직접 위임 관계를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="75d5a-120">테넌트 관리자 또는 사용자가 서로 구성을 차단할 수 없지만 Teams 관리 센터와 Teams 클라이언트는 두 위치 모두에서 이 관계를 정확하게 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="75d5a-121">테넌트 관리자가 사용자에 대한 위임(설정한 후)을 해제하면 잘못된 통화 라우팅을 방지하기 위해 Teams 관리 센터에서 해당 사용자에 대한 위임 관계를 정리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="75d5a-122">공유 선 모양 기능 가용성</span><span class="sxs-lookup"><span data-stu-id="75d5a-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="75d5a-123">공유 선 모양은 현재 다음 앱 및 장치에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="75d5a-124">기능</span><span class="sxs-lookup"><span data-stu-id="75d5a-124">Capability</span></span> | <span data-ttu-id="75d5a-125">Teams 데스크톱</span><span class="sxs-lookup"><span data-stu-id="75d5a-125">Teams Desktop</span></span> | <span data-ttu-id="75d5a-126">Teams Mac 앱</span><span class="sxs-lookup"><span data-stu-id="75d5a-126">Teams Mac App</span></span> | <span data-ttu-id="75d5a-127">Teams Web App(Edge)</span><span class="sxs-lookup"><span data-stu-id="75d5a-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="75d5a-128">Teams 모바일 iOS/Android 앱</span><span class="sxs-lookup"><span data-stu-id="75d5a-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="75d5a-129">Teams IP 전화</span><span class="sxs-lookup"><span data-stu-id="75d5a-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="75d5a-130">위임 설정</span><span class="sxs-lookup"><span data-stu-id="75d5a-130">Set up delegation</span></span> | <span data-ttu-id="75d5a-131">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-131">Yes</span></span> | <span data-ttu-id="75d5a-132">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-132">Yes</span></span> | <span data-ttu-id="75d5a-133">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-133">Yes</span></span> | <span data-ttu-id="75d5a-134">아니요</span><span class="sxs-lookup"><span data-stu-id="75d5a-134">No</span></span> | <span data-ttu-id="75d5a-135">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-135">Yes</span></span> |
| <span data-ttu-id="75d5a-136">다른 대신 전화 받기</span><span class="sxs-lookup"><span data-stu-id="75d5a-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="75d5a-137">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-137">Yes</span></span> | <span data-ttu-id="75d5a-138">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-138">Yes</span></span> | <span data-ttu-id="75d5a-139">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-139">Yes</span></span> | <span data-ttu-id="75d5a-140">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-140">Yes</span></span> | <span data-ttu-id="75d5a-141">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-141">Yes</span></span> |
| <span data-ttu-id="75d5a-142">다른 대신 전화 번호로 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="75d5a-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="75d5a-143">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-143">Yes</span></span> | <span data-ttu-id="75d5a-144">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-144">Yes</span></span> | <span data-ttu-id="75d5a-145">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-145">Yes</span></span> | <span data-ttu-id="75d5a-146">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-146">Yes</span></span> | <span data-ttu-id="75d5a-147">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-147">Yes</span></span> |
| <span data-ttu-id="75d5a-148">다른 사용자를 대신하여 Teams 사용자 호출</span><span class="sxs-lookup"><span data-stu-id="75d5a-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="75d5a-149">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-149">Yes</span></span> | <span data-ttu-id="75d5a-150">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-150">Yes</span></span> | <span data-ttu-id="75d5a-151">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-151">Yes</span></span> | <span data-ttu-id="75d5a-152">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-152">Yes</span></span> | <span data-ttu-id="75d5a-153">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-153">Yes</span></span> |
| <span data-ttu-id="75d5a-154">공유 줄의 관리자 보기 보기 보기</span><span class="sxs-lookup"><span data-stu-id="75d5a-154">See the admin view of shared lines</span></span> | <span data-ttu-id="75d5a-155">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-155">Yes</span></span> | <span data-ttu-id="75d5a-156">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-156">Yes</span></span> | <span data-ttu-id="75d5a-157">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-157">Yes</span></span> | <span data-ttu-id="75d5a-158">아니요</span><span class="sxs-lookup"><span data-stu-id="75d5a-158">No</span></span> | <span data-ttu-id="75d5a-159">아니요</span><span class="sxs-lookup"><span data-stu-id="75d5a-159">No</span></span> |
| <span data-ttu-id="75d5a-160">관리자의 통화 활동 관리자 보기 보기</span><span class="sxs-lookup"><span data-stu-id="75d5a-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="75d5a-161">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-161">Yes</span></span> | <span data-ttu-id="75d5a-162">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-162">Yes</span></span> | <span data-ttu-id="75d5a-163">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-163">Yes</span></span> | <span data-ttu-id="75d5a-164">아니요</span><span class="sxs-lookup"><span data-stu-id="75d5a-164">No</span></span> | <span data-ttu-id="75d5a-165">아니요</span><span class="sxs-lookup"><span data-stu-id="75d5a-165">No</span></span> |
| <span data-ttu-id="75d5a-166">대리인의 관리자 보기 보기</span><span class="sxs-lookup"><span data-stu-id="75d5a-166">See the manager view of delegates</span></span> | <span data-ttu-id="75d5a-167">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-167">Yes</span></span> | <span data-ttu-id="75d5a-168">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-168">Yes</span></span> | <span data-ttu-id="75d5a-169">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-169">Yes</span></span> | <span data-ttu-id="75d5a-170">아니요</span><span class="sxs-lookup"><span data-stu-id="75d5a-170">No</span></span> | <span data-ttu-id="75d5a-171">아니요</span><span class="sxs-lookup"><span data-stu-id="75d5a-171">No</span></span> |
| <span data-ttu-id="75d5a-172">관리자 또는 관리자는 보류하거나 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="75d5a-173">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-173">Yes</span></span> | <span data-ttu-id="75d5a-174">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-174">Yes</span></span> | <span data-ttu-id="75d5a-175">예</span><span class="sxs-lookup"><span data-stu-id="75d5a-175">Yes</span></span> | <span data-ttu-id="75d5a-176">아니요</span><span class="sxs-lookup"><span data-stu-id="75d5a-176">No</span></span> | <span data-ttu-id="75d5a-177">아니요</span><span class="sxs-lookup"><span data-stu-id="75d5a-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="75d5a-178">제한 사항</span><span class="sxs-lookup"><span data-stu-id="75d5a-178">Limitations</span></span>

<span data-ttu-id="75d5a-179">관리자는 최대 25명까지 대리인을 추가할 수 있으며 대리인은 최대 25명까지 관리자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="75d5a-180">테넌트에서 만들 수 있는 위임 관계의 수는 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="75d5a-181">위임자 및 대리인이 동일한 지리적 위치에 있지 않은 경우 발신자 ID가 위임된(대신) 호출의 다른 지리적 위치에서 표시될 수 있도록 하는 것은 PSTN 공급자의 의결입니다.</span><span class="sxs-lookup"><span data-stu-id="75d5a-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="75d5a-182">추가 정보</span><span class="sxs-lookup"><span data-stu-id="75d5a-182">More information</span></span>

[<span data-ttu-id="75d5a-183">대리인과 전화선 공유</span><span class="sxs-lookup"><span data-stu-id="75d5a-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
