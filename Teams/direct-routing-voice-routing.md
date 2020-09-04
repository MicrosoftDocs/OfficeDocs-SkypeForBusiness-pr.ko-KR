---
title: 다이렉트 라우팅에 대 한 음성 라우팅 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft 전화 시스템 다이렉트 라우팅을 사용 하 여 음성 라우팅을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 37343ad177e3408f94103296509e4b9bfc8ea759
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359414"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="9450a-103">다이렉트 라우팅에 대 한 음성 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="9450a-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="9450a-104">이 문서에서는 전화 시스템 다이렉트 라우팅에 대 한 음성 라우팅을 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="9450a-105">직접 라우팅 구성에 대 한 단계 3 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="9450a-106">1 단계.</span><span class="sxs-lookup"><span data-stu-id="9450a-106">Step 1.</span></span> [<span data-ttu-id="9450a-107">Microsoft 전화 시스템을 사용 하 여 SBC 연결 및 연결 확인</span><span class="sxs-lookup"><span data-stu-id="9450a-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="9450a-108">2 단계.</span><span class="sxs-lookup"><span data-stu-id="9450a-108">Step 2.</span></span> [<span data-ttu-id="9450a-109">사용자가 직접 라우팅, 음성, 보이스 메일을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="9450a-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="9450a-110">**3 단계. 음성 라우팅 구성** (이 문서)</span><span class="sxs-lookup"><span data-stu-id="9450a-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="9450a-111">4 단계.</span><span class="sxs-lookup"><span data-stu-id="9450a-111">Step 4.</span></span> [<span data-ttu-id="9450a-112">숫자를 대체 형식으로 번역</span><span class="sxs-lookup"><span data-stu-id="9450a-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="9450a-113">직접 라우팅을 설정 하는 데 필요한 모든 단계에 대 한 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9450a-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="9450a-114">음성 라우팅 개요</span><span class="sxs-lookup"><span data-stu-id="9450a-114">Voice routing overview</span></span>

<span data-ttu-id="9450a-115">Microsoft 휴대폰 시스템에는 다음을 기준으로 특정 SBC (세션 경계 컨트롤러)로 전화를 보낼 수 있는 라우팅 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="9450a-116">호출 된 번호 패턴</span><span class="sxs-lookup"><span data-stu-id="9450a-116">The called number pattern</span></span> 
- <span data-ttu-id="9450a-117">호출 되는 특정 사용자와 전화 번호 패턴을 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="9450a-118">SBCs는 활성 및 백업으로 지정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="9450a-119">활성으로 구성 된 SBC를 특정 통화 경로에 대해 사용할 수 없는 경우에는 통화가 백업 SBC로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="9450a-120">음성 라우팅은 다음 요소로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="9450a-121">**음성 라우팅 정책** – 사용자 또는 여러 사용자에 게 할당할 수 있는 PSTN 용도를 위한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="9450a-122">**Pstn** 사용 – 다른 음성 라우팅 정책에서 공유할 수 있는 음성 경로 및 PSTN 용도에 대 한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="9450a-123">**음성 경로** – 호출 번호가 패턴과 일치 하는 호출에 사용할 수 패턴과 온라인 PSTN 게이트웨이 집합을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="9450a-124">**온라인 PSTN 게이트웨이** -호출이 sbc를 통해 호출 될 때 적용 되는 구성을 저장 하는 sbc에 대 한 포인터로, (예: pai (정방향 P-어설션된-Identity) 또는 기본 설정 코덱). 음성 경로에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="9450a-125">음성 라우팅 정책 고려 사항</span><span class="sxs-lookup"><span data-stu-id="9450a-125">Voice routing policy considerations</span></span>

<span data-ttu-id="9450a-126">사용자에 게 통화 요금제 라이선스가 있는 경우 해당 사용자의 발신 통화가 Microsoft 호출 계획 PSTN 인프라를 통해 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="9450a-127">온라인 음성 라우팅 정책을 구성 하 고 호출 계획 사용자에 게 할당 하는 경우 해당 사용자의 발신 전화를 확인 하 여 전화를 거는 번호가 온라인 음성 라우팅 정책에 정의 된 번호 패턴과 일치 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="9450a-128">일치 하는 항목이 있는 경우에는 통화가 직접 라우팅 트렁크를 통해 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="9450a-129">일치 하는 항목이 없는 경우 통화 요금제 PSTN 인프라를 통해 통화가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="9450a-130">전역 (조직 전체 기본값) 온라인 음성 라우팅 정책을 구성 하 고 적용 하는 경우 조직의 모든 음성 사용 사용자가 해당 정책을 상속 하 여, 호출 계획 사용자가 실수로 직접 라우팅 트렁크로 라우팅되는 PSTN 호출이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="9450a-131">모든 사용자가 전역 온라인 음성 라우팅 정책을 사용 하지 않도록 하려면 사용자 지정 온라인 음성 라우팅 정책을 구성 하 고 개별 음성 사용 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="9450a-132">예제 1: PSTN 사용량이 하나인 음성 라우팅</span><span class="sxs-lookup"><span data-stu-id="9450a-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="9450a-133">다음 다이어그램은 통화 흐름에서 음성 라우팅 정책의 두 가지 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="9450a-134">**통화 흐름 1 (왼쪽):** 사용자가 + 1 425 XXX XX xx 또는 + 1 206 XXX XX XX에 전화를 거는 경우, 통화는 SBC sbc1.contoso.biz 또는 sbc2.contoso.biz로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="9450a-135">Sbc1.contoso.biz 나 sbc2.contoso.biz 모두 사용할 수 없는 경우에는 통화가 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="9450a-136">**통화 흐름 2 (오른쪽):** 사용자가 + 1 425 XXX XX xx 또는 + 1 206 XXX XX XX에 전화를 거는 경우, 통화는 먼저 SBC sbc1.contoso.biz 또는 sbc2.contoso.biz로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="9450a-137">두 SBC를 모두 사용할 수 없는 경우 우선 순위가 낮은 경로 (sbc3.contoso.biz 및 sbc4.contoso.biz)가 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="9450a-138">사용할 수 있는 SBCs 장치가 없으면 통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-138">If none of the SBCs are available, the call is dropped.</span></span> 

![음성 라우팅 정책 예제 표시](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="9450a-140">두 예제에서 음성 경로에 우선 순위를 할당 하는 동안 경로의 SBCs는 임의 순서 대로 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9450a-141">사용자에 게 Microsoft 통화 계획 라이선스가 없는 경우 예제 구성의 패턴 + 1 425 XXX XX xx 또는 + 1 206 XXX XX XX와 일치 하는 숫자를 제외한 모든 번호로 거는 호출이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-141">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="9450a-142">사용자에 게 통화 요금제 라이선스가 있는 경우이 통화는 Microsoft 호출 계획의 정책에 따라 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-142">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="9450a-143">Microsoft 통화 요금제는 Microsoft 통화 계획 라이선스를 사용 하 여 모든 사용자의 마지막 경로에 자동으로 적용 되며 추가 통화 라우팅 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-143">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="9450a-144">다음 다이어그램에 표시 된 예제에서는 다른 모든 미국 및 캐나다 번호로 전화를 보낼 수 있는 음성 경로가 추가 됩니다 (호출 되는 번호 패턴 + 1 XXX XXX XX XX (으)로 이동 하는 호출).</span><span class="sxs-lookup"><span data-stu-id="9450a-144">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![세 번째 경로가 있는 음성 라우팅 정책 표시](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="9450a-146">다른 모든 통화에 대해 사용자에 게 라이선스 (Microsoft 전화 시스템 및 Microsoft 호출 계획)가 둘 다 있는 경우 자동 경로가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-146">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="9450a-147">관리자가 만든 온라인 음성 경로의 숫자 패턴과 일치 하는 항목이 없는 경우 통화는 Microsoft 통화 요금제를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-147">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="9450a-148">사용자에 게 Microsoft 전화 시스템만 있는 경우에는 일치 하는 규칙을 사용할 수 없기 때문에 통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-148">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9450a-149">패턴 + 1 XXX XXX XX XX와 일치 하는 경로만 있으므로이 경우 경로 "Other + 1"에 대 한 우선 순위 값은 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-149">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="9450a-150">사용자가 + 1 324 567 89 89를 호출 하 고 sbc5.contoso.biz 및 sbc6.contoso.biz를 모두 사용할 수 없는 경우 통화가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-150">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="9450a-151">다음 표에는 세 가지 음성 경로를 사용 하는 구성이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-151">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="9450a-152">이 예제에서는 세 경로가 모두 동일한 PSTN 사용 인 "미국 및 캐나다"의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-152">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="9450a-153">모든 경로는 "미국 및 캐나다" PSTN 사용과 연결 되며 PSTN 사용은 "미국 전용" 음성 라우팅 정책에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-153">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="9450a-154">**PSTN 사용**</span><span class="sxs-lookup"><span data-stu-id="9450a-154">**PSTN usage**</span></span>|<span data-ttu-id="9450a-155">**음성 경로**</span><span class="sxs-lookup"><span data-stu-id="9450a-155">**Voice route**</span></span>|<span data-ttu-id="9450a-156">**번호 패턴**</span><span class="sxs-lookup"><span data-stu-id="9450a-156">**Number pattern**</span></span>|<span data-ttu-id="9450a-157">**중요도**</span><span class="sxs-lookup"><span data-stu-id="9450a-157">**Priority**</span></span>|<span data-ttu-id="9450a-158">**하더라도**</span><span class="sxs-lookup"><span data-stu-id="9450a-158">**SBC**</span></span>|<span data-ttu-id="9450a-159">**설명**</span><span class="sxs-lookup"><span data-stu-id="9450a-159">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9450a-160">미국 및 캐나다</span><span class="sxs-lookup"><span data-stu-id="9450a-160">US and Canada</span></span>|<span data-ttu-id="9450a-161">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="9450a-161">"Redmond 1"</span></span>|<span data-ttu-id="9450a-162">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="9450a-162">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9450a-163">1</span><span class="sxs-lookup"><span data-stu-id="9450a-163">1</span></span>|<span data-ttu-id="9450a-164">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-164">sbc1.contoso.biz</span></span><br/><span data-ttu-id="9450a-165">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-165">sbc2.contoso.biz</span></span>|<span data-ttu-id="9450a-166">호출 되는 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX의 활성 경로</span><span class="sxs-lookup"><span data-stu-id="9450a-166">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9450a-167">미국 및 캐나다</span><span class="sxs-lookup"><span data-stu-id="9450a-167">US and Canada</span></span>|<span data-ttu-id="9450a-168">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="9450a-168">"Redmond 2"</span></span>|<span data-ttu-id="9450a-169">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="9450a-169">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9450a-170">2</span><span class="sxs-lookup"><span data-stu-id="9450a-170">2</span></span>|<span data-ttu-id="9450a-171">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-171">sbc3.contoso.biz</span></span><br/><span data-ttu-id="9450a-172">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-172">sbc4.contoso.biz</span></span>|<span data-ttu-id="9450a-173">호출 되는 번호에 대 한 백업 경로 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="9450a-173">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9450a-174">미국 및 캐나다</span><span class="sxs-lookup"><span data-stu-id="9450a-174">US and Canada</span></span>|<span data-ttu-id="9450a-175">"기타 + 1"</span><span class="sxs-lookup"><span data-stu-id="9450a-175">"Other +1"</span></span>|<span data-ttu-id="9450a-176">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="9450a-176">^\\+1(\d{10})$</span></span>|<span data-ttu-id="9450a-177">3</span><span class="sxs-lookup"><span data-stu-id="9450a-177">3</span></span>|<span data-ttu-id="9450a-178">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-178">sbc5.contoso.biz</span></span><br/><span data-ttu-id="9450a-179">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-179">sbc6.contoso.biz</span></span>|<span data-ttu-id="9450a-180">호출 되는 번호에 대 한 경로 + 1 XXX XXX XX XX (+ 1 425 XXX xx xx 또는 + 1 206 XXX XX xx 제외)</span><span class="sxs-lookup"><span data-stu-id="9450a-180">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="9450a-181">예제 1: 구성 단계</span><span class="sxs-lookup"><span data-stu-id="9450a-181">Example 1: Configuration steps</span></span>

<span data-ttu-id="9450a-182">다음 예제에서는 다음을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-182">The following example shows how to:</span></span>

1. <span data-ttu-id="9450a-183">단일 PSTN 사용량을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-183">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="9450a-184">세 가지 음성 경로를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-184">Configure three voice routes.</span></span>
3. <span data-ttu-id="9450a-185">음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-185">Create a voice routing policy.</span></span>
4. <span data-ttu-id="9450a-186">Spencer Low 라는 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-186">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="9450a-187">[Microsoft 팀 관리 센터](#admincenterexample1) 또는 [PowerShell](#powershellexample1) 을 사용 하 여 다음 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-187">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9450a-188">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="9450a-188">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="9450a-189">1 단계: "미국 및 캐나다" PSTN 사용을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-189">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="9450a-190">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **다이렉트 라우팅으로**이동한 다음 오른쪽 위 모서리에서 **PSTN 사용 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-190">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="9450a-191">**추가**를 클릭 하 고 **미국 및 캐나다**를 입력 한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-191">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="9450a-192">2 단계: 세 개의 음성 경로 만들기 (Redmond 1, 레드먼드 2, 기타 + 1)</span><span class="sxs-lookup"><span data-stu-id="9450a-192">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="9450a-193">다음 단계에서는 음성 경로를 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-193">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="9450a-194">이 단계를 사용 하 여 앞의 표에 나와 있는 설정을 사용 하 여이 예제에서 레드먼드 1, 레드먼드 2, 그리고 기타 + 1 이라는 세 개의 음성 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-194">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="9450a-195">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **다이렉트 라우팅으로**이동한 다음 **음성 경로** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-195">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="9450a-196">**추가**를 클릭 한 다음 음성 경로의 이름과 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-196">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="9450a-197">우선 순위를 설정 하 고 전화 번호 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-197">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="9450a-198">음성 경로를 사용 하 여 SBC를 등록 하려면 **sbcs 등록 (선택)** 아래에 **sbcs 추가**를 클릭 하 고 등록할 Sbcs를 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-198">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="9450a-199">PSTN 사용 레코드를 추가 하려면 **pstn 사용 레코드 (선택 사항)** 에서 **pstn 사용량 추가**를 클릭 하 고 추가 하려는 pstn 레코드를 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-199">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="9450a-200">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-200">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="9450a-201">3 단계: "미국 전용" 이라는 음성 라우팅 정책 만들기 및 정책에 "미국 및 캐나다" PSTN 사용 추가</span><span class="sxs-lookup"><span data-stu-id="9450a-201">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="9450a-202">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **음성 라우팅 정책**으로 이동한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-202">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="9450a-203">이름으로 **만 US** 를 입력 하 고 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-203">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="9450a-204">**Pstn 사용 레코드**에서 **pstn 사용량 추가**를 클릭 하 고 "미국 및 캐나다" pstn 사용 레코드를 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-204">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="9450a-205">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-205">Click **Save**.</span></span>

<span data-ttu-id="9450a-206">자세히 알아보려면 [음성 라우팅 정책 관리](manage-voice-routing-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9450a-206">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="9450a-207">4 단계: Spencer Low 라는 사용자에 게 음성 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9450a-207">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="9450a-208">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-208">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="9450a-209">**정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-209">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="9450a-210">**음성 라우팅 정책**에서 "미국 전용" 정책을 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-210">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="9450a-211">자세히 알아보려면 [음성 라우팅 정책 관리](manage-voice-routing-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9450a-211">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9450a-212">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="9450a-212">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="9450a-213">1 단계: "미국 및 캐나다" PSTN 사용을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-213">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="9450a-214">비즈니스용 Skype Online의 원격 PowerShell 세션에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-214">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="9450a-215">다음을 입력 하 여 사용법을 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-215">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="9450a-216">다음은 잘릴 수 있는 이름 목록을 반환 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-216">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="9450a-217">다음 예제에서는 `(Get-CSOnlinePSTNUsage).usage` Powershell 명령을 실행 하 여 전체 이름을 표시 하는 결과를 보여 줍니다 (잘리지 않음).</span><span class="sxs-lookup"><span data-stu-id="9450a-217">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="9450a-218">2 단계: 세 개의 음성 경로 만들기 (Redmond 1, 레드먼드 2, 기타 + 1)</span><span class="sxs-lookup"><span data-stu-id="9450a-218">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="9450a-219">비즈니스용 Skype Online의 PowerShell 세션에서 "Redmond 1" 경로를 만들려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-219">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="9450a-220">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="9450a-220">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="9450a-221">Redmond 2 경로를 만들려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-221">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="9450a-222">다른 + 1 경로를 만들려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-222">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="9450a-223">번호 패턴 특성의 정규식이 유효한 식 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-223">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="9450a-224">이 웹 사이트를 사용 하 여 테스트할 수 있습니다. [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="9450a-224">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="9450a-225">일부 경우에는 동일한 SBC에 대 한 모든 통화를 라우팅할 필요가 있습니다. -번호 사용 패턴 ". \*"</span><span class="sxs-lookup"><span data-stu-id="9450a-225">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="9450a-226">모든 통화를 동일한 SBC에 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-226">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="9450a-227">아래 `Get-CSOnlineVoiceRoute` 와 같이 옵션을 사용 하 여 PowerShell 명령을 실행 하 여 경로를 올바르게 구성 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-227">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="9450a-228">다음을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-228">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
</pre>

<span data-ttu-id="9450a-229">이 예제에서 경로 "Other + 1"에 우선 순위 4가 자동으로 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-229">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="9450a-230">3 단계: "미국 전용" 이라는 음성 라우팅 정책 만들기 및 정책에 "미국 및 캐나다" PSTN 사용 추가</span><span class="sxs-lookup"><span data-stu-id="9450a-230">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="9450a-231">비즈니스용 Skype Online의 PowerShell 세션에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-231">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="9450a-232">결과는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-232">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="9450a-233">4 단계: Spencer Low 라는 사용자에 게 음성 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9450a-233">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="9450a-234">비즈니스용 Skype Online의 PowerShell 세션에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-234">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="9450a-235">다음 명령을 입력 하 여 정책 할당의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-235">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="9450a-236">이 명령은 다음을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-236">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="9450a-237">예제 2: 여러 PSTN 용도를 사용 하는 음성 라우팅</span><span class="sxs-lookup"><span data-stu-id="9450a-237">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="9450a-238">예 1에서 만든 음성 라우팅 정책은 Microsoft 통화 계획 라이선스가 사용자에 게 할당 되지 않는 이상 미국 및 캐나다의 전화 번호로만 통화 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-238">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="9450a-239">다음 예제에서는 "제한 없음" 음성 라우팅 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-239">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="9450a-240">이 정책에서는 예제 1에서 만든 "US 및 캐나다" PSTN 사용 및 새로운 "국제" PSTN 사용을 재사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-240">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="9450a-241">이 정책은 SBCs sbc2.contoso.biz 및 sbc5.contoso.biz에 대 한 다른 모든 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-241">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="9450a-242">표시 되는 예제에서는 사용자에 대 한 US 전용 정책만, 사용자에 게는 제한 사항 없음 정책, Spencer John 숲에는 다음과 같이 라우팅이 발생 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-242">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="9450a-243">Spencer 낮음 – 미국 전용 정책.</span><span class="sxs-lookup"><span data-stu-id="9450a-243">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="9450a-244">통화는 미국 및 캐나다 번호로만 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-244">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="9450a-245">Redmond 번호 범위로 전화를 거는 경우 특정 SBCs 집합을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-245">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="9450a-246">통화 요금제 라이선스가 사용자에 게 할당 되지 않으면 미국 이외의 번호는 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-246">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="9450a-247">John 숲 – 국제 정책.</span><span class="sxs-lookup"><span data-stu-id="9450a-247">John Woods – International policy.</span></span>  <span data-ttu-id="9450a-248">모든 숫자가 통화에 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-248">Calls are allowed to any number.</span></span> <span data-ttu-id="9450a-249">Redmond 번호 범위로 전화를 거는 경우 특정 SBCs 집합을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-249">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="9450a-250">미국 이외의 번호는 sbc2.contoso.biz 및 sbc5.contoso.biz를 사용 하 여 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-250">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![사용자 Spencer 낮음으로 지정 된 음성 라우팅 정책을 표시 합니다.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="9450a-252">다른 모든 통화에 대해 사용자에 게 라이선스 (Microsoft 전화 시스템 및 Microsoft 호출 계획)가 둘 다 있는 경우 자동 경로가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-252">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="9450a-253">관리자가 만든 온라인 음성 경로의 번호 패턴에 일치 하는 항목이 없는 경우에는 Microsoft 통화 요금제를 사용 하 여 통화가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-253">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="9450a-254">사용자에 게 Microsoft 전화 시스템만 있는 경우에는 일치 하는 규칙이 없기 때문에 통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-254">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![사용자에 게 할당 된 음성 라우팅 정책 표시, John 숲](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="9450a-256">다음 표에서는 라우팅 정책 "제한 없음" 사용 현황 및 음성 경로를 요약 하 여 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-256">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="9450a-257">**PSTN 사용**</span><span class="sxs-lookup"><span data-stu-id="9450a-257">**PSTN usage**</span></span>|<span data-ttu-id="9450a-258">**음성 경로**</span><span class="sxs-lookup"><span data-stu-id="9450a-258">**Voice route**</span></span>|<span data-ttu-id="9450a-259">**번호 패턴**</span><span class="sxs-lookup"><span data-stu-id="9450a-259">**Number pattern**</span></span>|<span data-ttu-id="9450a-260">**중요도**</span><span class="sxs-lookup"><span data-stu-id="9450a-260">**Priority**</span></span>|<span data-ttu-id="9450a-261">**하더라도**</span><span class="sxs-lookup"><span data-stu-id="9450a-261">**SBC**</span></span>|<span data-ttu-id="9450a-262">**설명**</span><span class="sxs-lookup"><span data-stu-id="9450a-262">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9450a-263">미국 및 캐나다</span><span class="sxs-lookup"><span data-stu-id="9450a-263">US and Canada</span></span>|<span data-ttu-id="9450a-264">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="9450a-264">"Redmond 1"</span></span>|<span data-ttu-id="9450a-265">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="9450a-265">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9450a-266">1</span><span class="sxs-lookup"><span data-stu-id="9450a-266">1</span></span>|<span data-ttu-id="9450a-267">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-267">sbc1.contoso.biz</span></span><br/><span data-ttu-id="9450a-268">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-268">sbc2.contoso.biz</span></span>|<span data-ttu-id="9450a-269">호출 수신자 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX의 활성 경로</span><span class="sxs-lookup"><span data-stu-id="9450a-269">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9450a-270">미국 및 캐나다</span><span class="sxs-lookup"><span data-stu-id="9450a-270">US and Canada</span></span>|<span data-ttu-id="9450a-271">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="9450a-271">"Redmond 2"</span></span>|<span data-ttu-id="9450a-272">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="9450a-272">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9450a-273">2</span><span class="sxs-lookup"><span data-stu-id="9450a-273">2</span></span>|<span data-ttu-id="9450a-274">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-274">sbc3.contoso.biz</span></span><br/><span data-ttu-id="9450a-275">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-275">sbc4.contoso.biz</span></span>|<span data-ttu-id="9450a-276">호출 수신자 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX에 대 한 백업 경로</span><span class="sxs-lookup"><span data-stu-id="9450a-276">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9450a-277">미국 및 캐나다</span><span class="sxs-lookup"><span data-stu-id="9450a-277">US and Canada</span></span>|<span data-ttu-id="9450a-278">"기타 + 1"</span><span class="sxs-lookup"><span data-stu-id="9450a-278">"Other +1"</span></span>|<span data-ttu-id="9450a-279">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="9450a-279">^\\+1(\d{10})$</span></span>|<span data-ttu-id="9450a-280">3</span><span class="sxs-lookup"><span data-stu-id="9450a-280">3</span></span>|<span data-ttu-id="9450a-281">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-281">sbc5.contoso.biz</span></span><br/><span data-ttu-id="9450a-282">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-282">sbc6.contoso.biz</span></span>|<span data-ttu-id="9450a-283">호출 수신자 번호 + 1 XXX XXX XX XX (+ 1 425 XXX xx xx 또는 + 1 206 XXX XX xx 제외)의 경로</span><span class="sxs-lookup"><span data-stu-id="9450a-283">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="9450a-284">국제화</span><span class="sxs-lookup"><span data-stu-id="9450a-284">International</span></span>|<span data-ttu-id="9450a-285">국제화</span><span class="sxs-lookup"><span data-stu-id="9450a-285">International</span></span>|<span data-ttu-id="9450a-286">\d +</span><span class="sxs-lookup"><span data-stu-id="9450a-286">\d+</span></span>|<span data-ttu-id="9450a-287">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="9450a-287">4</span></span>|<span data-ttu-id="9450a-288">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-288">sbc2.contoso.biz</span></span><br/><span data-ttu-id="9450a-289">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9450a-289">sbc5.contoso.biz</span></span>|<span data-ttu-id="9450a-290">임의의 숫자 패턴에 대 한 라우팅</span><span class="sxs-lookup"><span data-stu-id="9450a-290">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="9450a-291">음성 라우팅 정책의 PSTN 사용량 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-291">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="9450a-292">용도는 순서 대로 적용 되며 첫 번째 사용에서 일치 하는 항목을 찾은 경우 다른 용도는 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-292">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="9450a-293">"국제" PSTN 사용은 "미국 및 캐나다" PSTN 사용 후에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-293">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="9450a-294">PSTN 사용량의 순서를 변경 하려면 `Set-CSOnlineVoiceRoutingPolicy` 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-294">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="9450a-295">예를 들어 "미국 및 캐나다"의 순서와 역순으로 "국제" 초를 순서 대로 변경 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-295">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="9450a-296">"기타 + 1" 및 "국제" 음성 경로에 대 한 우선 순위는 자동으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-296">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="9450a-297">"Redmond 1" 및 "Redmond 2" 보다 우선 순위가 낮은 경우에는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-297">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="9450a-298">예제 2: 구성 단계</span><span class="sxs-lookup"><span data-stu-id="9450a-298">Example 2: Configuration steps</span></span>

<span data-ttu-id="9450a-299">다음 예제에서는 다음을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-299">The following example shows how to:</span></span>

1. <span data-ttu-id="9450a-300">국제 전화 라는 새로운 PSTN 사용을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-300">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="9450a-301">국제적 이라는 새 음성 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-301">Create a new voice route called International.</span></span>
3. <span data-ttu-id="9450a-302">음성 라우팅 정책을 만듭니다. 제한 없음이 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-302">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="9450a-303">사용자 John 숲에 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-303">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="9450a-304">[Microsoft 팀 관리 센터](#admincenterexample2) 또는 [PowerShell](#powershellexample2) 을 사용 하 여 다음 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-304">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9450a-305">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="9450a-305">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="9450a-306">1 단계: "국제" PSTN 사용 만들기</span><span class="sxs-lookup"><span data-stu-id="9450a-306">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="9450a-307">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **다이렉트 라우팅으로**이동한 다음 오른쪽 위 모서리에서 **PSTN 사용 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-307">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="9450a-308">**추가**를 클릭 하 고 **국제 전화**를 입력 한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-308">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="9450a-309">2 단계: "국제" 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="9450a-309">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="9450a-310">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **다이렉트 라우팅으로**이동한 다음 **음성 경로** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-310">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="9450a-311">**추가**를 클릭 하 고 이름으로 "국제"을 입력 한 다음 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-311">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="9450a-312">우선 순위를 4로 설정한 다음 전화를 걸 번호 패턴을 \d +로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-312">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="9450a-313">**Sbcs 등록 (선택 사항)** 에서 **SBCs 추가**를 클릭 하 고 sbc2.contoso.biz 및 Sbc5.contoso.biz를 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-313">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="9450a-314">**Pstn 사용 레코드 (선택 사항)** 에서 **PSTN 사용량 추가**를 클릭 하 고 "국제" pstn 사용 레코드를 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-314">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="9450a-315">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-315">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="9450a-316">3 단계: "제한 없음" 이라는 음성 라우팅 정책 만들기 및 "미국 및 캐나다" 및 "국제" PSTN 용도를 정책에 추가</span><span class="sxs-lookup"><span data-stu-id="9450a-316">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="9450a-317">PSTN 사용 "미국 및 캐나다"는 로컬 또는 온-프레미스 통화로 "+ 1 425 XXX xx" 및 "+ 1 206 XXX XX XX"로 거는 통화에 대 한 특수 처리를 유지 하기 위해이 음성 라우팅 정책에서 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-317">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="9450a-318">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **음성 라우팅 정책**으로 이동한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-318">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="9450a-319">이름으로 **제한을** 입력 하 고 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-319">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="9450a-320">**Pstn 사용 레코드**에서 **pstn 사용량 추가**를 클릭 하 고 "미국 및 캐나다" pstn 사용 레코드를 선택한 다음 "국제" pstn 사용 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-320">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="9450a-321">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-321">Click **Apply**.</span></span>

    <span data-ttu-id="9450a-322">PSTN 사용 순서를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-322">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="9450a-323">이 예제에서와 같이 구성 된 사용량으로 "+ 1 425 XXX XX"로 전화를 걸고 나면 통화는 "미국 및 캐나다" 사용에 설정 된 경로를 따르고 특별 한 라우팅 논리가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-323">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="9450a-324">즉, 통화가 먼저 sbc1.contoso.biz 및 sbc2.contoso.biz를 사용 하 여 라우팅된 다음 백업 경로로 sbc3.contoso.biz 및 sbc4.contoso.biz 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-324">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="9450a-325">"국제" PSTN 사용이 "미국 및 캐나다" 보다 앞에 있는 경우 + 1 425 XXX XX XX로 거는 호출은 라우팅 논리의 일부로 sbc2.contoso.biz 및 sbc5.contoso.biz로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-325">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="9450a-326">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-326">Click **Save**.</span></span>

<span data-ttu-id="9450a-327">자세히 알아보려면 [음성 라우팅 정책 관리](manage-voice-routing-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9450a-327">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="9450a-328">4 단계: John 숲 이라는 사용자에 게 음성 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9450a-328">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="9450a-329">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-329">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="9450a-330">**정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-330">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="9450a-331">**음성 라우팅 정책**에서 "제한 없음" 정책을 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-331">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="9450a-332">결과적으로 John 숲의 통화에 적용 되는 음성 정책은 무제한 이며 미국, 캐나다, 국제 통화를 위해 제공 되는 통화 라우팅의 논리를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-332">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9450a-333">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="9450a-333">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="9450a-334">1 단계: "국제" PSTN 사용 만들기</span><span class="sxs-lookup"><span data-stu-id="9450a-334">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="9450a-335">비즈니스용 Skype Online의 원격 PowerShell 세션에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-335">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="9450a-336">2 단계: "국제" 이라는 새 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="9450a-336">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="9450a-337">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="9450a-337">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="9450a-338">3 단계: "제한 없음" 이라는 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9450a-338">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="9450a-339">PSTN 사용 "Redmond 1" 및 "Redmond"는 전화 번호 "+ 1 425 XXX xx" 및 "+ 1 206 XXX XX XX"를 로컬 또는 온-프레미스 통화로 하는 특별 한 처리를 유지 하기 위해이 음성 라우팅 정책에 재사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-339">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="9450a-340">PSTN 사용 순서를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-340">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="9450a-341">다음 예제와 같이 구성 된 사용량으로 "+ 1 425 XXX XX"로 전화를 걸고 나면 통화는 "미국 및 캐나다" 사용에 설정 된 경로를 따르고 특별 한 라우팅 논리가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-341">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="9450a-342">즉, 통화가 먼저 sbc1.contoso.biz 및 sbc2.contoso.biz를 사용 하 여 라우팅된 다음 백업 경로로 sbc3.contoso.biz 및 sbc4.contoso.biz 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-342">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="9450a-343">"국제" PSTN 사용이 "미국 및 캐나다" 보다 앞에 있는 경우 + 1 425 XXX XX XX로 거는 호출은 라우팅 논리의 일부로 sbc2.contoso.biz 및 sbc5.contoso.biz로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-343">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="9450a-344">명령 입력:</span><span class="sxs-lookup"><span data-stu-id="9450a-344">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="9450a-345">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="9450a-345">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="9450a-346">4 단계: John 숲 이라는 사용자에 게 음성 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9450a-346">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="9450a-347">그런 다음 명령을 사용 하 여 과제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-347">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="9450a-348">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="9450a-348">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="9450a-349">결과적으로 John 숲의 통화에 적용 되는 음성 정책에는 제한이 없으며 미국, 캐나다, 국제 통화를 위해 제공 되는 통화 라우팅의 논리에 따라 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9450a-349">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="9450a-350">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9450a-350">See also</span></span>

[<span data-ttu-id="9450a-351">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="9450a-351">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="9450a-352">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="9450a-352">Configure Direct Routing</span></span>](direct-routing-configure.md)
