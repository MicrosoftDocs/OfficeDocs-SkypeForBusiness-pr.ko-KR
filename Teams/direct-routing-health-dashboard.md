---
title: 직접 라우팅에 대한 상태 대시보드
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 상태 대시보드를 사용하여 세션 테두리 컨트롤러와 직접 라우팅 간의 연결을 모니터링하는 방법을 배워야 합니다.
ms.openlocfilehash: a75510340815489921a5dd67a204b6914a9539d4
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45229114"
---
# <a name="health-dashboard-for-direct-routing"></a><span data-ttu-id="f181e-103">직접 라우팅에 대한 상태 대시보드</span><span class="sxs-lookup"><span data-stu-id="f181e-103">Health Dashboard for Direct Routing</span></span>

<span data-ttu-id="f181e-104">직접 라우팅에 대한 상태 대시보드를 사용하면 SBC(세션 테두리 컨트롤러)와 직접 라우팅 인터페이스 간의 연결을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-104">Health Dashboard for Direct Routing lets you monitor the connection between your Session Border Controller (SBC) and the Direct Routing interface.</span></span>  <span data-ttu-id="f181e-105">상태 대시보드를 사용하여 SBC, 전화 통신 서비스 및 SBC와 직접 라우팅 인터페이스 간의 네트워크 매개 변수에 대한 정보를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-105">With Health Dashboard, you can monitor information about your SBC, the telephony service, and the network parameters between your SBC and the Direct Routing interface.</span></span> <span data-ttu-id="f181e-106">이 정보는 호출이 떨어진 이유를 포함하여 문제를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="f181e-107">예를 들어 SBC의 인증서가 만료되었거나 네트워크 문제가 있는 경우 SBC에서 호출 전송을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-107">For example, the SBC might stop sending calls if a certificate on the SBC has expired or if there are network issues.</span></span> <span data-ttu-id="f181e-108">상태 [대시보드에 대한 액세스](using-admin-roles.md) 권한이 있는 사용자에 대한 자세한 내용은 관리자 역할을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f181e-108">See the [admin roles](using-admin-roles.md) to learn who has access to the health dashboard.</span></span>

<span data-ttu-id="f181e-109">상태 대시보드는 두 가지 수준의 정보를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-109">Health Dashboard monitors two levels of information:</span></span>

- <span data-ttu-id="f181e-110">연결된 SBC의 전반적인 상태</span><span class="sxs-lookup"><span data-stu-id="f181e-110">Overall health of the connected SBCs</span></span>
- <span data-ttu-id="f181e-111">연결된 SBC에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="f181e-111">Detailed information about the connected SBCs</span></span>

<span data-ttu-id="f181e-112">Microsoft Teams 및 비즈니스용 Skype 관리 센터에서 상태 대시보드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-112">You can view Health Dashboard in the Microsoft Teams and Skype for Business Admin Center.</span></span>

## <a name="overall-health"></a><span data-ttu-id="f181e-113">전반적인 상태</span><span class="sxs-lookup"><span data-stu-id="f181e-113">Overall health</span></span>

<span data-ttu-id="f181e-114">상태 대시보드는 연결된 SBC의 전반적인 상태와 관련된 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-114">Health Dashboard provides the following information related to overall health of the connected SBCs:</span></span>

 ![상태 대시보드 통계 표시](media/direct-routing-dashboard-stats1.png)

- <span data-ttu-id="f181e-116">**직접 라우팅 요약** - 시스템에 등록된 SBC의 총 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-116">**Direct Routing summary** - Shows the total number of SBCs registered in the system.</span></span> <span data-ttu-id="f181e-117">등록은 테넌트 관리자가 New-CsOnlinePSTNGateway 명령을 사용하여 SBC를 추가했다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-117">Registration means that the tenant administrator added an SBC by using the New-CsOnlinePSTNGateway command.</span></span> <span data-ttu-id="f181e-118">SBC가 PowerShell에 추가되지만 연결되지 않은 경우 상태 대시보드에 해당 SBC가 상태 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-118">If the SBC was added in PowerShell, but never connected, the Health Dashboard shows it in an unhealthy status.</span></span>

