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
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42158000"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="9db95-103">다이렉트 라우팅에 대 한 음성 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="9db95-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="9db95-104">이 문서에서는 전화 시스템 다이렉트 라우팅에 대 한 음성 라우팅을 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="9db95-105">직접 라우팅 구성에 대 한 단계 3 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="9db95-106">1 단계.</span><span class="sxs-lookup"><span data-stu-id="9db95-106">Step 1.</span></span> [<span data-ttu-id="9db95-107">Microsoft 전화 시스템을 사용 하 여 SBC 연결 및 연결 확인</span><span class="sxs-lookup"><span data-stu-id="9db95-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="9db95-108">2 단계.</span><span class="sxs-lookup"><span data-stu-id="9db95-108">Step 2.</span></span> [<span data-ttu-id="9db95-109">사용자가 직접 라우팅, 음성, 보이스 메일을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="9db95-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)    
- <span data-ttu-id="9db95-110">**3 단계. 음성 라우팅 구성** (이 문서)</span><span class="sxs-lookup"><span data-stu-id="9db95-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="9db95-111">4 단계.</span><span class="sxs-lookup"><span data-stu-id="9db95-111">Step 4.</span></span> [<span data-ttu-id="9db95-112">숫자를 대체 형식으로 번역</span><span class="sxs-lookup"><span data-stu-id="9db95-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="9db95-113">직접 라우팅을 설정 하는 데 필요한 모든 단계에 대 한 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9db95-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="9db95-114">음성 라우팅 개요</span><span class="sxs-lookup"><span data-stu-id="9db95-114">Voice routing overview</span></span>

<span data-ttu-id="9db95-115">Microsoft 휴대폰 시스템에는 다음을 기준으로 특정 SBC (세션 경계 컨트롤러)로 전화를 보낼 수 있는 라우팅 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="9db95-116">호출 된 번호 패턴</span><span class="sxs-lookup"><span data-stu-id="9db95-116">The called number pattern</span></span> 
- <span data-ttu-id="9db95-117">호출 되는 특정 사용자와 전화 번호 패턴을 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="9db95-118">SBCs는 활성 및 백업으로 지정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="9db95-119">활성으로 구성 된 SBC를 특정 통화 경로에 대해 사용할 수 없는 경우에는 통화가 백업 SBC로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="9db95-120">음성 라우팅은 다음 요소로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="9db95-121">**음성 라우팅 정책** – 사용자 또는 여러 사용자에 게 할당할 수 있는 PSTN 용도를 위한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-121">**Voice routing policy** – A container for PSTN Usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="9db95-122">**Pstn** 사용 – 다른 음성 라우팅 정책에서 공유할 수 있는 음성 경로 및 PSTN 용도에 대 한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="9db95-123">**음성 경로** – 호출 번호가 패턴과 일치 하는 호출에 사용할 수 패턴과 온라인 PSTN 게이트웨이 집합을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-123">**Voice Routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="9db95-124">**온라인 PSTN 게이트웨이** -호출이 sbc를 통해 호출 될 때 적용 되는 구성을 저장 하는 sbc에 대 한 포인터로, (예: pai (정방향 P-어설션된-Identity) 또는 기본 설정 코덱). 음성 경로에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="9db95-125">예제 1: PSTN 사용량이 하나인 음성 라우팅</span><span class="sxs-lookup"><span data-stu-id="9db95-125">Example 1: Voice routing with one PSTN Usage</span></span>

<span data-ttu-id="9db95-126">다음 다이어그램은 통화 흐름에서 음성 라우팅 정책의 두 가지 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="9db95-127">**통화 흐름 1 (왼쪽):** 사용자가 + 1 425 XXX XX xx 또는 + 1 206 XXX XX XX에 전화를 거는 경우, 통화는 SBC sbc1.contoso.biz 또는 sbc2.contoso.biz로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="9db95-128">Sbc1.contoso.biz 나 sbc2.contoso.biz 모두 사용할 수 없는 경우에는 통화가 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="9db95-129">**통화 흐름 2 (오른쪽):** 사용자가 + 1 425 XXX XX xx 또는 + 1 206 XXX XX XX에 전화를 거는 경우, 통화는 먼저 SBC sbc1.contoso.biz 또는 sbc2.contoso.biz로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="9db95-130">두 SBC를 모두 사용할 수 없는 경우 우선 순위가 낮은 경로 (sbc3.contoso.biz 및 sbc4.contoso.biz)가 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="9db95-131">사용할 수 있는 SBCs 장치가 없으면 통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-131">If none of the SBCs are available, the call is dropped.</span></span> 

