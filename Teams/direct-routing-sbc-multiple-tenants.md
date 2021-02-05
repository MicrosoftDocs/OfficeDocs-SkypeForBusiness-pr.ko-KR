---
title: 세션 테두리 컨트롤러 구성 - 여러 테넌트
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
description: Microsoft 파트너 및/또는 PSTN 통신 사업자에 대해 여러 테넌트에 서비스를 제공하도록 SBC(세션 테두리 컨트롤러)를 구성하는 방법에 대해 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b81709b46774762036ba9465444d066a0adf019c
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110241"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="f0e67-103">여러 테넌트에 대해 세션 경계 컨트롤러 구성</span><span class="sxs-lookup"><span data-stu-id="f0e67-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="f0e67-104">직접 라우팅은 여러 테넌트에 제공될 하나의 SBC(세션 테두리 컨트롤러)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="f0e67-105">이 시나리오는 Microsoft 파트너 및/또는 PSTN 통신 사업자용으로 설계되어 이 문서의 후반부에서 통신 사업자라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="f0e67-106">통신 사업자에서 고객에게 Microsoft Teams에 배달된 전화 통신 서비스를 판매합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="f0e67-107">통신사:</span><span class="sxs-lookup"><span data-stu-id="f0e67-107">A carrier:</span></span>
- <span data-ttu-id="f0e67-108">데이터 센터에서 SBC를 배포하고 관리합니다(고객은 SBC를 구현할 필요가 없습니다. Teams 클라이언트의 통신사로부터 전화 통신 서비스를 수신함).</span><span class="sxs-lookup"><span data-stu-id="f0e67-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="f0e67-109">SBC를 여러 테넌트에 상호 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="f0e67-110">고객에게 PSTN 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="f0e67-111">통화 품질 종단을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="f0e67-112">PSTN 서비스에 대한 요금은 별도로 청구됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="f0e67-113">Microsoft는 통신업체를 관리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="f0e67-114">Microsoft는 PBX(Microsoft Phone System) 및 Teams 클라이언트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client.</span></span> <span data-ttu-id="f0e67-115">또한 Microsoft는 휴대폰을 인증하고 Microsoft Phone System에서 사용할 수 있는 SBC를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-115">Microsoft also certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="f0e67-116">통신 사업자 선택 전에 선택한 SBC에 인증된 SBC가 있으며 음성 품질 엔드를 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-116">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="f0e67-117">다음은 시나리오를 구성하는 기술 구현 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-117">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="f0e67-118">**통신 사업자만:**</span><span class="sxs-lookup"><span data-stu-id="f0e67-118">**Carrier only:**</span></span>
1. <span data-ttu-id="f0e67-119">SBC를 배포하고 인증된 SBC 공급업체의 지침에 따라 호스팅 시나리오에 대해 [구성합니다.](#deploy-and-configure-the-sbc)</span><span class="sxs-lookup"><span data-stu-id="f0e67-119">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="f0e67-120">통신 사업자 테넌트에 기본 도메인 이름을 등록하고 와일드카드 인증서를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-120">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="f0e67-121">기본 도메인의 일부인 모든 고객에 대해 하위 도메인을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-121">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="f0e67-122">**고객 전역 관리자를 통해 통신 사업자:**</span><span class="sxs-lookup"><span data-stu-id="f0e67-122">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="f0e67-123">고객 테넌트에 하위omain 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-123">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="f0e67-124">하위omain 이름을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-124">Activate the subdomain name.</span></span>
3. <span data-ttu-id="f0e67-125">통신 사업자에서 고객 테넌트로 트렁크를 구성하고 사용자를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-125">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="f0e67-126">*DNS 기본 및 도메인 이름이 Microsoft 365 또는 Office 365에서 관리되는 방법을 이해해야 합니다. 계속하기 [전에 Microsoft 365 또는 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 도메인에 대한 도움말을 검토합니다.*</span><span class="sxs-lookup"><span data-stu-id="f0e67-126">*Please make sure you understand DNS basics and how the domain name is managed in Microsoft 365 or Office 365. Review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="f0e67-127">SBC 배포 및 구성</span><span class="sxs-lookup"><span data-stu-id="f0e67-127">Deploy and configure the SBC</span></span>

<span data-ttu-id="f0e67-128">SBC 호스팅 시나리오에 대한 SBC를 배포하고 구성하는 방법에 대한 자세한 단계는 SBC 공급업체의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e67-128">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="f0e67-129">**AudioCodes:** [직접](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)라우팅 구성 정보 , "AudioCodes SBC를 Microsoft Teams 직접 라우팅 호스팅 호스팅 모델 구성 메모"에 설명된 SBC 호스팅 시나리오의 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-129">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note."</span></span> 
- <span data-ttu-id="f0e67-130">**Oracle:** [직접 라우팅](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)구성 정보 , SBC 호스팅 시나리오의 구성은 "Microsoft" 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-130">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="f0e67-131">**리본 메뉴 통신:**  리본 코어 시리즈 [SB를](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) 구성하는 방법에 대한 설명서 및 이 페이지 리본 메뉴 모범 사례 - Microsoft Teams 직접 라우팅 [SBC Edge에](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier) 대한 통신 사업자 구성에 대한 설명서는 리본 통신 SBC Core Microsoft Teams 구성 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e67-131">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)</span></span>
- <span data-ttu-id="f0e67-132">**TE-Systems(anynode):**  여러 테넌트에 대해 임의 SBC를 구성하는 방법에 대한 설명서 및 예제는 [TE-Systems](https://community.te-systems.de/) 커뮤니티 페이지에 등록하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e67-132">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>
- <span data-ttu-id="f0e67-133">**Metaswitch:**  여러 테넌트에 Perimeta SBC를 사용하도록 설정하는 방법에 대한 설명서는 [Metaswitch](https://manuals.metaswitch.com/MAN39555) 커뮤니티 페이지에 등록하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e67-133">**Metaswitch:**  Please register on the [Metaswitch Community page](https://manuals.metaswitch.com/MAN39555) for documentation on how to enable Perimeta SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="f0e67-134">"연락처" 헤더를 구성하는 방법에 주의합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-134">Please pay attention to how to configure the "Contact" header.</span></span> <span data-ttu-id="f0e67-135">연락처 헤더는 들어오는 초대 메시지에서 고객 테넌트 찾기에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-135">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="f0e67-136">기본 도메인 및 하위 도메인 등록</span><span class="sxs-lookup"><span data-stu-id="f0e67-136">Register a base domain and subdomains</span></span>

<span data-ttu-id="f0e67-137">호스팅 시나리오의 경우 다음을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-137">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="f0e67-138">운송업체가 소유한 하나의 기본 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-138">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="f0e67-139">모든 고객 테넌트에서 기본 도메인 이름의 일부인 하위 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-139">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="f0e67-140">다음 예제에서는</span><span class="sxs-lookup"><span data-stu-id="f0e67-140">In the following example:</span></span>
- <span data-ttu-id="f0e67-141">Adatum은 인터넷 및 전화 통신 서비스를 제공하여 여러 고객에게 서비스를 제공하는 통신 사업자입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-141">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="f0e67-142">Woodgrove Bank, Contoso 및 Adventure Works는 Microsoft 365 또는 Office 365 도메인을 사용하지만 Adatum에서 전화 통신 서비스를 받는 세 가지 고객입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-142">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Microsoft 365 or Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="f0e67-143">하위 도마는  Microsoft 365 또는 Office 365에 초대를 보낼 때 고객에 대해 구성될 트렁크의 FQDN 이름과 연락처 헤더의 FQDN과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-143">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="f0e67-144">Microsoft 365 또는 Office 365 직접 라우팅 인터페이스에 호출이 도착하면 인터페이스는 Contact 헤더를 사용하여 사용자를 검색해야 하는 테넌트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-144">When a call arrives at the Microsoft 365 or Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="f0e67-145">일부 고객에게는 여러 테넌트에서 겹칠 수 있는 DID이 아닌 번호가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-145">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="f0e67-146">따라서 연락처 헤더의 FQDN 이름은 전화 번호로 사용자를 찾아야 하는 정확한 테넌트 식별에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-146">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="f0e67-147">*Microsoft  [365 또는 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 조직에서 도메인 이름을 만드는 데 대한 자세한 내용은 Office 365 도메인에 대한 도움말을 검토하세요.*</span><span class="sxs-lookup"><span data-stu-id="f0e67-147">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="f0e67-148">다음 다이어그램에서는 기본 도메인, 하위 도메인 및 연락처 헤더에 대한 요구 사항을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-148">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![도메인 및 연락처 헤더에 대한 요구 사항을 보여주는 다이어그램](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="f0e67-150">SBC는 연결을 인증하기 위해 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-150">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="f0e67-151">SBC 호스팅 시나리오의 경우 통신 사업자는 CN 및/또는 SAN을 통해 인증서를 요청해야 *\* .base_domain(예: \* .customers.adatum.biz).*</span><span class="sxs-lookup"><span data-stu-id="f0e67-151">For the SBC hosting scenario, the carrier needs to request a certificate with CN and/or SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="f0e67-152">이 인증서를 사용하여 단일 SBC에서 제공된 여러 테넌트에 대한 연결을 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-152">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="f0e67-153">다음 표는 하나의 구성의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-153">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="f0e67-154">새 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="f0e67-154">New domain name</span></span> |<span data-ttu-id="f0e67-155">유형</span><span class="sxs-lookup"><span data-stu-id="f0e67-155">Type</span></span>|<span data-ttu-id="f0e67-156">등록</span><span class="sxs-lookup"><span data-stu-id="f0e67-156">Registered</span></span>  |<span data-ttu-id="f0e67-157">SBC용 인증서 CN/SAN</span><span class="sxs-lookup"><span data-stu-id="f0e67-157">Certificate CN/SAN for SBC</span></span>  |<span data-ttu-id="f0e67-158">예제의 테넌트 기본 도메인</span><span class="sxs-lookup"><span data-stu-id="f0e67-158">Tenant default domain in the example</span></span>  |<span data-ttu-id="f0e67-159">사용자에게 전화를 보낼 때 SBC가 연락처 헤더에 있어야 하는 FQDN 이름</span><span class="sxs-lookup"><span data-stu-id="f0e67-159">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="f0e67-160">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-160">customers.adatum.biz</span></span>|    <span data-ttu-id="f0e67-161">기본</span><span class="sxs-lookup"><span data-stu-id="f0e67-161">Base</span></span>     |     <span data-ttu-id="f0e67-162">통신 사업자 테넌트</span><span class="sxs-lookup"><span data-stu-id="f0e67-162">In carrier tenant</span></span>  |    <span data-ttu-id="f0e67-163">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-163">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="f0e67-164">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-164">adatum.biz</span></span>      |<span data-ttu-id="f0e67-165">NA, 서비스 테넌트, 사용자 없음</span><span class="sxs-lookup"><span data-stu-id="f0e67-165">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="f0e67-166">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-166">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="f0e67-167">하위omain</span><span class="sxs-lookup"><span data-stu-id="f0e67-167">Subdomain</span></span>  |    <span data-ttu-id="f0e67-168">고객 테넌트에서</span><span class="sxs-lookup"><span data-stu-id="f0e67-168">In a customer tenant</span></span>  |    <span data-ttu-id="f0e67-169">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-169">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="f0e67-170">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="f0e67-170">woodgrovebank.us</span></span>  |  <span data-ttu-id="f0e67-171">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-171">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="f0e67-172">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-172">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="f0e67-173">하위omain</span><span class="sxs-lookup"><span data-stu-id="f0e67-173">Subdomain</span></span> | <span data-ttu-id="f0e67-174">고객 테넌트에서</span><span class="sxs-lookup"><span data-stu-id="f0e67-174">In a customer tenant</span></span>   |   <span data-ttu-id="f0e67-175">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-175">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="f0e67-176">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0e67-176">contoso.com</span></span>   |<span data-ttu-id="f0e67-177">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-177">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="f0e67-178">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-178">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="f0e67-179">하위omain</span><span class="sxs-lookup"><span data-stu-id="f0e67-179">Subdomain</span></span> | <span data-ttu-id="f0e67-180">고객 테넌트에서</span><span class="sxs-lookup"><span data-stu-id="f0e67-180">In a customer tenant</span></span> |   <span data-ttu-id="f0e67-181">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-181">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="f0e67-182">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="f0e67-182">adventureworks.com</span></span> | <span data-ttu-id="f0e67-183">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-183">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="f0e67-184">기본 및 하위 배포를 구성하기 위해 아래에 설명된 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f0e67-184">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="f0e67-185">이 예제에서는 한 고객에 대한 기본 도메인 이름(customers.adatum.biz) 및 하위 도메인(Woodgrove Bank 테넌트의 sbc1.customers.adatum.biz)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-185">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="f0e67-186">통신 sbcX.customers.adatum.biz 사용하여 통신사 테넌트에서 음성을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-186">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span> <span data-ttu-id="f0e67-187">sbcX는 고유하고 유효한 영자 호스트 이름일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-187">sbcX can be any unique and valid alphanumeric hostname.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="f0e67-188">운송업체 테넌트에 기본 도메인 이름 등록</span><span class="sxs-lookup"><span data-stu-id="f0e67-188">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="f0e67-189">**이러한 작업은 통신 사업자 테넌트에서 수행됩니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-189">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="f0e67-190">운송업체 테넌트에 적절한 권한을 가졌다고 확인</span><span class="sxs-lookup"><span data-stu-id="f0e67-190">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="f0e67-191">전역 관리자로 Microsoft 365 관리 센터에 로그인한 경우 새 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-191">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="f0e67-192">역할의 유효성을 검사하려면 Microsoft 365 관리 센터에 로그인합니다(사용자 활성 사용자로 이동한 다음 전역 관리자 역할이 https://portal.office.com)   >  있는지 확인).</span><span class="sxs-lookup"><span data-stu-id="f0e67-192">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="f0e67-193">관리자 역할 및 Microsoft 365 또는 Office 365에서 역할을 할당하는 방법에 대한 자세한 내용은 관리자 역할 정보를 [참조하세요.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)</span><span class="sxs-lookup"><span data-stu-id="f0e67-193">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="f0e67-194">테넌트에 기본 도메인 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="f0e67-194">Add a base domain to the tenant and verify it</span></span>

1. <span data-ttu-id="f0e67-195">Microsoft 365 관리 센터에서 **설정** 도메인 추가  >    >  **도메인으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-195">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="f0e67-196">소유한 도메인 **입력** 상자에 기본 도메인의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-196">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="f0e67-197">다음 예제에서는 기본 도메인이 *customers.adatum.biz.*</span><span class="sxs-lookup"><span data-stu-id="f0e67-197">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![도메인 추가 페이지를 보여주는 스크린샷](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="f0e67-199">다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-199">Click **Next**.</span></span>
4. <span data-ttu-id="f0e67-200">이 예제에서 테넌트는 이미 확인된 도메인 adatum.biz 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-200">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="f0e67-201">마법사는 이미 등록된 이름의 하위 customers.adatum.biz 추가 확인을 요청하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-201">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="f0e67-202">그러나 전에 확인되지 않은 FQDN을 추가하는 경우 확인 프로세스를 진행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-202">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="f0e67-203">확인 프로세스는 [아래에 설명되어 있습니다.](#add-a-subdomain-to-the-customer-tenant-and-verify-it)</span><span class="sxs-lookup"><span data-stu-id="f0e67-203">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![확인된 도메인 이름 확인을 보여주는 스크린샷](media/direct-routing-3-sbc-verify-domain.png)

5. <span data-ttu-id="f0e67-205">**다음을** 클릭하고 **DNS** 설정 업데이트 페이지에서 **DNS** 레코드를 자신을 추가하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-205">Click **Next**, and on the **Update DNS Settings** page, select **I'll add the DNS records myself** and click **Next**.</span></span>
6. <span data-ttu-id="f0e67-206">다음 페이지에서 Exchange, SharePoint 또는 Teams/비즈니스용 Skype에 도메인 이름을 사용하지 않는 한 모든 값을 지우고 다음을 클릭한 다음 마침을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-206">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="f0e67-207">새 도메인이 설치 완료 상태인지 확인</span><span class="sxs-lookup"><span data-stu-id="f0e67-207">Make sure your new domain is in the Setup complete status.</span></span>

    ![설정이 완료된 도메인을 보여주는 스크린샷](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="f0e67-209">도메인 이름 활성화</span><span class="sxs-lookup"><span data-stu-id="f0e67-209">Activate the domain name</span></span>

<span data-ttu-id="f0e67-210">도메인 이름을 등록한 후 전화 시스템 라이선스가 있는 사용자를 하나 이상 추가하고 만든 기본 도메인과 일치하는 SIP 주소의 FQDN 부분이 있는 SIP 주소를 할당하여 도메인 이름을 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-210">After you have registered a domain name, you need to activate it by adding at least one user with Phone System license and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> <span data-ttu-id="f0e67-211">도메인 활성화 후 라이선스를 해지할 수 있습니다(최대 24시간이 걸릴 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="f0e67-211">License can be revoked after the domain activation (it can take up to 24 hours).</span></span>

> [!NOTE]
> <span data-ttu-id="f0e67-212">통신사 테넌트는 비즈니스용 Skype 구성을 제거하지 않도록 테넌트에 할당된 하나 이상의 전화 시스템 라이선스를 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-212">The Carrier tenant must keep at least one Phone System license assigned to the tenant to avoid removal of the Skype for Business configuration.</span></span> 

<span data-ttu-id="f0e67-213">*Microsoft [365 또는 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 조직에서 사용자 추가에 대한 자세한 내용은 Microsoft 365 또는 Office 365 도메인에 대한 도움말을 검토하세요.*</span><span class="sxs-lookup"><span data-stu-id="f0e67-213">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="f0e67-214">예: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-214">For example: test@customers.adatum.biz</span></span>

![기본 도메인 활성화 페이지의 스크린샷](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="f0e67-216">고객 테넌트에 하위omain 이름 등록</span><span class="sxs-lookup"><span data-stu-id="f0e67-216">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="f0e67-217">모든 고객에 대해 고유한 하위omain 이름을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-217">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="f0e67-218">이 예제에서는 기본 도메인 이름이 sbc1.customers.adatum.biz 테넌트에 하위 도메인 woodgrovebank.us.</span><span class="sxs-lookup"><span data-stu-id="f0e67-218">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="f0e67-219">**아래 모든 작업은 고객 테넌트에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-219">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="f0e67-220">고객 테넌트에 적절한 권한을 가야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-220">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="f0e67-221">전역 관리자로 Microsoft 365 관리 센터에 로그인한 경우 새 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-221">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="f0e67-222">역할의 유효성을 검사하려면 Microsoft 365 관리 센터에 로그인합니다(사용자 활성 사용자로 이동한 다음 전역 관리자 역할이 https://portal.office.com)   >  있는지 확인).</span><span class="sxs-lookup"><span data-stu-id="f0e67-222">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="f0e67-223">관리자 역할 및 Microsoft 365 또는 Office 365에서 역할을 할당하는 방법에 대한 자세한 내용은 관리자 역할 정보를 [참조하세요.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)</span><span class="sxs-lookup"><span data-stu-id="f0e67-223">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="f0e67-224">고객 테넌트에 하위omain을 추가하고 확인</span><span class="sxs-lookup"><span data-stu-id="f0e67-224">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="f0e67-225">Microsoft 365 관리 센터에서 **설정** 도메인 추가  >    >  **도메인으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-225">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="f0e67-226">소유한 도메인 **입력** 상자에 이 테넌트에 대한 하위 도메인의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-226">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="f0e67-227">아래 예제에서는 하위 sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="f0e67-227">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![도메인 추가 페이지의 스크린샷](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="f0e67-229">다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-229">Click **Next**.</span></span>
4. <span data-ttu-id="f0e67-230">FQDN은 테넌트에 등록된 적이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-230">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="f0e67-231">다음 단계에서는 도메인을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-231">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="f0e67-232">대신 **TXT 레코드 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-232">Select **Add a TXT record instead**.</span></span> 

    ![도메인 확인 페이지의 스크린샷](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="f0e67-234">다음을 **클릭하고** 도메인 이름을 확인하기 위해 생성된 TXT 값을 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-234">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![도메인 확인 페이지의 텍스트 레코드 스크린샷](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="f0e67-236">통신업체의 DNS 호스팅 공급자에서 이전 단계의 값을 사용하여 TXT 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-236">Create the TXT record with the value from the previous step in carrier's DNS hosting provider.</span></span>

    ![TXT 레코드 만들기를 보여주는 스크린샷](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="f0e67-238">자세한 내용은 DNS 호스팅 공급자에서 [DNS 레코드 만들기를 참조하세요.](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)</span><span class="sxs-lookup"><span data-stu-id="f0e67-238">For more information, refer to [Create DNS records at any DNS hosting provider](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="f0e67-239">고객의 Microsoft 365 관리 센터로 돌아가서 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-239">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="f0e67-240">다음 페이지에서 **DNS** 레코드를 자신을 추가하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-240">On the next page, select **I'll add the DNS records myself** and click **Next**.</span></span>

    ![DNS 설정 업데이트 페이지의 옵션 스크린샷](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="f0e67-242">온라인 서비스 **선택 페이지에서** 모든 옵션을 선택 취소하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-242">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![온라인 서비스 선택 페이지의 스크린샷](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="f0e67-244">DNS **설정** 업데이트 페이지에서 **마쳤습니다.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-244">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![DNS 설정 업데이트 페이지의 스크린샷](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="f0e67-246">상태가 설정 완료 **상태인지 확인**</span><span class="sxs-lookup"><span data-stu-id="f0e67-246">Ensure that the status is **Setup complete**.</span></span> 
    
    ![설치 완료 상태를 보여주는 페이지의 스크린샷](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> <span data-ttu-id="f0e67-248">직접 경로 트렁크를 추가할 수 있도록 개별 클라이언트의 기본 URL 및 하위 도마인이 동일한 테넌트에 _있을_ 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-248">The base URL and the subdomain for the individual client have to be on the same tenant to enable you to add a _direct route_ trunk.</span></span>

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="f0e67-249">하위omain 이름 활성화</span><span class="sxs-lookup"><span data-stu-id="f0e67-249">Activate the subdomain name</span></span>

<span data-ttu-id="f0e67-250">도메인 이름을 등록한 후 하나 이상의 사용자를 추가하여 활성화하고 고객 테넌트에서 만든 하위 도메인과 일치하는 SIP 주소의 FQDN 부분이 있는 SIP 주소를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-250">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span> <span data-ttu-id="f0e67-251">하위 배포 활성화 후 사용자로부터 라이선스를 해지할 수 있습니다(최대 24시간이 걸릴 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="f0e67-251">License can be revoked from user after the subdomain activation (it can take up to 24 hours).</span></span>

<span data-ttu-id="f0e67-252">*Microsoft [365 또는 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 조직에서 사용자 추가에 대한 자세한 내용은 Microsoft 365 또는 Office 365 도메인에 대한 도움말을 검토하세요.*</span><span class="sxs-lookup"><span data-stu-id="f0e67-252">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="f0e67-253">예: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="f0e67-253">For example: test@sbc1.customers.adatum.biz</span></span>

![하위omain 페이지의 활성화 스크린샷](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="f0e67-255">트렁크 만들기 및 사용자 프로비전</span><span class="sxs-lookup"><span data-stu-id="f0e67-255">Create a trunk and provision users</span></span>

<span data-ttu-id="f0e67-256">직접 라우팅의 초기 릴리스에서 Microsoft는 New-CSOnlinePSTNGateway를 사용하여 제공된 각 테넌트(고객 테넌트)에 트렁크를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-256">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="f0e67-257">그러나 다음 두 가지 이유로 최적으로 입증되지는 못합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-257">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="f0e67-258">**오버헤드 관리.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-258">**Overhead management**.</span></span> <span data-ttu-id="f0e67-259">예를 들어 SBC의 오프로드 또는 드레인은 미디어 우회 사용 또는 사용 안 끄기와 같은 일부 매개 변수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-259">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="f0e67-260">포트를 변경하려면 (Set-CSOnlinePSTNGateway를 실행하여) 여러 테넌트에서 매개 변수를 변경해야 하지만 실제로는 동일한 SBC입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-260">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="f0e67-261">**오버헤드 처리.**</span><span class="sxs-lookup"><span data-stu-id="f0e67-261">**Overhead processing**.</span></span> <span data-ttu-id="f0e67-262">트렁크 상태 데이터 수집 및 모니터링 - 실제로 동일한 SBC 및 동일한 물리적 트렁크인 여러 논리 트렁크에서 수집된 SIP 옵션은 라우팅 데이터의 처리 속도를 저하합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-262">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 
<span data-ttu-id="f0e67-263">이 피드백에 따라 Microsoft는 고객 테넌트에 대한 트렁크를 프로비전하는 새 논리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-263">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="f0e67-264">두 개의 새 엔터티가 도입됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-264">Two new entities were introduced:</span></span>
-    <span data-ttu-id="f0e67-265">New-CSOnlinePSTNGateway 명령을 사용하여 운송업체 테넌트에 등록된 통신사 트렁크(예: New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span><span class="sxs-lookup"><span data-stu-id="f0e67-265">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span></span>

-    <span data-ttu-id="f0e67-266">등록이 필요하지 않은 파생 트렁크입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-266">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="f0e67-267">운송업체 트렁크에서 추가된 원하는 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-267">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="f0e67-268">통신업체 트렁크에서 모든 구성 매개 변수를 파생합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-268">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="f0e67-269">파생 트렁크는 PowerShell에서 만들 필요가 없습니다. 통신사 트렁크와의 연결은 FQDN 이름을 기반으로 합니다(아래 세부 정보 참조).</span><span class="sxs-lookup"><span data-stu-id="f0e67-269">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="f0e67-270">**프로비전 논리 및 예제**</span><span class="sxs-lookup"><span data-stu-id="f0e67-270">**Provisioning logic and example**</span></span>

-    <span data-ttu-id="f0e67-271">운송업체는 다음 명령을 사용하여 단일 트렁크(운송업체 도메인의 운송업체 트렁크)만 설정하고 Set-CSOnlinePSTNGateway 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-271">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="f0e67-272">위의 예제에서는 다음 adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="f0e67-272">In the example above it is adatum.biz;</span></span>
-    <span data-ttu-id="f0e67-273">고객 테넌트에서 통신 사업자만 사용자의 음성 라우팅 정책에 파생 트렁크 FQDN을 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-273">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="f0e67-274">트렁크에 대해 New-CSOnlinePSTNGateway 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-274">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-    <span data-ttu-id="f0e67-275">이름에서 알 수 있 있처럼 파생된 트렁크는 운송업체 트렁크에서 모든 구성 매개 변수를 상속하거나 파생합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-275">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="f0e67-276">예:</span><span class="sxs-lookup"><span data-stu-id="f0e67-276">Examples:</span></span>
-    <span data-ttu-id="f0e67-277">Customers.adatum.biz - 운송업체 테넌트에서 만들어야 하는 운송업체 트렁크입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-277">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-    <span data-ttu-id="f0e67-278">Sbc1.customers.adatum.biz - PowerShell에서 만들 필요가 없는 고객 테넌트의 파생 트렁크입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-278">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="f0e67-279">온라인 음성 라우팅 정책의 고객 테넌트에서 파생 트렁크의 이름을 만들지 않고 간단히 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-279">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="f0e67-280">운송업체는 파생 트렁크 FQDN을 운송업체 SBC IP 주소로 확인하여 DNS 레코드를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-280">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-    <span data-ttu-id="f0e67-281">운송업체 트렁크(운송업체 테넌트)에 대한 변경 내용은 파생 트렁크에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-281">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="f0e67-282">예를 들어 운송업체는 운송업체 트렁크에서 SIP 포트를 변경할 수 있으며, 이 변경은 파생된 모든 트렁크에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-282">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="f0e67-283">트렁크를 구성하는 새 논리는 모든 테넌트로 이동하여 모든 트렁크에서 매개 변수를 변경할 필요가 없는 관리를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-283">New logic to configure the trunks simplifies the management as you don't need to go to every tenant and change the parameter on every trunk.</span></span>
-    <span data-ttu-id="f0e67-284">옵션은 운송업체 트렁크 FQDN으로만 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-284">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="f0e67-285">운송업체 트렁크의 상태는 파생된 모든 트렁크에 적용되고 라우팅 결정에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-285">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="f0e67-286">직접 라우팅 [옵션에](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)대해 더 많은 정보를 찾아 보십시오.</span><span class="sxs-lookup"><span data-stu-id="f0e67-286">Find out more about [Direct Routing options](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).</span></span>
-    <span data-ttu-id="f0e67-287">운송업체는 운송업체 트렁크를 드레인할 수 있으며 파생된 모든 트렁크도 드레인됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-287">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="f0e67-288">**이전 모델에서 운송업체 트렁크로 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="f0e67-288">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="f0e67-289">통신 사업자 호스팅 모델의 현재 구현에서 새 모델로 마이그레이션하려면 통신 사업자는 고객 테넌트에 대한 트렁크를 다시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-289">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="f0e67-290">(통신 사업자 테넌트에 트렁크를 Remove-CSOnlinePSTNGateway)를 사용하여 고객 테넌트에서 트렁크를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-290">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="f0e67-291">운송업체 및 파생 트렁크 모델을 사용하여 모니터링 및 프로비전을 향상하는 최대한 빨리 새 솔루션으로 마이그레이션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-291">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="f0e67-292">Contact 헤더에서 하위 메일의 FQDN 이름을 전송하도록 구성하는 방법에 대한 [SBC](#deploy-and-configure-the-sbc) 공급업체 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e67-292">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

## <a name="considerations-for-setting-up-muti-tenant-failover"></a><span data-ttu-id="f0e67-293">muti 테넌트 장애 조치(failover) 설정 시 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f0e67-293">Considerations for setting up muti-tenant failover</span></span> 

<span data-ttu-id="f0e67-294">다중 테넌트 환경에 대한 장애 조치(failover)를 설정하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-294">To set up failover for a multi-tenant environment, you'll need to do the following:</span></span>

- <span data-ttu-id="f0e67-295">각 테넌트에 대해 두 개의 서로 다른 SBC에 대한 FQDNS를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-295">For each tenant, add the FQDNs for two different SBCs.</span></span>  <span data-ttu-id="f0e67-296">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-296">For example:</span></span>

   <span data-ttu-id="f0e67-297">customer1.sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0e67-297">customer1.sbc1.contoso.com</span></span> <br>
   <span data-ttu-id="f0e67-298">customer1.sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0e67-298">customer1.sbc2.contoso.com</span></span> <br>

- <span data-ttu-id="f0e67-299">사용자의 온라인 음성 라우팅 정책에서 두 SBC를 모두 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-299">In the Online Voice Routing policies of the users, specify both SBCs.</span></span>  <span data-ttu-id="f0e67-300">하나의 SBC가 실패하면 라우팅 정책은 호출을 두 번째 SBC로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e67-300">If one SBC fails, the routing policy will route calls to the second SBC.</span></span>


## <a name="see-also"></a><span data-ttu-id="f0e67-301">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0e67-301">See also</span></span>

[<span data-ttu-id="f0e67-302">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="f0e67-302">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="f0e67-303">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="f0e67-303">Configure Direct Routing</span></span>](direct-routing-configure.md)
