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
description: 다이렉트 라우팅 프로토콜
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5fc90ace7a2b1bd8a6984c7268903a1a6063e137
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835038"
---
# <a name="direct-routing---sip-protocol"></a><span data-ttu-id="84765-103">다이렉트 라우팅-SIP 프로토콜</span><span class="sxs-lookup"><span data-stu-id="84765-103">Direct Routing - SIP protocol</span></span>

<span data-ttu-id="84765-104">이 문서에서는 다이렉트 라우팅이 세션 시작 프로토콜 (SIP)을 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-104">This article describes how Direct Routing implements the Session Initiation Protocol (SIP).</span></span> <span data-ttu-id="84765-105">SBC (세션 경계 컨트롤러)와 SIP 프록시 간의 트래픽을 적절 하 게 라우팅하려면 일부 SIP 매개 변수에 특정 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-105">To properly route traffic between a Session Border Controller (SBC) and the SIP proxy, some SIP parameters must have specific values.</span></span> <span data-ttu-id="84765-106">이 문서는 온-프레미스 SBC 및 SIP 프록시 서비스 간 연결 구성을 담당 하는 음성 관리자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-106">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a><span data-ttu-id="84765-107">수신 요청 처리: 테 넌 트 및 사용자 찾기</span><span class="sxs-lookup"><span data-stu-id="84765-107">Processing the incoming request: finding the tenant and user</span></span>

<span data-ttu-id="84765-108">수신 전화에서 SIP 프록시는 통화가 전송 되는 테 넌 트를 찾아이 테 넌 트 내의 특정 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-108">On an incoming call, the SIP proxy needs to find the tenant to which the call is destined and find the specific user within this tenant.</span></span> <span data-ttu-id="84765-109">테 넌 트 관리자는 여러 테 넌 트에 + 1001와 같이 숫자가 아닌 번호를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-109">The tenant administrator might configure non-DID numbers, for example +1001, in multiple tenants.</span></span> <span data-ttu-id="84765-110">따라서 여러 Office 365 테 넌 트에서 숫자가 아닌 숫자가 동일할 수 있으므로 번호 조회를 수행할 특정 테 넌 트를 찾는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-110">Therefore, it is important to find the specific tenant on which to perform the number lookup because the non-DID numbers might be the same in multiple Office 365 tenants.</span></span>  

<span data-ttu-id="84765-111">이 섹션에서는 SIP 프록시에서 테 넌 트 및 사용자를 찾고, 들어오는 연결에 대 한 SBC의 인증을 수행 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-111">This section describes how the SIP proxy finds the tenant and the user, and performs authentication of the SBC on the incoming connection.</span></span>

<span data-ttu-id="84765-112">다음은 수신 전화에 대 한 SIP 초대 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="84765-112">The following is an example of the SIP Invite message on an incoming call:</span></span>

| <span data-ttu-id="84765-113">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="84765-113">Parameter name</span></span> | <span data-ttu-id="84765-114">값의 예</span><span class="sxs-lookup"><span data-stu-id="84765-114">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="84765-115">요청 URI</span><span class="sxs-lookup"><span data-stu-id="84765-115">Request-URI</span></span> | <span data-ttu-id="84765-116">Sip:+18338006777@sip.pstnhub.microsoft.com SIP/2.0 초대</span><span class="sxs-lookup"><span data-stu-id="84765-116">INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span></span> |
| <span data-ttu-id="84765-117">Via 헤더</span><span class="sxs-lookup"><span data-stu-id="84765-117">Via Header</span></span> | <span data-ttu-id="84765-118">Via: SIP/2.0/TLS sbc1:5058, alias, branch = z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="84765-118">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="84765-119">최대 전달 헤더</span><span class="sxs-lookup"><span data-stu-id="84765-119">Max-Forwards header</span></span> | <span data-ttu-id="84765-120">최대 착신: 68</span><span class="sxs-lookup"><span data-stu-id="84765-120">Max-Forwards:68</span></span> |
| <span data-ttu-id="84765-121">머리글에서</span><span class="sxs-lookup"><span data-stu-id="84765-121">From Header</span></span> | <span data-ttu-id="84765-122">보낸 사람 머리글: <sip: 7168712781@sbc1 adatum, transport = udp, tag = 1c747237679</span><span class="sxs-lookup"><span data-stu-id="84765-122">From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span></span> |
| <span data-ttu-id="84765-123">To 머리글</span><span class="sxs-lookup"><span data-stu-id="84765-123">To Header</span></span> | <span data-ttu-id="84765-124">대상: sip:+183338006777@sbc1.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="84765-124">To: sip:+183338006777@sbc1.adatum.biz</span></span> | 
| <span data-ttu-id="84765-125">CSeq 헤더</span><span class="sxs-lookup"><span data-stu-id="84765-125">CSeq header</span></span> | <span data-ttu-id="84765-126">CSeq: 1 초대</span><span class="sxs-lookup"><span data-stu-id="84765-126">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="84765-127">연락처 머리글</span><span class="sxs-lookup"><span data-stu-id="84765-127">Contact Header</span></span> | <span data-ttu-id="84765-128">연락처: <sip: 68712781@sbc1 adatum, transport = tls></span><span class="sxs-lookup"><span data-stu-id="84765-128">Contact: <sip: 68712781@sbc1.adatum.biz;transport=tls></span></span> | 

<span data-ttu-id="84765-129">초대를 받을 때 SIP 프록시는 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-129">On receiving the invite, the SIP proxy performs the following steps:</span></span>

1. <span data-ttu-id="84765-130">인증서를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-130">Check the certificate.</span></span> <span data-ttu-id="84765-131">초기 연결에서 다이렉트 라우팅 서비스는 Contact 헤더에 표시 된 FQDN 이름을 가져와 제시 된 인증서의 일반 이름 또는 주체 대체 이름과 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="84765-131">On the initial connection, the Direct Routing service takes the FQDN name presented in the Contact header and matches it to the Common Name or Subject Alternative name of the presented certificate.</span></span> <span data-ttu-id="84765-132">SBC 이름은 다음 옵션 중 하 나와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-132">The SBC name must match one of the following options:</span></span>

   - <span data-ttu-id="84765-133">옵션 1.</span><span class="sxs-lookup"><span data-stu-id="84765-133">Option 1.</span></span> <span data-ttu-id="84765-134">Contact 헤더에 표시 되는 전체 FQDN 이름은 제시 된 인증서의 일반 이름/주체 대체 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-134">The full FQDN name presented in the Contact header must match the Common Name/Subject Alternative name of the presented certificate.</span></span>  

   - <span data-ttu-id="84765-135">옵션 2.</span><span class="sxs-lookup"><span data-stu-id="84765-135">Option 2.</span></span> <span data-ttu-id="84765-136">Contact 헤더에 표시 되는 FQDN 이름 (예: FQDN name sbc1.adatum.biz의 adatum.biz)의 도메인 부분은 일반 이름/주체 대체 이름 (예: \*. adatum.biz)의 와일드 카드 값과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-136">The domain portion of the FQDN name presented in the Contact header (for example adatum.biz of the FQDN name sbc1.adatum.biz) must match the wildcard value in Common Name/Subject Alternative Name (for example \*.adatum.biz).</span></span>

