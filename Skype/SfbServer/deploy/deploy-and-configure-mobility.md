---
title: 비즈니스용 Skype 서버에 대 한 이동성 배포 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 이동성 기능을 활용할 수 있도록 하기 위해 기존 비즈니스용 Skype Server 설치를 구성 하는 단계를 안내 합니다.
ms.openlocfilehash: 910e23e8aec18d36c3a7e4bda9e97828fb498802
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234577"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="5b7aa-103">비즈니스용 Skype 서버에 대 한 이동성 배포 및 구성</span><span class="sxs-lookup"><span data-stu-id="5b7aa-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="5b7aa-104">이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 이동성 기능을 활용할 수 있도록 하기 위해 기존 비즈니스용 Skype Server 설치를 구성 하는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="5b7aa-105">비즈니스용 [Skype server 문서에 대 한 이동성 계획](../plan-your-deployment/mobility.md) 을 검토 한 후 아래 단계를 진행 하 여 비즈니스용 skype server 환경에 이동성을 배포할 준비가 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="5b7aa-106">단계는 다음과 같습니다 (이 표에는 사용 권한 목록에 포함 되어 있습니다).</span><span class="sxs-lookup"><span data-stu-id="5b7aa-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="5b7aa-107">**단계의**</span><span class="sxs-lookup"><span data-stu-id="5b7aa-107">**Phase**</span></span>|<span data-ttu-id="5b7aa-108">**필요한**</span><span class="sxs-lookup"><span data-stu-id="5b7aa-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5b7aa-109">DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="5b7aa-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="5b7aa-110">도메인 관리자</span><span class="sxs-lookup"><span data-stu-id="5b7aa-110">Domain Admins</span></span>  <br/> <span data-ttu-id="5b7aa-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="5b7aa-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="5b7aa-112">인증서 수정</span><span class="sxs-lookup"><span data-stu-id="5b7aa-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="5b7aa-113">로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="5b7aa-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="5b7aa-114">역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="5b7aa-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="5b7aa-115">로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="5b7aa-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="5b7aa-116">하이브리드 배포를 사용 하 여 이동성에 대 한 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="5b7aa-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="5b7aa-117">도메인 관리자</span><span class="sxs-lookup"><span data-stu-id="5b7aa-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="5b7aa-118">모바일 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="5b7aa-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="5b7aa-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b7aa-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="5b7aa-120">푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="5b7aa-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="5b7aa-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5b7aa-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="5b7aa-122">이동성 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5b7aa-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="5b7aa-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b7aa-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="5b7aa-124">다음 섹션에는 계획 항목을 읽은 것으로 가정 하는 단계가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="5b7aa-125">혼란 스 러 울 경우 해당 위치에서 정보를 자유롭게 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="5b7aa-126">이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="5b7aa-127">현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="5b7aa-128">MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="5b7aa-129">DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="5b7aa-129">Create DNS records</span></span>
<span data-ttu-id="5b7aa-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="5b7aa-130"></span></span>

