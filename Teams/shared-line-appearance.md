---
title: 공유 줄 모양의 Microsoft Teams
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
description: 오디오 회의 정보를 통해 사용자에게 전자 메일을 보내는 방법에 대해 Microsoft Teams.
ms.openlocfilehash: b6a9e8dfba0db32eb4f02f1f4d4e9ea5f2c4be3e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117046"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="5a3db-103">공유 줄 모양의 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a3db-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="5a3db-104">공유 줄 모양은 사용자가 대신 호출에 응답하거나 처리할 대리인을 선택할 수 있는 위임 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="5a3db-105">이 기능은 사용자의 호출을 정기적으로 처리하는 관리 도우미가 있는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-105">This feature is helpful if a user has an administrative assistant who regularly handles the user's calls.</span></span> <span data-ttu-id="5a3db-106">공유 줄 모양의 컨텍스트에서 관리자는 대리인을 대신하여 전화를 걸거나 받을 수 있도록 권한을 위임하는 사람으로, 대리인은 다른 사람을 대신하여 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a3db-107">이 기능은 배포 Teams 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="5a3db-108">배포 모드에 대한 Teams 자세한 내용은 Microsoft Teams 및 상호 비즈니스용 Skype 이해를 [참조합니다.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="5a3db-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="5a3db-109">라이선스 필수</span><span class="sxs-lookup"><span data-stu-id="5a3db-109">License required</span></span>