- <span data-ttu-id="f181e-119">**SBC** - 페어링된 SBC의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-119">**SBC** - The FQDN of the paired SBC.</span></span>

- <span data-ttu-id="f181e-120">**NER(네트워크** 효율성 비율) - NER는 수신자에게 전송된 호출 수와 받는 사람에게 전달된 호출 수를 측정하여 호출을 배달하는 네트워크의 기능을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-120">**Network Effectiveness Ratio (NER)** - The NER measures the ability of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>  

   <span data-ttu-id="f181e-121">NER는 최종 터미널에 대한 호출을 배달하는 네트워크의 기능을 측정합니다. 즉, 호출 거부를 초래하는 사용자 작업을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-121">The NER measures the ability of networks to deliver calls to the far-end terminal--excluding user actions resulting in call rejections.</span></span>  <span data-ttu-id="f181e-122">받는 사람이 통화를 거부하거나 음성 메일로 통화를 보낸 경우 통화는 성공적인 배달로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-122">If the recipient rejected a call or sent the call to voicemail, the call is counted as a successful delivery.</span></span> <span data-ttu-id="f181e-123">즉, 응답 메시지, 사용 중 신호 또는 응답이 없는 벨은 모두 성공적인 호출로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-123">This means that an answer message, a busy signal, or a ring with no answer are all considered successful calls.</span></span>
  
   <span data-ttu-id="f181e-124">예를 들어 직접 라우팅이 SBC에 대한 호출을 보내고 SBC가 SIP 코드 "504 서버 시간 제한 - 서버가 요청을 처리하려고 시도하고 프롬프트 응답을 받지 못했습니다."라는 SIP 코드를 반환했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-124">For example, assume Direct Routing sent a call to the SBC and the SBC returns SIP code “504 Server Time-out - The server attempted to access another server in attempting to process the request and did not receive a prompt response”.</span></span> <span data-ttu-id="f181e-125">이 응답은 SBC 쪽에 문제가 있으며 이 SBC의 상태 대시보드에서 NER가 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-125">This response indicates there is an issue on the SBC side, and this will decrease the NER on the Health Dashboard for this SBC.</span></span>
  
   <span data-ttu-id="f181e-126">수행되는 작업은 영향을 받는 호출 수에 따라 다를 수 있기 때문에 상태 대시보드에는 매개 변수를 계산하기 위해 분석된 호출 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-126">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span> <span data-ttu-id="f181e-127">호출 수가 100개 미만이면 NER가 매우 낮을 수 있지만 여전히 정상입니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-127">If the number of calls is less than 100, the NER might be quite low, but still be normal.</span></span>

   <span data-ttu-id="f181e-128">NER를 계산하는 데 사용되는 수식은</span><span class="sxs-lookup"><span data-stu-id="f181e-128">The formula used to calculate NER is:</span></span>

   <span data-ttu-id="f181e-129">NER = 100 x(응답 통화 + 사용자 사용 중 + 링 없음 응답 + 터미널 거부 발작)/총 호출</span><span class="sxs-lookup"><span data-stu-id="f181e-129">NER = 100 x (Answered calls + User Busy + Ring no Answer + Terminal Reject Seizures)/Total Calls</span></span>