2. <span data-ttu-id="84765-137">연락처 머리글에 표시 된 전체 FQDN 이름을 사용 하 여 테 넌 트를 찾아 봅니다.</span><span class="sxs-lookup"><span data-stu-id="84765-137">Try to find a tenant using the full FQDN name presented in the Contact header.</span></span>  

   <span data-ttu-id="84765-138">Contact 헤더의 FQDN 이름 (sbc1.adatum.biz)이 Office 365 테 넌 트에서 DNS 이름으로 등록 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-138">Check if the FQDN name from the Contact header (sbc1.adatum.biz) is registered as a DNS name in any Office 365 tenant.</span></span> <span data-ttu-id="84765-139">발견 되 면 사용자의 조회가 도메인 이름으로 등록 된 SBC FQDN이 있는 테 넌 트에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-139">If found, the lookup of the user is performed in the tenant that has the SBC FQDN registered as a Domain name.</span></span> <span data-ttu-id="84765-140">이를 찾을 수 없는 경우 3 단계가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-140">If not found, Step 3 applies.</span></span>   

3. <span data-ttu-id="84765-141">3 단계는 2 단계가 실패 한 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-141">Step 3 only applies if Step 2 failed.</span></span> 

   <span data-ttu-id="84765-142">FQDN에서 호스트 부분 (호스트 부분: adatum.biz을 제거한 후에는 FQDN: sbc12.adatum.biz)을 제거 하 고이 이름이 Office 365 테 넌 트에서 DNS 이름으로 등록 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-142">Remove the host portion from the FQDN, presented in the Contact header (FQDN: sbc12.adatum.biz, after removing the host portion: adatum.biz), and check if this name is registered as a DNS name in any Office 365 tenant.</span></span> <span data-ttu-id="84765-143">발견 되 면 사용자 조회가이 테 넌 트에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-143">If found, the user lookup is performed in this tenant.</span></span> <span data-ttu-id="84765-144">찾을 수 없는 경우에는 통화에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-144">If not found, the call fails.</span></span>

4. <span data-ttu-id="84765-145">요청 URI에 표시 된 전화 번호를 사용 하 여 2 단계 또는 3 단계의 테 넌 트 내에서 역 번호 조회를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-145">Using the phone number presented in the Request-URI, perform the reverse number lookup within the tenant found in Step 2 or 3.</span></span> <span data-ttu-id="84765-146">제시 된 전화 번호를 이전 단계에서 찾은 테 넌 트 내의 사용자 SIP URI와 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="84765-146">Match the presented phone number to a user SIP URI within the tenant found on the previous step.</span></span>

5. <span data-ttu-id="84765-147">트렁크 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-147">Apply trunk settings.</span></span> <span data-ttu-id="84765-148">이 SBC에 대 한 테 넌 트 관리자가 설정한 매개 변수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-148">Find the parameters set by the tenant admin for this SBC.</span></span>

   <span data-ttu-id="84765-149">Microsoft는 Microsoft SIP 프록시와 쌍으로 연결 된 SBC 사이에 타사 SIP 프록시 또는 사용자 에이전트 서버를 지원 하지 않으며,이는 페어링된 SBC에서 만든 요청 URI를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-149">Microsoft does not support having a third-party SIP proxy or User Agent Server between the Microsoft SIP proxy and the paired SBC, which might modify the Request URI created by the paired SBC.</span></span>

   <span data-ttu-id="84765-150">한 SBC이 여러 테 넌 트에 연결 되어 있는 시나리오에 필요한 두 가지 조회 (2 단계 및 3 번)에 대 한 요구 사항은이 문서의 뒷부분에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-150">The requirements for the two lookups (steps 2 and 3) needed for the scenario where one SBC is interconnected to many tenants (carrier scenario) are covered later in this article.</span></span>

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a><span data-ttu-id="84765-151">연락처 헤더 및 요청 URI에 대 한 자세한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="84765-151">Detailed requirements for Contact header and Request-URI</span></span>

#### <a name="contact-header"></a><span data-ttu-id="84765-152">연락처 머리글</span><span class="sxs-lookup"><span data-stu-id="84765-152">Contact header</span></span>

<span data-ttu-id="84765-153">Microsoft SIP 프록시로 들어오는 모든 통화에 대해 Contact 헤더에 다음과 같이 URI 호스트 이름에 쌍으로 된 SBC FQDN이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-153">For all incoming calls to the Microsoft SIP proxy, the Contact header must have the paired SBC FQDN in the URI hostname as follows:</span></span>

<span data-ttu-id="84765-154">구문: 연락처: <sip: SBC의 휴대폰 또는 sip address@FQDN, transport = tls></span><span class="sxs-lookup"><span data-stu-id="84765-154">Syntax: Contact:  <sip:phone or sip address@FQDN of the SBC;transport=tls></span></span> 

<span data-ttu-id="84765-155">이 이름은 제시 된 인증서의 일반 이름 또는 주체 대체 이름 필드에도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-155">This name must also be in the Common Name or Subject Alternative name field(s) of the presented certificate.</span></span> <span data-ttu-id="84765-156">Microsoft는 인증서의 일반 이름 또는 주체 대체 이름 필드에서 이름의 와일드 카드 값을 사용 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-156">Microsoft supports using wildcard values of the name(s) in the Common Name or Subject Alternative Name fields of the certificate.</span></span>   

