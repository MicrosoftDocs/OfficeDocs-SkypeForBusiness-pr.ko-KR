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
description: 세션 테두리 컨트롤러, 직접 라우팅 구성 요소 및 Telecom 트렁크를 포함하여 직접 라우팅 구성을 모니터링하고 문제를 해결하는 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52ab594b901606ccf7c3b43fc8484d989c248fcd
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901913"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="976ba-103">직접 라우팅 모니터링 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="976ba-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="976ba-104">이 문서에서는 직접 라우팅 구성을 모니터링하고 문제를 해결하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="976ba-105">직접 라우팅을 사용하여 호출을 걸고 받는 능력에는 다음 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="976ba-106">SBC(세션 테두리 컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="976ba-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="976ba-107">Microsoft 클라우드의 직접 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="976ba-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="976ba-108">Telecom 트렁크</span><span class="sxs-lookup"><span data-stu-id="976ba-108">Telecom trunks</span></span> 

<span data-ttu-id="976ba-109">문제 해결에 어려움이 있는 경우 SBC 공급업체 또는 Microsoft에 지원 사례를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="976ba-110">Microsoft는 문제 해결 및 모니터링을 위한 더 많은 도구를 제공하기 위해 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="976ba-111">업데이트에 대한 설명서를 주기적으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="976ba-112">SIP(세션 시작 프로토콜) 옵션 메시지를 사용하여 세션 테두리 컨트롤러의 가용성 모니터링</span><span class="sxs-lookup"><span data-stu-id="976ba-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="976ba-113">직접 라우팅은 세션 테두리 컨트롤러에서 보낸 SIP 옵션을 사용하여 SBC 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="976ba-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="976ba-114">SIP 옵션 모니터링을 사용하도록 설정하려면 테넌트 관리자에게 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="976ba-115">라우팅 결정을 내릴 때 수집된 정보를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="976ba-116">예를 들어 특정 사용자의 경우 호출을 라우팅하는 데 사용할 수 있는 여러 SBC가 있는 경우 직접 라우팅은 각 SBC에서 받은 SIP 옵션 정보를 고려하여 라우팅을 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="976ba-117">다음 다이어그램은 구성의 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-117">The following diagram shows an example of the configuration:</span></span> 

![SIP 옵션 구성 예제](media/sip-options-config-example.png)

<span data-ttu-id="976ba-119">사용자가 7자리 숫자 +1 425를> 경우 직접 라우팅은 \< 경로를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="976ba-120">경로에는 두 개의 SBC, 즉 sbc1.contoso.com 및 sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="976ba-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="976ba-121">두 SBC 모두 경로에서 동일한 우선 순위를 습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="976ba-122">SBC를 선택하기 전에 라우팅 메커니즘은 SBC가 SIP 옵션을 마지막으로 보낸 시기를 기반으로 SBC의 상태 평가를 합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="976ba-123">호출을 보낼 때 통계가 SBC가 1분마다 옵션을 전송하는 것으로 표시될 경우 SBC는 정상으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="976ba-124">호출이 이행된 경우 다음 논리가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="976ba-125">SBC는 오전 11시에 쌍으로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="976ba-126">SBC는 오전 11시, 오전 11시 2분에 옵션을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="976ba-127">11시 15분에 사용자가 전화를 걸고 라우팅 메커니즘이 이 SBC를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="976ba-128">직접 라우팅은 일반 간격 옵션을 세 번(일반 간격은 1분)합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="976ba-129">지난 3분 동안 옵션이 전송된 경우 SBC는 정상으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="976ba-130">예제의 SBC가 오전 11시 12분과 오전 11시 15분 사이에 옵션을 보낸 경우(호출이 만들어진 시간) 정상으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="976ba-131">그렇지 않은 경우 SBC는 경로에서 강하됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="976ba-132">강하는 SBC가 먼저 시도되지 않는 경우를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="976ba-133">예를 들어 우선 순위가 sbc1.contoso.com sbc2.contoso.com 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="976ba-134">이전에 sbc1.contoso.com 정기적으로 SIP 옵션을 보내지 않는 경우 강아집니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="976ba-135">다음으로 sbc2.contoso.com 호출을 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="976ba-136">sbc2.contoso.con에서 호출을 배달할 수 없는 경우 sbc1.contoso.com(강하)를 다시 시도한 후 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="976ba-137">한 경로에 있는 두 개 이상의 SBC가 정상 및 같음으로 간주되는 경우 Fisher-Yates 셔플이 적용되어 SBC 간에 호출을 분산합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="976ba-138">통화 품질 분석 대시보드 및 SBC 로그 모니터링</span><span class="sxs-lookup"><span data-stu-id="976ba-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="976ba-139">경우에 따라 특히 초기 페어링 중에 SBC 또는 직접 라우팅 서비스의 구성 잘못과 관련된 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="976ba-140">다음 도구를 사용하여 구성을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="976ba-141">통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="976ba-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="976ba-142">SBC 로그</span><span class="sxs-lookup"><span data-stu-id="976ba-142">SBC logs</span></span> 

<span data-ttu-id="976ba-143">직접 라우팅 서비스에는 호출 분석 또는 SBC 로그에 보고된 매우 설명적인 오류 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="976ba-144">통화 품질 대시보드는 통화 품질 및 안정성에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="976ba-145">통화 분석을 사용하여 문제를 해결하는 방법에 대한 자세한 내용은 Microsoft Teams 및 [비즈니스용 Skype Online에](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) 대한 통화 품질 대시보드 켜기 및 사용 및 통화 분석을 사용하여 통화 품질 문제 해결을 [참조하세요.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="976ba-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="976ba-146">호출 실패 시 호출 분석은 문제 해결에 도움이 되는 표준 SIP 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![호출 실패에 대한 샘플 SIP 코드](media/failed-response-code.png)

<span data-ttu-id="976ba-148">그러나 호출 분석은 호출이 직접 라우팅의 내부 구성 요소에 도달하고 실패할 때만 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="976ba-149">SBC 페어링 관련 문제 또는 SIP "초대"가 거부된 문제(예: 트렁크 FQDN의 이름이 잘못 구성) 호출 분석은 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="976ba-150">이 경우 SBC 로그를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="976ba-151">직접 라우팅은 문제에 대한 자세한 설명을 SBC에 전송합니다. 이러한 문제는 SBC 로그에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ba-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
