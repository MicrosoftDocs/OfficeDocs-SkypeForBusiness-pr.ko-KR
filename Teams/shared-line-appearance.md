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
ms.openlocfilehash: 619e011e1af5a765bc86ca6bd68134dc5ab1e9fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182405"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="77afb-103">Microsoft 팀의 공유 선 모양</span><span class="sxs-lookup"><span data-stu-id="77afb-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="77afb-104">공유 선 모양은 사용자가 자신을 대신 하 여 통화에 응답 하거나 처리할 대리인을 선택할 수 있는 위임 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="77afb-105">이 기능은 사용자가 사용자의 통화를 정기적으로 처리 하는 관리 도우미가 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-105">This feature is helpful if a user has an administrative assistant who regularly handles the user’s calls.</span></span> <span data-ttu-id="77afb-106">공유 선 모양의 컨텍스트에서 관리자는 자신을 대신 하 여 전화를 걸거나 받을 대리인에 게 권한을 부여 하 고 대리인이 다른 사람을 대신 하 여 전화를 걸고 받을 수 있는 사람을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77afb-107">이 기능은 팀 전용 배포 모드 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="77afb-108">팀 배포 모드에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77afb-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="77afb-109">라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="77afb-109">License required</span></span>

<span data-ttu-id="77afb-110">사용자는 대리인 이거나 위임을 설정 하 고 다른 사람이 대신 전화를 걸거나 받을 수 있도록 하는 enterprise voice 사용자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-110">A user must be an enterprise voice user to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="77afb-111">관리자와 대리인 모두 엔터프라이즈 음성 기능을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-111">Both managers and delegates need to be enterprise voice enabled.</span></span> <span data-ttu-id="77afb-112">공유 회선 환경은 위임의 일부 이며 추가 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-112">The shared line experience is part of delegation, and requires no additional license.</span></span> <span data-ttu-id="77afb-113">라이선스 모델에 대 한 자세한 내용은 [Microsoft 팀 용 Office 365 라이선스](office-365-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77afb-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="77afb-114">위임 및 공유 선 모양 구성</span><span class="sxs-lookup"><span data-stu-id="77afb-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="77afb-115">위임 및 공유 선 모양은 구성할 관리 설정이 없기 때문에 사용자 기반 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="77afb-116">이 기능을 사용 하는 방법에 대 한 자세한 내용은 [대리인과 전화 회선 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77afb-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="77afb-117">테 넌 트 관리자는이 기능을 사용 하기 위해 **Teamscallingpolicy allowdelegation** 통한 위임을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-117">The tenant admin should enable delegation via the **TeamsCallingPolicy AllowDelegation** setting for this feature to work.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="77afb-118">공유 선 모양 기능 가용성</span><span class="sxs-lookup"><span data-stu-id="77afb-118">Shared line appearance feature availability</span></span>

<span data-ttu-id="77afb-119">현재 공유 선 모양은 다음 앱 및 장치에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-119">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="77afb-120">성능</span><span class="sxs-lookup"><span data-stu-id="77afb-120">Capability</span></span> | <span data-ttu-id="77afb-121">팀 데스크톱</span><span class="sxs-lookup"><span data-stu-id="77afb-121">Teams Desktop</span></span> | <span data-ttu-id="77afb-122">팀 Mac 앱</span><span class="sxs-lookup"><span data-stu-id="77afb-122">Teams Mac App</span></span> | <span data-ttu-id="77afb-123">팀 웹 앱 (Edge)</span><span class="sxs-lookup"><span data-stu-id="77afb-123">Teams Web App (Edge)</span></span> |<span data-ttu-id="77afb-124">팀 모바일 iOS/Android 앱</span><span class="sxs-lookup"><span data-stu-id="77afb-124">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="77afb-125">팀 IP 전화</span><span class="sxs-lookup"><span data-stu-id="77afb-125">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="77afb-126">대리인 설정</span><span class="sxs-lookup"><span data-stu-id="77afb-126">Set up delegation</span></span> | <span data-ttu-id="77afb-127">'</span><span class="sxs-lookup"><span data-stu-id="77afb-127">Yes</span></span> | <span data-ttu-id="77afb-128">'</span><span class="sxs-lookup"><span data-stu-id="77afb-128">Yes</span></span> | <span data-ttu-id="77afb-129">'</span><span class="sxs-lookup"><span data-stu-id="77afb-129">Yes</span></span> | <span data-ttu-id="77afb-130">아니요</span><span class="sxs-lookup"><span data-stu-id="77afb-130">No</span></span> | <span data-ttu-id="77afb-131">아니요</span><span class="sxs-lookup"><span data-stu-id="77afb-131">No</span></span> |
| <span data-ttu-id="77afb-132">다른 사람을 대신 하 여 전화 받기</span><span class="sxs-lookup"><span data-stu-id="77afb-132">Receive calls on behalf of another</span></span> | <span data-ttu-id="77afb-133">'</span><span class="sxs-lookup"><span data-stu-id="77afb-133">Yes</span></span> | <span data-ttu-id="77afb-134">'</span><span class="sxs-lookup"><span data-stu-id="77afb-134">Yes</span></span> | <span data-ttu-id="77afb-135">'</span><span class="sxs-lookup"><span data-stu-id="77afb-135">Yes</span></span> | <span data-ttu-id="77afb-136">'</span><span class="sxs-lookup"><span data-stu-id="77afb-136">Yes</span></span> | <span data-ttu-id="77afb-137">'</span><span class="sxs-lookup"><span data-stu-id="77afb-137">Yes</span></span> |
| <span data-ttu-id="77afb-138">다른 사람을 대신 하 여 전화 번호 호출</span><span class="sxs-lookup"><span data-stu-id="77afb-138">Call a phone number on behalf of another</span></span> | <span data-ttu-id="77afb-139">'</span><span class="sxs-lookup"><span data-stu-id="77afb-139">Yes</span></span> | <span data-ttu-id="77afb-140">'</span><span class="sxs-lookup"><span data-stu-id="77afb-140">Yes</span></span> | <span data-ttu-id="77afb-141">'</span><span class="sxs-lookup"><span data-stu-id="77afb-141">Yes</span></span> | <span data-ttu-id="77afb-142">'</span><span class="sxs-lookup"><span data-stu-id="77afb-142">Yes</span></span> | <span data-ttu-id="77afb-143">'</span><span class="sxs-lookup"><span data-stu-id="77afb-143">Yes</span></span> |
| <span data-ttu-id="77afb-144">다른 사람을 대신 하 여 팀 사용자에 게 전화</span><span class="sxs-lookup"><span data-stu-id="77afb-144">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="77afb-145">'</span><span class="sxs-lookup"><span data-stu-id="77afb-145">Yes</span></span> | <span data-ttu-id="77afb-146">'</span><span class="sxs-lookup"><span data-stu-id="77afb-146">Yes</span></span> | <span data-ttu-id="77afb-147">'</span><span class="sxs-lookup"><span data-stu-id="77afb-147">Yes</span></span> | <span data-ttu-id="77afb-148">'</span><span class="sxs-lookup"><span data-stu-id="77afb-148">Yes</span></span> | <span data-ttu-id="77afb-149">'</span><span class="sxs-lookup"><span data-stu-id="77afb-149">Yes</span></span> |
| <span data-ttu-id="77afb-150">공유 된 회선의 관리 보기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77afb-150">See the admin view of shared lines</span></span> | <span data-ttu-id="77afb-151">'</span><span class="sxs-lookup"><span data-stu-id="77afb-151">Yes</span></span> | <span data-ttu-id="77afb-152">'</span><span class="sxs-lookup"><span data-stu-id="77afb-152">Yes</span></span> | <span data-ttu-id="77afb-153">'</span><span class="sxs-lookup"><span data-stu-id="77afb-153">Yes</span></span> | <span data-ttu-id="77afb-154">아니요</span><span class="sxs-lookup"><span data-stu-id="77afb-154">No</span></span> | <span data-ttu-id="77afb-155">아니요</span><span class="sxs-lookup"><span data-stu-id="77afb-155">No</span></span> |
| <span data-ttu-id="77afb-156">관리자의 통화 활동에 대 한 관리 보기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77afb-156">See the admin view of manager's call activities</span></span> | <span data-ttu-id="77afb-157">'</span><span class="sxs-lookup"><span data-stu-id="77afb-157">Yes</span></span> | <span data-ttu-id="77afb-158">'</span><span class="sxs-lookup"><span data-stu-id="77afb-158">Yes</span></span> | <span data-ttu-id="77afb-159">'</span><span class="sxs-lookup"><span data-stu-id="77afb-159">Yes</span></span> | <span data-ttu-id="77afb-160">아니요</span><span class="sxs-lookup"><span data-stu-id="77afb-160">No</span></span> | <span data-ttu-id="77afb-161">아니요</span><span class="sxs-lookup"><span data-stu-id="77afb-161">No</span></span> |
| <span data-ttu-id="77afb-162">대리인의 관리자 보기 참조</span><span class="sxs-lookup"><span data-stu-id="77afb-162">See the manager view of delegates</span></span> | <span data-ttu-id="77afb-163">'</span><span class="sxs-lookup"><span data-stu-id="77afb-163">Yes</span></span> | <span data-ttu-id="77afb-164">'</span><span class="sxs-lookup"><span data-stu-id="77afb-164">Yes</span></span> | <span data-ttu-id="77afb-165">'</span><span class="sxs-lookup"><span data-stu-id="77afb-165">Yes</span></span> | <span data-ttu-id="77afb-166">아니요</span><span class="sxs-lookup"><span data-stu-id="77afb-166">No</span></span> | <span data-ttu-id="77afb-167">아니요</span><span class="sxs-lookup"><span data-stu-id="77afb-167">No</span></span> |
| <span data-ttu-id="77afb-168">관리자 또는 관리자가 보류 또는 다시 시작 가능</span><span class="sxs-lookup"><span data-stu-id="77afb-168">Admin or manager can hold or resume</span></span> | <span data-ttu-id="77afb-169">'</span><span class="sxs-lookup"><span data-stu-id="77afb-169">Yes</span></span> | <span data-ttu-id="77afb-170">'</span><span class="sxs-lookup"><span data-stu-id="77afb-170">Yes</span></span> | <span data-ttu-id="77afb-171">'</span><span class="sxs-lookup"><span data-stu-id="77afb-171">Yes</span></span> | <span data-ttu-id="77afb-172">아니요</span><span class="sxs-lookup"><span data-stu-id="77afb-172">No</span></span> | <span data-ttu-id="77afb-173">아니요</span><span class="sxs-lookup"><span data-stu-id="77afb-173">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="77afb-174">따릅니다</span><span class="sxs-lookup"><span data-stu-id="77afb-174">Limitations</span></span>

<span data-ttu-id="77afb-175">관리자는 대리인을 최대 25 개까지 추가할 수 있으며 대리인은 최대 25 명의 관리자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-175">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="77afb-176">테 넌 트에서 만들 수 있는 위임 관계의 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-176">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="77afb-177">위임자와 대리인이 같은 지리적 위치에 있지 않은 경우 발신자 ID가 위임 됨 (대신) 통화에 대해 다른 지리적 위치에서 표시 되도록 하는 것은 PSTN 공급자에 게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77afb-177">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="77afb-178">추가 정보</span><span class="sxs-lookup"><span data-stu-id="77afb-178">More information</span></span>

[<span data-ttu-id="77afb-179">대리인과 전화 라인 공유</span><span class="sxs-lookup"><span data-stu-id="77afb-179">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
