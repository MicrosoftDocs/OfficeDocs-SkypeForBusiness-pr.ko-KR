---
title: 직접 라우팅에 대 한 상태 대시보드
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
description: 상태 대시보드를 사용 하 여 세션 경계 컨트롤러와 직접 라우팅 간의 연결을 모니터링 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 55ae433428a8bb6fd42d4166e5d756432463b4ed
ms.sourcegitcommit: 929c050c038a64216e38b0a67569a8f18ad4baf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43940745"
---
# <a name="health-dashboard-for-direct-routing"></a><span data-ttu-id="13c7f-103">직접 라우팅에 대 한 상태 대시보드</span><span class="sxs-lookup"><span data-stu-id="13c7f-103">Health Dashboard for Direct Routing</span></span>

<span data-ttu-id="13c7f-104">직접 라우팅에 대 한 상태 대시보드를 통해 SBC (세션 경계 컨트롤러) 및 직접 라우팅 인터페이스 간의 연결을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-104">Health Dashboard for Direct Routing lets you monitor the connection between your Session Border Controller (SBC) and the Direct Routing interface.</span></span>  <span data-ttu-id="13c7f-105">상태 대시보드를 사용 하 여 sbc, 전화 통신 서비스 및 SBC와 직접 라우팅 인터페이스 간의 네트워크 매개 변수에 대 한 정보를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-105">With Health Dashboard, you can monitor information about your SBC, the telephony service, and the network parameters between your SBC and the Direct Routing interface.</span></span> <span data-ttu-id="13c7f-106">이 정보는 통화 제거 사유를 포함 하 여 문제를 식별 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="13c7f-107">예를 들어 sbc의 인증서가 만료 되었거나 네트워크 문제가 있는 경우 SBC는 호출 보내기를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-107">For example, the SBC might stop sending calls if a certificate on the SBC has expired or if there are network issues.</span></span>  

<span data-ttu-id="13c7f-108">상태 대시보드는 두 가지 수준의 정보를 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-108">Health Dashboard monitors two levels of information:</span></span>

- <span data-ttu-id="13c7f-109">연결 된 SBCs의 전반적인 상태</span><span class="sxs-lookup"><span data-stu-id="13c7f-109">Overall health of the connected SBCs</span></span>
- <span data-ttu-id="13c7f-110">연결 된 SBCs에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="13c7f-110">Detailed information about the connected SBCs</span></span>

<span data-ttu-id="13c7f-111">Microsoft 팀 및 비즈니스용 Skype 관리 센터에서 상태 대시보드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-111">You can view Health Dashboard in the Microsoft Teams and Skype for Business Admin Center.</span></span>


## <a name="overall-health"></a><span data-ttu-id="13c7f-112">전반적인 상태</span><span class="sxs-lookup"><span data-stu-id="13c7f-112">Overall health</span></span>

<span data-ttu-id="13c7f-113">상태 대시보드는 연결 된 SBCs의 전체 상태와 관련 된 다음과 같은 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-113">Health Dashboard provides the following information related to overall health of the connected SBCs:</span></span>

 ![상태 대시보드 통계를 표시 합니다.](media/direct-routing-dashboard-stats1.png)

- <span data-ttu-id="13c7f-115">**다이렉트 라우팅 요약** -시스템에 등록 된 총 SBCs 수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-115">**Direct Routing summary** - Shows the total number of SBCs registered in the system.</span></span> <span data-ttu-id="13c7f-116">등록은 테 넌 트 관리자가 New-CsOnlinePSTNGateway 명령을 사용 하 여 SBC를 추가 했음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-116">Registration means that the tenant administrator added an SBC by using the New-CsOnlinePSTNGateway command.</span></span> <span data-ttu-id="13c7f-117">SBC이 PowerShell에 추가 되었지만 연결 되지 않은 경우 상태 대시보드에 상태가 비정상 상태로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-117">If the SBC was added in PowerShell, but never connected, the Health Dashboard shows it in an unhealthy status.</span></span>