![음성 라우팅 정책 예제 표시](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="9db95-133">두 예제에서 음성 경로에 우선 순위를 할당 하는 동안 경로의 SBCs는 임의 순서 대로 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9db95-134">사용자에 게 Microsoft 통화 계획 라이선스가 없는 경우 예제 구성의 패턴 + 1 425 XXX XX xx 또는 + 1 206 XXX XX XX와 일치 하는 숫자를 제외한 모든 번호로 거는 호출이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="9db95-135">사용자에 게 통화 요금제 라이선스가 있는 경우이 통화는 Microsoft 호출 계획의 정책에 따라 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="9db95-136">Microsoft 통화 요금제는 Microsoft 통화 계획 라이선스를 사용 하 여 모든 사용자의 마지막 경로에 자동으로 적용 되며 추가 통화 라우팅 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="9db95-137">다음 다이어그램에 표시 된 예제에서는 다른 모든 미국 및 캐나다 번호로 전화를 보낼 수 있는 음성 경로가 추가 됩니다 (호출 되는 번호 패턴 + 1 XXX XXX XX XX (으)로 이동 하는 호출).</span><span class="sxs-lookup"><span data-stu-id="9db95-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![세 번째 경로가 있는 음성 라우팅 정책 표시](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="9db95-139">다른 모든 통화:</span><span class="sxs-lookup"><span data-stu-id="9db95-139">For all other calls:</span></span>

- <span data-ttu-id="9db95-140">사용자에 게 라이선스 (Microsoft 전화 시스템 및 Microsoft 호출 계획)가 둘 다 있는 경우 자동 경로가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="9db95-141">관리자가 만든 온라인 음성 경로의 숫자 패턴과 일치 하는 항목이 없는 경우 통화는 Microsoft 통화 요금제를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="9db95-142">사용자에 게 Microsoft 전화 시스템만 있는 경우에는 일치 하는 규칙을 사용할 수 없기 때문에 통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9db95-143">패턴 + 1 XXX XXX XX XX와 일치 하는 경로만 있으므로이 경우 경로 "Other + 1"에 대 한 우선 순위 값은 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-143">The Priority value for route "Other +1" doesn’t matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="9db95-144">사용자가 + 1 324 567 89 89를 호출 하 고 sbc5.contoso.biz 및 sbc6.contoso.biz를 모두 사용할 수 없는 경우 통화가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="9db95-145">다음 표에는 세 가지 음성 경로를 사용 하는 구성이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="9db95-146">이 예제에서는 세 개의 경로가 모두 동일한 PSTN 사용 인 "미국 및 캐나다"의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-146">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>  <span data-ttu-id="9db95-147">모든 경로는 PSTN 사용 "미국 및 캐나다"와 연결 되며, PSTN 사용은 음성 라우팅 정책 "미국 전용"과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-147">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> 

|<span data-ttu-id="9db95-148">**PSTN 사용**</span><span class="sxs-lookup"><span data-stu-id="9db95-148">**PSTN usage**</span></span>|<span data-ttu-id="9db95-149">**음성 경로**</span><span class="sxs-lookup"><span data-stu-id="9db95-149">**Voice route**</span></span>|<span data-ttu-id="9db95-150">**번호 패턴**</span><span class="sxs-lookup"><span data-stu-id="9db95-150">**Number pattern**</span></span>|<span data-ttu-id="9db95-151">**중요도**</span><span class="sxs-lookup"><span data-stu-id="9db95-151">**Priority**</span></span>|<span data-ttu-id="9db95-152">**하더라도**</span><span class="sxs-lookup"><span data-stu-id="9db95-152">**SBC**</span></span>|<span data-ttu-id="9db95-153">**설명**</span><span class="sxs-lookup"><span data-stu-id="9db95-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9db95-154">미국만</span><span class="sxs-lookup"><span data-stu-id="9db95-154">US only</span></span>|<span data-ttu-id="9db95-155">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="9db95-155">"Redmond 1"</span></span>|<span data-ttu-id="9db95-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="9db95-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9db95-157">1</span><span class="sxs-lookup"><span data-stu-id="9db95-157">1</span></span>|<span data-ttu-id="9db95-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="9db95-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="9db95-160">호출 되는 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX의 활성 경로</span><span class="sxs-lookup"><span data-stu-id="9db95-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9db95-161">미국만</span><span class="sxs-lookup"><span data-stu-id="9db95-161">US only</span></span>|<span data-ttu-id="9db95-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="9db95-162">"Redmond 2"</span></span>|<span data-ttu-id="9db95-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="9db95-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9db95-164">2</span><span class="sxs-lookup"><span data-stu-id="9db95-164">2</span></span>|<span data-ttu-id="9db95-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="9db95-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="9db95-167">호출 되는 번호에 대 한 백업 경로 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="9db95-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9db95-168">미국만</span><span class="sxs-lookup"><span data-stu-id="9db95-168">US only</span></span>|<span data-ttu-id="9db95-169">"기타 + 1"</span><span class="sxs-lookup"><span data-stu-id="9db95-169">"Other +1"</span></span>|<span data-ttu-id="9db95-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="9db95-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="9db95-171">3</span><span class="sxs-lookup"><span data-stu-id="9db95-171">3</span></span>|<span data-ttu-id="9db95-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="9db95-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="9db95-174">호출 되는 번호에 대 한 경로 + 1 XXX XXX XX XX (+ 1 425 XXX xx xx 또는 + 1 206 XXX XX xx 제외)</span><span class="sxs-lookup"><span data-stu-id="9db95-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||


### <a name="example-1-configuration-steps"></a><span data-ttu-id="9db95-175">예제 1: 구성 단계</span><span class="sxs-lookup"><span data-stu-id="9db95-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="9db95-176">다음 예제에서는 다음을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-176">The following example shows how to:</span></span>

- <span data-ttu-id="9db95-177">단일 PSTN 사용 만들기</span><span class="sxs-lookup"><span data-stu-id="9db95-177">Create a single PSTN Usage</span></span> 
- <span data-ttu-id="9db95-178">세 가지 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="9db95-178">Configure three voice routes</span></span>
- <span data-ttu-id="9db95-179">음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9db95-179">Create a voice routing policy</span></span>
- <span data-ttu-id="9db95-180">사용자 Spencer 낮음으로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9db95-180">Assign the policy to user Spencer Low</span></span>

<span data-ttu-id="9db95-181">**1 단계:** PSTN 사용량 "미국 및 캐나다" 만들기</span><span class="sxs-lookup"><span data-stu-id="9db95-181">**Step 1:** Create the PSTN Usage "US and Canada"</span></span>

<span data-ttu-id="9db95-182">비즈니스용 Skype 원격 PowerShell 세션에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-182">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="9db95-183">다음을 입력 하 여 사용이 생성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-183">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="9db95-184">다음은 잘릴 수 있는 이름 목록을 반환 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-184">Which returns a list of names that may be truncated:</span></span>
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="9db95-185">다음 예제에서는 PowerShell 명령을 `(Get-CSOnlinePSTNUsage).usage` 실행 하 여 전체 이름을 표시 하는 결과를 보여 줍니다 (잘리지 않음).</span><span class="sxs-lookup"><span data-stu-id="9db95-185">The example below shows the result of  running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated):</span></span>

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

<span data-ttu-id="9db95-186">**2 단계:** 비즈니스용 Skype Online의 PowerShell 세션에서 앞의 표에 나와 있는 것 처럼 Redmond 1, 레드먼드 2, 기타 + 1의 세 가지 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-186">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as shown in the previous table</span></span>

<span data-ttu-id="9db95-187">"Redmond 1" 경로를 만들려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-187">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="9db95-188">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="9db95-188">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="9db95-189">Redmond 2 경로를 만들려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-189">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="9db95-190">다른 + 1 경로를 만들려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-190">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="9db95-191">번호 패턴 특성의 정규식이 유효한 식 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-191">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="9db95-192">이 웹 사이트를 사용 하 여 테스트할 수 있습니다.[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="9db95-192">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="9db95-193">일부 경우에는 동일한 SBC에 대 한 모든 통화를 라우팅할 필요가 있습니다. -번호 사용 패턴 ". \*"</span><span class="sxs-lookup"><span data-stu-id="9db95-193">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="9db95-194">모든 통화를 동일한 SBC로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-194">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="9db95-195">다음과 같이 옵션을 사용 하 여 `Get-CSOnlineVoiceRoute` PowerShell 명령을 실행 하 여 경로를 올바르게 구성 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-195">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="9db95-196">다음을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-196">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="9db95-197">이 예제에서 경로 "Other + 1"에 우선 순위 4가 자동으로 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-197">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="9db95-198">**3 단계:** 음성 라우팅 정책 "미국 전용"을 만들고 PSTN 사용량 "미국 및 캐나다"를 정책에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-198">**Step 3:** Create a voice routing policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="9db95-199">비즈니스용 Skype Online의 PowerShell 세션에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-199">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="9db95-200">결과는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-200">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="9db95-201">**4 단계:** PowerShell을 사용 하 여 사용자에 게 음성 라우팅 정책을 Spencer 낮음으로 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-201">**Step 4:** By using PowerShell, grant the voice routing policy to the user Spencer Low:</span></span>

<span data-ttu-id="9db95-202">비즈니스용 Skype Online의 PowerShell 세션에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-202">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="9db95-203">다음 명령을 입력 하 여 정책 할당의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-203">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="9db95-204">이 명령은 다음을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-204">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="9db95-205">예제 2: 여러 PSTN 용도를 사용 하는 음성 라우팅</span><span class="sxs-lookup"><span data-stu-id="9db95-205">Example 2: Voice routing with multiple PSTN Usages</span></span>

<span data-ttu-id="9db95-206">예 1에서 만든 음성 라우팅 정책은 Microsoft 통화 계획 라이선스가 사용자에 게 할당 되지 않는 이상 미국 및 캐나다의 전화 번호로만 통화 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-206">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="9db95-207">다음 예제에서는 음성 라우팅 정책 "제한 없음"을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-207">In the example that follows, you can create the voice routing policy "No Restrictions."</span></span> <span data-ttu-id="9db95-208">이 정책은 예제 1에서 만든 PSTN 사용량 "미국 및 캐나다"와 새로운 PSTN 사용량 "국제"를 재사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-208">The policy reuses the PSTN Usage "US and Canada" created in Example 1, as well as the new PSTN Usage "International."</span></span>  <span data-ttu-id="9db95-209">이 정책은 SBCs sbc2.contoso.biz 및 sbc5.contoso.biz에 대 한 다른 모든 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-209">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> 

<span data-ttu-id="9db95-210">표시 되는 예제에서는 사용자에 대 한 US 전용 정책만, 사용자에 게는 제한 사항 없음 정책, Spencer John 숲에는 다음과 같이 라우팅이 발생 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-210">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="9db95-211">Spencer 낮음 – 미국 전용 정책.</span><span class="sxs-lookup"><span data-stu-id="9db95-211">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="9db95-212">통화는 미국 및 캐나다 번호로만 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-212">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="9db95-213">Redmond 번호 범위로 전화를 거는 경우 특정 SBCs 집합을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-213">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="9db95-214">통화 요금제 라이선스가 사용자에 게 할당 되지 않으면 미국 이외의 번호는 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-214">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="9db95-215">John 숲 – 국제 정책.</span><span class="sxs-lookup"><span data-stu-id="9db95-215">John Woods – International policy.</span></span>  <span data-ttu-id="9db95-216">모든 숫자가 통화에 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-216">Calls are allowed to any number.</span></span> <span data-ttu-id="9db95-217">Redmond 번호 범위로 전화를 거는 경우 특정 SBCs 집합을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-217">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="9db95-218">미국 이외의 번호는 sbc2.contoso.biz 및 sbc5.contoso.biz를 사용 하 여 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-218">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![사용자 Spencer 낮음으로 지정 된 음성 라우팅 정책을 표시 합니다.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="9db95-220">다른 모든 통화에 대해 사용자에 게 라이선스 (Microsoft 전화 시스템 및 Microsoft 호출 계획)가 둘 다 있는 경우 자동 경로가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-220">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="9db95-221">관리자가 만든 온라인 음성 경로의 번호 패턴에 일치 하는 항목이 없는 경우에는 Microsoft 통화 요금제를 사용 하 여 통화가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-221">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="9db95-222">사용자에 게 Microsoft 전화 시스템만 있는 경우에는 일치 하는 규칙이 없기 때문에 통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-222">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![사용자에 게 할당 된 음성 라우팅 정책 표시, John 숲](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="9db95-224">다음 표에서는 라우팅 정책 "제한 없음" 사용 현황 및 음성 경로를 요약 하 여 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-224">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="9db95-225">**PSTN 사용**</span><span class="sxs-lookup"><span data-stu-id="9db95-225">**PSTN usage**</span></span>|<span data-ttu-id="9db95-226">**음성 경로**</span><span class="sxs-lookup"><span data-stu-id="9db95-226">**Voice route**</span></span>|<span data-ttu-id="9db95-227">**번호 패턴**</span><span class="sxs-lookup"><span data-stu-id="9db95-227">**Number pattern**</span></span>|<span data-ttu-id="9db95-228">**중요도**</span><span class="sxs-lookup"><span data-stu-id="9db95-228">**Priority**</span></span>|<span data-ttu-id="9db95-229">**하더라도**</span><span class="sxs-lookup"><span data-stu-id="9db95-229">**SBC**</span></span>|<span data-ttu-id="9db95-230">**설명**</span><span class="sxs-lookup"><span data-stu-id="9db95-230">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9db95-231">미국만</span><span class="sxs-lookup"><span data-stu-id="9db95-231">US Only</span></span>|<span data-ttu-id="9db95-232">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="9db95-232">"Redmond 1"</span></span>|<span data-ttu-id="9db95-233">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="9db95-233">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9db95-234">1</span><span class="sxs-lookup"><span data-stu-id="9db95-234">1</span></span>|<span data-ttu-id="9db95-235">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-235">sbc1.contoso.biz</span></span><br/><span data-ttu-id="9db95-236">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-236">sbc2.contoso.biz</span></span>|<span data-ttu-id="9db95-237">호출 수신자 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX의 활성 경로</span><span class="sxs-lookup"><span data-stu-id="9db95-237">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9db95-238">미국만</span><span class="sxs-lookup"><span data-stu-id="9db95-238">US Only</span></span>|<span data-ttu-id="9db95-239">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="9db95-239">"Redmond 2"</span></span>|<span data-ttu-id="9db95-240">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="9db95-240">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9db95-241">2</span><span class="sxs-lookup"><span data-stu-id="9db95-241">2</span></span>|<span data-ttu-id="9db95-242">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-242">sbc3.contoso.biz</span></span><br/><span data-ttu-id="9db95-243">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-243">sbc4.contoso.biz</span></span>|<span data-ttu-id="9db95-244">호출 수신자 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX에 대 한 백업 경로</span><span class="sxs-lookup"><span data-stu-id="9db95-244">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9db95-245">미국만</span><span class="sxs-lookup"><span data-stu-id="9db95-245">US Only</span></span>|<span data-ttu-id="9db95-246">"기타 + 1"</span><span class="sxs-lookup"><span data-stu-id="9db95-246">"Other +1"</span></span>|<span data-ttu-id="9db95-247">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="9db95-247">^\\+1(\d{10})$</span></span>|<span data-ttu-id="9db95-248">3</span><span class="sxs-lookup"><span data-stu-id="9db95-248">3</span></span>|<span data-ttu-id="9db95-249">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-249">sbc5.contoso.biz</span></span><br/><span data-ttu-id="9db95-250">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-250">sbc6>.contoso.biz</span></span>|<span data-ttu-id="9db95-251">호출 수신자 번호 + 1 XXX XXX XX XX (+ 1 425 XXX xx xx 또는 + 1 206 XXX XX xx 제외)의 경로</span><span class="sxs-lookup"><span data-stu-id="9db95-251">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="9db95-252">국제화</span><span class="sxs-lookup"><span data-stu-id="9db95-252">International</span></span>|<span data-ttu-id="9db95-253">국제화</span><span class="sxs-lookup"><span data-stu-id="9db95-253">International</span></span>|<span data-ttu-id="9db95-254">\d +</span><span class="sxs-lookup"><span data-stu-id="9db95-254">\d+</span></span>|<span data-ttu-id="9db95-255">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="9db95-255">4</span></span>|<span data-ttu-id="9db95-256">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-256">sbc2.contoso.biz</span></span><br/><span data-ttu-id="9db95-257">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9db95-257">sbc5.contoso.biz</span></span>|<span data-ttu-id="9db95-258">임의의 숫자 패턴에 대 한 라우팅</span><span class="sxs-lookup"><span data-stu-id="9db95-258">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="9db95-259">음성 라우팅 정책의 PSTN 사용량 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-259">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="9db95-260">용도는 순서 대로 적용 되며 첫 번째 사용에서 일치 하는 항목을 찾은 경우 다른 용도는 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-260">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="9db95-261">Pstn 사용 "국제"는 PSTN 사용량 "미국 전용" 뒤에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-261">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="9db95-262">PSTN 사용량의 순서를 변경 하려면 `Set-CSOnlineVoiceRoutingPolicy` 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-262">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="9db95-263">예를 들어 "미국 및 캐나다"의 순서와 역순으로 "국제" 초를 순서 대로 변경 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-263">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="9db95-264">"기타 + 1" 및 "국제" 음성 경로에 대 한 우선 순위는 자동으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-264">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="9db95-265">"Redmond 1" 및 "Redmond 2" 보다 우선 순위가 낮은 경우에는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-265">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>


### <a name="example-2-configuration-steps"></a><span data-ttu-id="9db95-266">예제 2: 구성 단계</span><span class="sxs-lookup"><span data-stu-id="9db95-266">Example 2: Configuration steps</span></span>

<span data-ttu-id="9db95-267">다음 예제에서는 다음을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-267">The following example shows how to:</span></span>

- <span data-ttu-id="9db95-268">국제 표준 이라는 새 PSTN 사용 만들기</span><span class="sxs-lookup"><span data-stu-id="9db95-268">Create a new PSTN Usage called International</span></span>
- <span data-ttu-id="9db95-269">국제 새 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="9db95-269">Create a new voice route called International</span></span>
- <span data-ttu-id="9db95-270">음성 라우팅 정책 만들기 제한 사항 없음</span><span class="sxs-lookup"><span data-stu-id="9db95-270">Create a voice routing policy called No Restrictions</span></span>
- <span data-ttu-id="9db95-271">사용자에 게 정책 할당 John 숲</span><span class="sxs-lookup"><span data-stu-id="9db95-271">Assign the policy to user John Woods</span></span>


<span data-ttu-id="9db95-272">**1 단계**: PSTN 사용량 "국제"를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-272">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="9db95-273">비즈니스용 Skype Online의 원격 PowerShell 세션에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-273">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="9db95-274">**2 단계**: "국제" 새 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="9db95-274">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="9db95-275">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="9db95-275">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="9db95-276">**3 단계**: 음성 라우팅 정책 "제한 없음"을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-276">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="9db95-277">PSTN 사용 "Redmond 1" 및 "Redmond"는 전화 번호 "+ 1 425 XXX xx" 및 "+ 1 206 XXX XX XX"를 로컬 또는 온-프레미스 통화로 하는 특별 한 처리를 유지 하기 위해이 음성 라우팅 정책에 재사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-277">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="9db95-278">PSTN 사용 순서를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-278">Take note of the order of PSTN Usages:</span></span>

  <span data-ttu-id="9db95-279">에서.</span><span class="sxs-lookup"><span data-stu-id="9db95-279">a.</span></span> <span data-ttu-id="9db95-280">다음 예제와 같이 구성 된 사용량으로 "+ 1 425 XXX XX"로 전화를 걸고 나면 통화는 "미국 및 캐나다" 사용에 설정 된 경로를 따르고 특별 한 라우팅 논리가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-280">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="9db95-281">즉, 통화가 먼저 sbc1.contoso.biz 및 sbc2.contoso.biz를 사용 하 여 라우팅된 다음 백업 경로로 sbc3.contoso.biz 및 sbc4.contoso.biz 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-281">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  <span data-ttu-id="9db95-282">b.</span><span class="sxs-lookup"><span data-stu-id="9db95-282">b.</span></span> <span data-ttu-id="9db95-283">"국제" PSTN 사용이 "미국 및 캐나다" 보다 앞에 있는 경우 + 1 425 XXX XX XX로 거는 호출은 라우팅 논리의 일부로 sbc2.contoso.biz 및 sbc5.contoso.biz로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-283">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="9db95-284">명령 입력:</span><span class="sxs-lookup"><span data-stu-id="9db95-284">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="9db95-285">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="9db95-285">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

<span data-ttu-id="9db95-286">**4 단계**: 다음 명령을 사용 하 여 사용자 "John 숲"에 음성 라우팅 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-286">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="9db95-287">그런 다음 명령을 사용 하 여 과제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-287">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="9db95-288">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="9db95-288">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="9db95-289">결과적으로 John 숲의 통화에 적용 되는 음성 정책에는 제한이 없으며 미국, 캐나다, 국제 통화를 위해 제공 되는 통화 라우팅의 논리에 따라 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db95-289">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>



## <a name="see-also"></a><span data-ttu-id="9db95-290">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9db95-290">See also</span></span>

[<span data-ttu-id="9db95-291">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="9db95-291">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="9db95-292">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="9db95-292">Configure Direct Routing</span></span>](direct-routing-configure.md)
