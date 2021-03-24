---
title: 비즈니스용 Skype 서버 모바일 배포 및 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 모바일 기능을 활용할 수 있도록 Mobility Service를 사용하도록 기존 비즈니스용 Skype 서버 설치를 구성하는 단계를 단계로 진행합니다.
ms.openlocfilehash: 2ba0a81350dac6e47f4e909b4cfba256ee90de18
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103864"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="fa848-103">비즈니스용 Skype 서버 모바일 배포 및 구성</span><span class="sxs-lookup"><span data-stu-id="fa848-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="fa848-104">이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 모바일 기능을 활용할 수 있도록 Mobility Service를 사용하도록 기존 비즈니스용 Skype 서버 설치를 구성하는 단계를 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="fa848-105">비즈니스용 [Skype](../plan-your-deployment/mobility.md) 서버의 모바일 계획 문서를 검토한 후 아래 단계를 진행하여 비즈니스용 Skype 서버 환경에 Mobility을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="fa848-106">단계는 다음과 같습니다(이 표에 사용 권한 목록 포함).</span><span class="sxs-lookup"><span data-stu-id="fa848-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="fa848-107">**작업 단계**</span><span class="sxs-lookup"><span data-stu-id="fa848-107">**Phase**</span></span>|<span data-ttu-id="fa848-108">**사용 권한**</span><span class="sxs-lookup"><span data-stu-id="fa848-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="fa848-109">DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="fa848-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="fa848-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="fa848-110">Domain Admins</span></span>  <br/> <span data-ttu-id="fa848-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="fa848-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="fa848-112">인증서 수정</span><span class="sxs-lookup"><span data-stu-id="fa848-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="fa848-113">로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="fa848-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="fa848-114">역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="fa848-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="fa848-115">로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="fa848-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="fa848-116">하이브리드 배포를 통해 모바일 기능을 위한 자동검사 구성</span><span class="sxs-lookup"><span data-stu-id="fa848-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="fa848-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="fa848-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="fa848-118">모바일 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="fa848-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="fa848-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="fa848-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="fa848-120">푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="fa848-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="fa848-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="fa848-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="fa848-122">모바일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="fa848-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="fa848-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="fa848-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="fa848-124">다음 모든 섹션에는 계획 항목을 읽었다고 가정하는 단계가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="fa848-125">혼란스러울 경우 정보를 자유롭게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="fa848-126">레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="fa848-127">모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="fa848-128">MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="fa848-129">DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="fa848-129">Create DNS records</span></span>
<span data-ttu-id="fa848-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="fa848-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="fa848-131">이러한 레코드가 비즈니스용 Skype 서버 환경의 일부로 이미 있을 수 있지만 자동 검색이 작동하려면 다음 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="fa848-132">조직 네트워크 내에서 연결하고 있는 모바일 사용자를 지원하기 위한 내부 DNS 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="fa848-133">조직 네트워크 외부에서 연결하는 모바일 사용자를 지원하기 위한 외부(또는 공용) DNS 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="fa848-134">이러한 레코드는 A(호스트) 이름 또는 CNAME 레코드일 수 있습니다(둘 다 만들지 않은 경우 여기에 있는 모든 단계만 포함).</span><span class="sxs-lookup"><span data-stu-id="fa848-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="fa848-135">내부 DNS CNAME 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="fa848-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="fa848-136">**Domain Admins** 그룹 또는 **DnsAdmins** 그룹의 구성원인 네트워크의 DNS 서버에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="fa848-137">**시작,** 관리 도구 **선택(시작**  메뉴의 옵션이 아닌 경우 검색해야 할 수 있습니다)을 클릭한 다음 **DNS를** 클릭하여 DNS 관리 스냅인을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="fa848-138">콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버의 프런트 엔드 서버가 있는 도메인으로 이동하여 정방 검색 범위를 확장해야 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="fa848-139">다음 중 어떤 것이 필요한지 잠시 시간을 내어 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="fa848-140">프런트 엔드 서버(Standard 또는 Enterprise) 또는 프런트 엔드 풀에 대한 호스트 A 또는 AAAA 레코드</span><span class="sxs-lookup"><span data-stu-id="fa848-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="fa848-141">Director 또는 Director 풀에 대한 모든 호스트 A 또는 AAAA 레코드(배포에 사용할 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="fa848-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="fa848-142">이를 확인한 후 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 메뉴에서 새 **별칭(CNAME)을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="fa848-143">별칭 **이름** 텍스트 상자에 내부 자동 검색 서비스 URL에 호스트 이름의 lyncdiscoverinternal을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="fa848-144">대상 호스트의 **FQDN(FQDN)에서** 위의 4단계에서 식별된 프런트 엔드 풀(또는 단일 프런트 엔드 서버 또는 Director 풀 또는 Director)에 대한 내부 웹 서비스 FQDN을 입력하거나 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="fa848-145">입력할 때 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="fa848-146">비즈니스용 Skype 서버 환경에서 지원되는 각 SIP 도메인에 대한 정방 검색 영역의 새 자동 검색 CNAME 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="fa848-147">외부 DNS CNAME 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="fa848-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="fa848-148">이러한 단계는 일반적입니다. 사용 중일 수 있는 공용 DNS 공급자를 알 수 없지만 여전히 도움을 줄 수 있습니다. 새 DNS 레코드를 만들 수 있는 계정으로 공용 DNS 공급자에 로그인하세요.</span><span class="sxs-lookup"><span data-stu-id="fa848-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="fa848-149">이때 비즈니스용 Skype 서버에 대한 SIP 도메인이 이미 존재해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="fa848-150">이 SIP 도메인에 대한 **정방** 검색 범위를 확장하거나 다른 경우 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="fa848-151">다음 중 어떤 것이 필요한지 잠시 시간을 내어 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="fa848-152">프런트 엔드 서버(Standard 또는 Enterprise) 또는 프런트 엔드 풀에 대한 호스트 A 또는 AAAA 레코드</span><span class="sxs-lookup"><span data-stu-id="fa848-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="fa848-153">Director 또는 Director 풀에 대한 모든 호스트 A 또는 AAAA 레코드(배포에 사용할 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="fa848-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="fa848-154">해당 정보가 있는 경우 새 별칭(CNAME)을 만들기 위한 옵션을 선택할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="fa848-155">이제 별칭 이름을 입력할 수 있습니다. 외부 자동iscover 서비스 URL에 대해 여기에 lyncdiscover를 입력해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="fa848-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="fa848-156">다음으로 대상 호스트의 FQDN에 입력할 영역이 있습니다. 이 영역은 위의 3단계에서 식별된 프런트 엔드 풀(또는 단일 프런트 엔드 서버 또는 Director 풀 또는 Director)에 대한 **FQDN이** 되거나 아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="fa848-157">여기서 저장해야 할 수도 있습니다. 또는 비즈니스용 Skype 서버 환경의 각 SIP 도메인의 정방 검색 영역으로 추가 CNAME 레코드를 만들어야 하는 경우 이렇게 해야 하지만 준비가 된 후 작업을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="fa848-158">내부 DNS A 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="fa848-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="fa848-159">**Domain Admins** 그룹 또는 **DnsAdmins** 그룹의 구성원인 네트워크의 DNS 서버에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="fa848-160">**시작,** 관리 도구 **선택(시작**  메뉴의 옵션이 아닌 경우 검색해야 할 수 있습니다)을 클릭한 다음 **DNS를** 클릭하여 DNS 관리 스냅인을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="fa848-161">콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버의 프런트 엔드 서버가 있는 도메인으로 이동하여 정방 검색 범위를 확장해야 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="fa848-162">다음 중 어떤 것이 필요한지 잠시 시간을 내어 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="fa848-163">프런트 엔드 서버(Standard 또는 Enterprise) 또는 프런트 엔드 풀에 대한 호스트 A 또는 AAAA 레코드</span><span class="sxs-lookup"><span data-stu-id="fa848-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="fa848-164">Director 또는 Director 풀에 대한 모든 호스트 A 또는 AAAA 레코드(배포에 사용할 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="fa848-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="fa848-165">지정한 후 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 메뉴에서 새 **호스트(A 또는 AAAA)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="fa848-166">이름 **텍스트** 상자에 내부 자동 검색 서비스 URL에 대해 호스트 이름의 lyncdiscoverinternal을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="fa848-167">IP **주소 텍스트** 상자에 위의 4단계에서 식별된 프런트 엔드 풀(또는 단일 프런트 엔드 서버 또는 Director 풀 또는 Director)에 대한 내부 웹 서비스 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="fa848-168">이 완료되면 호스트 **추가를** 클릭하고 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="fa848-169">비즈니스용 Skype 서버 환경에서 지원되는 각 SIP 도메인에 대한 정방 검색 영역의 새 자동 검색 A 또는 AAAA 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="fa848-170">이 작업을 수행하려면 필요에 따라 6-8단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="fa848-171">완료되면 완료 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="fa848-172">외부 DNS A 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="fa848-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="fa848-173">이러한 단계는 일반적입니다. 사용 중일 수 있는 공용 DNS 공급자를 알 수 없지만 여전히 도움을 줄 수 있습니다. 새 DNS 레코드를 만들 수 있는 계정으로 공용 DNS 공급자에 로그인하세요.</span><span class="sxs-lookup"><span data-stu-id="fa848-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="fa848-174">이때 비즈니스용 Skype 서버에 대한 SIP 도메인이 이미 존재해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="fa848-175">이 SIP 도메인에 대한 **정방** 검색 범위를 확장하거나 다른 경우 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="fa848-176">다음 중 어떤 것이 필요한지 잠시 시간을 내어 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="fa848-177">프런트 엔드 서버(Standard 또는 Enterprise) 또는 프런트 엔드 풀에 대한 호스트 A 또는 AAAA 레코드</span><span class="sxs-lookup"><span data-stu-id="fa848-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="fa848-178">Director 또는 Director 풀에 대한 모든 호스트 A 또는 AAAA 레코드(배포에 사용할 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="fa848-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="fa848-179">해당 정보가 있는 경우 새 호스트 A 또는 **AAAA를** 만들기 위한 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="fa848-180">이제 이름 을 입력할 수 있습니다. 외부 자동iscover 서비스 URL에 대해 여기에 lyncdiscover를 입력해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="fa848-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="fa848-181">다음으로 IP 주소 에 입력할 영역이 있습니다. 이 IP는 위의 3단계에서 식별된 프런트 엔드 풀(또는 단일 프런트 엔드 서버 또는 Director 풀 또는 Director)의 **IP가** 되거나 아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="fa848-182">여기서 저장해야 할 수도 있습니다. 또는 비즈니스용 Skype 서버 환경에 대한 각 SIP 도메인의 정방 검색 영역으로 추가 A 또는 AAAA 레코드를 만들어야 하는 경우 이 작업을 해야 하지만 준비가 된 후 작업을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="fa848-183">인증서 수정</span><span class="sxs-lookup"><span data-stu-id="fa848-183">Modify certificates</span></span>
<span data-ttu-id="fa848-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="fa848-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="fa848-185">인증서 계획에 대한 질문이 있는 경우 비즈니스용 [Skype](../plan-your-deployment/mobility.md) 서버 계획 문서에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="fa848-186">검토한 후 다음을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="fa848-187">새 인증서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="fa848-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="fa848-188">CA(인증 기관)에서 새 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="fa848-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="fa848-189">PowerShell을 사용하여 대체 인증서로 인치 인증서를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="fa848-190">MMC(Microsoft Management Console)에서 인증서 스냅인을 사용하여 인증서 확인</span><span class="sxs-lookup"><span data-stu-id="fa848-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="fa848-191">새 인증서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="fa848-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="fa848-192">먼저 현재 있는 인증서와 인증서에 필요한 항목이 있는지 여부를 확인하고 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="fa848-193">이를 위해 로컬 관리자인 계정을 사용하여 비즈니스용 Skype 서버에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="fa848-194">이 계정은 또한 이러한 단계 중 일부에 대해 발급 CA(인증 기관)에 대한 권한이 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="fa848-195">비즈니스용 Skype 서버 관리 셸을 여세요(시작 메뉴 또는 작업 표시줄에 고정되지 않은 경우 검색을 사용하여 찾을 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="fa848-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="fa848-196">업데이트된 인증서를 추가하기 전에 할당된 인증서를 반드시 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="fa848-197">따라서 명령에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="fa848-198">3단계의 정보는 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="fa848-199">여러 가지에 대해 할당된 단일 인증서가 있는지 또는 인증서가 필요한 다른 구성 요소에 대해 다른 인증서가 할당되어 있는지 여부를 판단하기 위해 이를 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="fa848-200">Use **매개** 변수는 인증서 사용 방법을 알려 주며 **Thumbprint** 매개 변수는 인증서가 모두 동일한 인증서 또는 여러 인증서에 해당하는지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="fa848-201">계획 섹션에서 권장되는 SAN 항목이 있는 경우 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="fa848-202">그렇지 않은 경우 인증 기관에서 새 인증서 또는 여러 인증서(구성에 따라 다를 수 있습니다.)를 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="fa848-203">CA(인증 기관)에서 새 인증서 또는 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="fa848-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="fa848-204">SAN 항목이 있는 항목을 확인한 후 단일 인증서가 있는  것을 알 수 있으며(위의 단계를 통해 확인한 후) 필요한 항목이 모두 없는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="fa848-205">CA에 새 인증서 요청을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="fa848-206">비즈니스용 Skype 서버 PowerShell을 여는 경우:</span><span class="sxs-lookup"><span data-stu-id="fa848-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="fa848-207">누락된 자동iscover 서비스 SAN(-Ca 매개 변수를 자체 인증 기관 경로로 대체)의 경우:</span><span class="sxs-lookup"><span data-stu-id="fa848-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="fa848-208">이제 SIP 도메인이 여러 개 있는 경우 위의 예와 같은 AllSipDomain 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="fa848-209">대신 DomainName 매개 변수를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="fa848-210">DomainName 매개 변수를 사용하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대한 FQDN을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="fa848-211">예를 들면 다음과 같습니다(-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기).</span><span class="sxs-lookup"><span data-stu-id="fa848-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="fa848-212">또는 어떤 SAN 항목이 있는지 확인한 후 필요한 항목이  모두 없는 인증서가 여러 개 있는 것을 발견했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="fa848-213">CA에 새 인증서 요청을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="fa848-214">비즈니스용 Skype 서버 PowerShell을 여는 경우:</span><span class="sxs-lookup"><span data-stu-id="fa848-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="fa848-215">누락된 자동iscover 서비스 SAN(-Ca 매개 변수를 자체 인증 기관 경로로 대체)의 경우:</span><span class="sxs-lookup"><span data-stu-id="fa848-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="fa848-216">이제 SIP 도메인이 여러 개 있는 경우 위의 예와 같은 AllSipDomain 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="fa848-217">대신 DomainName 매개 변수를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="fa848-218">DomainName 매개 변수를 사용하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대한 FQDN을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="fa848-219">예를 들면 다음과 같습니다(-Ca 매개 변수를 자체 인증 기관 경로로 대체).</span><span class="sxs-lookup"><span data-stu-id="fa848-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="fa848-220">CA에서 새 인증서를 생성한 후 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="fa848-221">비즈니스용 Skype 서버 관리 셸을 사용하여 인증서 할당</span><span class="sxs-lookup"><span data-stu-id="fa848-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="fa848-222">위의 새 인증 필요 섹션에서 확인한 대로 다음 중 하나를  실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="fa848-223">모든(지문이 동일)에 대한 단일 인증서가 있는 경우 다음을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="fa848-224">다른 인증서가 있는 경우(지문이 모두 다를 경우) 대신 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="fa848-225">MMC(Microsoft Management Console)에서 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="fa848-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="fa848-226">MMC에 대한 인증서 스냅인을 사용하여 인증서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="fa848-227">검색에 MMC를 입력하기만 하면 응용 프로그램 옵션으로 팝업됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="fa848-228">인증서 스냅인을 추가하려면 파일 을 클릭한 다음 스냅인 **추가/제거...(또는** 바로 가기 키 **Ctrl+M도** 작동)를 클릭해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="fa848-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="fa848-229">**왼쪽 창에서** 인증서를 선택하고 팝업 창에서 컴퓨터 계정을  선택한 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="fa848-230">여전히 팝업 창에서 보아야 하는 인증서가 있는 컴퓨터에서 이 작업을 수행하고 있으므로 로컬 컴퓨터에서 선택을 그대로 두십시오. </span><span class="sxs-lookup"><span data-stu-id="fa848-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="fa848-231">원격 컴퓨터에서 작업하는 경우 라디오 단추를 다른  컴퓨터로 변경한 다음 해당 컴퓨터의 FQDN을 입력하거나 찾아보기 단추를 사용하여 AD를 통해 해당 컴퓨터를 검색합니다. </span><span class="sxs-lookup"><span data-stu-id="fa848-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="fa848-232">컴퓨터를 선택한 후 준비되면 마친을  클릭한 다음  확인을 클릭하여 MMC에 스냅인을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="fa848-233">MMC의 **왼쪽** 창에서 인증서 섹션을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="fa848-234">개인 **폴더도** 확장한 다음 **인증서 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="fa848-235">이렇게 하면 이 저장소의 인증서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="fa848-236">보하려는 인증서를 찾아 마우스 오른쪽 단추로 클릭한 다음 열기 를 **선택해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa848-237">인증서를 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fa848-237">How do you know what certificate this is?</span></span> <span data-ttu-id="fa848-238">팜의 모든 인증서에 할당된 단일 인증서 또는 기본, 내부 웹 서비스 등 여러 가지 인증서가 있을 수 있습니다. 이 경우 여러 인증서를 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="fa848-239">여러 인증서의 지문이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="fa848-240">인증서 보기를 확인한  후 세부 **정보 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="fa848-241">이렇게 하면 주체 를 선택하면 인증서 주체 이름을 볼 수 있으며 할당된 주체 이름 및 관련 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="fa848-242">주체 대체 이름 **항목도 확인해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="fa848-243">다음 중 하나 이상을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="fa848-244">이 풀의 풀 이름 또는 풀이 아닌 경우 단일 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="fa848-245">인증서가 할당된 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="fa848-246">단순 URL 레코드(일반적으로 meet 및 dialin)입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="fa848-247">웹 서비스 내부 및 웹 서비스 외부 이름(예: webpool01.contoso.net, webpool01.contoso.com)은 토폴로지 작성기에서 선택한 선택과 과도하게 지워진 웹 서비스 선택을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="fa848-248">이미 할당된 경우 lyncdiscover입니다.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="fa848-248">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="fa848-249">및 lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="fa848-249">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="fa848-250">레코드를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-250">records.</span></span>
    
     <span data-ttu-id="fa848-251">할당된 인증서가 두 개 이상 있는 경우 여러 인증서를 확인해야 합니다(위의 참고 사항 확인).</span><span class="sxs-lookup"><span data-stu-id="fa848-251">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="fa848-252">따라서 lyncdiscover를 찾으면\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="fa848-252">So, if you find lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="fa848-253">및 lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="fa848-253">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="fa848-254">레코드를 이미 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-254">records, you've got this configured already.</span></span> <span data-ttu-id="fa848-255">MMC를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-255">You can close the MMC.</span></span>
    
9. <span data-ttu-id="fa848-256">할당되지 않은 경우 새 인증서 요청(위에 설명된)을 만들거나 사후 요청(위의 PowerShell에 다음을 따르는 것이 좋습니다)을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-256">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="fa848-257">역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="fa848-257">Configure the reverse proxy</span></span>
<span data-ttu-id="fa848-258"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="fa848-258"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="fa848-259">아래 단계는 정확히 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-259">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="fa848-260">이전 버전의 제품에서는 TMG(위협 관리 게이트웨이) 구성과 같은 작업을 진행하고 이를 사용하지 않는 경우 해당 버전에서 자체 버전을 작업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-260">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="fa848-261">TMG는 더 이상 Microsoft에서 제품으로 제공되지 않습니다. TMG를 구성해야 하는 경우 [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility)단계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-261">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility).</span></span> <span data-ttu-id="fa848-262">그러나 다음 정보는 모든 역방향 프록시에 대해 특정 안내 단계를 제공할 수 있는 방법이 없는 경우에도 일반적으로 유용하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-262">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="fa848-263">다음과 같은 두 가지 주요 사항들을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-263">We have two main things to consider:</span></span>
  
- <span data-ttu-id="fa848-264">HTTPS(권장)를 통해 초기 자동Iscover 요청을 수행하게 되나요?</span><span class="sxs-lookup"><span data-stu-id="fa848-264">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="fa848-265">웹 게시 규칙이 있는 경우 해당 규칙을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-265">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="fa848-266">아직 웹 게시 규칙이 없는 경우 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-266">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="fa848-267">HTTP를 통해 초기 자동Iscover 요청을 수행하고 있는 경우 해당 규칙을 만들거나 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-267">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fa848-268">**중요** 프록시 시간제한 값은 배포마다 다른 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-268">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="fa848-269">배포를 모니터링하고 클라이언트를 위한 최상의 환경을 위해 값을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-269">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="fa848-270">값을 200으로 낮게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-270">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="fa848-271">환경에서 Lync 모바일 클라이언트를 지원하는 경우 시간 아웃 값이 900인 Office 365의 푸시 알림 시간 아웃을 허용하도록 값을 960으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-271">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="fa848-272">값이 너무 낮은 경우 클라이언트 연결이 끊어지지 않도록 시간 종료 값을 늘리거나, 프록시를 통한 연결이 끊어지지는 않지만 클라이언트 연결이 끊어진 후 오래 지워지지 않는 경우 이 수를 줄이면 시간 종료 값을 늘려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-272">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="fa848-273">환경에 일반적인 기준을 모니터링하고 기준을 세우는 것만이 이 값에 적합한 설정을 결정하는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-273">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="fa848-274">외부 자동 검색 SAN 및 URL에 대한 기존 웹 게시 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="fa848-274">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="fa848-275">역방향 프록시 인터페이스를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-275">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="fa848-276">웹 게시 규칙을 찾아 편집 옵션을 선택해야 합니다(역방향 프록시 구성에 따라 메뉴 또는 탭에 있을 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="fa848-276">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="fa848-277">이 웹 게시 규칙이 적용되는 영역을 말해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-277">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="fa848-278">들어오는 사이트 또는 사이트에 대한 요청에 대해 이 규칙을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-278">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="fa848-279">새 항목을 **추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-279">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="fa848-280">자동 검색 사이트의 이름(예: lyncdiscover.contoso.com)을 입력하고 역방향 프록시의  형식에 따라 확인 또는 저장을 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="fa848-280">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="fa848-281">자동iscover SAN 항목이 있는 새 인증서가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-281">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="fa848-282">역방향 프록시의 설정에 따라 사용하도록 설치 및 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-282">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="fa848-283">구성이 완료되면 모든 것을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-283">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="fa848-284">역방향 프록시에 **테스트** 기능이 있는 경우 이를 사용하여 모든 기능이 제대로 작동하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-284">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="fa848-285">이제 환경에 Director 또는 Director 풀이 있는 경우 이러한 단계를 반복해야 할 수 있습니다(즉, 두 번째 규칙이 있는 것입니다).</span><span class="sxs-lookup"><span data-stu-id="fa848-285">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="fa848-286">외부 자동 검색 URL에 대한 웹 게시 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="fa848-286">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="fa848-287">역방향 프록시 인터페이스를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-287">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="fa848-288">웹 게시 규칙을 만드는 인터페이스에서 새로 만들기 또는 만들기 옵션을  선택해야  합니다(역방향 프록시 구성에 따라 메뉴 또는 탭에 있을 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="fa848-288">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="fa848-289">새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-289">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="fa848-290">일반적으로 다음 정보를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-290">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="fa848-291">**이름**: 규칙의 이름</span><span class="sxs-lookup"><span data-stu-id="fa848-291">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="fa848-292">**규칙 동작:** 이 경우 허용  규칙이면 역방향 프록시를 통해 무언가를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-292">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="fa848-293">선택하는 **게시** 규칙 또는 옵션은 단일 웹 사이트 또는 부하 균형 **조정기입니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-293">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="fa848-294">외부 액세스를 위해 **SSL이** 필요하면 해당 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-294">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="fa848-295">**내부** 게시에 대한 경로를 게시하고 프런트 엔드 풀의 부하 균형 조정에 외부 웹 서비스의 FQDN(또는 있는 경우 Director 풀의 부하 균형 조정 서비스의 FQDN)을 입력해야 합니다. 예를 들어 sfb_pool01.contoso.local을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-295">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="fa848-296">게시할 경로로 _를 입력해야 하지만 원래 호스트 **/\\** 헤더\*\*를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-296">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="fa848-297">공개 또는 외부 이름 **세부 정보** 또는 정보에 대한 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-297">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="fa848-298">입력할 수 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-298">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="fa848-299">**요청을 수락하지만** 도메인 이름에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-299">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="fa848-300">이름 **에** **lyncdiscover를 입력해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-300">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="fa848-301"><sipdomain> 이 URL은 외부 자동iscover 서비스 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-301"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="fa848-302">이제 프런트 엔드 풀에서 외부 웹 서비스 URL에 대한 규칙을 만드는 경우 프런트 엔드 풀의 외부 웹 서비스에 대한 FQDN(예: lyncwebextpool01.contoso.com)을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-302">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="fa848-303">경로 옵션이  있으며 여기에 \* 를 **/\\** 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-303">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="fa848-304">최신 공용 인증서를 사용 하 여 **SSL 수신기** 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-304">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="fa848-305">**인증 위임은** **위임 안** 하도록 설정 해야 하지만 직접 클라이언트 인증을 **허용** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-305">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="fa848-306">규칙을 모든 **사용자로 설정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-306">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="fa848-307">이 규칙은 이 규칙을 만들고 계속 진행하는 데 필요한 모든 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-307">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="fa848-308">원래 호스트 헤더가 전달되도록  해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-308">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="fa848-309">웹 **서버** 포트도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-309">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="fa848-310">**HTTP 포트로** 요청을 리디렉션하고 포트 번호는 **8080 입니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-310">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="fa848-311">**SSL 포트로 요청을 리디렉션하고** 포트 번호는 **4443 입니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-311">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="fa848-312">모든 구성이 구성된 경우 이러한 규칙을 저장하거나 적용해야 합니다. 그런 다음 규칙을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-312">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="fa848-313">포트 80에 대한 웹 게시 규칙 만들기(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="fa848-313">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="fa848-314">역방향 프록시 인터페이스를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-314">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="fa848-315">웹 게시 규칙을 만드는 인터페이스에서 새로 만들기 또는 만들기 옵션을  선택해야  합니다(역방향 프록시 구성에 따라 메뉴 또는 탭에 있을 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="fa848-315">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="fa848-316">새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-316">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="fa848-317">일반적으로 다음 정보를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-317">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="fa848-318">**이름**: 규칙의 이름</span><span class="sxs-lookup"><span data-stu-id="fa848-318">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="fa848-319">**규칙 동작:** 이 경우 허용  규칙이면 역방향 프록시를 통해 무언가를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-319">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="fa848-320">선택하는 **게시** 규칙 또는 옵션은 단일 웹 사이트 또는 부하 균형 **조정기입니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-320">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="fa848-321">이 연결은 게시된 웹 서버 또는 팜에 연결하기 위한 보안되지 않은 **연결일 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-321">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="fa848-322">내부 게시에 대한 경로를 게시하고 프런트 엔드 풀의 부하 균형 조정의 **VIP** 주소에 대한 FQDN을 입력해야 합니다. 예를 들어 sfb_pool01.contoso.local을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-322">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="fa848-323">게시할 경로로 _를 입력해야 하지만 원래 호스트 **/\\** 헤더\*\*를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-323">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="fa848-324">공개 또는 외부 이름 **세부 정보** 또는 정보에 대한 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-324">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="fa848-325">입력할 수 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-325">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="fa848-326">**요청을 수락하지만** 도메인 이름에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-326">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="fa848-327">이름 **에** **lyncdiscover를 입력해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-327">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="fa848-328"><sipdomain> 이 URL은 외부 자동iscover 서비스 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-328"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="fa848-329">경로 옵션이  있으며 여기에 \* 를 **/\\** 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-329">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="fa848-330">웹 수신기 또는 역방향 프록시를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-330">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="fa848-331">**인증 위임은** **위임 안** 하도록 설정해야 하지만 직접 클라이언트 인증은 **허용되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-331">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="fa848-332">규칙을 모든 **사용자로 설정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-332">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="fa848-333">이 규칙은 이 규칙을 만들고 계속 진행하는 데 필요한 모든 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-333">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="fa848-334">웹 **서버** 포트를 설정해야 합니다. 다음을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-334">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="fa848-335">**HTTP 포트로** 요청을 리디렉션하고 포트 번호는 **8080 입니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-335">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="fa848-336">**SSL 포트로 요청을 리디렉션하고** 포트 번호는 **4443 입니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-336">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="fa848-337">모든 구성이 구성된 경우 이러한 규칙을 저장하거나 적용해야 합니다. 그런 다음 규칙을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-337">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="fa848-338">하이브리드 배포를 통해 모바일 기능을 위한 자동검사 구성</span><span class="sxs-lookup"><span data-stu-id="fa848-338">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="fa848-339"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="fa848-339"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="fa848-340">비즈니스용 Skype 서버의 하이브리드 환경은 사내 환경과 O365 환경을 결합하는 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-340">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="fa848-341">하이브리드 환경에서 비즈니스용 Skype 서버가 작동할 경우 자동 검색 서비스가 이러한 환경 중 하나에서 사용자를 찾을 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-341">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="fa848-342">모바일 클라이언트가 사용자의 위치를 검색할 수 있도록 자동 검색 서비스를 새 URL(Uniform Resource Locator)으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-342">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="fa848-343">그 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-343">The steps are:</span></span>
  
1. <span data-ttu-id="fa848-344">비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-344">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="fa848-345">다음을 실행하여 비즈니스용 Skype 서버 환경에 대한 **ProxyFQDN** 특성 값을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-345">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="fa848-346">그런 다음 셸 창에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-346">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="fa848-347">여기서 [identity]는 공유 SIP 주소 공간의 도메인 이름으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-347">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="fa848-348">모바일 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="fa848-348">Test your Mobility deployment</span></span>
<span data-ttu-id="fa848-349"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="fa848-349"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="fa848-350">비즈니스용 Skype 서버 Mobility Service 및 비즈니스용 Skype 서버 자동 검색 서비스를 배포한 후 테스트 트랜잭션을 실행하여 배포가 올바른지 확인하려는 경우</span><span class="sxs-lookup"><span data-stu-id="fa848-350">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="fa848-351">**Test-CsUcwaConference를** 실행하여 두 사용자가 회의에서 만들고 참가하고 통신할 수 있는 기능을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-351">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="fa848-352">이 테스트를 수행하려면 두 사용자(실제 또는 테스트)와 전체 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-352">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="fa848-353">이 명령은 비즈니스용 Skype 클라이언트와 Lync Server 2013 클라이언트 모두에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-353">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="fa848-354">비즈니스용 Skype 서버 2015의 Lync Server 2010 클라이언트의 경우 **Test-CsMcxP2PIM을** 실행하여 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="fa848-355">Lync Server 2010 사용자는 여전히 실제 사용자 또는 미리 정의한 테스트 사용자일 수 있으며 암호 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-355">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="fa848-356">레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-356">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="fa848-357">모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-357">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="fa848-358">MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-358">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="fa848-359">비즈니스용 Skype 및 Lync 2013 모바일 클라이언트에 대한 회의 테스트</span><span class="sxs-lookup"><span data-stu-id="fa848-359">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="fa848-360">비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 모든 컴퓨터에서 **CsAdministrator** 역할의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="fa848-361">비즈니스용 **Skype 서버** 관리 셸을 시작합니다(검색에  이름을 입력하거나 모든 프로그램으로 이동하여 선택할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="fa848-361">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="fa848-362">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-362">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="fa848-363">스크립트에서 자격 증명을 설정하고 테스트 cmdlet에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-363">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="fa848-364">아래 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa848-364">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="fa848-365">Lync 2010 모바일 클라이언트에 대한 테스트 회의</span><span class="sxs-lookup"><span data-stu-id="fa848-365">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="fa848-366">레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-366">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="fa848-367">모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-367">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="fa848-368">MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-368">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="fa848-369">비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 모든 컴퓨터에서 **CsAdministrator** 역할의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="fa848-370">비즈니스용 **Skype 서버** 관리 셸을 시작합니다(검색에  이름을 입력하거나 모든 프로그램으로 이동하여 선택할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="fa848-370">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="fa848-371">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-371">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="fa848-372">스크립트에서 자격 증명을 설정하고 테스트 cmdlet에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-372">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="fa848-373">아래 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa848-373">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="fa848-374">명령 절차를 더 검토하기 위해 [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) 및 [Test-CsMcxP2PIM을](/powershell/module/skype/test-csmcxp2pim?view=skype-ps)확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-374">To review the command procedures further, you can check out [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="fa848-375">푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="fa848-375">Configure for push notifications</span></span>
<span data-ttu-id="fa848-376"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="fa848-376"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="fa848-377">배지, 아이콘 또는 알림 형식의 푸시 알림은 Skype 또는 Lync 앱이 비활성일 때에도 모바일 장치로 전송될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-377">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="fa848-378">그러나 푸시 알림이란?</span><span class="sxs-lookup"><span data-stu-id="fa848-378">But what are push notifications?</span></span> <span data-ttu-id="fa848-379">새 IM 초대나 부재 중 IM 초대와 같은 이벤트 알림 또는 수신된 음성 메일에 대한 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-379">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="fa848-380">비즈니스용 Skype 서버 모바일 서비스는 이러한 알림을 클라우드 기반 비즈니스용 Skype 서버 푸시 알림 서비스로 전송한 다음 Windows Phone 사용자를 위해 MSNS(Microsoft 푸시 알림 서비스)에 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-380">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="fa848-381">이 기능은 Lync Server 2013에서 변경되지 않지만 비즈니스용 Skype 서버가 있는 경우 다음을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-381">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="fa848-382">비즈니스용 Skype 서버 에지 서버의 경우 새 호스팅 공급자인 Microsoft 비즈니스용 Skype Online을 추가한 다음 조직과 비즈니스용 Skype Online 간에 호스팅 공급자 페더링을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="fa848-382">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="fa848-383">**Set-CsPushNotificationConfiguration** cmdlet을 실행하여 푸시 알림을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-383">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="fa848-384">기본적으로 푸시 알림은 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-384">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="fa848-385">페더전 구성 및 푸시 알림을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-385">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="fa848-386">푸시 알림에 대해 비즈니스용 Skype 에지 서버 구성</span><span class="sxs-lookup"><span data-stu-id="fa848-386">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="fa848-387">**CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-387">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="fa848-388">비즈니스용 **Skype 서버 관리 셸을 시작합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-388">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fa848-389">비즈니스용 Skype 서버 온라인 호스팅 공급자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-389">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="fa848-390">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-390">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="fa848-391">단일 호스팅 공급자와의 페더링 관계를 두 개 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-391">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="fa848-392">따라서 sipfed.online.lync.com 페더링 관계가 있는 호스팅 공급자를 이미 설정한 경우 호스팅 공급자의 ID가 SkypeOnline이 아니어도 해당 공급자에 대해 다른 호스팅 공급자를 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-392">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="fa848-393">조직과 비즈니스용 Skype Online의 푸시 알림 서비스 간에 호스팅 공급자 페더링을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-393">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="fa848-394">명령줄에 다음을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-394">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="fa848-395">푸시 알림 사용</span><span class="sxs-lookup"><span data-stu-id="fa848-395">Enable push notifications</span></span>

1. <span data-ttu-id="fa848-396">**CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-396">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="fa848-397">비즈니스용 **Skype 서버 관리 셸을 시작합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-397">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fa848-398">푸시 알림을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="fa848-398">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="fa848-399">페더ation을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="fa848-399">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="fa848-400">페더ation 및 푸시 알림 테스트</span><span class="sxs-lookup"><span data-stu-id="fa848-400">Test federation and push notifications</span></span>

1. <span data-ttu-id="fa848-401">**CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-401">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="fa848-402">비즈니스용 **Skype 서버 관리 셸을 시작합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-402">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fa848-403">페더ation 구성을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-403">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="fa848-404">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-404">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="fa848-405">푸시 알림을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-405">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="fa848-406">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-406">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="fa848-407">모바일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="fa848-407">Configure Mobility policy</span></span>
<span data-ttu-id="fa848-408"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="fa848-408"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="fa848-409">비즈니스용 Skype 서버와 함께 모바일 서비스, 직장 전화, VoIP(Voice over IP) 또는 비디오를 사용할 수 있는 사용자와 VoIP 또는 비디오에 WiFi가 필요한지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-409">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="fa848-410">업무번호로 전화 기능을 사용하면 모바일 사용자가 전화를 걸고 받을 때 휴대폰 번호 대신 직장 전화 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-410">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="fa848-411">회선의 다른 끝에 있는 사용자는 모바일 사용자의 휴대폰 번호를 볼 수 없습니다. 이를 통해 모바일 사용자는 발신 전화 요금을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-411">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="fa848-412">VoIP 및 비디오가 설정되어 있는 경우 사용자는 VoIP 통화 및 비디오를 받아서 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-412">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="fa848-413">WiFi 사용 설정에 따라 사용자의 모바일 장치가 셀룰러 데이터 네트워크를 통해 WiFi 네트워크를 사용하는 데 필요한지 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-413">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="fa848-414">모바일 기능, 직장을 통한 통화 및 VoIP 및 비디오 기능은 모두 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-414">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="fa848-415">VoIP 및 비디오에 WiFi를 요구하는 설정은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-415">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="fa848-416">관리자는 전역, 사이트 또는 사용자에 따라 이를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-416">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="fa848-417">모바일 기능 및 직장을 통한 통화 기능을 사용하려면 사용자가 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-417">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="fa848-418">비즈니스용 Skype 서버에 사용</span><span class="sxs-lookup"><span data-stu-id="fa848-418">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="fa848-419">이 옵션을 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fa848-419">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="fa848-420">**EnableMobility** 옵션이 True로 설정된 모바일 **정책이 할당됩니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-420">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="fa848-421">사용자가 직장을 통해 전화를 사용할 수 있도록 하려면 다음도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-421">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="fa848-422">동시 전화 울림 사용 옵션이 선택된 음성 **정책이** 할당되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-422">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="fa848-423">**EnableOutsideVoice가 True로** 설정된 모바일 **정책이 할당됩니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-423">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fa848-424">Enterprise Voice 사용할 수 없는 사용자는 모바일 장치를 사용하여 Skype에서 Skype VoIP로 전화를 걸거나, 연결된 음성 정책에 대해 적절한 옵션이 설정된 경우 모바일 장치에서 클릭하여 참가 링크를 사용하여 전화 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-424">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="fa848-425">계획 항목에는 자세한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-425">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="fa848-426">전역 모바일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="fa848-426">Modify global Mobility policy</span></span>

1. <span data-ttu-id="fa848-427">**CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="fa848-428">비즈니스용 **Skype 서버 관리 셸을 시작합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fa848-429">다음을 입력하여 Mobility and Call via Work에 대한 액세스를 전역적으로 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-429">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="fa848-430">Mobility에 대한 액세스를 해제하지 않고 업무를 통한 통화를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-430">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="fa848-431">그러나 모바일 기능을 해제할 수 없는 경우 Work를 통한 통화도 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-431">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="fa848-432">자세한 내용은 [Set-CsMobilityPolicy를 참조하세요.](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="fa848-432">For more info, check out [Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="fa848-433">사이트당 모바일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="fa848-433">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="fa848-434">**CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-434">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="fa848-435">비즈니스용 **Skype 서버 관리 셸을 시작합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-435">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fa848-436">사이트 수준 정책을 만들고, VoIP 및 비디오를 끄고, IP 오디오에 WiFi 필요를 사용하도록 설정하고, 사이트당 IP 비디오에 WiFi 필요를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-436">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="fa848-437">유형:</span><span class="sxs-lookup"><span data-stu-id="fa848-437">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="fa848-438">자세한 내용은 [New-CsMobilityPolicy를 통해 자세히 알아보시고,](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="fa848-438">Learn more at [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="fa848-439">사용자에 따라 모바일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="fa848-439">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="fa848-440">**CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-440">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="fa848-441">비즈니스용 **Skype 서버 관리 셸을 시작합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa848-441">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fa848-442">사용자 수준 모바일 정책을 만들고 사용자에 의해 모바일 및 직장을 통한 통화를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-442">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="fa848-443">유형:</span><span class="sxs-lookup"><span data-stu-id="fa848-443">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="fa848-444">샘플 데이터가 있는 추가 예제:</span><span class="sxs-lookup"><span data-stu-id="fa848-444">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="fa848-445">Mobility에 대한 액세스를 해제하지 않고 업무를 통한 통화를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-445">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="fa848-446">그러나 모바일 기능을 해제할 수 없는 경우 Work를 통한 통화도 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa848-446">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
