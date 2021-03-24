---
title: Microsoft 365 또는 Office 365 조직과 클라우드 커넥터 통합 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Microsoft 365 또는 Office 365 조직과 클라우드 커넥터 통합을 구성하는 방법을 학습합니다.
ms.openlocfilehash: 74696023dcffbc91641bb4e9950f2988a89abbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095092"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="1753b-103">Microsoft 365 또는 Office 365 조직과 클라우드 커넥터 통합 구성</span><span class="sxs-lookup"><span data-stu-id="1753b-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>

> [!Important] 
> <span data-ttu-id="1753b-104">Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="1753b-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="1753b-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="1753b-106">Microsoft 365 또는 Office 365 조직과 클라우드 커넥터 통합을 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-106">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="1753b-107">비즈니스용 Skype 클라우드 커넥터 버전 설치가 완료되면 이 섹션의 단계를 수행하여 배포를 구성하고 Microsoft 365 또는 Office 365 조직에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-107">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="1753b-108">방화벽 설정 구성</span><span class="sxs-lookup"><span data-stu-id="1753b-108">Configure firewall settings</span></span>

<span data-ttu-id="1753b-109">경계 네트워크에 대한 내부 및 외부 방화벽 설정에 대한 방화벽 설정을 구성하여 [](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) Plan for Skype [for Business Cloud Connector Edition의](plan-skype-for-business-cloud-connector-edition.md)포트 및 프로토콜에 설명된 바와 같이 필요한 포트를 열도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-109">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="1753b-110">PSTN(Public Switched Telephone Network) 게이트웨이 설정</span><span class="sxs-lookup"><span data-stu-id="1753b-110">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="1753b-111">모든 어플라이언스에 대한 중재 서버를 다시 설정하기 위해 각 PSTN 게이트웨이에서 트렁크를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="1753b-112">풀 FQDN은 풀의 모든 서버에 대해 동일하기 때문에 각 트렁크는 중재 서버 풀 FQDN 대신 하나의 중재 서버 FQDN 또는 IP 주소를 지점해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-112">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="1753b-113">트렁크는 동일한 우선 순위로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-113">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="1753b-114">중재 서버와 게이트웨이 간에 TLS를 사용하는 경우 다음과 같이 MTLS를 지원하도록 게이트웨이 및 중재 서버를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-114">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="1753b-115">클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-115">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="1753b-116">루트 CA를 가져오는 데 대한 PSTN 게이트웨이 공급업체의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-116">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="1753b-117">중재 서버의 게이트웨이로 발급된 인증서에 대한 루트 CA 인증서를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-117">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="1753b-118">게이트웨이에 대한 SSL 인증서를 얻어야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행되는 인증 기관 서비스를 사용하여 이 작업을 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-118">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="1753b-119">기존 웹 서버 서식 파일을 수정하여 인증된 사용자가 등록하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성하고 인증된 사용자가 등록할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-119">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="1753b-120">자세한 지침은 인증서 템플릿 [을 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="1753b-120">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="1753b-121">사용하도록 설정한 웹 서버 템플릿을 선택하는 인증서 스냅인을 사용하여 인증서를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-121">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="1753b-122">게이트웨이의 FQDN을 사용하여 대체 이름의 주체 및 DNS 이름에 일반 이름을 추가하고 키 옵션에서 개인 키를 내보낼 수 있도록 설정이 선택되어 있는지 개인 키에 대해 확인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-122">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="1753b-123">개인 키로 SSL 인증서를 내보내고 인증서를 가져오기 위해 PSTN 게이트웨이 공급업체의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-123">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="1753b-124">테넌트의 도메인 업데이트</span><span class="sxs-lookup"><span data-stu-id="1753b-124">Update the domain for your tenant</span></span>

<span data-ttu-id="1753b-125">Microsoft 365 또는 Office 365에서 도메인을 업데이트하는 단계를 완료하고 DNS 레코드를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-125">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="1753b-126">Microsoft 365 또는 Office 365에서 도메인을 설정하는 방법에 대한 자세한 내용은 [Microsoft 365 또는 Office 365에 도메인 추가를 참조하세요.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="1753b-126">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="1753b-127">Edge에 대한 DNS 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="1753b-127">Add DNS records for your Edge</span></span>

