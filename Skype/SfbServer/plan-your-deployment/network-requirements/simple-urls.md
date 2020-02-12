---
title: 비즈니스용 Skype 서버의 간단한 Url에 대 한 DNS 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '요약: 비즈니스용 Skype 서버에 대 한 DNS 레코드를 구현 하기 전에이 항목의 간단한 URL 고려 사항을 검토 하세요.'
ms.openlocfilehash: 3296e3678d1d38f021b792a2362f61de66796d0f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888477"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a><span data-ttu-id="f3c46-103">비즈니스용 Skype 서버의 간단한 Url에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3c46-103">DNS requirements for simple URLs in Skype for Business Server</span></span>

<span data-ttu-id="f3c46-104">**요약:** 비즈니스용 Skype 서버에 대 한 DNS 레코드를 구현 하기 전에이 항목의 간단한 URL 고려 사항을 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3c46-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server.</span></span>

<span data-ttu-id="f3c46-105">간단한 Url을 사용 하면 사용자에 게 보다 쉽게 모임에 참가할 수 있으며, 관리자는 비즈니스용 Skype 서버 관리 도구를 사용 하는 것이 더 쉬워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="f3c46-106">간단한 Url은 사용자가 정의한 SIP 도메인과 일치 하지 않는 자체 도메인을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 

<span data-ttu-id="f3c46-107">비즈니스용 Skype 서버는 회의, 전화 접속 및 관리자의 세 가지 간단한 Url을 지원 합니다. 시작 및 전화 접속에 대 한 간단한 Url을 설정 해야 하며, 관리자 단순 URL은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="f3c46-108">간단한 url을 지원 하기 위해 필요한 DNS (Domain Name System) 레코드는 간단한 url을 정의한 방법과 간단한 Url에 대 한 재해 복구를 지원 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 

## <a name="simple-url-scope"></a><span data-ttu-id="f3c46-109">간단한 URL 범위</span><span class="sxs-lookup"><span data-stu-id="f3c46-109">Simple URL scope</span></span>

<span data-ttu-id="f3c46-110">전역 범위를 포함 하도록 간단한 Url을 구성 하거나 조직의 각 중앙 사이트에 대해 서로 다른 간단한 Url을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-110">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="f3c46-111">전역 단순 URL과 사이트 단순 URL이 모두 지정 된 경우 사이트 단순 URL이 우선권을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-111">If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 

<span data-ttu-id="f3c46-112">대부분의 경우 사용자가 한 사이트에서 다른 사이트로 이동 하는 경우 단순한 URL이 변경 되지 않도록 전역 수준 에서만 간단한 Url을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="f3c46-113">이 예외는 다른 사이트의 전화 접속 사용자에 게 다른 전화 번호를 사용 해야 하는 조직입니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="f3c46-114">사이트의 간단한 URL (예: 전화 접속 간단한 URL)을 사이트 수준 간단한 URL로 설정한 경우에는 해당 사이트의 다른 간단한 url도 사이트 수준으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<span data-ttu-id="f3c46-115">토폴로지 작성기에서 전역 단순 Url을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="f3c46-116">사이트 수준에서 간단한 URL을 설정 하려면 Set-CsSimpleURLConfiguration cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