- <span data-ttu-id="13c7f-118">**SBC** -쌍으로 된 SBC의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-118">**SBC** - The FQDN of the paired SBC.</span></span>

- <span data-ttu-id="13c7f-119">**네트워크 효율성 비율 (NER)** -NER는 받는 사람에 게 전달 되는 통화 수를 측정 하 여 전화를 전달 하는 네트워크의 기능을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-119">**Network Effectiveness Ratio (NER)** - The NER measures the ability of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>  

   <span data-ttu-id="13c7f-120">NER는 호출이 거부 되는 사용자 작업을 제외 하 고, 엔드 터미널에 대 한 호출을 제공 하는 네트워크의 기능을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-120">The NER measures the ability of networks to deliver calls to the far-end terminal--excluding user actions resulting in call rejections.</span></span>  <span data-ttu-id="13c7f-121">받는 사람이 전화를 걸거나 음성 메일로 전화를 보낸 경우, 통화가 성공적으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-121">If the recipient rejected a call or sent the call to voicemail, the call is counted as a successful delivery.</span></span> <span data-ttu-id="13c7f-122">즉, 응답 메시지, 통화 중 신호 또는 응답이 없는 고리는 모두 성공적인 통화를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-122">This means that an answer message, a busy signal, or a ring with no answer are all considered successful calls.</span></span> 
  
   <span data-ttu-id="13c7f-123">예를 들어 직접 라우팅이 SBC에 대 한 호출을 전송 했다고 가정 하 고 SBC는 SIP 코드 "504 서버 시간 초과-요청을 처리 하려고 시도 하는 서버가 다른 서버에 액세스 하려고 하 고 프롬프트 응답을 받지 못했습니다."</span><span class="sxs-lookup"><span data-stu-id="13c7f-123">For example, assume Direct Routing sent a call to the SBC and the SBC returns SIP code “504 Server Time-out - The server attempted to access another server in attempting to process the request and did not receive a prompt response”.</span></span> <span data-ttu-id="13c7f-124">이 응답은 SBC 측면에 문제가 있음을 나타내고,이를 통해이 SBC에 대 한 상태 대시보드의 NER 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-124">This response indicates there is an issue on the SBC side, and this will decrease the NER on the Health Dashboard for this SBC.</span></span> 
  
   <span data-ttu-id="13c7f-125">사용 하는 동작은 영향을 받는 호출 수에 따라 달라질 수 있으므로 상태 대시보드에는 매개 변수를 계산 하기 위해 분석 된 호출 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-125">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span> <span data-ttu-id="13c7f-126">통화 수가 100 보다 작은 경우 NER는 매우 낮을 수 있지만 여전히 정상입니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-126">If the number of calls is less than 100, the NER might be quite low, but still be normal.</span></span> 

   <span data-ttu-id="13c7f-127">NER 계산에 사용 되는 수식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-127">The formula used to calculate NER is:</span></span>

   <span data-ttu-id="13c7f-128">NER = 100 x (응답 통화 + 사용자 사용 중 + 반지 응답 없음 + 터미널 거부 발작)/총 통화</span><span class="sxs-lookup"><span data-stu-id="13c7f-128">NER = 100 x (Answered calls + User Busy + Ring no Answer + Terminal Reject Seizures)/Total Calls</span></span>

 
