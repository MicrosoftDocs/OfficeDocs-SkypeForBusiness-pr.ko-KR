---
title: 클라우드 커넥터 배포 문제 해결
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 클라우드 커넥터 버전 배포 문제를 해결합니다.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359334"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="c15ca-103">클라우드 커넥터 배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c15ca-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="c15ca-104">Cloud Connector Edition은 2021년 7월 31일 비즈니스용 Skype Online과 함께 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="c15ca-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="c15ca-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="c15ca-106">클라우드 커넥터 버전 배포 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="c15ca-107">이 항목에서는 Cloud Connector Edition 배포의 일반적인 문제에 대한 해결법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="c15ca-108">PSTN(Public Switched Telephone Network)과의 통화에 문제가 있는 경우 이 항목에 설명된 솔루션에 따라 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="c15ca-109">클라우드 커넥터는 일부 문제를 자동으로 해결하기 위한 기본 제공 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="c15ca-110">자동 검색 프로세스는 Cloud Connector 어플라이언스에서 발생할 수 있는 문제를 검색하고 가능한 경우 관리자 개입 없이 이러한 문제를 해결하기 위한 수정 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="c15ca-111">검색 프로세스는 다음과 같이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="c15ca-112">**검색 시퀀스:** 클라우드 커넥터 관리 서비스는 어플라이언스가 다운되어 있는지 감지하기 위해 60초마다 프로세스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="c15ca-113">클라우드 커넥터 버전 2.0 이상에서 검색 프로세스는 비즈니스용 Skype Corpnet 스위치를 사용하여 클라우드 커넥터 컴퓨터로 PowerShell을 연결합니다. 2.0 이전 버전의 경우 검색 프로세스에서 클라우드 커넥터 관리 스위치를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c15ca-114">자동 복구가 성공하려면 호스트 네트워크 스위치를 통해 호스트와 가상 컴퓨터 간에 네트워크 연결이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="c15ca-115">네트워크 연결을 확인하여 자동 검색 및 복구가 성공할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="c15ca-116">**모니터링:** 다음 서비스는 클라우드 커넥터 버전 2.0 이상에서 모니터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="c15ca-117">가상 컴퓨터는 클라우드 커넥터 회사 또는 인터넷 가상 스위치에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="c15ca-118">가상 컴퓨터가 저장된 상태 또는 중지된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="c15ca-119">중앙 관리 서버 서비스: 복제본, MASTER</span><span class="sxs-lookup"><span data-stu-id="c15ca-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="c15ca-120">중재 서버 서비스: 복제본, RTCSRV 및 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="c15ca-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="c15ca-121">에지 서버 서비스: 복제본, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="c15ca-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="c15ca-122">에지 서버의 CS RTCSRV, 중재 서버의 CS RTCMEDSRV에 대해 인바운드 방화벽 규칙을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="c15ca-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="c15ca-123">클라우드 커넥터 버전 1.4.2에서는 다음 서비스만 모니터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="c15ca-124">중재 서버 서비스: RTCSRV 및 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="c15ca-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="c15ca-125">에지 서버 서비스: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="c15ca-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="c15ca-126">**복구 프로세스:** 모니터링된 서비스가 다운되면 어플라이언스가 다운된 것으로 표시되어 모든 문제를 해결할 수 있을 때까지 서비스가 중지되어 수동으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="c15ca-127">이렇게 하면 통화가 통화 실패를 일으킬 수 있는 어플라이언스로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="c15ca-128">클라우드 커넥터 관리 서비스가 다음과 같이 자동 복구를 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="c15ca-129">초기 다시 시도 간격은 10초마다 최대 간격 시간이 1시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="c15ca-130">처음 세 번의 복구 시도의 간격은 10초입니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="c15ca-131">네 번째 다시 시도부터 시작하여 간격 시간이 이전 간격 시간의 두 배로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="c15ca-132">예를 들어 네 번째 다시 시도는 20초, 5번째는 40초 등입니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="c15ca-133">1시간의 최대 간격에 도달하면 한 시간마다 한 번씩 다시 검색이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="c15ca-134">복구에 성공하면 간격과 다시 시도 횟수가 초기 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="c15ca-135">관리 서비스가 다시 시작되면 간격과 다시 시도 횟수가 초기 값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="c15ca-136">문제 해결</span><span class="sxs-lookup"><span data-stu-id="c15ca-136">Troubleshooting</span></span>