<span data-ttu-id="5b7aa-131">이는 비즈니스용 Skype Server 환경의 일부로 이미 포함 되어 있을 수 있지만 자동 검색을 사용 하려면 다음 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="5b7aa-132">조직의 네트워크 내에서 연결 하는 모바일 사용자를 지 원하는 내부 DNS 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="5b7aa-133">외부 (또는 공용) DNS 레코드-조직의 네트워크 외부에서 연결 하는 모바일 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="5b7aa-134">이러한 레코드는 (호스트) 이름 또는 CNAME 레코드 (여기에 모두 포함 될 필요는 없음) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="5b7aa-135">내부 DNS CNAME 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="5b7aa-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="5b7aa-136">네트워크에서 **Domain Admins** 그룹의 구성원 이거나 **DnsAdmins** 그룹에 속하는 DNS 서버에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="5b7aa-137">**시작**을 클릭 하 고 **관리 도구** (시작 메뉴를 해제 하는 옵션이 아닌 경우 **검색** 해야 할 수 있음)를 선택한 다음 **dns** 를 클릭 하 여 dns 관리 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="5b7aa-138">콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버 프런트 엔드 서버에 홈으로 접속 하는 도메인으로 이동 하 고 여기서 **정방향 조회 영역** 을 확장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="5b7aa-139">다음 중 어느 것을 사용 하 고 있는지 확인해 주십시오.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="5b7aa-140">프런트 엔드 서버 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 () 용 호스트 A 또는 AAAA 레코드</span><span class="sxs-lookup"><span data-stu-id="5b7aa-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="5b7aa-141">디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="5b7aa-142">이 내용을 적어 둔 후 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **새 별칭 (CNAME)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="5b7aa-143">**별칭 이름** 텍스트 상자에 내부 자동 검색 서비스 URL에 대 한 lyncdiscoverinternal를 호스트 이름으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="5b7aa-144">정규화 된 **도메인 이름 (대상 호스트의 FQDN**)에서 위의 4 단계에서 확인 한 프런트 엔드 풀 (또는 싱글 프런트 엔드 서버 또는 디렉터 풀 또는 디렉터)에 대 한 내부 웹 서비스 FQDN을 입력 하거나 탐색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="5b7aa-145">입력 하는 경우 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="5b7aa-146">비즈니스용 Skype 서버 환경에서 지원 되는 각 SIP 도메인에 대해 정방향 조회 영역에서 새 자동 검색 CNAME 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="5b7aa-147">외부 DNS CNAME 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="5b7aa-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="5b7aa-148">사용 하 고 있는 공용 DNS 공급자를 알 수 없기 때문에이 단계를 수행 하는 데 도움이 필요 합니다. 새 DNS 레코드를 만들 수 있는 계정으로 공용 DNS 공급자에 로그인 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="5b7aa-149">이 시점에서 SIP 도메인은 비즈니스용 Skype 서버용으로 이미 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="5b7aa-150">이 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 하거나 다른 방법으로 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="5b7aa-151">다음 중 어느 것을 사용 하 고 있는지 확인해 주십시오.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="5b7aa-152">프런트 엔드 서버 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 () 용 호스트 A 또는 AAAA 레코드</span><span class="sxs-lookup"><span data-stu-id="5b7aa-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="5b7aa-153">디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="5b7aa-154">해당 정보를 찾았으면 **새 별칭 (CNAME)** 을 만들기 위한 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="5b7aa-155">이제 **별칭 이름을**입력할 수 있으며, 외부 자동 검색 서비스 URL에 대 한 lyncdiscover를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="5b7aa-156">그 다음에는 **대상 호스트의 fqdn**에 입력할 영역이 있으며 위의 3 단계에서 확인 된 프런트 엔드 풀 (또는 단일 프런트 엔드 서버 또는 디렉터 풀 또는 디렉터)에 대 한 fqdn 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="5b7aa-157">여기에 저장 해야 하거나 비즈니스용 Skype 서버 환경에서 각 SIP 도메인의 정방향 조회 영역에 추가 CNAME 레코드를 만들어야 하는 경우에는이 작업을 수행 해야 하지만, 준비가 되 면 업무를 저장 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="5b7aa-158">내부 DNS A 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="5b7aa-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="5b7aa-159">네트워크에서 **Domain Admins** 그룹의 구성원 이거나 **DnsAdmins** 그룹에 속하는 DNS 서버에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="5b7aa-160">**시작**을 클릭 하 고 **관리 도구** (시작 메뉴를 해제 하는 옵션이 아닌 경우 **검색** 해야 할 수 있음)를 선택한 다음 **dns** 를 클릭 하 여 dns 관리 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="5b7aa-161">콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버 프런트 엔드 서버에 홈으로 접속 하는 도메인으로 이동 하 고 여기서 **정방향 조회 영역** 을 확장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="5b7aa-162">다음 중 어느 것을 사용 하 고 있는지 확인해 주십시오.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="5b7aa-163">프런트 엔드 서버 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 () 용 호스트 A 또는 AAAA 레코드</span><span class="sxs-lookup"><span data-stu-id="5b7aa-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="5b7aa-164">디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="5b7aa-165">이에 대 한 설명이 표시 되 면 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **새 호스트 (A 또는 AAAA)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="5b7aa-166">**이름** 텍스트 상자에 내부 자동 검색 서비스 URL에 대 한 lyncdiscoverinternal를 호스트 이름으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="5b7aa-167">**IP 주소** 텍스트 상자에 위의 4 단계에서 확인 한 프런트 엔드 풀 (또는 단일 프런트 엔드 서버 또는 디렉터 풀 또는 디렉터)에 대 한 내부 웹 서비스 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="5b7aa-168">이 작업이 완료 되 면 **호스트 추가**를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="5b7aa-169">비즈니스용 Skype 서버 환경에서 지원 되는 각 SIP 도메인에 대 한 새 자동 검색 A 또는 AAAA 레코드를 정방향 조회 영역에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="5b7aa-170">이렇게 하려면, 필요한 횟수 만큼 6-8 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="5b7aa-171">모두 마쳤으면 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="5b7aa-172">외부 DNS A 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="5b7aa-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="5b7aa-173">사용 하 고 있는 공용 DNS 공급자를 알 수 없기 때문에이 단계를 수행 하는 데 도움이 필요 합니다. 새 DNS 레코드를 만들 수 있는 계정으로 공용 DNS 공급자에 로그인 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="5b7aa-174">이 시점에서 SIP 도메인은 비즈니스용 Skype 서버용으로 이미 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="5b7aa-175">이 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 하거나 다른 방법으로 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="5b7aa-176">다음 중 어느 것을 사용 하 고 있는지 확인해 주십시오.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="5b7aa-177">프런트 엔드 서버 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 () 용 호스트 A 또는 AAAA 레코드</span><span class="sxs-lookup"><span data-stu-id="5b7aa-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="5b7aa-178">디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="5b7aa-179">이 정보를 사용 하는 경우 새 호스트를 만드는 옵션을 선택할 수 있습니다 ( **a 또는 AAAA**).</span><span class="sxs-lookup"><span data-stu-id="5b7aa-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="5b7aa-180">이제 **이름을**입력할 수 있으며, 외부 자동 검색 서비스 URL에 대해 여기서 lyncdiscover를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="5b7aa-181">그 다음에는 **IP Addresss**에 입력할 영역 이어야 하며, 위의 3 단계에서 확인 된 프런트 엔드 풀 (또는 단일 프런트 엔드 서버 또는 디렉터 풀 또는 디렉터)에 대 한 IP가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="5b7aa-182">여기에 저장 해야 하거나 비즈니스용 Skype 서버 환경에 대 한 각 SIP 도메인의 정방향 조회 영역에서 추가 A 또는 AAAA 레코드를 만들어야 하는 경우에는이 작업을 수행 해야 하지만, 준비 된 후에는 업무를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="5b7aa-183">인증서 수정</span><span class="sxs-lookup"><span data-stu-id="5b7aa-183">Modify certificates</span></span>
<span data-ttu-id="5b7aa-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="5b7aa-184"></span></span>

