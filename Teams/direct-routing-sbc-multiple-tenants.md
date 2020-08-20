---
title: 세션 테두리 컨트롤러 구성 - 다중 테넌트
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
description: Microsoft 파트너 및/또는 PSTN 통신 사업자를 위한 여러 테넌트를 제공하도록 한 세션 테두리 컨트롤러(SBC)를 구성하는 방법을 알아보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91ca12f3e0d9720800ad9b0bcf946df8d31b3e86
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814244"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="8822b-103">여러 테넌트에 대해 세션 경계 컨트롤러 구성</span><span class="sxs-lookup"><span data-stu-id="8822b-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="8822b-104">직접 라우터는 하나의 SBC(테두리 컨트롤러)를 구성하여 여러 테넌트 작업을 수행하려고 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="8822b-105">이 시나리오는 이 문서의 뒷부분에서 수행할 수 있는 Microsoft 파트너 및/또는 PSTN 통신 사원을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="8822b-106">Microsoft Teams에 제공된 전사리리리 서비스는 고객에게 전달된 기술 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="8822b-107">차이도:</span><span class="sxs-lookup"><span data-stu-id="8822b-107">A carrier:</span></span>
- <span data-ttu-id="8822b-108">SBC를 데이터 센터에 배포하고 관리합니다(고객은 SBC를 구현할 필요가 없으며 Teams 클라이언트의 전송 회사에서 전문 서비스를 받기).</span><span class="sxs-lookup"><span data-stu-id="8822b-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="8822b-109">SBC를 여러 테넌트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="8822b-110">고객에게 PSTN 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="8822b-111">통화 품질이 끝나는 지출을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="8822b-112">PSTN 서비스에 대해 별도로 요금이 청구됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="8822b-113">Microsoft는 이용하는 이동체를 관리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="8822b-114">Microsoft는 PBX(Microsoft 휴대폰 시스템) 및 Teams 클라이언트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client.</span></span> <span data-ttu-id="8822b-115">또한 Microsoft는 전화기를 인증하고 Microsoft 휴대폰 시스템과 함께 사용할 수 있는 SBC를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-115">Microsoft also certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="8822b-116">어떤 이용 중인 서비스를 선택하기 전에 선택한 SBC에 인증된 SBC가 있는지 확인하고 음성 품질을 끝까지 관리할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8822b-116">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="8822b-117">다음은 시나리오를 구성하기 위한 기술 구현 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-117">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="8822b-118">**Carrier만 해당:**</span><span class="sxs-lookup"><span data-stu-id="8822b-118">**Carrier only:**</span></span>
1. <span data-ttu-id="8822b-119">SBC를 배포하고 인증된 SBC 공급업체의 지침에 따라 호스팅 [시나리오에 맞게 구성합니다.](#deploy-and-configure-the-sbc)</span><span class="sxs-lookup"><span data-stu-id="8822b-119">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="8822b-120">통신 회사 테넌트에서 기본 도메인 이름을 등록하고 와일드카드 인증서를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-120">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="8822b-121">기본 도메인에 포함되는 모든 고객에 대한 하위 도메인을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-121">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="8822b-122">**고객 전역 관리자로 이동해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-122">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="8822b-123">고객 테넌트에 하위 도메인 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-123">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="8822b-124">하위 도메인 이름을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-124">Activate the subdomain name.</span></span>
3. <span data-ttu-id="8822b-125">통신 회사의 트리키를 고객 테넌트로 구성하고 사용자를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-125">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="8822b-126">*DNS 기본 사항과 Microsoft 365 또는 Office 365에서 도메인 이름이 관리되는 방법을 알고 있어야 합니다. 추가로 [진행하기 전에 Microsoft 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 또는 Office 365 도메인에 대한 도움말을 검토하세요.*</span><span class="sxs-lookup"><span data-stu-id="8822b-126">*Please make sure you understand DNS basics and how the domain name is managed in Microsoft 365 or Office 365. Review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="8822b-127">SBC 배포 및 구성</span><span class="sxs-lookup"><span data-stu-id="8822b-127">Deploy and configure the SBC</span></span>

<span data-ttu-id="8822b-128">SBC 호스팅 시나리오에 대해 SBC를 배포하고 구성하는 방법에 대한 자세한 단계는 SBC 공급업체의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8822b-128">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="8822b-129">**AudioCodes:** [직접 라우팅 구성 노트,](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)"Microsoft Teams 직접 라우팅 모델 구성 페이지에 AudioCodes SBC 연결 시나리오의 구성입니다."에 설명된 SBC 호스팅 시나리오의 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-129">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note."</span></span> 
- <span data-ttu-id="8822b-130">**Oracle:** [직접 라우팅 구성 노트에서](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)SBC 호스팅 시나리오의 구성을 "Microsoft" 섹션에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-130">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="8822b-131">**리본 메뉴 의사소통:**  리본 메뉴 면계 [SBC](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) 및 이 페이지 리본 모범 사례를 구성하는 방법에 대한 문서를 바꾸려면 리본 커뮤니케이션 SBC 커서 Microsoft Teams 구성 가이드를 참조하세요. Microsoft Teams 직접 라우트 라우징 [SBC Edge용 기본 구성](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)</span><span class="sxs-lookup"><span data-stu-id="8822b-131">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)</span></span>
- <span data-ttu-id="8822b-132">**TE-Systems(모노드):**  설명서 및 여러 테넌트에 대해 모노드 SBC를 구성하는 방법에 대한 자세한 내용은 [TE-Systems](https://community.te-systems.de/) 커뮤니티 페이지를 등록하세요.</span><span class="sxs-lookup"><span data-stu-id="8822b-132">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>
- <span data-ttu-id="8822b-133">**메타전환:**  여러 테넌트에 [대해 Perimeta](https://sso.metaswitch.com/UI/Login) SBC를 사용하도록 설정하는 방법에 대한 설명은 메타전환 커뮤니티 페이지에 등록하세요.</span><span class="sxs-lookup"><span data-stu-id="8822b-133">**Metaswitch:**  Please register on the [Metaswitch Community page](https://sso.metaswitch.com/UI/Login) for documentation on how to enable Perimeta SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="8822b-134">"연락처" 머리글을 구성하는 방법에 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="8822b-134">Please pay attention to how to configure the "Contact" header.</span></span> <span data-ttu-id="8822b-135">연락처 헤더는 받는 초대 메시지에서 고객 테넌트를 찾는 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-135">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="8822b-136">기본 도메인 및 하위 도메인 등록</span><span class="sxs-lookup"><span data-stu-id="8822b-136">Register a base domain and subdomains</span></span>

<span data-ttu-id="8822b-137">호스팅 시나리오에 대해 다음을 만들어서 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-137">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="8822b-138">이용 하고 있는 기본 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="8822b-138">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="8822b-139">모든 고객 테넌트에서 기본 도메인 이름에 포함되는 하위 도메인</span><span class="sxs-lookup"><span data-stu-id="8822b-139">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="8822b-140">다음 예제에서는 다음 과정이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-140">In the following example:</span></span>
- <span data-ttu-id="8822b-141">Adatum은 인터넷 및 원격 서비스를 제공하여 여러 고객을 서비스하는 통신 회사입니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-141">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="8822b-142">Woodgrove Bank, Contoso 및 Adventure Works는 Microsoft 365 또는 Office 365 도메인을 보유하만 Adatum에서 전화 서비스를 받는 3개의 고객입니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-142">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Microsoft 365 or Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="8822b-143">하위 **도메인은** Microsoft 365 또는 Office 365에 초대를 보낼 때 고객에 대해 구성할 트리크의 FQDN 이름과 연락처 헤더의 FQDN 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-143">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="8822b-144">통화가 Microsoft 365 또는 Office 365 직접 라우트 인터페이스에 도착하면 인터페이스는 연락처 머리글을 사용하여 사용자가 조회할 테넌트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-144">When a call arrives at the Microsoft 365 or Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="8822b-145">일부 고객에게는 여러 테넌트에서 겹을 수 있는 DID 번호가 있을 수 있지만, 일부 고객은 초대시에 전화 번호 조회를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-145">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="8822b-146">따라서 전화 번호로 사용자를 조회하기 위한 정확한 테넌트를 식별하려면 연락처 헤더의 FQDN 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-146">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="8822b-147">*Microsoft  [365 또는 Office 365 조직에서](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 도메인 이름을 만드는 방법에 자세한 내용은 Office 365 도메인에 대한 도움말을 검토하세요.*</span><span class="sxs-lookup"><span data-stu-id="8822b-147">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="8822b-148">다음 다이어그램에는 기본 도메인, 하위 도메인, 연락처 헤더에 대한 요구 사항이 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-148">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![도메인 및 연락처 헤더에 대한 요구 사항을 보여 주는 다이어그램](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="8822b-150">SBC를 연결하려면 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-150">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="8822b-151">SBC 호스팅 시나리오의 경우 이동 회사는 SAN \* \* .base_domain(예: \* .customers.adatum.biz)로 인증서를 요청해야 합니다.\*</span><span class="sxs-lookup"><span data-stu-id="8822b-151">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="8822b-152">이 인증서는 단일 SBC에서 보낸 여러 테넌트에 대한 연결을 인증하는 용도로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-152">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="8822b-153">다음 표에는 단일 구성의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-153">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="8822b-154">새 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="8822b-154">New domain name</span></span> |<span data-ttu-id="8822b-155">유형</span><span class="sxs-lookup"><span data-stu-id="8822b-155">Type</span></span>|<span data-ttu-id="8822b-156">등록됨</span><span class="sxs-lookup"><span data-stu-id="8822b-156">Registered</span></span>  |<span data-ttu-id="8822b-157">SBC용 인증서 SAN</span><span class="sxs-lookup"><span data-stu-id="8822b-157">Certificate SAN for SBC</span></span>  |<span data-ttu-id="8822b-158">예제의 테넌트 기본 도메인</span><span class="sxs-lookup"><span data-stu-id="8822b-158">Tenant default domain in the example</span></span>  |<span data-ttu-id="8822b-159">사용자에게 전화를 걸 때 SBC가 연락처 헤더에 있어서 제공해야 하는 FQDN 이름</span><span class="sxs-lookup"><span data-stu-id="8822b-159">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="8822b-160">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-160">customers.adatum.biz</span></span>|    <span data-ttu-id="8822b-161">base</span><span class="sxs-lookup"><span data-stu-id="8822b-161">Base</span></span>     |     <span data-ttu-id="8822b-162">이동 중 테넌트</span><span class="sxs-lookup"><span data-stu-id="8822b-162">In carrier tenant</span></span>  |    <span data-ttu-id="8822b-163">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-163">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="8822b-164">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-164">adatum.biz</span></span>      |<span data-ttu-id="8822b-165">NA, 서비스 테넌트이지만 사용자가 없음</span><span class="sxs-lookup"><span data-stu-id="8822b-165">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="8822b-166">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-166">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="8822b-167">Subdomain(하위 도메인)</span><span class="sxs-lookup"><span data-stu-id="8822b-167">Subdomain</span></span>  |    <span data-ttu-id="8822b-168">고객 테넌트 내</span><span class="sxs-lookup"><span data-stu-id="8822b-168">In a customer tenant</span></span>  |    <span data-ttu-id="8822b-169">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-169">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="8822b-170">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="8822b-170">woodgrovebank.us</span></span>  |  <span data-ttu-id="8822b-171">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-171">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="8822b-172">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-172">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="8822b-173">Subdomain(하위 도메인)</span><span class="sxs-lookup"><span data-stu-id="8822b-173">Subdomain</span></span> | <span data-ttu-id="8822b-174">고객 테넌트 내</span><span class="sxs-lookup"><span data-stu-id="8822b-174">In a customer tenant</span></span>   |   <span data-ttu-id="8822b-175">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-175">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="8822b-176">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8822b-176">contoso.com</span></span>   |<span data-ttu-id="8822b-177">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-177">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="8822b-178">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-178">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="8822b-179">Subdomain(하위 도메인)</span><span class="sxs-lookup"><span data-stu-id="8822b-179">Subdomain</span></span> | <span data-ttu-id="8822b-180">고객 테넌트 내</span><span class="sxs-lookup"><span data-stu-id="8822b-180">In a customer tenant</span></span> |   <span data-ttu-id="8822b-181">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-181">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="8822b-182">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="8822b-182">adventureworks.com</span></span> | <span data-ttu-id="8822b-183">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-183">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="8822b-184">기본 및 하위 도메인을 구성하려면 아래에 설명된 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="8822b-184">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="8822b-185">이 예제에서는 한 고객의 기본 도메인 이름(customers.adatum.biz)과 하위 도메인(Woodgrove Bankk에서 sbc1.customers.adatum.biz)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-185">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="8822b-186">이동 sbcX.customers.adatum.biz 지인의 테넌트에서 음성을 사용하도록 설정하는 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-186">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span> <span data-ttu-id="8822b-187">sbcX는 고유하고 유효한 알파숫자 호스트 이름일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-187">sbcX can be any unique and valid alphanumeric hostname.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="8822b-188">통신 사무실에서 기본 도메인 이름 등록</span><span class="sxs-lookup"><span data-stu-id="8822b-188">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="8822b-189">**이러한 작업은 이동 하면서 테넌트에서 수행됩니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-189">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="8822b-190">이동 원형 테넌트에 적절한 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8822b-190">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="8822b-191">전역 관리자로 Microsoft 365 관리 센터에 로그인한 경우만 새 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-191">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="8822b-192">가지고 있는 역할을 확인하려면 Microsoft 365 관리 센터(사용자 활성 사용자로 이동)한 다음 https://portal.office.com) 전역 **Users**  >  **Active Users**관리자 역할이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8822b-192">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="8822b-193">관리자 역할 및 Microsoft 365 또는 Office 365에서 관리자 역할할당 방법에 대한 자세한 내용은 [관리자 역할 정보를 참조하세요.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)</span><span class="sxs-lookup"><span data-stu-id="8822b-193">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="8822b-194">테넌트에 기본 도메인을 추가하고 확인</span><span class="sxs-lookup"><span data-stu-id="8822b-194">Add a base domain to the tenant and verify it</span></span>

1. <span data-ttu-id="8822b-195">Microsoft 365 관리 센터에서 **Setup**도메인 추가  >  **도메인으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-195">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="8822b-196">**소유한 도메인 입력 상자에** 기본 도메인의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-196">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="8822b-197">다음 예제에서는 기본 도메인이 표준 *customers.adatum.biz.*</span><span class="sxs-lookup"><span data-stu-id="8822b-197">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![도메인 추가 페이지를 보여 주는 스크린샷](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="8822b-199">다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-199">Click **Next**.</span></span>
4. <span data-ttu-id="8822b-200">예제에서 테넌트는 확인된 adatum.biz 이름으로 이미 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-200">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="8822b-201">장치가 이미 등록된 이름의 하위 customers.adatum.biz 부여하므로 마법사는 추가 인증을 요청하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-201">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="8822b-202">하지만 이전에 확인되지 않은 FQDN을 추가한 경우 확인 프로세스를 안내해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-202">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="8822b-203">확인 프로세스는 [다음과 설명되어 있습니다.](#add-a-subdomain-to-the-customer-tenant-and-verify-it)</span><span class="sxs-lookup"><span data-stu-id="8822b-203">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![확인된 도메인 이름을 확인하는 스크린샷](media/direct-routing-3-sbc-verify-domain.png)

5. <span data-ttu-id="8822b-205">**다음을**클릭하고 **DNS 설정 업데이트 페이지에서** DNS 레코드를 **스스로 추가하고 다음을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-205">Click **Next**, and on the **Update DNS Settings** page, select **I'll add the DNS records myself** and click **Next**.</span></span>
6. <span data-ttu-id="8822b-206">다음 페이지에서 Exchange, SharePoint 또는 Teams/비즈니스용 Skype의 도메인 이름을 사용하려는 경우가 아제나지 지우고 다음을 클릭하고 **마침을 클릭합니다.** **Next**</span><span class="sxs-lookup"><span data-stu-id="8822b-206">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="8822b-207">새 도메인이 설치 완료 상태에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-207">Make sure your new domain is in the Setup complete status.</span></span>

    ![설정 상태가 완료된 도메인을 보여 주는 스크린샷](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="8822b-209">도메인 이름 활성화</span><span class="sxs-lookup"><span data-stu-id="8822b-209">Activate the domain name</span></span>

<span data-ttu-id="8822b-210">도메인 이름을 등록한 후에는 라이선스가 하나 이상의 E1, E3 또는 E5 라이선스가 할당된 사용자를 추가하고 생성된 기본 도메인과 일치하는 SIP 주소의 FQDN 부분과 SIP 주소를 할당하여 이를 정품 인증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-210">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> <span data-ttu-id="8822b-211">도메인 인증 후에 라이선스를 해지할 수 있습니다(최대 24시간이 걸릴 수 있음).</span><span class="sxs-lookup"><span data-stu-id="8822b-211">License can be revoked after the domain activation (it can take up to 24 hours).</span></span>

<span data-ttu-id="8822b-212">*Microsoft [365 또는 Office 365 조직에서 사용자를](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 추가하는 방법에 대한 자세한 내용은 Microsoft 365 또는 Office 365 도메인에 대한 도움말을 검토하세요.*</span><span class="sxs-lookup"><span data-stu-id="8822b-212">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="8822b-213">예: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-213">For example: test@customers.adatum.biz</span></span>

![기본 도메인 활성화 페이지의 스크린샷](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="8822b-215">고객 테넌트에서 하위 도메인 이름 등록</span><span class="sxs-lookup"><span data-stu-id="8822b-215">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="8822b-216">모든 고객에 대해 고유한 하위 도메인 이름을 만들어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-216">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="8822b-217">이 예제에서는 하위 도메인 이름이 sbc1.customers.adatum.biz 테넌트에 하위 도메인 이름이 woodgrovebank.us.</span><span class="sxs-lookup"><span data-stu-id="8822b-217">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="8822b-218">**아래의 모든 작업은 고객 테넌트에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-218">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="8822b-219">고객 테넌트에 적절한 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8822b-219">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="8822b-220">전역 관리자로 Microsoft 365 관리 센터에 로그인한 경우만 새 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-220">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="8822b-221">가지고 있는 역할을 확인하려면 Microsoft 365 관리 센터(사용자 활성 사용자로 이동)한 다음 https://portal.office.com) 전역 **Users**  >  **Active Users**관리자 역할이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8822b-221">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="8822b-222">관리자 역할 및 Microsoft 365 또는 Office 365에서 관리자 역할할당 방법에 대한 자세한 내용은 [관리자 역할 정보를 참조하세요.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)</span><span class="sxs-lookup"><span data-stu-id="8822b-222">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="8822b-223">고객 테넌트에 하위 도메인 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="8822b-223">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="8822b-224">Microsoft 365 관리 센터에서 **Setup**도메인 추가  >  **도메인으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-224">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="8822b-225">**소유하고 있는 도메인 입력** 상자에 이 테넌트에 대한 하위 도메인의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-225">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="8822b-226">아래 예제에서는 하위 도메인이 sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="8822b-226">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![도메인 추가 페이지의 스크린샷](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="8822b-228">다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-228">Click **Next**.</span></span>
4. <span data-ttu-id="8822b-229">FQDN이 테넌트에 등록되어 있을 전용으로 등록되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-229">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="8822b-230">다음 단계에서는 도메인을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-230">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="8822b-231">대신 **TXT 레코드 추가를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="8822b-231">Select **Add a TXT record instead**.</span></span> 

    ![도메인 확인 페이지의 스크린샷](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="8822b-233">**다음을**클릭하고, 생성된 TXT 값을 확인하여 도메인 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-233">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![도메인 확인 페이지의 텍스트 레코드 스크린샷](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="8822b-235">이전 단계의 DNS 호스팅 공급자에 있는 값을 사용하여 TXT 레코드를 만입니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-235">Create the TXT record with the value from the previous step in carrier's DNS hosting provider.</span></span>

    ![TXT 레코드 만들기를 보여주는 스크린샷](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="8822b-237">자세한 내용은 모든 [DNS 호스팅 공급자에서 DNS 레코드 만들기를 참조하세요.](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)</span><span class="sxs-lookup"><span data-stu-id="8822b-237">For more information, refer to [Create DNS records at any DNS hosting provider](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="8822b-238">고객의 Microsoft 365 관리 센터로 돌아가서 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-238">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="8822b-239">다음 페이지에서 **DNS 레코드를 자기 레코드를 추가하고 다음을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-239">On the next page, select **I'll add the DNS records myself** and click **Next**.</span></span>

    ![DNS 설정 업데이트 페이지의 옵션 스크린샷](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="8822b-241">온라인 서비스 **선택 페이지에서 모든** 옵션의 선택을 취소하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-241">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![온라인 서비스 선택 페이지의 스크린샷](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="8822b-243">DNS **설정** 업데이트 **페이지에서 마침을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-243">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![DNS 설정 업데이트 페이지의 스크린샷](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="8822b-245">상태가 설정 **완료인지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="8822b-245">Ensure that the status is **Setup complete**.</span></span> 
    
    ![설정 완료 상태를 보여 주는 페이지 스크린샷](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="8822b-247">하위 도메인 이름 활성화</span><span class="sxs-lookup"><span data-stu-id="8822b-247">Activate the subdomain name</span></span>

<span data-ttu-id="8822b-248">도메인 이름을 등록한 후에는 사용자를 하나 이상 추가하고 고객 테넌트의 생성된 하위 도메인과 일치하는 SIP 주소의 FQDN 부분을 할당하여 이를 정품 인증한 후에는 이 주소를 정품 인증한 후에는 고객 테넌트의 생성된 하위 도메인과 일치하는 SIP 주소의 FQDN 부분을 할당하여 이를 정품 인증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-248">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span> <span data-ttu-id="8822b-249">하위 도메인 정품 인증 후 사용자로부터 라이선스를 해지할 수 있습니다(최대 24시간이 걸릴 수 있음).</span><span class="sxs-lookup"><span data-stu-id="8822b-249">License can be revoked from user after the subdomain activation (it can take up to 24 hours).</span></span>

<span data-ttu-id="8822b-250">*Microsoft [365 또는 Office 365 조직에서 사용자를](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 추가하는 방법에 대한 자세한 내용은 Microsoft 365 또는 Office 365 도메인에 대한 도움말을 검토하세요.*</span><span class="sxs-lookup"><span data-stu-id="8822b-250">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="8822b-251">예: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8822b-251">For example: test@sbc1.customers.adatum.biz</span></span>

![하위 도메인 페이지의 활성화 스크린샷](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="8822b-253">트런크 및 사용자 프로비전</span><span class="sxs-lookup"><span data-stu-id="8822b-253">Create a trunk and provision users</span></span>

<span data-ttu-id="8822b-254">직접 라우트를 초기 릴리스할 때 Microsoft는 New-CSOnlinePSTNGateway를 사용하여 각 Served 테넌트(고객 테넌트)에 트리크를 추가해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-254">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="8822b-255">그러나 다음은 두 가지 이유로 최적화되지 않지만 다음 두 가지 이유로 최적화되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-255">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="8822b-256">**오버헤드 관리**.</span><span class="sxs-lookup"><span data-stu-id="8822b-256">**Overhead management**.</span></span> <span data-ttu-id="8822b-257">SBC를 오프로드또는 사그오는 등의 일부 매개 변수를 변경합니다(예: 미디어 우회 사용 또는 사용 안 설정).</span><span class="sxs-lookup"><span data-stu-id="8822b-257">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="8822b-258">포트를 변경하려면 Set-CSOnlinePSTNGateway를 실행하는 방식으로 여러 테넌트에서 매개 변수를 변경해야 하지만 실제로 SBC에 있다는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-258">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="8822b-259">**오버헤드 처리**.</span><span class="sxs-lookup"><span data-stu-id="8822b-259">**Overhead processing**.</span></span> <span data-ttu-id="8822b-260">트러크 상태 데이터를 수집하고 모니터화 - 실제로 같은 SBC 및 동일한 물리적 트루크에서 수집된 SIP 옵션은 라우트 데이터의 처리 속도를 느려립니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-260">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 
<span data-ttu-id="8822b-261">Microsoft는 이 피드백을 기반으로 새 논리를 가져와 고객 테넌트에 대한 트런스키를 프로비저닝합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-261">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="8822b-262">두 가지 새 로고 가치가 도로로 도로 받되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-262">Two new entities were introduced:</span></span>
-    <span data-ttu-id="8822b-263">명령 New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI 문자)를 사용하여 통신 회사 테넌트에 등록된 전사 소송기 $true.</span><span class="sxs-lookup"><span data-stu-id="8822b-263">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span></span>

-    <span data-ttu-id="8822b-264">분산 트리스트의 경우 레지스트리가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-264">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="8822b-265">통신소 트리크에서 추가된 원하는 호스트 이름만으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-265">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="8822b-266">운동 체제 트리크에서 모든 구성 매개 변수를 파임합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-266">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="8822b-267">파생된 트상드타트를 PowerShell에서 만들 필요가 없으며, 통신사 트리너 트리스크와의 연결은 FQDN 이름을 기반으로 합니다(아래의 세부 내용 참조).</span><span class="sxs-lookup"><span data-stu-id="8822b-267">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="8822b-268">**프로비저닝 논리 및 예제**</span><span class="sxs-lookup"><span data-stu-id="8822b-268">**Provisioning logic and example**</span></span>

-    <span data-ttu-id="8822b-269">Using the csOnlinePSTNGateway 명령을 사용하여 단일 트런거크(이동통 도메인에서 통신사 트리거)를 설정하고 관리만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-269">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="8822b-270">위 예제에서는 값을 제16 행, adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="8822b-270">In the example above it is adatum.biz;</span></span>
-    <span data-ttu-id="8822b-271">고객 테넌트에서 사용하는 행위계는 장애가 있는 트리버 FQDN을 사용자의 음성 라우트 정책에 추가하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-271">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="8822b-272">트리크에 대해 New-CSOnlinePSTNGateway를 실행할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-272">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-    <span data-ttu-id="8822b-273">파동된 트리호(상점권 또는 파도는 이동 신호의 모든 구성 매개 변수를 상상시 또는 파동)합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-273">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="8822b-274">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-274">Examples:</span></span>
-    <span data-ttu-id="8822b-275">Customers.adatum.biz - 이동 중 테넌트에서 만들어야 하는 이동 지사의 트리시간.</span><span class="sxs-lookup"><span data-stu-id="8822b-275">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-    <span data-ttu-id="8822b-276">Sbc1.customers.adatum.biz - PowerShell에서 만들 필요가 없는 고객 테넌트에서 파생된 트리크입니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-276">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="8822b-277">파트너를 만들지 않고 온라인 음성 라우트에 있는 고객 테넌트에서 진원 명령 이름을 추가하는 것만으로도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-277">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="8822b-278">이동지리기는 계층 적타 FQDN을 확인한 DNS 레코드를 설정해야 버리는 PC SBC ip 주소를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-278">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-    <span data-ttu-id="8822b-279">통신사 트리키(통신사 테넌트에서 변경한 모든 내용은 파생 소크에 자동으로 적용됩니다.)</span><span class="sxs-lookup"><span data-stu-id="8822b-279">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="8822b-280">예를 들어 이동지는 어린이 트리크에서 SIP 포트를 변경할 수 있고, 이 변경 사항은 모든 파신 트리크에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-280">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="8822b-281">새 논리를 구성하면 모든 테넌트로 이동하여 모든 트루트에서 매개 변수를 변경할 필요가 있으기 때문에 관리가 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-281">New logic to configure the trunks simplifies the management as you don't need to go to every tenant and change the parameter on every trunk.</span></span>
-    <span data-ttu-id="8822b-282">이 옵션은 경계자 트리버 FQDN에만 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-282">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="8822b-283">통신사 트리크의 상태는 모든 파리형 트루크에 적용되며 라우트 고지에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-283">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="8822b-284">직접 라우트 [옵션에 대한 자세한 내용을 알아보세요.](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)</span><span class="sxs-lookup"><span data-stu-id="8822b-284">Find out more about [Direct Routing options](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).</span></span>
-    <span data-ttu-id="8822b-285">운신리운 운전체는 이용 중인 운입사자들이 만나기를 할 수 있고, 모든 어린 트러크도 고비됩니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-285">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="8822b-286">**이전 모델에서 이동- 실행형 트리키시스템으로 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="8822b-286">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="8822b-287">새 모델로 호스팅되는 모델의 현재 구현에서 새로운 모델로의 마이그레이션을 수행하려면 통신 회사는 고객 테넌트에 대한 트루크를 다시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-287">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="8822b-288">Remove-CSOnlinePSTNGateway를 사용하여 고객 테넌트에서 트런트를 제거(통신 회사 테넌트의 트플로크는 그대로 유지됨)</span><span class="sxs-lookup"><span data-stu-id="8822b-288">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="8822b-289">Microsoft는 통신기 및 시설된 트러크 모델을 사용하여 모니터링 및 프로비저닝되도록 새로운 솔루션으로 마이그레이션하는 것을 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-289">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="8822b-290">연락처 헤더에 있는 하위 도메인의 FQDN 이름을 전송하는 방법에 대한 [SBC](#deploy-and-configure-the-sbc) 공급업체 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8822b-290">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

## <a name="considerations-for-setting-up-muti-tenant-failover"></a><span data-ttu-id="8822b-291">음소스 테넌트 장애 조인 설정 을 고려해야 하는 문제</span><span class="sxs-lookup"><span data-stu-id="8822b-291">Considerations for setting up muti-tenant failover</span></span> 

<span data-ttu-id="8822b-292">다중 테넌트 환경에 대한 장애 조인을 설정하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-292">To set up failover for a multi-tenant environment, you'll need to do the following:</span></span>

- <span data-ttu-id="8822b-293">각 테넌트에 대해 두 개의 다른 SBC에 대한 FQDN을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-293">For each tenant, add the FQDNs for two different SBCs.</span></span>  <span data-ttu-id="8822b-294">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-294">For example:</span></span>

   <span data-ttu-id="8822b-295">customer1.sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8822b-295">customer1.sbc1.contoso.com</span></span> <br>
   <span data-ttu-id="8822b-296">customer1.sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8822b-296">customer1.sbc2.contoso.com</span></span> <br>

- <span data-ttu-id="8822b-297">사용자의 온라인 Voice 라우트 정책에서 두 SBC를 모두 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-297">In the Online Voice Routing policies of the users, specify both SBCs.</span></span>  <span data-ttu-id="8822b-298">한 SBC에 오류가 있는 경우 라우팅 정책은 두 번째 SBC로 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8822b-298">If one SBC fails, the routing policy will route calls to the second SBC.</span></span>


## <a name="see-also"></a><span data-ttu-id="8822b-299">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8822b-299">See also</span></span>

[<span data-ttu-id="8822b-300">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="8822b-300">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="8822b-301">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="8822b-301">Configure Direct Routing</span></span>](direct-routing-configure.md)