<span data-ttu-id="c15ca-137">다음은 일반적으로 발생하는 문제에 대한 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="c15ca-138">**문제: 배포 스크립트를 실행하면 배포가 실패하거나 응답하지 않습니다. 각 VM에 로그온한 후 관리/내부/외부 NIC에 대해 IP 주소가 누락되거나 잘못되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="c15ca-139">**해결 해결:** 이 문제는 자동으로 해결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="c15ca-140">NI는 실행되는 동안 VM에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="c15ca-141">hyper-v 관리자에서 이러한 VM을 종료하고 제거한 후 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="c15ca-142">**문제: Active Directory 서버 및 포리스트가 설치된 후 CMS 서버 및/또는 중재 서버가 도메인에 올바르게 가입되지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="c15ca-143">**해결 해결:** 이 문제를 해결하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="c15ca-144">Active Directory 서버에 로그온하고 도메인이 올바르게 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="c15ca-145">CMS/중재 서버에 로그온하고 Corpnet NIC에서 유효한 IP 주소가 할당되어 있으며 유효한 정적 IP 및 DNS가 AD 서버의 IP 주소로 구성되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="c15ca-146">CMS/중재 서버에 로그온하고 명령 프롬프트를 열어 립니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="c15ca-147">Active Directory 서버의 FQDN 및 IP 주소를 ping할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="c15ca-148">이 경우 IP 주소 충돌이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="c15ca-149">Active Directory에 대한 새 IP를 할당하고 그에 따라 CMS/중재 서버에서 DNS를 업데이트하십시오.</span><span class="sxs-lookup"><span data-stu-id="c15ca-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="c15ca-150">**문제: "Remove-VMSwitch : 가상 이더넷 스위치를 제거하는 동안 실패했습니다. '클라우드 커넥터 관리 스위치'는 가상 컴퓨터를 실행하거나 자식 풀에 할당하여 사용 중이기 때문에 삭제할 수 없습니다."**</span><span class="sxs-lookup"><span data-stu-id="c15ca-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="c15ca-151">**해결 해결:** 배포 후에 "클라우드 커넥터 관리 스위치"가 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="c15ca-152">이 오류가 발생하면 Hyper-v 관리자로 이동하여 여전히 연결된 가상 컴퓨터는 없는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c15ca-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="c15ca-153">가상 컴퓨터도 계속 연결되어 있는 경우 연결을 끊고 관리 스위치를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="c15ca-154">관리 스위치를 삭제할 수 없는 경우 호스트 서버를 다시 시작하고 다시 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="c15ca-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="c15ca-155">**문제: "Service RTCMRAUTH를 시작하지 못했습니다. 서비스가 사용하지 않도록 설정되지 않은지 확인**</span><span class="sxs-lookup"><span data-stu-id="c15ca-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c15ca-156">이 문제는 1.4.2 이전의 클라우드 커넥터 버전에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="c15ca-157">이 프런트 엔드 서버가 이전에 장애 조치(fail over)했기 때문에 시작할 수 없습니다(컴퓨터 장애 조치 사용).</span><span class="sxs-lookup"><span data-stu-id="c15ca-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="c15ca-158">이 경우 장애 조치(fail back)를 호출합니다(컴퓨터 장애 조치(fail back) 사용).</span><span class="sxs-lookup"><span data-stu-id="c15ca-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="c15ca-159">**해결 해결:** 이 문제는 에지 서버에서 루트 CA 인증서 또는 중간 CA 인증서를 신뢰할 수 없는 경우 에지 서버에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="c15ca-160">외부 인증서를 가져올 수 있지만 인증서 체인이 손상된 경우에도</span><span class="sxs-lookup"><span data-stu-id="c15ca-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="c15ca-161">이 조건에서는 RTCMRAUTH 및/또는 RTCSRV 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="c15ca-162">외부 인증서의 루트 CA 인증서와 모든 중간 CA 인증서를 에지 서버로 수동으로 가져온 다음 에지 서버를 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="c15ca-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="c15ca-163">에지 서버에서 RTCMRAUTH 및 RTCSRV 서비스가 시작된 것을 확인한 후 호스트 서버로 돌아가 관리자 권한으로 PowerShell 콘솔을 시작한 다음 다음 cmdlet을 실행하여 새 배포로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="c15ca-164">**문제: Windows 업데이트가 적용될 때 호스트 서버가 다시 시작되고 서버에서 서비스하는 통화가 실패합니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="c15ca-165">**해결 해결:** 고가용성 환경을 배포한 경우 Microsoft는 Windows 업데이트를 수동으로 확인하고 설치할 때 하나의 호스트 컴퓨터(배포 인스턴스)를 현재 토폴로지로 또는 현재 토폴로지로 이동하는 데 도움이 되는 cmdlet을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="c15ca-166">이 작업을 수행하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="c15ca-167">호스트 서버에서 관리자 권한으로 PowerShell 콘솔을 시작한 후 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="c15ca-168">업데이트를 확인하고 사용 가능한 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="c15ca-169">PowerShell 콘솔에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="c15ca-170">**문제: PSTN 번호를 사용하여 비즈니스용 Skype 클라이언트에서 전화를 걸면 다른 PSTN 번호를 요청하여 전화가 전화 회의로 에스컬레이터될 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="c15ca-171">**해결 해결:** 이 문제를 해결하려면 온라인 하이브리드 중재 서버 설정 [구성을 참조하세요.](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)</span><span class="sxs-lookup"><span data-stu-id="c15ca-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="c15ca-172">**문제: Active Directory 서버를 설치할 때 Windows 업데이트에 대한 경고 메시지가 표시됩니다. "Windows 자동 업데이트를 사용할 수 없습니다. 새로 설치한 역할 또는 기능이 자동으로 업데이트되도록 Windows 업데이트를 켜야 합니다."**</span><span class="sxs-lookup"><span data-stu-id="c15ca-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="c15ca-173">**해결 해결:** 비즈니스용 Skype 테넌트 관리자 자격 증명을 사용하여 테넌트 원격 PowerShell 세션을 시작한 다음 다음 cmdlet을 실행하여 _사이트의 EnableAutoUpdate_ 구성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="c15ca-174">_EnableAutoUpdate가_ **True로** 설정된 경우 CCEManagement 서비스가 가상 컴퓨터와 호스트 서버에 대한 Windows 업데이트 다운로드 및 설치를 모두 처리하기 때문에 이 경고 메시지를 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="c15ca-175">_EnableAutoUpdate가_ **False로** 설정된 경우 다음 cmdlet을 실행하여 **True로 설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="c15ca-176">또는 업데이트를 수동으로 확인하고 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="c15ca-177">다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c15ca-177">See the next section.</span></span>
    