- <span data-ttu-id="13c7f-129">**평균 통화 기간** -평균 통화 시간에 대 한 정보는 통화 품질을 모니터링 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-129">**Average call duration** - Information about average call duration can help you monitor the quality of calls.</span></span> <span data-ttu-id="13c7f-130">1:1 PSTN 통화의 평균 기간은 4 ~ 5 분입니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-130">The average duration of a 1:1 PSTN call is four to five minutes.</span></span>  <span data-ttu-id="13c7f-131">그러나 각 회사에 대해이 평균이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-131">However, for each company, this average can differ.</span></span>  <span data-ttu-id="13c7f-132">Microsoft는 회사의 평균 통화 기간에 대 한 초기 계획을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-132">Microsoft recommends establishing a baseline for the average call duration for your company.</span></span> <span data-ttu-id="13c7f-133">이 매개 변수가 기준선 보다 크게 떨어지면 사용자에 게 통화 품질 또는 안정성 문제가 발생 하 여 평소 보다 이전 버전에 있는 것으로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-133">If this parameter goes significantly below the baseline, it might indicate that your users are having issues with call quality or reliability and are hanging up earlier than usual.</span></span> <span data-ttu-id="13c7f-134">15 초와 같이 매우 낮은 평균 통화 시간을 표시 하기 시작 하면 서비스가 안정적으로 수행 되지 않으므로 호출자가 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-134">If you start seeing extremely low average call duration, for example 15 seconds, callers might be hanging up because your service is not performing reliably.</span></span> 

   <span data-ttu-id="13c7f-135">사용 하는 동작은 영향을 받는 호출 수에 따라 달라질 수 있으므로 상태 대시보드에는 매개 변수를 계산 하기 위해 분석 된 호출 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-135">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span>

- <span data-ttu-id="13c7f-136">**Tls 연결 상태** -Tls (전송 계층 보안) 연결은 직접 라우팅과 SBC 간의 tls 연결 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-136">**TLS connectivity status** - TLS (Transport Layer Security) connectivity shows the status of the TLS connections between Direct Routing and the SBC.</span></span> <span data-ttu-id="13c7f-137">상태 대시보드는 또한 인증서 만료 날짜를 분석 하 고, 인증서가 30 일 내에 만료 되도록 설정 되어 있는지에 대 한 경고를 표시 하 고, 관리자가 서비스 중단 전에 인증서를 갱신할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-137">Health Dashboard also analyzes the certificate expiration date and warns if a certificate is set to expire within 30 days so that administrators can renew the certificate before service is disrupted.</span></span>

   <span data-ttu-id="13c7f-138">경고 메시지를 클릭 하면 팝업 창에서 자세한 문제 설명과 문제 해결 방법에 대 한 권장 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-138">By clicking the Warning message, you can see a detailed issue description in a popup window on the right and recommendations for how to fix the issue.</span></span>

- <span data-ttu-id="13c7f-139">**SIP 옵션 상태** – 기본적으로 SBC는 1 분 마다 옵션 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-139">**SIP options status** – By default, the SBC sends options messages every minute.</span></span> <span data-ttu-id="13c7f-140">이 구성은 SBC 공급 업체 마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-140">This configuration can vary for different SBC vendors.</span></span> <span data-ttu-id="13c7f-141">다이렉트 라우팅은 SIP 옵션이 전송 되지 않거나 구성 되어 있지 않은 경우에 경고 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-141">Direct Routing warns if the SIP options are not sent or are not configured.</span></span> <span data-ttu-id="13c7f-142">SIP 옵션 모니터링과 SBC가 작동 하지 않음으로 표시 될 수 있는 조건에 대 한 자세한 내용은 [직접 라우팅 모니터링 및 문제 해결](direct-routing-monitor-and-troubleshoot.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13c7f-142">For more information about SIP options monitoring, and conditions when an SBC can be marked as not functional, see [Monitor and troubleshoot Direct Routing](direct-routing-monitor-and-troubleshoot.md).</span></span>

