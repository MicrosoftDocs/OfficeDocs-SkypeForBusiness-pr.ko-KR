---
title: 전화 시스템 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 직접 라우팅 프로토콜
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0756860bc6fad7a470a33e00ac8452e7977ecde0
ms.sourcegitcommit: 93c5afed49f47574f1b00305e5dfbb8a89be02a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44859653"
---
# <a name="direct-routing---sip-protocol"></a><span data-ttu-id="47424-103">직접 라우팅 - SIP 프로토콜</span><span class="sxs-lookup"><span data-stu-id="47424-103">Direct Routing - SIP protocol</span></span>

<span data-ttu-id="47424-104">이 문서에서는 직접 라우팅이 SIP(세션 시작 프로토콜)를 구현하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-104">This article describes how Direct Routing implements the Session Initiation Protocol (SIP).</span></span> <span data-ttu-id="47424-105">SBC(세션 테두리 컨트롤러)와 SIP 프록시 간에 트래픽을 올바르게 라우팅하려면 일부 SIP 매개 변수에 특정 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-105">To properly route traffic between a Session Border Controller (SBC) and the SIP proxy, some SIP parameters must have specific values.</span></span> <span data-ttu-id="47424-106">이 문서는 프레미스 SBC와 SIP 프록시 서비스 간의 연결을 구성할 책임이 있는 음성 관리자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47424-106">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a><span data-ttu-id="47424-107">들어오는 요청 처리: 테넌트 및 사용자 찾기</span><span class="sxs-lookup"><span data-stu-id="47424-107">Processing the incoming request: finding the tenant and user</span></span>

<span data-ttu-id="47424-108">들어오는 호출에서 SIP 프록시는 호출이 발신되는 테넌트를 찾고 이 테넌트 내에서 특정 사용자를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-108">On an incoming call, the SIP proxy needs to find the tenant to which the call is destined and find the specific user within this tenant.</span></span> <span data-ttu-id="47424-109">테넌트 관리자는 여러 테넌트에서 DID이 아닌 번호(예: +1001)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-109">The tenant administrator might configure non-DID numbers, for example +1001, in multiple tenants.</span></span> <span data-ttu-id="47424-110">따라서 여러 Microsoft 365 또는 Office 365 조직에서 지정하지 않은 숫자가 동일할 수 있으므로 번호 검색을 수행할 특정 테넌트는 찾는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-110">Therefore, it is important to find the specific tenant on which to perform the number lookup because the non-DID numbers might be the same in multiple Microsoft 365 or Office 365 organizations.</span></span>  

<span data-ttu-id="47424-111">이 섹션에서는 SIP 프록시가 테넌트와 사용자를 찾고 들어오는 연결에서 SBC의 인증을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-111">This section describes how the SIP proxy finds the tenant and the user, and performs authentication of the SBC on the incoming connection.</span></span>

<span data-ttu-id="47424-112">다음은 들어오는 호출에 대한 SIP 초대 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="47424-112">The following is an example of the SIP Invite message on an incoming call:</span></span>

| <span data-ttu-id="47424-113">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="47424-113">Parameter name</span></span> | <span data-ttu-id="47424-114">값의 예</span><span class="sxs-lookup"><span data-stu-id="47424-114">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="47424-115">Request-URI</span><span class="sxs-lookup"><span data-stu-id="47424-115">Request-URI</span></span> | <span data-ttu-id="47424-116">INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="47424-116">INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span></span> |
| <span data-ttu-id="47424-117">헤더를 통해</span><span class="sxs-lookup"><span data-stu-id="47424-117">Via Header</span></span> | <span data-ttu-id="47424-118">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="47424-118">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="47424-119">Max-Forwards 헤더</span><span class="sxs-lookup"><span data-stu-id="47424-119">Max-Forwards header</span></span> | <span data-ttu-id="47424-120">Max-Forwards:68</span><span class="sxs-lookup"><span data-stu-id="47424-120">Max-Forwards:68</span></span> |
| <span data-ttu-id="47424-121">헤더에서</span><span class="sxs-lookup"><span data-stu-id="47424-121">From Header</span></span> | <span data-ttu-id="47424-122">헤더에서: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span><span class="sxs-lookup"><span data-stu-id="47424-122">From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span></span> |
| <span data-ttu-id="47424-123">헤더로</span><span class="sxs-lookup"><span data-stu-id="47424-123">To Header</span></span> | <span data-ttu-id="47424-124">To: sip:+183338006777@sbc1.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="47424-124">To: sip:+183338006777@sbc1.adatum.biz</span></span> | 
| <span data-ttu-id="47424-125">CSeq 헤더</span><span class="sxs-lookup"><span data-stu-id="47424-125">CSeq header</span></span> | <span data-ttu-id="47424-126">CSeq: 1 INVITE</span><span class="sxs-lookup"><span data-stu-id="47424-126">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="47424-127">연락처 헤더</span><span class="sxs-lookup"><span data-stu-id="47424-127">Contact Header</span></span> | <span data-ttu-id="47424-128">연락처: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls></span><span class="sxs-lookup"><span data-stu-id="47424-128">Contact: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls></span></span> | 

<span data-ttu-id="47424-129">초대를 받을 때 SIP 프록시는 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-129">On receiving the invite, the SIP proxy performs the following steps:</span></span>

1. <span data-ttu-id="47424-130">인증서를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-130">Check the certificate.</span></span> <span data-ttu-id="47424-131">초기 연결에서 직접 라우팅 서비스는 연락처 헤더에 제공된 FQDN 이름을 사용하여 제공된 인증서의 일반 이름 또는 주체 대체 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-131">On the initial connection, the Direct Routing service takes the FQDN name presented in the Contact header and matches it to the Common Name or Subject Alternative name of the presented certificate.</span></span> <span data-ttu-id="47424-132">SBC 이름은 다음 옵션 중 하나와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-132">The SBC name must match one of the following options:</span></span>

   - <span data-ttu-id="47424-133">옵션 1.</span><span class="sxs-lookup"><span data-stu-id="47424-133">Option 1.</span></span> <span data-ttu-id="47424-134">연락처 헤더에 제시된 전체 FQDN 이름은 제시된 인증서의 일반 이름/주체 대체 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-134">The full FQDN name presented in the Contact header must match the Common Name/Subject Alternative name of the presented certificate.</span></span>  

   - <span data-ttu-id="47424-135">옵션 2.</span><span class="sxs-lookup"><span data-stu-id="47424-135">Option 2.</span></span> <span data-ttu-id="47424-136">연락처 헤더에 제시된 FQDN 이름의 도메인 부분(예 adatum.biz: FQDN 이름 sbc1.adatum.biz)은 일반 이름/주체 대체 이름(예: \*.adatum.biz)의 와일드카드 값과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-136">The domain portion of the FQDN name presented in the Contact header (for example adatum.biz of the FQDN name sbc1.adatum.biz) must match the wildcard value in Common Name/Subject Alternative Name (for example \*.adatum.biz).</span></span>

