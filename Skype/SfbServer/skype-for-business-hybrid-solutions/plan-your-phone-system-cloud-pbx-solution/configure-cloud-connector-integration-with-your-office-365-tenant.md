---
title: Office 365 테넌트와 클라우드 커넥터 통합을 구성
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
description: Office 365 테 넌 트에서 클라우드 커넥터 통합을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3e451757d82957987b394b67babe88dac199715b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803588"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="5fd70-103">Office 365 테넌트와 클라우드 커넥터 통합을 구성</span><span class="sxs-lookup"><span data-stu-id="5fd70-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="5fd70-104">Office 365 테 넌 트에서 클라우드 커넥터 통합을 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="5fd70-105">비즈니스용 Skype 클라우드 커넥터 버전 설치가 완료 되 면이 섹션의 단계를 수행 하 여 배포를 구성 하 고 Office 365 테 넌 트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="5fd70-106">방화벽 설정 구성</span><span class="sxs-lookup"><span data-stu-id="5fd70-106">Configure firewall settings</span></span>

<span data-ttu-id="5fd70-107">주변 네트워크의 내부 및 외부 방화벽 설정에 대 한 방화벽 설정을 구성 하 여 [비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 계획](plan-skype-for-business-cloud-connector-edition.md)의 [포트 및 프로토콜](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) 에 설명 된 대로 필요한 포트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="5fd70-108">PSTN (공개 교환 전화 네트워크) 게이트웨이 설정</span><span class="sxs-lookup"><span data-stu-id="5fd70-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="5fd70-109">모든 기기에 대 한 중재 서버로 다시 가리키도록 각 PSTN 게이트웨이에서 trunks을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="5fd70-110">풀의 모든 서버에서 풀 FQDN이 동일 하기 때문에 각 트렁크는 중재 서버 풀 FQDN 대신 하나의 중재 서버 FQDN 또는 IP 주소를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="5fd70-111">Trunks는 동일한 우선 순위로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="5fd70-112">중재 서버와 게이트웨이 간에 TLS를 사용 하는 경우 다음과 같이 MTLS를 지원 하도록 게이트웨이 및 중재 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="5fd70-113">클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="5fd70-114">PSTN 게이트웨이 공급 업체 지침에 따라 루트 CA를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="5fd70-115">중재 서버에서 게이트웨이로 발급 된 인증서에 대 한 루트 CA 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="5fd70-116">게이트웨이에 대 한 SSL 인증서를 구해야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행 되는 인증 기관 서비스를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="5fd70-117">기존 웹 서버 템플릿을 수정 하 여 인증 된 사용자가 등록 하도록 설정 하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성 하 고 인증 된 사용자가 등록할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="5fd70-118">자세한 지침은 [인증서 템플릿을](https://technet.microsoft.com/en-us/library/cc730705.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd70-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="5fd70-119">사용 하도록 설정한 웹 서버 서식 파일을 선택 하 여 인증서 스냅인을 사용 하 여 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="5fd70-120">대체 이름에 게이트웨이의 FQDN을 사용 하 여 제목 및 DNS 이름에 일반 이름을 추가 하 고, 키를 내보낼 수 있도록 하는 개인 키를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="5fd70-121">개인 키를 사용 하 여 SSL 인증서를 내보내고 PSTN 게이트웨이 공급 업체의 지침에 따라 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="5fd70-122">테 넌 트의 도메인 업데이트</span><span class="sxs-lookup"><span data-stu-id="5fd70-122">Update the domain for your tenant</span></span>

