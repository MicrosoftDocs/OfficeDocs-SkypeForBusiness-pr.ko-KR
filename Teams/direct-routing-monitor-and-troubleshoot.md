---
title: 직접 라우팅 모니터링 및 문제 해결
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 세션 경계 컨트롤러, 직접 라우팅 구성 요소 및 Telecom 트렁크를 포함하여 직접 라우팅 구성을 모니터링하고 문제를 해결하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121406"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="0b2ba-103">직접 라우팅 모니터링 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0b2ba-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="0b2ba-104">이 문서에서는 직접 라우팅 구성을 모니터링하고 문제를 해결하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="0b2ba-105">직접 라우팅을 사용하여 전화를 걸고 받는 능력에는 다음 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="0b2ba-106">세션 테두리 컨트롤러(SBC)</span><span class="sxs-lookup"><span data-stu-id="0b2ba-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="0b2ba-107">Microsoft Cloud의 직접 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0b2ba-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="0b2ba-108">Telecom 트렁크</span><span class="sxs-lookup"><span data-stu-id="0b2ba-108">Telecom trunks</span></span> 

<span data-ttu-id="0b2ba-109">문제 해결에 문제가 있는 경우 SBC 공급업체 또는 Microsoft에서 지원 사례를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="0b2ba-110">Microsoft는 문제 해결 및 모니터링을 위한 더 많은 도구를 제공하기 위해 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="0b2ba-111">업데이트를 위해 설명서를 주기적으로 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="0b2ba-112">SIP(세션 시작 프로토콜) 옵션 메시지를 사용하여 세션 테두리 컨트롤러의 가용성 모니터링</span><span class="sxs-lookup"><span data-stu-id="0b2ba-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="0b2ba-113">직접 라우팅은 세션 테두리 컨트롤러에서 전송한 SIP 옵션을 사용하여 SBC 상태 모니터링을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="0b2ba-114">SIP 옵션 모니터링을 사용하도록 설정하는 데 테넌트 관리자에게 필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="0b2ba-115">수집된 정보는 라우팅 결정을 내릴 때 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="0b2ba-116">예를 들어 특정 사용자의 경우 호출을 라우팅하는 데 사용할 수 있는 SBC가 여러 개 있는 경우 직접 라우팅은 각 SBC에서 수신한 SIP 옵션 정보를 고려하여 라우팅을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="0b2ba-117">다음 다이어그램은 구성의 예제를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-117">The following diagram shows an example of the configuration:</span></span> 

![SIP 옵션 구성 예제](media/sip-options-config-example.png)

<span data-ttu-id="0b2ba-119">사용자가 +1 425 번호로 전화를 걸면 직접 라우팅이 \<any seven digits> 경로를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="0b2ba-120">경로에는 두 개의 SBC가 있습니다. sbc1.contoso.com 및 sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="0b2ba-121">두 SBC 모두 경로에 동일한 우선 순위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="0b2ba-122">SBC를 선택하기 전에 라우팅 메커니즘은 SBC가 SIP 옵션을 마지막으로 보낸 시기를 기준으로 SBC의 상태도 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="0b2ba-123">호출을 보내는 순간의 통계가 SBC에서 1분마다 옵션을 전송하는 경우 SBC는 정상으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="0b2ba-124">호출이 설정된 경우 다음 논리가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="0b2ba-125">SBC는 오전 11:00에 페어링됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="0b2ba-126">SBC는 오전 11:01, 오전 11:02에 옵션을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="0b2ba-127">11:15에서 사용자가 전화를 걸고 라우팅 메커니즘이 이 SBC를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="0b2ba-128">직접 라우팅은 일반 간격 옵션을 세 번(일반 간격은 1분)으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="0b2ba-129">지난 3분 동안 옵션이 전송된 경우 SBC가 정상으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="0b2ba-130">예제의 SBC가 오전 11시 12분에서 오전 11시 15분 사이에 옵션을 보낸 경우(통화가 시작된 시간) 정상으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="0b2ba-131">그렇지 않은 경우 SBC가 경로에서 강하됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="0b2ba-132">강하는 SBC가 먼저 시도되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="0b2ba-133">예를 들어 동일한 우선 순위를 sbc1.contoso.com sbc2.contoso.com 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="0b2ba-134">이전에 sbc1.contoso.com 주기적으로 SIP 옵션을 보내지 않는 경우 강하됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="0b2ba-135">다음으로 sbc2.contoso.com 를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="0b2ba-136">sbc2.contoso.con이 호출을 배달할 수 없는 경우 실패가 sbc1.contoso.com 전에 다시 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="0b2ba-137">한 경로에서 두 개 이상의 SBC가 정상 및 같음으로 간주되는 Fisher-Yates 셔플이 적용되어 SBC 간에 호출을 분산합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="0b2ba-138">통화 품질 분석 대시보드 및 SBC 로그 모니터링</span><span class="sxs-lookup"><span data-stu-id="0b2ba-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="0b2ba-139">특히 초기 페어링 중에 SBC 또는 직접 라우팅 서비스의 잘못 구성과 관련된 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="0b2ba-140">다음 도구를 사용하여 구성을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="0b2ba-141">통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="0b2ba-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="0b2ba-142">SBC 로그</span><span class="sxs-lookup"><span data-stu-id="0b2ba-142">SBC logs</span></span> 

<span data-ttu-id="0b2ba-143">직접 라우팅 서비스에는 Call Analytics 또는 SBC 로그에 보고된 매우 설명적인 오류 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="0b2ba-144">통화 품질 대시보드는 통화 품질 및 안정성에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="0b2ba-145">Call Analytics를 사용하여 문제 해결 방법에 [](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) 대한 자세한 내용은 통화 품질 대시보드를 켜고 사용하는 방법을 참조하세요. Microsoft Teams 및 비즈니스용 Skype 통화 분석을 사용하여 통화 품질 문제를 [해결하세요.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="0b2ba-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="0b2ba-146">호출 오류가 발생하면 Call Analytics는 문제 해결에 도움이 되는 표준 SIP 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![호출 실패에 대한 샘플 SIP 코드](media/failed-response-code.png)

<span data-ttu-id="0b2ba-148">그러나 호출 분석은 호출이 직접 라우팅의 내부 구성 요소에 도달하고 실패할 때만 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="0b2ba-149">SBC 페어링에 문제가 있는 경우 또는 SIP "초대"가 거부된 문제(예: 트렁크 FQDN의 이름이 잘못 구성) 호출 분석에 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="0b2ba-150">이 경우 SBC 로그를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="0b2ba-151">직접 라우팅은 문제에 대한 자세한 설명을 SBC에 전송합니다. 이러한 문제는 SBC 로그에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2ba-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span>