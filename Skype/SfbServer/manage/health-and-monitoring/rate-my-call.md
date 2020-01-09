---
title: 비즈니스용 Skype 서버에서 내 통화 평가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: '요약: 비즈니스용 Skype 서버의 통화 속도 평가 기능에 대해 알아보세요.'
ms.openlocfilehash: 6902bdaa9b5021963d128bf67dab7adc8ab1d982
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991743"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="bb2ec-103">비즈니스용 Skype 서버에서 내 통화 평가</span><span class="sxs-lookup"><span data-stu-id="bb2ec-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="bb2ec-104">**요약:** 비즈니스용 Skype 서버의 통화 속도 평가 기능에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="bb2ec-105">통화 요금 비즈니스용 Skype 2015 및 2016 클라이언트가 최종 사용자의 피드백을 받을 수 있는 방법을 제공 하는 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="bb2ec-106">내 통화 속도 창에는 "별" 등급 시스템 및 오디오 및 비디오 통화를 위해 미리 정의 된 토큰이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="bb2ec-107">또한 관리자는 사용자 지정 필드를 사용 하 여 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="bb2ec-108">수집 된 요금 내 통화 데이터가 기존 모니터링 보고서에 포함 되어 있지 않은 경우에는 별도의 모니터링 보고서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="bb2ec-109">데이터는 sql 쿼리를 실행 하 여 액세스할 수 있는 SQL 테이블로 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="bb2ec-110">내 통화 선행 조건 평가</span><span class="sxs-lookup"><span data-stu-id="bb2ec-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="bb2ec-111">비즈니스용 Skype 서버 배포의 사용자가 내 통화 기능에 액세스할 수 있으려면 먼저 다음 구성 요소 집합을 배포 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="bb2ec-112">Skype for Business Server가 설치 되어 있어야 합니다 (버전 9160 이상).</span><span class="sxs-lookup"><span data-stu-id="bb2ec-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="bb2ec-113">사용자에 게 비즈니스용 Skype의 최신 버전을 설치 하 고 업데이트 하 여 비즈니스용 skype UI를 사용 하도록 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="bb2ec-114">사용자는 비즈니스용 Skype 서버 프런트 엔드 풀에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="bb2ec-115">비즈니스용 skype 서버에 대 한 모니터링 데이터베이스가 배포 되 고 해당 비즈니스 서버에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="bb2ec-116">CQD (통화 품질 대시보드)를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="bb2ec-117">통화 요금 구성</span><span class="sxs-lookup"><span data-stu-id="bb2ec-117">Configure Rate my Call</span></span>