<span data-ttu-id="84765-157">와일드 카드 지원은 [RFC 2818, 섹션 3.1](https://tools.ietf.org/html/rfc2818#section-3.1)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-157">The support for wildcards is described in [RFC 2818, section 3.1](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="84765-158">개발</span><span class="sxs-lookup"><span data-stu-id="84765-158">Specifically:</span></span>

<span data-ttu-id="84765-159">*"이름에는 단일 도메인 이름 \* 구성 요소 또는 구성 요소 조각과 일치 하는 것으로 간주 되는 와일드 카드 문자가 포함 될 수 있습니다. 예: a.com \*는 foo.a.com와 일치 하지만 bar.foo.a.com는 그렇지 않습니다. \*foo.com는 일치 하지만 bar.com는 그렇지 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="84765-159">*"Names may contain the wildcard character \* which is considered to match any single domain name component or component fragment. E.g., \*.a.com matches foo.a.com but not bar.foo.a.com. f\*.com matches foo.com but not bar.com."*</span></span>

<span data-ttu-id="84765-160">SIP 메시지에 표시 된 연락처 머리글에 두 개 이상의 값이 SBC에 의해 전송 되는 경우 연락처 머리글의 첫 번째 값에 대 한 FQDN 부분만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-160">If more than one value in the Contact header presented in a SIP message is sent by the SBC, only the FQDN portion of the first value of the Contact header is used.</span></span>

#### <a name="request-uri"></a><span data-ttu-id="84765-161">요청 URI</span><span class="sxs-lookup"><span data-stu-id="84765-161">Request-URI</span></span> 

<span data-ttu-id="84765-162">들어오는 모든 통화에 대해 요청 URI를 사용 하 여 전화 번호를 사용자와 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="84765-162">For all incoming calls, the Request-URI is used to match the phone number to a user.</span></span>   

<span data-ttu-id="84765-163">현재 전화 번호는 다음 예와 같이 더하기 기호 (+)를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-163">Currently The phone number must contain a plus sign (+) as shown in the following example.</span></span> 

```
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a><span data-ttu-id="84765-164">연락처 및 레코드 경로 헤더 고려 사항</span><span class="sxs-lookup"><span data-stu-id="84765-164">Contact and Record-Route headers considerations</span></span>

<span data-ttu-id="84765-165">SIP 프록시는 새로운 대화 상자 클라이언트 트랜잭션 (예: Bye 또는 재 초대)에 대해 다음 홉 FQDN을 계산 해야 하며 SIP 옵션에 회신할 때</span><span class="sxs-lookup"><span data-stu-id="84765-165">The SIP proxy needs to calculate the next hop FQDN for new in-dialog client transactions (for example Bye or Re-Invite), and when replying to SIP Options.</span></span> <span data-ttu-id="84765-166">연락처 또는 레코드 경로가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-166">Either Contact or Record-Route are used.</span></span> 

<span data-ttu-id="84765-167">RFC 3261에 따르면 새 대화를 만들 수 있는 모든 요청에 대해 Contact 헤더가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-167">According to RFC 3261, Contact header is required in any request that can result in a new dialog.</span></span> <span data-ttu-id="84765-168">레코드 경로는 프록시에서 대화에 대 한 향후 요청 경로를 유지 하려는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-168">The Record-Route is only required if a proxy wants to stay on the path of future requests in a dialog.</span></span> 

<span data-ttu-id="84765-169">다음과 같은 이유로 인해 연락처 머리글만 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-169">Microsoft recommends using only Contact header for the following reasons:</span></span>

- <span data-ttu-id="84765-170">RFC 3261에서 레코드는 프록시에서 대화에 대 한 향후 요청 경로를 유지 하려는 경우에 사용 되며,이는 모든 트래픽이 Microsoft SIP 프록시와 페어링된 SBC 사이에서 진행 됨에 따라 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="84765-170">Per RFC 3261, Record-Route is used if a proxy wants to stay on the path of future requests in a dialog, which is not essential as all traffic goes between the Microsoft SIP proxy and the paired SBC.</span></span> <span data-ttu-id="84765-171">SBC와 Microsoft SIP 프록시 사이에는 중간 프록시 서버가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-171">There is no need for an intermediate proxy server between the SBC and Microsoft SIP proxy.</span></span>

- <span data-ttu-id="84765-172">Microsoft SIP 프록시는 아웃 바운드 ping 옵션을 보낼 때 다음 홉을 결정 하는 데 레코드 경로가 아닌 대화 상대 머리글만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-172">The Microsoft SIP proxy uses only Contact header (not Record-Route) to determine the next hop when sending outbound ping Options.</span></span> <span data-ttu-id="84765-173">2 (연락처 및 레코드 경로) 대신 매개 변수 (Contact) 하나만 구성 하면 관리가 간단해 집니다.</span><span class="sxs-lookup"><span data-stu-id="84765-173">Configuring only one parameter (Contact) instead of two (Contact and Record-Route) simplifies the administration.</span></span>

<span data-ttu-id="84765-174">다음 홉을 계산 하기 위해 SIP 프록시는 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-174">To calculate the next hop, the SIP proxy uses:</span></span>

- <span data-ttu-id="84765-175">우선 순위 1</span><span class="sxs-lookup"><span data-stu-id="84765-175">Priority 1.</span></span> <span data-ttu-id="84765-176">최상위 수준 레코드 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="84765-176">Top-level Record-Route.</span></span> <span data-ttu-id="84765-177">최상위 레코드 경로에 FQDN 이름 또는 IP가 포함 되어 있으면 FQDN 이름 또는 IP를 사용 하 여 아웃 바운드 대화 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84765-177">If the top-level Record-Route contains the FQDN name or IP, the FQDN name or IP is used to make the outbound in-dialog connection.</span></span>

- <span data-ttu-id="84765-178">우선 순위 2.</span><span class="sxs-lookup"><span data-stu-id="84765-178">Priority 2.</span></span> <span data-ttu-id="84765-179">연락처 머리글.</span><span class="sxs-lookup"><span data-stu-id="84765-179">Contact header.</span></span> <span data-ttu-id="84765-180">레코드 경로가 없는 경우 SIP 프록시는 연락처 헤더의 값을 조회 하 여 아웃 바운드 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84765-180">If Record-Route does not exist, the SIP proxy will look up the value of the Contact header to make the outbound connection.</span></span> <span data-ttu-id="84765-181">(이것은 권장 되는 구성입니다.)</span><span class="sxs-lookup"><span data-stu-id="84765-181">(This is the recommended configuration.)</span></span>

<span data-ttu-id="84765-182">연락처 및 레코드 경로를 모두 사용 하는 경우 SBC 관리자는 값을 동일 하 게 유지 해야 하므로 관리 오버 헤드가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-182">If both Contact and Record-Route are used, the SBC administrator must keep their values identical, which causes administrative overhead.</span></span> 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a><span data-ttu-id="84765-183">연락처 또는 레코드 경로에 FQDN 이름 사용</span><span class="sxs-lookup"><span data-stu-id="84765-183">Use of FQDN name in Contact or Record-Route</span></span>

<span data-ttu-id="84765-184">IP 주소 사용은 레코드 경로 또는 연락처에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-184">Use of an IP address is not supported in either Record-Route or Contact.</span></span> <span data-ttu-id="84765-185">유일 하 게 지원 되는 옵션은 SBC 인증서의 일반 이름 또는 주체 대체 이름과 일치 해야 하는 FQDN입니다 (인증서의 와일드 카드 값이 지원 됨).</span><span class="sxs-lookup"><span data-stu-id="84765-185">The only supported option is an FQDN, which must match either the Common Name or Subject Alternative Name of the SBC certificate (wildcard values in the certificate are supported).</span></span>

- <span data-ttu-id="84765-186">IP 주소가 레코드 경로 또는 연락처에 표시 되는 경우 인증서 검사에 실패 하 고 통화가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-186">If an IP address is presented in Record-route or Contact, the certificate check fails and the call fails.</span></span>

- <span data-ttu-id="84765-187">FQDN이 제시 된 인증서의 공통 또는 주체 대체 이름 값과 일치 하지 않으면 통화에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-187">If the FQDN does not match the value of the Common or Subject Alternative Name in the presented certificate, the call fails.</span></span> 

## <a name="inbound-call-sip-dialog-description"></a><span data-ttu-id="84765-188">인바운드 통화: SIP 대화 상자 설명</span><span class="sxs-lookup"><span data-stu-id="84765-188">Inbound call: SIP dialog description</span></span>

<span data-ttu-id="84765-189">다음 표에는 비 바이패스 및 우회 모드의 호출 흐름 차이 및 유사성에 대 한 요약이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-189">The following table below summarizes the call flow differences and similarities between non-bypass and bypass modes:</span></span>

| <span data-ttu-id="84765-190">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="84765-190">Parameter name</span></span> | <span data-ttu-id="84765-191">비 바이패스 모드</span><span class="sxs-lookup"><span data-stu-id="84765-191">Non-bypass mode</span></span> | <span data-ttu-id="84765-192">우회 모드</span><span class="sxs-lookup"><span data-stu-id="84765-192">Bypass mode</span></span>
| :---------------------  |:---------------------- |:----------------|
| <span data-ttu-id="84765-193">183 및 200 메시지의 미디어 후보자는 다음에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-193">Media candidates in 183 and 200 messages coming from</span></span> | <span data-ttu-id="84765-194">미디어 프로세서</span><span class="sxs-lookup"><span data-stu-id="84765-194">Media processors</span></span> | <span data-ttu-id="84765-195">클라이언트</span><span class="sxs-lookup"><span data-stu-id="84765-195">Clients</span></span> | 
| <span data-ttu-id="84765-196">SBC에서 받을 수 있는 183 메시지 수</span><span class="sxs-lookup"><span data-stu-id="84765-196">Number of 183 messages SBC can receive</span></span> | <span data-ttu-id="84765-197">세션 당 하나</span><span class="sxs-lookup"><span data-stu-id="84765-197">One per session</span></span> | <span data-ttu-id="84765-198">개인</span><span class="sxs-lookup"><span data-stu-id="84765-198">Multiple</span></span> | 
| <span data-ttu-id="84765-199">Provisional answer를 사용 하 여 통화를 할 수 있습니다 (183).</span><span class="sxs-lookup"><span data-stu-id="84765-199">Call can be with provisional answer (183)</span></span> | <span data-ttu-id="84765-200">예</span><span class="sxs-lookup"><span data-stu-id="84765-200">Yes</span></span> | <span data-ttu-id="84765-201">예</span><span class="sxs-lookup"><span data-stu-id="84765-201">Yes</span></span> |
| <span data-ttu-id="84765-202">Provisional 응답을 받지 않고 통화할 수 있음 (183)</span><span class="sxs-lookup"><span data-stu-id="84765-202">Call can be without provisional answer (183)</span></span> | <span data-ttu-id="84765-203">예</span><span class="sxs-lookup"><span data-stu-id="84765-203">Yes</span></span> | <span data-ttu-id="84765-204">예</span><span class="sxs-lookup"><span data-stu-id="84765-204">Yes</span></span> |

###  <a name="non-media-bypass-flow"></a><span data-ttu-id="84765-205">비 미디어 바이패스 흐름</span><span class="sxs-lookup"><span data-stu-id="84765-205">Non-media bypass flow</span></span>

<span data-ttu-id="84765-206">팀 사용자는 동시에 여러 끝점을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-206">A Teams user might have multiple endpoints at the same time.</span></span> <span data-ttu-id="84765-207">예를 들어 Windows 클라이언트용 팀, iPhone 용 팀 클라이언트, 팀 전화 (팀 Android 클라이언트).</span><span class="sxs-lookup"><span data-stu-id="84765-207">For example, Teams for Windows client, Teams for iPhone client, and Teams Phone (Teams Android client).</span></span> <span data-ttu-id="84765-208">각 끝점은 다음과 같이 HTTP 나머지에 신호를 보낼 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-208">Each endpoint might signal an HTTP rest as follows:</span></span>

-   <span data-ttu-id="84765-209">통화 진행 중 – SIP 프록시에서 SIP 메시지 180로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-209">Call progress – converted by the SIP proxy to the SIP message 180.</span></span> <span data-ttu-id="84765-210">메시지 180 수신 시 SBC는 로컬 신호음을 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-210">On receiving message 180, the SBC must generate local ringing.</span></span>

-   <span data-ttu-id="84765-211">미디어 응답 – SDP (세션 설명 프로토콜)에서 미디어 후보가 있는 메시지 183로 SIP 프록시에서 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-211">Media answer – converted by the SIP proxy to message 183 with media candidates in Session Description Protocol (SDP).</span></span> <span data-ttu-id="84765-212">메시지 183 수신 시 SBC는 SDP 메시지에서 받은 미디어 후보자에 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-212">On receiving message 183, the SBC expects to connect to the media candidates received in the SDP message.</span></span> <span data-ttu-id="84765-213">일부 경우에는 미디어 대답이 생성 되지 않을 수 있으며, 끝점은 "통화 수락" 메시지와 함께 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-213">Note that in some cases the Media answer might not be generated, and the end point might answer with “Call Accepted” message.</span></span>

-   <span data-ttu-id="84765-214">통화 수락 – SIP 프록시에서 SDP로 SIP 메시지 200으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-214">Call accepted – converted by the SIP proxy to SIP message 200 with SDP.</span></span> <span data-ttu-id="84765-215">메시지 200을 받을 때 SBC는 제공 된 SDP 후보자에 미디어를 보내고 받을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-215">On receiving message 200, the SBC is expected to send and receive media to and from the provided SDP candidates.</span></span>

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a><span data-ttu-id="84765-216">Provisional answer로 벨이 여러 끝점</span><span class="sxs-lookup"><span data-stu-id="84765-216">Multiple endpoints ringing with provisional answer</span></span>

1.  <span data-ttu-id="84765-217">SBC에서 첫 번째 초대를 받을 때 SIP 프록시는 "SIP SIP/2.0 100 시도 중" 메시지를 보내고 수신 전화에 대 한 모든 최종 사용자 끝점에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="84765-217">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="84765-218">알림을 받으면 각 끝점은 링을 시작 하 고 "통화 진행" 메시지를 SIP 프록시로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="84765-218">Upon notification, each endpoint will start ringing and sending "Call progress” messages to the SIP proxy.</span></span> <span data-ttu-id="84765-219">팀 사용자는 여러 끝점을 가질 수 있으므로 SIP 프록시는 여러 통화 진행 상황 메시지를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-219">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="84765-220">클라이언트에서 수신 되는 모든 통화 진행 상태 메시지에 대해 SIP 프록시는 통화 진행 상황 메시지를 SIP 메시지 "SIP SIP/2.0 180 시도"로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-220">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span> <span data-ttu-id="84765-221">이러한 메시지를 보내는 간격은 호출 컨트롤러에서 받는 메시지의 간격에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-221">The interval for sending such messages is defined by the interval of the receiving messages from the Call Controller.</span></span> <span data-ttu-id="84765-222">다음 다이어그램에는 SIP 프록시에서 생성 된 2 180 메시지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-222">In the following diagram, there are two 180 messages generated by the SIP proxy.</span></span> <span data-ttu-id="84765-223">이러한 메시지는 사용자의 두 팀 끝점에서 발송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-223">These messages come from the two Teams endpoints of the user.</span></span> <span data-ttu-id="84765-224">각 클라이언트에는 고유한 태그 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-224">The clients each have a unique Tag ID.</span></span>  <span data-ttu-id="84765-225">다른 끝점에서 오는 모든 메시지는 별도의 세션입니다 ("To" 필드의 "tag" 매개 변수는 달라 집니다).</span><span class="sxs-lookup"><span data-stu-id="84765-225">Every message coming from a different endpoint will be a separate session (the parameter “tag” in the “To” field will be different).</span></span> <span data-ttu-id="84765-226">그러나 끝점은 다음 다이어그램에 나와 있는 것 처럼 메시지 180을 생성 하 고 메시지 183을 바로 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-226">But an endpoint might not generate message 180 and send message 183 right away as shown in the following diagram.</span></span>

4.  <span data-ttu-id="84765-227">끝점에서 끝점의 미디어 후보의 IP 주소를 사용 하 여 미디어 응답 메시지를 생성 한 후에는 SIP 프록시에서 받은 메시지를 클라이언트의 SDP가 미디어 프로세서의 SDP로 대체 하 여 "SIP 183 세션 진행 중" 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-227">Once an endpoint generates a Media Answer message with the IP addresses of endpoint’s media candidates, the SIP proxy converts the message received to a "SIP 183 Session Progress" message with the SDP from the client replaced by the SDP from the Media Processor.</span></span> <span data-ttu-id="84765-228">다음 다이어그램에서 포크 2의 끝점은 호출에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-228">In the following diagram, the endpoint from Fork 2 answered the call.</span></span> <span data-ttu-id="84765-229">트렁크가 바이패스 되지 않으면 183 SIP 메시지가 한 번만 생성 됩니다 (링 봇 또는 클라이언트 끝점).</span><span class="sxs-lookup"><span data-stu-id="84765-229">If the trunk is non-bypassed, the 183 SIP message is generated only once (either Ring Bot or Client End Point).</span></span> <span data-ttu-id="84765-230">183이 기존 포크에 도달 하거나 새를 시작할 때가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-230">The 183 might come on an existing fork or start a new one.</span></span>

5.  <span data-ttu-id="84765-231">통화 수락 메시지는 통화를 수락 하는 끝점의 최종 후보자와 함께 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-231">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="84765-232">통화 수락 메시지가 SIP 메시지 200로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-232">The Call Acceptance message is converted to SIP message 200.</span></span> 

![Provisional answer로 벨이 되는 여러 끝점을 보여 주는 다이어그램](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a><span data-ttu-id="84765-234">Provisional 응답 없이 여러 끝점을 벨 울림</span><span class="sxs-lookup"><span data-stu-id="84765-234">Multiple endpoints ringing without provisional answer</span></span>

1.  <span data-ttu-id="84765-235">SBC에서 첫 번째 초대를 받을 때 SIP 프록시는 "SIP SIP/2.0 100 시도 중" 메시지를 보내고 수신 전화에 대 한 모든 최종 사용자 끝점에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="84765-235">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="84765-236">알림을 받으면 각 끝점은 링을 시작 하 고 메시지 "호출 진행"을 SIP 프록시로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="84765-236">Upon notification, each endpoint will start ringing and sending the message "Call progress” to the SIP proxy.</span></span> <span data-ttu-id="84765-237">팀 사용자는 여러 끝점을 가질 수 있으므로 SIP 프록시는 여러 통화 진행 상황 메시지를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-237">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="84765-238">클라이언트에서 수신 되는 모든 통화 진행 상태 메시지에 대해 SIP 프록시는 통화 진행 상황 메시지를 SIP 메시지 "SIP SIP/2.0 180 시도"로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-238">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span>  <span data-ttu-id="84765-239">메시지를 보내는 간격은 호출 컨트롤러에서 메시지를 받는 간격으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-239">The interval for sending the messages is defined by the interval of receiving the messages from the Call Controller.</span></span> <span data-ttu-id="84765-240">아래 그림에는 SIP 프록시에서 생성 된 2 180 메시지가 있으며,이는 사용자가 세 개의 팀 클라이언트에 로그인 하 여 각 클라이언트가 호출 진행 상황을 보내도록 하 고 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-240">On the picture below there are two 180 messages generated by the SIP proxy, meaning that user logged into three Teams clients and each client send the call progress.</span></span> <span data-ttu-id="84765-241">모든 메시지는 별도의 세션으로 지정 됩니다 ("To" 필드의 "tag" 매개 변수는 다름).</span><span class="sxs-lookup"><span data-stu-id="84765-241">Every message will be a separate session (parameter “tag” in “To” field is different)</span></span>

4.  <span data-ttu-id="84765-242">통화 수락 메시지는 통화를 수락 하는 끝점의 최종 후보자와 함께 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-242">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="84765-243">통화 수락 메시지가 SIP 메시지 200로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-243">The Call Acceptance message is converted to SIP message 200.</span></span> 

![여러 끝점을 표시 하는 다이어그램 provisional answer 없이 신호음](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a><span data-ttu-id="84765-245">미디어 우회 흐름</span><span class="sxs-lookup"><span data-stu-id="84765-245">Media bypass flow</span></span>

<span data-ttu-id="84765-246">미디어 바이패스 시나리오에는 동일한 메시지 (100 시도, 180, 183)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-246">The same messages (100 Trying, 180, 183) are used in the media bypass scenario.</span></span> 

<span data-ttu-id="84765-247">아래 스키마는 호출 흐름 바이패스의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84765-247">The schema below shows an example of the bypass call flow.</span></span> <span data-ttu-id="84765-248">미디어 후보는 여러 끝점에서 생성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-248">Note that the media candidates can come from different endpoints.</span></span> 

![Provisional answer로 벨이 되는 여러 끝점을 보여 주는 다이어그램](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a><span data-ttu-id="84765-250">옵션 바꾸기</span><span class="sxs-lookup"><span data-stu-id="84765-250">Replaces option</span></span>

<span data-ttu-id="84765-251">SBC는 대체와의 초대를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-251">The SBC must support Invite with Replaces.</span></span>

## <a name="size-of-sdp-considerations"></a><span data-ttu-id="84765-252">SDP 고려 사항 크기</span><span class="sxs-lookup"><span data-stu-id="84765-252">Size of SDP considerations</span></span>

<span data-ttu-id="84765-253">다이렉트 라우팅 인터페이스는 1500 바이트를 초과 하는 SIP 메시지를 보낼 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-253">The Direct Routing interface might send a SIP message exceeding 1,500 bytes.</span></span>  <span data-ttu-id="84765-254">SDP 크기는 주로이를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="84765-254">The size of SDP primarily causes this.</span></span> <span data-ttu-id="84765-255">그러나 SBC 뒤에 UDP 트렁크가 있는 경우에는 Microsoft SIP 프록시에서 수정 되지 않은 트렁크로 전달 되는 경우 메시지를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-255">However, if there is a UDP trunk behind the SBC, it might reject the message if it is forwarded from the Microsoft SIP proxy to the trunk unmodified.</span></span> <span data-ttu-id="84765-256">UDP trunks에 메시지를 보낼 때 SBC에서 일부 값을 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-256">Microsoft recommends stripping some values in SDP on the SBC when sending the message to the UDP trunks.</span></span> <span data-ttu-id="84765-257">예를 들어, 아이스 후보자 또는 사용 하지 않는 코덱이 제거 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-257">For example, the ICE candidates or unused codecs can be removed.</span></span>

## <a name="call-transfer"></a><span data-ttu-id="84765-258">통화 전달</span><span class="sxs-lookup"><span data-stu-id="84765-258">Call transfer</span></span>

<span data-ttu-id="84765-259">다이렉트 라우팅은 두 가지 통화 전달 방법을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-259">Direct Routing supports two methods for call transfer:</span></span>

- <span data-ttu-id="84765-260">옵션 1.</span><span class="sxs-lookup"><span data-stu-id="84765-260">Option 1.</span></span> <span data-ttu-id="84765-261">SIP 프록시 프로세스는 클라이언트에서 로컬로 참조 하 고 RFC 3892 섹션 7.1의 설명에 따라 Referee 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-261">SIP proxy processes Refer from the client locally and acts as a Referee as described in section 7.1 of RFC 3892.</span></span>

  <span data-ttu-id="84765-262">이 옵션을 사용 하면 SIP 프록시가 전송을 종료 하 고 새 초대를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-262">With this option, the SIP proxy terminates the transfer and adds a new Invite.</span></span> 


- <span data-ttu-id="84765-263">옵션 2.</span><span class="sxs-lookup"><span data-stu-id="84765-263">Option 2.</span></span> <span data-ttu-id="84765-264">SIP 프록시는 SBC에 대 한 참조를 보내고, 전송 역할을 하거나, RFC 5589 섹션 6에서 설명 하는 방법으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-264">SIP proxy sends the Refer to the SBC and acts as a Transferor as describing in Section 6 of RFC 5589.</span></span>

  <span data-ttu-id="84765-265">이 옵션을 사용 하는 경우 SIP 프록시는 SBC에 대 한 참조를 보내고 SBC가 전송을 완전히 처리 하도록 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-265">With this option, the SIP proxy sends a Refer to the SBC and expects the SBC to handle the Transfer fully.</span></span>

<span data-ttu-id="84765-266">SIP 프록시는 SBC에서 보고 하는 기능을 기반으로 메서드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-266">The SIP proxy selects the method based on the capabilities reported by the SBC.</span></span> <span data-ttu-id="84765-267">SBC에서 "참조" 메서드를 지원 한다고 표시 하는 경우 SIP 프록시는 통화 전송에 옵션 2를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-267">If the SBC indicates that it supports the method “Refer”, the SIP proxy will use Option 2 for call transfers.</span></span>

<span data-ttu-id="84765-268">다음은 참조 메서드가 지원 됨을 나타내는 메시지를 보내는 SBC의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="84765-268">The following is an example of an SBC sending the message that the Refer method is supported:</span></span>

```
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

<span data-ttu-id="84765-269">SBC에서 지원 되는 메서드를 참조 하는 것으로 표시 되지 않으면 직접 라우팅이 옵션 1 (SIP 프록시 역할을 하는 Referee)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-269">If the SBC doesn’t indicate that Refer as a supported method, Direct Routing will use Option 1 (SIP proxy acts as a Referee) .</span></span> <span data-ttu-id="84765-270">SBC는 또한 Notify 메서드를 지원 한다는 신호를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-270">The SBC  must also signal that it supports the Notify method:</span></span>

<span data-ttu-id="84765-271">참조 메서드가 지원 되지 않음을 나타내는 SBC의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="84765-271">Example of SBC indicating that Refer method is not supported:</span></span>

```
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a><span data-ttu-id="84765-272">SIP 프록시 프로세스는 클라이언트에서 로컬로 참조 하 고 Referee 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-272">SIP proxy processes Refer from the client locally and acts as a Referee</span></span>

<span data-ttu-id="84765-273">SBC에서 참조 메서드가 지원 되지 않는 것으로 표시 되는 경우 SIP 프록시는 Referee 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-273">If the SBC indicated that the Refer method is not supported, the SIP proxy acts as a Referee.</span></span> 

<span data-ttu-id="84765-274">클라이언트에서 들어오는 참조 요청이 SIP 프록시에서 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-274">The Refer request that comes from the client will be terminated on the SIP proxy.</span></span> <span data-ttu-id="84765-275">(클라이언트의 참조 요청은 다음 다이어그램에서 "Dave에 대 한 통화 전환"으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-275">(The Refer request from the client is shown as “Call transfer to Dave” in the following diagram.</span></span>  <span data-ttu-id="84765-276">자세한 내용은 [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)의 섹션 7.1을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84765-276">For more information, see section 7.1 of [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt).</span></span> 

![Provisional answer로 벨이 되는 여러 끝점을 보여 주는 다이어그램](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a><span data-ttu-id="84765-278">SIP 프록시는 SBC에 대 한 참조를 보내고 전송 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-278">SIP proxy send the Refer to the SBC and acts as a Transferor</span></span>

<span data-ttu-id="84765-279">이것은 통화 전송에 가장 적합 한 방법으로, 미디어 바이패스 인증을 찾는 장치에 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="84765-279">This is the preferred method for call transfers, and it is mandatory for devices seeking media bypass certification.</span></span> <span data-ttu-id="84765-280">미디어 바이패스 모드에서는 SBC가 지원 되지 않는 경우에도 통화 전송이 참조를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-280">Call Transfer without the SBC being able to handle Refer is not supported in media bypass mode.</span></span> 

<span data-ttu-id="84765-281">표준은 RFC 5589 섹션 6에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-281">The standard is explained in Section 6 of RFC 5589.</span></span> <span data-ttu-id="84765-282">관련 Rfc는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-282">The related RFCs are:</span></span>

- [<span data-ttu-id="84765-283">SIP (세션 초기화 프로토콜) 통화 제어-전송</span><span class="sxs-lookup"><span data-stu-id="84765-283">Session Initiation Protocol (SIP) Call Control - Transfer</span></span>](https://tools.ietf.org/html/rfc5589)

- [<span data-ttu-id="84765-284">SIP (세션 시작 프로토콜) "대체" 머리글</span><span class="sxs-lookup"><span data-stu-id="84765-284">Session Initiation Protocol (SIP) "Replaces" Header</span></span>](https://tools.ietf.org/html/rfc3891)

- [<span data-ttu-id="84765-285">SIP (세션 시작 프로토콜) "참조 하는" 메커니즘</span><span class="sxs-lookup"><span data-stu-id="84765-285">Session Initiation Protocol (SIP) "Referred-By" mechanism</span></span>](https://tools.ietf.org/html/rfc3892)

<span data-ttu-id="84765-286">이 옵션은 SIP 프록시가 전송 역할을 하는 것으로 가정 하 고 SBC에 대 한 참조 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="84765-286">This option assumes that the SIP proxy acts as a Transferor and sends a Refer message to the SBC.</span></span> <span data-ttu-id="84765-287">SBC는 Transferee 역할을 하 고, 전송에 대 한 새 제안 생성을 위한 참조를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-287">The SBC acts as a Transferee and handles the Refer to generate a new offer for transfer.</span></span> <span data-ttu-id="84765-288">다음과 같은 두 가지 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-288">There are two possible cases:</span></span>

- <span data-ttu-id="84765-289">통화가 외부 PSTN 참여자로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-289">The call is transferred to an external PSTN participant.</span></span> 
- <span data-ttu-id="84765-290">통화는 한 팀 사용자에서 SBC를 통해 동일한 테 넌 트의 다른 팀 사용자에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-290">The call is transferred from one Teams user to another Teams user in the same tenant via the SBC.</span></span> 

<span data-ttu-id="84765-291">호출을 SBC를 통해 한 팀 사용자에 게 전달 하는 경우 SBC는 참조 메시지에서 받은 정보를 사용 하 여 전송 대상 (팀 사용자)에 대해 새 초대 (새 대화 상자 시작)를 발행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-291">If the call is transferred from one Teams user to another via the SBC, the SBC is expected to issue a new invite (start a new dialog) for the transfer target (the Teams user) using the information received in the Refer message.</span></span> 

<span data-ttu-id="84765-292">요청 거래에 대 한 To/전송 또는 필드를 내부적으로 채우려면 SIP 프록시는 참조/참조로 헤더 내에이 정보를 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-292">To populate the To/Transferor fields for the transaction of the request internally, the SIP proxy needs to convey this information  inside the REFER-TO/REFERRED-BY headers.</span></span> 

<span data-ttu-id="84765-293">SIP 프록시는 호스트 이름 및 다음 중 하나의 sip 프록시 FQDN으로 구성 된 SIP URI로 참조를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-293">The SIP proxy will form the REFER-TO as a SIP URI comprised of a SIP proxy FQDN in the hostname and either one of the following:</span></span>

- <span data-ttu-id="84765-294">전송 대상이 전화 번호에 해당 하는 경우 URI의 사용자 이름 부분에 있는 전자 164 개의 전화 번호이 고,</span><span class="sxs-lookup"><span data-stu-id="84765-294">An E.164 phone number in the username part of the URI in case the transfer target is a phone number, or</span></span>

- <span data-ttu-id="84765-295">x-m 및 x-t 매개 변수는 각각 전체 전송 대상 MRI 및 테 넌 트 ID를 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-295">x-m and x-t parameters encoding the full transfer target MRI and tenant ID respectively</span></span> 

<span data-ttu-id="84765-296">참조 헤더는 다음 표에 나와 있는 것 처럼 전송 또는 테 넌 트 ID 및 기타 전달 컨텍스트 매개 변수를 포함 하는 SIP URI (전송 또는 MRI가 인코딩된)입니다.</span><span class="sxs-lookup"><span data-stu-id="84765-296">The REFERRED-BY header is a SIP URI with transferor MRI encoded in it as well as transferor tenant ID and other transfer context parameters as shown in the following table:</span></span>

| <span data-ttu-id="84765-297">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84765-297">Parameter</span></span> | <span data-ttu-id="84765-298">값</span><span class="sxs-lookup"><span data-stu-id="84765-298">Value</span></span> | <span data-ttu-id="84765-299">설명</span><span class="sxs-lookup"><span data-stu-id="84765-299">Description</span></span> |  
|:---------------------  |:---------------------- |:---------------------- |
| <span data-ttu-id="84765-300">x-m</span><span class="sxs-lookup"><span data-stu-id="84765-300">x-m</span></span> | <span data-ttu-id="84765-301">MRI</span><span class="sxs-lookup"><span data-stu-id="84765-301">MRI</span></span> | <span data-ttu-id="84765-302">참조로 채워진 전송 또는 대상의 전체 MRI</span><span class="sxs-lookup"><span data-stu-id="84765-302">Full MRI of transferor/transfer target as populated by CC</span></span> |
| <span data-ttu-id="84765-303">x-t</span><span class="sxs-lookup"><span data-stu-id="84765-303">x-t</span></span> | <span data-ttu-id="84765-304">테 넌 트 ID</span><span class="sxs-lookup"><span data-stu-id="84765-304">Tenant ID</span></span> | <span data-ttu-id="84765-305">x-t 테 넌 트 ID 선택적 테 넌 트의 입력</span><span class="sxs-lookup"><span data-stu-id="84765-305">x-t Tenant ID Optional Tenant Id as populated by CC</span></span> |
| <span data-ttu-id="84765-306">x ti</span><span class="sxs-lookup"><span data-stu-id="84765-306">x-ti</span></span> | <span data-ttu-id="84765-307">전송 또는 상관 관계 Id</span><span class="sxs-lookup"><span data-stu-id="84765-307">Transferor Correlation Id</span></span> | <span data-ttu-id="84765-308">전송 전화에 대 한 통화의 상관 관계 Id 또는</span><span class="sxs-lookup"><span data-stu-id="84765-308">Correlation Id of the call to the transferor</span></span> |
| <span data-ttu-id="84765-309">x-tt</span><span class="sxs-lookup"><span data-stu-id="84765-309">x-tt</span></span> | <span data-ttu-id="84765-310">전송 대상 통화 URI</span><span class="sxs-lookup"><span data-stu-id="84765-310">Transfer target call URI</span></span> | <span data-ttu-id="84765-311">인코딩된 호출 대체 URI</span><span class="sxs-lookup"><span data-stu-id="84765-311">Encoded call replacement URI</span></span> |

<span data-ttu-id="84765-312">이 경우에는 참조 헤더의 크기가 최대 400 기호가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-312">The size of the Refer Header can be up to 400 symbols in this case.</span></span> <span data-ttu-id="84765-313">SBC는 크기를 최대 400 기호까지 포함 하는 처리 참조 메시지를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-313">The SBC must support handling Refer messages with size up to 400 symbols.</span></span>

![Provisional answer로 벨이 되는 여러 끝점을 보여 주는 다이어그램](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a><span data-ttu-id="84765-315">세션 타이머</span><span class="sxs-lookup"><span data-stu-id="84765-315">Session timer</span></span>

<span data-ttu-id="84765-316">SIP 프록시는 비 바이패스 호출에서 세션 타이머를 지원 하 고 우회 통화에서 제공 하지는 않습니다 (항상 제공).</span><span class="sxs-lookup"><span data-stu-id="84765-316">The SIP proxy supports (always offers) the Session Timer on non-bypass calls but does not offer it on bypass calls.</span></span> <span data-ttu-id="84765-317">SBC에서 세션 타이머를 사용 하는 것은 필수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="84765-317">Use of the Session Timer by the SBC is not mandatory.</span></span>

##  <a name="use-of-request-uri-parameter-userphone"></a><span data-ttu-id="84765-318">요청 URI 매개 변수 user = phone 사용</span><span class="sxs-lookup"><span data-stu-id="84765-318">Use of Request-URI parameter user=phone</span></span>

<span data-ttu-id="84765-319">SIP 프록시는 요청 URI를 분석 하 고 사용자 i p i i a p i i a i a i a i a i a i a i a i a i이 있는</span><span class="sxs-lookup"><span data-stu-id="84765-319">The SIP proxy analyses the Request-URI and if the parameter user=phone is present, the service will handle the Request-URI as a phone number, matching the number to a user.</span></span> <span data-ttu-id="84765-320">매개 변수가 표시 되지 않는 경우 SIP 프록시는 요청 URI 사용자 형식 (전화 번호 또는 SIP 주소)을 확인 하기 위해 추론을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-320">If parameter is not present the SIP proxy applies heuristics to determine  the Request-URI user type (phone number or a SIP address).</span></span>

<span data-ttu-id="84765-321">Microsof는 항상 사용자 = phone 매개 변수를 적용 하 여 전화 설정 프로세스를 간소화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-321">Microsof recommends always applying the user=phone parameter to simplify the call setup process.</span></span>

## <a name="history-info-header"></a><span data-ttu-id="84765-322">기록-정보 헤더</span><span class="sxs-lookup"><span data-stu-id="84765-322">History-Info header</span></span>

<span data-ttu-id="84765-323">History-정보 헤더는 대상 변경 SIP 요청에 사용 되며 "네트워크 및 최종 사용자를 위해 다양 한 서비스를 사용 하도록 요청 기록 정보를 캡처하기 위한 표준 메커니즘을 제공 합니다."</span><span class="sxs-lookup"><span data-stu-id="84765-323">The History-Info header is used for retargeting SIP requests and “provide(s) a standard mechanism for capturing the request history information to enable a wide variety of services for networks and end-users.”</span></span> <span data-ttu-id="84765-324">자세한 내용은 [RFC 4244-섹션 1.1](http://www.ietf.org/rfc/rfc4244.txt)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84765-324">For more information, see [RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt).</span></span> <span data-ttu-id="84765-325">Microsoft 전화 시스템의 경우이 헤더는 Simulring 및 착신 전환 시나리오에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-325">For Microsoft Phone System, this header is used in Simulring and Call Forwarding scenarios.</span></span>  

<span data-ttu-id="84765-326">보내는 경우 기록 정보는 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-326">If sending, the History-Info is enabled as follows:</span></span>

- <span data-ttu-id="84765-327">SIP 프록시는 PSTN 컨트롤러로 전송 되는 기록 정보 헤더를 구성 하는 개별 기록 정보 항목에 연결 된 전화 번호를 포함 하는 매개 변수를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-327">The SIP proxy will insert a parameter containing the associated phone number in individual History-Info entries that comprise the History-Info header sent to the PSTN Controller.</span></span>  <span data-ttu-id="84765-328">전화 번호 매개 변수가 있는 항목만 사용 하 여 PSTN 컨트롤러는 새 기록-정보 헤더를 다시 작성 하 여 SIP 프록시를 통해 SIP 트렁크 공급자에 게 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-328">Using only entries that have the phone number parameter, the PSTN Controller will rebuild a new History-Info header, and pass it on to the SIP trunk provider via SIP proxy.</span></span>

- <span data-ttu-id="84765-329">기록-동시 연결 및 착신 전환 케이스에 대 한 정보 헤더가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-329">History-Info header will be added for simultaneous ring and call forwarding cases.</span></span>

- <span data-ttu-id="84765-330">통화 전달 서비스 케이스에 대 한 기록 정보 헤더가 추가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-330">History-Info header will not be added for call transfer cases.</span></span>

- <span data-ttu-id="84765-331">다시 구성 된 기록-정보 헤더의 개별 기록 항목에는 URI의 호스트 부분으로 sip.pstnhub.microsoft.com (직접 라우팅 FQDN) 집합과 함께 제공 된 전화 번호 매개 변수가 포함 됩니다. ' user = phone ' 매개 변수가 SIP URI의 일부로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-331">An individual history entry in the reconstructed History-Info header will have the phone number parameter provided combined with the Direct Routing FQDN (sip.pstnhub.microsoft.com) set as the host part of the URI; a parameter of ‘user=phone’ will be added as part of the SIP URI.</span></span>  <span data-ttu-id="84765-332">전화 컨텍스트 매개 변수를 제외 하 고 원래 기록 정보 헤더와 관련 된 다른 모든 매개 변수는 다시 생성 된 기록 정보 헤더에서 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-332">Any other parameters associated with the original History-Info header, except for phone context parameters, will be passed through in the re-constructed History-Info header.</span></span>  <span data-ttu-id="84765-333">개인 항목 (RFC 4244 섹션의 3.3에 정의 된 메커니즘에 따라 결정 됨)은 SIP 트렁크 공급자가 신뢰할 수 있는 피어 이기 때문에 그대로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-333">Note that entries that are private (as determined by the mechanisms defined in Section 3.3 of RFC 4244) will be forwarded as is because  the SIP trunk provider is a trusted peer.</span></span>

- <span data-ttu-id="84765-334">인바운드 기록-정보가 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-334">Inbound History-Info is ignored.</span></span>

<span data-ttu-id="84765-335">SIP 프록시에서 보낸 기록 정보 헤더의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-335">Following is the format of the History-info header sent by the SIP proxy:</span></span>

```
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

<span data-ttu-id="84765-336">통화가 여러 번 리디렉션되는 경우 모든 리디렉션에 대 한 정보는 시간 순서에 따라 적절 한 이유로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-336">If the call was redirected several times, information about every redirect is included with the appropriate reason in chronological order.</span></span>


<span data-ttu-id="84765-337">머리글 예:</span><span class="sxs-lookup"><span data-stu-id="84765-337">Header Example:</span></span>

```
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

<span data-ttu-id="84765-338">기록 정보는 필수 TLS 메커니즘으로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-338">The History-Info is protected by a mandatory TLS mechanism.</span></span> 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a><span data-ttu-id="84765-339">직접적인 라우팅 및 장애 조치 메커니즘에 대 한 SBC 연결</span><span class="sxs-lookup"><span data-stu-id="84765-339">SBC connection to Direct Routing and failover mechanism</span></span>

<span data-ttu-id="84765-340">[직접적인 라우팅 계획](direct-routing-plan.md#failover-mechanism-for-sip-signaling)의 SIP 신호에 대 한 장애 조치 메커니즘 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84765-340">See the section Failover mechanism for SIP signaling in [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).</span></span>

## <a name="retry-after"></a><span data-ttu-id="84765-341">다시 시도-이후</span><span class="sxs-lookup"><span data-stu-id="84765-341">Retry-After</span></span>

<span data-ttu-id="84765-342">직접 라우팅 데이터 센터가 사용 중인 경우 서비스는 SBC에 1 초 간격으로 다시 시도 후 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84765-342">If a Direct Routing datacenter is busy, the service can send a Retry-After message with a one-second interval to the SBC.</span></span> <span data-ttu-id="84765-343">다시 시도-After 헤더가 초대에 대 한 응답으로 SBC에서 503 메시지를 수신 하는 경우 SBC는 해당 연결을 종료 하 고 다음으로 제공 되는 Microsoft 데이터 센터를 시도해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-343">When the SBC receives a 503 message with a Retry-After header in response to an INVITE, the SBC must terminate that connection and try the next available Microsoft datacenter.</span></span> 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a><span data-ttu-id="84765-344">ICE 다시 시작: 미디어 바이패스를 지원 하지 않는 끝점으로 전송 된 미디어 건너뛰기 통화</span><span class="sxs-lookup"><span data-stu-id="84765-344">ICE Restart: Media bypass call transferred to an endpoint that does not support media bypass</span></span>

<span data-ttu-id="84765-345">이 SBC는 [RFC 5245, 섹션 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)에 설명 된 대로 ICE 다시 시작을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-345">The SBC must support ICE restarts as described in [RFC 5245, section 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span>

<span data-ttu-id="84765-346">직접 라우팅의 다시 시작은 RFC의 다음 단락에 따라 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84765-346">The restart in Direct Routing is implemented according to the following paragraphs of the RFC:</span></span>

<span data-ttu-id="84765-347">*ICE를 다시 시작 하려면 상담원은 제공의 미디어 스트림에 대 한 ice-ufrag 및 ice-고객을 모두 변경 해야 합니다.  한 가지 제안에 세션 수준 특성을 사용할 수 있지만, 이후 제안에서 동일한 ice-pwd 또는 ice-ufrag을 미디어 수준 특성으로 제공 합니다.  이는 암호가 변경 되지 않고, 표시 되는 변경만 발생 하며, ICE 다시 시작 되지는 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="84765-347">*To restart ICE, an agent MUST change both the ice-pwd and the ice-ufrag for the media stream in an offer.  Note that it is permissible to use a session-level attribute in one offer, but to provide the same ice-pwd or ice-ufrag as a media-level attribute in a subsequent offer.  This is not a change in password, just a change in its representation, and does not cause an ICE restart.*</span></span>

<span data-ttu-id="84765-348">*에이전트는이 미디어 스트림의 초기 제공에서와 마찬가지로이 미디어 스트림의 SDP에 나머지 필드를 설정 합니다 (4.3 섹션 참조).  따라서 후보 집합에는 해당 스트림에 대 한 이전 후보의이 일부, 없음 또는 모두 포함 될 수 있으며, 4.1.1 섹션에 설명 된 것 처럼 완전히 새로운 후보 집합이 포함 될 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="84765-348">*An agent sets the rest of the fields in the SDP for this media stream as it would in an initial offer of this media stream (see Section 4.3).  Consequently, the set of candidates MAY include some, none, or all of the previous candidates for that stream and MAY include a totally new set of candidates gathered as described in Section 4.1.1.*</span></span>

<span data-ttu-id="84765-349">처음에 통화를 미디어 바이패스로 설정 하 고 통화를 비즈니스용 Skype 클라이언트로 전송 하는 경우에는 다이렉트 라우팅이 미디어 바이패스로 비즈니스용 Skype 클라이언트에 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="84765-349">If the call was initially established with media bypass, and the call is transferred to a Skype for Business client, Direct Routing needs to insert a Media Processor--this is because Direct Routing cannot be used with a Skype for Business client with media bypass.</span></span> <span data-ttu-id="84765-350">직접 라우팅은 ice-pwd 및 ufrag를 변경 하 고 reinvite에서 새 미디어 후보를 제공 하 여 ICE 다시 시작 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="84765-350">Direct Routing starts the ICE restart process by  changing the ice-pwd and ice-ufrag and offering new media candidates in a reinvite.</span></span> 


