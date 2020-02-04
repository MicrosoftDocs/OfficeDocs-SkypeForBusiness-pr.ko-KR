---
title: 'Lync Server 2013: 주소록 관리용 가져오기-CsService'
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
ms.openlocfilehash: 656c1aa545a1f10e49c5ff60b51c20386854d146
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="8cb4d-102">Lync Server 2013의 주소록 관리를 위한 Get CsService</span><span class="sxs-lookup"><span data-stu-id="8cb4d-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cb4d-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8cb4d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8cb4d-104">이 cmdlet을 실행할 수 있는 사용자: 기본적으로 다음 그룹의 구성원은 Get-CsService cmdlet을 로컬로 실행할 권한이 있습니다 (RTCUniversalUserAdmins, RTCUniversalServerAdmins).</span><span class="sxs-lookup"><span data-stu-id="8cb4d-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="8cb4d-105">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb4d-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="8cb4d-106">Get-CsService는 인프라의 정의 된 웹 서비스에 대 한 현재 구성을 검색 하 고 표시 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb4d-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="8cb4d-107">풀의 FQDN (정규화 된 도메인 이름) 및 매개 변수 WebServer을 정의 하면 cmdlet은 주소록 처리기 및 메일 그룹 확장 Uri를 포함 하 여 서버에서 제공 하는 웹 기반 서비스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb4d-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="8cb4d-108">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb4d-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="8cb4d-109">이 cmdlet은 다음을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb4d-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="8cb4d-110">Id: WebServer "pool01.</span><span class="sxs-lookup"><span data-stu-id="8cb4d-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="8cb4d-111">작업 저장소: 네트워크 저장소:dc01. e 1.</span><span class="sxs-lookup"><span data-stu-id="8cb4d-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="8cb4d-112">UserServer: UserServer:pool01 net.tcp. e 1.</span><span class="sxs-lookup"><span data-stu-id="8cb4d-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="8cb4d-113">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="8cb4d-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="8cb4d-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="8cb4d-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="8cb4d-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="8cb4d-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="8cb4d-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="8cb4d-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="8cb4d-117">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="8cb4d-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="8cb4d-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="8cb4d-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="8cb4d-119">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="8cb4d-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="8cb4d-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="8cb4d-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="8cb4d-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="8cb4d-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="8cb4d-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="8cb4d-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="8cb4d-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="8cb4d-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="8cb4d-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="8cb4d-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="8cb4d-125">LIServiceInternalUri:https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="8cb4d-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="8cb4d-126">ABHandlerInternalUri:https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="8cb4d-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="8cb4d-127">ABHandlerExternalUri:https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="8cb4d-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="8cb4d-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="8cb4d-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="8cb4d-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="8cb4d-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="8cb4d-130">CAHandlerInternalUri:https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="8cb4d-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="8cb4d-131">CAHandlerInternalAnonUri:http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="8cb4d-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="8cb4d-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="8cb4d-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="8cb4d-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="8cb4d-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="8cb4d-134">CAHandlerExternalUri:https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="8cb4d-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="8cb4d-135">DeviceUpdateDownloadInternalUri:https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="8cb4d-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="8cb4d-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="8cb4d-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="8cb4d-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="8cb4d-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="8cb4d-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="8cb4d-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="8cb4d-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="8cb4d-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="8cb4d-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="8cb4d-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="8cb4d-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="8cb4d-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="8cb4d-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="8cb4d-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="8cb4d-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="8cb4d-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="8cb4d-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="8cb4d-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="8cb4d-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="8cb4d-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="8cb4d-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="8cb4d-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="8cb4d-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="8cb4d-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="8cb4d-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8cb4d-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="8cb4d-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8cb4d-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="8cb4d-150">DependentServiceList: {등록자 1], pool01. ConferencingServer:pool01. e t e}</span><span class="sxs-lookup"><span data-stu-id="8cb4d-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="8cb4d-151">ServiceId: 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="8cb4d-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="8cb4d-152">SiteId: 사이트: Redmond</span><span class="sxs-lookup"><span data-stu-id="8cb4d-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="8cb4d-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8cb4d-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="8cb4d-154">버전: 5</span><span class="sxs-lookup"><span data-stu-id="8cb4d-154">Version : 5</span></span>

<span data-ttu-id="8cb4d-155">역할: WebServer</span><span class="sxs-lookup"><span data-stu-id="8cb4d-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8cb4d-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cb4d-156">See Also</span></span>


[<span data-ttu-id="8cb4d-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="8cb4d-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

