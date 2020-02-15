---
title: 비즈니스용 Skype 서버에 대 한 모바일 기능 배포 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 모바일 기능을 활용할 수 있도록 하는 기존 비즈니스용 Skype 서버 설치를 구성 하는 단계를 안내 합니다.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029069"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="a4197-103">비즈니스용 Skype 서버에 대 한 모바일 기능 배포 및 구성</span><span class="sxs-lookup"><span data-stu-id="a4197-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="a4197-104">이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 모바일 기능을 활용할 수 있도록 하는 기존 비즈니스용 Skype 서버 설치를 구성 하는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="a4197-105">비즈니스용 [Skype 서버](../plan-your-deployment/mobility.md) 에 대 한 모바일 기능 계획을 검토 한 후에는 아래 단계를 계속 진행 하 여 비즈니스용 skype 서버 환경에 모바일 기능을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="a4197-106">단계는 다음과 같습니다 (이 표에 사용 권한 목록에 포함).</span><span class="sxs-lookup"><span data-stu-id="a4197-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="a4197-107">**작업 단계**</span><span class="sxs-lookup"><span data-stu-id="a4197-107">**Phase**</span></span>|<span data-ttu-id="a4197-108">**사용 권한**</span><span class="sxs-lookup"><span data-stu-id="a4197-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a4197-109">DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="a4197-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="a4197-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="a4197-110">Domain Admins</span></span>  <br/> <span data-ttu-id="a4197-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="a4197-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="a4197-112">인증서 수정</span><span class="sxs-lookup"><span data-stu-id="a4197-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="a4197-113">로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="a4197-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="a4197-114">역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="a4197-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="a4197-115">로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="a4197-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="a4197-116">하이브리드 배포를 사용 하 여 모바일 기능에 대 한 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="a4197-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="a4197-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="a4197-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="a4197-118">모바일 기능 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="a4197-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="a4197-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a4197-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="a4197-120">푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="a4197-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="a4197-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a4197-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="a4197-122">모바일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="a4197-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="a4197-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a4197-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="a4197-124">다음의 모든 섹션에는 계획 항목을 읽은 것으로 가정 하는 단계가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="a4197-125">혼란 스러운 경우에는 해당 정보를 자유롭게 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="a4197-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="a4197-126">이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a4197-127">현재 모든 비즈니스용 Skype 모바일 클라이언트는 IM (인스턴트 메시징), 현재 상태 및 연락처를 지원 하기 위해 이미 통합 커뮤니케이션 웹 API (c)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a4197-128">MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="a4197-129">DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="a4197-129">Create DNS records</span></span>
<span data-ttu-id="a4197-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="a4197-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="a4197-131">이러한 사용자는 비즈니스용 Skype 서버 환경에 포함 될 수 있지만 자동 검색을 사용 하려면 다음 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="a4197-132">조직의 네트워크 내에서 연결 하는 모바일 사용자를 지원 하기 위한 내부 DNS 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="a4197-133">조직의 네트워크 외부에서 연결 하는 모바일 사용자를 지원 하기 위한 외부 (또는 공용) DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="a4197-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="a4197-134">이러한 레코드는 (호스트) 이름 또는 CNAME 레코드 (둘 다 수행할 필요는 없음) 일 수 있으며 여기에는 모든 항목에 대 한 단계를 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="a4197-135">내부 DNS CNAME 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="a4197-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="a4197-136">**Domain Admins** 그룹의 구성원 이거나 **DnsAdmins** 그룹 인 네트워크의 DNS 서버에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="a4197-137">**시작**을 클릭 하 고 **관리 도구** (시작 메뉴에서 옵션을 선택 하지 않은 경우에는 **검색** 을 수행 해야 할 수도 있음)를 선택한 다음 **dns** 를 클릭 하 여 dns 관리 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="a4197-138">콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버의 프런트 엔드 서버에 대 한 홈 도메인으로 이동 하 고 여기에서 **정방향 조회 영역** 을 확장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="a4197-139">다음 중 어느 것이 있는지 잠시 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="a4197-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a4197-140">프런트 엔드 서버에 대 한 호스트 A 또는 AAAA 레코드 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 (s)</span><span class="sxs-lookup"><span data-stu-id="a4197-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a4197-141">디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="a4197-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="a4197-142">이에 대 한 설명이 나타나면 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **새 별칭 (CNAME)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="a4197-143">**별칭 이름** 텍스트 상자에 내부 자동 검색 서비스 URL에 대 한 lyncdiscoverinternal을 호스트 이름으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="a4197-144">**대상 호스트의 FQDN (정규화 된 도메인 이름**)에서 위의 4 단계에서 확인 한 프런트 엔드 풀 (또는 단일 프런트 엔드 서버, 디렉터 풀 또는 디렉터)에 대 한 내부 웹 서비스 FQDN을 입력 하거나 탐색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="a4197-145">이를 입력 하면 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="a4197-146">비즈니스용 Skype 서버 환경에서 지원 되는 각 SIP 도메인에 대해 정방향 조회 영역에 새 자동 검색 CNAME 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="a4197-147">외부 DNS CNAME 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="a4197-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="a4197-148">이러한 단계는 사용 중인 공용 DNS 공급자를 알 수 없지만, 계속 해 서 도움이 됩니다. 새 DNS 레코드를 만들 수 있는 계정을 사용 하 여 공용 DNS 공급자에 로그인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4197-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="a4197-149">이 시점에서는 비즈니스용 Skype 서버에 대 한 SIP 도메인이 이미 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="a4197-150">이 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 하거나, 그렇지 않은 경우에는이를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="a4197-151">다음 중 어느 것이 있는지 잠시 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="a4197-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a4197-152">프런트 엔드 서버에 대 한 호스트 A 또는 AAAA 레코드 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 (s)</span><span class="sxs-lookup"><span data-stu-id="a4197-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a4197-153">디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="a4197-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="a4197-154">이러한 정보를 확인 한 후에는 **새 별칭 (CNAME)** 을 만드는 옵션을 선택할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="a4197-155">이제 **별칭 이름을**입력할 수 있으며, 외부 자동 검색 서비스 URL에 대해 lyncdiscover를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="a4197-156">다음에는 **대상 호스트에 대해 fqdn**에 입력할 영역이 있어야 하며 위의 3 단계에서 확인 한 프런트 엔드 풀 (또는 단일 프런트 엔드 서버, 디렉터 풀 또는 디렉터)에 대 한 fqdn 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="a4197-157">여기에 저장 해야 하거나, 비즈니스용 Skype 서버 환경에서 각 SIP 도메인의 정방향 조회 영역에 추가 CNAME 레코드를 만들어야 하는 경우에는 해당 작업을 수행 해야 하지만 준비가 완료 되 면 작업이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="a4197-158">내부 DNS A 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="a4197-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="a4197-159">**Domain Admins** 그룹의 구성원 이거나 **DnsAdmins** 그룹 인 네트워크의 DNS 서버에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="a4197-160">**시작**을 클릭 하 고 **관리 도구** (시작 메뉴에서 옵션을 선택 하지 않은 경우에는 **검색** 을 수행 해야 할 수도 있음)를 선택한 다음 **dns** 를 클릭 하 여 dns 관리 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="a4197-161">콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버의 프런트 엔드 서버에 대 한 홈 도메인으로 이동 하 고 여기에서 **정방향 조회 영역** 을 확장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="a4197-162">다음 중 어느 것이 있는지 잠시 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="a4197-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a4197-163">프런트 엔드 서버에 대 한 호스트 A 또는 AAAA 레코드 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 (s)</span><span class="sxs-lookup"><span data-stu-id="a4197-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a4197-164">디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="a4197-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="a4197-165">이에 대 한 설명이 나타나면 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **새 호스트 (A 또는 AAAA)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="a4197-166">**이름** 텍스트 상자에 내부 자동 검색 서비스 URL에 대 한 lyncdiscoverinternal을 호스트 이름으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="a4197-167">**IP 주소** 텍스트 상자에 위의 4 단계에서 확인 한 프런트 엔드 풀 (또는 단일 프런트 엔드 서버, 디렉터 풀 또는 디렉터)에 대 한 내부 웹 서비스 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="a4197-168">이 작업이 완료 되 면 **호스트 추가**를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="a4197-169">비즈니스용 Skype 서버 환경에서 지원 되는 각 SIP 도메인에 대해 정방향 조회 영역에 새 자동 검색 A 또는 AAAA 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="a4197-170">이 작업을 수행 하려면 6-8 단계를 필요한 만큼 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="a4197-171">작업을 마치면 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="a4197-172">외부 DNS A 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="a4197-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="a4197-173">이러한 단계는 사용 중인 공용 DNS 공급자를 알 수 없지만, 계속 해 서 도움이 됩니다. 새 DNS 레코드를 만들 수 있는 계정을 사용 하 여 공용 DNS 공급자에 로그인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4197-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="a4197-174">이 시점에서는 비즈니스용 Skype 서버에 대 한 SIP 도메인이 이미 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="a4197-175">이 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 하거나, 그렇지 않은 경우에는이를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="a4197-176">다음 중 어느 것이 있는지 잠시 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="a4197-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a4197-177">프런트 엔드 서버에 대 한 호스트 A 또는 AAAA 레코드 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 (s)</span><span class="sxs-lookup"><span data-stu-id="a4197-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a4197-178">디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="a4197-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="a4197-179">이러한 정보를 확인 한 후에는 **새 호스트 a 또는 AAAA**를 만드는 옵션을 선택할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="a4197-180">이제 **이름을**입력할 수 있으며, 외부 자동 검색 서비스 URL에 대해 lyncdiscover를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="a4197-181">다음에는 **IP Addresss**에 입력할 영역을 입력 해야 하며 위의 3 단계에서 확인 한 프런트 엔드 풀 (또는 단일 프런트 엔드 서버 또는 디렉터 풀 또는 감독)의 IP 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="a4197-182">여기에 저장 해야 하거나, 비즈니스용 Skype 서버 환경에 대 한 각 SIP 도메인의 정방향 조회 영역에서 추가 A 또는 AAAA 레코드를 만들어야 하는 경우에는 해당 작업을 수행 해야 하지만 준비가 완료 되 면 작업이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="a4197-183">인증서 수정</span><span class="sxs-lookup"><span data-stu-id="a4197-183">Modify certificates</span></span>
<span data-ttu-id="a4197-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a4197-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="a4197-185">인증서를 계획 하는 방법에 대 한 질문이 있는 경우 [비즈니스용 Skype 서버](../plan-your-deployment/mobility.md) 에 대 한 모바일 기능 계획 문서에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="a4197-186">검토 한 후에는 다음을 안내해 드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="a4197-187">새 인증서가 필요 합니까?</span><span class="sxs-lookup"><span data-stu-id="a4197-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="a4197-188">CA (인증 기관)에서 새 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="a4197-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="a4197-189">PowerShell을 사용 하 여 대체 항목을 사용 하 여 원본 위치 인증서 업데이트</span><span class="sxs-lookup"><span data-stu-id="a4197-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="a4197-190">MMC (Microsoft Management Console)에서 인증서 스냅인을 사용 하 여 인증서를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="a4197-191">새 인증서가 필요 합니까?</span><span class="sxs-lookup"><span data-stu-id="a4197-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="a4197-192">먼저 현재 위치에 있는 인증서와 필요한 항목이 있는지 여부를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="a4197-193">이렇게 하려면 로컬 관리자 인 계정을 사용 하 여 비즈니스용 Skype 서버에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="a4197-194">이 계정에는 이러한 단계 중 일부에 대해 발급 하는 CA (인증 기관)에 대 한 권한도 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="a4197-195">비즈니스용 Skype 서버 관리 셸을 엽니다 (검색을 사용 하 여 시작 메뉴나 작업 표시줄에 고정 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="a4197-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="a4197-196">업데이트 된 인증서를 추가 하기 전에 어떤 인증서가 할당 되었는지 반드시 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="a4197-197">명령에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="a4197-198">3 단계의 정보는 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="a4197-199">여러 항목에 할당 된 단일 인증서가 있는지 또는이를 필요로 하는 다른 구성 요소에 대해 다른 인증서를 할당 했는지 확인 하기 위해이 방법을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="a4197-200">**Use** 매개 변수를 사용 하 여 인증서를 사용 하는 방법을 결정 하 고, **지문** 매개 변수는 모두 동일한 인증서 또는 여러 인증을 갖는 경우를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="a4197-201">이 계획 섹션에서 SAN 항목을 권장 하는 경우에는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="a4197-202">그렇지 않으면 인증 기관에서 새 인증서 또는 구성에 따라 여러 인증서를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="a4197-203">CA (인증 기관)에서 새 인증서 또는 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="a4197-204">보유 하 고 있는 SAN 항목을 확인 한 후에는 **단일 인증서** (위 단계를 통해 확인 한 후)가 있고 필요한 항목이 모두 없는 것을 알게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="a4197-205">새 인증서 요청을 CA에 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="a4197-206">비즈니스용 Skype 서버 PowerShell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="a4197-207">자동 검색 서비스 SAN의 경우 (-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기)</span><span class="sxs-lookup"><span data-stu-id="a4197-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="a4197-208">이제 여러 SIP 도메인이 있는 경우 위의 예제와 같이 AllSipDomain 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="a4197-209">대신 DomainName 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="a4197-210">또한 DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="a4197-211">예를 들면 (-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기).</span><span class="sxs-lookup"><span data-stu-id="a4197-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="a4197-212">또한 어떤 SAN 항목이 있는지 확인 한 후에는 필요한 항목을 모두 포함 하지 않은 **인증서가 여러** 개 있다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="a4197-213">새 인증서 요청을 CA에 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="a4197-214">비즈니스용 Skype 서버 PowerShell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="a4197-215">자동 검색 서비스 SAN의 경우 (-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기)</span><span class="sxs-lookup"><span data-stu-id="a4197-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="a4197-216">이제 여러 SIP 도메인이 있는 경우 위의 예제와 같이 AllSipDomain 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="a4197-217">대신 DomainName 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="a4197-218">또한 DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="a4197-219">예를 들면 (-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기).</span><span class="sxs-lookup"><span data-stu-id="a4197-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="a4197-220">CA에서 새 인증서를 생성 한 후에는 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a4197-221">비즈니스용 Skype 서버 관리 셸을 사용 하 여 인증서 할당</span><span class="sxs-lookup"><span data-stu-id="a4197-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="a4197-222">위의 새 인증 필요 섹션에 나와 있는 항목에 따라 다음 중 **하나** 를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="a4197-223">모든 항목에 대 한 인증서가 하나인 경우 (지문이 동일)이 작업을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="a4197-224">다른 항목에 대 한 여러 인증서가 있는 경우 (지문을 모두 다른 경우) 대신 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="a4197-225">MMC (Microsoft Management Console)에서 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="a4197-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="a4197-226">MMC의 인증서 스냅인을 사용 하 여 인증서를 확인할 수 있는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="a4197-227">검색에 MMC를 입력 하 고 응용 프로그램 옵션으로 팝업 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="a4197-228">인증서 스냅인을 추가 하려면 **파일**을 클릭 한 다음 **스냅인 추가/제거 ...** (또는 바로 가기 **키 Ctrl + M** 도 작동) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="a4197-229">**인증서** 는 왼쪽 창에서 옵션이 되며, 해당 옵션을 선택한 다음 팝업 창에서 **컴퓨터 계정을** 선택 하 고 다음 **을 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a4197-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="a4197-230">여전히 팝업 창에서 확인 해야 하는 인증서에 대 한 홈 인 컴퓨터에서이 작업을 수행할 수 있으므로이 경우 **로컬 컴퓨터** 에서 선택 항목을 그대로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="a4197-231">원격 컴퓨터에서 작업 하는 경우 라디오 단추를 **다른 컴퓨터로** 변경한 다음 해당 컴퓨터의 FQDN을 입력 하거나, **찾아보기** 단추를 사용 하 여 AD를 통해 해당 컴퓨터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="a4197-232">컴퓨터를 선택한 후 준비가 되 면 **마침을** 클릭 하 고 **확인** 을 누른 다음 MMC에 스냅인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="a4197-233">MMC의 왼쪽 창에서 **인증서** 섹션을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="a4197-234">**개인** 폴더도 확장 한 다음 **인증서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="a4197-235">이를 통해이 저장소의 인증서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="a4197-236">보려는 인증서를 찾아서 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a4197-237">인증서가 무엇 인지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a4197-237">How do you know what certificate this is?</span></span> <span data-ttu-id="a4197-238">여기에는 팜의 모든 항목에 할당 된 단일 인증서가 있거나, 기본, 내부 웹 서비스 등의 다른 항목에 대 한 인증서가 여러 개 있을 수 있으며,이 경우에는 여러 인증서를 확인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="a4197-239">여러 인증서에는 동일한 지문이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="a4197-240">**인증서** 보기를 확인 한 후 **자세히**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="a4197-241">이렇게 하면 **주체**를 선택 하면 인증서 주체 이름이 표시 되 고 지정 된 주체 이름 및 관련 속성이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="a4197-242">또한 **주체 대체 이름** 항목을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="a4197-243">다음 중 하나 이상의 항목을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="a4197-244">이 풀의 풀 이름 또는 단일 서버 이름 (풀이 아닌 경우)</span><span class="sxs-lookup"><span data-stu-id="a4197-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="a4197-245">인증서가 할당 된 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="a4197-246">단순 URL 레코드 (일반적으로 모임 및 전화 접속)</span><span class="sxs-lookup"><span data-stu-id="a4197-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="a4197-247">웹 서비스 내부 및 웹 서비스 외부 이름 (예: webpool01.contoso.net, webpool01.contoso.com)-토폴로지 작성기 및 재정의를 사용한 웹 서비스 선택에 대 한 선택 사항에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="a4197-248">이미 지정 된 경우 lyncdiscover입니다. \<microsoft.rtc.management.xds.sipdomain object\> 및 lyncdiscoverinternal \<microsoft.rtc.management.xds.sipdomain object\> 레코드</span><span class="sxs-lookup"><span data-stu-id="a4197-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="a4197-249">할당 된 인증서가 두 개 이상인 경우에는 여러 보증서를 확인 해야 합니다 (위의 참고 사항 확인).</span><span class="sxs-lookup"><span data-stu-id="a4197-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="a4197-250">따라서 lyncdiscover가 발견 되 면이 방법을 사용할 수 있습니다. \<microsoft.rtc.management.xds.sipdomain object\> 및 lyncdiscoverinternal \<microsoft.rtc.management.xds.sipdomain object\> 레코드가 이미 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="a4197-251">MMC를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="a4197-252">할당 되지 않은 경우에는 위에서 설명한 새 인증서 요청을 만들거나 요청 후에 설치 해야 합니다 (위의 PowerShell을 먼저 수행 하는 것이 좋습니다).</span><span class="sxs-lookup"><span data-stu-id="a4197-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="a4197-253">역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="a4197-253">Configure the reverse proxy</span></span>
<span data-ttu-id="a4197-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="a4197-254"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="a4197-255">아래 단계는 정확히 따라야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="a4197-256">이전 버전의 제품에서 TMG (위협 관리 게이트웨이) 구성,이를 사용 하지 않은 경우에는 사용자가 해당 버전에서 직접 작업을 수행 해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="a4197-257">TMG가 Microsoft에서 제품으로 더 이상 제공 되지 않으며 여전히 구성 해야 하는 경우 [Lync Server 2013 단계](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="a4197-258">그러나 다음 정보는 모든 역방향 프록시에 대 한 특정 연습 단계를 제공할 수 있는 방법이 없더라도 더 일반적으로 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="a4197-259">다음과 같은 두 가지 주요 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="a4197-260">HTTPS를 통한 초기 자동 검색 요청을 수행할 것인가 (권장)?</span><span class="sxs-lookup"><span data-stu-id="a4197-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="a4197-261">웹 게시 규칙이 있는 경우 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="a4197-262">아직 웹 게시 규칙이 없는 경우에는 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="a4197-263">HTTP를 통한 초기 자동 검색 요청을 수행 하는 경우 해당 규칙도 만들거나 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a4197-264">**중요** 프록시 제한 시간 값은 배포에 따라 달라 지는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="a4197-265">배포를 모니터링 하 고 클라이언트의 모범 환경에 맞게 값을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="a4197-266">200 보다 낮은 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="a4197-267">사용자 환경에서 Lync 모바일 클라이언트를 지 원하는 경우 시간 제한 값이 900 인 Office 365에서 푸시 알림 시간 제한을 허용 하려면이 값을 960로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="a4197-268">값이 너무 낮을 때 클라이언트 연결이 끊어지지 않도록 하려면 시간 제한 값을 늘려야 하며, 그렇지 않으면 프록시를 통한 연결이 끊어지지 않으면 숫자를 줄이고 클라이언트 연결이 끊어진 후에는 장시간 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="a4197-269">이 값에 대 한 적절 한 설정을 결정 하는 유일한 방법은 사용자 환경에서 일반적으로 수행 하는 작업의 모니터링 및 기준 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="a4197-270">외부 자동 검색 SAN 및 URL에 대 한 기존 웹 게시 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="a4197-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="a4197-271">역방향 프록시 인터페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a4197-272">웹 게시 규칙을 찾고, 역방향 프록시 구성에 따라 메뉴 또는 탭에 있는 편집 옵션을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="a4197-273">이 웹 게시 규칙이 적용 되는 대상을 나타내는 영역이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="a4197-274">수신 사이트 또는 사이트 요청에 대해이 규칙을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="a4197-275">새 항목을 **추가** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="a4197-276">자동 검색 사이트의 이름 (사용 하는 예제는 lyncdiscover.contoso.com)을 입력 하 고 역방향 프록시 형식에 따라 **확인** 또는 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="a4197-277">자동 검색 SAN 항목을 포함 하는 새 인증서가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="a4197-278">설치 해야 하 고 역방향 프록시 설정에 따라 사용 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="a4197-279">구성이 완료 되 면 모든 사항을 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="a4197-280">역방향 프록시에 **테스트** 기능이 있는 경우 해당 기능을 사용 하 여 모든 기능이 제대로 작동 하는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4197-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="a4197-281">이제 환경에 디렉터 또는 디렉터 풀이 있는 경우 이러한 단계를 반복 해야 할 수도 있습니다 (이는 두 번째 규칙이 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="a4197-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="a4197-282">외부 자동 검색 URL에 대 한 웹 게시 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="a4197-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="a4197-283">역방향 프록시 인터페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a4197-284">인터페이스에서 웹 게시 규칙을 만드는 위치를 찾고, **새** 또는 **만들기** 옵션 (역방향 프록시 구성에 따라 메뉴나 탭에 있을 수 있음)을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="a4197-285">새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="a4197-286">일반적으로는 다음 정보를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="a4197-287">**이름**: 규칙의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="a4197-288">**규칙 동작**:이 경우에는 사용자가 역방향 프록시를 통과 하는 것이 **허용** 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="a4197-289">선택 하는 **게시** 규칙이 나 옵션은 **단일 웹 사이트 또는 부하 분산 장치**입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="a4197-290">외부 액세스용으로 **SSL** 을 사용 해야 하는 경우 해당 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="a4197-291">**내부 게시용**경로를 게시 하 고 프런트 엔드 풀의 부하 분산 장치 (또는 디렉터 풀의 부하 분산 장치에 있는 경우 fqdn)에 외부 웹 서비스의 fqdn을 입력 해야 하는 경우에는 예를 sfb_pool01 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="a4197-292">게시할 경로에 \*\* / \*\*\*를 입력 해야 하지만, **원본 호스트 헤더도 전달**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="a4197-293">**공용 또는 외부 이름** 세부 정보 또는 정보에 대 한 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="a4197-294">이 위치는 다음을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="a4197-295">**요청을 수락**하지만이 이름은 도메인 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="a4197-296">**이름**에는 **lyncdiscover** 를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="a4197-297"><sipdomain>(이것은 외부 자동 검색 서비스 URL)입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="a4197-298">이제 프런트 엔드 풀에서 외부 웹 서비스 URL에 대 한 규칙을 만드는 경우 프런트 엔드 풀의 외부 웹 서비스에 대 한 FQDN (예: lyncwebextpool01.contoso.com)을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="a4197-299">여기에는 **경로** 옵션이 있으며 \* 여기에 입력 \*\* / \*\*해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="a4197-300">최신 공용 인증서를 사용 하 여 **SSL 수신기** 를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="a4197-301">**인증 위임은** **위임 안 함**으로 설정 해야 하지만 직접 클라이언트 인증을 허용 **해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="a4197-302">**모든 사용자**에 대해 규칙을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="a4197-303">이 규칙을 만드는 데 필요한 모든 정보를 확인 하 고 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="a4197-304">**원래 호스트 헤더가** 전달 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="a4197-305">**웹 서버** 포트도 함께 설정 해야 하는 경우 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="a4197-306">**요청을 HTTP 포트로 리디렉션하고** 포트 번호는 **8080**이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="a4197-307">**요청을 SSL 포트로 리디렉션하고** 포트 번호는 **4443**이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="a4197-308">모든 것이 구성 되어 있으면 이러한 항목을 저장 하거나 적용 한 다음 규칙을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="a4197-309">포트 80에 대 한 웹 게시 규칙 만들기 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a4197-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="a4197-310">역방향 프록시 인터페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a4197-311">인터페이스에서 웹 게시 규칙을 만드는 위치를 찾고, **새** 또는 **만들기** 옵션 (역방향 프록시 구성에 따라 메뉴나 탭에 있을 수 있음)을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="a4197-312">새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="a4197-313">일반적으로는 다음 정보를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="a4197-314">**이름**: 규칙의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="a4197-315">**규칙 동작**:이 경우에는 사용자가 역방향 프록시를 통과 하는 것이 **허용** 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="a4197-316">선택 하는 **게시** 규칙이 나 옵션은 **단일 웹 사이트 또는 부하 분산 장치**입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="a4197-317">이 연결을 통해 **게시 된 웹 서버 또는 팜에 연결 하려면 보안 되지 않은 연결이**필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="a4197-318">**내부 게시용**경로를 게시 하 고 프런트 엔드 풀의 부하 분산 장치 **VIP 주소** 에 대 한 FQDN을 입력 해야 하는 경우에는 예제 sfb_pool01 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="a4197-319">게시할 경로에 \*\* / \*\*\*를 입력 해야 하지만, **원본 호스트 헤더도 전달**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="a4197-320">**공용 또는 외부 이름** 세부 정보 또는 정보에 대 한 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="a4197-321">이 위치는 다음을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="a4197-322">**요청을 수락**하지만이 이름은 도메인 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="a4197-323">**이름**에는 **lyncdiscover** 를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="a4197-324"><sipdomain>(이것은 외부 자동 검색 서비스 URL)입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="a4197-325">여기에는 **경로** 옵션이 있으며 \* 여기에 입력 \*\* / \*\*해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="a4197-326">웹 수신기를 선택 하거나 역방향 프록시가 직접 만들도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="a4197-327">**인증 위임은** **위임 안 함**으로 설정 해야 하지만 직접 클라이언트 인증은 허용 **하지 않아야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="a4197-328">**모든 사용자**에 대해 규칙을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="a4197-329">이 규칙을 만드는 데 필요한 모든 정보를 확인 하 고 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="a4197-330">**웹 서버** 포트를 설정 해야 하는 경우에는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="a4197-331">**요청을 HTTP 포트로 리디렉션하고** 포트 번호는 **8080**이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="a4197-332">**요청을 SSL 포트로 리디렉션하고** 포트 번호는 **4443**이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="a4197-333">모든 것이 구성 되어 있으면 이러한 항목을 저장 하거나 적용 한 다음 규칙을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="a4197-334">하이브리드 배포를 사용 하 여 모바일 기능에 대 한 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="a4197-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="a4197-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="a4197-335"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="a4197-336">비즈니스용 Skype 서버의 하이브리드 환경은 온-프레미스 및 O365 환경을 결합 하는 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="a4197-337">비즈니스용 Skype 서버가 하이브리드 환경에서 작동 하는 경우 자동 검색 서비스가 이러한 환경 중 하나에서 사용자를 찾을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="a4197-338">모바일 클라이언트가 사용자가 위치한 위치를 검색 하도록 하려면 자동 검색 서비스를 새로운 URL (uniform resource locator)을 사용 하 여 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="a4197-339">그 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-339">The steps are:</span></span>
  