- <span data-ttu-id="c15ca-178">**문제: 오류 메시지가 표시됩니다. 현재 입력/구성 또는 기존 어플라이언스와 충돌하거나 충돌하여 어플라이언스를 등록할 \<SiteName\> \<ApplianceName\> 수 \<Mediation Server FQDN\> \<Mediation Server IP Address\> 없습니다. 충돌하는 어플라이언스를 제거하거나 입력/구성 정보를 업데이트한 다음 다시 등록합니다. ' when run Register-CcAppliance to register current appliance to online.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="c15ca-179">**해결 해결:** 에 대한 \<ApplianceName\> 값은 \<Mediation Server FQDN\> 고유해야 하며 하나의 어플라이언스 등록에만 \<Mediation Server IP Address\> 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="c15ca-180">기본적으로 호스트 \<ApplianceName\> 이름에서 온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="c15ca-181">\<Mediation Server FQDN\> 및 \<Mediation Server IP Address\> 구성 ini 파일에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="c15ca-182">예를 들어 (ApplianceName= MyserverNew, 중재 서버 FQDN=ms.contoso.com, SiteName=MySite에 등록할 중재 서버 IP 주소=10.10.10.10이지만 등록된 어플라이언스(ApplianceName= Myserver, 중재 서버 FQDN=ms.contoso.com, 중재 서버 IP 주소=10.10.10.10)가 있는 경우 충돌이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="c15ca-183">먼저 ApplianceRoot 디렉터리 섹션에서 CloudConnector.ini 파일을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="c15ca-184">파일에서 \<SiteName\> 값을 \<Mediation Server FQDN\> \<Mediation Server IP Address\> 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="c15ca-185">\<ApplianceName\> 는 호스트 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="c15ca-186">둘째, 비즈니스용 Skype 테넌트 관리자 자격 증명을 사용하여 테넌트 원격 PowerShell을 시작한 다음 다음 cmdlet을 실행하여 등록된 어플라이언스를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="c15ca-187">충돌을 식별한 후 등록된 어플라이언스와 일치하는 정보로 CloudConnector.ini 파일을 업데이트하거나 기존 어플라이언스 등록을 등록을 해소하여 충돌을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="c15ca-188">**문제: Get-CcRunningVersion 배포된 어플라이언스가 호스트에서 실행되는 경우 이 cmdlet은 빈 값을 반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="c15ca-189">**해결 해결:** 이 경우 1.3.4 또는 1.3.8에서 1.4.1로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="c15ca-190">.msi와 함께 버전 1.4.1을 설치한 후 다른 cmdlet을 실행하기 전에 `Register-CcAppliance` 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="c15ca-191">`Register-CcAppliance` 는 %UserProfile%\CloudConnector에서 %ProgramData%\CloudConnector로 module.ini 파일을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="c15ca-192">이 폴더를 놓친 경우 %ProgramData%\CloudConnector module.ini 새 데이터베이스가 만들어지며 1.3.4 또는 1.3.8에 대한 실행 중인/백업 버전 정보를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="c15ca-193">%UserProfile%\CloudConnector 및 %ProgramData%\CloudConnector 폴더의 module.ini 파일을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="c15ca-194">차이점이 있는 경우 %ProgramData%\CloudConnector에서 module.ini 파일을 삭제하고 다시  `Register-CcAppliance` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="c15ca-195">또한 파일을 올바른 실행 및 백업 버전으로 수동으로 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="c15ca-196">**문제: Switch-CcVersion cmdlet을 실행하여 현재 스크립트 버전과 다른 이전 버전으로 전환한 후 이 이전 버전에 대한 고가용성 지원이 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="c15ca-197">**해결 해결:** 예를 들어 1.4.1에서 1.4.2로 업그레이드한 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="c15ca-198">실행하여 결정될 수 있는 현재 스크립트 버전과 실행하여 결정될 수 있는 실행 중인 버전은 둘 다 `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2입니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="c15ca-199">현재 실행 중인 버전을 다시 1.4.1로 전환하기 위해 실행하면 이 이전 버전에 대한 고가용성 `Switch-CcVersion` 지원이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="c15ca-200">전체 고가용성 지원을 얻습니다. 다시 1.4.2로 전환하여 실행 중인 버전과 스크립트 버전이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="c15ca-201">1.4.2 배포에 문제가 있는 경우 최대한 빨리 제거하고 다시 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="c15ca-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="c15ca-202">**문제: 중앙 관리 저장소, 중재 서버 및 에지 서버에 발급된 인증 기관 인증서 또는 내부 인증서가 거의 만료되거나 손상된 경우**</span><span class="sxs-lookup"><span data-stu-id="c15ca-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="c15ca-203">**해결 해결:** 비즈니스용 Skype 인증 기관 인증서는 5년 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="c15ca-204">중앙 관리 저장소, 중재 서버 및 에지 서버에 발급된 내부 인증서는 2년 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c15ca-205">클라우드 커넥터 버전 2.0 이상에서는 Renew-CcServerCertificate cmdlet이 Update-CcServerCertificate 변경되어 Renew-CcCACertificate cmdlet이 Update-CcCACertificate로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="c15ca-206">중앙 관리 저장소, 중재 서버 및 에지 서버에 발급된 내부 인증서가 만료되거나 손상된 경우 Renew-CcServerCertificate 또는 Update-CcServerCertificate cmdlet을 실행하여 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="c15ca-207">인증 기관 인증서가 만료 날짜가 다가오면 인증서를 Renew-CcCACertificate 또는 Update-CcCACertificate cmdlet을 실행하여 인증서를 갱신합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="c15ca-208">**인증 기관 인증서가** 손상되어 사이트에 어플라이언스가 하나만 있는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="c15ca-209">서비스 Enter-CcUpdate cmdlet을 실행하여 서비스를 드레인하고 어플라이언스를 유지 관리 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="c15ca-210">다음 cmdlet을 실행하여 새 인증 기관 인증서 및 모든 내부 서버 인증서를 다시 설정하고 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="c15ca-211">클라우드 커넥터가 2.0 이전으로 릴리스된 경우:</span><span class="sxs-lookup"><span data-stu-id="c15ca-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="c15ca-212">또는 클라우드 커넥터 릴리스 2.0 이상:</span><span class="sxs-lookup"><span data-stu-id="c15ca-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="c15ca-213">게이트웨이와 중재 서버 간에 TLS를 사용하는 경우 어플라이언스에서 Export-CcRootCertificate cmdlet을 실행한 다음 내보낼 인증서를 PSTN 게이트웨이에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="c15ca-214">게이트웨이에서 인증서를 다시 발급해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="c15ca-215">Exit-CcUpdate cmdlet을 실행하여 서비스를 시작하고 유지 관리 모드를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="c15ca-216">**인증 기관** 인증서가 손상되어 사이트에 여러 어플라이언스가 있는 경우 사이트의 각 어플라이언스에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="c15ca-217">사용량이 많은 시간 동안 이러한 단계를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="c15ca-218">첫 번째 어플라이언스에서 Remove-CcCertificationAuthorityFile cmdlet을 실행하여 디렉터리에서 CA 백업 파일을 \<SiteRoot\> 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="c15ca-219">서비스 Enter-CcUpdate cmdlet을 실행하여 서비스를 드레인하고 각 어플라이언스를 유지 관리 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="c15ca-220">첫 번째 어플라이언스에서 다음 cmdlet을 실행하여 새 인증 기관 인증서와 모든 내부 서버 인증서를 다시 설정하고 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="c15ca-221">클라우드 커넥터가 2.0 이전으로 릴리스된 경우:</span><span class="sxs-lookup"><span data-stu-id="c15ca-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="c15ca-222">또는 클라우드 커넥터 릴리스 2.0 이상:</span><span class="sxs-lookup"><span data-stu-id="c15ca-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="c15ca-223">첫 번째 어플라이언스에서 다음 cmdlet을 실행하여 CA 파일을 폴더에 \<SiteRoot\> 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="c15ca-224">동일한 사이트의 다른 모든 어플라이언스에서 다음 명령을 실행하여 CA 백업 파일을 사용하며, 그러면 어플라이언스가 모두 동일한 루트 인증서를 사용할 수 있도록 한 다음 새 인증서를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="c15ca-225">게이트웨이와 중재 서버 간에 TLS를 사용하는 경우 사이트의 모든 어플라이언스에서 Export-CcRootCertificate cmdlet을 실행한 다음 내보낼 인증서를 PSTN 게이트웨이에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="c15ca-226">게이트웨이에서 인증서를 다시 발급해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="c15ca-227">Exit-CcUpdate cmdlet을 실행하여 서비스를 시작하고 유지 관리 모드를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="c15ca-228">**문제: Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log"에 다음 오류 메시지가 표시됩니다. CceService 오류: 0: 온라인에 상태를 보고할 때 예기치 않은 예외: System.Management.Automation.CmdletInvocationException: 사용자에 대해 로그온에 \<Global Tenant Admin\> 실패했습니다. 올바른 사용자 이름과 암호를 사용한 새 자격 증명 개체를 만들어야 합니다. ---\>**</span><span class="sxs-lookup"><span data-stu-id="c15ca-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="c15ca-229">**해결 해결:** 클라우드 커넥터 어플라이언스가 등록된 이후 Microsoft 365 또는 Office 365 전역 테넌트 관리자 자격 증명이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="c15ca-230">클라우드 커넥터 어플라이언스에서 로컬에 저장된 자격 증명을 업데이트하기 위해 호스트 어플라이언스의 관리자 PowerShell에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="c15ca-231">**문제: 배포에 사용한 호스트 서버 계정의 암호를 변경한 후 %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log에서 또는 Get-CcCredential cmdlet을 실행하는 동안 "ConvertTo-SecureString : 키가 지정된 상태로 사용할 수 없습니다." 오류 메시지가 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="c15ca-232">**해결 해결:** 모든 클라우드 커넥터 자격 증명은 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="c15ca-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="c15ca-233">호스트 서버의 암호가 변경되는 경우 로컬에 저장된 자격 증명을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="c15ca-234">**Cloud Connector 버전 1.4.2를** 실행하는 경우 다음 단계를 수행하여 모든 클라우드 커넥터 암호를 다시 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="c15ca-235">호스트 서버를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="c15ca-236">다음 파일을 삭제합니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="c15ca-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="c15ca-237">관리자 권한으로 PowerShell 콘솔을 시작한 다음 "Register-CcAppliance -Local"을 실행하여 설명에 따라 암호를 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="c15ca-238">클라우드 커넥터 배포 전에 입력한 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="c15ca-239">Cloud Connector 버전 **2.0** 이상을 실행하는 경우 다음 단계를 수행하여 모든 클라우드 커넥터 암호를 다시 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="c15ca-240">호스트 서버를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="c15ca-241">다음 파일을 삭제합니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" .</span><span class="sxs-lookup"><span data-stu-id="c15ca-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="c15ca-242">관리자 권한으로 PowerShell 콘솔을 시작한 다음 "Register-CcAppliance -Local"을 실행하여 설명에 따라 암호를 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="c15ca-243">캐시된 암호 파일이 클라우드 커넥터 버전 1.4.2를 사용하여 생성된 경우 메시지가 표시될 때 CceService 암호에 VMAdmin 암호를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c15ca-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="c15ca-244">다른 모든 계정에 대해 클라우드 커넥터 배포를 위해 앞에서 입력한 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="c15ca-245">캐시된 암호 파일이 클라우드 커넥터 버전 1.4.2를 사용하여 생성되어 DomainAdmin 및 VMAdmin 암호가 다른 경우 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="c15ca-246">다음과 Set-CcCredential -AccountType DomainAdmin을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="c15ca-247">이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="c15ca-248">새 계정 자격 증명을 입력하라는 메시지가 표시될 때 전에 사용한 DomainAdmin 암호의 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="c15ca-249">캐시된 암호 파일이 클라우드 커넥터 버전 2.0 이상에서 생성된 경우 기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="c15ca-250">DomainAdmin 및 VMAdmin 암호를 변경한 경우 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="c15ca-251">다음과 Set-CcCredential -AccountType DomainAdmin을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="c15ca-252">이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="c15ca-253">새 계정 자격 증명을 입력하라는 메시지가 표시될 때 전에 사용한 DomainAdmin 암호의 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="c15ca-254">다음과 Set-CcCredential -AccountType VmAdmin을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="c15ca-255">이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="c15ca-256">새 계정 자격 증명을 입력하라는 메시지가 표시될 때 전에 사용한 VmAdmin 암호의 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="c15ca-257">**문제: 클라우드 커넥터 버전 2.1 이상에서 어플라이언스에서 Register-CcAppliance 또는 기타 cmdlet을 실행하면 "for Each-Object : The property 'Common' cannot be found on this object. 속성이 있는지 확인 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span><span class="sxs-lookup"><span data-stu-id="c15ca-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="c15ca-258">**해결 해결:** 클라우드 커넥터 2.1 이상에는 .NET Framework 4.6.1 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="c15ca-259">어플라이언스에서 .NET Framework를 버전 4.6.1 이상으로 업데이트하고 cmdlet을 다시 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="c15ca-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="c15ca-260">**문제: Cloud Connector Edition 2.1을 실행하면 Install-CcAppliance를 실행하면 "오류로 새 인스턴스를 설치하지 못했습니다. 문자열만 XmlNode 속성을 설정하는 값으로 사용할 수 있기 때문에 "State"를 설정할 수 없습니다." 등의 오류 메시지가 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="c15ca-261">**해결 해결:** In Cloudconnector.ini, under the [Common] section, please add the "State" config as below: CountryCode=US State=WA City=Redmond</span><span class="sxs-lookup"><span data-stu-id="c15ca-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="c15ca-262">"상태" 줄의 값이 반드시 있는 것은 아니지만 "상태" 줄은 Cloudconnector.ini 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="c15ca-263">**문제: "Dismount-WindowsImage : Dismount-WindowsImage 실패했습니다. 오류 코드 = 0xc1550115"를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="c15ca-264">**해결 해결:** 관리자 권한으로 PowerShell 콘솔을 시작하고 "DISM -Cleanup-Wim'"을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="c15ca-265">그러면 문제가 있는 모든 이미지가 정리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-265">This will clean up all troubled images.</span></span> <span data-ttu-id="c15ca-266">다시 Install-CcAppliance 실행하거나 비트가 자동으로 업그레이드될 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="c15ca-267">**문제: HA 환경에서 첫 번째 클라우드 커넥터 어플라이언스 배포 실패**</span><span class="sxs-lookup"><span data-stu-id="c15ca-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="c15ca-268">**해결 해결:** 배포에 실패한 이유에 따라 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="c15ca-269">첫 번째 Cloud Connector 어플라이언스가 실패하고 실패 이유를 확인할 수 없는 경우 배포가 성공할 때까지 어플라이언스를 다시 설치한 다음 다른 어플라이언스를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="c15ca-270">첫 번째 Cloud Connector 어플라이언스가 외부 인증서 문제와 같은 사소한 문제로 실패하면 어플라이언스를 다시 설치하지 않고도 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="c15ca-271">그런 다음 테넌트 원격 PowerShell을 사용하여 배포를 다음과 같이 성공적으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="c15ca-272">첫 번째 배포가 성공한 경우 다음 단계를 사용할 수도 있지만, 어떤 이유로 클라우드 커넥터가 배포를 성공으로 보고하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="c15ca-273">첫 번째 Cloud Connector 어플라이언스의 ID(GUID)를 얻습니다. Get-CsHybridPSTNAppliance 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="c15ca-274">어플라이언스를 성공적으로 배포된 것으로 표시하기 위해 다음과 Set-CsCceApplianceDeploymentStatus 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="c15ca-275">**문제: 호스트 서버 또는 가상 컴퓨터에 Windows 업데이트를 수동으로 확인하고 설치해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="c15ca-276">**해결 해결:** 비즈니스용 Skype 클라우드 커넥터 버전에서 제공하는 자동화된 OS 업데이트를 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="c15ca-277">어플라이언스가 온라인 관리에 등록되고 자동 OS 업데이트를 사용하도록 설정하면 호스트 서버 및 가상 컴퓨터는 OS 업데이트 시간 창 설정에 따라 자동으로 Windows 업데이트를 확인하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="c15ca-278">Windows 업데이트를 수동으로 확인하고 설치해야 하는 경우 배포 유형에 적용되는 이 섹션의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c15ca-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="c15ca-279">업데이트에 필요한 정전 시간을 최소화하기 위해 호스트 서버와 호스트 서버에서 실행되는 가상 컴퓨터를 동시에 업데이트할 계획을 세우는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="c15ca-280">원하는 경우 WSUS(Windows Server Update Services) 서버를 사용하여 클라우드 커넥터 서버에 대한 업데이트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="c15ca-281">Windows 업데이트를 자동으로 설치하지 못하도록 **구성해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="c15ca-282">클라우드 커넥터 배포를 수동으로 업데이트하는 방법에 대한 자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c15ca-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="c15ca-283">**문제: 클라우드 커넥터가 새 빌드로 업데이트될 때 클라우드 커넥터 cmdlet이 업데이트되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="c15ca-284">자동 업데이트가 발생할 때 PowerShell 창이 열린 경우에 이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="c15ca-285">**해결 해결:** 업데이트된 cmdlet을 로드하기 위해 다음 단계 중 하나를 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="c15ca-286">Cloud Connector 어플라이언스에서 PowerShell을 닫은 다음 PowerShell을 다시 연 다음.</span><span class="sxs-lookup"><span data-stu-id="c15ca-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="c15ca-287">또는 CloudConnector -Force를 Import-Module 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="c15ca-288">**문제: "'Stop-CsWindowsService'라는 용어가 cmdlet, 함수, 스크립트 파일 또는 작동 프로그램 이름으로 인식되지 않습니다." cmdlet을 실행하려고 할 때 Enter-CcUpdate 오류가 발생합니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="c15ca-289">**해결 해결:** $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="c15ca-290">PowerShell에서는 매월 모든 모듈을 다시 분석할 수 있도록 이 파일을 찾는 모듈의 cmdlet 캐시로 만듭니다. 이렇게 하면 속도가 매우 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="c15ca-291">대부분의 경우 해당 캐시에서 다시 읽을 때 PowerShell에 잘못된 결과를 제공하는 일부 파일이 손상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="c15ca-292">**문제: "Import-Module CloudConnector"에서 "Import-Module: 지정된 모듈 "CloudConnector"가 로드되지 않았습니다. 모든 모듈 디렉터리에서 유효한 모듈 파일을 찾을 수 없습니다."**</span><span class="sxs-lookup"><span data-stu-id="c15ca-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="c15ca-293">**해결 방법:**</span><span class="sxs-lookup"><span data-stu-id="c15ca-293">**Resolution:**</span></span>
    - <span data-ttu-id="c15ca-294">c:\Program Files\WindowsPowerShell\Modules 아래에 CloudConnector 모듈이 존재하는지 확인</span><span class="sxs-lookup"><span data-stu-id="c15ca-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="c15ca-295">CloudConnector 모듈이 이 위치에 존재하는지 확인한 후 모듈 위치에 대한 경로를 저장하는 PSModulePath 환경 변수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="c15ca-296">a.</span><span class="sxs-lookup"><span data-stu-id="c15ca-296">a.</span></span> <span data-ttu-id="c15ca-297">임시 변경: 관리자 권한으로 Powershell을 시작하고 $env:PSModulePath = $env:PSModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="c15ca-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="c15ca-298">b.</span><span class="sxs-lookup"><span data-stu-id="c15ca-298">b.</span></span> <span data-ttu-id="c15ca-299">영구 변경의 경우 관리자 권한으로 PowerShell을 시작하고 다음 명령을 하나씩 실행합니다. $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span><span class="sxs-lookup"><span data-stu-id="c15ca-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="c15ca-300">수동으로 Windows 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="c15ca-300">Install Windows updates manually</span></span>

