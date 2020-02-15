---
title: 'Lync Server 2013: 주소록 관리용 Get-help 서비스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d41d0d3fe8960f286cfe9bed1f27ae08d43c9fe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="e9267-102">Lync Server 2013의 주소록 관리를 위한 get-help 서비스</span><span class="sxs-lookup"><span data-stu-id="e9267-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9267-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e9267-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e9267-p101">이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalUserAdmins 및 RTCUniversalServerAdmins 그룹의 구성원은 Get-CsService cmdlet을 로컬로 실행할 수 있습니다. 사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 가져오려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e9267-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="e9267-106">Get-CsService는 인프라의 정의 된 웹 서비스에 대 한 현재 구성을 검색 하 고 표시 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9267-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="e9267-107">이 cmdlet은 풀의 FQDN(정규화된 도메인 이름) 및 WebServer 매개 변수를 정의하여 서버에서 제공하는 웹 기반 서비스(주소록 처리기 및 메일 그룹 확장 URK 포함)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e9267-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="e9267-108">예:</span><span class="sxs-lookup"><span data-stu-id="e9267-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="e9267-109">이 cmdlet이 반환하는 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e9267-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="e9267-110">Identity: WebServer.</span><span class="sxs-lookup"><span data-stu-id="e9267-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="e9267-111">초당 작업 저장소: 저장소 1, dc01. contoso.</span><span class="sxs-lookup"><span data-stu-id="e9267-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="e9267-112">UserServer: UserServer:pool01. contoso.</span><span class="sxs-lookup"><span data-stu-id="e9267-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="e9267-113">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="e9267-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="e9267-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="e9267-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="e9267-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="e9267-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="e9267-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="e9267-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="e9267-117">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="e9267-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="e9267-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="e9267-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="e9267-119">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="e9267-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="e9267-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="e9267-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="e9267-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="e9267-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="e9267-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="e9267-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="e9267-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="e9267-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="e9267-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="e9267-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="e9267-125">LIServiceInternalUri:https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="e9267-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="e9267-126">ABHandlerInternalUri:https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="e9267-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="e9267-127">ABHandlerExternalUri:https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="e9267-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="e9267-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="e9267-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="e9267-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="e9267-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="e9267-130">CAHandlerInternalUri:https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="e9267-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="e9267-131">CAHandlerInternalAnonUri:http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="e9267-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="e9267-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="e9267-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="e9267-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="e9267-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="e9267-134">CAHandlerExternalUri:https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="e9267-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="e9267-135">DeviceUpdateDownloadInternalUri:https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="e9267-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="e9267-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="e9267-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="e9267-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="e9267-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="e9267-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="e9267-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="e9267-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="e9267-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="e9267-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="e9267-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="e9267-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="e9267-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="e9267-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="e9267-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="e9267-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="e9267-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="e9267-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="e9267-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="e9267-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="e9267-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="e9267-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="e9267-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="e9267-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="e9267-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="e9267-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9267-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="e9267-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e9267-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="e9267-150">DependentServiceList: {등록자:pool01. ConferencingServer:pool01. contoso.</span><span class="sxs-lookup"><span data-stu-id="e9267-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="e9267-151">ServiceId: 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="e9267-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="e9267-152">SiteId: Site: Redmond</span><span class="sxs-lookup"><span data-stu-id="e9267-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="e9267-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e9267-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="e9267-154">버전: 5</span><span class="sxs-lookup"><span data-stu-id="e9267-154">Version : 5</span></span>

<span data-ttu-id="e9267-155">역할: WebServer</span><span class="sxs-lookup"><span data-stu-id="e9267-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e9267-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9267-156">See Also</span></span>


[<span data-ttu-id="e9267-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="e9267-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