1. <span data-ttu-id="a4197-340">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="a4197-341">다음을 실행 하 여 비즈니스용 Skype 서버 환경에 대 한 **Proxyfqdn** 특성 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="a4197-342">그리고 나 서 셸 창에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="a4197-343">여기서 [identity]는 공유 SIP 주소 공간의 도메인 이름으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="a4197-344">모바일 기능 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="a4197-344">Test your Mobility deployment</span></span>
<span data-ttu-id="a4197-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="a4197-345"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="a4197-346">비즈니스용 Skype 서버 모바일 서비스 및 비즈니스용 Skype 서버 자동 검색 서비스를 배포한 후에는 테스트 트랜잭션을 실행 하 여 배포의 작업 권한을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="a4197-347">**Test-csucwaconference** 를 실행 하 여 두 사용자가 회의에서 생성, 참가 및 통신 하는 기능을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="a4197-348">이 테스트를 수행 하려면 두 명의 사용자 (실제 또는 테스트)와 전체 자격 증명이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="a4197-349">이 명령은 Lync Server 2013 클라이언트 뿐만 아니라 비즈니스용 Skype 클라이언트에 대해서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="a4197-350">Lync Server 2010 클라이언트 (비즈니스용 Skype 서버 2015)의 경우 테스트 하려면 **test-csmcxp2pim** 를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="a4197-351">Lync Server 2010 사용자는 여전히 실제 사용자 이거나 미리 정의 된 테스트 사용자 여야 하며, 암호 자격 증명이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="a4197-352">이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a4197-353">현재 모든 비즈니스용 Skype 모바일 클라이언트는 IM (인스턴트 메시징), 현재 상태 및 연락처를 지원 하기 위해 이미 통합 커뮤니케이션 웹 API (c)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a4197-354">MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="a4197-355">비즈니스용 Skype 및 Lync 2013 모바일 클라이언트에 대 한 테스트 회의</span><span class="sxs-lookup"><span data-stu-id="a4197-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="a4197-356">**비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 설치 된 모든 컴퓨터에서 **csadministrator** 역할의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a4197-357">**비즈니스용 Skype 서버 관리 셸을** 시작 합니다 (검색에 이름을 입력 하거나 **모든 프로그램** 으로 이동한 후 선택할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="a4197-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="a4197-358">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="a4197-359">또한 스크립트에 자격 증명을 설정 하 고이를 테스트 cmdlet에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="a4197-360">이에 대 한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-360">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="a4197-361">Lync 2010 모바일 클라이언트에 대 한 테스트 회의</span><span class="sxs-lookup"><span data-stu-id="a4197-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="a4197-362">이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a4197-363">현재 모든 비즈니스용 Skype 모바일 클라이언트는 IM (인스턴트 메시징), 현재 상태 및 연락처를 지원 하기 위해 이미 통합 커뮤니케이션 웹 API (c)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a4197-364">MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="a4197-365">**비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 설치 된 모든 컴퓨터에서 **csadministrator** 역할의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a4197-366">**비즈니스용 Skype 서버 관리 셸을** 시작 합니다 (검색에 이름을 입력 하거나 **모든 프로그램** 으로 이동한 후 선택할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="a4197-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="a4197-367">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="a4197-368">또한 스크립트에 자격 증명을 설정 하 고이를 테스트 cmdlet에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="a4197-369">이에 대 한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-369">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="a4197-370">명령 절차를 자세히 검토 하려면 [test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 및 [test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4197-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="a4197-371">푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="a4197-371">Configure for push notifications</span></span>
<span data-ttu-id="a4197-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="a4197-372"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="a4197-373">배지, 아이콘 또는 경고 형태의 푸시 알림은 Skype 또는 Lync 앱이 비활성 상태인 경우에도 모바일 장치로 전송 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="a4197-374">하지만 푸시 알림은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="a4197-374">But what are push notifications?</span></span> <span data-ttu-id="a4197-375">이러한 알림은 신규 또는 누락 된 IM 초대 또는 받은 음성 메일과 같은 이벤트 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="a4197-376">비즈니스용 Skype 서버 모바일 서비스에서는 이러한 알림을 클라우드 기반 비즈니스용 Skype 서버 푸시 알림 서비스로 보내 Windows Phone 사용자를 위해 MSNS (Microsoft 푸시 알림 서비스)로 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="a4197-377">이 기능은 Lync Server 2013에서 변경 되지 않았지만, 비즈니스용 Skype 서버가 있는 경우 다음을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="a4197-378">비즈니스용 Skype 서버에 지 서버에 대해 새 호스팅 공급자, Microsoft 비즈니스용 Skype Online을 추가 하 고 조직과 비즈니스용 Skype Online 간에 호스팅 공급자 페더레이션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="a4197-379">**Get-cspushnotificationconfiguration** cmdlet을 실행 하 여 푸시 알림을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="a4197-380">기본적으로 푸시 알림은 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="a4197-381">페더레이션 구성 및 푸시 알림을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="a4197-382">푸시 알림을 위해 비즈니스용 Skype에 지 서버 구성</span><span class="sxs-lookup"><span data-stu-id="a4197-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="a4197-383">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a4197-384">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a4197-385">비즈니스용 Skype 서버 온라인 호스팅 공급자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="a4197-386">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="a4197-387">단일 호스팅 공급자와 페더레이션 관계를 둘 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="a4197-388">따라서 sipfed.online.lync.com와 페더레이션 관계가 있는 호스팅 공급자를 이미 설정한 경우 호스팅 공급자의 id가 SkypeOnline 이외의 다른 호스팅 공급자를 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="a4197-389">비즈니스용 Skype Online에서 조직과 푸시 알림 서비스 간의 호스팅 공급자 페더레이션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="a4197-390">명령줄에 다음을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="a4197-391">푸시 알림 사용</span><span class="sxs-lookup"><span data-stu-id="a4197-391">Enable push notifications</span></span>

