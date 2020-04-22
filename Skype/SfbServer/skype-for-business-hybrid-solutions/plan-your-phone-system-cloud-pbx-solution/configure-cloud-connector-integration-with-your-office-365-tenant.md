---
title: Microsoft 365 또는 Office 365 조직과의 클라우드 커넥터 통합 구성
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
description: Office 365 조직과의 클라우드 커넥터 통합을 구성 하는 방법을 알아봅니다.
ms.openlocfilehash: 1fecf017f614fc8bdf0f38b5f51c29e4b2774357
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780647"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="040c1-103">Microsoft 365 또는 Office 365 조직과의 클라우드 커넥터 통합 구성</span><span class="sxs-lookup"><span data-stu-id="040c1-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>
 
<span data-ttu-id="040c1-104">Office 365 조직과의 클라우드 커넥터 통합을 구성 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-104">Learn how to configure Cloud Connector integration with your Office 365 organization.</span></span>
  
<span data-ttu-id="040c1-105">비즈니스용 Skype 클라우드 커넥터 Edition 설치가 완료 되 면이 섹션의 단계를 수행 하 여 배포를 구성 하 고 Office 365 조직에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="040c1-106">방화벽 설정 구성</span><span class="sxs-lookup"><span data-stu-id="040c1-106">Configure firewall settings</span></span>

<span data-ttu-id="040c1-107">주변 네트워크에 대 한 내부 및 외부 방화벽 설정에 대 한 방화벽 설정을 구성 하 여 [비즈니스용 Skype 클라우드 커넥터 에디션 계획](plan-skype-for-business-cloud-connector-edition.md)의 [포트 및 프로토콜](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) 에 설명 된 대로 필요한 포트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="040c1-108">공중 전화망 (PSTN) 게이트웨이 설정</span><span class="sxs-lookup"><span data-stu-id="040c1-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="040c1-109">모든 기기에 대 한 중재 서버를 가리키도록 각 PSTN 게이트웨이에서 트렁크을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="040c1-110">풀 FQDN은 풀에 있는 모든 서버에서 동일 하므로 각 트렁크는 중재 서버 풀 FQDN 대신 하나의 중재 서버 FQDN 또는 IP 주소를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="040c1-111">트렁크는 동일한 우선 순위로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="040c1-112">중재 서버와 게이트웨이 간에 TLS를 사용 하는 경우 다음과 같이 MTLS를 지원 하도록 게이트웨이 및 중재 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="040c1-113">클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="040c1-114">PSTN 게이트웨이 공급 업체 지침에 따라 루트 CA를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="040c1-115">중재 서버에서 게이트웨이로 발급 된 인증서에 대 한 루트 CA 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="040c1-116">게이트웨이에 대 한 SSL 인증서를 취득 해야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행 되는 인증 기관 서비스를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="040c1-117">기존 웹 서버 서식 파일을 수정 하 여 인증 된 사용자가 등록 하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성 하 고 인증 된 사용자가 등록할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="040c1-118">자세한 내용은 [인증서 템플릿을](https://technet.microsoft.com/library/cc730705.aspx)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="040c1-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="040c1-119">사용 하도록 설정한 웹 서버 서식 파일을 선택 하 여 인증서 스냅인을 사용 하 여 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="040c1-120">주체 및 DNS 이름의 일반 이름을 게이트웨이 FQDN과 함께 대체 이름으로 추가 하 고, 키 옵션에서 내보낼 수 있는 개인 키를 선택 하는 개인 키를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="040c1-121">개인 키를 사용 하 여 SSL 인증서를 내보내고 PSTN 게이트웨이 공급 업체의 지침에 따라 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="040c1-122">테 넌 트에 대 한 도메인 업데이트</span><span class="sxs-lookup"><span data-stu-id="040c1-122">Update the domain for your tenant</span></span>

