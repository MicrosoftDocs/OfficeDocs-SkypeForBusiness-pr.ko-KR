---
title: Microsoft 팀의 공유 선 모양
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 사용자가 자신을 대신 하 여 통화에 응답 하거나 처리할 대리인을 선택할 수 있는 공유 선 모양
ms.openlocfilehash: e2e99d214ef493933ed44d28c4a9cbdaeaab1077
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243115"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="1def7-103">Microsoft 팀의 공유 선 모양</span><span class="sxs-lookup"><span data-stu-id="1def7-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="1def7-104">공유 선 모양은 사용자가 자신을 대신 하 여 통화에 응답 하거나 처리할 대리인을 선택할 수 있는 위임 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="1def7-105">이 기능은 사용자가 사용자의 통화를 정기적으로 처리 하는 관리 도우미가 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-105">This feature is helpful if a user has an administrative assistant who regularly handles the user’s calls.</span></span> <span data-ttu-id="1def7-106">공유 선 모양의 컨텍스트에서 관리자는 자신을 대신 하 여 전화를 걸거나 받을 대리인에 게 권한을 부여 하 고 대리인이 다른 사람을 대신 하 여 전화를 걸고 받을 수 있는 사람을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1def7-107">이 기능은 팀 전용 배포 모드 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="1def7-108">팀 배포 모드에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1def7-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="1def7-109">라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="1def7-109">License required</span></span>