<span data-ttu-id="5b7aa-185">인증서를 계획 하는 방법에 대 한 질문이 있는 경우 [비즈니스용 Skype 서버 문서에 대 한 모바일 이동성 계획](../plan-your-deployment/mobility.md) 에서이에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="5b7aa-186">검토가 완료 되 면 다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="5b7aa-187">새 인증서가 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="5b7aa-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="5b7aa-188">CA (인증 기관)에서 새 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="5b7aa-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="5b7aa-189">PowerShell을 사용 하 여 현재 위치 인증서를 대체 하 여 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="5b7aa-190">MMC (Microsoft Management Console)에서 인증서 스냅인을 사용 하 여 인증서를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="5b7aa-191">새 인증서가 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="5b7aa-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="5b7aa-192">먼저 현재 위치에 있는 인증서와 필요한 항목이 있는지 여부를 확인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="5b7aa-193">이렇게 하려면 로컬 관리자 계정을 사용 하 여 비즈니스용 Skype 서버에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="5b7aa-194">이 계정에는 이러한 단계 중 일부에 대해 발급 하는 CA (인증 기관)에 대 한 권한도 있어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="5b7aa-195">비즈니스용 Skype Server Management Shell을 엽니다 (검색을 사용 하 여 시작 메뉴 또는 작업 표시줄에 고정 되어 있지 않은 경우 찾을 수 있음).</span><span class="sxs-lookup"><span data-stu-id="5b7aa-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="5b7aa-196">업데이트 된 인증서를 추가 하기 전에 어떤 인증서가 할당 되었는지 아는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="5b7aa-197">명령에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-197">So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="5b7aa-198">3 단계의 정보는 사용자에 게 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="5b7aa-199">여러 작업에 할당 된 단일 인증서가 있는지 또는이를 필요로 하는 다른 구성 요소에 대해 다른 인증서가 할당 되었는지 확인 하려면이를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="5b7aa-200">**Use** 매개 변수는 인증서를 사용 하는 방법을 알려 주는 반면, **지문** 매개 변수는 동일한 인증서 또는 여러 인증서가 있는지 여부를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="5b7aa-201">계획 섹션에 SAN 항목이 권장 되는 경우에는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="5b7aa-202">그렇지 않은 경우 인증 기관에서 새 인증서 또는 구성에 따라 여러 인증서를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="5b7aa-203">CA (인증 기관)에서 새 인증서 또는 인증서 요청</span><span class="sxs-lookup"><span data-stu-id="5b7aa-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="5b7aa-204">보유 하 고 있는 SAN 항목을 확인 한 후에는 **단일 인증서** (위 단계를 통해 확인 한 후)가 있다는 것을 알고 있으며 필요한 항목이 모두 없는 것을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="5b7aa-205">CA에 대 한 새로운 인증서 요청이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="5b7aa-206">비즈니스용 Skype Server PowerShell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="5b7aa-207">누락 된 자동 검색 서비스 SAN (-Ca 매개 변수를 고유한 인증 기관 경로로 바꾸는 경우):</span><span class="sxs-lookup"><span data-stu-id="5b7aa-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="5b7aa-208">이제 여러 SIP 도메인이 있는 경우 위의 예제와 같이 AllSipDomain 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="5b7aa-209">대신 DomainName 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="5b7aa-210">DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="5b7aa-211">예를 들어-Ca 매개 변수를 고유한 인증 기관 경로로 바꾸는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="5b7aa-212">또는, 보유 하 고 있는 SAN 항목을 확인 한 후에는 필요한 항목을 모두 갖고 있지 않은 **여러 개의 인증서** 가 있다는 것을 발견 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="5b7aa-213">CA에 대 한 새로운 인증서 요청이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="5b7aa-214">비즈니스용 Skype Server PowerShell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="5b7aa-215">누락 된 자동 검색 서비스 SAN (-Ca 매개 변수를 고유한 인증 기관 경로로 바꾸는 경우):</span><span class="sxs-lookup"><span data-stu-id="5b7aa-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="5b7aa-216">이제 여러 SIP 도메인이 있는 경우 위의 예제와 같이 AllSipDomain 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="5b7aa-217">대신 DomainName 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="5b7aa-218">DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="5b7aa-219">예를 들면 (-Ca 매개 변수를 고유한 인증 기관 경로로 바꾸는 경우):</span><span class="sxs-lookup"><span data-stu-id="5b7aa-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="5b7aa-220">CA에서 새 인증서를 생성 한 후에는 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5b7aa-221">비즈니스용 Skype Server Management Shell을 사용 하 여 인증서 할당</span><span class="sxs-lookup"><span data-stu-id="5b7aa-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="5b7aa-222">위의 새 인증 필요 사항 섹션에 있는 항목에 따라 다음 중 **하나** 를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="5b7aa-223">모든 것에 대 한 단일 인증서가 있는 경우 (지문이 동일한 경우) 다음을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="5b7aa-224">다른 항목에 대 한 인증서가 있다면 (지문이 모두 다름) 대신이를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="5b7aa-225">MMC (Microsoft Management Console)에서 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="5b7aa-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="5b7aa-226">MMC에 대 한 인증서 스냅인을 사용 하 여 인증서를 확인 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="5b7aa-227">검색에 MMC를 입력 하면 응용 프로그램 옵션으로 팝업 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="5b7aa-228">인증서 스냅인을 추가 하려면 **파일**을 클릭 한 다음 **스냅인 추가/제거** 를 선택 해야 합니다. (또는 바로 가기 키 **Ctrl + M** 도 작동 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="5b7aa-229">**인증서** 는 왼쪽 창의 옵션이 되며,이 옵션을 선택 하 고 나 서 팝업 창에서 **컴퓨터 계정을** 선택한 다음 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="5b7aa-230">여전히 팝업 창에 표시 해야 하는 인증서가 있는 컴퓨터에서이 작업을 수행할 수 있으므로, 이렇게 하면 **로컬 컴퓨터** 에서 선택 항목을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="5b7aa-231">원격 컴퓨터에서 작업 하는 경우 라디오 단추를 **다른 컴퓨터로** 변경 하 고 해당 컴퓨터의 FQDN을 입력 하거나 **찾아보기** 단추를 사용 하 여 광고를 통해 해당 컴퓨터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="5b7aa-232">컴퓨터를 선택한 후에 준비가 되 면 **마침을** 클릭 하 고 **확인** 으로 MMC에 스냅인을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="5b7aa-233">MMC의 왼쪽 창에서 **인증서** 섹션을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="5b7aa-234">**개인** 폴더도 확장 하 고 **인증서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="5b7aa-235">이 저장소의 인증서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="5b7aa-236">보려는 인증서를 찾아 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5b7aa-237">인증서의 종류를 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="5b7aa-237">How do you know what certificate this is?</span></span> <span data-ttu-id="5b7aa-238">이는 팜에 대해 모든 사용자에 게 할당 된 단일 인증서 이거나 기본 웹 서비스 등 다양 한 항목에 대해 여러 인증서가 있을 수 있으며,이 경우 여러 인증서를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="5b7aa-239">여러 인증서에는 동일한 지문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="5b7aa-240">**인증서** 보기로 연결한 후에 **세부 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="5b7aa-241">이를 통해 **주체**를 선택 하면 인증서 주체 이름이 표시 되 고 지정 된 제목 이름과 관련 속성이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="5b7aa-242">또한 **주체 대체 이름** 항목을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="5b7aa-243">다음 중 하나 이상을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="5b7aa-244">이 풀의 풀 이름 또는 풀이 아닌 경우 단일 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="5b7aa-245">인증서가 할당 된 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="5b7aa-246">간단한 URL 레코드 (일반적으로 모임 및 전화 접속)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="5b7aa-247">웹 서비스 내부 및 웹 서비스 외부 이름 (예: webpool01.contoso.net, webpool01.contoso.com)-토폴로지 작성기 및 재정의 된 웹 서비스 선택 항목을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="5b7aa-248">이미 할당 된 경우 lyncdiscover. \<sipdomain\> 및 lyncdiscoverinternal. \<레코드\> 를 sipdomain.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="5b7aa-249">둘 이상의 항목을 할당 한 경우 여러 개의 인증서를 확인 해야 합니다 (위의 참고 사항 확인).</span><span class="sxs-lookup"><span data-stu-id="5b7aa-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="5b7aa-250">따라서 lyncdiscover을 찾을 수 있습니다. \<sipdomain\> 및 lyncdiscoverinternal. \<sipdomain\> 레코드가 이미 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="5b7aa-251">MMC를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="5b7aa-252">해당 사용자가 할당 되지 않은 경우에는 새 인증서 요청을 만들어야 합니다 (위 개요). 또는 사후 요청을 설치 해야 합니다 (위의 PowerShell을 다음에 추천).</span><span class="sxs-lookup"><span data-stu-id="5b7aa-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="5b7aa-253">역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="5b7aa-253">Configure the reverse proxy</span></span>
<span data-ttu-id="5b7aa-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="5b7aa-254"></span></span>

<span data-ttu-id="5b7aa-255">아래 단계는 정확히 팔 로우 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="5b7aa-256">이는 이전 버전의 제품에서 TMG (위협 관리 게이트웨이)를 구성 하는 등의 작업을 수행 하 고, 사용 하지 않은 경우 해당 위치에서 자신만의 버전을 관리 해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="5b7aa-257">TMG는 Microsoft에서 더 이상 제품으로 제공 되지 않으며 여전히 구성 해야 하는 경우 [Lync Server 2013 단계](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="5b7aa-258">그러나 다음 정보는 모든 리버스 프록시에 대해 특정 연습 단계를 제공할 수 없는 경우에도 더 일반적으로 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="5b7aa-259">다음과 같은 두 가지 주요 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="5b7aa-260">HTTPS를 통해 초기 자동 검색 요청을 진행 하 고 계십니까 (권장)?</span><span class="sxs-lookup"><span data-stu-id="5b7aa-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="5b7aa-261">웹 게시 규칙이 있으면 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="5b7aa-262">웹 게시 규칙이 아직 없는 경우 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="5b7aa-263">HTTP를 통해 초기 자동 검색 요청을 수행 하는 경우에는 해당 규칙도 만들거나 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5b7aa-264">**중요** 프록시 시간 초과 값은 배포에 따라 달라 지는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="5b7aa-265">배포를 모니터링 하 고 클라이언트에 대 한 최상의 환경을 위해 값을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="5b7aa-266">200 보다 낮은 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="5b7aa-267">환경에서 Lync 모바일 클라이언트를 지원 하는 경우에는 시간 제한 값이 900 인 Office 365에서 푸시 알림 시간 제한을 허용 하도록 값을 960로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="5b7aa-268">값이 너무 낮을 경우 클라이언트 연결이 끊어지지 않도록 시간 초과 값을 늘려야 하거나, 프록시를 통한 연결이 끊어지면이를 차단 하지만 클라이언트의 연결이 끊긴 후에는 장시간 해제 해야 할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="5b7aa-269">환경에 대 한 모니터링 및 기준 지정은 해당 값에 대 한 적절 한 설정을 결정 하는 유일한 올바른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="5b7aa-270">외부 자동 검색 SAN 및 URL에 대 한 기존 웹 게시 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="5b7aa-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="5b7aa-271">역방향 프록시 인터페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="5b7aa-272">웹 게시 규칙을 찾고 편집 옵션을 선택 해야 합니다 (리버스 프록시 구성에 따라 메뉴나 탭에 있을 수 있음).</span><span class="sxs-lookup"><span data-stu-id="5b7aa-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="5b7aa-273">이 웹 게시 규칙이 적용 되는 내용을 명시 하는 영역이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="5b7aa-274">수신 사이트 또는 사이트 요청에 대해이 규칙을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="5b7aa-275">새 항목을 **추가** 해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="5b7aa-276">자동 검색 사이트의 이름을 입력 하 고 (사용 하는 예제는 lyncdiscover.contoso.com) 리버스 프록시의 형식에 따라 **확인** 또는 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="5b7aa-277">자동 검색 하는 SAN 항목이 있는 새 인증서가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="5b7aa-278">또한 리버스 프록시의 설정에 따라 함께 설치 하 고 사용 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="5b7aa-279">구성이 완료 되 면 모두 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="5b7aa-280">역방향 프록시에 **테스트** 기능이 있는 경우 해당 기능을 사용 하 여 모든 항목이 제대로 작동 하는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="5b7aa-281">이제 환경에 디렉터 또는 디렉터 풀이 있는 경우이 단계를 반복 해야 할 수 있습니다 (이는 두 번째 규칙이 있는 것을 의미 함).</span><span class="sxs-lookup"><span data-stu-id="5b7aa-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="5b7aa-282">외부 자동 검색 URL에 대 한 웹 게시 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="5b7aa-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="5b7aa-283">역방향 프록시 인터페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="5b7aa-284">웹 게시 규칙을 만드는 인터페이스에서 위치를 찾고, **새** 또는 **만들기** 옵션을 선택 해야 합니다 (이는 리버스 프록시 구성에 따라 메뉴나 탭에 있을 수 있음).</span><span class="sxs-lookup"><span data-stu-id="5b7aa-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="5b7aa-285">새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="5b7aa-286">일반적으로 아래와 같은 정보를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="5b7aa-287">**이름**: 규칙 이름</span><span class="sxs-lookup"><span data-stu-id="5b7aa-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="5b7aa-288">**규칙 동작**:이 경우에는 사용자가 리버스 프록시를 통과 **하도록 허용** 하는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="5b7aa-289">선택 하는 **게시** 규칙이 나 옵션은 **단일 웹 사이트 또는 부하 분산 장치**입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="5b7aa-290">이는 외부 액세스를 위해 **SSL** 이어야 하며 해당 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="5b7aa-291">**내부 게시용**경로를 게시 하 고 프런트 엔드 풀의 부하 분산 장치 (또는 사용자가 있는 경우 디렉터 풀의 부하 분산 장치 fqdn)에 대 한 fqdn을 입력 해야 하는 경우 예를 들어 보겠습니다. sfb_ pool01.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="5b7aa-292">게시할 경로로 \* \*\* / \*\*를 입력 해야 하지만, **원본 호스트 헤더도 전달**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="5b7aa-293">**공용 또는 외부 이름** 세부 정보 또는 정보에 대 한 옵션이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="5b7aa-294">입력할 수 있는 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="5b7aa-295">**요청을 수락**하지만 도메인 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="5b7aa-296">**이름**에는 **lyncdiscover** 를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="5b7aa-297"><sipdomain>(외부 자동 검색 서비스 URL)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="5b7aa-298">이제 프런트 엔드 풀에서 외부 웹 서비스 URL에 대 한 규칙을 만드는 경우 프런트 엔드 풀의 외부 웹 서비스에 대 한 FQDN을 입력 해야 합니다 (예: lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5b7aa-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="5b7aa-299">**경로** 옵션이 있으므로 \* 여기에 \*를 입력 \*\* / \*\*해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="5b7aa-300">최신 공용 인증서를 사용 하 여 **SSL 수신기** 를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="5b7aa-301">**인증 위임은** **위임 없음으로**설정 해야 하지만 직접 클라이언트 인증은 허용 되어야 합니다 \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="5b7aa-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="5b7aa-302">**모든 사용자**에 게 규칙을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="5b7aa-303">이 규칙을 만드는 데 필요한 모든 정보를 사용 하 여 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="5b7aa-304">**원본 호스트 헤더가** 전달 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="5b7aa-305">**웹 서버** 포트만 설정 해야 하므로 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="5b7aa-306">**요청을 HTTP 포트로 리디렉션** 하 고 포트 번호는 **8080**이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="5b7aa-307">**요청을 SSL 포트로 리디렉션** 하 고 포트 번호는 **4443**이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="5b7aa-308">모든 것이 구성 된 경우에는이를 저장 하거나 적용 한 다음 규칙을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="5b7aa-309">포트 80에 대 한 웹 게시 규칙 만들기 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="5b7aa-310">역방향 프록시 인터페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="5b7aa-311">웹 게시 규칙을 만드는 인터페이스에서 위치를 찾고, **새** 또는 **만들기** 옵션을 선택 해야 합니다 (이는 리버스 프록시 구성에 따라 메뉴나 탭에 있을 수 있음).</span><span class="sxs-lookup"><span data-stu-id="5b7aa-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="5b7aa-312">새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="5b7aa-313">일반적으로 아래와 같은 정보를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="5b7aa-314">**이름**: 규칙 이름</span><span class="sxs-lookup"><span data-stu-id="5b7aa-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="5b7aa-315">**규칙 동작**:이 경우에는 사용자가 리버스 프록시를 통과 **하도록 허용** 하는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="5b7aa-316">선택 하는 **게시** 규칙이 나 옵션은 **단일 웹 사이트 또는 부하 분산 장치**입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="5b7aa-317">이 연결을 통해 **게시 된 웹 서버 또는 팜에 연결 하려면 보안이 되지 않는**것이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="5b7aa-318">**내부 게시용**경로를 게시 하 고 프런트 엔드 풀의 부하 분산 장치의 **VIP 주소** 에 대 한 FQDN을 입력 해야 하는 경우 예제는 sfb_pool01입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="5b7aa-319">게시할 경로로 \* \*\* / \*\*를 입력 해야 하지만, **원본 호스트 헤더도 전달**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="5b7aa-320">**공용 또는 외부 이름** 세부 정보 또는 정보에 대 한 옵션이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="5b7aa-321">입력할 수 있는 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="5b7aa-322">**요청을 수락**하지만 도메인 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="5b7aa-323">**이름**에는 **lyncdiscover** 를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="5b7aa-324"><sipdomain>(외부 자동 검색 서비스 URL)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="5b7aa-325">**경로** 옵션이 있으므로 \* 여기에 \*를 입력 \*\* / \*\*해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="5b7aa-326">웹 수신기를 선택 하거나 리버스 프록시에서 만들 수 있도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="5b7aa-327">**인증 위임은** **위임 없음으로**설정 해야 하지만 직접 클라이언트 인증은 허용 **되지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="5b7aa-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="5b7aa-328">**모든 사용자**에 게 규칙을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="5b7aa-329">이 규칙을 만드는 데 필요한 모든 정보를 사용 하 여 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="5b7aa-330">**웹 서버** 포트를 설정 해야 하는 경우 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="5b7aa-331">**요청을 HTTP 포트로 리디렉션** 하 고 포트 번호는 **8080**이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="5b7aa-332">**요청을 SSL 포트로 리디렉션** 하 고 포트 번호는 **4443**이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="5b7aa-333">모든 것이 구성 된 경우에는이를 저장 하거나 적용 한 다음 규칙을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="5b7aa-334">하이브리드 배포를 사용 하 여 이동성에 대 한 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="5b7aa-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="5b7aa-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="5b7aa-335"></span></span>

<span data-ttu-id="5b7aa-336">비즈니스용 Skype Server의 하이브리드 환경은 온-프레미스 및 O365 환경을 결합 하는 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="5b7aa-337">하이브리드 환경에서 비즈니스용 Skype 서버를 사용 하는 경우 자동 검색 서비스가 이러한 환경 중 하나에서 사용자를 찾을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="5b7aa-338">모바일 클라이언트가 사용자가 위치한 위치를 검색할 수 있도록 하려면 새 URL (uniform resource locator)을 사용 하 여 자동 검색 서비스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="5b7aa-339">단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-339">The steps are:</span></span>
  
1. <span data-ttu-id="5b7aa-340">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="5b7aa-341">다음을 실행 하 여 비즈니스용 Skype 서버 환경에 대 한 **Proxyfqdn** 특성 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="5b7aa-342">계속 해 서 셸 창에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-342">Then, still in the shell window, run:</span></span>
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="5b7aa-343">여기서 [identity]는 공유 SIP 주소 공간의 도메인 이름으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="5b7aa-344">모바일 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="5b7aa-344">Test your Mobility deployment</span></span>
<span data-ttu-id="5b7aa-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="5b7aa-345"></span></span>

<span data-ttu-id="5b7aa-346">비즈니스용 Skype Server Mobility Service 및 비즈니스용 Skype 서버 자동 검색 서비스를 배포한 후에는 테스트 트랜잭션을 실행 하 여 배포의 작동을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="5b7aa-347">**테스트-CsUcwaConference** 를 실행 하 여 두 사용자가 회의를 만들고 참가 하 고 통신 하는 기능을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="5b7aa-348">이 테스트를 수행 하려면 두 명의 사용자 (실제 또는 테스트)와 전체 자격 증명이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="5b7aa-349">이 명령은 Lync Server 2013 클라이언트는 물론 비즈니스용 Skype 클라이언트 모두에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="5b7aa-350">비즈니스용 Skype Server 2015의 Lync Server 2010 클라이언트의 경우 테스트 하려면 **CsMcxP2PIM** 을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="5b7aa-351">Lync Server 2010 사용자는 여전히 실제 사용자 또는 미리 정의 된 테스트 사용자 여야 하며, 암호 자격 증명이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="5b7aa-352">이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="5b7aa-353">현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="5b7aa-354">MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="5b7aa-355">비즈니스용 Skype 및 Lync 2013 모바일 클라이언트에 대 한 회의 테스트</span><span class="sxs-lookup"><span data-stu-id="5b7aa-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="5b7aa-356">**비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 되어 있는 컴퓨터에서 **csadministrator** 역할의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5b7aa-357">**비즈니스용 Skype Server Management Shell** 을 시작 하세요 (검색에 이름을 입력 하거나 **모든 프로그램** 으로 이동 하 고 선택할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="5b7aa-358">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-358">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="5b7aa-359">스크립트에서 자격 증명을 설정 하 고 테스트 cmdlet에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="5b7aa-360">이에 대 한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-360">We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="5b7aa-361">Lync 2010 모바일 클라이언트에 대 한 회의 테스트</span><span class="sxs-lookup"><span data-stu-id="5b7aa-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="5b7aa-362">이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="5b7aa-363">현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="5b7aa-364">MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="5b7aa-365">**비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 되어 있는 컴퓨터에서 **csadministrator** 역할의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5b7aa-366">**비즈니스용 Skype Server Management Shell** 을 시작 하세요 (검색에 이름을 입력 하거나 **모든 프로그램** 으로 이동 하 고 선택할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="5b7aa-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="5b7aa-367">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-367">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="5b7aa-368">스크립트에서 자격 증명을 설정 하 고 테스트 cmdlet에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="5b7aa-369">이에 대 한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-369">We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="5b7aa-370">명령 절차를 더 자세히 검토 하기 위해 [CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 및 [test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="5b7aa-371">푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="5b7aa-371">Configure for push notifications</span></span>
<span data-ttu-id="5b7aa-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="5b7aa-372"></span></span>

<span data-ttu-id="5b7aa-373">배지, 아이콘 또는 알림 형식의 푸시 알림은 Skype 또는 Lync 앱이 비활성화 된 경우에도 모바일 장치로 전송 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="5b7aa-374">그러나 푸시 알림은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="5b7aa-374">But what are push notifications?</span></span> <span data-ttu-id="5b7aa-375">이러한 알림은 새로운 또는 부재 중 메신저 대화 초대 또는 받은 보이스 메일 등의 이벤트 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="5b7aa-376">비즈니스용 Skype 서버 모바일 서비스는이 알림을 클라우드 기반 비즈니스용 Skype Server 푸시 알림 서비스로 보내 Windows Phone 사용자를 위한 MSNS (Microsoft 푸시 알림 서비스)에 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="5b7aa-377">이 기능은 Lync Server 2013에서 변경 되지 않았지만 비즈니스용 Skype 서버를 사용 하는 경우 다음을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="5b7aa-378">비즈니스용 Skype Server Edge 서버의 경우 새 호스팅 공급자, Microsoft 비즈니스용 Skype Online을 추가 하 고 조직과 비즈니스용 Skype Online 간 호스팅 공급자 페더레이션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="5b7aa-379">**Set-CsPushNotificationConfiguration** cmdlet을 실행 하 여 푸시 알림을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="5b7aa-380">기본적으로 푸시 알림은 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="5b7aa-381">페더레이션 구성 및 푸시 알림을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="5b7aa-382">푸시 알림에 대 한 비즈니스용 Skype Edge 서버 구성</span><span class="sxs-lookup"><span data-stu-id="5b7aa-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="5b7aa-383">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5b7aa-384">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5b7aa-385">비즈니스용 Skype 서버 online 호스팅 공급자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="5b7aa-386">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-386">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="5b7aa-387">단일 호스팅 공급자에 두 개 이상의 페더레이션 관계를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="5b7aa-388">따라서 sipfed.online.lync.com와 페더레이션 관계가 있는 호스팅 공급자를 이미 설정한 경우 호스팅 공급자의 id가 SkypeOnline 이외의 다른 호스팅 공급자를 사용 하는 경우에도이를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="5b7aa-389">비즈니스용 Skype Online에서 조직과 푸시 알림 서비스 간에 호스팅 공급자 페더레이션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="5b7aa-390">명령줄에 다음을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-390">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="5b7aa-391">푸시 알림 사용</span><span class="sxs-lookup"><span data-stu-id="5b7aa-391">Enable push notifications</span></span>

1. <span data-ttu-id="5b7aa-392">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5b7aa-393">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5b7aa-394">푸시 알림 사용:</span><span class="sxs-lookup"><span data-stu-id="5b7aa-394">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="5b7aa-395">페더레이션 사용:</span><span class="sxs-lookup"><span data-stu-id="5b7aa-395">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="5b7aa-396">페더레이션 및 푸시 알림 테스트</span><span class="sxs-lookup"><span data-stu-id="5b7aa-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="5b7aa-397">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5b7aa-398">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5b7aa-399">페더레이션 구성을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-399">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="5b7aa-400">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-400">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="5b7aa-401">푸시 알림 테스트:</span><span class="sxs-lookup"><span data-stu-id="5b7aa-401">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="5b7aa-402">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-402">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="5b7aa-403">이동성 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5b7aa-403">Configure Mobility policy</span></span>
<span data-ttu-id="5b7aa-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="5b7aa-404"></span></span>

<span data-ttu-id="5b7aa-405">비즈니스용 Skype 서버에서 모바일 서비스를 사용할 수 있는 사용자, 작업 시간, VoIP (voice over IP) 또는 비디오를 비롯 하 여 VoIP 또는 비디오에 WiFi가 필요한 지 여부를 결정 하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="5b7aa-406">회사 전화를 통해 전화를 통해 휴대 전화는 전화를 걸고 받을 때 휴대폰 번호 대신 회사 전화번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="5b7aa-407">줄의 다른 쪽 끝에 있는 사용자는 휴대폰 번호를 볼 수 없으며,이로 인해 모바일 사용자가 발신 전화 요금을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="5b7aa-408">VoIP와 비디오가 설정 되 면 사용자는 VoIP 통화와 동영상을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="5b7aa-409">WiFi 사용 설정에 따라 사용자의 모바일 장치에서 셀룰러 데이터 네트워크를 통해 WiFi 네트워크를 사용 해야 하는지 여부가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="5b7aa-410">이동성, 업무에 대 한 통화, VoIP 및 비디오 기능은 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="5b7aa-411">VoIP 및 비디오에 WiFi를 요구 하는 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="5b7aa-412">관리자는 전역, 사이트별 또는 사용자를 기준으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="5b7aa-413">모바일 기능을 사용 하 고 작업을 통해 통화할 수 있으려면 사용자가 다음과 같이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="5b7aa-414">비즈니스용 Skype 서버 사용</span><span class="sxs-lookup"><span data-stu-id="5b7aa-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="5b7aa-415">엔터프라이즈 음성에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="5b7aa-416">**EnableMobility** 옵션이 **True**로 설정 된 이동성 정책이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="5b7aa-417">사용자가 작업을 통해 통화를 사용할 수 있도록 하려면 다음도 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="5b7aa-418">**전화의 동시 신호음 사용** 옵션이 선택 된 음성 정책이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="5b7aa-419">**EnableOutsideVoice** 가 **True**로 설정 된 이동성 정책을 할당 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5b7aa-420">Enterprise Voice를 사용 하도록 설정 하지 않은 사용자는 모바일 장치를 사용 하 여 Skype VoIP 통화를 하거나, 해당 옵션이 연결 된 음성 정책에 대해 설정 된 경우 클릭 하 여 링크를 사용 하 여 회의에 참가할 수 있습니다. 과.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="5b7aa-421">자세한 내용은 계획 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="5b7aa-422">전역 이동성 정책 수정</span><span class="sxs-lookup"><span data-stu-id="5b7aa-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="5b7aa-423">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5b7aa-424">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5b7aa-425">다음을 입력 하 여 업무에 대 한 액세스를 해제 하 고 회사의 전화를 통해 통화 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="5b7aa-426">Mobility에 대 한 액세스를 해제 하지 않고 작업을 통해 통화를 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="5b7aa-427">그러나 작업을 통해 통화를 끄지 않고는 이동성을 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="5b7aa-428">자세한 내용은 [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="5b7aa-429">사이트별 이동성 정책 수정</span><span class="sxs-lookup"><span data-stu-id="5b7aa-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="5b7aa-430">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5b7aa-431">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5b7aa-432">사이트 수준 정책을 만들고, VoIP 및 비디오를 끄고 IP 오디오에 WiFi 필요를 사용 하도록 설정 하 고, 사이트 별로 IP 비디오에 WiFi를 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="5b7aa-433">입력할</span><span class="sxs-lookup"><span data-stu-id="5b7aa-433">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="5b7aa-434">[새로운 기능](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)에 대해 자세히 CsMobilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="5b7aa-435">사용자별 이동성 정책 수정</span><span class="sxs-lookup"><span data-stu-id="5b7aa-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="5b7aa-436">**Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5b7aa-437">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5b7aa-438">사용자 수준 이동성 정책을 만들고, 이동성을 사용 하지 않도록 설정 하 고, 사용자의 작업을 통해 전화를 겁니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="5b7aa-439">입력할</span><span class="sxs-lookup"><span data-stu-id="5b7aa-439">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="5b7aa-440">예제 데이터가 있는 추가 예:</span><span class="sxs-lookup"><span data-stu-id="5b7aa-440">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="5b7aa-441">Mobility에 대 한 액세스를 해제 하지 않고 작업을 통해 통화를 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="5b7aa-442">그러나 작업을 통해 통화를 끄지 않고는 이동성을 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b7aa-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