<span data-ttu-id="040c1-123">Office 365에서 도메인을 업데이트 하는 단계를 완료 했으며 DNS 레코드를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="040c1-124">Office 365에서 도메인을 설정 하는 방법에 대 한 자세한 내용은 [Add a domain To office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="040c1-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="040c1-125">에 지에 대 한 Office 365의 DNS 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="040c1-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="040c1-126">Office 365 조직에 다음 DNS 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-126">Add the following DNS records to your Office 365 organization.</span></span> <span data-ttu-id="040c1-127">Office 365 조직에 DNS 레코드를 추가 하는 방법에 대 한 자세한 내용은 [office 365에서 사용자 지정 dns 레코드 추가 또는 편집](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="040c1-127">For information about how to add DNS records to your Office 365 organization, see [Add or edit custom DNS records in Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="040c1-128">액세스에 지에 대 한 DNS A 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="040c1-129">SRV 레코드는 Office 365 및 배포 스크립트에 의해 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-129">SRV records will automatically be created by Office 365 and the deployment scripts.</span></span> <span data-ttu-id="040c1-130">Edge: _sip 및 _sipfederationtls에서 다음 두 SIP 서비스를 조회할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-130">Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![SRV 레코드 확인](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="040c1-132">클라우드 커넥터 버전 및 Office 365 간 하이브리드 연결 설정</span><span class="sxs-lookup"><span data-stu-id="040c1-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="040c1-133">비즈니스용 Skype 클라우드 커넥터 에디션 배포와 Office 365 조 직 간에 하이브리드 연결을 구성 하려면 원격 PowerShell 세션에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="040c1-134">원격 PowerShell 세션을 설정 하는 방법에 [대 한 자세한 내용은 Windows PowerShell에 대 한 컴퓨터 설정](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="040c1-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="040c1-135">Cmdlet은 액세스에 지 외부 FQDN을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="040c1-136">첫 번째 명령에서 외부 액세스에 지 \<FQDN\> 은 SIP 액세스에 지 역할에 대해 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="040c1-137">기본적으로이 이름은 ap. 도메인 이름\<\>이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="040c1-138">피어 대상에 사용 되는 외부 액세스에 지 FQDN은 사용자가 PSTN 사이트에 할당 되지 않은 경우에만 폴백으로 사용 되는 PSTN 사이트로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="040c1-139">자세한 내용은 [클라우드 커넥터에 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md) 및 [클라우드 커넥터에 여러 사이트 배포](deploy-multiple-sites-in-cloud-connector.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="040c1-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="040c1-140">PSTN 게이트웨이 설정</span><span class="sxs-lookup"><span data-stu-id="040c1-140">Set up PSTN gateways</span></span>

<span data-ttu-id="040c1-141">모든 기기에 대 한 중재 서버를 가리키도록 각 PSTN 게이트웨이에서 트렁크을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="040c1-142">풀 FQDN은 풀에 있는 모든 서버에서 동일 하므로 각 트렁크는 중재 서버 풀 FQDN 대신 중재 서버 FQDN 또는 IP 주소 하나를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="040c1-143">트렁크는 동일한 우선 순위로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="040c1-144">중재 서버와 게이트웨이 간에 TLS를 사용 하는 경우 다음과 같이 MTLS를 지원 하도록 게이트웨이 및 중재 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="040c1-145">클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="040c1-146">PSTN 게이트웨이 공급 업체 지침에 따라 루트 CA를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="040c1-147">중재 서버에서 게이트웨이로 발급 된 인증서에 대 한 루트 CA 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="040c1-148">게이트웨이에 대 한 SSL 인증서를 취득 해야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행 되는 인증 기관 서비스를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="040c1-149">기존 웹 서버 서식 파일을 수정 하 여 인증 된 사용자가 등록 하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성 하 고 인증 된 사용자가 등록할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="040c1-150">자세한 내용은 [인증서 템플릿을](https://technet.microsoft.com/library/cc730705.aspx)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="040c1-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="040c1-151">사용 하도록 설정한 웹 서버 서식 파일을 선택 하 여 인증서 스냅인을 사용 하 여 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="040c1-152">주체 및 DNS 이름의 일반 이름을 게이트웨이 FQDN과 함께 대체 이름으로 추가 하 고, 키 옵션에서 내보낼 수 있는 개인 키를 선택 하는 개인 키를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="040c1-153">개인 키를 사용 하 여 SSL 인증서를 내보내고 PSTN 게이트웨이 공급 업체의 지침에 따라 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="040c1-154">PSTN 사이트 하나에 있는 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="040c1-155">Office 365에서 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="040c1-155">Set up your users in Office 365</span></span>

<span data-ttu-id="040c1-156">Microsoft 365 관리 센터에 로그인 하 고, 온라인 음성 서비스에 사용할 사용자를 추가 하 고, 다음 사용자에 게 E3 라이선스에 대 한 e 5 추가 기능 365에서 E5 라이선스 또는 전화 시스템을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-156">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="040c1-157">사용자를 추가 하는 방법에 대 한 자세한 내용은 [비즈니스용 Office 365에 사용자 추가](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="040c1-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="040c1-158">Office 365 음성 및 음성 메일 서비스에서 전화 시스템에 대해 사용자를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="040c1-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="040c1-159">Office 365에 사용자를 추가한 후 음성 메일을 포함 하 여 Office 365 음성 서비스에서 전화 시스템용 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="040c1-160">이러한 기능을 사용 하도록 설정 하려면 전역 관리자 역할인 계정을 사용 하 여 Office 365 조직에 로그인 하 고 원격 PowerShell을 실행할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-160">To enable these capabilities, you must log in to your Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="040c1-161">원격 PowerShell 세션을 설정 하는 방법에 [대 한 자세한 내용은 Windows PowerShell에 대 한 컴퓨터 설정](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="040c1-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="040c1-162">사용자에 게 정책을 할당 하 고 **Identity** 매개 변수의 값으로 지정 하는 사용자의 비즈니스 음성 전화 번호를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="040c1-163">사용자의 SIP 주소, UPN (사용자 계정 이름) 또는 사용자의 Active Directory 표시 이름 (예: "Bob 최소라")을 사용 하 여 id를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="040c1-164">별표 (\*) 문자는 사용자 Id로 표시 이름과 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="040c1-165">예를 들어 Id "\*smith"는 표시 이름이 문자열 값 "Smith"로 끝나는 모든 사용자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="040c1-166">그러면 다음 스크립트를 사용 하 여 사용자가 추가 되 고 사용 하도록 설정 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="040c1-167">사용자가 국제 전화를 걸 수 있도록 할지 여부를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-167">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="040c1-168">기본적으로 국제 통화는 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-168">By default, international calling is enabled.</span></span> <span data-ttu-id="040c1-169">온라인 비즈니스용 Skype 관리 센터를 사용 하 여 국제 전화 걸기에 대해 사용자를 사용 하지 않도록 설정 하거나 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-169">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="040c1-170">사용자별로 국제 통화를 사용 하지 않도록 설정 하려면 비즈니스용 Skype Online PowerShell에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="040c1-171">사용자 단위를 사용 하지 않도록 설정한 후 국가별 호출을 다시 사용 하도록 설정 하려면 동일한 cmdlet을 실행 하 되 **PolicyName** 의 값을 *InternationalCallsAllowed* 로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="040c1-172">PSTN 사이트에 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="040c1-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="040c1-173">단일 사이트만 배포한 경우에도 테 넌 트 원격 PowerShell을 사용 하 여 사용자에 게 사이트를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="040c1-174">원격 PowerShell 세션을 설정 하는 방법에 [대 한 자세한 내용은 Windows PowerShell에 대 한 컴퓨터 설정](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="040c1-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="040c1-175">사용자에 게 할당 된 PSTN 사이트가 없는 경우 비즈니스용 Skype 클라우드 커넥터 에디션 배포와 Office 365 조직 간의 하이브리드 연결이 다시 시도 하 여 전화를 완료할 수 있도록 테 넌 트 수준 기본 1 (피어 대상)을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="040c1-176">온라인 하이브리드 중재 서버 설정 구성</span><span class="sxs-lookup"><span data-stu-id="040c1-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="040c1-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="040c1-177"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="040c1-178">P2P 호출이 PSTN 회의로 에스컬레이션 되 면 비즈니스용 Skype 온라인 회의 서버에서 클라우드 커넥터 중재 서버에 대 한 초대를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="040c1-179">Office 365에서이 초대를 라우팅할 수 있도록 하려면 각 클라우드 커넥터 중재 서버에 대해 다음과 같이 온라인 테 넌 트의 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="040c1-180">Microsoft 365 관리 센터에서 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-180">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="040c1-181">원하는 사용자 이름 (예: "MediationServer1")을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="040c1-182">사용자 도메인으로는 클라우드 커넥터의 기본 SIP 도메인 (.ini 파일의 첫 번째 SIP 도메인)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="040c1-183">라이선스 할당은 비즈니스용 Skype online 디렉터리로의 사용자 전파에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="040c1-184">만든 계정에 Office 365 라이선스 (예: E5)를 할당 하 고, 변경 내용을 전파할 최대 1 시간을 허용 하 고, 다음 cmdlet을 실행 하 여 사용자 계정이 비즈니스용 Skype 온라인 디렉터리에 올바르게 프로 비전 되었는지 확인 한 후에이 계정에서 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="040c1-185">전역 또는 사용자 관리자 자격 증명을 사용 하 여 테 넌 트 Azure AD 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행 하 여 1 단계에서 구성한 Azure AD 사용자 계정에 대 한 부서를 "HybridMediationServer"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="040c1-186">비즈니스용 Skype 테 넌 트 관리자 자격 증명을 사용 하 여 테 넌 트 비즈니스용 Skype 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행 하 여 중재 서버 및에 지 서버 FQDN을 해당 사용자 \<계정\> 으로 설정 하 고 DisplayName을 1 단계에서 만든 계정에 대 한 사용자의 표시 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="040c1-187">Id의 경우이 중재 서버에 대해 만든 사용자 계정의 표시 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-187">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="040c1-188">*Mediationserverfqdn* 에 대해 중재 서버에 대해 정의 된 내부 FQDN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="040c1-189">*EdgeServerExternalFQDN* 의 경우에 지 서버 액세스 프록시에 대해 정의 된 외부 FQDN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="040c1-190">클라우드 커넥터 PSTN 사이트가 여러 개인 경우 중재 서버가 있는 사이트에 할당 된에 지 서버 액세스 프록시 FQDN을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="040c1-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="040c1-191">여러 클라우드 커넥터 중재 서버 (다중 사이트, HA)가 있는 경우에는 각 작업에 대해 위의 단계를 반복 해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="040c1-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