<span data-ttu-id="c15ca-301">환경에서 자동 업데이트를 사용하지 않을 경우 다음 단계에 따라 Windows 업데이트를 수동으로 확인하고 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="c15ca-302">Windows 업데이트를 확인하고 설치하려면 서버를 다시 시작해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="c15ca-303">호스트 서버가 다시 시작되는 경우 사용자는 클라우드 커넥터를 사용하여 통화를 걸거나 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="c15ca-304">업데이트를 수동으로 확인하고 설치하여 업데이트가 수행될 때를 제어한 다음 서비스 중단을 방지하기 위해 선택한 시간 동안 필요한 경우 컴퓨터를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="c15ca-305">업데이트를 수동으로 확인하려면 각 호스트 서버에 연결하고 **제어판을 니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="c15ca-306">시스템 **및 보안 Windows \> 업데이트를** 선택한 다음 사용자 환경에 따라 업데이트 및 서버 다시 시작을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="c15ca-307">사이트에 어플라이언스가 하나뿐인 경우 각 가상 컴퓨터에 연결하고 **제어판을 니다.**</span><span class="sxs-lookup"><span data-stu-id="c15ca-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="c15ca-308">시스템 **및 보안 Windows \> 업데이트를** 선택한 다음 업데이트 및 서버 다시 시작을 적절하게 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="c15ca-309">사이트에 어플라이언스가 두 개 이상 있는 경우 업데이트 및 다시 시작되는 인스턴스는 업데이트하는 동안 사용자가 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="c15ca-310">사용자는 모든 가상 컴퓨터와 모든 비즈니스용 Skype 서비스가 업데이트가 완료된 후 가상 컴퓨터에 시작될 때까지 배포의 다른 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="c15ca-311">서비스 중단을 방지하기 위해 업데이트를 적용하는 동안 HA에서 인스턴스를 제거한 다음 완료되면 복원하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="c15ca-312">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-312">To do so:</span></span>
    