<span data-ttu-id="1def7-110">사용자는 대리인 이거나 위임을 설정 하 고 다른 사람이 대신 전화를 걸거나 받을 수 있도록 하는 enterprise voice 사용자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-110">A user must be an enterprise voice user to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="1def7-111">관리자와 대리인 모두 엔터프라이즈 음성 기능을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-111">Both managers and delegates need to be enterprise voice enabled.</span></span> <span data-ttu-id="1def7-112">공유 회선 환경은 위임의 일부 이며 추가 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-112">The shared line experience is part of delegation and requires no additional license.</span></span> <span data-ttu-id="1def7-113">라이선스 모델에 대 한 자세한 내용은 [Microsoft 팀 용 Office 365 라이선스](office-365-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1def7-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="1def7-114">위임 및 공유 선 모양 구성</span><span class="sxs-lookup"><span data-stu-id="1def7-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="1def7-115">위임 및 공유 선 모양은 구성할 관리 설정이 없기 때문에 사용자 기반 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="1def7-116">이 기능을 사용 하는 방법에 대 한 자세한 내용은 [대리인과 전화 회선 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1def7-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="1def7-117">테 넌 트 관리자는이 기능을 사용 하기 위해 **Teamscallingpolicy AllowDelegation** 설정 또는 팀 관리 포털을 통해 위임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="1def7-118">테 넌 트 관리자는 또한 팀 관리 센터에서 사용자에 대 한 위임 관계를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="1def7-119">또한 최종 사용자는 팀에서 직접 위임 관계를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="1def7-120">테 넌 트 관리자 또는 사용자는 서로에 대 한 구성을 차단할 수 없지만 팀 관리 센터 및 팀 클라이언트는이 관계를 두 위치에 정확 하 게 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1def7-121">테 넌 트 관리자가 사용자에 대 한 위임 기능을 해제 하면 (설정 된 후) 팀 관리 센터에서 해당 사용자에 대 한 위임 관계도 정리 하 여 잘못 된 통화 라우팅이 발생 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="1def7-122">공유 선 모양 기능 가용성</span><span class="sxs-lookup"><span data-stu-id="1def7-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="1def7-123">현재 공유 선 모양은 다음 앱 및 장치에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="1def7-124">성능</span><span class="sxs-lookup"><span data-stu-id="1def7-124">Capability</span></span> | <span data-ttu-id="1def7-125">팀 데스크톱</span><span class="sxs-lookup"><span data-stu-id="1def7-125">Teams Desktop</span></span> | <span data-ttu-id="1def7-126">팀 Mac 앱</span><span class="sxs-lookup"><span data-stu-id="1def7-126">Teams Mac App</span></span> | <span data-ttu-id="1def7-127">팀 웹 앱 (Edge)</span><span class="sxs-lookup"><span data-stu-id="1def7-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="1def7-128">팀 모바일 iOS/Android 앱</span><span class="sxs-lookup"><span data-stu-id="1def7-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="1def7-129">팀 IP 전화</span><span class="sxs-lookup"><span data-stu-id="1def7-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="1def7-130">대리인 설정</span><span class="sxs-lookup"><span data-stu-id="1def7-130">Set up delegation</span></span> | <span data-ttu-id="1def7-131">'</span><span class="sxs-lookup"><span data-stu-id="1def7-131">Yes</span></span> | <span data-ttu-id="1def7-132">'</span><span class="sxs-lookup"><span data-stu-id="1def7-132">Yes</span></span> | <span data-ttu-id="1def7-133">'</span><span class="sxs-lookup"><span data-stu-id="1def7-133">Yes</span></span> | <span data-ttu-id="1def7-134">아니요</span><span class="sxs-lookup"><span data-stu-id="1def7-134">No</span></span> | <span data-ttu-id="1def7-135">아니요</span><span class="sxs-lookup"><span data-stu-id="1def7-135">No</span></span> |
| <span data-ttu-id="1def7-136">다른 사람을 대신 하 여 전화 받기</span><span class="sxs-lookup"><span data-stu-id="1def7-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="1def7-137">'</span><span class="sxs-lookup"><span data-stu-id="1def7-137">Yes</span></span> | <span data-ttu-id="1def7-138">'</span><span class="sxs-lookup"><span data-stu-id="1def7-138">Yes</span></span> | <span data-ttu-id="1def7-139">'</span><span class="sxs-lookup"><span data-stu-id="1def7-139">Yes</span></span> | <span data-ttu-id="1def7-140">'</span><span class="sxs-lookup"><span data-stu-id="1def7-140">Yes</span></span> | <span data-ttu-id="1def7-141">'</span><span class="sxs-lookup"><span data-stu-id="1def7-141">Yes</span></span> |
| <span data-ttu-id="1def7-142">다른 사람을 대신 하 여 전화 번호 호출</span><span class="sxs-lookup"><span data-stu-id="1def7-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="1def7-143">'</span><span class="sxs-lookup"><span data-stu-id="1def7-143">Yes</span></span> | <span data-ttu-id="1def7-144">'</span><span class="sxs-lookup"><span data-stu-id="1def7-144">Yes</span></span> | <span data-ttu-id="1def7-145">'</span><span class="sxs-lookup"><span data-stu-id="1def7-145">Yes</span></span> | <span data-ttu-id="1def7-146">'</span><span class="sxs-lookup"><span data-stu-id="1def7-146">Yes</span></span> | <span data-ttu-id="1def7-147">'</span><span class="sxs-lookup"><span data-stu-id="1def7-147">Yes</span></span> |
| <span data-ttu-id="1def7-148">다른 사람을 대신 하 여 팀 사용자에 게 전화</span><span class="sxs-lookup"><span data-stu-id="1def7-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="1def7-149">'</span><span class="sxs-lookup"><span data-stu-id="1def7-149">Yes</span></span> | <span data-ttu-id="1def7-150">'</span><span class="sxs-lookup"><span data-stu-id="1def7-150">Yes</span></span> | <span data-ttu-id="1def7-151">'</span><span class="sxs-lookup"><span data-stu-id="1def7-151">Yes</span></span> | <span data-ttu-id="1def7-152">'</span><span class="sxs-lookup"><span data-stu-id="1def7-152">Yes</span></span> | <span data-ttu-id="1def7-153">'</span><span class="sxs-lookup"><span data-stu-id="1def7-153">Yes</span></span> |
| <span data-ttu-id="1def7-154">공유 된 회선의 관리 보기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1def7-154">See the admin view of shared lines</span></span> | <span data-ttu-id="1def7-155">'</span><span class="sxs-lookup"><span data-stu-id="1def7-155">Yes</span></span> | <span data-ttu-id="1def7-156">'</span><span class="sxs-lookup"><span data-stu-id="1def7-156">Yes</span></span> | <span data-ttu-id="1def7-157">'</span><span class="sxs-lookup"><span data-stu-id="1def7-157">Yes</span></span> | <span data-ttu-id="1def7-158">아니요</span><span class="sxs-lookup"><span data-stu-id="1def7-158">No</span></span> | <span data-ttu-id="1def7-159">아니요</span><span class="sxs-lookup"><span data-stu-id="1def7-159">No</span></span> |
| <span data-ttu-id="1def7-160">관리자의 통화 활동에 대 한 관리 보기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1def7-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="1def7-161">'</span><span class="sxs-lookup"><span data-stu-id="1def7-161">Yes</span></span> | <span data-ttu-id="1def7-162">'</span><span class="sxs-lookup"><span data-stu-id="1def7-162">Yes</span></span> | <span data-ttu-id="1def7-163">'</span><span class="sxs-lookup"><span data-stu-id="1def7-163">Yes</span></span> | <span data-ttu-id="1def7-164">아니요</span><span class="sxs-lookup"><span data-stu-id="1def7-164">No</span></span> | <span data-ttu-id="1def7-165">아니요</span><span class="sxs-lookup"><span data-stu-id="1def7-165">No</span></span> |
| <span data-ttu-id="1def7-166">대리인의 관리자 보기 참조</span><span class="sxs-lookup"><span data-stu-id="1def7-166">See the manager view of delegates</span></span> | <span data-ttu-id="1def7-167">'</span><span class="sxs-lookup"><span data-stu-id="1def7-167">Yes</span></span> | <span data-ttu-id="1def7-168">'</span><span class="sxs-lookup"><span data-stu-id="1def7-168">Yes</span></span> | <span data-ttu-id="1def7-169">'</span><span class="sxs-lookup"><span data-stu-id="1def7-169">Yes</span></span> | <span data-ttu-id="1def7-170">아니요</span><span class="sxs-lookup"><span data-stu-id="1def7-170">No</span></span> | <span data-ttu-id="1def7-171">아니요</span><span class="sxs-lookup"><span data-stu-id="1def7-171">No</span></span> |
| <span data-ttu-id="1def7-172">관리자 또는 관리자가 보류 또는 다시 시작 가능</span><span class="sxs-lookup"><span data-stu-id="1def7-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="1def7-173">'</span><span class="sxs-lookup"><span data-stu-id="1def7-173">Yes</span></span> | <span data-ttu-id="1def7-174">'</span><span class="sxs-lookup"><span data-stu-id="1def7-174">Yes</span></span> | <span data-ttu-id="1def7-175">'</span><span class="sxs-lookup"><span data-stu-id="1def7-175">Yes</span></span> | <span data-ttu-id="1def7-176">아니요</span><span class="sxs-lookup"><span data-stu-id="1def7-176">No</span></span> | <span data-ttu-id="1def7-177">아니요</span><span class="sxs-lookup"><span data-stu-id="1def7-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="1def7-178">따릅니다</span><span class="sxs-lookup"><span data-stu-id="1def7-178">Limitations</span></span>

<span data-ttu-id="1def7-179">관리자는 대리인을 최대 25 개까지 추가할 수 있으며 대리인은 최대 25 명의 관리자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="1def7-180">테 넌 트에서 만들 수 있는 위임 관계의 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="1def7-181">위임자와 대리인이 같은 지리적 위치에 있지 않은 경우 발신자 ID가 위임 됨 (대신) 통화에 대해 다른 지리적 위치에서 표시 되도록 하는 것은 PSTN 공급자에 게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1def7-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="1def7-182">추가 정보</span><span class="sxs-lookup"><span data-stu-id="1def7-182">More information</span></span>

[<span data-ttu-id="1def7-183">대리인과 전화 라인 공유</span><span class="sxs-lookup"><span data-stu-id="1def7-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
