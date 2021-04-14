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
ms.openlocfilehash: 8b1917408fa14ced9a490cba1559228dde924cfc
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697783"
---
# <a name="direct-routing---sip-protocol"></a><span data-ttu-id="0b61b-103">직접 라우팅 - SIP 프로토콜</span><span class="sxs-lookup"><span data-stu-id="0b61b-103">Direct Routing - SIP protocol</span></span>

<span data-ttu-id="0b61b-104">이 문서에서는 직접 라우팅이 SIP(세션 시작 프로토콜)를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-104">This article describes how Direct Routing implements the Session Initiation Protocol (SIP).</span></span> <span data-ttu-id="0b61b-105">SBC(세션 테두리 컨트롤러)와 SIP 프록시 간에 트래픽을 올바르게 라우팅하려면 일부 SIP 매개 변수에 특정 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-105">To properly route traffic between a Session Border Controller (SBC) and the SIP proxy, some SIP parameters must have specific values.</span></span> <span data-ttu-id="0b61b-106">이 문서는 프레미스 SBC와 SIP 프록시 서비스 간의 연결을 구성할 책임이 있는 음성 관리자를 위한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-106">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a><span data-ttu-id="0b61b-107">들어오는 요청 처리: 테넌트 및 사용자 찾기</span><span class="sxs-lookup"><span data-stu-id="0b61b-107">Processing the incoming request: finding the tenant and user</span></span>

<span data-ttu-id="0b61b-108">수신 또는 아웃바운드 호출을 처리하기 전에 옵션 메시지는 SIP 프록시와 SBC 간에 교환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-108">Before an incoming or outbound call can be processed, OPTIONS messages are exchanged between SIP Proxy and the SBC.</span></span> <span data-ttu-id="0b61b-109">이러한 옵션 메시지를 통해 SIP 프록시는 SBC에 허용된 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-109">These OPTIONS messages allow SIP Proxy to provide the allowed capabilities to SBC.</span></span> <span data-ttu-id="0b61b-110">옵션 협상이 성공해야 합니다(200OK 응답), 호출을 설정하기 위해 SBC와 SIP 프록시 간의 추가 통신을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-110">It is important for OPTIONS negotiation to be successful (200OK response), allowing for further communication between SBC and SIP Proxy for establishing calls.</span></span> <span data-ttu-id="0b61b-111">SIP 프록시에 대한 OPTIONS 메시지의 SIP 헤더는 아래 예제로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-111">The SIP headers in an OPTIONS messages to SIP Proxy are provided as an example below:</span></span>

| <span data-ttu-id="0b61b-112">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="0b61b-112">Parameter name</span></span> | <span data-ttu-id="0b61b-113">값의 예</span><span class="sxs-lookup"><span data-stu-id="0b61b-113">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="0b61b-114">Request-URI</span><span class="sxs-lookup"><span data-stu-id="0b61b-114">Request-URI</span></span> | <span data-ttu-id="0b61b-115">OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="0b61b-115">OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0</span></span> |
| <span data-ttu-id="0b61b-116">헤더를 통해</span><span class="sxs-lookup"><span data-stu-id="0b61b-116">Via Header</span></span> | <span data-ttu-id="0b61b-117">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="0b61b-117">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="0b61b-118">Max-Forwards 헤더</span><span class="sxs-lookup"><span data-stu-id="0b61b-118">Max-Forwards header</span></span> | <span data-ttu-id="0b61b-119">Max-Forwards:68</span><span class="sxs-lookup"><span data-stu-id="0b61b-119">Max-Forwards:68</span></span> |
| <span data-ttu-id="0b61b-120">헤더에서</span><span class="sxs-lookup"><span data-stu-id="0b61b-120">From Header</span></span> | <span data-ttu-id="0b61b-121">헤더에서: <sip:sbc1.adatum.biz:5058></span><span class="sxs-lookup"><span data-stu-id="0b61b-121">From Header From: <sip:sbc1.adatum.biz:5058></span></span> |
| <span data-ttu-id="0b61b-122">헤더로</span><span class="sxs-lookup"><span data-stu-id="0b61b-122">To Header</span></span> | <span data-ttu-id="0b61b-123">받는 사람: <sip:sip.pstnhub.microsoft.com:5061></span><span class="sxs-lookup"><span data-stu-id="0b61b-123">To: <sip:sip.pstnhub.microsoft.com:5061></span></span> |
| <span data-ttu-id="0b61b-124">CSeq 헤더</span><span class="sxs-lookup"><span data-stu-id="0b61b-124">CSeq header</span></span> | <span data-ttu-id="0b61b-125">CSeq: 1 INVITE</span><span class="sxs-lookup"><span data-stu-id="0b61b-125">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="0b61b-126">헤더에 문의</span><span class="sxs-lookup"><span data-stu-id="0b61b-126">Contact Header</span></span> | <span data-ttu-id="0b61b-127">연락처: <sip:sbc1.adatum.biz:50588;transport=tls></span><span class="sxs-lookup"><span data-stu-id="0b61b-127">Contact: <sip:sbc1.adatum.biz:50588;transport=tls></span></span> |

> [!NOTE]
> <span data-ttu-id="0b61b-128">SIP 헤더에는 사용 중인 SIP URI에 userinfo가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-128">The SIP headers do not contain userinfo in the SIP URI in use.</span></span> <span data-ttu-id="0b61b-129">[RFC 3261, 섹션 19.1.1에](https://tools.ietf.org/html/rfc3261#section-19.1.1)따라 URI의 userinfo 부분은 선택 사항이며 대상 호스트에 사용자에 대한 생각이 없는 경우 또는 호스트 자체가 식별되는 리소스인 경우 부재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-129">As per [RFC 3261, section 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1), the userinfo part of a URI is optional and MAY be absent when the destination host does not have a notion of users or when the hosst itself is the resource being identified.</span></span> <span data-ttu-id="0b61b-130">@ 기호가 SIP URI에 있는 경우 사용자 필드가 비어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-130">If the @ sign is present in a SIP URI, the user field MUST NOT be empty.</span></span>

<span data-ttu-id="0b61b-131">들어오는 호출에서 SIP 프록시는 호출이 예정된 테넌트를 찾고 이 테넌트 내에서 특정 사용자를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-131">On an incoming call, the SIP proxy needs to find the tenant to which the call is destined and find the specific user within this tenant.</span></span> <span data-ttu-id="0b61b-132">테넌트 관리자는 여러 테넌트에서 비 DID 번호(예: +1001)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-132">The tenant administrator might configure non-DID numbers, for example +1001, in multiple tenants.</span></span> <span data-ttu-id="0b61b-133">따라서 비 DID 번호가 여러 Microsoft 365 또는 Office 365 조직에서 동일할 수 있으므로 숫자 검색을 수행할 특정 테넌트를 찾는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-133">Therefore, it is important to find the specific tenant on which to perform the number lookup because the non-DID numbers might be the same in multiple Microsoft 365 or Office 365 organizations.</span></span>  

<span data-ttu-id="0b61b-134">이 섹션에서는 SIP 프록시가 테넌트와 사용자를 찾고 들어오는 연결에서 SBC의 인증을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-134">This section describes how the SIP proxy finds the tenant and the user, and performs authentication of the SBC on the incoming connection.</span></span>

<span data-ttu-id="0b61b-135">다음은 들어오는 호출의 SIP 초대 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-135">The following is an example of the SIP Invite message on an incoming call:</span></span>

