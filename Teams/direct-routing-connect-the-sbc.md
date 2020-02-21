---
title: 직접 라우팅에 SBC (세션 경계 컨트롤러) 연결
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
description: Microsoft 전화 시스템 다이렉트 라우팅을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157998"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a><span data-ttu-id="8921d-103">직접 라우팅에 SBC (세션 경계 컨트롤러) 연결</span><span class="sxs-lookup"><span data-stu-id="8921d-103">Connect your Session Border Controller (SBC) to Direct Routing</span></span> 

<span data-ttu-id="8921d-104">이 문서에서는 SBC (세션 경계 컨트롤러)를 전화 시스템 다이렉트 라우팅에 연결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-104">This article describes how to connect your Session Border Controller (SBC) to Phone System Direct Routing.</span></span>  <span data-ttu-id="8921d-105">직접 라우팅 구성에 대 한 단계 1 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-105">This is step 1 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="8921d-106">**1 단계. 전화 시스템을 사용 하 여 SBC 연결 및 연결 확인** (이 문서)</span><span class="sxs-lookup"><span data-stu-id="8921d-106">**Step 1. Connect your SBC with Phone System and validate the connection** (This article)</span></span>
- <span data-ttu-id="8921d-107">2 단계.</span><span class="sxs-lookup"><span data-stu-id="8921d-107">Step 2.</span></span> [<span data-ttu-id="8921d-108">사용자가 직접 라우팅 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="8921d-108">Enable users for Direct Routing</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="8921d-109">3 단계.</span><span class="sxs-lookup"><span data-stu-id="8921d-109">Step 3.</span></span> [<span data-ttu-id="8921d-110">통화 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="8921d-110">Configure call routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="8921d-111">4 단계.</span><span class="sxs-lookup"><span data-stu-id="8921d-111">Step 4.</span></span> [<span data-ttu-id="8921d-112">숫자를 대체 형식으로 번역</span><span class="sxs-lookup"><span data-stu-id="8921d-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="8921d-113">직접 라우팅을 설정 하는 데 필요한 모든 단계에 대 한 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8921d-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="8921d-114">SBC를 직접 라우팅에 연결 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-114">To connect your SBC to Direct Routing, you'll need to:</span></span> 

1. <span data-ttu-id="8921d-115">PowerShell을 사용 하 여 **비즈니스용 Skype Online** 관리 센터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-115">Connect to **Skype for Business Online** admin center by using PowerShell.</span></span>            
2. <span data-ttu-id="8921d-116">테 넌 트에 SBC를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-116">Connect the SBC to the tenant.</span></span>
3. <span data-ttu-id="8921d-117">연결의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-117">Validate the connection.</span></span> 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="8921d-118">PowerShell을 사용 하 여 비즈니스용 Skype Online에 연결</span><span class="sxs-lookup"><span data-stu-id="8921d-118">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="8921d-119">테 넌 트에 연결 된 PowerShell 세션을 사용 하 여 SBC를 직접 라우팅 인터페이스에 쌍으로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-119">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="8921d-120">PowerShell 세션을 열려면 [Windows powershell 용 컴퓨터 설정](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)에서 설명 하는 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-120">To open a PowerShell session, follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="8921d-121">원격 PowerShell 세션을 설정한 후 SBC를 관리 하는 명령을 볼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-121">After you establish a remote PowerShell session, validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="8921d-122">명령에 대 한 유효성을 검사 하려면 PowerShell 세션에 다음 명령을 입력 하거나 복사 하 여 붙여 넣은 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-122">To validate the commands, type or copy and paste the following command in the PowerShell session and press Enter:</span></span> 

```PowerShell
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="8921d-123">이 명령은 SBC를 관리할 수 있도록 여기에 나와 있는 네 개의 함수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-123">The command returns the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


## <a name="connect-the-sbc-to-the-tenant"></a><span data-ttu-id="8921d-124">테 넌 트에 SBC 연결</span><span class="sxs-lookup"><span data-stu-id="8921d-124">Connect the SBC to the tenant</span></span> 

<span data-ttu-id="8921d-125">테 넌 트에 SBC를 연결 하려면 PowerShell 세션에서 다음을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-125">To connect the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="8921d-126">SBC 설명서에 나와 있는 정보를 사용 하 여 SBC에서 최대 통화 제한을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-126">Microsoft recommends setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="8921d-127">이 제한은 SBC이 용량 수준에 있는 경우 알림을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-127">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="8921d-128">FQDN의 도메인 부분이 onmicrosoft.com를 제외 \*하 고 테 넌 트에서 등록 된 도메인 중 하 나와 일치 하는 경우에만 SBC를 쌍으로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-128">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="8921d-129">Onmicrosoft.com \*도메인 이름을 사용 하는 것은 SBC FQDN 이름에 대해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-129">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="8921d-130">예를 들어 도메인 이름이 두 개 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="8921d-130">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="8921d-131">**contoso**. c a m</span><span class="sxs-lookup"><span data-stu-id="8921d-131">**contoso**.com</span></span><br/><span data-ttu-id="8921d-132">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8921d-132">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="8921d-133">SBC 이름에는 이름 sbc.contoso.com를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-133">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="8921d-134">Sbc와 이름 sbc를 쌍으로 연결 하려고 하면이 테 넌 트가 도메인을 소유 하지 않으므로 시스템에서 사용자를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-134">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="8921d-135">테 넌 트에 등록 된 도메인 외에도 해당 도메인 및 할당 된 E3 또는 E5 라이선스를 가진 사용자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-135">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="8921d-136">그렇지 않으면 다음 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-136">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="8921d-137">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="8921d-137">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span></span>

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="8921d-138">구합니다</span><span class="sxs-lookup"><span data-stu-id="8921d-138">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="8921d-139">연결 프로세스 중에 설정할 수 있는 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-139">There are additional options that can be set during the connection process.</span></span> <span data-ttu-id="8921d-140">그러나 앞의 예제에서는 필요한 최소 매개 변수만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-140">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="8921d-141">다음 표에는 매개 변수를 ```New-CsOnlinePstnGateway```설정 하는 데 사용할 수 있는 추가 매개 변수가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-141">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="8921d-142">필수?</span><span class="sxs-lookup"><span data-stu-id="8921d-142">Required?</span></span>|<span data-ttu-id="8921d-143">이름</span><span class="sxs-lookup"><span data-stu-id="8921d-143">Name</span></span>|<span data-ttu-id="8921d-144">설명</span><span class="sxs-lookup"><span data-stu-id="8921d-144">Description</span></span>|<span data-ttu-id="8921d-145">기본값</span><span class="sxs-lookup"><span data-stu-id="8921d-145">Default</span></span>|<span data-ttu-id="8921d-146">사용할 수 있는 값</span><span class="sxs-lookup"><span data-stu-id="8921d-146">Possible values</span></span>|<span data-ttu-id="8921d-147">유형 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="8921d-147">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8921d-148">예</span><span class="sxs-lookup"><span data-stu-id="8921d-148">Yes</span></span>|<span data-ttu-id="8921d-149">Q</span><span class="sxs-lookup"><span data-stu-id="8921d-149">FQDN</span></span>|<span data-ttu-id="8921d-150">SBC의 FQDN 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-150">The FQDN name of the SBC</span></span> |<span data-ttu-id="8921d-151">없음</span><span class="sxs-lookup"><span data-stu-id="8921d-151">None</span></span>|<span data-ttu-id="8921d-152">비 Efqdn 이름, 63 문자 제한</span><span class="sxs-lookup"><span data-stu-id="8921d-152">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="8921d-153">[Active Directory에서 컴퓨터, 도메인, 사이트 및 ou에 대 한 명명 규칙](https://support.microsoft.com/help/909264) 의 허용 및 허용 되지 않는 문자 목록 문자열</span><span class="sxs-lookup"><span data-stu-id="8921d-153">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="8921d-154">아니요</span><span class="sxs-lookup"><span data-stu-id="8921d-154">No</span></span>|<span data-ttu-id="8921d-155">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="8921d-155">MediaBypass</span></span> |<span data-ttu-id="8921d-156">SBC로 표시 된 매개 변수는 미디어 바이패스를 지원 하 고 관리자가이를 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-156">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="8921d-157">없음</span><span class="sxs-lookup"><span data-stu-id="8921d-157">None</span></span>|<span data-ttu-id="8921d-158">False</span><span class="sxs-lookup"><span data-stu-id="8921d-158">True</span></span><br/><span data-ttu-id="8921d-159">해제</span><span class="sxs-lookup"><span data-stu-id="8921d-159">False</span></span>|<span data-ttu-id="8921d-160">부울</span><span class="sxs-lookup"><span data-stu-id="8921d-160">Boolean</span></span>|
|<span data-ttu-id="8921d-161">예</span><span class="sxs-lookup"><span data-stu-id="8921d-161">Yes</span></span>|<span data-ttu-id="8921d-162">SipSignalingPort</span><span class="sxs-lookup"><span data-stu-id="8921d-162">SipSignalingPort</span></span> |<span data-ttu-id="8921d-163">TLS (전송 계층 보안) 프로토콜을 사용 하 여 직접 라우팅 서비스와 통신 하는 데 사용 되는 수신 대기 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-163">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="8921d-164">없음</span><span class="sxs-lookup"><span data-stu-id="8921d-164">None</span></span>|<span data-ttu-id="8921d-165">모든 포트</span><span class="sxs-lookup"><span data-stu-id="8921d-165">Any port</span></span>|<span data-ttu-id="8921d-166">0 ~ 65535</span><span class="sxs-lookup"><span data-stu-id="8921d-166">0 to 65535</span></span> |
|<span data-ttu-id="8921d-167">아니요</span><span class="sxs-lookup"><span data-stu-id="8921d-167">No</span></span>|<span data-ttu-id="8921d-168">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="8921d-168">FailoverTimeSeconds</span></span> |<span data-ttu-id="8921d-169">10으로 설정 된 경우 (기본값), 게이트웨이에서 응답 하지 않은 아웃 바운드 호출은 10 초 이내에 사용 가능한 다음 트렁크로 라우팅됩니다. 추가 trunks 없으면 통화가 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-169">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="8921d-170">느린 네트워크 및 게이트웨이 응답을 사용 하는 조직에서 호출이 불필요 하 게 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-170">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="8921d-171">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-171">The default value is 10.</span></span>|<span data-ttu-id="8921d-172">1천만</span><span class="sxs-lookup"><span data-stu-id="8921d-172">10</span></span>|<span data-ttu-id="8921d-173">숫자로</span><span class="sxs-lookup"><span data-stu-id="8921d-173">Number</span></span>|<span data-ttu-id="8921d-174">Int</span><span class="sxs-lookup"><span data-stu-id="8921d-174">Int</span></span>|
|<span data-ttu-id="8921d-175">아니요</span><span class="sxs-lookup"><span data-stu-id="8921d-175">No</span></span>|<span data-ttu-id="8921d-176">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="8921d-176">ForwardCallHistory</span></span> |<span data-ttu-id="8921d-177">트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-177">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="8921d-178">이 기능을 사용 하도록 설정 하면 Office 365 PSTN 프록시가 두 가지 헤더 인 기록 정보 및 참조 하는 사람을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-178">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="8921d-179">기본값은 **False** ($False)입니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-179">The default value is **False** ($False).</span></span> |<span data-ttu-id="8921d-180">해제</span><span class="sxs-lookup"><span data-stu-id="8921d-180">False</span></span>|<span data-ttu-id="8921d-181">False</span><span class="sxs-lookup"><span data-stu-id="8921d-181">True</span></span><br/><span data-ttu-id="8921d-182">해제</span><span class="sxs-lookup"><span data-stu-id="8921d-182">False</span></span>|<span data-ttu-id="8921d-183">부울</span><span class="sxs-lookup"><span data-stu-id="8921d-183">Boolean</span></span>|
|<span data-ttu-id="8921d-184">아니요</span><span class="sxs-lookup"><span data-stu-id="8921d-184">No</span></span>|<span data-ttu-id="8921d-185">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="8921d-185">ForwardPAI</span></span>|<span data-ttu-id="8921d-186">PAI(P-Asserted-Identity) 헤더를 통화와 함께 전달할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-186">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="8921d-187">PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-187">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="8921d-188">사용 하도록 설정한 경우 개인 정보 취급 방침: ID 헤더만 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-188">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="8921d-189">기본값은 **False** ($False)입니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-189">The default value is **False** ($False).</span></span>|<span data-ttu-id="8921d-190">해제</span><span class="sxs-lookup"><span data-stu-id="8921d-190">False</span></span>|<span data-ttu-id="8921d-191">False</span><span class="sxs-lookup"><span data-stu-id="8921d-191">True</span></span><br/><span data-ttu-id="8921d-192">해제</span><span class="sxs-lookup"><span data-stu-id="8921d-192">False</span></span>|<span data-ttu-id="8921d-193">부울</span><span class="sxs-lookup"><span data-stu-id="8921d-193">Boolean</span></span>|
|<span data-ttu-id="8921d-194">아니요</span><span class="sxs-lookup"><span data-stu-id="8921d-194">No</span></span>|<span data-ttu-id="8921d-195">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="8921d-195">SendSIPOptions</span></span> |<span data-ttu-id="8921d-196">SBC가 SIP 옵션을 보내지 않을 지 여부를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-196">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="8921d-197">이 기능을 사용 하지 않도록 설정 하면 SBC이 모니터링 및 경고 시스템에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-197">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="8921d-198">SIP 옵션을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-198">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="8921d-199">기본값은 **True**입니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-199">Default value is **True**.</span></span> |<span data-ttu-id="8921d-200">False</span><span class="sxs-lookup"><span data-stu-id="8921d-200">True</span></span>|<span data-ttu-id="8921d-201">False</span><span class="sxs-lookup"><span data-stu-id="8921d-201">True</span></span><br/><span data-ttu-id="8921d-202">해제</span><span class="sxs-lookup"><span data-stu-id="8921d-202">False</span></span>|<span data-ttu-id="8921d-203">부울</span><span class="sxs-lookup"><span data-stu-id="8921d-203">Boolean</span></span>|
|<span data-ttu-id="8921d-204">아니요</span><span class="sxs-lookup"><span data-stu-id="8921d-204">No</span></span>|<span data-ttu-id="8921d-205">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="8921d-205">MaxConcurrentSessions</span></span> |<span data-ttu-id="8921d-206">경고 시스템에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-206">Used by alerting system.</span></span> <span data-ttu-id="8921d-207">값이 설정 되 면 경고 시스템에서는 동시 세션 수가이 값 보다 90% 이상일 때 테 넌 트 관리자에 게 알림을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-207">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent sessions is 90% or higher than this value.</span></span> <span data-ttu-id="8921d-208">매개 변수가 설정 되지 않은 경우에는 경고가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-208">If the parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="8921d-209">그러나 모니터링 시스템에서는 24 시간 마다 동시 세션의 수를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-209">However, the monitoring system will report number of concurrent sessions every 24 hours.</span></span> |<span data-ttu-id="8921d-210">L</span><span class="sxs-lookup"><span data-stu-id="8921d-210">Null</span></span>|<span data-ttu-id="8921d-211">L</span><span class="sxs-lookup"><span data-stu-id="8921d-211">Null</span></span><br/><span data-ttu-id="8921d-212">1 ~ 10만</span><span class="sxs-lookup"><span data-stu-id="8921d-212">1 to 100,000</span></span> ||
|<span data-ttu-id="8921d-213">아니요</span><span class="sxs-lookup"><span data-stu-id="8921d-213">No</span></span>|<span data-ttu-id="8921d-214">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="8921d-214">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="8921d-215">수동으로 미디어 경로를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-215">Allows selecting path for media manually.</span></span> <span data-ttu-id="8921d-216">직접 라우팅은 미디어 경로에 대 한 데이터 센터에 SBC의 공용 IP를 기반으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-216">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="8921d-217">항상 SBC 데이터 센터에 가장 가까운 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-217">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="8921d-218">그러나 일부 경우에는 미국 범위를 유럽에 위치한 SBC에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-218">However, in some cases a public IP from, for example, a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="8921d-219">이 경우 최적화 되지 않은 미디어 경로를 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-219">In this case, we will be using not optimal media path.</span></span> <span data-ttu-id="8921d-220">이 매개 변수를 사용 하면 미디어 트래픽에 대 한 기본 설정 영역을 수동으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-220">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="8921d-221">Microsoft는 미디어 경로에 대 한 데이터 센터의 자동 할당이 SBC 데이터 센터에 가장 가까운 것을 할당 하지 않는다는 것을 호출 로그가 명확 하 게 표시 하는 경우에만이 매개 변수 설정을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-221">Microsoft only recommends setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="8921d-222">없음</span><span class="sxs-lookup"><span data-stu-id="8921d-222">None</span></span>|<span data-ttu-id="8921d-223">ISO 형식의 국가 코드</span><span class="sxs-lookup"><span data-stu-id="8921d-223">Country codes in ISO format</span></span>||
|<span data-ttu-id="8921d-224">아니요</span><span class="sxs-lookup"><span data-stu-id="8921d-224">No</span></span>|<span data-ttu-id="8921d-225">수</span><span class="sxs-lookup"><span data-stu-id="8921d-225">Enabled</span></span>|<span data-ttu-id="8921d-226">이 SBC를 발신 전화에 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-226">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="8921d-227">업데이트 중이거나 유지 관리 하는 동안 SBC를 일시적으로 제거 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-227">Can be used to temporarily remove the SBC while it is being updated or during maintenance.</span></span> |<span data-ttu-id="8921d-228">해제</span><span class="sxs-lookup"><span data-stu-id="8921d-228">False</span></span>|<span data-ttu-id="8921d-229">False</span><span class="sxs-lookup"><span data-stu-id="8921d-229">True</span></span><br/><span data-ttu-id="8921d-230">해제</span><span class="sxs-lookup"><span data-stu-id="8921d-230">False</span></span>|<span data-ttu-id="8921d-231">부울</span><span class="sxs-lookup"><span data-stu-id="8921d-231">Boolean</span></span>|
 
## <a name="verify-the-sbc-connection"></a><span data-ttu-id="8921d-232">SBC 연결 확인</span><span class="sxs-lookup"><span data-stu-id="8921d-232">Verify the SBC connection</span></span> 

<span data-ttu-id="8921d-233">연결을 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-233">To verify the connection:</span></span> 
- <span data-ttu-id="8921d-234">SBC가 쌍의 SBCs 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-234">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="8921d-235">SIP 옵션의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-235">Validate SIP Options.</span></span> 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="8921d-236">SBC가 쌍의 SBCs 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-236">Check if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="8921d-237">SBC에 연결한 후 원격 PowerShell 세션에서 다음 명령을 실행 하 여 해당 SBC가 쌍을 이루는 SBCs 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-237">After you connect the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session:</span></span> 

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

<span data-ttu-id="8921d-238">쌍으로 연결 된 게이트웨이는 아래 예제에 표시 된 대로 목록에 표시 되어야 하 고, **Enabled** 매개 변수는 **True**값을 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-238">The paired gateway should appear in the list as shown in the example below, and the **Enabled** parameter should display a value of **True**.</span></span> 


<span data-ttu-id="8921d-239">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="8921d-239">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

### <a name="validate-sip-options-flow"></a><span data-ttu-id="8921d-240">SIP 옵션 흐름의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8921d-240">Validate SIP Options flow</span></span> 

<span data-ttu-id="8921d-241">나가는 SIP 옵션을 사용 하 여 페어링의 유효성을 검사 하려면 SBC 관리 인터페이스를 사용 하 고 SBC가 보내는 옵션 메시지에 대 한 200 OK 응답을 수신 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-241">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="8921d-242">직접적인 라우팅이 수신 옵션을 인식 하는 경우 수신 옵션 메시지의 대화 상대 헤더 필드에 구성 된 SBC FQDN으로 보내는 SIP 옵션 메시지를 전송 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-242">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="8921d-243">들어오는 SIP 옵션을 사용 하 여 페어링의 유효성을 검사 하려면 SBC 관리 인터페이스를 사용 하 여 SBC가 직접 라우팅에서 들어오는 옵션 메시지에 대 한 응답을 보내고, 전송 하는 응답 코드는 200 OK를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8921d-243">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>


## <a name="see-also"></a><span data-ttu-id="8921d-244">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8921d-244">See also</span></span>

[<span data-ttu-id="8921d-245">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="8921d-245">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="8921d-246">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="8921d-246">Configure Direct Routing</span></span>](direct-routing-configure.md)