- <span data-ttu-id="f181e-130">**평균 통화 기간** - 평균 통화 기간에 대한 정보는 통화 품질을 모니터링하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-130">**Average call duration** - Information about average call duration can help you monitor the quality of calls.</span></span> <span data-ttu-id="f181e-131">1:1 PSTN 호출의 평균 기간은 4~5분입니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-131">The average duration of a 1:1 PSTN call is four to five minutes.</span></span>  <span data-ttu-id="f181e-132">그러나 각 회사에 대해 이 평균은 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-132">However, for each company, this average can differ.</span></span>  <span data-ttu-id="f181e-133">Microsoft는 회사의 평균 호출 기간에 대한 기준을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-133">Microsoft recommends establishing a baseline for the average call duration for your company.</span></span> <span data-ttu-id="f181e-134">이 매개 변수가 기준보다 크게 낮아질 경우 사용자가 통화 품질 또는 안정성에 문제가 있으며 평소보다 일찍 중단된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-134">If this parameter goes significantly below the baseline, it might indicate that your users are having issues with call quality or reliability and are hanging up earlier than usual.</span></span> <span data-ttu-id="f181e-135">예를 들어 15초와 같은 평균 호출 기간이 매우 낮게 표시될 경우 서비스가 안정적으로 수행되지 못하기 때문에 호출자는 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-135">If you start seeing extremely low average call duration, for example 15 seconds, callers might be hanging up because your service is not performing reliably.</span></span>

   <span data-ttu-id="f181e-136">수행되는 작업은 영향을 받는 호출 수에 따라 다를 수 있기 때문에 상태 대시보드에는 매개 변수를 계산하기 위해 분석된 호출 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-136">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span>

- <span data-ttu-id="f181e-137">**TLS 연결 상태** - TLS(전송 계층 보안) 연결은 직접 라우팅과 SBC 간의 TLS 연결 상태를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-137">**TLS connectivity status** - TLS (Transport Layer Security) connectivity shows the status of the TLS connections between Direct Routing and the SBC.</span></span> <span data-ttu-id="f181e-138">또한 상태 대시보드는 인증서 만료 날짜를 분석하고 인증서가 30일 이내에 만료로 설정되어 있는 경우 경고를 표시하여 관리자가 서비스가 중단되기 전에 인증서를 갱신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-138">Health Dashboard also analyzes the certificate expiration date and warns if a certificate is set to expire within 30 days so that administrators can renew the certificate before service is disrupted.</span></span>

   <span data-ttu-id="f181e-139">경고 메시지를 클릭하면 오른쪽의 팝업 창에서 자세한 문제 설명과 문제를 해결하는 방법에 대한 권장 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-139">By clicking the Warning message, you can see a detailed issue description in a popup window on the right and recommendations for how to fix the issue.</span></span>

- <span data-ttu-id="f181e-140">**SIP 옵션 상태** – 기본적으로 SBC는 1분마다 옵션 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-140">**SIP options status** – By default, the SBC sends options messages every minute.</span></span> <span data-ttu-id="f181e-141">이 구성은 SBC 공급업체마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-141">This configuration can vary for different SBC vendors.</span></span> <span data-ttu-id="f181e-142">직접 라우팅은 SIP 옵션이 전송되지 않는지 또는 구성되지 않은지 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-142">Direct Routing warns if the SIP options are not sent or are not configured.</span></span> <span data-ttu-id="f181e-143">SIP 옵션 모니터링 및 SBC가 기능하지 않는 것으로 표시될 수 있는 조건에 대한 자세한 내용은 직접 라우팅 모니터링 및 문제 [해결을 참조하세요.](direct-routing-monitor-and-troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="f181e-143">For more information about SIP options monitoring, and conditions when an SBC can be marked as not functional, see [Monitor and troubleshoot Direct Routing](direct-routing-monitor-and-troubleshoot.md).</span></span>