<span data-ttu-id="bb2ec-118">다음 설정을 사용 하 여 클라이언트 정책에서 내 통화 속도 평가 기능이 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="bb2ec-119">통화 표시 비율-10%</span><span class="sxs-lookup"><span data-stu-id="bb2ec-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="bb2ec-120">통화 요금 사용자 지정 사용자 피드백 허용-사용 안 함</span><span class="sxs-lookup"><span data-stu-id="bb2ec-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="bb2ec-121">기본 기능을 사용 하도록 설정 하는 데 필요한 작업은 없지만 사용자 지정 피드백을 원하는 경우 별도로 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="bb2ec-122">다음 Windows PowerShell cmdlet은 사용자 지정 최종 사용자 피드백을 사용 하도록 설정 하 고 간격을 10%에서 80%로 변경 하는 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="bb2ec-123">내 통화 데이터 속도에 액세스</span><span class="sxs-lookup"><span data-stu-id="bb2ec-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="bb2ec-124">사용자의 데이터는 모니터링 데이터베이스의 두 테이블에 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="bb2ec-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -이 표에는 최종 사용자의 토큰 폴링 결과가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="bb2ec-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -이 표에는 토큰 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="bb2ec-127">토큰 정의는 다음과 같이 코딩 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bb2ec-128">1</span><span class="sxs-lookup"><span data-stu-id="bb2ec-128">1</span></span>  <br/> |<span data-ttu-id="bb2ec-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="bb2ec-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="bb2ec-130">2</span><span class="sxs-lookup"><span data-stu-id="bb2ec-130">2</span></span>  <br/> | <span data-ttu-id="bb2ec-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="bb2ec-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="bb2ec-132">3</span><span class="sxs-lookup"><span data-stu-id="bb2ec-132">3</span></span>  <br/> | <span data-ttu-id="bb2ec-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="bb2ec-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="bb2ec-134">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="bb2ec-134">4</span></span>  <br/> |<span data-ttu-id="bb2ec-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="bb2ec-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="bb2ec-136">5mb</span><span class="sxs-lookup"><span data-stu-id="bb2ec-136">5</span></span>  <br/> |<span data-ttu-id="bb2ec-137">O</span><span class="sxs-lookup"><span data-stu-id="bb2ec-137">Echo</span></span>  <br/> |
|<span data-ttu-id="bb2ec-138">mb</span><span class="sxs-lookup"><span data-stu-id="bb2ec-138">21</span></span>  <br/> | <span data-ttu-id="bb2ec-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="bb2ec-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="bb2ec-140">khz</span><span class="sxs-lookup"><span data-stu-id="bb2ec-140">22</span></span>  <br/> | <span data-ttu-id="bb2ec-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="bb2ec-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="bb2ec-142">gb</span><span class="sxs-lookup"><span data-stu-id="bb2ec-142">23</span></span>  <br/> | <span data-ttu-id="bb2ec-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="bb2ec-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="bb2ec-144">fps</span><span class="sxs-lookup"><span data-stu-id="bb2ec-144">24</span></span>  <br/> | <span data-ttu-id="bb2ec-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="bb2ec-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="bb2ec-146">km</span><span class="sxs-lookup"><span data-stu-id="bb2ec-146">25</span></span>  <br/> | <span data-ttu-id="bb2ec-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="bb2ec-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="bb2ec-148">101</span><span class="sxs-lookup"><span data-stu-id="bb2ec-148">101</span></span>  <br/> |<span data-ttu-id="bb2ec-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="bb2ec-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="bb2ec-150">102</span><span class="sxs-lookup"><span data-stu-id="bb2ec-150">102</span></span>  <br/> |<span data-ttu-id="bb2ec-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="bb2ec-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="bb2ec-152">103</span><span class="sxs-lookup"><span data-stu-id="bb2ec-152">103</span></span>  <br/> |<span data-ttu-id="bb2ec-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="bb2ec-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="bb2ec-154">104</span><span class="sxs-lookup"><span data-stu-id="bb2ec-154">104</span></span>  <br/> |<span data-ttu-id="bb2ec-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="bb2ec-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="bb2ec-156">105</span><span class="sxs-lookup"><span data-stu-id="bb2ec-156">105</span></span>  <br/> |<span data-ttu-id="bb2ec-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="bb2ec-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="bb2ec-158">106</span><span class="sxs-lookup"><span data-stu-id="bb2ec-158">106</span></span>  <br/> |<span data-ttu-id="bb2ec-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="bb2ec-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="bb2ec-160">107</span><span class="sxs-lookup"><span data-stu-id="bb2ec-160">107</span></span>  <br/> |<span data-ttu-id="bb2ec-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="bb2ec-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="bb2ec-162">108</span><span class="sxs-lookup"><span data-stu-id="bb2ec-162">108</span></span>  <br/> |<span data-ttu-id="bb2ec-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="bb2ec-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="bb2ec-164">109</span><span class="sxs-lookup"><span data-stu-id="bb2ec-164">109</span></span>  <br/> |<span data-ttu-id="bb2ec-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="bb2ec-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="bb2ec-166">201</span><span class="sxs-lookup"><span data-stu-id="bb2ec-166">201</span></span>  <br/> |<span data-ttu-id="bb2ec-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="bb2ec-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="bb2ec-168">202</span><span class="sxs-lookup"><span data-stu-id="bb2ec-168">202</span></span>  <br/> |<span data-ttu-id="bb2ec-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="bb2ec-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="bb2ec-170">203</span><span class="sxs-lookup"><span data-stu-id="bb2ec-170">203</span></span>  <br/> |<span data-ttu-id="bb2ec-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="bb2ec-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="bb2ec-172">204</span><span class="sxs-lookup"><span data-stu-id="bb2ec-172">204</span></span>  <br/> |<span data-ttu-id="bb2ec-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="bb2ec-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="bb2ec-174">205</span><span class="sxs-lookup"><span data-stu-id="bb2ec-174">205</span></span>  <br/> |<span data-ttu-id="bb2ec-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="bb2ec-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="bb2ec-176">206</span><span class="sxs-lookup"><span data-stu-id="bb2ec-176">206</span></span>  <br/> |<span data-ttu-id="bb2ec-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="bb2ec-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="bb2ec-178">207</span><span class="sxs-lookup"><span data-stu-id="bb2ec-178">207</span></span>  <br/> |<span data-ttu-id="bb2ec-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="bb2ec-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="bb2ec-180">208</span><span class="sxs-lookup"><span data-stu-id="bb2ec-180">208</span></span>  <br/> |<span data-ttu-id="bb2ec-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="bb2ec-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="bb2ec-182">301</span><span class="sxs-lookup"><span data-stu-id="bb2ec-182">301</span></span>  <br/> |<span data-ttu-id="bb2ec-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="bb2ec-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="bb2ec-184">401</span><span class="sxs-lookup"><span data-stu-id="bb2ec-184">401</span></span>  <br/> |<span data-ttu-id="bb2ec-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="bb2ec-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="bb2ec-186">402</span><span class="sxs-lookup"><span data-stu-id="bb2ec-186">402</span></span>  <br/> |<span data-ttu-id="bb2ec-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="bb2ec-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="bb2ec-188">403</span><span class="sxs-lookup"><span data-stu-id="bb2ec-188">403</span></span>  <br/> |<span data-ttu-id="bb2ec-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="bb2ec-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="bb2ec-190">404</span><span class="sxs-lookup"><span data-stu-id="bb2ec-190">404</span></span>  <br/> |<span data-ttu-id="bb2ec-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="bb2ec-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="bb2ec-192">405</span><span class="sxs-lookup"><span data-stu-id="bb2ec-192">405</span></span>  <br/> |<span data-ttu-id="bb2ec-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="bb2ec-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="bb2ec-194">406</span><span class="sxs-lookup"><span data-stu-id="bb2ec-194">406</span></span>  <br/> |<span data-ttu-id="bb2ec-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="bb2ec-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="bb2ec-196">407</span><span class="sxs-lookup"><span data-stu-id="bb2ec-196">407</span></span>  <br/> |<span data-ttu-id="bb2ec-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="bb2ec-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="bb2ec-198">408</span><span class="sxs-lookup"><span data-stu-id="bb2ec-198">408</span></span>  <br/> |<span data-ttu-id="bb2ec-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="bb2ec-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="bb2ec-200">501</span><span class="sxs-lookup"><span data-stu-id="bb2ec-200">501</span></span>  <br/> |<span data-ttu-id="bb2ec-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="bb2ec-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="bb2ec-202">502</span><span class="sxs-lookup"><span data-stu-id="bb2ec-202">502</span></span>  <br/> |<span data-ttu-id="bb2ec-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="bb2ec-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="bb2ec-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** 이 표에는 "Star" 투표의 폴링 결과와 고객 피드백이 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="bb2ec-205">**[Table.Name] query \* 에서 select** 를 사용 하거나 Microsoft SQL Server Management Studio를 사용 하 여 테이블의 데이터를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="bb2ec-206">다음 SQL 쿼리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="bb2ec-207">**오디오**</span><span class="sxs-lookup"><span data-stu-id="bb2ec-207">**Audio**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 <span data-ttu-id="bb2ec-208">**비디오만**</span><span class="sxs-lookup"><span data-stu-id="bb2ec-208">**Video**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a><span data-ttu-id="bb2ec-209">토큰 정의 업데이트</span><span class="sxs-lookup"><span data-stu-id="bb2ec-209">Updating Token Definitions</span></span>

<span data-ttu-id="bb2ec-210">최신 비즈니스용 Skype 클라이언트는 [QoeMetrics]에 없을 수 있는\> 새로운 문제 토큰 id (100)를 보고 합니다. [dbo]. [CallQualityFeedbackTokenDef] 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="bb2ec-211">최신 토큰 정의를 사용 하 여 데이터베이스 테이블을 업데이트 하려면 아래 SQL 명령을 Microsoft SQL Server Management Studio를 통해 모니터링 데이터베이스에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="bb2ec-212">이 명령은 [QoeMetrics]의 모든 항목을 바꿉니다. [dbo]. [CallQualityFeedbackTokenDef] 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ec-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


