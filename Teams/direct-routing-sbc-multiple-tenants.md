---
title: 세션 경계 컨트롤러 구성-여러 테 넌 트
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
description: 여러 테 넌 트를 처리 하도록 한 SBC (세션 경계 컨트롤러)를 구성 하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1419a42a6affa00bbeed35d328f91331ad5357ec
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779574"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="3b7e4-103">여러 테넌트에 대해 세션 경계 컨트롤러 구성</span><span class="sxs-lookup"><span data-stu-id="3b7e4-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="3b7e4-104">직접 라우팅은 여러 테 넌 트를 처리 하는 하나의 SBC (세션 경계 컨트롤러) 구성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="3b7e4-105">이 시나리오는이 문서의 뒷부분에 있는 매개체 라고도 하는 Microsoft 파트너 및/또는 PSTN 통신 회사를 위해 고안 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="3b7e4-106">전화 통신 서비스를 Microsoft 팀에 제공 하는 고객에 게 판매 하는 반송파입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="3b7e4-107">반송파:</span><span class="sxs-lookup"><span data-stu-id="3b7e4-107">A carrier:</span></span>
- <span data-ttu-id="3b7e4-108">데이터 센터에서 SBC를 배포 하 고 관리 합니다 (고객은 SBC를 구현할 필요가 없으며 팀 클라이언트의 통신 업체에서 전화 접속 서비스를 받습니다).</span><span class="sxs-lookup"><span data-stu-id="3b7e4-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="3b7e4-109">SBC를 여러 테 넌 트와 상호 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="3b7e4-110">고객에 게 PSTN 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="3b7e4-111">통화 음질을 종료까지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="3b7e4-112">PSTN 서비스에 대 한 요금은 별도로 청구 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="3b7e4-113">Microsoft는 통신 회사를 관리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="3b7e4-114">Microsoft는 PBX (Microsoft 전화 시스템)와 팀 클라이언트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client.</span></span> <span data-ttu-id="3b7e4-115">Microsoft는 또한 Microsoft 전화 시스템에서 사용할 수 있는 전화 및 인증을 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-115">Microsoft also certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="3b7e4-116">통신 회사를 선택 하기 전에 선택에 인증 된 SBC이 있는지 확인 하 고 음성 음질을 종료까지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-116">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="3b7e4-117">시나리오를 구성 하기 위한 기술 구현 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-117">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="3b7e4-118">**통신 회사만:**</span><span class="sxs-lookup"><span data-stu-id="3b7e4-118">**Carrier only:**</span></span>
1. <span data-ttu-id="3b7e4-119">SBC를 배포 하 고 [인증 된 sbc 공급 업체의 지침](#deploy-and-configure-the-sbc)에 따라 호스팅 시나리오에 맞게이를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-119">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="3b7e4-120">반송파 테 넌 트에 기본 도메인 이름을 등록 하 고 와일드 카드 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-120">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="3b7e4-121">기본 도메인의 일부인 모든 고객에 대해 하위 도메인을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-121">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="3b7e4-122">**고객 전역 관리자가 있는 통신 회사:**</span><span class="sxs-lookup"><span data-stu-id="3b7e4-122">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="3b7e4-123">하위 도메인 이름을 고객 테 넌 트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-123">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="3b7e4-124">하위 도메인 이름을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-124">Activate the subdomain name.</span></span>
3. <span data-ttu-id="3b7e4-125">캐리어에서 고객 테 넌 트로 트렁크를 구성 하 고 사용자를 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-125">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="3b7e4-126">*DNS 기본 사항 및 Office 365에서 도메인 이름이 관리 되는 방법을 이해 하 고 있는지 확인 하세요. 계속 진행 하기 전에 [Office 365 도메인 관련 도움말을](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 검토 하세요.*</span><span class="sxs-lookup"><span data-stu-id="3b7e4-126">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="3b7e4-127">SBC 배포 및 구성</span><span class="sxs-lookup"><span data-stu-id="3b7e4-127">Deploy and configure the SBC</span></span>

<span data-ttu-id="3b7e4-128">SBC 호스팅 시나리오의 SBCs를 배포 하 고 구성 하는 방법에 대 한 자세한 단계는 SBC 공급 업체의 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-128">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="3b7e4-129">**오디오 코드:** "오디오 코드 Sbc를 Microsoft 팀의 직접 라우팅 호스팅 모델 구성에 연결"에 설명 된 SBC 호스팅 시나리오의 구성 인 [직접 라우팅 구성 참고 사항](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-129">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note."</span></span> 
- <span data-ttu-id="3b7e4-130">**Oracle:** [직접 라우팅 구성 참고](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)이 SBC 호스팅 시나리오의 구성은 "Microsoft" 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-130">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="3b7e4-131">**리본 통신:**  리본 메뉴의 [커뮤니케이션 SBC 핵심 Microsoft 팀 구성 가이드](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) 를 참조 하세요. 리본 메뉴의 핵심 계열 SBCs를 구성 하는 방법에 대 한 문서를 보려면 [최상의 방법-Microsoft 팀의 매체 구성 직접 경로 설정 SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="3b7e4-131">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>
- <span data-ttu-id="3b7e4-132">**TE-시스템 (anynode):**  여러 테 넌 트에 대해 anynode SBC를 구성 하는 방법에 대 한 설명서와 예제는 [TE Systems 커뮤니티 페이지](https://community.te-systems.de/) 를 통해 등록 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-132">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="3b7e4-133">"Contact" 헤더를 구성 하는 방법에 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-133">Please pay attention to how to configure the "Contact" header.</span></span> <span data-ttu-id="3b7e4-134">연락처 머리글은 들어오는 초대 메시지에서 고객 테 넌 트를 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-134">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="3b7e4-135">기본 도메인과 하위 도메인 등록</span><span class="sxs-lookup"><span data-stu-id="3b7e4-135">Register a base domain and subdomains</span></span>

<span data-ttu-id="3b7e4-136">호스팅 시나리오를 위해서는 다음을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-136">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="3b7e4-137">통신 회사에서 소유 하는 하나의 기본 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-137">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="3b7e4-138">모든 고객 테 넌 트에 있는 기본 도메인 이름의 일부인 하위 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-138">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="3b7e4-139">다음 예제를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-139">In the following example:</span></span>
- <span data-ttu-id="3b7e4-140">Adatum는 인터넷 및 전화 통신 서비스를 제공 하 여 여러 고객에 게 역할을 하는 통신 회사입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-140">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="3b7e4-141">Woodgrove 은행, Contoso 및 어드벤처 작업은 Office 365 도메인이 있지만 Adatum에서 전화 통신 서비스를 수신 하는 세 명의 고객입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-141">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="3b7e4-142">하위 도메인은 365 Office에 대 한 초대를 보낼 때 고객에 대해 구성 되는 트렁크의 FQDN 이름과 연락처 머리글의 FQDN과 일치 **해야 합니다** .</span><span class="sxs-lookup"><span data-stu-id="3b7e4-142">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="3b7e4-143">전화가 Office 365 다이렉트 라우팅 인터페이스에 도달 하면 인터페이스는 Contact 헤더를 사용 하 여 사용자를 조회할 테 넌 트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-143">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="3b7e4-144">일부 고객에 게는 여러 테 넌 트에서 중복 될 수 있는 숫자가 아닌 경우에도 다이렉트 라우팅이 전화 번호 조회를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-144">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="3b7e4-145">따라서 전화 번호로 사용자를 조회할 정확한 테 넌 트를 식별 하는 데 Contact 헤더의 FQDN 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-145">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="3b7e4-146">*Office 365 조직에서 도메인 이름을 만드는 방법에 대 한 자세한 내용은 [office 365 도메인](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 에 대 한 도움말 보기를 검토 하세요.*</span><span class="sxs-lookup"><span data-stu-id="3b7e4-146">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 organizations.*</span></span>

<span data-ttu-id="3b7e4-147">다음 다이어그램에는 기본 도메인, 하위 도메인 및 연락처 머리글에 대 한 요구 사항이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-147">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![도메인 및 연락처 머리글에 대 한 요구 사항을 보여주는 다이어그램](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="3b7e4-149">SBC는 연결을 인증 하는 데 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-149">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="3b7e4-150">SBC 호스팅 시나리오의 경우 \* \*, \*반송파는 base_domain (예: customers.adatum.biz)\* 를 사용 하 여 인증서를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-150">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="3b7e4-151">이 인증서는 단일 SBC에서 제공 하는 여러 테 넌 트에 대 한 연결을 인증 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-151">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="3b7e4-152">다음 표에서는 한 가지 구성의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-152">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="3b7e4-153">새 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="3b7e4-153">New domain name</span></span> |<span data-ttu-id="3b7e4-154">유형</span><span class="sxs-lookup"><span data-stu-id="3b7e4-154">Type</span></span>|<span data-ttu-id="3b7e4-155">되어</span><span class="sxs-lookup"><span data-stu-id="3b7e4-155">Registered</span></span>  |<span data-ttu-id="3b7e4-156">SBC 용 인증서 SAN</span><span class="sxs-lookup"><span data-stu-id="3b7e4-156">Certificate SAN for SBC</span></span>  |<span data-ttu-id="3b7e4-157">이 예제의 테 넌 트 기본 도메인</span><span class="sxs-lookup"><span data-stu-id="3b7e4-157">Tenant default domain in the example</span></span>  |<span data-ttu-id="3b7e4-158">사용자에 게 전화를 보낼 때 SBC가 연락처 헤더에 표시 해야 하는 FQDN 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-158">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="3b7e4-159">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-159">customers.adatum.biz</span></span>|    <span data-ttu-id="3b7e4-160">기반의</span><span class="sxs-lookup"><span data-stu-id="3b7e4-160">Base</span></span>     |     <span data-ttu-id="3b7e4-161">반송파 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="3b7e4-161">In carrier tenant</span></span>  |    <span data-ttu-id="3b7e4-162">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-162">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="3b7e4-163">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-163">adatum.biz</span></span>      |<span data-ttu-id="3b7e4-164">NA,이는 서비스 테 넌 트 이므로 사용자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-164">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="3b7e4-165">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-165">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="3b7e4-166">하위 도메인</span><span class="sxs-lookup"><span data-stu-id="3b7e4-166">Subdomain</span></span>  |    <span data-ttu-id="3b7e4-167">고객 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="3b7e4-167">In a customer tenant</span></span>  |    <span data-ttu-id="3b7e4-168">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-168">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="3b7e4-169">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="3b7e4-169">woodgrovebank.us</span></span>  |  <span data-ttu-id="3b7e4-170">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-170">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="3b7e4-171">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-171">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="3b7e4-172">하위 도메인</span><span class="sxs-lookup"><span data-stu-id="3b7e4-172">Subdomain</span></span> | <span data-ttu-id="3b7e4-173">고객 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="3b7e4-173">In a customer tenant</span></span>   |   <span data-ttu-id="3b7e4-174">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-174">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="3b7e4-175">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b7e4-175">contoso.com</span></span>   |<span data-ttu-id="3b7e4-176">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-176">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="3b7e4-177">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-177">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="3b7e4-178">하위 도메인</span><span class="sxs-lookup"><span data-stu-id="3b7e4-178">Subdomain</span></span> | <span data-ttu-id="3b7e4-179">고객 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="3b7e4-179">In a customer tenant</span></span> |   <span data-ttu-id="3b7e4-180">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-180">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="3b7e4-181">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="3b7e4-181">adventureworks.com</span></span> | <span data-ttu-id="3b7e4-182">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-182">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="3b7e4-183">기본 및 하위 도메인을 구성 하려면 아래 설명 된 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-183">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="3b7e4-184">이 예제에서는 customers.adatum.biz (기본 도메인 이름) 및 한 고객의 하위 도메인 (Woodgrove 은행 테 넌 트의 sbc1.customers.adatum.biz)을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-184">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="3b7e4-185">SbcX.customers.adatum.biz를 사용 하 여 반송파 테 넌 트에서 음성을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-185">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="3b7e4-186">반송파 테 넌 트에 기본 도메인 이름 등록</span><span class="sxs-lookup"><span data-stu-id="3b7e4-186">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="3b7e4-187">**이러한 작업은 반송파 테 넌 트에서 수행 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3b7e4-187">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="3b7e4-188">반송파 테 넌 트에 대 한 적절 한 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3b7e4-188">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="3b7e4-189">전역 관리자로 Microsoft 365 관리 센터에 로그인 한 경우 새 도메인만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-189">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="3b7e4-190">사용 중인https://portal.office.com)역할의 유효성을 검사 하려면 Microsoft 365 관리 센터에 로그인 하 여 **사용자** > **활성 사용자**로 이동한 다음 전역 관리자 역할이 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-190">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="3b7e4-191">관리자 역할 및 Office 365에서 역할을 할당 하는 방법에 대 한 자세한 내용은 [office 365 관리자 역할](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-191">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="3b7e4-192">테 넌 트에 기본 도메인을 추가 하 고이를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-192">Add a base domain to the tenant and verify it</span></span>

1.    <span data-ttu-id="3b7e4-193">Microsoft 365 관리 센터에서**Domains** > **도메인 추가** **설정** > 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-193">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.    <span data-ttu-id="3b7e4-194">**소유 하는 도메인 입력** 상자에 기본 도메인의 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-194">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="3b7e4-195">다음 예제에서는 기본 도메인이 *customers.adatum.biz*.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-195">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![도메인 추가 페이지를 보여 주는 스크린샷](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="3b7e4-197">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-197">Click **Next**.</span></span>
4. <span data-ttu-id="3b7e4-198">이 예제에서 테 넌 트에서 이미 확인 된 도메인 이름으로 adatum.biz를가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-198">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="3b7e4-199">Customers.adatum.biz는 이미 등록 된 이름에 대 한 하위 도메인이 기 때문에 마법사에서 추가 확인을 요청 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-199">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="3b7e4-200">그러나 이전에 확인 되지 않은 FQDN을 추가 하는 경우에는 확인 프로세스를 거쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-200">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="3b7e4-201">확인 프로세스는 [아래에서 설명](#add-a-subdomain-to-the-customer-tenant-and-verify-it)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-201">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![확인 된 도메인 이름 확인을 보여 주는 스크린샷](media/direct-routing-3-sbc-verify-domain.png)

5.    <span data-ttu-id="3b7e4-203">**다음**을 클릭 하 고 **dns 설정 업데이트** 페이지에서 **직접 dns 레코드 추가** 를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-203">Click **Next**, and on the **Update DNS Settings** page, select **I'll add the DNS records myself** and click **Next**.</span></span>
6.    <span data-ttu-id="3b7e4-204">다음 페이지에서 모든 값을 지웁니다 (Exchange, SharePoint 또는 비즈니스용 도메인 이름을 사용 하지 않으려면 **다음**을 클릭 하 고 **마침을**클릭 합니다.)</span><span class="sxs-lookup"><span data-stu-id="3b7e4-204">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="3b7e4-205">새 도메인이 설정 완료 상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-205">Make sure your new domain is in the Setup complete status.</span></span>

    ![설치 상태가 완료 된 도메인을 보여 주는 스크린샷](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="3b7e4-207">도메인 이름 활성화</span><span class="sxs-lookup"><span data-stu-id="3b7e4-207">Activate the domain name</span></span>

<span data-ttu-id="3b7e4-208">도메인 이름을 등록 한 후에는 E1, E3 또는 E5 라이선스 사용자를 하나 이상 추가 하 고 생성 된 기본 도메인과 일치 하는 SIP 주소의 FQDN 부분으로 SIP 주소를 지정 하 여 정품 인증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-208">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="3b7e4-209">*Office 365 조직에서 사용자를 추가 하는 방법에 대 한 자세한 내용은 [office 365 도메인 관련 도움말](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 을 검토 하세요.*</span><span class="sxs-lookup"><span data-stu-id="3b7e4-209">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 organizations.*</span></span>

<span data-ttu-id="3b7e4-210">예: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-210">For example: test@customers.adatum.biz</span></span>

![기본 도메인 활성화 페이지 스크린샷](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="3b7e4-212">고객 테 넌 트에 하위 도메인 이름 등록</span><span class="sxs-lookup"><span data-stu-id="3b7e4-212">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="3b7e4-213">모든 고객에 대해 고유한 하위 도메인 이름을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-213">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="3b7e4-214">이 예제에서는 기본 도메인 이름 woodgrovebank.us를 사용 하 여 테 넌 트에 하위 도메인 sbc1.customers.adatum.biz를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-214">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="3b7e4-215">**아래의 모든 동작은 고객 테 넌 트에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3b7e4-215">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="3b7e4-216">고객 테 넌 트에 대 한 적절 한 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3b7e4-216">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="3b7e4-217">전역 관리자로 Microsoft 365 관리 센터에 로그인 한 경우 새 도메인만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-217">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="3b7e4-218">사용 중인https://portal.office.com)역할의 유효성을 검사 하려면 Microsoft 365 관리 센터에 로그인 하 여 **사용자** > **활성 사용자**로 이동한 다음 전역 관리자 역할이 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-218">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="3b7e4-219">관리자 역할 및 Office 365에서 역할을 할당 하는 방법에 대 한 자세한 내용은 [office 365 관리자 역할](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-219">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="3b7e4-220">고객 테 넌 트에 하위 도메인을 추가 하 고 확인</span><span class="sxs-lookup"><span data-stu-id="3b7e4-220">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="3b7e4-221">Microsoft 365 관리 센터에서**Domains** > **도메인 추가** **설정** > 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-221">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="3b7e4-222">**소유 하는 도메인 입력** 상자에이 테 넌 트에 대 한 하위 도메인의 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-222">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="3b7e4-223">아래 예제에서는 하위 도메인이 sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-223">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![도메인 추가 페이지 스크린샷](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="3b7e4-225">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-225">Click **Next**.</span></span>
4. <span data-ttu-id="3b7e4-226">FQDN이 테 넌 트에서 등록 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-226">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="3b7e4-227">다음 단계에서는 도메인을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-227">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="3b7e4-228">**대신 TXT 레코드 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-228">Select **Add a TXT record instead**.</span></span> 

    ![도메인 확인 페이지 스크린샷](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="3b7e4-230">**다음**을 클릭 하 고 생성 된 TXT 값을 기록 하 여 도메인 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-230">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![도메인 확인 페이지의 텍스트 레코드 스크린샷](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="3b7e4-232">반송파의 DNS 호스팅 공급자에서 이전 단계의 값을 사용 하 여 TXT 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-232">Create the TXT record with the value from the previous step in carrier's DNS hosting provider.</span></span>

    ![TXT 레코드 만들기를 보여 주는 스크린샷](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="3b7e4-234">자세한 내용은 [Office 365 용 dns 호스팅 공급자에서 dns 레코드 만들기](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-234">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="3b7e4-235">고객의 Microsoft 365 관리 센터로 돌아가서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-235">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="3b7e4-236">다음 페이지에서 **DNS 레코드를 직접 추가** 를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-236">On the next page, select **I'll add the DNS records myself** and click **Next**.</span></span>

    ![DNS 설정 업데이트 페이지의 옵션 스크린샷](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="3b7e4-238">**온라인 서비스 선택** 페이지에서 모든 옵션의 선택을 취소 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-238">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![온라인 서비스 선택 페이지 스크린샷](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="3b7e4-240">**DNS 설정 업데이트** 페이지에서 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-240">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![DNS 설정 업데이트 페이지 스크린샷](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="3b7e4-242">상태가 **설정 완료**인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-242">Ensure that the status is **Setup complete**.</span></span> 
    
    ![설정 완료 상태를 보여 주는 페이지의 스크린샷](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="3b7e4-244">하위 도메인 이름 활성화</span><span class="sxs-lookup"><span data-stu-id="3b7e4-244">Activate the subdomain name</span></span>

<span data-ttu-id="3b7e4-245">도메인 이름을 등록 한 후에는 사용자를 하나 이상 추가 하 고 sip 주소의 FQDN 부분을 사용 하 여 고객 테 넌 트의 만들어진 하위 도메인에 일치 하는 SIP 주소를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-245">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="3b7e4-246">*Office 365 조직에서 사용자를 추가 하는 방법에 대 한 자세한 내용은 [office 365 도메인 관련 도움말](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 을 검토 하세요.*</span><span class="sxs-lookup"><span data-stu-id="3b7e4-246">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 organizations.*</span></span>

<span data-ttu-id="3b7e4-247">예: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3b7e4-247">For example: test@sbc1.customers.adatum.biz</span></span>

![하위 도메인 페이지의 활성화 스크린샷](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="3b7e4-249">트렁크를 만들고 사용자를 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-249">Create a trunk and provision users</span></span>

<span data-ttu-id="3b7e4-250">Microsoft는 직접적인 라우팅의 초기 릴리스에서 새 CSOnlinePSTNGateway를 사용 하 여 각 제공 된 테 넌 트에 추가 되는 트렁크 (고객 테 넌 트)을 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-250">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="3b7e4-251">그러나이는 다음 두 가지 이유로 인해 최적이 증명 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-251">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="3b7e4-252">**오버 헤드 관리**.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-252">**Overhead management**.</span></span> <span data-ttu-id="3b7e4-253">예를 들어 SBC를 해제 하거나 드레이닝 하면 미디어 바이패스를 사용 하거나 사용 하지 않도록 설정 하는 등의 일부 매개 변수가 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-253">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="3b7e4-254">포트를 변경 하려면 CSOnlinePSTNGateway를 실행 하 여 여러 테 넌 트의 매개 변수를 변경 해야 하지만, 실제로는 동일한 SBC입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-254">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="3b7e4-255">**오버 헤드 처리**.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-255">**Overhead processing**.</span></span> <span data-ttu-id="3b7e4-256">트렁크 상태 데이터 수집 및 모니터링-즉, 같은 SBC와 물리적 트렁크가 같은 여러 논리적 trunks에서 수집 된 SIP 옵션으로 라우팅 데이터 처리 속도가 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-256">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 
<span data-ttu-id="3b7e4-257">이 피드백에 따라 Microsoft는 고객 테 넌 트에 대 한 trunks를 프로 비전 하는 새 논리를 제공 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-257">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="3b7e4-258">두 개의 새 엔터티가 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-258">Two new entities were introduced:</span></span>
-    <span data-ttu-id="3b7e4-259">CSOnlinePSTNGateway (예: New-CSOnlinePSTNGateway-FQDN customers.adatum.biz-SIPSignalingport 5068-ForwardPAI $true)를 사용 하 여 반송파 테 넌 트에 등록 된 반송파 트렁크</span><span class="sxs-lookup"><span data-stu-id="3b7e4-259">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span></span>

-    <span data-ttu-id="3b7e4-260">등록이 필요 하지 않은 파생 트렁크</span><span class="sxs-lookup"><span data-stu-id="3b7e4-260">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="3b7e4-261">이는 단순히 반송파 트렁크에서 추가 된 원하는 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-261">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="3b7e4-262">이는 모든 구성 매개 변수를 반송파 트렁크에서 파생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-262">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="3b7e4-263">파생 트렁크는 PowerShell에서 만들 필요가 없으며, 반송파 트렁크와의 연결은 FQDN 이름 (아래 세부 정보 참조)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-263">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="3b7e4-264">**프로 비전 논리 및 예제**</span><span class="sxs-lookup"><span data-stu-id="3b7e4-264">**Provisioning logic and example**</span></span>

-    <span data-ttu-id="3b7e4-265">통신 사업자는 Set-CSOnlinePSTNGateway 명령을 사용 하 여 단일 트렁크 (통신 회사 도메인의 반송파 트렁크)를 설정 하 고 관리 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-265">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="3b7e4-266">위의 예제에서 adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-266">In the example above it is adatum.biz;</span></span>
-    <span data-ttu-id="3b7e4-267">고객 테 넌 트에서 반송파는 파생 트렁크 FQDN을 사용자의 음성 라우팅 정책에 추가 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-267">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="3b7e4-268">트렁크 용으로 CSOnlinePSTNGateway를 실행할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-268">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-     <span data-ttu-id="3b7e4-269">이름이 제안 하는 대로 파생 트렁크는 반송파 트렁크의 모든 구성 매개 변수를 상속 하거나 파생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-269">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="3b7e4-270">예제의</span><span class="sxs-lookup"><span data-stu-id="3b7e4-270">Examples:</span></span>
-    <span data-ttu-id="3b7e4-271">Customers.adatum.biz – 반송파 테 넌 트에 만들어야 하는 반송파 트렁크입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-271">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-    <span data-ttu-id="3b7e4-272">Sbc1.customers.adatum.biz-고객 테 넌 트에서 PowerShell에서 만들 필요가 없는 파생 트렁크입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-272">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="3b7e4-273">온라인 음성 라우팅 정책의 고객 테 넌 트에서 파생 트렁크의 이름을 만들지 않고 간단히 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-273">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="3b7e4-274">통신 회사는 파생 트렁크 FQDN을 통신 하는 DNS 레코드를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-274">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-    <span data-ttu-id="3b7e4-275">반송파 트렁크 (반송파 테 넌 트)에서 이루어진 변경 사항은 모두 파생 trunks에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-275">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="3b7e4-276">예를 들어 통신 업체 트렁크에서 SIP 포트를 변경할 수 있으며,이 변경 내용은 파생 된 모든 trunks에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-276">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="3b7e4-277">Trunks를 구성 하는 새로운 논리는 모든 사용자의 테 넌 트로 이동할 필요가 없으므로 관리를 간소화 하 고 모든 트렁크에서 매개 변수를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-277">New logic to configure the trunks simplifies the management as you don't need to go to every tenant and change the parameter on every trunk.</span></span>
-    <span data-ttu-id="3b7e4-278">옵션은 반송파 트렁크 FQDN 으로만 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-278">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="3b7e4-279">반송파 트렁크의 상태는 파생 된 모든 trunks에 적용 되며 라우팅 결정에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-279">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="3b7e4-280">자세한 내용은 [다이렉트 라우팅 옵션](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-280">Find out more about [Direct Routing options](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).</span></span>
-    <span data-ttu-id="3b7e4-281">반송파는 반송파 트렁크를 방전 시킬 수 있으며, 모든 파생 trunks 함께 소모 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-281">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="3b7e4-282">**이전 모델에서 반송파 트렁크로 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="3b7e4-282">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="3b7e4-283">현재 반송파 호스팅 모델 구현에서 새 모델로의 마이그레이션을 위해, 캐리어가 고객 테 넌 트에 대 한 trunks를 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-283">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="3b7e4-284">CSOnlinePSTNGateway (반송파 테 넌 트에 트렁크를 떠나는)를 사용 하 여 고객 테 넌 트에서 trunks 제거-</span><span class="sxs-lookup"><span data-stu-id="3b7e4-284">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="3b7e4-285">지금 바로 통신 회사 및 유도 트렁크 모델을 사용 하 여 모니터링과 프로 비전을 향상 시킬 수 있으므로 최대한 빨리 새로운 솔루션으로 마이그레이션 하는 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-285">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="3b7e4-286">연락처 머리글에 하위 도메인의 FQDN 이름 보내기를 구성 하는 방법에 대 한 [자세한 내용은 SBC 공급 업체 지침](#deploy-and-configure-the-sbc) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-286">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

## <a name="considerations-for-setting-up-muti-tenant-failover"></a><span data-ttu-id="3b7e4-287">Muti-테 넌 트 장애 조치 설정에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="3b7e4-287">Considerations for setting up muti-tenant failover</span></span> 

<span data-ttu-id="3b7e4-288">다중 테 넌 트 환경에 대 한 장애 조치를 설정 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-288">To set up failover for a multi-tenant environment, you'll need to do the following:</span></span>

- <span data-ttu-id="3b7e4-289">각 테 넌 트에 대해 두 개의 다른 SBCs에 대 한 Fqdn을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-289">For each tenant, add the FQDNs for two different SBCs.</span></span>  <span data-ttu-id="3b7e4-290">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-290">For example:</span></span>

   <span data-ttu-id="3b7e4-291">customer1.sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b7e4-291">customer1.sbc1.contoso.com</span></span> <br>
   <span data-ttu-id="3b7e4-292">customer2.sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b7e4-292">customer2.sbc2.contoso.com</span></span> <br>

- <span data-ttu-id="3b7e4-293">사용자의 온라인 음성 라우팅 정책에서 SBCs를 모두 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-293">In the Online Voice Routing policies of the users, specify both SBCs.</span></span>  <span data-ttu-id="3b7e4-294">한 SBC에 오류가 발생 하는 경우 라우팅 정책은 호출을 두 번째 SBC으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7e4-294">If one SBC fails, the routing policy will route calls to the second SBC.</span></span>


## <a name="see-also"></a><span data-ttu-id="3b7e4-295">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b7e4-295">See also</span></span>

[<span data-ttu-id="3b7e4-296">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="3b7e4-296">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="3b7e4-297">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="3b7e4-297">Configure Direct Routing</span></span>](direct-routing-configure.md)