- <span data-ttu-id="13c7f-143">**자세한 sip 옵션 상태** -sip 옵션 흐름에 문제가 있음을 표시 하는 것 외에도 상태 대시보드에서 오류에 대 한 자세한 설명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-143">**Detailed SIP options status** - In addition to showing that there is an issue with SIP options flow, the Health Dashboard also provides detailed descriptions of the errors.</span></span> <span data-ttu-id="13c7f-144">"경고" 메시지를 클릭 하 여 설명에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-144">You can access the description by clicking the “Warning” message.</span></span> <span data-ttu-id="13c7f-145">오른쪽의 팝업 창에 자세한 오류 설명이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-145">A pop-up window on the right will show the detailed error description.</span></span>

   <span data-ttu-id="13c7f-146">SIP 옵션 상태 메시지에 사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-146">Possible values for SIP options status messages are as follows:</span></span>

    - <span data-ttu-id="13c7f-147">활성 – SBC가 활성 상태입니다-Microsoft 다이렉트 라우팅 서비스는 정기적으로 이동 하는 옵션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-147">Active – The SBC is active--Microsoft Direct Routing service sees the options flowing on a regular interval.</span></span>

    - <span data-ttu-id="13c7f-148">경고, SIP 옵션 없음-데이터베이스에 세션 경계 컨트롤러가 있습니다 (관리자가 command New-CsOnlinePSTNGateway를 사용 하 여이를 만들었습니다).</span><span class="sxs-lookup"><span data-stu-id="13c7f-148">Warning, no SIP options - The Session Border Controller exists in the database (your administrator created it using the command New-CsOnlinePSTNGateway).</span></span> <span data-ttu-id="13c7f-149">SIP 옵션을 보내도록 구성 되어 있지만 직접 라우팅 서비스는이 SBC에서 들어오는 SIP 옵션을 전혀 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-149">It is configured to send SIP options, but the Direct Routing service never saw the SIP options coming back from this SBC.</span></span>

    - <span data-ttu-id="13c7f-150">경고, sip 메시지가 구성 되지 않음-SIP 옵션을 사용 하 여 트렁크 모니터링이 켜져 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-150">Warning, SIP Messages aren't configured - Trunk monitoring using SIP options isn’t turned on.</span></span> <span data-ttu-id="13c7f-151">Microsoft 호출 시스템은 SIP (전송 계층) 핸드셰이크 모니터링을 사용 하 여 응용 프로그램 수준에서 연결 된 SBCs (세션 경계 컨트롤러)의 상태를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-151">Microsoft Calling System uses SIP options and Transport Layer Security (TLS) handshake monitoring to detect the health of the connected Session Border Controllers (SBCs) at the application level.</span></span> <span data-ttu-id="13c7f-152">이 트렁크가 네트워크 수준 (ping 기준)에 도달할 수 있지만 인증서가 만료 되었거나 SIP 스택이 작동 하지 않는 경우 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-152">You’ll have problems if this trunk can be reached at the network level (by ping), but the certificate has expired or the SIP stack doesn’t work.</span></span> <span data-ttu-id="13c7f-153">이러한 문제를 조기에 확인할 수 있도록 Microsoft에서 SIP 옵션 보내기를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-153">To help identify such problems early, Microsoft recommends enabling sending SIP options.</span></span> <span data-ttu-id="13c7f-154">SBC 제조업체 설명서를 확인 하 여 SIP 옵션 보내기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-154">Check your SBC manufacturer documentation to configure sending SIP options.</span></span> 

- <span data-ttu-id="13c7f-155">**동시 통화 용량** -MaxConcurrentSessions 매개 변수를 사용 하 여 새 CsOnlinePSTNGateway 명령으로 SBC에서 처리할 수 있는 동시 호출의 한계를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-155">**Concurrent calls capacity** - You can specify the limit of concurrent calls that an SBC can handle by using the New- or Set-CsOnlinePSTNGateway command with the -MaxConcurrentSessions parameter.</span></span> <span data-ttu-id="13c7f-156">이 매개 변수는 특정 SBC를 사용 하 여 직접 라우팅이 보내거나 받은 통화 수를 계산 하 여 설정 된 제한과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-156">This parameter calculates how many calls were sent or received by Direct Routing using a specific SBC and compares it with the limit set.</span></span> <span data-ttu-id="13c7f-157">참고: SBC가 다른 Pbx에 대 한 호출만 처리 하는 경우이 번호는 실제 동시 호출을 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-157">Note:  If the SBC also handles calls to different PBXs, this number will not show the actual concurrent calls.</span></span>


## <a name="detailed-information-for-each-sbc"></a><span data-ttu-id="13c7f-158">각 SBC에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="13c7f-158">Detailed information for each SBC</span></span>

<span data-ttu-id="13c7f-159">다음 스크린샷에서 표시 된 것 처럼 특정 SBC에 대 한 자세한 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-159">You can also view the detailed information for a specific SBC as shown in the following screenshot:</span></span>

