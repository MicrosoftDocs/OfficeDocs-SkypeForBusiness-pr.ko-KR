---
title: 비즈니스용 Skype 서버의 단순 URL에 대한 DNS 요구 사항
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '요약: 비즈니스용 Skype 서버에 대한 DNS 레코드를 구현하기 전에 이 항목의 단순 URL 고려 사항을 검토합니다.'
ms.openlocfilehash: d1c4213e1fe28c6f42cd4fa14f48bc8ce9b7bdf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834588"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a><span data-ttu-id="5bbfd-103">비즈니스용 Skype 서버의 단순 URL에 대한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bbfd-103">DNS requirements for simple URLs in Skype for Business Server</span></span>

<span data-ttu-id="5bbfd-104">**요약:** 비즈니스용 Skype 서버에 대한 DNS 레코드를 구현하기 전에 이 항목의 단순 URL 고려 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server.</span></span>

<span data-ttu-id="5bbfd-105">단순 URL을 사용하면 사용자가 모임에 쉽게 참가할 수 있으며, 관리자가 비즈니스용 Skype 서버 관리 도구를 보다 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="5bbfd-106">단순 URL은 정의한 SIP 도메인과 일치하지 않는 자체 도메인을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 

<span data-ttu-id="5bbfd-107">비즈니스용 Skype 서버는 Meet, Dial-In 및 Admin의 세 가지 단순 URL을 지원합니다. Meet 및 Dial-In에 대한 단순 URL을 설정해야 하는 경우 관리자 단순 URL은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="5bbfd-108">단순 URL을 지원하는 데 필요한 DNS(Domain Name System) 레코드는 이러한 단순 URL을 정의한 방법 및 단순 URL에 대해 재해 복구를 지원할지 여부에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 

## <a name="simple-url-scope"></a><span data-ttu-id="5bbfd-109">단순 URL 범위</span><span class="sxs-lookup"><span data-stu-id="5bbfd-109">Simple URL scope</span></span>

<span data-ttu-id="5bbfd-p103">전역 범위에서 적용되도록 단순 URL을 구성하거나 조직의 각 중앙 사이트에 대해 서로 다른 단순 URL을 지정할 수 있습니다. 전역 단순 URL과 사이트 단순 URL이 둘 다 지정된 경우에는 사이트 단순 URL이 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-p103">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization. If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 

<span data-ttu-id="5bbfd-112">대부분의 경우 단순 URL은 전역 수준에서만 설정하는 것이 좋습니다. 따라서 사용자가 한 사이트에서 다른 사이트로 이동하면 사용자의 Meet 단순 URL이 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="5bbfd-113">단, 여러 사이트의 전화 접속 사용자에 서로 다른 전화 번호를 사용해야 하는 조직은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="5bbfd-114">사이트에서 하나의 단순 URL(예: 전화 접속 단순 URL)을 사이트 수준 단순 URL로 설정한 경우에는 해당 사이트의 다른 단순 URL도 사이트 수준으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<span data-ttu-id="5bbfd-115">토폴로지 작성기에서 전역 단순 URL을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="5bbfd-116">사이트 수준에서 단순 URL을 설정하기 위해 Set-CsSimpleURLConfiguration cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