| <span data-ttu-id="0b61b-136">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="0b61b-136">Parameter name</span></span> | <span data-ttu-id="0b61b-137">값의 예</span><span class="sxs-lookup"><span data-stu-id="0b61b-137">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="0b61b-138">Request-URI</span><span class="sxs-lookup"><span data-stu-id="0b61b-138">Request-URI</span></span> | <span data-ttu-id="0b61b-139">INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="0b61b-139">INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span></span> |
| <span data-ttu-id="0b61b-140">헤더를 통해</span><span class="sxs-lookup"><span data-stu-id="0b61b-140">Via Header</span></span> | <span data-ttu-id="0b61b-141">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="0b61b-141">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="0b61b-142">Max-Forwards 헤더</span><span class="sxs-lookup"><span data-stu-id="0b61b-142">Max-Forwards header</span></span> | <span data-ttu-id="0b61b-143">Max-Forwards:68</span><span class="sxs-lookup"><span data-stu-id="0b61b-143">Max-Forwards:68</span></span> |
| <span data-ttu-id="0b61b-144">헤더에서</span><span class="sxs-lookup"><span data-stu-id="0b61b-144">From Header</span></span> | <span data-ttu-id="0b61b-145">헤더에서: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span><span class="sxs-lookup"><span data-stu-id="0b61b-145">From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span></span> |
| <span data-ttu-id="0b61b-146">헤더로</span><span class="sxs-lookup"><span data-stu-id="0b61b-146">To Header</span></span> | <span data-ttu-id="0b61b-147">to: sip:+183338006777@sbc1.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0b61b-147">To: sip:+183338006777@sbc1.adatum.biz</span></span> | 
| <span data-ttu-id="0b61b-148">CSeq 헤더</span><span class="sxs-lookup"><span data-stu-id="0b61b-148">CSeq header</span></span> | <span data-ttu-id="0b61b-149">CSeq: 1 INVITE</span><span class="sxs-lookup"><span data-stu-id="0b61b-149">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="0b61b-150">헤더에 문의</span><span class="sxs-lookup"><span data-stu-id="0b61b-150">Contact Header</span></span> | <span data-ttu-id="0b61b-151">연락처: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls></span><span class="sxs-lookup"><span data-stu-id="0b61b-151">Contact: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls></span></span> | 

<span data-ttu-id="0b61b-152">초대를 받을 때 SIP 프록시는 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-152">On receiving the invite, the SIP proxy performs the following steps:</span></span>

1. <span data-ttu-id="0b61b-153">인증서를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-153">Check the certificate.</span></span> <span data-ttu-id="0b61b-154">초기 연결에서 직접 라우팅 서비스는 연락처 헤더에 제시된 FQDN 이름을 사용하여 제시된 인증서의 일반 이름 또는 주체 대체 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-154">On the initial connection, the Direct Routing service takes the FQDN name presented in the Contact header and matches it to the Common Name or Subject Alternative name of the presented certificate.</span></span> <span data-ttu-id="0b61b-155">SBC 이름은 다음 옵션 중 하나와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-155">The SBC name must match one of the following options:</span></span>

   - <span data-ttu-id="0b61b-156">옵션 1.</span><span class="sxs-lookup"><span data-stu-id="0b61b-156">Option 1.</span></span> <span data-ttu-id="0b61b-157">연락처 헤더에 제시된 전체 FQDN 이름은 제시된 인증서의 일반 이름/주체 대체 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-157">The full FQDN name presented in the Contact header must match the Common Name/Subject Alternative name of the presented certificate.</span></span>  

   - <span data-ttu-id="0b61b-158">옵션 2.</span><span class="sxs-lookup"><span data-stu-id="0b61b-158">Option 2.</span></span> <span data-ttu-id="0b61b-159">연락처 헤더에 제시된 FQDN 이름의 도메인 부분(예: FQDN adatum.biz 이름의 sbc1.adatum.biz)은 일반 이름/주체 대체 이름(예: \*.adatum.biz)의 와일드카드 값과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-159">The domain portion of the FQDN name presented in the Contact header (for example adatum.biz of the FQDN name sbc1.adatum.biz) must match the wildcard value in Common Name/Subject Alternative Name (for example \*.adatum.biz).</span></span>

2. <span data-ttu-id="0b61b-160">연락처 헤더에 제시된 전체 FQDN 이름을 사용하여 테넌트를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-160">Try to find a tenant using the full FQDN name presented in the Contact header.</span></span>  

   <span data-ttu-id="0b61b-161">연락처 헤더(sbc1.adatum.biz)의 FQDN 이름이 Microsoft 365 또는 Office 365 조직에서 DNS 이름으로 등록되어 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-161">Check if the FQDN name from the Contact header (sbc1.adatum.biz) is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="0b61b-162">발견된 경우 사용자의 검색은 SBC FQDN이 도메인 이름으로 등록된 테넌트에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-162">If found, the lookup of the user is performed in the tenant that has the SBC FQDN registered as a Domain name.</span></span> <span data-ttu-id="0b61b-163">찾을 수 없는 경우 3단계가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-163">If not found, Step 3 applies.</span></span>   

3. <span data-ttu-id="0b61b-164">3단계는 2단계가 실패한 경우만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-164">Step 3 only applies if Step 2 failed.</span></span> 

   <span data-ttu-id="0b61b-165">호스트 부분을 제거한 후 FQDN(FQDN: sbc12.adatum.biz adatum.biz)에 있는 호스트 부분을 제거하고, 이 이름이 Microsoft 365 또는 Office 365 조직에서 DNS 이름으로 등록되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-165">Remove the host portion from the FQDN, presented in the Contact header (FQDN: sbc12.adatum.biz, after removing the host portion: adatum.biz), and check if this name is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="0b61b-166">찾은 경우 이 테넌트에서 사용자 보기가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-166">If found, the user lookup is performed in this tenant.</span></span> <span data-ttu-id="0b61b-167">찾을 수 없는 경우 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-167">If not found, the call fails.</span></span>

4. <span data-ttu-id="0b61b-168">Request-URI에 제공된 전화 번호를 사용하여 2단계 또는 3단계에 있는 테넌트 내에서 역 번호 보기를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-168">Using the phone number presented in the Request-URI, perform the reverse number lookup within the tenant found in Step 2 or 3.</span></span> <span data-ttu-id="0b61b-169">이전 단계에서 발견된 테넌트 내의 사용자 SIP URI에 제시된 전화 번호를 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-169">Match the presented phone number to a user SIP URI within the tenant found on the previous step.</span></span>

5. <span data-ttu-id="0b61b-170">트렁크 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-170">Apply trunk settings.</span></span> <span data-ttu-id="0b61b-171">이 SBC에 대한 테넌트 관리자가 설정한 매개 변수를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-171">Find the parameters set by the tenant admin for this SBC.</span></span>

   <span data-ttu-id="0b61b-172">Microsoft는 Microsoft SIP 프록시와 페어링된 SBC 간에 타사 SIP 프록시 또는 사용자 에이전트 서버가 있는 경우를 지원하지 않습니다. 이는 쌍을 이루는 SBC에서 만든 요청 URI를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-172">Microsoft does not support having a third-party SIP proxy or User Agent Server between the Microsoft SIP proxy and the paired SBC, which might modify the Request URI created by the paired SBC.</span></span>

   <span data-ttu-id="0b61b-173">한 SBC가 여러 테넌트(통신사 시나리오)에 상호 연결되는 시나리오에 필요한 두 가지 보기(2단계 및 3단계)에 대한 요구 사항은 이 문서의 나중에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-173">The requirements for the two lookups (steps 2 and 3) needed for the scenario where one SBC is interconnected to many tenants (carrier scenario) are covered later in this article.</span></span>

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a><span data-ttu-id="0b61b-174">연락처 헤더 및 Request-URI에 대한 자세한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b61b-174">Detailed requirements for Contact header and Request-URI</span></span>

#### <a name="contact-header"></a><span data-ttu-id="0b61b-175">연락처 헤더</span><span class="sxs-lookup"><span data-stu-id="0b61b-175">Contact header</span></span>

<span data-ttu-id="0b61b-176">Microsoft SIP 프록시에 들어오는 모든 SIP 메시지(OPTIONS, INVITE)의 경우 연락처 헤더에 다음과 같이 URI 호스트 이름에 쌍이 있는 SBC FQDN이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-176">For all incoming SIP messages (OPTIONS, INVITE) to the Microsoft SIP proxy, the Contact header must have the paired SBC FQDN in the URI hostname as follows:</span></span>

<span data-ttu-id="0b61b-177">구문: 연락처: <sip:phone 또는 sip address@FQDN SBC;transport=tls></span><span class="sxs-lookup"><span data-stu-id="0b61b-177">Syntax: Contact:  <sip:phone or sip address@FQDN of the SBC;transport=tls></span></span> 