<span data-ttu-id="5a3db-110">사용자는 PSTN 연결(전화 시스템 계획 라이선스 또는 직접 라우팅 OnlineVoiceRoutingPolicy)을 사용하여 위임 또는 위임 설정 및 다른 사용자가 대신 전화를 걸거나 받을 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-110">A user must be have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy) to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="5a3db-111">관리자와 대리인 모두 PSTN 연결(전화 시스템 계획 라이선스 또는 Direct 라우팅 OnlineVoiceRoutingPolicy)을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-111">Both managers and delegates need to have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy).</span></span> <span data-ttu-id="5a3db-112">공유 줄 환경은 위임의 일부로 전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="5a3db-112">The shared line experience is part of delegation and is included with Phone System.</span></span> <span data-ttu-id="5a3db-113">라이선스 모델에 대한 자세한 내용은 서비스 [Microsoft Teams 참조하세요.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="5a3db-113">For additional details on the licensing model, See [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="5a3db-114">위임 및 공유 줄 모양 구성</span><span class="sxs-lookup"><span data-stu-id="5a3db-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="5a3db-115">위임 및 공유 줄 모양은 사용자 기반 기능입니다. 구성할 관리자 설정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="5a3db-116">이 기능을 사용하는 방법에 대한 자세한 내용은 대리인과 전화선 [공유를 참조하세요.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="5a3db-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="5a3db-117">테넌트 관리자는 **TeamsCallingPolicy AllowDelegation** 설정을 통해 위임하거나 이 기능을 사용할 Teams 관리 포털을 통해 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="5a3db-118">테넌트 관리자는 관리 센터의 사용자에 대한 위임 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="5a3db-119">또한 최종 사용자는 해당 위임 관계를 직접 구성할 Teams.</span><span class="sxs-lookup"><span data-stu-id="5a3db-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="5a3db-120">테넌트 관리자 또는 사용자가 서로 구성을 차단할 수 없지만 Teams 관리 센터 및 Teams 클라이언트는 두 위치 모두에서 이 관계를 정확하게 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5a3db-121">테넌트 관리자가 사용자에 대한 위임(설정한 후)을 해제하면 잘못된 호출 라우팅을 방지하기 위해 Teams 관리 센터에서 해당 사용자에 대한 위임 관계를 정리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="5a3db-122">공유 줄 모양 기능 가용성</span><span class="sxs-lookup"><span data-stu-id="5a3db-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="5a3db-123">공유 줄 모양은 현재 다음 앱 및 장치에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="5a3db-124">기능</span><span class="sxs-lookup"><span data-stu-id="5a3db-124">Capability</span></span> | <span data-ttu-id="5a3db-125">Teams 데스크톱</span><span class="sxs-lookup"><span data-stu-id="5a3db-125">Teams Desktop</span></span> | <span data-ttu-id="5a3db-126">Teams Mac 앱</span><span class="sxs-lookup"><span data-stu-id="5a3db-126">Teams Mac App</span></span> | <span data-ttu-id="5a3db-127">Teams 웹앱(Edge)</span><span class="sxs-lookup"><span data-stu-id="5a3db-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="5a3db-128">Teams iOS/Android 앱</span><span class="sxs-lookup"><span data-stu-id="5a3db-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="5a3db-129">Teams IP 전화</span><span class="sxs-lookup"><span data-stu-id="5a3db-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="5a3db-130">위임 설정</span><span class="sxs-lookup"><span data-stu-id="5a3db-130">Set up delegation</span></span> | <span data-ttu-id="5a3db-131">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-131">Yes</span></span> | <span data-ttu-id="5a3db-132">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-132">Yes</span></span> | <span data-ttu-id="5a3db-133">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-133">Yes</span></span> | <span data-ttu-id="5a3db-134">아니요</span><span class="sxs-lookup"><span data-stu-id="5a3db-134">No</span></span> | <span data-ttu-id="5a3db-135">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-135">Yes</span></span> |
| <span data-ttu-id="5a3db-136">다른 대신 통화 받기</span><span class="sxs-lookup"><span data-stu-id="5a3db-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="5a3db-137">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-137">Yes</span></span> | <span data-ttu-id="5a3db-138">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-138">Yes</span></span> | <span data-ttu-id="5a3db-139">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-139">Yes</span></span> | <span data-ttu-id="5a3db-140">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-140">Yes</span></span> | <span data-ttu-id="5a3db-141">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-141">Yes</span></span> |
| <span data-ttu-id="5a3db-142">다른 대신 전화 번호로 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="5a3db-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="5a3db-143">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-143">Yes</span></span> | <span data-ttu-id="5a3db-144">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-144">Yes</span></span> | <span data-ttu-id="5a3db-145">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-145">Yes</span></span> | <span data-ttu-id="5a3db-146">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-146">Yes</span></span> | <span data-ttu-id="5a3db-147">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-147">Yes</span></span> |
| <span data-ttu-id="5a3db-148">다른 사용자를 대신하여 Teams 사용자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="5a3db-149">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-149">Yes</span></span> | <span data-ttu-id="5a3db-150">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-150">Yes</span></span> | <span data-ttu-id="5a3db-151">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-151">Yes</span></span> | <span data-ttu-id="5a3db-152">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-152">Yes</span></span> | <span data-ttu-id="5a3db-153">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-153">Yes</span></span> |
| <span data-ttu-id="5a3db-154">공유 줄의 관리자 보기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a3db-154">See the admin view of shared lines</span></span> | <span data-ttu-id="5a3db-155">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-155">Yes</span></span> | <span data-ttu-id="5a3db-156">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-156">Yes</span></span> | <span data-ttu-id="5a3db-157">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-157">Yes</span></span> | <span data-ttu-id="5a3db-158">아니요</span><span class="sxs-lookup"><span data-stu-id="5a3db-158">No</span></span> | <span data-ttu-id="5a3db-159">아니요</span><span class="sxs-lookup"><span data-stu-id="5a3db-159">No</span></span> |
| <span data-ttu-id="5a3db-160">관리자의 통화 활동의 관리자 보기 보기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a3db-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="5a3db-161">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-161">Yes</span></span> | <span data-ttu-id="5a3db-162">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-162">Yes</span></span> | <span data-ttu-id="5a3db-163">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-163">Yes</span></span> | <span data-ttu-id="5a3db-164">아니요</span><span class="sxs-lookup"><span data-stu-id="5a3db-164">No</span></span> | <span data-ttu-id="5a3db-165">아니요</span><span class="sxs-lookup"><span data-stu-id="5a3db-165">No</span></span> |
| <span data-ttu-id="5a3db-166">대리인의 관리자 보기</span><span class="sxs-lookup"><span data-stu-id="5a3db-166">See the manager view of delegates</span></span> | <span data-ttu-id="5a3db-167">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-167">Yes</span></span> | <span data-ttu-id="5a3db-168">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-168">Yes</span></span> | <span data-ttu-id="5a3db-169">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-169">Yes</span></span> | <span data-ttu-id="5a3db-170">아니요</span><span class="sxs-lookup"><span data-stu-id="5a3db-170">No</span></span> | <span data-ttu-id="5a3db-171">아니요</span><span class="sxs-lookup"><span data-stu-id="5a3db-171">No</span></span> |
| <span data-ttu-id="5a3db-172">관리자 또는 관리자는 보류 또는 재개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="5a3db-173">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-173">Yes</span></span> | <span data-ttu-id="5a3db-174">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-174">Yes</span></span> | <span data-ttu-id="5a3db-175">예</span><span class="sxs-lookup"><span data-stu-id="5a3db-175">Yes</span></span> | <span data-ttu-id="5a3db-176">아니요</span><span class="sxs-lookup"><span data-stu-id="5a3db-176">No</span></span> | <span data-ttu-id="5a3db-177">아니요</span><span class="sxs-lookup"><span data-stu-id="5a3db-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="5a3db-178">제한 사항</span><span class="sxs-lookup"><span data-stu-id="5a3db-178">Limitations</span></span>

<span data-ttu-id="5a3db-179">관리자는 최대 25명까지 대리인을 추가할 수 있으며 대리인은 최대 25명의 관리자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="5a3db-180">테넌트에서 만들 수 있는 위임 관계 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="5a3db-181">위임자 및 대리인이 동일한 지리적 위치에 있지 않은 경우 발신자 ID가 위임된(대신) 호출에 대해 다른 지리적 위치에서 표시하도록 허용하는 것은 PSTN 공급자의 의결입니다.</span><span class="sxs-lookup"><span data-stu-id="5a3db-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="5a3db-182">추가 정보</span><span class="sxs-lookup"><span data-stu-id="5a3db-182">More information</span></span>

[<span data-ttu-id="5a3db-183">대리인과 전화선 공유</span><span class="sxs-lookup"><span data-stu-id="5a3db-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)