<span data-ttu-id="5bbfd-117">단순 URL을 정의하려면 DNS 구성에서 A 및/또는 AAAA 레코드를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="5bbfd-118">단순 URL 이름 지정 및 유효성 검사 규칙</span><span class="sxs-lookup"><span data-stu-id="5bbfd-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="5bbfd-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="5bbfd-119"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="5bbfd-120">토폴로지 작성기 및 비즈니스용 Skype 서버 관리 셸 cmdlet은 단순 URL에 대해 몇 가지 유효성 검사 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="5bbfd-121">모임 및 전화 접속 단순 URL은 필수 설정이지만 관리 단순 URL은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="5bbfd-122">모임 단순 URL은 SIP 도메인마다 별도의 URL이 있어야 하지만 전화 접속 단순 URL과 관리 단순 URL은 전체 조직에 하나만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="5bbfd-123">조직의 각 단순 URL에는 고유한 이름이 있어야 하지만 다른 단순 URL의 SfB2015.contoso.com/Meet 수 없습니다. 예를 들어 SfB2015.contoso.com/Meet 단순 URL로 설정할 수 SfB2015.contoso.com/Meet/Dialin URL로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="5bbfd-124">단순 URL 이름에는 풀의 FQDN 또는 포트 정보가 포함될 수 없습니다(예: https://FQDN:88/meet 허용되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="5bbfd-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="5bbfd-125">모든 단순 URL은 https:// 접두사로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-125">All simple URLs must start with the https:// prefix.</span></span> 

<span data-ttu-id="5bbfd-p108">단순 URL은 영숫자(즉, a-z, A-Z, 0-9 및 마침표(.))만 포함할 수 있습니다. 다른 문자를 사용하면 단순 URL이 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-p108">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="5bbfd-128">배포 후 단순 URL 변경</span><span class="sxs-lookup"><span data-stu-id="5bbfd-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="5bbfd-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="5bbfd-129"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="5bbfd-130">초기 배포 후 단순 URL을 변경하려면 단순 URL의 DNS 레코드 및 인증서가 이러한 변경으로 인해 받을 수 있는 영향을 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="5bbfd-131">단순 URL의 기준이 변경되면 DNS 레코드 및 인증서도 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="5bbfd-132">예를 들어 기본 URL을 SfB2015.contoso.com url에서 meet.contoso.com 변경하는 경우 DNS 레코드 및 인증서를 변경하여 기본 URL을 참조해야 https://SfB2015.contoso.com/Meet https://meet.contoso.com meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="5bbfd-133">단순 URL을 변경한 경우 기본 URL의 SfB2015.contoso.com 동일하게 유지되어 DNS 또는 인증서를 변경할 https://SfB2015.contoso.com/Meet 필요가 https://SfB2015.contoso.com/Meetings 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-133">If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="5bbfd-134">그러나 단순 URL 이름을 변경할 때마다 각 Director 및 프런트 엔드 서버에서 **Enable-CsComputer를** 실행하여 변경을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-134">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="5bbfd-135">단순 URL의 이름 이름 예제</span><span class="sxs-lookup"><span data-stu-id="5bbfd-135">Naming examples for Simple URLs</span></span>
<span data-ttu-id="5bbfd-136"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="5bbfd-136"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="5bbfd-p110">단순 URL의 이름을 지정할 때 권장되는 세 가지 옵션이 있습니다. 선택한 옵션에 따라 단순 URL을 지원하는 DNS A 레코드 및 인증서 설정 방법이 결정됩니다. 각 옵션에서는 조직의 각 SIP 도메인에 대해 하나의 모임 단순 URL을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-p110">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 

<span data-ttu-id="5bbfd-140">보유한 SIP 도메인 수에 관계없이 전화 접속 단순 URL과 관리 단순 URL은 항상 전체 조직에서 각각 하나씩만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-140">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="5bbfd-141">옵션 1에서는 각 단순 URL에 대한 새 SIP 도메인 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-141">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="5bbfd-142">이 옵션을 사용하는 경우 각 단순 URL에 대해 별도의 DNS A 레코드가 필요하며 각 모임 단순 URL의 이름이 인증서에 지정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-142">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

<span data-ttu-id="5bbfd-143">**단순 URL 이름 지정 옵션 1**</span><span class="sxs-lookup"><span data-stu-id="5bbfd-143">**Simple URL Naming Option 1**</span></span>


| <span data-ttu-id="5bbfd-144">**단순 URL**</span><span class="sxs-lookup"><span data-stu-id="5bbfd-144">**Simple URL**</span></span> <br/> | <span data-ttu-id="5bbfd-145">**예**</span><span class="sxs-lookup"><span data-stu-id="5bbfd-145">**Example**</span></span> <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5bbfd-146">Meet</span><span class="sxs-lookup"><span data-stu-id="5bbfd-146">Meet</span></span>  <br/>          | <span data-ttu-id="5bbfd-147">https://meet.contoso.com, https://meet.fabrikam.com 등(조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="5bbfd-147">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="5bbfd-148">전화 접속</span><span class="sxs-lookup"><span data-stu-id="5bbfd-148">Dial-in</span></span>  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| <span data-ttu-id="5bbfd-149">관리자</span><span class="sxs-lookup"><span data-stu-id="5bbfd-149">Admin</span></span>  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

<span data-ttu-id="5bbfd-150">옵션 2를 사용하면 단순 URL이 도메인 이름과 SfB2015.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-150">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com.</span></span> <span data-ttu-id="5bbfd-151">따라서 세 가지 유형의 단순 URL을 모두 사용할 수 있는 DNS A 레코드가 하나만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-151">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="5bbfd-152">이 DNS A 레코드는 SfB2015.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-152">This DNS A record references SfB2015.contoso.com.</span></span> <span data-ttu-id="5bbfd-153">또한 조직의 다른 SIP 도메인에 대해 별도의 DNS A 레코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-153">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 

<span data-ttu-id="5bbfd-154">**단순 URL 이름 지정 옵션 2**</span><span class="sxs-lookup"><span data-stu-id="5bbfd-154">**Simple URL Naming Option 2**</span></span>


| <span data-ttu-id="5bbfd-155">**단순 URL**</span><span class="sxs-lookup"><span data-stu-id="5bbfd-155">**Simple URL**</span></span> <br/> | <span data-ttu-id="5bbfd-156">**예**</span><span class="sxs-lookup"><span data-stu-id="5bbfd-156">**Example**</span></span> <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5bbfd-157">Meet</span><span class="sxs-lookup"><span data-stu-id="5bbfd-157">Meet</span></span>  <br/>          | <span data-ttu-id="5bbfd-158">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet 등(조직의 각 SIP 도메인에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="5bbfd-158">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="5bbfd-159">전화 접속</span><span class="sxs-lookup"><span data-stu-id="5bbfd-159">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| <span data-ttu-id="5bbfd-160">관리자</span><span class="sxs-lookup"><span data-stu-id="5bbfd-160">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

<span data-ttu-id="5bbfd-161">옵션 3은 많은 SIP 도메인이 있고 각각에 별도의 모임 단순 URL을 사용하지만 이러한 단순 URL에 필요한 DNS 레코드 및 인증서를 최소화하려는 경우에 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-161">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 

<span data-ttu-id="5bbfd-162">**단순 URL 이름 지정 옵션 3**</span><span class="sxs-lookup"><span data-stu-id="5bbfd-162">**Simple URL Naming Option 3**</span></span>


| <span data-ttu-id="5bbfd-163">**단순 URL**</span><span class="sxs-lookup"><span data-stu-id="5bbfd-163">**Simple URL**</span></span> <br/> | <span data-ttu-id="5bbfd-164">**예**</span><span class="sxs-lookup"><span data-stu-id="5bbfd-164">**Example**</span></span> <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5bbfd-165">Meet</span><span class="sxs-lookup"><span data-stu-id="5bbfd-165">Meet</span></span>  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| <span data-ttu-id="5bbfd-166">전화 접속</span><span class="sxs-lookup"><span data-stu-id="5bbfd-166">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| <span data-ttu-id="5bbfd-167">관리자</span><span class="sxs-lookup"><span data-stu-id="5bbfd-167">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="5bbfd-168">단순 URL에 대한 재해 복구 옵션</span><span class="sxs-lookup"><span data-stu-id="5bbfd-168">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="5bbfd-169"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="5bbfd-169"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="5bbfd-170">프런트 엔드 풀이 포함된 사이트가 여러 개 있으며 DNS 공급자가 GeoDNS를 지원하는 경우 재해 복구를 지원하기 위해 단순 URL에 대한 DNS 레코드를 설정하여 전체 프런트 엔드 풀이 다운된 경우에도 단순 URL 기능이 계속 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-170">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="5bbfd-171">이 재해 복구 기능은 모임 및 전화 접속 단순 URL을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-171">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="5bbfd-p113">이와 같이 구성하려면 GeoDNS 주소 두 개를 만듭니다. 각 주소에는 재해 복구용으로 쌍으로 지정된 두 개의 풀로 확인되는 DNS A 또는 CNAME 레코드 두 개가 포함됩니다. GeoDNS 주소 중 하나는 내부 액세스용으로 사용되며, 두 풀에 대한 내부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인됩니다. 나머지 GeoDNS 주소는 외부 액세스용으로 사용되며, 두 풀의 외부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인됩니다. 아래에는 풀의 FQDN을 사용하는 모임 단순 URL의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-p113">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 

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

<span data-ttu-id="5bbfd-177">그런 후에 meet.contoso.com과 같은 모임 단순 URL을 두 개의 GeoDNS 주소로 확인하는 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-177">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="5bbfd-178">네트워크에서 헤어핀(조직 내부에서 생성되는 트래픽을 비롯하여 모든 단순 URL 트래픽을 외부 링크를 통해 라우팅)을 사용하는 경우에는 외부 GeoDNS 주소만 구성하고 모임 단순 URL을 해당 외부 주소로만 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-178">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>

<span data-ttu-id="5bbfd-179">이 방법을 사용하는 경우 각 GeoDNS 주소가 라운드 로빈 방법을 사용하여 요청을 두 풀로 분산시키거나, 기본적으로 한 풀(예: 지리적으로 더 가까이 있는 풀)에 연결하고 다른 풀은 연결 오류 시에만 사용하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-179">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 

<span data-ttu-id="5bbfd-180">전화 접속 단순 URL에 대해 같은 구성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-180">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="5bbfd-181">이렇게 하여 이전 예제의 레코드와 같은 추가 레코드를 만들어 DNS 레코드에  `dialin` `meet` 대신합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-181">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="5bbfd-182">관리 단순 URL의 경우 이 섹션 앞부분에 나와 있는 세 가지 옵션 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-182">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="5bbfd-183">이 구성을 설정한 후에는 모니터링 응용 프로그램을 사용하여 오류를 감시할 HTTP 모니터링을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-183">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="5bbfd-184">외부 액세스의 경우 HTTPS GET lyncdiscover가 있는지 모니터링합니다.<sipdomain></span><span class="sxs-lookup"><span data-stu-id="5bbfd-184">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="5bbfd-185">두 풀에 대한 외부 웹 FQDN 또는 부하 조정자 IP 주소에 대한 요청이 성공적입니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-185">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="5bbfd-186">예를 들어 다음 요청은 **ACCEPT** 헤더를 포함하면 안 되며 **200 OK** 를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-186">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="5bbfd-187">내부 액세스의 경우에는 두 풀에 대해 내부 웹 FQDN 또는 부하 분산 장치 IP 주소에서 포트 5061을 모니터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-187">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="5bbfd-188">연결 오류가 감지되면 이러한 풀의 VIP가 포트 80, 443 및 4443을 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbfd-188">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>