<span data-ttu-id="0b61b-178">[RFC 3261, 섹션 11.1에](https://tools.ietf.org/html/rfc3261#section-11.1)따라 옵션 메시지에 연락처 헤더 필드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-178">As per [RFC 3261, section 11.1](https://tools.ietf.org/html/rfc3261#section-11.1), a Contact header field MAY be present in an OPTIONS message.</span></span> <span data-ttu-id="0b61b-179">직접 라우팅에서 연락처 헤더가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-179">In Direct Routing the contact header is required.</span></span> <span data-ttu-id="0b61b-180">위의 형식의 INVITE 메시지의 경우 옵션 메시지의 경우 SIP URI에서 userinfo를 제거할 수 있으며 다음과 같이 FQDN 형식으로만 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-180">For INVITE messages in format above, for OPTIONS messages the userinfo can be removed from SIP URI and only FQDN sent in format as follows:</span></span>

<span data-ttu-id="0b61b-181">구문: 연락처: <sip:FQDN의 SBC;transport=tls></span><span class="sxs-lookup"><span data-stu-id="0b61b-181">Syntax: Contact:  <sip:FQDN of the SBC;transport=tls></span></span>

<span data-ttu-id="0b61b-182">이 이름(FQDN)은 제시된 인증서의 공통 이름 또는 주체 대체 이름 필드에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-182">This name (FQDN) must also be in the Common Name or Subject Alternative name field(s) of the presented certificate.</span></span> <span data-ttu-id="0b61b-183">Microsoft는 인증서의 일반 이름 또는 주체 대체 이름 필드에서 이름의 와일드카드 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-183">Microsoft supports using wildcard values of the name(s) in the Common Name or Subject Alternative Name fields of the certificate.</span></span>   

<span data-ttu-id="0b61b-184">와일드카드에 대한 지원은 [RFC 2818, 섹션 3.1에 설명되어 있습니다.](https://tools.ietf.org/html/rfc2818#section-3.1)</span><span class="sxs-lookup"><span data-stu-id="0b61b-184">The support for wildcards is described in [RFC 2818, section 3.1](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="0b61b-185">특히:</span><span class="sxs-lookup"><span data-stu-id="0b61b-185">Specifically:</span></span>

<span data-ttu-id="0b61b-186">*"이름에는 단일 도메인 이름 구성 요소 또는 구성 요소 조각과 일치하는 것으로 간주되는 와일드카드 \* 문자가 포함될 수 있습니다. 예: .a.com 일치하지만 foo.a.com \* bar.foo.a.com. f .com은 foo.com 일치하지만 \* bar.com."*</span><span class="sxs-lookup"><span data-stu-id="0b61b-186">*"Names may contain the wildcard character \* which is considered to match any single domain name component or component fragment. E.g., \*.a.com matches foo.a.com but not bar.foo.a.com. f\*.com matches foo.com but not bar.com."*</span></span>

<span data-ttu-id="0b61b-187">SIP 메시지에 있는 연락처 헤더에 두 개 이상의 값이 SBC에서 전송되는 경우 연락처 헤더의 첫 번째 값의 FQDN 부분만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-187">If more than one value in the Contact header presented in a SIP message is sent by the SBC, only the FQDN portion of the first value of the Contact header is used.</span></span>

<span data-ttu-id="0b61b-188">직접 라우팅의 경우 원칙적으로 FQDN을 사용하여 IP 대신 SIP URI를 채우는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-188">As rule of thumb for Direct Routing, it is important that FQDN is used to populate SIP URI instead of IP.</span></span> <span data-ttu-id="0b61b-189">호스트 이름을 FQDN이 아닌 IP로 표시하는 연락처 헤더를 사용하여 SIP 프록시에 들어오는 INVITE 또는 OPTIONS 메시지는 403 금지된 연결로 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-189">An incoming INVITE or OPTIONS message to SIP Proxy with Contact header where hostname is represented by IP and not FQDN, the connection will be refused with 403 Forbidden.</span></span>

#### <a name="request-uri"></a><span data-ttu-id="0b61b-190">Request-URI</span><span class="sxs-lookup"><span data-stu-id="0b61b-190">Request-URI</span></span> 

<span data-ttu-id="0b61b-191">들어오는 모든 호출의 경우 Request-URI를 사용하여 전화 번호를 사용자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-191">For all incoming calls, the Request-URI is used to match the phone number to a user.</span></span>   

<span data-ttu-id="0b61b-192">현재 전화 번호는 다음 예제와 같이 더하기 기호(+)를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-192">Currently The phone number must contain a plus sign (+) as shown in the following example.</span></span> 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a><span data-ttu-id="0b61b-193">연락처 및 Record-Route 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0b61b-193">Contact and Record-Route headers considerations</span></span>

<span data-ttu-id="0b61b-194">SIP 프록시는 새 대화 상자 클라이언트 트랜잭션(예: Bye 또는 다시 초대) 및 SIP 옵션에 회신할 때 다음 홉 FQDN을 계산해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-194">The SIP proxy needs to calculate the next hop FQDN for new in-dialog client transactions (for example Bye or Re-Invite), and when replying to SIP Options.</span></span> <span data-ttu-id="0b61b-195">연락처 또는 Record-Route 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-195">Either Contact or Record-Route are used.</span></span> 

<span data-ttu-id="0b61b-196">[RFC 3261, 섹션 8.1.1.8에](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)따라 연락처 헤더는 새 대화 상자가 될 수 있는 모든 요청에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-196">According to [RFC 3261, section 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8), Contact header is required in any request that can result in a new dialog.</span></span> <span data-ttu-id="0b61b-197">Record-Route 프록시가 대화 상자에서 향후 요청 경로에 유지하려는 경우만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-197">The Record-Route is only required if a proxy wants to stay on the path of future requests in a dialog.</span></span> <span data-ttu-id="0b61b-198">프록시 SBC가 직접 라우팅에 대한 [로컬 미디어](./direct-routing-media-optimization.md)최적화와 함께 사용 중이면 프록시 SBC가 경로에 유지해야 하여 레코드 경로를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-198">If a proxy SBC is in use with [Local Media Optimization for Direct Routing](./direct-routing-media-optimization.md), a record route will need to be configured as the proxy SBC needs to stay in the route.</span></span> 

<span data-ttu-id="0b61b-199">프록시 SBC를 사용하지 않는 경우 연락처 헤더만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-199">Microsoft recommends using only Contact header if a proxy SBC is not used:</span></span>

- <span data-ttu-id="0b61b-200">[RFC 3261, 섹션 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route 프록시가 대화 상자의 향후 요청 경로를 유지하려는 경우 사용됩니다. 모든 트래픽이 Microsoft SIP 프록시와 페어링된 SBC 간에 진행될 때 프록시 SBC가 구성되지 않는 경우 필수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-200">Per [RFC 3261, section 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route is used if a proxy wants to stay on the path of future requests in a dialog, which is not essential if no proxy SBC is configured as all traffic goes between the Microsoft SIP proxy and the paired SBC.</span></span> 

- <span data-ttu-id="0b61b-201">Microsoft SIP 프록시는 아웃바운드 ping 옵션을 보낼 때 다음 홉을 결정하기 위해 연락처 헤더(레코드-경로 아 아닌)만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-201">The Microsoft SIP proxy uses only Contact header (not Record-Route) to determine the next hop when sending outbound ping Options.</span></span> <span data-ttu-id="0b61b-202">프록시 SBC를 사용하지 않는 경우 두 매개 변수(연락처 및 레코드 경로)가 아닌 하나의 매개 변수(연락처)를 구성하면 관리가 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-202">Configuring only one parameter (Contact) instead of two (Contact and Record-Route) simplifies the administration if a proxy SBC is not in use.</span></span> 

<span data-ttu-id="0b61b-203">다음 홉을 계산하기 위해 SIP 프록시는 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-203">To calculate the next hop, the SIP proxy uses:</span></span>

- <span data-ttu-id="0b61b-204">우선 순위 1.</span><span class="sxs-lookup"><span data-stu-id="0b61b-204">Priority 1.</span></span> <span data-ttu-id="0b61b-205">최상위 레코드 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-205">Top-level Record-Route.</span></span> <span data-ttu-id="0b61b-206">최상위 수준 Record-Route FQDN 이름이 포함된 경우 FQDN 이름은 아웃바운드 대화 상자 연결을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-206">If the top-level Record-Route contains the FQDN name, the FQDN name is used to make the outbound in-dialog connection.</span></span>

- <span data-ttu-id="0b61b-207">우선 순위 2.</span><span class="sxs-lookup"><span data-stu-id="0b61b-207">Priority 2.</span></span> <span data-ttu-id="0b61b-208">연락처 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-208">Contact header.</span></span> <span data-ttu-id="0b61b-209">Record-Route 없는 경우 SIP 프록시는 연락처 헤더 값을 찾아 아웃바운드 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-209">If Record-Route does not exist, the SIP proxy will look up the value of the Contact header to make the outbound connection.</span></span> <span data-ttu-id="0b61b-210">(권장되는 구성입니다.)</span><span class="sxs-lookup"><span data-stu-id="0b61b-210">(This is the recommended configuration.)</span></span>

<span data-ttu-id="0b61b-211">연락처 및 Record-Route 모두 사용하는 경우 SBC 관리자는 해당 값을 동일하게 유지해야 하여 관리 오버헤드가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-211">If both Contact and Record-Route are used, the SBC administrator must keep their values identical, which causes administrative overhead.</span></span> 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a><span data-ttu-id="0b61b-212">연락처 또는 연락처에서 FQDN 이름을 Record-Route</span><span class="sxs-lookup"><span data-stu-id="0b61b-212">Use of FQDN name in Contact or Record-Route</span></span>

<span data-ttu-id="0b61b-213">IP 주소의 사용은 연락처 또는 연락처에서 Record-Route 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-213">Use of an IP address is not supported in either Record-Route or Contact.</span></span> <span data-ttu-id="0b61b-214">지원되는 유일한 옵션은 SBC 인증서의 일반 이름 또는 주체 대체 이름과 일치해야 하는 FQDN입니다(인증서의 와일드카드 값이 지원됩니다).</span><span class="sxs-lookup"><span data-stu-id="0b61b-214">The only supported option is an FQDN, which must match either the Common Name or Subject Alternative Name of the SBC certificate (wildcard values in the certificate are supported).</span></span>

- <span data-ttu-id="0b61b-215">IP 주소가 레코드 경로 또는 연락처에 있는 경우 인증서 검사가 실패하고 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-215">If an IP address is presented in Record-route or Contact, the certificate check fails and the call fails.</span></span>

- <span data-ttu-id="0b61b-216">FQDN이 제시된 인증서의 일반 또는 주체 대체 이름 값과 일치하지 않는 경우 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-216">If the FQDN does not match the value of the Common or Subject Alternative Name in the presented certificate, the call fails.</span></span> 

## <a name="inbound-call-sip-dialog-description"></a><span data-ttu-id="0b61b-217">인바운드 호출: SIP 대화 상자 설명</span><span class="sxs-lookup"><span data-stu-id="0b61b-217">Inbound call: SIP dialog description</span></span>

<span data-ttu-id="0b61b-218">아래 표에서는 비우회 모드와 우회 모드 간의 호출 흐름 차이 및 유사성에 대한 요약을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-218">The following table below summarizes the call flow differences and similarities between non-bypass and bypass modes:</span></span>

| <span data-ttu-id="0b61b-219">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="0b61b-219">Parameter name</span></span> | <span data-ttu-id="0b61b-220">비우회 모드</span><span class="sxs-lookup"><span data-stu-id="0b61b-220">Non-bypass mode</span></span> | <span data-ttu-id="0b61b-221">우회 모드</span><span class="sxs-lookup"><span data-stu-id="0b61b-221">Bypass mode</span></span>
| :---------------------  |:---------------------- |:----------------|
| <span data-ttu-id="0b61b-222">183개 및 200개 메시지의 미디어 후보</span><span class="sxs-lookup"><span data-stu-id="0b61b-222">Media candidates in 183 and 200 messages coming from</span></span> | <span data-ttu-id="0b61b-223">미디어 프로세서</span><span class="sxs-lookup"><span data-stu-id="0b61b-223">Media processors</span></span> | <span data-ttu-id="0b61b-224">클라이언트</span><span class="sxs-lookup"><span data-stu-id="0b61b-224">Clients</span></span> | 
| <span data-ttu-id="0b61b-225">SBC에서 받을 수 있는 메시지 수 183개</span><span class="sxs-lookup"><span data-stu-id="0b61b-225">Number of 183 messages SBC can receive</span></span> | <span data-ttu-id="0b61b-226">세션당 1개</span><span class="sxs-lookup"><span data-stu-id="0b61b-226">One per session</span></span> | <span data-ttu-id="0b61b-227">다중</span><span class="sxs-lookup"><span data-stu-id="0b61b-227">Multiple</span></span> | 
| <span data-ttu-id="0b61b-228">잠정 답변(183)으로 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-228">Call can be with provisional answer (183)</span></span> | <span data-ttu-id="0b61b-229">예</span><span class="sxs-lookup"><span data-stu-id="0b61b-229">Yes</span></span> | <span data-ttu-id="0b61b-230">예</span><span class="sxs-lookup"><span data-stu-id="0b61b-230">Yes</span></span> |
| <span data-ttu-id="0b61b-231">잠정 응답 없이 통화할 수 있습니다(183)</span><span class="sxs-lookup"><span data-stu-id="0b61b-231">Call can be without provisional answer (183)</span></span> | <span data-ttu-id="0b61b-232">예</span><span class="sxs-lookup"><span data-stu-id="0b61b-232">Yes</span></span> | <span data-ttu-id="0b61b-233">예</span><span class="sxs-lookup"><span data-stu-id="0b61b-233">Yes</span></span> |

###  <a name="non-media-bypass-flow"></a><span data-ttu-id="0b61b-234">비미디어 우회 흐름</span><span class="sxs-lookup"><span data-stu-id="0b61b-234">Non-media bypass flow</span></span>

<span data-ttu-id="0b61b-235">Teams 사용자에게 동시에 여러 엔드포인트가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-235">A Teams user might have multiple endpoints at the same time.</span></span> <span data-ttu-id="0b61b-236">예를 들어 Windows용 Teams 클라이언트, iPhone용 Teams 클라이언트 및 Teams Phone(Teams Android 클라이언트)을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-236">For example, Teams for Windows client, Teams for iPhone client, and Teams Phone (Teams Android client).</span></span> <span data-ttu-id="0b61b-237">각 엔드포인트는 다음과 같이 HTTP 나머지를 신호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-237">Each endpoint might signal an HTTP rest as follows:</span></span>

-   <span data-ttu-id="0b61b-238">호출 진행률 - SIP 프록시에서 SIP 메시지 180으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-238">Call progress – converted by the SIP proxy to the SIP message 180.</span></span> <span data-ttu-id="0b61b-239">메시지 180을 수신할 때 SBC는 로컬 벨소리를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-239">On receiving message 180, the SBC must generate local ringing.</span></span>

-   <span data-ttu-id="0b61b-240">미디어 답변 - SDP(세션 설명 프로토콜)에서 미디어 후보를 사용하여 SIP 프록시에서 메시지 183으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-240">Media answer – converted by the SIP proxy to message 183 with media candidates in Session Description Protocol (SDP).</span></span> <span data-ttu-id="0b61b-241">메시지 183을 수신할 때 SBC는 SDP 메시지에 수신된 미디어 후보에 연결할 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-241">On receiving message 183, the SBC expects to connect to the media candidates received in the SDP message.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="0b61b-242">경우에 따라 미디어 답변이 생성되지 않을 수 있으며, 엔드포인트가 "수락된 통화" 메시지로 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-242">In some cases the Media answer might not be generated, and the end point might answer with “Call Accepted” message.</span></span>

-   <span data-ttu-id="0b61b-243">수락된 호출 - SIP 프록시에서 SDP를 사용하여 SIP 메시지 200으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-243">Call accepted – converted by the SIP proxy to SIP message 200 with SDP.</span></span> <span data-ttu-id="0b61b-244">메시지 200을 수신할 때 SBC는 제공된 SDP 후보에게 미디어를 보내고 받을 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-244">On receiving message 200, the SBC is expected to send and receive media to and from the provided SDP candidates.</span></span>

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a><span data-ttu-id="0b61b-245">잠정 답변으로 울리는 여러 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="0b61b-245">Multiple endpoints ringing with provisional answer</span></span>

1.  <span data-ttu-id="0b61b-246">SBC에서 첫 번째 초대를 받을 때 SIP 프록시는 "SIP SIP/2.0 100 Trying"을 보내고 들어오는 호출에 대한 모든 최종 사용자 엔드포인트를 알림합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-246">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="0b61b-247">알림이 표시될 때 각 엔드포인트가 울리기 시작하고 SIP 프록시에 "통화 진행률" 메시지를 보내기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-247">Upon notification, each endpoint will start ringing and sending "Call progress” messages to the SIP proxy.</span></span> <span data-ttu-id="0b61b-248">Teams 사용자에게 여러 엔드포인트가 있을 수 있기 때문에 SIP 프록시는 여러 통화 진행률 메시지를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-248">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="0b61b-249">클라이언트에서 받은 모든 호출 진행률 메시지에 대해 SIP 프록시는 호출 진행률 메시지를 SIP 메시지 "SIP SIP/2.0 180 시도"로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-249">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span> <span data-ttu-id="0b61b-250">이러한 메시지를 보내는 간격은 통화 컨트롤러에서 메시지를 받는 간격으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-250">The interval for sending such messages is defined by the interval of the receiving messages from the Call Controller.</span></span> <span data-ttu-id="0b61b-251">다음 다이어그램에는 SIP 프록시에 의해 생성된 180개의 메시지가 두 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-251">In the following diagram, there are two 180 messages generated by the SIP proxy.</span></span> <span data-ttu-id="0b61b-252">이러한 메시지는 사용자의 두 Teams 엔드포인트에서 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-252">These messages come from the two Teams endpoints of the user.</span></span> <span data-ttu-id="0b61b-253">클라이언트마다 고유한 태그 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-253">The clients each have a unique Tag ID.</span></span>  <span data-ttu-id="0b61b-254">다른 엔드포인트에서 오는 모든 메시지는 별도의 세션입니다("To" 필드의 매개 변수 "태그"는 다를 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="0b61b-254">Every message coming from a different endpoint will be a separate session (the parameter “tag” in the “To” field will be different).</span></span> <span data-ttu-id="0b61b-255">그러나 엔드포인트는 다음 다이어그램과 같이 메시지 180을 생성하고 메시지 183을 바로 보내지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-255">But an endpoint might not generate message 180 and send message 183 right away as shown in the following diagram.</span></span>

4.  <span data-ttu-id="0b61b-256">엔드포인트가 엔드포인트 미디어 후보의 IP 주소가 있는 미디어 응답 메시지를 생성하면 SIP 프록시는 받은 메시지를 클라이언트의 SDP로 "SIP 183 세션 진행률" 메시지로 변환하여 미디어 프로세서의 SDP로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-256">Once an endpoint generates a Media Answer message with the IP addresses of endpoint’s media candidates, the SIP proxy converts the message received to a "SIP 183 Session Progress" message with the SDP from the client replaced by the SDP from the Media Processor.</span></span> <span data-ttu-id="0b61b-257">다음 다이어그램에서 Fork 2의 엔드포인트가 호출에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-257">In the following diagram, the endpoint from Fork 2 answered the call.</span></span> <span data-ttu-id="0b61b-258">트렁크를 무시하지 않은 경우 183 SIP 메시지는 한 번만 생성됩니다(링 봇 또는 클라이언트 엔드포인트).</span><span class="sxs-lookup"><span data-stu-id="0b61b-258">If the trunk is non-bypassed, the 183 SIP message is generated only once (either Ring Bot or Client End Point).</span></span> <span data-ttu-id="0b61b-259">183은 기존 포크에 오거나 새 포크를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-259">The 183 might come on an existing fork or start a new one.</span></span>

5.  <span data-ttu-id="0b61b-260">호출 수락 메시지는 호출을 수락한 엔드포인트의 최종 후보와 함께 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-260">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="0b61b-261">호출 수락 메시지는 SIP 메시지 200으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-261">The Call Acceptance message is converted to SIP message 200.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b61b-262">![잠정 답변으로 울리는 여러 엔드포인트를 보여주는 다이어그램](media/direct-routing-protocols-1.png)</span><span class="sxs-lookup"><span data-stu-id="0b61b-262">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-1.png)</span></span>

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a><span data-ttu-id="0b61b-263">잠정 답변 없이 울리는 여러 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="0b61b-263">Multiple endpoints ringing without provisional answer</span></span>

1.  <span data-ttu-id="0b61b-264">SBC에서 첫 번째 초대를 받을 때 SIP 프록시는 "SIP SIP/2.0 100 Trying"을 보내고 들어오는 호출에 대한 모든 최종 사용자 엔드포인트를 알림합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-264">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="0b61b-265">알림이 표시될 때 각 엔드포인트가 울리기 시작하고 SIP 프록시에 "통화 진행률"을 보내기 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-265">Upon notification, each endpoint will start ringing and sending the message "Call progress” to the SIP proxy.</span></span> <span data-ttu-id="0b61b-266">Teams 사용자에게 여러 엔드포인트가 있을 수 있기 때문에 SIP 프록시는 여러 통화 진행률 메시지를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-266">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="0b61b-267">클라이언트에서 받은 모든 호출 진행률 메시지에 대해 SIP 프록시는 호출 진행률 메시지를 SIP 메시지 "SIP SIP/2.0 180 시도"로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-267">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span>  <span data-ttu-id="0b61b-268">메시지를 보내는 간격은 통화 컨트롤러에서 메시지를 받는 간격으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-268">The interval for sending the messages is defined by the interval of receiving the messages from the Call Controller.</span></span> <span data-ttu-id="0b61b-269">아래 그림에는 SIP 프록시에서 생성된 2개의 180개의 메시지가 있습니다. 즉, 사용자가 세 개의 Teams 클라이언트에 로그인하고 각 클라이언트가 호출 진행률을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-269">On the picture below there are two 180 messages generated by the SIP proxy, meaning that user logged into three Teams clients and each client send the call progress.</span></span> <span data-ttu-id="0b61b-270">모든 메시지는 별도의 세션이 됩니다("To" 필드의 매개 변수 "tag"가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-270">Every message will be a separate session (parameter “tag” in “To” field is different)</span></span>

4.  <span data-ttu-id="0b61b-271">호출 수락 메시지는 호출을 수락한 엔드포인트의 최종 후보와 함께 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-271">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="0b61b-272">호출 수락 메시지는 SIP 메시지 200으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-272">The Call Acceptance message is converted to SIP message 200.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b61b-273">![잠정 답변 없이 울리는 여러 엔드포인트를 보여주는 다이어그램](media/direct-routing-protocols-2.png)</span><span class="sxs-lookup"><span data-stu-id="0b61b-273">![Diagram showing multiple endpoints ringing without provisional answer](media/direct-routing-protocols-2.png)</span></span>

### <a name="media-bypass-flow"></a><span data-ttu-id="0b61b-274">미디어 우회 흐름</span><span class="sxs-lookup"><span data-stu-id="0b61b-274">Media bypass flow</span></span>

<span data-ttu-id="0b61b-275">미디어 우회 시나리오에서 동일한 메시지(100 시도, 180, 183)가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-275">The same messages (100 Trying, 180, 183) are used in the media bypass scenario.</span></span> 

<span data-ttu-id="0b61b-276">아래 schema는 우회 호출 흐름의 예제를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-276">The schema below shows an example of the bypass call flow.</span></span> 

> [!NOTE]
> <span data-ttu-id="0b61b-277">미디어 후보는 서로 다른 엔드포인트에서 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-277">The media candidates can come from different endpoints.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b61b-278">![잠정 답변으로 울리는 여러 엔드포인트를 보여주는 다이어그램](media/direct-routing-protocols-3.png)</span><span class="sxs-lookup"><span data-stu-id="0b61b-278">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-3.png)</span></span>

## <a name="replaces-option"></a><span data-ttu-id="0b61b-279">대체 옵션</span><span class="sxs-lookup"><span data-stu-id="0b61b-279">Replaces option</span></span>

<span data-ttu-id="0b61b-280">SBC는 Replaces로 초대를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-280">The SBC must support Invite with Replaces.</span></span>

## <a name="size-of-sdp-considerations"></a><span data-ttu-id="0b61b-281">SDP 고려 사항의 크기</span><span class="sxs-lookup"><span data-stu-id="0b61b-281">Size of SDP considerations</span></span>

<span data-ttu-id="0b61b-282">직접 라우팅 인터페이스는 1,500 byte를 초과하는 SIP 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-282">The Direct Routing interface might send a SIP message exceeding 1,500 bytes.</span></span>  <span data-ttu-id="0b61b-283">SDP의 크기는 주로 이로 인해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-283">The size of SDP primarily causes this.</span></span> <span data-ttu-id="0b61b-284">그러나 SBC 뒤에 UDP 트렁크가 있는 경우 Microsoft SIP 프록시에서 변경되지 않은 트렁크로 전달된 경우 메시지를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-284">However, if there is a UDP trunk behind the SBC, it might reject the message if it is forwarded from the Microsoft SIP proxy to the trunk unmodified.</span></span> <span data-ttu-id="0b61b-285">메시지를 UDP 트렁크로 보낼 때 SBC의 SDP에서 일부 값을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-285">Microsoft recommends stripping some values in SDP on the SBC when sending the message to the UDP trunks.</span></span> <span data-ttu-id="0b61b-286">예를 들어 ICE 후보 또는 사용되지 않는 코덱을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-286">For example, the ICE candidates or unused codecs can be removed.</span></span>

## <a name="call-transfer"></a><span data-ttu-id="0b61b-287">통화 전송</span><span class="sxs-lookup"><span data-stu-id="0b61b-287">Call transfer</span></span>

<span data-ttu-id="0b61b-288">직접 라우팅은 통화 전송에 대한 두 가지 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-288">Direct Routing supports two methods for call transfer:</span></span>

- <span data-ttu-id="0b61b-289">옵션 1.</span><span class="sxs-lookup"><span data-stu-id="0b61b-289">Option 1.</span></span> <span data-ttu-id="0b61b-290">SIP 프록시 프로세스는 클라이언트에서 로컬로 참조하고 RFC 3892의 섹션 7.1에 설명된 바와 같이 심판 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-290">SIP proxy processes Refer from the client locally and acts as a Referee as described in section 7.1 of RFC 3892.</span></span>

  <span data-ttu-id="0b61b-291">이 옵션을 사용하면 SIP 프록시가 전송을 종료하고 새 초대를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-291">With this option, the SIP proxy terminates the transfer and adds a new Invite.</span></span> 


- <span data-ttu-id="0b61b-292">옵션 2.</span><span class="sxs-lookup"><span data-stu-id="0b61b-292">Option 2.</span></span> <span data-ttu-id="0b61b-293">SIP 프록시는 SBC 참조를 보내고 RFC 5589의 섹션 6에서 설명하는 전송자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-293">SIP proxy sends the Refer to the SBC and acts as a Transferor as describing in Section 6 of RFC 5589.</span></span>

  <span data-ttu-id="0b61b-294">이 옵션을 사용하면 SIP 프록시는 SBC 참조를 보내고 SBC가 전송을 완전히 처리하기를 기대합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-294">With this option, the SIP proxy sends a Refer to the SBC and expects the SBC to handle the Transfer fully.</span></span>

<span data-ttu-id="0b61b-295">SIP 프록시는 SBC에서 보고하는 기능에 따라 메서드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-295">The SIP proxy selects the method based on the capabilities reported by the SBC.</span></span> <span data-ttu-id="0b61b-296">SBC가 메서드 "참조"를 지원하고 있는 경우 SIP 프록시는 통화 전송에 옵션 2를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-296">If the SBC indicates that it supports the method “Refer”, the SIP proxy will use Option 2 for call transfers.</span></span>

<span data-ttu-id="0b61b-297">다음은 참조 메서드가 지원되는 메시지를 보내는 SBC의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-297">The following is an example of an SBC sending the message that the Refer method is supported:</span></span>

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

<span data-ttu-id="0b61b-298">SBC에서 지원되는 메서드로 참조를 나타내지 않는 경우 직접 라우팅은 Option 1(SIP 프록시는 심판 역할을 합니다)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-298">If the SBC doesn’t indicate that Refer as a supported method, Direct Routing will use Option 1 (SIP proxy acts as a Referee) .</span></span> <span data-ttu-id="0b61b-299">또한 SBC는 알림 메서드를 지원하는지 신호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-299">The SBC  must also signal that it supports the Notify method:</span></span>

<span data-ttu-id="0b61b-300">참조 메서드가 지원되지 않는다는 것을 나타내는 SBC의 예:</span><span class="sxs-lookup"><span data-stu-id="0b61b-300">Example of SBC indicating that Refer method is not supported:</span></span>

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a><span data-ttu-id="0b61b-301">SIP 프록시 프로세스는 클라이언트에서 로컬로 참조하고 심판 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-301">SIP proxy processes Refer from the client locally and acts as a Referee</span></span>

<span data-ttu-id="0b61b-302">SBC에서 참조 메서드가 지원되지 않는다고 표시한 경우 SIP 프록시는 심판 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-302">If the SBC indicated that the Refer method is not supported, the SIP proxy acts as a Referee.</span></span> 

<span data-ttu-id="0b61b-303">클라이언트에서 오는 참조 요청은 SIP 프록시에서 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-303">The Refer request that comes from the client will be terminated on the SIP proxy.</span></span> <span data-ttu-id="0b61b-304">(클라이언트의 참조 요청은 다음 다이어그램에서 "Dave로 전화 전송"으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-304">(The Refer request from the client is shown as “Call transfer to Dave” in the following diagram.</span></span>  <span data-ttu-id="0b61b-305">자세한 내용은 [RFC 3892의 7.1 섹션을 참조하세요.](https://www.ietf.org/rfc/rfc3892.txt)</span><span class="sxs-lookup"><span data-stu-id="0b61b-305">For more information, see section 7.1 of [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b61b-306">![잠정 답변으로 울리는 여러 엔드포인트를 보여주는 다이어그램](media/direct-routing-protocols-4.png)</span><span class="sxs-lookup"><span data-stu-id="0b61b-306">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-4.png)</span></span>

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a><span data-ttu-id="0b61b-307">SIP 프록시는 SBC 참조를 보내고 전송자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-307">SIP proxy send the Refer to the SBC and acts as a Transferor</span></span>

<span data-ttu-id="0b61b-308">이 방법은 통화 전송에 선호되는 방법으로, 미디어 우회 인증을 찾는 디바이스에 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-308">This is the preferred method for call transfers, and it is mandatory for devices seeking media bypass certification.</span></span> <span data-ttu-id="0b61b-309">참조를 처리할 수 있는 SBC가 없는 통화 전송은 미디어 우회 모드에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-309">Call Transfer without the SBC being able to handle Refer is not supported in media bypass mode.</span></span> 

<span data-ttu-id="0b61b-310">표준은 RFC 5589의 섹션 6에 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-310">The standard is explained in Section 6 of RFC 5589.</span></span> <span data-ttu-id="0b61b-311">관련 RFC는:</span><span class="sxs-lookup"><span data-stu-id="0b61b-311">The related RFCs are:</span></span>

- [<span data-ttu-id="0b61b-312">SIP(세션 시작 프로토콜) 호출 제어 - 전송</span><span class="sxs-lookup"><span data-stu-id="0b61b-312">Session Initiation Protocol (SIP) Call Control - Transfer</span></span>](https://tools.ietf.org/html/rfc5589)

- [<span data-ttu-id="0b61b-313">SIP(세션 시작 프로토콜) "대체" 헤더</span><span class="sxs-lookup"><span data-stu-id="0b61b-313">Session Initiation Protocol (SIP) "Replaces" Header</span></span>](https://tools.ietf.org/html/rfc3891)

- [<span data-ttu-id="0b61b-314">세션 시작 프로토콜(SIP) "Referred-By" 메커니즘</span><span class="sxs-lookup"><span data-stu-id="0b61b-314">Session Initiation Protocol (SIP) "Referred-By" mechanism</span></span>](https://tools.ietf.org/html/rfc3892)

<span data-ttu-id="0b61b-315">이 옵션은 SIP 프록시가 전송자 역할을 하여 SBC에 참조 메시지를 보낸 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-315">This option assumes that the SIP proxy acts as a Transferor and sends a Refer message to the SBC.</span></span> <span data-ttu-id="0b61b-316">SBC는 전송자 역할을 하며 참조를 처리하여 새 전송 제안을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-316">The SBC acts as a Transferee and handles the Refer to generate a new offer for transfer.</span></span> <span data-ttu-id="0b61b-317">두 가지 가능한 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-317">There are two possible cases:</span></span>

- <span data-ttu-id="0b61b-318">호출은 외부 PSTN 참가자로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-318">The call is transferred to an external PSTN participant.</span></span> 
- <span data-ttu-id="0b61b-319">호출은 SBC를 통해 동일한 테넌트의 다른 Teams 사용자로 한 Teams 사용자에서 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-319">The call is transferred from one Teams user to another Teams user in the same tenant via the SBC.</span></span> 

<span data-ttu-id="0b61b-320">호출이 SBC를 통해 한 Teams 사용자에서 다른 팀 사용자로 전송되는 경우 SBC는 참조 메시지에 수신된 정보를 사용하여 전송 대상(Teams 사용자)에 대한 새 초대(새 대화 상자 시작)를 발급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-320">If the call is transferred from one Teams user to another via the SBC, the SBC is expected to issue a new invite (start a new dialog) for the transfer target (the Teams user) using the information received in the Refer message.</span></span> 

<span data-ttu-id="0b61b-321">요청 트랜잭션에 대한 To/Transferor 필드를 내부적으로 채우기 위해 SIP 프록시는 REFER-TO/REFERRED-BY 헤더 내에서 이 정보를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-321">To populate the To/Transferor fields for the transaction of the request internally, the SIP proxy needs to convey this information  inside the REFER-TO/REFERRED-BY headers.</span></span> 

<span data-ttu-id="0b61b-322">SIP 프록시는 호스트 이름의 SIP 프록시 FQDN으로 구성된 SIP URI로 REFER-TO를 형성하고 다음 중 하나를 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-322">The SIP proxy will form the REFER-TO as a SIP URI comprised of a SIP proxy FQDN in the hostname and either one of the following:</span></span>

- <span data-ttu-id="0b61b-323">전송 대상이 전화 번호인 경우 URI의 사용자 이름 부분의 E.164 전화 번호</span><span class="sxs-lookup"><span data-stu-id="0b61b-323">An E.164 phone number in the username part of the URI in case the transfer target is a phone number, or</span></span>

- <span data-ttu-id="0b61b-324">전체 전송 대상 MRI 및 테넌트 ID를 각각 인코딩하는 x-m 및 x-t 매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b61b-324">x-m and x-t parameters encoding the full transfer target MRI and tenant ID respectively</span></span> 

<span data-ttu-id="0b61b-325">REFERRED-BY 헤더는 다음 표와 같이 전송자 테넌트 ID 및 기타 전송 컨텍스트 매개 변수뿐만 아니라 전송자 MRI가 인코딩된 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-325">The REFERRED-BY header is a SIP URI with transferor MRI encoded in it as well as transferor tenant ID and other transfer context parameters as shown in the following table:</span></span>

| <span data-ttu-id="0b61b-326">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b61b-326">Parameter</span></span> | <span data-ttu-id="0b61b-327">값</span><span class="sxs-lookup"><span data-stu-id="0b61b-327">Value</span></span> | <span data-ttu-id="0b61b-328">설명</span><span class="sxs-lookup"><span data-stu-id="0b61b-328">Description</span></span> |  
|:---------------------  |:---------------------- |:---------------------- |
| <span data-ttu-id="0b61b-329">x-m</span><span class="sxs-lookup"><span data-stu-id="0b61b-329">x-m</span></span> | <span data-ttu-id="0b61b-330">MRI</span><span class="sxs-lookup"><span data-stu-id="0b61b-330">MRI</span></span> | <span data-ttu-id="0b61b-331">CC에 의해 채워진 전송기/전송 대상의 전체 MRI</span><span class="sxs-lookup"><span data-stu-id="0b61b-331">Full MRI of transferor/transfer target as populated by CC</span></span> |
| <span data-ttu-id="0b61b-332">x-t</span><span class="sxs-lookup"><span data-stu-id="0b61b-332">x-t</span></span> | <span data-ttu-id="0b61b-333">테넌트 ID</span><span class="sxs-lookup"><span data-stu-id="0b61b-333">Tenant ID</span></span> | <span data-ttu-id="0b61b-334">x-t 테넌트 ID 선택적 테넌트 ID가 CC로 채워진 경우</span><span class="sxs-lookup"><span data-stu-id="0b61b-334">x-t Tenant ID Optional Tenant ID as populated by CC</span></span> |
| <span data-ttu-id="0b61b-335">x-ti</span><span class="sxs-lookup"><span data-stu-id="0b61b-335">x-ti</span></span> | <span data-ttu-id="0b61b-336">전송자 상관 관계 ID</span><span class="sxs-lookup"><span data-stu-id="0b61b-336">Transferor Correlation Id</span></span> | <span data-ttu-id="0b61b-337">전송자에 대한 호출의 상관 관계 ID</span><span class="sxs-lookup"><span data-stu-id="0b61b-337">Correlation ID of the call to the transferor</span></span> |
| <span data-ttu-id="0b61b-338">x-tt</span><span class="sxs-lookup"><span data-stu-id="0b61b-338">x-tt</span></span> | <span data-ttu-id="0b61b-339">전송 대상 호출 URI</span><span class="sxs-lookup"><span data-stu-id="0b61b-339">Transfer target call URI</span></span> | <span data-ttu-id="0b61b-340">인코딩된 호출 대체 URI</span><span class="sxs-lookup"><span data-stu-id="0b61b-340">Encoded call replacement URI</span></span> |

<span data-ttu-id="0b61b-341">참조 헤더의 크기는 이 경우 최대 400개 기호일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-341">The size of the Refer Header can be up to 400 symbols in this case.</span></span> <span data-ttu-id="0b61b-342">SBC는 최대 400개 기호 크기의 참조 메시지 처리를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-342">The SBC must support handling Refer messages with size up to 400 symbols.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b61b-343">![잠정 답변으로 울리는 여러 엔드포인트를 보여주는 다이어그램](media/direct-routing-protocols-5.png)</span><span class="sxs-lookup"><span data-stu-id="0b61b-343">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-5.png)</span></span>

## <a name="session-timer"></a><span data-ttu-id="0b61b-344">세션 시간</span><span class="sxs-lookup"><span data-stu-id="0b61b-344">Session timer</span></span>

<span data-ttu-id="0b61b-345">SIP 프록시는 비우회 호출에서 세션 시간(항상 제공)을 지원하지만, 우회 호출에서는 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-345">The SIP proxy supports (always offers) the Session Timer on non-bypass calls but does not offer it on bypass calls.</span></span> <span data-ttu-id="0b61b-346">SBC에서 세션 시간(Session Timer)을 사용하는 것은 필수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-346">Use of the Session Timer by the SBC is not mandatory.</span></span>

##  <a name="use-of-request-uri-parameter-userphone"></a><span data-ttu-id="0b61b-347">Request-URI 매개 변수 user=phone 사용</span><span class="sxs-lookup"><span data-stu-id="0b61b-347">Use of Request-URI parameter user=phone</span></span>

<span data-ttu-id="0b61b-348">SIP 프록시는 Request-URI를 분석하고 매개 변수 user=phone이 있는 경우 서비스는 Request-URI를 전화 번호로 처리하여 사용자와 번호가 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-348">The SIP proxy analyses the Request-URI and if the parameter user=phone is present, the service will handle the Request-URI as a phone number, matching the number to a user.</span></span> <span data-ttu-id="0b61b-349">매개 변수가 없는 경우 SIP 프록시는 요청-URI 사용자 유형(전화 번호 또는 SIP 주소)을 결정하기 위해 heuristics를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-349">If parameter is not present the SIP proxy applies heuristics to determine  the Request-URI user type (phone number or a SIP address).</span></span>

<span data-ttu-id="0b61b-350">호출 설정 프로세스를 간소화하기 위해 항상 user=phone 매개 변수를 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-350">Microsoft recommends always applying the user=phone parameter to simplify the call setup process.</span></span>

## <a name="history-info-header"></a><span data-ttu-id="0b61b-351">History-Info 헤더</span><span class="sxs-lookup"><span data-stu-id="0b61b-351">History-Info header</span></span>

<span data-ttu-id="0b61b-352">History-Info 헤더는 SIP 요청을 리타게팅하는 데 사용됩니다. "제공(을) 네트워크 및 최종 사용자에 대한 다양한 서비스를 사용하도록 요청 기록 정보를 캡처하기 위한 표준 메커니즘"입니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-352">The History-Info header is used for retargeting SIP requests and “provide(s) a standard mechanism for capturing the request history information to enable a wide variety of services for networks and end-users.”</span></span> <span data-ttu-id="0b61b-353">자세한 내용은 [RFC 4244 – 섹션 1.1 을 참조하세요.](http://www.ietf.org/rfc/rfc4244.txt)</span><span class="sxs-lookup"><span data-stu-id="0b61b-353">For more information, see [RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt).</span></span> <span data-ttu-id="0b61b-354">Microsoft Phone System의 경우 이 헤더는 시뮬레이션 및 전달 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-354">For Microsoft Phone System, this header is used in Simulring and Call Forwarding scenarios.</span></span>  

<span data-ttu-id="0b61b-355">보내는 경우 다음과 History-Info 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-355">If sending, the History-Info is enabled as follows:</span></span>

- <span data-ttu-id="0b61b-356">SIP 프록시는 PSTN 컨트롤러로 전송된 History-Info 구성하는 개별 History-Info 전화 번호가 포함된 매개 변수를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-356">The SIP proxy will insert a parameter containing the associated phone number in individual History-Info entries that comprise the History-Info header sent to the PSTN Controller.</span></span>  <span data-ttu-id="0b61b-357">전화 번호 매개 변수가 있는 항목만 사용하여 PSTN 컨트롤러는 새 History-Info 헤더를 다시 작성하고 SIP 프록시를 통해 SIP 트렁크 공급자에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-357">Using only entries that have the phone number parameter, the PSTN Controller will rebuild a new History-Info header, and pass it on to the SIP trunk provider via SIP proxy.</span></span>

- <span data-ttu-id="0b61b-358">History-Info 링 및 통화 전달 사례에 대한 추가 헤더가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-358">History-Info header will be added for simultaneous ring and call forwarding cases.</span></span>

- <span data-ttu-id="0b61b-359">History-Info 전송 사례에 대해 헤더가 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-359">History-Info header will not be added for call transfer cases.</span></span>

- <span data-ttu-id="0b61b-360">재구성된 History-Info 헤더의 개별 기록 항목에는 URI의 호스트 부분으로 설정된 직접 라우팅 FQDN(sip.pstnhub.microsoft.com)과 함께 제공되는 전화 번호 매개 변수가 있습니다. 'user=phone'의 매개 변수가 SIP URI의 일부로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-360">An individual history entry in the reconstructed History-Info header will have the phone number parameter provided combined with the Direct Routing FQDN (sip.pstnhub.microsoft.com) set as the host part of the URI; a parameter of ‘user=phone’ will be added as part of the SIP URI.</span></span>  <span data-ttu-id="0b61b-361">전화 컨텍스트 매개 변수를 제외한 원래 History-Info 다른 매개 변수는 다시 생성된 History-Info 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-361">Any other parameters associated with the original History-Info header, except for phone context parameters, will be passed through in the re-constructed History-Info header.</span></span>  

  > [!NOTE]
  > <span data-ttu-id="0b61b-362">개인 항목(RFC 4244의 섹션 3.3에 정의된 메커니즘에 따라 결정)은 SIP 트렁크 공급자가 신뢰할 수 있는 피어이기 때문에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-362">Entries that are private (as determined by the mechanisms defined in Section 3.3 of RFC 4244) will be forwarded as is because  the SIP trunk provider is a trusted peer.</span></span>

- <span data-ttu-id="0b61b-363">인바운드 History-Info 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-363">Inbound History-Info is ignored.</span></span>

<span data-ttu-id="0b61b-364">다음은 SIP 프록시에서 보낸 기록 정보 헤더의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-364">Following is the format of the History-info header sent by the SIP proxy:</span></span>

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

<span data-ttu-id="0b61b-365">호출이 여러 번 리디렉션된 경우 모든 리디렉션에 대한 정보가 시간 순서대로 적절한 이유에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-365">If the call was redirected several times, information about every redirect is included with the appropriate reason in chronological order.</span></span>


<span data-ttu-id="0b61b-366">헤더 예제:</span><span class="sxs-lookup"><span data-stu-id="0b61b-366">Header Example:</span></span>

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

<span data-ttu-id="0b61b-367">History-Info TLS 메커니즘으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-367">The History-Info is protected by a mandatory TLS mechanism.</span></span> 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a><span data-ttu-id="0b61b-368">직접 라우팅 및 장애 조치 메커니즘에 대한 SBC 연결</span><span class="sxs-lookup"><span data-stu-id="0b61b-368">SBC connection to Direct Routing and failover mechanism</span></span>

<span data-ttu-id="0b61b-369">직접 라우팅 계획의 SIP 신호에 대한 장애 조치 메커니즘 [섹션을 참조하세요.](direct-routing-plan.md#failover-mechanism-for-sip-signaling)</span><span class="sxs-lookup"><span data-stu-id="0b61b-369">See the section Failover mechanism for SIP signaling in [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).</span></span>

## <a name="retry-after"></a><span data-ttu-id="0b61b-370">Retry-After</span><span class="sxs-lookup"><span data-stu-id="0b61b-370">Retry-After</span></span>

<span data-ttu-id="0b61b-371">직접 라우팅 데이터 센터가 사용 중이면 서비스는 1초 간격으로 Retry-After 메시지를 SBC로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-371">If a Direct Routing datacenter is busy, the service can send a Retry-After message with a one-second interval to the SBC.</span></span> <span data-ttu-id="0b61b-372">SBC에서 INVITE에 대한 응답으로 Retry-After 503 메시지를 수신하면 SBC는 해당 연결을 종료하고 사용 가능한 다음 Microsoft 데이터 센터를 시도해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-372">When the SBC receives a 503 message with a Retry-After header in response to an INVITE, the SBC must terminate that connection and try the next available Microsoft datacenter.</span></span>

## <a name="handling-retries-603-response"></a><span data-ttu-id="0b61b-373">재시도 처리(603 응답)</span><span class="sxs-lookup"><span data-stu-id="0b61b-373">Handling retries (603 response)</span></span>
<span data-ttu-id="0b61b-374">최종 사용자가 들어오는 호출을 감소한 후에 하나의 호출에 대해 여러 번 누락된 호출을 관찰하는 경우 SBC 또는 PSTN 트렁크 공급자의 재시도 메커니즘이 잘못 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-374">If an end user observes several missed calls for one call after declining the incoming call, it means that the SBC or PSTN trunk provider's retry mechanism is misconfigured.</span></span> <span data-ttu-id="0b61b-375">603 응답에서 재시도 노력을 중지하려면 SBC를 다시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-375">The SBC must be reconfigured to stop the retry efforts on the 603 response.</span></span>

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a><span data-ttu-id="0b61b-376">ICE 다시 시작: 미디어 우회를 지원하지 않는 엔드포인트로 전송된 미디어 우회 호출</span><span class="sxs-lookup"><span data-stu-id="0b61b-376">ICE Restart: Media bypass call transferred to an endpoint that does not support media bypass</span></span>

<span data-ttu-id="0b61b-377">SBC는 [RFC 5245 섹션 9.1.1.1에](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)설명된 바와 같이 ICE 다시 시작을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-377">The SBC must support ICE restarts as described in [RFC 5245, section 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span>

<span data-ttu-id="0b61b-378">직접 라우팅에서 다시 시작은 RFC의 다음 단락에 따라 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-378">The restart in Direct Routing is implemented according to the following paragraphs of the RFC:</span></span>

<span data-ttu-id="0b61b-379">*ICE를 다시 시작하려면 에이전트가 제안의 미디어 스트림에 대한 ice-pwd 및 ice-ufrag를 모두 변경해야 합니다.  한 제안에서 세션 수준 특성을 사용할 수 있지만, 후속 제안에서 미디어 수준 특성으로 동일한 ice-pwd 또는 ice-ufrag를 제공하는 것이 제한됩니다.  이는 암호의 변경이 아니라 표현의 변경일 뿐만 아니라 ICE 다시 시작을 유발하지 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="0b61b-379">*To restart ICE, an agent MUST change both the ice-pwd and the ice-ufrag for the media stream in an offer.  Note that it is permissible to use a session-level attribute in one offer, but to provide the same ice-pwd or ice-ufrag as a media-level attribute in a subsequent offer.  This is not a change in password, just a change in its representation, and does not cause an ICE restart.*</span></span>

<span data-ttu-id="0b61b-380">*에이전트는 이 미디어 스트림의 초기 제안에서와 같은 이 미디어 스트림에 대한 SDP의 나머지 필드를 설정합니다(섹션 4.3 참조).  따라서 후보 집합에는 해당 스트림에 대한 일부, 없음 또는 모든 이전 후보가 포함될 수 있으며, 4.1.1 섹션에 설명된 바와 같이 수집된 완전히 새로운 후보 집합이 포함될 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="0b61b-380">*An agent sets the rest of the fields in the SDP for this media stream as it would in an initial offer of this media stream (see Section 4.3).  Consequently, the set of candidates MAY include some, none, or all of the previous candidates for that stream and MAY include a totally new set of candidates gathered as described in Section 4.1.1.*</span></span>

<span data-ttu-id="0b61b-381">처음에 미디어 우회를 사용하여 호출이 설정된 경우 통화가 비즈니스용 Skype 클라이언트로 전송되는 경우 직접 라우팅은 미디어 프로세서를 삽입해야 합니다. 즉, 미디어 우회가 있는 비즈니스용 Skype 클라이언트에서 직접 라우팅을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-381">If the call was initially established with media bypass, and the call is transferred to a Skype for Business client, Direct Routing needs to insert a Media Processor--this is because Direct Routing cannot be used with a Skype for Business client with media bypass.</span></span> <span data-ttu-id="0b61b-382">직접 라우팅은 ice-pwd 및 ice-ufrag를 변경하고 새로운 미디어 후보를 다시 시작하여 ICE 다시 시작 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0b61b-382">Direct Routing starts the ICE restart process by  changing the ice-pwd and ice-ufrag and offering new media candidates in a reinvite.</span></span>