1. <span data-ttu-id="a4197-392">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a4197-393">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a4197-394">푸시 알림 사용:</span><span class="sxs-lookup"><span data-stu-id="a4197-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="a4197-395">페더레이션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="a4197-396">테스트 페더레이션 및 푸시 알림</span><span class="sxs-lookup"><span data-stu-id="a4197-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="a4197-397">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a4197-398">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a4197-399">페더레이션 구성을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="a4197-400">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="a4197-401">푸시 알림을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="a4197-402">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="a4197-403">모바일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="a4197-403">Configure Mobility policy</span></span>
<span data-ttu-id="a4197-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="a4197-404"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="a4197-405">비즈니스용 Skype 서버에서 모바일 서비스를 사용할 수 있는 사람, 직장에서의 통화, VoIP (voice over IP) 또는 비디오를 확인 하 고 VoIP 또는 비디오에 대해 WiFi가 필요한 지 여부를 결정 하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="a4197-406">회사 번호로 전화를 걸어 통화를 걸고 받을 때 모바일 사용자가 자신의 회사 전화 번호 대신 사무실 전화번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="a4197-407">줄의 다른 쪽 끝에 있는 사람은 휴대폰 번호가 모바일 사용자의 휴대폰 번호를 볼 수 없으며,이를 통해 해당 사용자가 발신 전화 요금을 방지할 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="a4197-408">VoIP 및 비디오가 설정 되 면 사용자는 VoIP 통화 및 비디오를 만들고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="a4197-409">WiFi 사용에 대 한 설정에 따라 사용자의 모바일 장치에서 셀룰러 데이터 네트워크를 통해 WiFi 네트워크를 사용 해야 하는지 여부가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="a4197-410">이동성, 회사 전화 통화 및 VoIP 및 비디오 기능은 모두 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="a4197-411">VoIP 및 비디오용으로 WiFi를 요구 하는 설정을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="a4197-412">관리자는 전역, 사이트 또는 사용자별로이를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="a4197-413">모바일 기능을 사용 하 고 작업을 통해 전화를 걸려면 사용자는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="a4197-414">비즈니스용 Skype 서버 사용</span><span class="sxs-lookup"><span data-stu-id="a4197-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="a4197-415">Enterprise Voice를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="a4197-416">**EnableMobility** 옵션이 **True**로 설정 된 이동성 정책이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="a4197-417">사용자가 회사 번호로 전화를 걸 수 있으려면 다음 작업도 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="a4197-418">**동시 전화 신호 울림 사용** 옵션이 선택 된 음성 정책이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="a4197-419">**EnableOutsideVoice** 이 **True**로 설정 된 이동성 정책이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a4197-420">Enterprise Voice를 사용 하도록 설정 하지 않은 사용자는 모바일 장치를 사용 하 여 skype VoIP 통화를 수행 하거나, 연결 된 음성 정책에 대 한 적절 한 옵션이 설정 된 경우 모바일 장치에서 클릭 하 여 링크를 참가 시켜 회의에 참가할 수 있습니다. 으.</span><span class="sxs-lookup"><span data-stu-id="a4197-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="a4197-421">계획 항목에서는 더 자세하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="a4197-422">전역 이동성 정책 수정</span><span class="sxs-lookup"><span data-stu-id="a4197-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="a4197-423">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a4197-424">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a4197-425">다음을 입력 하 여 모바일 기능에 대 한 액세스를 해제 하 고 전체 직장에 전화</span><span class="sxs-lookup"><span data-stu-id="a4197-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="a4197-426">모바일 기능에 대 한 액세스를 해제 하지 않고 작업을 통해 통화를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="a4197-427">그러나 작업을 통해 통화를 끄지 않고 모바일 기능을 끌 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="a4197-428">자세한 내용은 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4197-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="a4197-429">사이트별 모바일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="a4197-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="a4197-430">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a4197-431">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a4197-432">사이트 수준 정책을 만들고, VoIP 및 비디오를 끄고, IP 오디오에 대해 WiFi 필요를 사용 하도록 설정 하 고, 사이트 별로 IP 비디오용 WiFi를 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="a4197-433">형식일</span><span class="sxs-lookup"><span data-stu-id="a4197-433">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="a4197-434">자세한 내용은 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4197-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="a4197-435">사용자별 모바일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="a4197-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="a4197-436">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a4197-437">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a4197-438">사용자 수준 이동성 정책을 만들고 사용자 별 작업을 통해 이동성 및 통화를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="a4197-439">형식일</span><span class="sxs-lookup"><span data-stu-id="a4197-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="a4197-440">예제 데이터가 포함 된 추가 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="a4197-441">모바일 기능에 대 한 액세스를 해제 하지 않고 작업을 통해 통화를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="a4197-442">그러나 작업을 통해 통화를 끄지 않고 모바일 기능을 끌 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4197-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