![상태 대시보드 SBC 세부 정보](media/direct-routing-dashboard-SBC-detail1.png)


<span data-ttu-id="13c7f-161">자세히 보기에는 다음과 같은 추가 매개 변수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-161">The detailed view shows the following additional parameters:</span></span>

- <span data-ttu-id="13c7f-162">**TLS 연결 상태** – "전반적인 상태" 페이지에 있는 것과 동일한 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-162">**TLS Connectivity status** – this is the same metric as on the “Overall Health” page;</span></span>

- <span data-ttu-id="13c7f-163">**TLS 연결 마지막 상태** -SBC에서 직접 라우팅 서비스에 대 한 TLS 연결을 수행한 시간을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-163">**TLS Connectivity last status** – shows time when the SBC made a TLS connection to the Direct Routing service;</span></span>

- <span data-ttu-id="13c7f-164">**SIP 옵션 상태** – "전반적인 상태" 페이지와 동일한 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-164">**SIP options status** – the same metric as on the “Overall Health” page.</span></span>

- <span data-ttu-id="13c7f-165">**마지막으로 확인 된 sip 옵션** -마지막으로 sip 옵션을 받은 시간</span><span class="sxs-lookup"><span data-stu-id="13c7f-165">**SIP options last checked** – time when the SIP options were received last time.</span></span>

- <span data-ttu-id="13c7f-166">**SBC 상태** – 모니터링 되는 모든 매개 변수를 기반으로 하는 sbc의 전반적인 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-166">**SBC status** – overall status of the SBC, based on all monitored parameters.</span></span>

- <span data-ttu-id="13c7f-167">**동시 통화**-SBC에서 처리 된 동시 호출 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-167">**Concurrent call**- shows  how many concurrent calls the SBC handled.</span></span> <span data-ttu-id="13c7f-168">이 정보는 필요한 동시 채널 수를 예측 하 고 추세를 확인 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-168">This information is useful to predict the number of concurrent channels you need and see the trend.</span></span> <span data-ttu-id="13c7f-169">일 수 및 통화 방향 (인바운드/아웃 바운드/모든 스트림)으로 데이터를 밀어 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-169">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

- <span data-ttu-id="13c7f-170">**네트워크 매개 변수** -모든 네트워크 매개 변수는 직접 라우팅 인터페이스에서 세션 경계 컨트롤러로 측정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-170">**Network parameters** - All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="13c7f-171">권장 값에 대 한 자세한 내용은 [Microsoft 팀 용 조직의 네트워크 준비](https://docs.microsoft.com/microsoftteams/prepare-network)를 참조 하 고 고객 Edge에서 microsoft edge 추천 값을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="13c7f-171">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

   - <span data-ttu-id="13c7f-172">지터 – RTCP (RTP 컨트롤 프로토콜)를 사용 하 여 두 끝점 간에 계산 된 네트워크 전파 지연 시간 변동의 밀리초 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-172">Jitter – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

   - <span data-ttu-id="13c7f-173">패킷 손실 – 도착 하지 못한 패킷의 척도입니다. 두 끝점 간에 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-173">Packet Loss – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

   - <span data-ttu-id="13c7f-174">지연 (라운드트립 시간이 라고도 함)은 신호가 전송 되는 데 걸리는 시간과 해당 신호를 수신 하는 데 걸리는 시간을 합한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-174">Latency - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="13c7f-175">이 시간 지연은 신호의 두 점 사이의 전파 시간으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-175">This time delay consists of the propagation times between the two points of a signal.</span></span>

   <span data-ttu-id="13c7f-176">일 수 및 통화 방향 (인바운드/아웃 바운드/모든 스트림)으로 데이터를 밀어 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-176">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

<span data-ttu-id="13c7f-177">**네트워크 효율성 비율** -전체 상태 대시보드에 표시 되는 것과 동일한 매개 변수 이며 시계열 또는 호출 방향으로 데이터를 분할 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c7f-177">**Network Effectiveness ratio** - This is the same parameter that appears on the Overall Health dashboard, but with the option to slice the data by time series or call direction.</span></span>