- <span data-ttu-id="f181e-144">**자세한 SIP** 옵션 상태 - SIP 옵션 흐름에 문제가 있는 것으로 표시하는 것 외에도 상태 대시보드에서 오류에 대한 자세한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-144">**Detailed SIP options status** - In addition to showing that there is an issue with SIP options flow, the Health Dashboard also provides detailed descriptions of the errors.</span></span> <span data-ttu-id="f181e-145">"경고" 메시지를 클릭하여 설명에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-145">You can access the description by clicking the “Warning” message.</span></span> <span data-ttu-id="f181e-146">오른쪽의 팝업 창에 자세한 오류 설명이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-146">A pop-up window on the right will show the detailed error description.</span></span>

   <span data-ttu-id="f181e-147">SIP 옵션 상태 메시지에 사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-147">Possible values for SIP options status messages are as follows:</span></span>

    - <span data-ttu-id="f181e-148">활성 - SBC가 활성 상태입니다. Microsoft 직접 라우팅 서비스는 정기적으로 흐르는 옵션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-148">Active – The SBC is active--Microsoft Direct Routing service sees the options flowing on a regular interval.</span></span>

    - <span data-ttu-id="f181e-149">경고, SIP 옵션 없음 - 세션 테두리 컨트롤러가 데이터베이스에 존재합니다(관리자가 New-CsOnlinePSTNGateway 명령을 사용하여 생성).</span><span class="sxs-lookup"><span data-stu-id="f181e-149">Warning, no SIP options - The Session Border Controller exists in the database (your administrator created it using the command New-CsOnlinePSTNGateway).</span></span> <span data-ttu-id="f181e-150">SIP 옵션을 보내도록 구성되지만 직접 라우팅 서비스는 이 SBC에서 다시 오는 SIP 옵션을 본 적이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-150">It is configured to send SIP options, but the Direct Routing service never saw the SIP options coming back from this SBC.</span></span>

    - <span data-ttu-id="f181e-151">경고, SIP 메시지가 구성되지 않습니다. SIP 옵션을 사용하는 트렁크 모니터링이 켜져 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-151">Warning, SIP Messages aren't configured - Trunk monitoring using SIP options isn’t turned on.</span></span> <span data-ttu-id="f181e-152">Microsoft Calling System은 SIP 옵션 및 TLS(전송 계층 보안) 핸드사이크 모니터링을 사용하여 애플리케이션 수준에서 연결된 SBC(세션 테두리 컨트롤러)의 상태 감지</span><span class="sxs-lookup"><span data-stu-id="f181e-152">Microsoft Calling System uses SIP options and Transport Layer Security (TLS) handshake monitoring to detect the health of the connected Session Border Controllers (SBCs) at the application level.</span></span> <span data-ttu-id="f181e-153">이 트렁크를 네트워크 수준에서(ping으로) 도달할 수 있지만 인증서가 만료되었거나 SIP 스택이 작동하지 않는 경우 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-153">You’ll have problems if this trunk can be reached at the network level (by ping), but the certificate has expired or the SIP stack doesn’t work.</span></span> <span data-ttu-id="f181e-154">이러한 문제를 초기에 식별할 수 있도록 Microsoft는 SIP 전송 옵션을 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-154">To help identify such problems early, Microsoft recommends enabling sending SIP options.</span></span> <span data-ttu-id="f181e-155">SBC 제조업체 설명서를 확인하여 SIP 전송 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-155">Check your SBC manufacturer documentation to configure sending SIP options.</span></span>

- <span data-ttu-id="f181e-156">**동시** 호출 용량 - -MaxConcurrentSessions 매개 변수와 함께 New- 또는 Set-CsOnlinePSTNGateway 명령을 사용하여 SBC에서 처리할 수 있는 동시 호출의 제한을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-156">**Concurrent calls capacity** - You can specify the limit of concurrent calls that an SBC can handle by using the New- or Set-CsOnlinePSTNGateway command with the -MaxConcurrentSessions parameter.</span></span> <span data-ttu-id="f181e-157">이 매개 변수는 특정 SBC를 사용하여 직접 라우팅에서 보내거나 받은 호출 수를 계산하고 제한 집합과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-157">This parameter calculates how many calls were sent or received by Direct Routing using a specific SBC and compares it with the limit set.</span></span> <span data-ttu-id="f181e-158">참고: SBC가 다른 PBX에 대한 호출을 처리하는 경우 이 번호는 실제 동시 호출을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-158">Note:  If the SBC also handles calls to different PBXs, this number will not show the actual concurrent calls.</span></span>

## <a name="detailed-information-for-each-sbc"></a><span data-ttu-id="f181e-159">각 SBC에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="f181e-159">Detailed information for each SBC</span></span>