<span data-ttu-id="1753b-128">Microsoft 365 또는 Office 365 조직에 다음 DNS 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-128">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="1753b-129">DNS 레코드를 추가하는 방법에 대한 자세한 내용은 [Microsoft 365 또는 Office 365에서](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)사용자 지정 DNS 레코드 추가 또는 편집을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1753b-129">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="1753b-130">액세스 에지용 DNS A 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-130">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="1753b-131">SRV 레코드는 Microsoft 365 또는 Office 365 및 배포 스크립트에 의해 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-131">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="1753b-132">에지에서 sip 및 \_ sipfederationtls의 두 SIP 서비스를 확인할 \_ 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-132">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![SRV 레코드 확인](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="1753b-134">클라우드 커넥터 버전과 Microsoft 365 또는 Office 365 간의 하이브리드 연결 설정</span><span class="sxs-lookup"><span data-stu-id="1753b-134">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="1753b-135">비즈니스용 Skype 클라우드 커넥터 버전 배포와 Microsoft 365 또는 Office 365 조직 간에 하이브리드 연결을 구성하기 위해 원격 PowerShell 세션에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-135">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="1753b-136">원격 PowerShell 세션을 설정하는 방법에 대한 자세한 내용은 Set [up your computer for Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="1753b-136">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
<span data-ttu-id="1753b-137">이 cmdlet은 액세스 에지 외부 FQDN을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-137">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="1753b-138">첫 번째 명령에서는 SIP 액세스 에지 역할에 \<External Access Edge FQDN\> 대한 명령이 에지 역할을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-138">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="1753b-139">기본적으로 이 구성은 ap \<Domain Name\> 입니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-139">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="1753b-140">피어 대상에 사용되는 외부 액세스 에지 FQDN은 사용자가 PSTN 사이트에 할당되지 않은 경우만 폴백으로 사용되는 PSTN 사이트로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-140">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="1753b-141">자세한 내용은 [클라우드](deploy-a-single-site-in-cloud-connector.md) 커넥터에서 단일 사이트 배포 및 클라우드 커넥터에서 여러 [사이트 배포를 참조하세요.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="1753b-141">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="1753b-142">PSTN 게이트웨이 설정</span><span class="sxs-lookup"><span data-stu-id="1753b-142">Set up PSTN gateways</span></span>

<span data-ttu-id="1753b-143">모든 어플라이언스에 대한 중재 서버를 다시 설정하기 위해 각 PSTN 게이트웨이에서 트렁크를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-143">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="1753b-144">풀 FQDN은 풀의 모든 서버에 대해 동일하기 때문에 각 트렁크는 중재 서버 풀 FQDN 대신 하나의 중재 서버 FQDN 또는 IP 주소를 지점해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-144">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="1753b-145">트렁크는 동일한 우선 순위로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-145">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="1753b-146">중재 서버와 게이트웨이 간에 TLS를 사용하는 경우 다음과 같이 MTLS를 지원하도록 게이트웨이 및 중재 서버를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-146">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="1753b-147">클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-147">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="1753b-148">루트 CA를 가져오는 데 대한 PSTN 게이트웨이 공급업체의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-148">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="1753b-149">중재 서버의 게이트웨이로 발급된 인증서에 대한 루트 CA 인증서를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-149">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="1753b-150">게이트웨이에 대한 SSL 인증서를 얻어야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행되는 인증 기관 서비스를 사용하여 이 작업을 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-150">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="1753b-151">기존 웹 서버 서식 파일을 수정하여 인증된 사용자가 등록할 수 있도록 설정하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성하고 인증된 사용자가 등록할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-151">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="1753b-152">자세한 지침은 인증서 템플릿 [을 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="1753b-152">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="1753b-153">사용하도록 설정한 웹 서버 템플릿을 선택하는 인증서 스냅인을 사용하여 인증서를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-153">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="1753b-154">게이트웨이의 FQDN을 사용하여 대체 이름의 주체 및 DNS 이름에 일반 이름을 추가하고 키 옵션에서 개인 키를 내보낼 수 있도록 설정이 선택되어 있는지 개인 키에 대해 확인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-154">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="1753b-155">개인 키로 SSL 인증서를 내보내고 인증서를 가져오기 위해 PSTN 게이트웨이 공급업체의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="1753b-156">한 PSTN 사이트의 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="1753b-157">사용자 설정</span><span class="sxs-lookup"><span data-stu-id="1753b-157">Set up your users</span></span>

<span data-ttu-id="1753b-158">Microsoft 365 관리 센터에 로그인하고, 온라인 음성 서비스를 사용할 수 있도록 할 사용자를 추가하고, E5 라이선스 또는 전화 시스템 추가 기능을 이러한 사용자에게 E3 라이선스에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-158">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="1753b-159">사용자 추가에 대한 자세한 내용은 [비즈니스용 Microsoft 365에 사용자 추가를 참조하세요.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)</span><span class="sxs-lookup"><span data-stu-id="1753b-159">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="1753b-160">사용자가 전화 시스템 음성 및 음성메일 서비스를 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="1753b-160">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="1753b-161">Microsoft 365 또는 Office 365에 사용자를 추가한 후 음성메일을 포함하여 전화 시스템 음성 서비스에 대한 계정을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="1753b-161">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="1753b-162">이러한 기능을 사용하려면 전역 관리자 역할인 계정을 사용하여 Microsoft 365 또는 Office 365 조직에 로그인하고 원격 PowerShell을 실행할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-162">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="1753b-163">원격 PowerShell 세션을 설정하는 방법에 대한 자세한 내용은 [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="1753b-163">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
- <span data-ttu-id="1753b-164">사용자에게 정책을 할당하고 Identity 매개 변수의 값으로 지정하는 사용자의 비즈니스 음성 전화 번호를 **구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="1753b-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="1753b-165">사용자 ID는 사용자의 SIP 주소, UPN(사용자 계정 이름) 또는 사용자의 Active Directory 표시 이름(예: "Bob Kelly")을 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-165">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="1753b-166">또한 표시 이름에 사용자 ID로 \* 추가() 문자를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-166">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="1753b-167">예를 들어 ID "Smith"는 표시 이름이 문자열 값 "Smith"로 끝나는 모든 사용자를 \* 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-167">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="1753b-168">그런 다음 다음 스크립트를 사용하여 사용자가 추가 및 사용하도록 설정되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-168">You can then verify that the users were added and enabled using the following script:</span></span>
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="1753b-169">사용자가 국제 전화를 걸 수 있는지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-169">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="1753b-170">기본적으로 국제 통화는 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-170">By default, international calling is enabled.</span></span> <span data-ttu-id="1753b-171">온라인 비즈니스용 Skype 관리 센터를 사용하여 사용자가 국제 전화 걸기를 사용할 수 있도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-171">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="1753b-172">사용자 기준으로 국제 통화를 사용하지 않도록 설정하기 위해 비즈니스용 Skype Online PowerShell에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-172">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="1753b-173">사용하지 않도록 설정한 후 사용자 기준 국제 통화를 다시 사용하도록 설정하려면 동일한 cmdlet을 실행하 고 **PolicyName의** 값을 *InternationalCallsAllowed로*  변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-173">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="1753b-174">PSTN 사이트에 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="1753b-174">Assign users to PSTN sites</span></span>

<span data-ttu-id="1753b-175">단일 사이트만 배포한 경우에도 테넌트 원격 PowerShell을 사용하여 사용자에게 사이트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-175">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="1753b-176">원격 PowerShell 세션을 설정하는 방법에 대한 자세한 내용은 Set [up your computer for Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="1753b-176">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="1753b-177">사용자에게 PSTN 사이트가 할당되지 않은 경우 통화를 완료할 수 있도록 비즈니스용 Skype 클라우드 커넥터 버전 배포와 Microsoft 365 또는 Office 365 조직 간의 하이브리드 연결은 테넌트 수준 기본 1(피어 대상)을 사용하기 위해 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-177">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="1753b-178">온라인 하이브리드 중재 서버 설정 구성</span><span class="sxs-lookup"><span data-stu-id="1753b-178">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="1753b-179"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="1753b-179"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="1753b-180">P2P 통화가 PSTN 회의로 에스컬레이터될 때 비즈니스용 Skype Online 회의 서버는 클라우드 커넥터 중재 서버로 초대를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-180">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="1753b-181">Microsoft 365 또는 Office 365에서 이 초대를 성공적으로 라우팅할 수 있도록 각 클라우드 커넥터 중재 서버에 대한 온라인 테넌트의 설정을 다음과 같이 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-181">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="1753b-182">Microsoft 365 관리 센터에서 사용자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-182">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1753b-183">원하는 사용자 이름(예: "MediationServer1")을 사용</span><span class="sxs-lookup"><span data-stu-id="1753b-183">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="1753b-184">클라우드 커넥터의 기본 SIP 도메인(.ini 파일의 첫 번째 SIP 도메인)을 사용자 도메인으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-184">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="1753b-185">라이선스 할당은 사용자가 비즈니스용 Skype 온라인 디렉터리로 전파하는 데만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-185">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="1753b-186">만든 계정에 Microsoft 365 또는 Office 365 라이선스(예: E5)를 할당하고, 변경 내용이 전파될 수 있도록 최대 1시간을 허용하고, 다음 cmdlet을 실행하여 사용자 계정이 비즈니스용 Skype 온라인 디렉터리에 올바르게 프로비전된 다음 이 계정에서 라이선스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-186">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="1753b-187">전역 또는 사용자 관리자 자격 증명을 사용하여 테넌트 Azure AD 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행하여 1단계에서 구성된 Azure AD 사용자 계정의 부서를 "HybridMediationServer"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-187">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="1753b-188">비즈니스용 Skype 테넌트 관리자 자격 증명을 사용하여 테넌트 비즈니스용 Skype 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행하여 중재 서버 및 에지 서버 FQDN을 해당 사용자 계정으로 설정하고, 1단계에서 만든 계정의 사용자 표시 이름으로 \<DisplayName\> 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-188">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="1753b-189">ID의 경우 이 중재 서버에 대해 만든 사용자 계정의 표시 이름을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1753b-189">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="1753b-190">*MediationServerFQDN의* 경우 중재 서버에 대해 정의된 내부 FQDN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-190">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="1753b-191">*EdgeServerExternalFQDN의* 경우 에지 서버 액세스 프록시에 정의된 외부 FQDN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1753b-191">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="1753b-192">클라우드 커넥터 PSTN 사이트가 여러 개 있는 경우 중재 서버가 있는 사이트에 할당된 에지 서버 액세스 프록시 FQDN을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="1753b-192">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="1753b-193">여러 클라우드 커넥터 중재 서버(다중 사이트, HA)가 있는 경우 각 서버에 대해 이전 단계를 반복하세요.</span><span class="sxs-lookup"><span data-stu-id="1753b-193">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