2. <span data-ttu-id="47424-137">연락처 헤더에 제시된 전체 FQDN 이름을 사용하여 테넌트 찾기를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-137">Try to find a tenant using the full FQDN name presented in the Contact header.</span></span>  

   <span data-ttu-id="47424-138">연락처 헤더(sbc1.adatum.biz)의 FQDN 이름이 Microsoft 365 또는 Office 365 조직에서 DNS 이름으로 등록되어 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-138">Check if the FQDN name from the Contact header (sbc1.adatum.biz) is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="47424-139">발견된 경우 사용자의 검색은 SBC FQDN이 도메인 이름으로 등록된 테넌트에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-139">If found, the lookup of the user is performed in the tenant that has the SBC FQDN registered as a Domain name.</span></span> <span data-ttu-id="47424-140">찾을 수 없는 경우 3단계가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-140">If not found, Step 3 applies.</span></span>   

3. <span data-ttu-id="47424-141">3단계는 2단계가 실패한 경우만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-141">Step 3 only applies if Step 2 failed.</span></span> 

   <span data-ttu-id="47424-142">호스트 부분을 제거한 후 연락처 헤더(FQDN: sbc12.adatum.biz)에 있는 FQDN에서 호스트 부분을 제거하고adatum.biz) 이 이름이 Microsoft 365 또는 Office 365 조직에서 DNS 이름으로 등록되어 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-142">Remove the host portion from the FQDN, presented in the Contact header (FQDN: sbc12.adatum.biz, after removing the host portion: adatum.biz), and check if this name is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="47424-143">발견된 경우 이 테넌트에서 사용자 Lookup이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-143">If found, the user lookup is performed in this tenant.</span></span> <span data-ttu-id="47424-144">찾을 수 없는 경우 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-144">If not found, the call fails.</span></span>

4. <span data-ttu-id="47424-145">요청-URI에 제공된 전화 번호를 사용하여 2단계 또는 3단계에서 찾은 테넌트 내에서 역방향 숫자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-145">Using the phone number presented in the Request-URI, perform the reverse number lookup within the tenant found in Step 2 or 3.</span></span> <span data-ttu-id="47424-146">제공된 전화 번호를 이전 단계에서 찾은 테넌트 내의 사용자 SIP URI와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-146">Match the presented phone number to a user SIP URI within the tenant found on the previous step.</span></span>

5. <span data-ttu-id="47424-147">트렁크 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-147">Apply trunk settings.</span></span> <span data-ttu-id="47424-148">이 SBC에 대한 테넌트 관리자가 설정한 매개 변수를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-148">Find the parameters set by the tenant admin for this SBC.</span></span>

   <span data-ttu-id="47424-149">Microsoft는 Microsoft SIP 프록시와 쌍을 이루는 SBC 간에 타사 SIP 프록시 또는 사용자 에이전트 서버가 있는 기능을 지원하지 않습니다. 이 서버는 쌍을 이루는 SBC에서 만든 요청 URI를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-149">Microsoft does not support having a third-party SIP proxy or User Agent Server between the Microsoft SIP proxy and the paired SBC, which might modify the Request URI created by the paired SBC.</span></span>

   <span data-ttu-id="47424-150">하나의 SBC가 여러 테넌트(통신 사업자 시나리오)에 상호 연결되는 시나리오에 필요한 두 가지(2단계 및 3단계)에 대한 요구 사항은 이 문서의 후반부에 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-150">The requirements for the two lookups (steps 2 and 3) needed for the scenario where one SBC is interconnected to many tenants (carrier scenario) are covered later in this article.</span></span>

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a><span data-ttu-id="47424-151">연락처 헤더 및 요청-URI에 대한 자세한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="47424-151">Detailed requirements for Contact header and Request-URI</span></span>

#### <a name="contact-header"></a><span data-ttu-id="47424-152">연락처 헤더</span><span class="sxs-lookup"><span data-stu-id="47424-152">Contact header</span></span>

<span data-ttu-id="47424-153">Microsoft SIP 프록시에 들어오는 모든 호출의 경우 연락처 헤더에 다음과 같이 URI 호스트 이름에 쌍을 이른 SBC FQDN이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-153">For all incoming calls to the Microsoft SIP proxy, the Contact header must have the paired SBC FQDN in the URI hostname as follows:</span></span>

<span data-ttu-id="47424-154">구문: <sip:phone 또는 sip address@FQDN SBC;transport=tls></span><span class="sxs-lookup"><span data-stu-id="47424-154">Syntax: Contact:  <sip:phone or sip address@FQDN of the SBC;transport=tls></span></span> 

<span data-ttu-id="47424-155">이 이름은 제시된 인증서의 일반 이름 또는 주체 대체 이름 필드에도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-155">This name must also be in the Common Name or Subject Alternative name field(s) of the presented certificate.</span></span> <span data-ttu-id="47424-156">Microsoft는 인증서의 일반 이름 또는 주체 대체 이름 필드에 이름의 와일드카드 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-156">Microsoft supports using wildcard values of the name(s) in the Common Name or Subject Alternative Name fields of the certificate.</span></span>   