<span data-ttu-id="5fd70-123">Office 365에서 도메인을 업데이트 하는 단계를 완료 하 고 DNS 레코드를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="5fd70-124">Office 365에서 도메인을 설정 하는 방법에 대 한 자세한 내용은 [office 365에 도메인 추가](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd70-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="5fd70-125">Edge 용 Office 365에서 DNS 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="5fd70-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="5fd70-126">다음 DNS 레코드를 Office 365 테 넌 트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="5fd70-127">Office 365 테 넌 트에 DNS 레코드를 추가 하는 방법에 대 한 자세한 내용은 [office 365에서 사용자 지정 DNS 레코드 추가 또는 편집](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd70-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="5fd70-128">액세스에 지에 대 한 DNS A 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="5fd70-129">SRV 레코드는 Office 365 및 배포 스크립트에서 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-129">SRV records will automatically be created by Office 365 and the deployment scripts.</span></span> <span data-ttu-id="5fd70-130">Edge에서 _sip 및 _sipfederationtls에 다음 두 가지 SIP 서비스를 조회할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-130">Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![SRV 레코드 확인](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="5fd70-132">클라우드 커넥터 버전 및 Office 365 간 하이브리드 연결 설정</span><span class="sxs-lookup"><span data-stu-id="5fd70-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="5fd70-133">비즈니스용 Skype 클라우드 커넥터 에디션 배포와 Office 365 테 넌 트 간 하이브리드 연결을 구성 하려면 원격 PowerShell 세션에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="5fd70-134">원격 PowerShell 세션을 설정 하는 방법에 [대 한 자세한 내용은 Windows PowerShell 용 컴퓨터 설정을](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd70-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="5fd70-135">Cmdlet은 액세스 경계 외부 FQDN을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="5fd70-136">첫 번째 명령에는 외부 액세스에 \<지 FQDN\> 이 SIP 액세스에 지 역할에 대 한 것 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="5fd70-137">기본적으로 ap. 도메인 이름\<\>이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="5fd70-138">피어 대상에 사용 되는 외부 액세스에 지 FQDN은 사용자가 PSTN 사이트에 할당 되지 않은 경우에만 fallback로 사용 되는 PSTN 사이트로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="5fd70-139">자세한 내용은 [클라우드 커넥터에 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md) 및 [클라우드 커넥터에 여러 사이트 배포](deploy-multiple-sites-in-cloud-connector.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd70-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="5fd70-140">PSTN 게이트웨이 설정</span><span class="sxs-lookup"><span data-stu-id="5fd70-140">Set up PSTN gateways</span></span>

<span data-ttu-id="5fd70-141">모든 기기에 대 한 중재 서버로 다시 가리키도록 각 PSTN 게이트웨이에서 trunks을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="5fd70-142">풀의 FQDN이 풀의 모든 서버에서 동일 하기 때문에 각 트렁크는 중재 서버 풀 FQDN 대신 하나의 중재 서버 FQDN 또는 IP 주소를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="5fd70-143">Trunks는 동일한 우선 순위로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="5fd70-144">중재 서버와 게이트웨이 간에 TLS를 사용 하는 경우 다음과 같이 MTLS를 지원 하도록 게이트웨이 및 중재 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="5fd70-145">클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="5fd70-146">PSTN 게이트웨이 공급 업체 지침에 따라 루트 CA를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="5fd70-147">중재 서버에서 게이트웨이로 발급 된 인증서에 대 한 루트 CA 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="5fd70-148">게이트웨이에 대 한 SSL 인증서를 구해야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행 되는 인증 기관 서비스를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="5fd70-149">기존 웹 서버 템플릿을 수정 하 여 인증 된 사용자가 등록 하도록 설정 하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성 하 고 인증 된 사용자가 등록할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="5fd70-150">자세한 지침은 [인증서 템플릿을](https://technet.microsoft.com/library/cc730705.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd70-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="5fd70-151">사용 하도록 설정한 웹 서버 서식 파일을 선택 하 여 인증서 스냅인을 사용 하 여 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="5fd70-152">대체 이름에 게이트웨이의 FQDN을 사용 하 여 제목 및 DNS 이름에 일반 이름을 추가 하 고, 키를 내보낼 수 있도록 하는 개인 키를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="5fd70-153">개인 키를 사용 하 여 SSL 인증서를 내보내고 PSTN 게이트웨이 공급 업체의 지침에 따라 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="5fd70-154">한 PSTN 사이트의 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="5fd70-155">Office 365에서 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="5fd70-155">Set up your users in Office 365</span></span>

<span data-ttu-id="5fd70-156">Office 365 관리 포털에 로그인 하 고, 온라인 음성 서비스에 사용할 사용자를 추가 하 고, Office 365 추가 기능에서이 사용자에 게 E3 라이선스에 대 한 E5 라이선스 또는 전화 시스템을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="5fd70-157">사용자를 추가 하는 방법에 대 한 자세한 내용은 [Office for business 365에 사용자 추가](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd70-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="5fd70-158">Office 365 음성 및 보이스 메일 서비스에서 전화 시스템용 사용자 사용</span><span class="sxs-lookup"><span data-stu-id="5fd70-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="5fd70-159">Office 365에 사용자를 추가한 후에는 음성 메일을 포함 하 여 Office 365 음성 서비스에서 전화 시스템용 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="5fd70-160">이러한 접근 권한 값을 사용 하려면 Office 365 전역 관리자 역할인 계정으로 Office 365 테 넌 트에 로그인 하 고 원격 PowerShell을 실행할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="5fd70-161">원격 PowerShell 세션을 설정 하는 방법을 알아보려면 다음을 참조 하세요. [Windows PowerShell 용 컴퓨터 설정](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5fd70-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="5fd70-162">사용자에 게 정책을 할당 하 고 **id** 매개 변수 값으로 지정 하는 사용자의 비즈니스 음성 전화 번호를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="5fd70-163">사용자 id는 사용자의 SIP 주소, UPN (사용자 계정 이름) 또는 사용자의 Active Directory 표시 이름 (예: "Bob 최소라")을 사용 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="5fd70-164">별표 (\*) 문자는 사용자 Id로 표시 이름과 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="5fd70-165">예를 들어 Id "\*smith"는 표시 이름을 문자열 값 "smith"로 끝나는 모든 사용자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="5fd70-166">그런 다음 아래 스크립트를 사용 하 여 사용자를 추가 하 고 사용 하도록 설정 했는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="5fd70-167">사용자가 국제 전화를 할 수 있도록 할지 여부를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-167">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="5fd70-168">국제 통화는 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-168">By default, international calling is enabled.</span></span> <span data-ttu-id="5fd70-169">온라인 비즈니스용 Skype 관리 센터를 사용 하 여 국제 전화를 할 수 있는 사용자를 사용 하도록 설정 하거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-169">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="5fd70-170">사용자별로 국제 통화를 사용 하지 않도록 설정 하려면 비즈니스용 Skype Online PowerShell에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="5fd70-171">사용자 단위를 사용 하지 않도록 설정한 후 국가별 통화를 다시 사용 하도록 설정 하려면 동일한 cmdlet을 실행 하 되 **PolicyName** 의 값을 *InternationalCallsAllowed* 로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="5fd70-172">PSTN 사이트에 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="5fd70-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="5fd70-173">단일 사이트를 배포 하는 경우에도 테 넌 트 원격 PowerShell을 사용 하 여 사이트를 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="5fd70-174">원격 PowerShell 세션을 설정 하는 방법에 [대 한 자세한 내용은 Windows PowerShell 용 컴퓨터 설정을](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd70-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="5fd70-175">사용자에 게 할당 된 PSTN 사이트가 없는 경우 비즈니스용 Skype 클라우드 커넥터 에디션 배포와 Office 365 테 넌 트가 다시 테 넌 트 수준 기본 1 (피어 대상)을 사용 하 여 통화가 완료 될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="5fd70-176">온라인 하이브리드 중재 서버 설정 구성</span><span class="sxs-lookup"><span data-stu-id="5fd70-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="5fd70-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="5fd70-177"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="5fd70-178">P2P 통화가 PSTN 회의로 에스컬레이션 되는 경우 비즈니스용 Skype Online 회의 서버는 클라우드 커넥터 중재 서버로 초대를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="5fd70-179">Office 365에서이 초대를 라우팅할 수 있도록 하려면 다음과 같이 각 클라우드 커넥터 중재 서버에 대 한 온라인 테 넌 트의 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="5fd70-180">Office 365 관리 포털에서 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="5fd70-181">"MediationServer1"와 같은 원하는 사용자 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="5fd70-182">클라우드 커넥터 (.ini 파일의 첫 번째 SIP 도메인)의 기본 SIP 도메인을 사용자 도메인으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="5fd70-183">라이선스 할당은 비즈니스용 Skype online 디렉터리로의 사용자 전파에만 필요 하다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd70-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="5fd70-184">만든 계정에 Office 365 라이선스 (예: E5)를 할당 하 고 변경 내용을 전파 하는 데 최대 1 시간 동안 다음 cmdlet을 실행 하 여 비즈니스용 Skype online 디렉터리로 사용자 계정이 올바르게 프로 비전 되었는지 확인 하 고 다음을 제거 합니다. 이 계정에서 라이선스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="5fd70-185">전역 또는 사용자 관리자 자격 증명을 사용 하 여 테 넌 트 Azure AD 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행 하 여 1 단계에서 구성한 Azure AD 사용자 계정에 대 한 부서를 "HybridMediationServer"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="5fd70-186">비즈니스용 Skype 테 넌 트 관리자 자격 증명을 사용 하 여 테 넌 트 Skype for Business 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행 하 여 DisplayName \<\> SERVER 및 Edge 서버 FQDN을 해당 사용자 계정으로 설정 하 고,이 이름을 1 단계에서 만든 계정의 사용자 표시 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="5fd70-187">Id의 경우이 중재 서버에 대해 만든 Office 365 사용자 계정의 표시 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-187">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="5fd70-188">*Mediationserverfqdn* 의 경우 중재 서버에 대해 정의 된 내부 FQDN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="5fd70-189">*EdgeServerExternalFQDN* 의 경우 Edge 서버 액세스 프록시에 대해 정의 된 외부 FQDN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="5fd70-190">여러 클라우드 커넥터 PSTN 사이트가 있는 경우 중재 서버가 있는 사이트에 할당 된 Edge 서버 액세스 프록시 FQDN을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd70-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="5fd70-191">여러 클라우드 커넥터 중재 서버 (다중 사이트, HA)가 있는 경우에는 각각에 대해 이전 단계를 반복 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd70-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