<span data-ttu-id="f181e-160">다음 스크린샷과 같이 특정 SBC에 대한 자세한 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-160">You can also view the detailed information for a specific SBC as shown in the following screenshot:</span></span>

![상태 대시보드 SBC 세부 정보](media/direct-routing-dashboard-SBC-detail1.png)

<span data-ttu-id="f181e-162">자세한 보기에는 다음과 같은 추가 매개 변수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-162">The detailed view shows the following additional parameters:</span></span>

- <span data-ttu-id="f181e-163">**TLS 연결 상태** – "전반적인 상태" 페이지에서와 동일한 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-163">**TLS Connectivity status** – this is the same metric as on the “Overall Health” page;</span></span>

- <span data-ttu-id="f181e-164">**TLS 연결 마지막 상태** – SBC가 직접 라우팅 서비스에 TLS 연결을 한 시간을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="f181e-164">**TLS Connectivity last status** – shows time when the SBC made a TLS connection to the Direct Routing service;</span></span>

- <span data-ttu-id="f181e-165">**SIP 옵션 상태** – "전반적인 상태" 페이지에서와 동일한 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-165">**SIP options status** – the same metric as on the “Overall Health” page.</span></span>

- <span data-ttu-id="f181e-166">**SIP 옵션이 마지막으로 선택된** 시간 - SIP 옵션이 마지막으로 수신된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-166">**SIP options last checked** – time when the SIP options were received last time.</span></span>

- <span data-ttu-id="f181e-167">**SBC 상태** – 모니터링되는 모든 매개 변수에 따라 SBC의 전체 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-167">**SBC status** – overall status of the SBC, based on all monitored parameters.</span></span>

- <span data-ttu-id="f181e-168">**동시 호출**- 처리된 SBC를 호출하는 동시 호출 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-168">**Concurrent call**- shows  how many concurrent calls the SBC handled.</span></span> <span data-ttu-id="f181e-169">이 정보는 필요한 동시 채널 수를 예측하고 추세를 보는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-169">This information is useful to predict the number of concurrent channels you need and see the trend.</span></span> <span data-ttu-id="f181e-170">일 수 및 호출 방향(인바운드/아웃바운드/모든 스트림)으로 데이터를 슬라이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-170">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

- <span data-ttu-id="f181e-171">**네트워크 매개** 변수 - 모든 네트워크 매개 변수는 직접 라우팅 인터페이스에서 세션 테두리 컨트롤러로 측정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-171">**Network parameters** - All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="f181e-172">권장 값에 대한 자세한 내용은 [Microsoft Teams에](https://docs.microsoft.com/microsoftteams/prepare-network)대한 조직의 네트워크 준비를 참조하고 고객 에지에서 Microsoft Edge로 권장되는 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-172">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

   - <span data-ttu-id="f181e-173">Jitter – RTCP(RTP 제어 프로토콜)를 사용하여 두 엔드포인트 간에 계산된 네트워크 전파 지연 시간의 변형을 밀리초 측정한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-173">Jitter – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

   - <span data-ttu-id="f181e-174">패킷 손실 – 도착하지 못한 패킷의 측정값입니다. 두 엔드포인트 간에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-174">Packet Loss – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

   - <span data-ttu-id="f181e-175">대기 시간 -(왕복 시간)은 신호가 전송되는 데 걸리는 시간과 해당 신호의 수신을 수신하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-175">Latency - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="f181e-176">이 시간 지연은 신호의 두 지점 사이의 전파 시간으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-176">This time delay consists of the propagation times between the two points of a signal.</span></span>

   <span data-ttu-id="f181e-177">일 수 및 호출 방향(인바운드/아웃바운드/모든 스트림)으로 데이터를 슬라이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-177">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

<span data-ttu-id="f181e-178">**네트워크 효과 비율** - 전체 상태 대시보드에 나타나는 매개 변수와 동일하지만, 데이터를 시간 계열 또는 호출 방향에 따라 분할하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f181e-178">**Network Effectiveness ratio** - This is the same parameter that appears on the Overall Health dashboard, but with the option to slice the data by time series or call direction.</span></span>