<span data-ttu-id="47424-157">와일드카드에 대한 지원은 [RFC 2818, 섹션 3.1에 설명되어 있습니다.](https://tools.ietf.org/html/rfc2818#section-3.1)</span><span class="sxs-lookup"><span data-stu-id="47424-157">The support for wildcards is described in [RFC 2818, section 3.1](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="47424-158">특히 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-158">Specifically:</span></span>

<span data-ttu-id="47424-159">*"이름에는 단일 도메인 이름 구성 요소 또는 구성 요소 조각과 일치하는 것으로 간주되는 와일드카드 \* 문자가 포함될 수 있습니다. 예: .a.com 일치하지만 foo.a.com \* bar.foo.a.com. \* f.com은 foo.com 일치하지만 bar.com."*</span><span class="sxs-lookup"><span data-stu-id="47424-159">*"Names may contain the wildcard character \* which is considered to match any single domain name component or component fragment. E.g., \*.a.com matches foo.a.com but not bar.foo.a.com. f\*.com matches foo.com but not bar.com."*</span></span>

<span data-ttu-id="47424-160">SIP 메시지에 있는 연락처 헤더에 있는 값이 SBC에서 두 개 이상 전송되는 경우 연락처 헤더의 첫 번째 값의 FQDN 부분만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-160">If more than one value in the Contact header presented in a SIP message is sent by the SBC, only the FQDN portion of the first value of the Contact header is used.</span></span>

#### <a name="request-uri"></a><span data-ttu-id="47424-161">Request-URI</span><span class="sxs-lookup"><span data-stu-id="47424-161">Request-URI</span></span> 

<span data-ttu-id="47424-162">들어오는 모든 호출의 경우 요청 URI는 전화 번호를 사용자와 일치하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-162">For all incoming calls, the Request-URI is used to match the phone number to a user.</span></span>   

<span data-ttu-id="47424-163">현재 전화 번호는 다음 예제와 같이 더하기 기호(+)를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-163">Currently The phone number must contain a plus sign (+) as shown in the following example.</span></span> 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a><span data-ttu-id="47424-164">연락처 및 Record-Route 헤더 고려 사항</span><span class="sxs-lookup"><span data-stu-id="47424-164">Contact and Record-Route headers considerations</span></span>

<span data-ttu-id="47424-165">SIP 프록시는 새 대화 상자 내 클라이언트 트랜잭션(예: Bye 또는 다시 초대) 및 SIP 옵션에 회신할 때 다음 홉 FQDN을 계산해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-165">The SIP proxy needs to calculate the next hop FQDN for new in-dialog client transactions (for example Bye or Re-Invite), and when replying to SIP Options.</span></span> <span data-ttu-id="47424-166">연락처 또는 Record-Route 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-166">Either Contact or Record-Route are used.</span></span> 

<span data-ttu-id="47424-167">RFC 3261에 따라 연락처 헤더는 새 대화 상자가 될 수 있는 모든 요청에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-167">According to RFC 3261, Contact header is required in any request that can result in a new dialog.</span></span> <span data-ttu-id="47424-168">이 Record-Route 프록시가 대화 상자의 향후 요청 경로를 유지하려는 경우 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-168">The Record-Route is only required if a proxy wants to stay on the path of future requests in a dialog.</span></span> <span data-ttu-id="47424-169">프록시 SBC가 직접 라우팅에 대한 로컬 미디어 최적화와 함께 사용 중이면 프록시 SBC가 경로에 유지해야 하여 레코드 경로를 구성해야 합니다. [](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization)</span><span class="sxs-lookup"><span data-stu-id="47424-169">If a proxy SBC is in use with [Local Media Optimization for Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization), a record route will need to be configured as the proxy SBC needs to stay in the route.</span></span> 

<span data-ttu-id="47424-170">프록시 SBC를 사용하지 않는 경우 연락처 헤더만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-170">Microsoft recommends using only Contact header if a proxy SBC is not used:</span></span>

- <span data-ttu-id="47424-171">RFC 3261당 Record-Route 프록시가 대화 상자에서 향후 요청의 경로를 유지하려는 경우 사용됩니다. Microsoft SIP 프록시와 쌍을 이루는 SBC 간에 모든 트래픽이 연결될 때 프록시 SBC가 구성되지 않은 경우 필수는 아 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-171">Per RFC 3261, Record-Route is used if a proxy wants to stay on the path of future requests in a dialog, which is not essential if no proxy SBC is configured as all traffic goes between the Microsoft SIP proxy and the paired SBC.</span></span> 

- <span data-ttu-id="47424-172">Microsoft SIP 프록시는 아웃바운드 ping 옵션을 보낼 때 연락처 헤더(레코드 경로 아래)만 사용하여 다음 홉을 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-172">The Microsoft SIP proxy uses only Contact header (not Record-Route) to determine the next hop when sending outbound ping Options.</span></span> <span data-ttu-id="47424-173">프록시 SBC를 사용하지 않는 경우 두 매개 변수(연락처 및 레코드 경로) 대신 하나의 매개 변수(연락처)만 구성하면 관리가 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-173">Configuring only one parameter (Contact) instead of two (Contact and Record-Route) simplifies the administration if a proxy SBC is not in use.</span></span> 

<span data-ttu-id="47424-174">다음 홉을 계산하기 위해 SIP 프록시는 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-174">To calculate the next hop, the SIP proxy uses:</span></span>

- <span data-ttu-id="47424-175">우선 순위 1.</span><span class="sxs-lookup"><span data-stu-id="47424-175">Priority 1.</span></span> <span data-ttu-id="47424-176">최상위 레코드 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="47424-176">Top-level Record-Route.</span></span> <span data-ttu-id="47424-177">최상위 수준 Record-Route FQDN 이름 또는 IP를 포함하는 경우 FQDN 이름 또는 IP는 아웃바운드 대화 상자 연결을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-177">If the top-level Record-Route contains the FQDN name or IP, the FQDN name or IP is used to make the outbound in-dialog connection.</span></span>

- <span data-ttu-id="47424-178">우선 순위 2.</span><span class="sxs-lookup"><span data-stu-id="47424-178">Priority 2.</span></span> <span data-ttu-id="47424-179">연락처 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="47424-179">Contact header.</span></span> <span data-ttu-id="47424-180">이 Record-Route 없는 경우 SIP 프록시는 연락처 헤더의 값을 찾아 아웃바운드 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-180">If Record-Route does not exist, the SIP proxy will look up the value of the Contact header to make the outbound connection.</span></span> <span data-ttu-id="47424-181">(권장되는 구성입니다.)</span><span class="sxs-lookup"><span data-stu-id="47424-181">(This is the recommended configuration.)</span></span>

<span data-ttu-id="47424-182">연락처 및 Record-Route 사용하는 경우 SBC 관리자는 해당 값을 동일하게 유지해야 하여 관리 오버헤드가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-182">If both Contact and Record-Route are used, the SBC administrator must keep their values identical, which causes administrative overhead.</span></span> 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a><span data-ttu-id="47424-183">연락처 또는 연락처에서 FQDN 이름 Record-Route</span><span class="sxs-lookup"><span data-stu-id="47424-183">Use of FQDN name in Contact or Record-Route</span></span>

<span data-ttu-id="47424-184">IP 주소의 사용은 Record-Route 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-184">Use of an IP address is not supported in either Record-Route or Contact.</span></span> <span data-ttu-id="47424-185">지원되는 유일한 옵션은 SBC 인증서의 일반 이름 또는 주체 대체 이름과 일치해야 하는 FQDN입니다(인증서의 와일드카드 값이 지원됩니다).</span><span class="sxs-lookup"><span data-stu-id="47424-185">The only supported option is an FQDN, which must match either the Common Name or Subject Alternative Name of the SBC certificate (wildcard values in the certificate are supported).</span></span>

- <span data-ttu-id="47424-186">레코드 경로 또는 연락처에 IP 주소가 있는 경우 인증서 검사가 실패하고 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-186">If an IP address is presented in Record-route or Contact, the certificate check fails and the call fails.</span></span>

- <span data-ttu-id="47424-187">FQDN이 제시된 인증서의 일반 또는 주체 대체 이름 값과 일치하지 않는 경우 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-187">If the FQDN does not match the value of the Common or Subject Alternative Name in the presented certificate, the call fails.</span></span> 

## <a name="inbound-call-sip-dialog-description"></a><span data-ttu-id="47424-188">인바운드 호출: SIP 대화 상자 설명</span><span class="sxs-lookup"><span data-stu-id="47424-188">Inbound call: SIP dialog description</span></span>

<span data-ttu-id="47424-189">다음 표에서는 비 우회 모드와 우회 모드 간의 호출 흐름 차이 및 유사성에 대한 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-189">The following table below summarizes the call flow differences and similarities between non-bypass and bypass modes:</span></span>

| <span data-ttu-id="47424-190">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="47424-190">Parameter name</span></span> | <span data-ttu-id="47424-191">비 우회 모드</span><span class="sxs-lookup"><span data-stu-id="47424-191">Non-bypass mode</span></span> | <span data-ttu-id="47424-192">우회 모드</span><span class="sxs-lookup"><span data-stu-id="47424-192">Bypass mode</span></span>
| :---------------------  |:---------------------- |:----------------|
| <span data-ttu-id="47424-193">183개 및 200개 메시지의 미디어 후보</span><span class="sxs-lookup"><span data-stu-id="47424-193">Media candidates in 183 and 200 messages coming from</span></span> | <span data-ttu-id="47424-194">미디어 프로세서</span><span class="sxs-lookup"><span data-stu-id="47424-194">Media processors</span></span> | <span data-ttu-id="47424-195">클라이언트</span><span class="sxs-lookup"><span data-stu-id="47424-195">Clients</span></span> | 
| <span data-ttu-id="47424-196">SBC에서 수신할 수 있는 183개 메시지 수</span><span class="sxs-lookup"><span data-stu-id="47424-196">Number of 183 messages SBC can receive</span></span> | <span data-ttu-id="47424-197">세션당 1개</span><span class="sxs-lookup"><span data-stu-id="47424-197">One per session</span></span> | <span data-ttu-id="47424-198">다중</span><span class="sxs-lookup"><span data-stu-id="47424-198">Multiple</span></span> | 
| <span data-ttu-id="47424-199">임시 응답을 사용하여 호출할 수 있습니다(183).</span><span class="sxs-lookup"><span data-stu-id="47424-199">Call can be with provisional answer (183)</span></span> | <span data-ttu-id="47424-200">예</span><span class="sxs-lookup"><span data-stu-id="47424-200">Yes</span></span> | <span data-ttu-id="47424-201">예</span><span class="sxs-lookup"><span data-stu-id="47424-201">Yes</span></span> |
| <span data-ttu-id="47424-202">임시 응답 없이 통화할 수 있습니다(183).</span><span class="sxs-lookup"><span data-stu-id="47424-202">Call can be without provisional answer (183)</span></span> | <span data-ttu-id="47424-203">예</span><span class="sxs-lookup"><span data-stu-id="47424-203">Yes</span></span> | <span data-ttu-id="47424-204">예</span><span class="sxs-lookup"><span data-stu-id="47424-204">Yes</span></span> |

###  <a name="non-media-bypass-flow"></a><span data-ttu-id="47424-205">비미디어 우회 흐름</span><span class="sxs-lookup"><span data-stu-id="47424-205">Non-media bypass flow</span></span>

<span data-ttu-id="47424-206">Teams 사용자는 동시에 여러 엔드포인트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-206">A Teams user might have multiple endpoints at the same time.</span></span> <span data-ttu-id="47424-207">예를 들어 Windows용 Teams 클라이언트, iPhone용 Teams 클라이언트 및 Teams Phone(Teams Android 클라이언트)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-207">For example, Teams for Windows client, Teams for iPhone client, and Teams Phone (Teams Android client).</span></span> <span data-ttu-id="47424-208">각 엔드포인트는 다음과 같이 HTTP rest를 신호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-208">Each endpoint might signal an HTTP rest as follows:</span></span>

-   <span data-ttu-id="47424-209">호출 진행률 - SIP 프록시에 의해 SIP 메시지 180으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-209">Call progress – converted by the SIP proxy to the SIP message 180.</span></span> <span data-ttu-id="47424-210">메시지 180을 수신할 때 SBC는 로컬 벨소리를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-210">On receiving message 180, the SBC must generate local ringing.</span></span>

-   <span data-ttu-id="47424-211">미디어 응답 – SDP(세션 설명 프로토콜)의 미디어 후보를 사용하여 SIP 프록시에서 메시지 183으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-211">Media answer – converted by the SIP proxy to message 183 with media candidates in Session Description Protocol (SDP).</span></span> <span data-ttu-id="47424-212">메시지 183을 수신할 때 SBC는 SDP 메시지에 수신된 미디어 후보에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-212">On receiving message 183, the SBC expects to connect to the media candidates received in the SDP message.</span></span> <span data-ttu-id="47424-213">경우에 따라 미디어 답변이 생성되지 않을 수 있으며 끝점은 "수락된 통화" 메시지로 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-213">Note that in some cases the Media answer might not be generated, and the end point might answer with “Call Accepted” message.</span></span>

-   <span data-ttu-id="47424-214">수락된 호출 - SIP 프록시에서 SDP를 사용하여 SIP 메시지 200으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-214">Call accepted – converted by the SIP proxy to SIP message 200 with SDP.</span></span> <span data-ttu-id="47424-215">메시지 200을 수신할 때 SBC는 제공된 SDP 후보와 미디어를 보내고 받을 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-215">On receiving message 200, the SBC is expected to send and receive media to and from the provided SDP candidates.</span></span>

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a><span data-ttu-id="47424-216">여러 엔드포인트에 프로비전 응답이 울림</span><span class="sxs-lookup"><span data-stu-id="47424-216">Multiple endpoints ringing with provisional answer</span></span>

1.  <span data-ttu-id="47424-217">SBC에서 첫 번째 초대를 받을 때 SIP 프록시는 "SIP SIP/2.0 100 시도 중" 메시지를 보내고 모든 최종 사용자 엔드포인트에 들어오는 호출에 대해 알림합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-217">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="47424-218">알림이 표시될 때 각 엔드포인트가 "호출 진행률" 메시지를 SIP 프록시로 보내기 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-218">Upon notification, each endpoint will start ringing and sending "Call progress” messages to the SIP proxy.</span></span> <span data-ttu-id="47424-219">Teams 사용자에게는 여러 개의 끝점이 있을 수 있기 때문에 SIP 프록시는 여러 통화 진행률 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-219">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="47424-220">클라이언트에서 받은 모든 호출 진행률 메시지에 대해 SIP 프록시는 호출 진행률 메시지를 SIP 메시지 "SIP SIP/2.0 180 시도 중"으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-220">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span> <span data-ttu-id="47424-221">이러한 메시지를 보내는 간격은 호출 컨트롤러에서 메시지를 수신하는 간격으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-221">The interval for sending such messages is defined by the interval of the receiving messages from the Call Controller.</span></span> <span data-ttu-id="47424-222">다음 다이어그램에는 SIP 프록시에서 생성된 두 개의 180개의 메시지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-222">In the following diagram, there are two 180 messages generated by the SIP proxy.</span></span> <span data-ttu-id="47424-223">이러한 메시지는 사용자의 두 Teams 엔드포인트에서 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-223">These messages come from the two Teams endpoints of the user.</span></span> <span data-ttu-id="47424-224">클라이언트마다 고유한 태그 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-224">The clients each have a unique Tag ID.</span></span>  <span data-ttu-id="47424-225">다른 엔드포인트에서 오는 모든 메시지는 별도의 세션이 됩니다("To" 필드의 "tag" 매개 변수는 다를 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="47424-225">Every message coming from a different endpoint will be a separate session (the parameter “tag” in the “To” field will be different).</span></span> <span data-ttu-id="47424-226">하지만 엔드포인트는 다음 다이어그램과 같이 메시지 180을 생성하지 못하고 바로 메시지 183을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-226">But an endpoint might not generate message 180 and send message 183 right away as shown in the following diagram.</span></span>

4.  <span data-ttu-id="47424-227">엔드포인트가 엔드포인트의 미디어 후보의 IP 주소로 미디어 응답 메시지를 생성하면 SIP 프록시는 수신된 메시지를 "SIP 183 세션 진행률" 메시지로 변환하고 클라이언트의 SDP가 미디어 프로세서의 SDP로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-227">Once an endpoint generates a Media Answer message with the IP addresses of endpoint’s media candidates, the SIP proxy converts the message received to a "SIP 183 Session Progress" message with the SDP from the client replaced by the SDP from the Media Processor.</span></span> <span data-ttu-id="47424-228">다음 다이어그램에서는 포크 2의 엔드포인트가 호출에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-228">In the following diagram, the endpoint from Fork 2 answered the call.</span></span> <span data-ttu-id="47424-229">트렁크를 무시하지 않는 경우 183 SIP 메시지는 한 번만 생성됩니다(링 봇 또는 클라이언트 끝점).</span><span class="sxs-lookup"><span data-stu-id="47424-229">If the trunk is non-bypassed, the 183 SIP message is generated only once (either Ring Bot or Client End Point).</span></span> <span data-ttu-id="47424-230">183은 기존 포크에 오거나 새 포크를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-230">The 183 might come on an existing fork or start a new one.</span></span>

5.  <span data-ttu-id="47424-231">통화 수락 메시지는 통화를 수락한 엔드포인트의 최종 후보와 함께 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-231">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="47424-232">통화 수락 메시지는 SIP 메시지 200으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-232">The Call Acceptance message is converted to SIP message 200.</span></span> 

![여러 엔드포인트에 프로비전 응답이 울리는 다이어그램](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a><span data-ttu-id="47424-234">임시 응답 없이 벨소리가 울리는 여러 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="47424-234">Multiple endpoints ringing without provisional answer</span></span>

1.  <span data-ttu-id="47424-235">SBC에서 첫 번째 초대를 받을 때 SIP 프록시는 "SIP SIP/2.0 100 시도 중" 메시지를 보내고 모든 최종 사용자 엔드포인트에 들어오는 호출에 대해 알림합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-235">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="47424-236">알림이 표시될 때 각 엔드포인트는 "호출 진행률" 메시지에 대한 벨이 울리기 시작하고 SIP 프록시로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-236">Upon notification, each endpoint will start ringing and sending the message "Call progress” to the SIP proxy.</span></span> <span data-ttu-id="47424-237">Teams 사용자에게는 여러 개의 끝점이 있을 수 있기 때문에 SIP 프록시는 여러 통화 진행률 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-237">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="47424-238">클라이언트에서 받은 모든 호출 진행률 메시지에 대해 SIP 프록시는 호출 진행률 메시지를 SIP 메시지 "SIP SIP/2.0 180 시도 중"으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-238">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span>  <span data-ttu-id="47424-239">메시지를 보내는 간격은 호출 컨트롤러에서 메시지를 받는 간격으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-239">The interval for sending the messages is defined by the interval of receiving the messages from the Call Controller.</span></span> <span data-ttu-id="47424-240">아래 그림에는 SIP 프록시에서 생성된 두 개의 180개의 메시지가 있습니다. 즉, 사용자가 세 개의 Teams 클라이언트에 로그인하고 각 클라이언트가 호출 진행률을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-240">On the picture below there are two 180 messages generated by the SIP proxy, meaning that user logged into three Teams clients and each client send the call progress.</span></span> <span data-ttu-id="47424-241">모든 메시지는 별도의 세션이 됩니다("To" 필드의 "tag" 매개 변수는 서로 다를 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="47424-241">Every message will be a separate session (parameter “tag” in “To” field is different)</span></span>

4.  <span data-ttu-id="47424-242">통화 수락 메시지는 통화를 수락한 엔드포인트의 최종 후보와 함께 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-242">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="47424-243">통화 수락 메시지는 SIP 메시지 200으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-243">The Call Acceptance message is converted to SIP message 200.</span></span> 

![여러 엔드포인트가 임시 응답 없이 울리는 다이어그램](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a><span data-ttu-id="47424-245">미디어 우회 흐름</span><span class="sxs-lookup"><span data-stu-id="47424-245">Media bypass flow</span></span>

<span data-ttu-id="47424-246">미디어 우회 시나리오에서 동일한 메시지(100 시도, 180, 183)가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-246">The same messages (100 Trying, 180, 183) are used in the media bypass scenario.</span></span> 

<span data-ttu-id="47424-247">아래 schema는 호출 흐름 우회의 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="47424-247">The schema below shows an example of the bypass call flow.</span></span> <span data-ttu-id="47424-248">미디어 후보는 서로 다른 엔드포인트에서 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-248">Note that the media candidates can come from different endpoints.</span></span> 

![여러 엔드포인트에 프로비전 응답이 울리는 다이어그램](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a><span data-ttu-id="47424-250">대체 옵션</span><span class="sxs-lookup"><span data-stu-id="47424-250">Replaces option</span></span>

<span data-ttu-id="47424-251">SBC는 Replaces로 초대를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-251">The SBC must support Invite with Replaces.</span></span>

## <a name="size-of-sdp-considerations"></a><span data-ttu-id="47424-252">SDP 고려 사항의 크기</span><span class="sxs-lookup"><span data-stu-id="47424-252">Size of SDP considerations</span></span>

<span data-ttu-id="47424-253">직접 라우팅 인터페이스는 1,500비트가 넘는 SIP 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-253">The Direct Routing interface might send a SIP message exceeding 1,500 bytes.</span></span>  <span data-ttu-id="47424-254">SDP의 크기로 인해 주로 이 문제가 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-254">The size of SDP primarily causes this.</span></span> <span data-ttu-id="47424-255">그러나 SBC 뒤에 UDP 트렁크가 있는 경우 Microsoft SIP 프록시에서 트렁크로 전달된 경우 메시지를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-255">However, if there is a UDP trunk behind the SBC, it might reject the message if it is forwarded from the Microsoft SIP proxy to the trunk unmodified.</span></span> <span data-ttu-id="47424-256">UDP 트렁크에 메시지를 보낼 때 SBC의 SDP에서 일부 값을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-256">Microsoft recommends stripping some values in SDP on the SBC when sending the message to the UDP trunks.</span></span> <span data-ttu-id="47424-257">예를 들어 ICE 후보 또는 사용되지 않는 코덱을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-257">For example, the ICE candidates or unused codecs can be removed.</span></span>

## <a name="call-transfer"></a><span data-ttu-id="47424-258">통화 전송</span><span class="sxs-lookup"><span data-stu-id="47424-258">Call transfer</span></span>

<span data-ttu-id="47424-259">직접 라우팅은 호출 전송에 대한 두 가지 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-259">Direct Routing supports two methods for call transfer:</span></span>

- <span data-ttu-id="47424-260">옵션 1.</span><span class="sxs-lookup"><span data-stu-id="47424-260">Option 1.</span></span> <span data-ttu-id="47424-261">SIP 프록시 프로세스는 클라이언트에서 로컬로 참조하고 RFC 3892의 섹션 7.1에 설명된 바와 같이 심판 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-261">SIP proxy processes Refer from the client locally and acts as a Referee as described in section 7.1 of RFC 3892.</span></span>

  <span data-ttu-id="47424-262">이 옵션을 사용하면 SIP 프록시가 전송을 종료하고 새 초대를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-262">With this option, the SIP proxy terminates the transfer and adds a new Invite.</span></span> 


- <span data-ttu-id="47424-263">옵션 2.</span><span class="sxs-lookup"><span data-stu-id="47424-263">Option 2.</span></span> <span data-ttu-id="47424-264">SIP 프록시는 SBC 참조를 보내고 RFC 5589의 섹션 6에서 설명하는 전송자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-264">SIP proxy sends the Refer to the SBC and acts as a Transferor as describing in Section 6 of RFC 5589.</span></span>

  <span data-ttu-id="47424-265">이 옵션을 사용하면 SIP 프록시는 SBC 참조를 보내고 SBC가 전송을 완전히 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-265">With this option, the SIP proxy sends a Refer to the SBC and expects the SBC to handle the Transfer fully.</span></span>

<span data-ttu-id="47424-266">SIP 프록시는 SBC에서 보고하는 기능에 따라 메서드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-266">The SIP proxy selects the method based on the capabilities reported by the SBC.</span></span> <span data-ttu-id="47424-267">SBC가 "참조" 메서드를 지원하고 있는 경우 SIP 프록시는 호출 전송에 옵션 2를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-267">If the SBC indicates that it supports the method “Refer”, the SIP proxy will use Option 2 for call transfers.</span></span>

<span data-ttu-id="47424-268">다음은 참조 메서드가 지원되는 메시지를 보내는 SBC의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="47424-268">The following is an example of an SBC sending the message that the Refer method is supported:</span></span>

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

<span data-ttu-id="47424-269">SBC가 지원되는 방법으로 참조를 나타내지 않는 경우 직접 라우팅은 옵션 1(SIP 프록시가 심판의 역할을 하여)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-269">If the SBC doesn’t indicate that Refer as a supported method, Direct Routing will use Option 1 (SIP proxy acts as a Referee) .</span></span> <span data-ttu-id="47424-270">또한 SBC는 Notify 메서드를 지원하고 있는 신호를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-270">The SBC  must also signal that it supports the Notify method:</span></span>

<span data-ttu-id="47424-271">참조 메서드가 지원되지 않는다는 것을 나타내는 SBC의 예:</span><span class="sxs-lookup"><span data-stu-id="47424-271">Example of SBC indicating that Refer method is not supported:</span></span>

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a><span data-ttu-id="47424-272">SIP 프록시 프로세스는 클라이언트에서 로컬로 참조하고 심판의 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-272">SIP proxy processes Refer from the client locally and acts as a Referee</span></span>

<span data-ttu-id="47424-273">SBC에서 참조 메서드가 지원되지 않는다고 표시하면 SIP 프록시가 심판의 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-273">If the SBC indicated that the Refer method is not supported, the SIP proxy acts as a Referee.</span></span> 

<span data-ttu-id="47424-274">클라이언트에서 오는 참조 요청은 SIP 프록시에서 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-274">The Refer request that comes from the client will be terminated on the SIP proxy.</span></span> <span data-ttu-id="47424-275">(클라이언트의 참조 요청은 다음 다이어그램에서 "Dave에 대한 호출 전송"으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-275">(The Refer request from the client is shown as “Call transfer to Dave” in the following diagram.</span></span>  <span data-ttu-id="47424-276">자세한 내용은 [RFC 3892의 섹션 7.1을 참조하세요.](https://www.ietf.org/rfc/rfc3892.txt)</span><span class="sxs-lookup"><span data-stu-id="47424-276">For more information, see section 7.1 of [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt).</span></span> 

![여러 엔드포인트에 프로비전 응답이 울리는 다이어그램](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a><span data-ttu-id="47424-278">SIP 프록시는 SBC 참조를 보내고 전송기 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-278">SIP proxy send the Refer to the SBC and acts as a Transferor</span></span>

<span data-ttu-id="47424-279">이는 통화 전송에 선호되는 방법으로, 인증을 무시하는 미디어를 찾는 디바이스에 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="47424-279">This is the preferred method for call transfers, and it is mandatory for devices seeking media bypass certification.</span></span> <span data-ttu-id="47424-280">참조를 처리할 수 있는 SBC가 없는 호출 전송은 미디어 우회 모드에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-280">Call Transfer without the SBC being able to handle Refer is not supported in media bypass mode.</span></span> 

<span data-ttu-id="47424-281">표준은 RFC 5589의 섹션 6에 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-281">The standard is explained in Section 6 of RFC 5589.</span></span> <span data-ttu-id="47424-282">관련 RFC는</span><span class="sxs-lookup"><span data-stu-id="47424-282">The related RFCs are:</span></span>

- [<span data-ttu-id="47424-283">SIP(세션 시작 프로토콜) 호출 제어 - 전송</span><span class="sxs-lookup"><span data-stu-id="47424-283">Session Initiation Protocol (SIP) Call Control - Transfer</span></span>](https://tools.ietf.org/html/rfc5589)

- [<span data-ttu-id="47424-284">SIP(세션 시작 프로토콜) "대체" 헤더</span><span class="sxs-lookup"><span data-stu-id="47424-284">Session Initiation Protocol (SIP) "Replaces" Header</span></span>](https://tools.ietf.org/html/rfc3891)

- [<span data-ttu-id="47424-285">SIP(세션 시작 프로토콜) "참조" 메커니즘</span><span class="sxs-lookup"><span data-stu-id="47424-285">Session Initiation Protocol (SIP) "Referred-By" mechanism</span></span>](https://tools.ietf.org/html/rfc3892)

<span data-ttu-id="47424-286">이 옵션은 SIP 프록시가 전송기 역할을 하여 SBC에 참조 메시지를 보낸 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-286">This option assumes that the SIP proxy acts as a Transferor and sends a Refer message to the SBC.</span></span> <span data-ttu-id="47424-287">SBC는 Transferee의 역할을 하여 전송할 새 제안을 생성하기 위해 참조를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-287">The SBC acts as a Transferee and handles the Refer to generate a new offer for transfer.</span></span> <span data-ttu-id="47424-288">두 가지 가능한 경우:</span><span class="sxs-lookup"><span data-stu-id="47424-288">There are two possible cases:</span></span>

- <span data-ttu-id="47424-289">통화는 외부 PSTN 참가자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-289">The call is transferred to an external PSTN participant.</span></span> 
- <span data-ttu-id="47424-290">통화는 SBC를 통해 한 Teams 사용자에서 동일한 테넌트의 다른 Teams 사용자로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-290">The call is transferred from one Teams user to another Teams user in the same tenant via the SBC.</span></span> 

<span data-ttu-id="47424-291">SBC를 통해 한 Teams 사용자로부터 다른 Teams 사용자로 통화를 전송하는 경우 SBC는 참조 메시지에 수신된 정보를 사용하여 전송 대상(Teams 사용자)에 대한 새 초대(새 대화 상자 시작)를 발급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-291">If the call is transferred from one Teams user to another via the SBC, the SBC is expected to issue a new invite (start a new dialog) for the transfer target (the Teams user) using the information received in the Refer message.</span></span> 

<span data-ttu-id="47424-292">내부적으로 요청 트랜잭션에 대한 To/Transferor 필드를 채우기 위해 SIP 프록시는 REFER-TO/REFERRED-BY 헤더 내에서 이 정보를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-292">To populate the To/Transferor fields for the transaction of the request internally, the SIP proxy needs to convey this information  inside the REFER-TO/REFERRED-BY headers.</span></span> 

<span data-ttu-id="47424-293">SIP 프록시는 호스트 이름의 SIP 프록시 FQDN 및 다음 중 하나로 구성된 SIP URI로 REFER-TO를 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-293">The SIP proxy will form the REFER-TO as a SIP URI comprised of a SIP proxy FQDN in the hostname and either one of the following:</span></span>

- <span data-ttu-id="47424-294">전송 대상이 전화 번호인 경우 URI의 사용자 이름 부분에 있는 E.164 전화 번호</span><span class="sxs-lookup"><span data-stu-id="47424-294">An E.164 phone number in the username part of the URI in case the transfer target is a phone number, or</span></span>

- <span data-ttu-id="47424-295">전체 전송 대상 MRI 및 테넌트 ID를 각각 인코딩하는 x-m 및 x-t 매개 변수</span><span class="sxs-lookup"><span data-stu-id="47424-295">x-m and x-t parameters encoding the full transfer target MRI and tenant ID respectively</span></span> 

<span data-ttu-id="47424-296">REFERRED-BY 헤더는 다음 표와 같이 전송자 테넌트 ID 및 기타 전송 컨텍스트 매개 변수뿐만 아니라 전송자 MRI로 인코딩된 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="47424-296">The REFERRED-BY header is a SIP URI with transferor MRI encoded in it as well as transferor tenant ID and other transfer context parameters as shown in the following table:</span></span>

| <span data-ttu-id="47424-297">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47424-297">Parameter</span></span> | <span data-ttu-id="47424-298">값</span><span class="sxs-lookup"><span data-stu-id="47424-298">Value</span></span> | <span data-ttu-id="47424-299">설명</span><span class="sxs-lookup"><span data-stu-id="47424-299">Description</span></span> |  
|:---------------------  |:---------------------- |:---------------------- |
| <span data-ttu-id="47424-300">x-m</span><span class="sxs-lookup"><span data-stu-id="47424-300">x-m</span></span> | <span data-ttu-id="47424-301">MRI</span><span class="sxs-lookup"><span data-stu-id="47424-301">MRI</span></span> | <span data-ttu-id="47424-302">CC에 의해 채워진 전송기/전송 대상의 전체 MRI</span><span class="sxs-lookup"><span data-stu-id="47424-302">Full MRI of transferor/transfer target as populated by CC</span></span> |
| <span data-ttu-id="47424-303">x-t</span><span class="sxs-lookup"><span data-stu-id="47424-303">x-t</span></span> | <span data-ttu-id="47424-304">테넌트 ID</span><span class="sxs-lookup"><span data-stu-id="47424-304">Tenant ID</span></span> | <span data-ttu-id="47424-305">CC로 채워진 x-t 테넌트 ID 선택적 테넌트 ID</span><span class="sxs-lookup"><span data-stu-id="47424-305">x-t Tenant ID Optional Tenant Id as populated by CC</span></span> |
| <span data-ttu-id="47424-306">x-ti</span><span class="sxs-lookup"><span data-stu-id="47424-306">x-ti</span></span> | <span data-ttu-id="47424-307">전송자 상관 관계 ID</span><span class="sxs-lookup"><span data-stu-id="47424-307">Transferor Correlation Id</span></span> | <span data-ttu-id="47424-308">전송자에 대한 호출의 상관 관계 ID</span><span class="sxs-lookup"><span data-stu-id="47424-308">Correlation Id of the call to the transferor</span></span> |
| <span data-ttu-id="47424-309">x-tt</span><span class="sxs-lookup"><span data-stu-id="47424-309">x-tt</span></span> | <span data-ttu-id="47424-310">전송 대상 호출 URI</span><span class="sxs-lookup"><span data-stu-id="47424-310">Transfer target call URI</span></span> | <span data-ttu-id="47424-311">인코딩된 호출 대체 URI</span><span class="sxs-lookup"><span data-stu-id="47424-311">Encoded call replacement URI</span></span> |

<span data-ttu-id="47424-312">이 경우 참조 헤더의 크기는 최대 400개 기호일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-312">The size of the Refer Header can be up to 400 symbols in this case.</span></span> <span data-ttu-id="47424-313">SBC는 최대 400개 기호 크기의 참조 메시지 처리를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-313">The SBC must support handling Refer messages with size up to 400 symbols.</span></span>

![여러 엔드포인트에 프로비전 응답이 울리는 다이어그램](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a><span data-ttu-id="47424-315">세션 timer</span><span class="sxs-lookup"><span data-stu-id="47424-315">Session timer</span></span>

<span data-ttu-id="47424-316">SIP 프록시는 비 우회 호출에서 세션 Timer를 지원(항상 제공)하지만 우회 호출에서는 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-316">The SIP proxy supports (always offers) the Session Timer on non-bypass calls but does not offer it on bypass calls.</span></span> <span data-ttu-id="47424-317">SBC에서 세션 Timer를 사용하는 것은 필수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="47424-317">Use of the Session Timer by the SBC is not mandatory.</span></span>

##  <a name="use-of-request-uri-parameter-userphone"></a><span data-ttu-id="47424-318">Request-URI 매개 변수 user=phone 사용</span><span class="sxs-lookup"><span data-stu-id="47424-318">Use of Request-URI parameter user=phone</span></span>

<span data-ttu-id="47424-319">SIP 프록시는 Request-URI를 분석하고 매개 변수 user=phone이 있는 경우 서비스는 요청-URI를 전화 번호로 처리하여 사용자에 대한 번호와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-319">The SIP proxy analyses the Request-URI and if the parameter user=phone is present, the service will handle the Request-URI as a phone number, matching the number to a user.</span></span> <span data-ttu-id="47424-320">매개 변수가 없는 경우 SIP 프록시는 요청-URI 사용자 유형(전화 번호 또는 SIP 주소)을 결정하기 위해추론을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-320">If parameter is not present the SIP proxy applies heuristics to determine  the Request-URI user type (phone number or a SIP address).</span></span>

<span data-ttu-id="47424-321">Microsof는 호출 설정 프로세스를 간소화하기 위해 항상 user=phone 매개 변수를 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-321">Microsof recommends always applying the user=phone parameter to simplify the call setup process.</span></span>

## <a name="history-info-header"></a><span data-ttu-id="47424-322">History-Info 헤더</span><span class="sxs-lookup"><span data-stu-id="47424-322">History-Info header</span></span>

<span data-ttu-id="47424-323">History-Info 헤더는 SIP 요청을 다시 설정하고 "네트워크 및 최종 사용자에 대해 다양한 서비스를 사용할 수 있도록 요청 기록 정보를 캡처하기 위한 표준 메커니즘을 제공합니다."에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-323">The History-Info header is used for retargeting SIP requests and “provide(s) a standard mechanism for capturing the request history information to enable a wide variety of services for networks and end-users.”</span></span> <span data-ttu-id="47424-324">자세한 내용은 [RFC 4244 – 섹션 1.1을 참조하세요.](http://www.ietf.org/rfc/rfc4244.txt)</span><span class="sxs-lookup"><span data-stu-id="47424-324">For more information, see [RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt).</span></span> <span data-ttu-id="47424-325">Microsoft Phone System의 경우 이 헤더는 단순화 및 통화 전달 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-325">For Microsoft Phone System, this header is used in Simulring and Call Forwarding scenarios.</span></span>  

<span data-ttu-id="47424-326">전송하는 경우 History-Info 다음과 같이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-326">If sending, the History-Info is enabled as follows:</span></span>

- <span data-ttu-id="47424-327">SIP 프록시는 PSTN 컨트롤러로 전송된 History-Info 헤더를 구성하는 개별 History-Info 전화 번호가 포함된 매개 변수를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-327">The SIP proxy will insert a parameter containing the associated phone number in individual History-Info entries that comprise the History-Info header sent to the PSTN Controller.</span></span>  <span data-ttu-id="47424-328">전화 번호 매개 변수가 있는 항목만 사용하여 PSTN 컨트롤러는 새 History-Info 헤더를 다시 작성하고 SIP 프록시를 통해 SIP 트렁크 공급자에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-328">Using only entries that have the phone number parameter, the PSTN Controller will rebuild a new History-Info header, and pass it on to the SIP trunk provider via SIP proxy.</span></span>

- <span data-ttu-id="47424-329">History-Info 헤더가 동시 링 및 통화 전달 사례에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-329">History-Info header will be added for simultaneous ring and call forwarding cases.</span></span>

- <span data-ttu-id="47424-330">History-Info 헤더는 통화 전송 사례에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-330">History-Info header will not be added for call transfer cases.</span></span>

- <span data-ttu-id="47424-331">재구성된 History-Info 헤더의 개별 기록 항목에는 URI의 호스트 부분으로 설정된 직접 라우팅 FQDN(sip.pstnhub.microsoft.com)과 결합된 전화 번호 매개 변수가 있습니다. 'user=phone'의 매개 변수가 SIP URI의 일부로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-331">An individual history entry in the reconstructed History-Info header will have the phone number parameter provided combined with the Direct Routing FQDN (sip.pstnhub.microsoft.com) set as the host part of the URI; a parameter of ‘user=phone’ will be added as part of the SIP URI.</span></span>  <span data-ttu-id="47424-332">전화 컨텍스트 매개 변수를 제외한 원래 History-Info 헤더와 연결된 다른 모든 매개 변수는 다시 생성된 History-Info 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-332">Any other parameters associated with the original History-Info header, except for phone context parameters, will be passed through in the re-constructed History-Info header.</span></span>  <span data-ttu-id="47424-333">개인 항목(RFC 4244의 섹션 3.3에 정의된 메커니즘에 따라 결정)은 SIP 트렁크 공급자가 신뢰할 수 있는 피어이기 때문에 다음과 같이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-333">Note that entries that are private (as determined by the mechanisms defined in Section 3.3 of RFC 4244) will be forwarded as is because  the SIP trunk provider is a trusted peer.</span></span>

- <span data-ttu-id="47424-334">인바운드 History-Info 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-334">Inbound History-Info is ignored.</span></span>

<span data-ttu-id="47424-335">다음은 SIP 프록시에서 보낸 기록 정보 헤더의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="47424-335">Following is the format of the History-info header sent by the SIP proxy:</span></span>

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

<span data-ttu-id="47424-336">호출이 여러 번 리디렉션된 경우 모든 리디렉션에 대한 정보가 시간 순서대로 적절한 이유에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-336">If the call was redirected several times, information about every redirect is included with the appropriate reason in chronological order.</span></span>


<span data-ttu-id="47424-337">헤더 예제:</span><span class="sxs-lookup"><span data-stu-id="47424-337">Header Example:</span></span>

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

<span data-ttu-id="47424-338">이 History-Info TLS 메커니즘으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-338">The History-Info is protected by a mandatory TLS mechanism.</span></span> 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a><span data-ttu-id="47424-339">직접 라우팅 및 장애 조치 메커니즘에 대한 SBC 연결</span><span class="sxs-lookup"><span data-stu-id="47424-339">SBC connection to Direct Routing and failover mechanism</span></span>

<span data-ttu-id="47424-340">직접 라우팅 계획의 SIP 신호에 대한 장애 [조치(failover) 메커니즘 섹션을 참조하세요.](direct-routing-plan.md#failover-mechanism-for-sip-signaling)</span><span class="sxs-lookup"><span data-stu-id="47424-340">See the section Failover mechanism for SIP signaling in [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).</span></span>

## <a name="retry-after"></a><span data-ttu-id="47424-341">Retry-After</span><span class="sxs-lookup"><span data-stu-id="47424-341">Retry-After</span></span>

<span data-ttu-id="47424-342">직접 라우팅 데이터 센터를 사용 중이면 서비스는 1초 간격으로 Retry-After 메시지를 SBC에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-342">If a Direct Routing datacenter is busy, the service can send a Retry-After message with a one-second interval to the SBC.</span></span> <span data-ttu-id="47424-343">SBC가 INVITE에 대한 응답으로 Retry-After 헤더가 있는 503 메시지를 받으면 SBC는 해당 연결을 종료하고 사용 가능한 다음 Microsoft 데이터 센터를 시도해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-343">When the SBC receives a 503 message with a Retry-After header in response to an INVITE, the SBC must terminate that connection and try the next available Microsoft datacenter.</span></span> 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a><span data-ttu-id="47424-344">ICE 다시 시작: 미디어 우회를 지원하지 않는 엔드포인트로 전송된 미디어 우회 호출</span><span class="sxs-lookup"><span data-stu-id="47424-344">ICE Restart: Media bypass call transferred to an endpoint that does not support media bypass</span></span>

<span data-ttu-id="47424-345">SBC는 [RFC 5245, 섹션 9.1.1.1에](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)설명된 바와 같이 ICE 다시 시작을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-345">The SBC must support ICE restarts as described in [RFC 5245, section 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span>

<span data-ttu-id="47424-346">직접 라우팅에서 다시 시작은 RFC의 다음 단락에 따라 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="47424-346">The restart in Direct Routing is implemented according to the following paragraphs of the RFC:</span></span>

<span data-ttu-id="47424-347">*ICE를 다시 시작하려면 에이전트가 제품에서 미디어 스트림에 대한 ice-pwd와 ice-ufrag를 모두 변경해야 합니다.  한 제안에서 세션 수준 특성을 사용할 수 있지만 후속 제안에서 동일한 ice-pwd 또는 ice-ufrag를 미디어 수준 특성으로 제공할 수 있습니다.  이는 암호의 변경이 아니며 표현의 변경일 뿐만 아니라 ICE가 다시 시작되지는 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="47424-347">*To restart ICE, an agent MUST change both the ice-pwd and the ice-ufrag for the media stream in an offer.  Note that it is permissible to use a session-level attribute in one offer, but to provide the same ice-pwd or ice-ufrag as a media-level attribute in a subsequent offer.  This is not a change in password, just a change in its representation, and does not cause an ICE restart.*</span></span>

<span data-ttu-id="47424-348">*에이전트는 이 미디어 스트림의 초기 제안과 같은 이 미디어 스트림에 대한 SDP의 나머지 필드를 설정합니다(섹션 4.3 참조).  따라서 후보 집합에는 해당 스트림에 대한 일부, 없음 또는 모든 이전 후보가 포함될 수 있으며 섹션 4.1.1에 설명된 바와 같이 수집된 완전히 새로운 후보 집합을 포함할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="47424-348">*An agent sets the rest of the fields in the SDP for this media stream as it would in an initial offer of this media stream (see Section 4.3).  Consequently, the set of candidates MAY include some, none, or all of the previous candidates for that stream and MAY include a totally new set of candidates gathered as described in Section 4.1.1.*</span></span>

<span data-ttu-id="47424-349">처음에 미디어 우회를 사용하여 통화를 설정하고 비즈니스용 Skype 클라이언트로 통화를 전송하는 경우 직접 라우팅은 미디어 프로세서를 삽입해야 합니다. 직접 라우팅은 미디어 우회가 있는 비즈니스용 Skype 클라이언트와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47424-349">If the call was initially established with media bypass, and the call is transferred to a Skype for Business client, Direct Routing needs to insert a Media Processor--this is because Direct Routing cannot be used with a Skype for Business client with media bypass.</span></span> <span data-ttu-id="47424-350">직접 라우팅은 ice-pwd 및 ice-ufrag를 변경하고 새로운 미디어 후보를 다시 제안하여 ICE 다시 시작 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="47424-350">Direct Routing starts the ICE restart process by  changing the ice-pwd and ice-ufrag and offering new media candidates in a reinvite.</span></span> 