1. <span data-ttu-id="c15ca-313">각 호스트 서버에서 관리자 권한으로 PowerShell 콘솔을 여는 경우</span><span class="sxs-lookup"><span data-stu-id="c15ca-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="c15ca-314">다음 cmdlet을 사용하여 HA에서 인스턴스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="c15ca-315">단일 인스턴스에 대한 단계에 따라 업데이트를 수동으로 적용하고 가상 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="c15ca-316">다음 cmdlet을 통해 인스턴스를 다시 HA로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="c15ca-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="c15ca-317">다중 사이트 배포의 경우 배포의 각 사이트에 대해 한 단계씩 수행하여 한 사이트에 업데이트를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="c15ca-318">클라우드 커넥터 호스트 컴퓨터에 바이러스 백신 소프트웨어를 설치할 때의 팁</span><span class="sxs-lookup"><span data-stu-id="c15ca-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="c15ca-319">클라우드 커넥터 호스트 컴퓨터에 바이러스 백신 소프트웨어를 설치해야 하는 경우 다음 제외를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="c15ca-320">각 컴퓨터의 로컬 어플라이언스 디렉터리</span><span class="sxs-lookup"><span data-stu-id="c15ca-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="c15ca-321">각 컴퓨터의 원격 사이트 디렉터리</span><span class="sxs-lookup"><span data-stu-id="c15ca-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="c15ca-322">컴퓨터의 로컬 사이트 디렉터리는 공유 사이트 루트 폴더를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c15ca-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="c15ca-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="c15ca-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="c15ca-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="c15ca-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="c15ca-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="c15ca-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="c15ca-326">프로세스가 Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="c15ca-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