<span data-ttu-id="f3c46-117">간단한 URL을 정의 하는 경우 DNS 구성에서 A 및/또는 AAAA 레코드를 설정 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="f3c46-118">간단한 URL 명명 및 유효성 검사 규칙</span><span class="sxs-lookup"><span data-stu-id="f3c46-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="f3c46-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="f3c46-119"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="f3c46-120">토폴로지 작성기 및 비즈니스용 Skype 서버 관리 셸 cmdlet은 간단한 Url에 대 한 여러 가지 유효성 검사 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="f3c46-121">간단한 Url을 시작 및 전화 접속으로 설정 해야 하지만 관리자 용으로 설정 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="f3c46-122">각 SIP 도메인에는 별도의 단순 URL이 필요 하지만, 전체 조직에 대해 하나의 전화 접속 단순 url과 하나의 관리자 단순 URL만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="f3c46-123">조직의 각 단순 URL은 고유한 이름을 가져야 하 고 다른 간단한 URL의 접두사가 될 수 없습니다 (예를 들어, SfB2015.contoso.com/Meet를 사용 하 여 단순한 url로 시작 하 고 SfB2015.contoso.com/Meet/Dialin를 전화 접속 간단한 URL로 설정할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="f3c46-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="f3c46-124">간단한 URL 이름에는 풀의 FQDN 또는 포트 정보 (예: 허용 되지 않음) https://FQDN:88/meet 가 포함 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="f3c46-125">모든 단순 Url은 https://접두사로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-125">All simple URLs must start with the https:// prefix.</span></span> 

<span data-ttu-id="f3c46-126">간단한 Url에는 영숫자 문자 (a-z, A-z, 0-9, 마침표 (.)만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-126">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="f3c46-127">다른 문자를 사용 하는 경우 간단한 Url이 예상 대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-127">If you use other characters, the simple URLs might not work as expected.</span></span>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="f3c46-128">배포 후 간단한 Url 변경</span><span class="sxs-lookup"><span data-stu-id="f3c46-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="f3c46-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="f3c46-129"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="f3c46-130">초기 배포 후 간단한 URL을 변경 하는 경우에는 변경 내용이 간단한 Url에 대 한 DNS 레코드 및 인증서에 영향을 주는 방식을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="f3c46-131">간단한 URL의 기본이 변경 되는 경우 DNS 레코드 및 인증서도 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="f3c46-132">예를 들어 SfB2015.contoso.com에서 https://SfB2015.contoso.com/Meet 로 https://meet.contoso.com 변경 하면 기본 URL이 MEET.CONTOSO.COM로 변경 되므로 DNS 레코드와 인증서를 변경 해야 meet.contoso.com을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="f3c46-133">간단한 URL을에서 https://SfB2015.contoso.com/Meet 으로 https://SfB2015.contoso.com/Meetings변경한 경우 SfB2015.contoso.com의 기본 url은 동일 하 게 유지 되므로 DNS 또는 인증서를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-133">If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="f3c46-134">그러나 간단한 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 **-CsComputer** 를 실행 하 여 변경 내용을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-134">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="f3c46-135">간단한 Url에 대 한 명명 예제</span><span class="sxs-lookup"><span data-stu-id="f3c46-135">Naming examples for Simple URLs</span></span>
<span data-ttu-id="f3c46-136"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="f3c46-136"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="f3c46-137">간단한 Url의 이름을 지정 하는 데 권장 되는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-137">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="f3c46-138">선택 하는 옵션에 따라 간단한 Url을 지 원하는 DNS 레코드 및 인증서 설정 방법에 대 한 영향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-138">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="f3c46-139">각 옵션에서 조직의 각 SIP 도메인에 대해 하나의 모임 단순 URL을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-139">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 

<span data-ttu-id="f3c46-140">사용 중인 SIP 도메인의 수에 관계 없이 모든 조직에서 전화 접속 및 관리자 용으로 하나의 간단한 URL만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-140">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="f3c46-141">옵션 1에서 각 단순 URL에 대 한 새 SIP 도메인 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-141">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="f3c46-142">이 옵션을 사용 하는 경우 각 단순 URL에 대 한 별도의 DNS A 레코드가 필요 하며, 각 일치 하는 단순 URL은 인증서에 명명 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-142">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

<span data-ttu-id="f3c46-143">**간단한 URL 명명 옵션 1**</span><span class="sxs-lookup"><span data-stu-id="f3c46-143">**Simple URL Naming Option 1**</span></span>


| <span data-ttu-id="f3c46-144">**간단한 URL**</span><span class="sxs-lookup"><span data-stu-id="f3c46-144">**Simple URL**</span></span> <br/> | <span data-ttu-id="f3c46-145">**예**</span><span class="sxs-lookup"><span data-stu-id="f3c46-145">**Example**</span></span> <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f3c46-146">시켜</span><span class="sxs-lookup"><span data-stu-id="f3c46-146">Meet</span></span>  <br/>          | <span data-ttu-id="f3c46-147">https://meet.contoso.comhttps://meet.fabrikam.com(조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="f3c46-147">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="f3c46-148">전화 접속</span><span class="sxs-lookup"><span data-stu-id="f3c46-148">Dial-in</span></span>  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| <span data-ttu-id="f3c46-149">관리자</span><span class="sxs-lookup"><span data-stu-id="f3c46-149">Admin</span></span>  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

<span data-ttu-id="f3c46-150">옵션 2에서는 간단한 Url이 도메인 이름 SfB2015.contoso.com를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-150">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com.</span></span> <span data-ttu-id="f3c46-151">따라서 세 가지 유형의 간단한 Url을 모두 사용할 수 있는 하나의 DNS A 레코드도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-151">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="f3c46-152">이 DNS A 레코드는 SfB2015.contoso.com를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-152">This DNS A record references SfB2015.contoso.com.</span></span> <span data-ttu-id="f3c46-153">또한 조직의 다른 SIP 도메인에 대 한 별도의 DNS A 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-153">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 

<span data-ttu-id="f3c46-154">**간단한 URL 명명 옵션 2**</span><span class="sxs-lookup"><span data-stu-id="f3c46-154">**Simple URL Naming Option 2**</span></span>


| <span data-ttu-id="f3c46-155">**간단한 URL**</span><span class="sxs-lookup"><span data-stu-id="f3c46-155">**Simple URL**</span></span> <br/> | <span data-ttu-id="f3c46-156">**예**</span><span class="sxs-lookup"><span data-stu-id="f3c46-156">**Example**</span></span> <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f3c46-157">시켜</span><span class="sxs-lookup"><span data-stu-id="f3c46-157">Meet</span></span>  <br/>          | <span data-ttu-id="f3c46-158">https://SfB2015.contoso.com/Meethttps://SfB2015.fabrikam.com/Meet(조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="f3c46-158">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="f3c46-159">전화 접속</span><span class="sxs-lookup"><span data-stu-id="f3c46-159">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| <span data-ttu-id="f3c46-160">관리자</span><span class="sxs-lookup"><span data-stu-id="f3c46-160">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

<span data-ttu-id="f3c46-161">옵션 3은 많은 SIP 도메인이 있는 경우 각 사용자에 게 별도의 단순 Url을 사용 하도록 하 고, 이러한 간단한 Url에 대 한 DNS 레코드 및 인증서 요구 사항을 최소화 하려는 경우에 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-161">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 

<span data-ttu-id="f3c46-162">**간단한 URL 명명 옵션 3**</span><span class="sxs-lookup"><span data-stu-id="f3c46-162">**Simple URL Naming Option 3**</span></span>


| <span data-ttu-id="f3c46-163">**간단한 URL**</span><span class="sxs-lookup"><span data-stu-id="f3c46-163">**Simple URL**</span></span> <br/> | <span data-ttu-id="f3c46-164">**예**</span><span class="sxs-lookup"><span data-stu-id="f3c46-164">**Example**</span></span> <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f3c46-165">시켜</span><span class="sxs-lookup"><span data-stu-id="f3c46-165">Meet</span></span>  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| <span data-ttu-id="f3c46-166">전화 접속</span><span class="sxs-lookup"><span data-stu-id="f3c46-166">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| <span data-ttu-id="f3c46-167">관리자</span><span class="sxs-lookup"><span data-stu-id="f3c46-167">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="f3c46-168">간단한 Url에 대 한 재해 복구 옵션</span><span class="sxs-lookup"><span data-stu-id="f3c46-168">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="f3c46-169"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="f3c46-169"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="f3c46-170">프런트 엔드 풀을 포함 하는 사이트가 여러 개 있고 DNS 공급자가 GeoDNS를 지 원하는 경우, 장애 복구를 지원 하도록 간단한 Url에 대 한 DNS 레코드를 설정 하 여 전체 프론트 엔드 풀 하나가 다운 되어도 간단한 URL 기능이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-170">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="f3c46-171">이 재해 복구 기능은 모임 및 전화 접속 간단한 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-171">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="f3c46-172">이를 구성 하려면 두 개의 GeoDNS 주소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-172">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="f3c46-173">각 주소에는 재해 복구용으로 서로 연결 된 두 개의 풀로 확인 되는 두 개의 DNS A 또는 CNAME 레코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-173">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="f3c46-174">하나의 GeoDNS 주소는 내부 액세스에 사용 되며, 두 풀의 내부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-174">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="f3c46-175">다른 GeoDNS 주소는 외부 액세스에 사용 되며, 두 풀의 외부 웹 FQDN 또는 부하 분산 장치 IP 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-175">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="f3c46-176">다음은 풀에 대 한 Fqdn을 사용 하 여 단순 URL을 충족 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-176">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

<span data-ttu-id="f3c46-177">그런 다음 두 GeoDNS 주소에 대 한 meet.contoso.com (예:)와 일치 하는 단순 URL을 확인 하는 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-177">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="f3c46-178">네트워크에서 hairpinning를 사용 하는 경우 (조직 내에서 제공 하는 트래픽을 포함 하 여 외부 링크를 통해 모든 간단한 URL 트래픽을 라우팅하는 경우), 외부 GeoDNS 주소를 구성 하 고 해당 하는 단순 URL만 문제를 해결할 수 있습니다. 외부 주소</span><span class="sxs-lookup"><span data-stu-id="f3c46-178">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>

<span data-ttu-id="f3c46-179">이 메서드를 사용 하는 경우 라운드 로빈 메서드를 사용 하 여 두 개의 풀에 요청을 분산 하거나, 기본 풀 (예: 지리적으로 가까운 풀)에 연결 하 고, 다음의 경우에만 다른 풀을 사용 하도록 각 GeoDNS 주소를 구성할 수 있습니다. 연결 실패.</span><span class="sxs-lookup"><span data-stu-id="f3c46-179">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 

<span data-ttu-id="f3c46-180">전화 접속 단순 URL에 대해 동일한 구성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-180">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="f3c46-181">이렇게 하려면 이전 예제와 같은 추가 레코드를 만들고 DNS 레코드 `dialin` `meet` 에서 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-181">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="f3c46-182">관리 간단한 URL의 경우이 섹션의 앞에 나열 된 세 가지 옵션 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-182">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="f3c46-183">이 구성을 설정한 후에는 모니터링 응용 프로그램을 사용 하 여 오류를 감시 하도록 HTTP 모니터링을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-183">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="f3c46-184">외부 액세스의 경우 모니터링을 통해 HTTPS가 lyncdiscover를 얻을 수 있습니다.<sipdomain></span><span class="sxs-lookup"><span data-stu-id="f3c46-184">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="f3c46-185">외부 웹 FQDN 또는 두 풀에 대 한 부하 분산 장치 IP 주소에 대 한 요청이 성공적으로 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-185">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="f3c46-186">예를 들어 다음 요청에는 **ACCEPT** 헤더가 없어야 하 고 **200 OK**를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-186">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="f3c46-187">내부 액세스의 경우 두 풀에 대 한 내부 웹 FQDN 또는 부하 분산 장치 IP 주소에서 포트 5061을 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-187">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="f3c46-188">연결 실패가 감지 되는 경우 이러한 풀의 VIP는 포트 80, 443 및 4443을 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c46-188">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>


