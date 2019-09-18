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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 이 문서에서는 직접 라우팅 구성을 모니터링 하 고 문제를 해결 하는 방법을 설명 합니다.
ms.openlocfilehash: e236a5cecb190d10082e06de24655bd722a410e5
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018826"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="739b3-103">직접 라우팅 모니터링 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="739b3-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="739b3-104">이 문서에서는 직접 라우팅 구성을 모니터링 하 고 문제를 해결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="739b3-105">직접 라우팅을 사용 하 여 전화를 걸고 받을 수 있는 기능은 다음 구성 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="739b3-106">SBCs (세션 경계 컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="739b3-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="739b3-107">Microsoft 클라우드의 직접 라우팅 구성 요소</span><span class="sxs-lookup"><span data-stu-id="739b3-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="739b3-108">통신 trunks</span><span class="sxs-lookup"><span data-stu-id="739b3-108">Telecom trunks</span></span> 

<span data-ttu-id="739b3-109">문제가 해결 되지 않는 경우 SBC 공급 업체나 Microsoft에서 지원 서비스 케이스를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="739b3-110">Microsoft는 문제 해결 및 모니터링을 위한 추가 도구를 제공 하는 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="739b3-111">문서를 정기적으로 업데이트를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="739b3-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="739b3-112">SIP (세션 초기화 프로토콜) 옵션 메시지를 사용 하 여 세션 경계 컨트롤러의 가용성 모니터링</span><span class="sxs-lookup"><span data-stu-id="739b3-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="739b3-113">직접 라우팅은 세션 경계 컨트롤러에서 보낸 SIP 옵션을 사용 하 여 SBC 상태를 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="739b3-114">테 넌 트 관리자가 SIP 옵션 모니터링을 사용 하도록 설정 하는 데 필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="739b3-115">수집 된 정보는 라우팅 결정을 할 때 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="739b3-116">예를 들어 특정 사용자에 대해 통화를 라우팅할 수 있는 몇 개의 SBCs가 있는 경우 다이렉트 라우팅은 각 SBC에서 받은 SIP 옵션 정보를 라우팅 결정을 고려 하 여 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="739b3-117">다음 다이어그램에서는 구성의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-117">The following diagram shows an example of the configuration:</span></span> 

![SIP 옵션 구성 예제](media/sip-options-config-example.png)

<span data-ttu-id="739b3-119">사용자가 7> 자리 숫자로 + 1 425 \<를 호출 하면 직접적인 라우팅이 경로를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="739b3-120">경로에는 sbc1.contoso.com 및 sbc2.contoso.com의 두 가지 SBCs가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="739b3-121">두 SBCs는 경로의 우선 순위가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="739b3-122">SBC를 선택 하기 전에 라우팅 메커니즘은 SBC에서 마지막으로 SIP 옵션을 보낸 시점을 기준으로 SBCs의 상태를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="739b3-123">호출을 보내는 순간의 통계가 1 분 마다 옵션을 전송 한다는 것을 표시 하면 SBC는 정상으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="739b3-124">호출이 이루어지면 다음 논리가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="739b3-125">SBC는 11:00 AM에 페어링 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="739b3-126">SBC는 오전 11:01, 11:02 AM 등의 옵션을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="739b3-127">11:15에서 사용자는 전화를 걸고 라우팅 메커니즘이이 SBC를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="739b3-128">직접 라우팅은 일반 간격 옵션을 세 번 (1 분 간격으로) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="739b3-129">지난 3 분 동안 옵션이 전송 된 경우 SBC는 정상으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="739b3-130">예의 SBC에서 11:12 AM 및 11:15 AM (통화 시간) 사이의 모든 기간에 대 한 옵션을 보낸 경우에는 정상적인 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="739b3-131">그렇지 않은 경우 SBC는 경로에서 강등 됩니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="739b3-132">강등은 SBC가 먼저 시도 되지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="739b3-133">예를 들어 우선 순위가 동일한 sbc1.contoso.com 및 sbc2.contoso.com 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="739b3-134">앞에서 설명한 대로 sbc1.contoso.com에서 SIP 옵션을 정기적으로 보내지 않는 경우 수준이 내려갑니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="739b3-135">그 다음 sbc2.contoso.com 통화를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="739b3-136">Sbc2에서 통화를 전달할 수 없는 경우에는 오류가 발생 하기 전에 sbc1.contoso.com (수준 내림)을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="739b3-137">한 경로에 둘 이상의 SBCs (또는 그 이상)가 있는 것으로 간주 되는 경우 SBCs 간의 통화를 분산 하기 위해 Fisher가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="739b3-138">통화 품질 분석 대시보드 및 SBC 로그 모니터링</span><span class="sxs-lookup"><span data-stu-id="739b3-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="739b3-139">일부 경우에 특히 초기 페어링 중에 SBCs 또는 다이렉트 라우팅 서비스의 잘못 된 구성 관련 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="739b3-140">다음 도구를 사용 하 여 구성을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="739b3-141">통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="739b3-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="739b3-142">SBC 로그</span><span class="sxs-lookup"><span data-stu-id="739b3-142">SBC logs</span></span> 

<span data-ttu-id="739b3-143">다이렉트 라우팅 서비스에는 호출 분석 또는 SBC 로그에 보고 되는 매우 설명적인 오류 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="739b3-144">통화 품질 대시보드는 통화 품질 및 안정성에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="739b3-145">통화 분석을 사용 하 여 발생 하는 문제를 해결 하는 방법에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype Online에 대 한 통화 품질 대시보드 켜기 및 사용](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) 및 통화 [분석을 사용 하 여 통화 품질 저하 문제 해결](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="739b3-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="739b3-146">통화 실패 시에는 통화 분석이 표준 SIP 코드를 제공 하 여 문제 해결에 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![통화 실패에 대 한 샘플 SIP 코드](media/failed-response-code.png)

<span data-ttu-id="739b3-148">그러나 통화 분석은 호출이 직접 라우팅 및 실패의 내부 구성 요소에 도달 하는 경우에만 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="739b3-149">SBC 페어링 또는 SIP "초대"가 거부 된 문제에 대 한 문제가 발생 하는 경우 (예: 트렁크 FQDN의 이름이 잘못 구성 된 경우)에는 통화 분석이 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-149">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="739b3-150">이 경우 SBC 로그를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="739b3-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="739b3-151">직접 라우팅은 SBCs에 대 한 문제에 대 한 자세한 설명을 보냅니다. 이러한 문제는 SBC 로그에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739b3-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
