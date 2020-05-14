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
description: Cloud Connector Edition 배포 문제를 해결 합니다.
ms.openlocfilehash: 97ece0ee1bcc11c22fd55709d025169ed95b16ff
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220228"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="e75ce-103">클라우드 커넥터 배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e75ce-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="e75ce-104">Cloud Connector Edition 배포 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="e75ce-105">이 항목에서는 Cloud Connector Edition 배포와 관련 된 일반적인 문제에 대 한 해결 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-105">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="e75ce-106">공중 전화망 (PSTN)과의 통화에 문제가 발생 하는 경우이 항목에서 설명 하는 솔루션을 따라 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-106">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="e75ce-107">클라우드 커넥터는 일부 문제를 자동으로 해결 하기 위한 기본 제공 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="e75ce-108">자동 검색 프로세스는 클라우드 커넥터 기기와 관련 된 잠재적 문제를 찾은 다음, 가능한 경우 관리자의 개입 없이 해당 문제를 해결 하기 위해 정정 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="e75ce-109">검색 프로세스는 다음과 같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="e75ce-110">**검색 시퀀스:** 클라우드 커넥터 관리 서비스는 기기가 다운 되었는지 여부를 검색 하기 위해 60 초 마다 프로세스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="e75ce-111">클라우드 커넥터 버전 2.0 이상에서 검색 프로세스는 클라우드 커넥터 컴퓨터에 PowerShell 연결을 설정 하는 데 비즈니스용 Skype Corpnet 스위치를 사용 합니다. 이전 버전 2.0의 경우 검색 프로세스에서 클라우드 커넥터 관리 스위치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e75ce-112">자동 복구가 성공 하려면 호스트 네트워크 스위치를 통해 호스트와 가상 컴퓨터 간에 네트워크 연결이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="e75ce-113">네트워크 연결을 확인 하 여 자동 검색 및 복구가 성공할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="e75ce-114">**모니터링:** 다음 서비스는 클라우드 커넥터 버전 2.0 이상에서 모니터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="e75ce-115">가상 컴퓨터가 클라우드 커넥터 회사 또는 인터넷 가상 스위치에 연결 되어 있지 않음</span><span class="sxs-lookup"><span data-stu-id="e75ce-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="e75ce-116">가상 컴퓨터가 저장 또는 중지 된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="e75ce-117">중앙 관리 서버 서비스: 복제본, 마스터</span><span class="sxs-lookup"><span data-stu-id="e75ce-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="e75ce-118">중재 서버 서비스: REPLICA, RTCSRV 및 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="e75ce-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="e75ce-119">에 지 서버 서비스: 복제본, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="e75ce-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="e75ce-120">중재 서버에서 RTCSRV에 지 서버, CS RTCMEDSRV의 CS에 대해 인바운드 방화벽 규칙이 사용 되지 않도록 설정 됨</span><span class="sxs-lookup"><span data-stu-id="e75ce-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="e75ce-121">클라우드 커넥터 버전 1.4.2에서는 다음 서비스만 모니터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="e75ce-122">중재 서버 서비스: RTCSRV 및 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="e75ce-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="e75ce-123">에 지 서버 서비스: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="e75ce-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="e75ce-124">**복구 프로세스:** 모니터링 되는 서비스가 다운 되 면 기기가 다운 된 것으로 표시 되며 모든 문제를 해결할 수 있을 때까지 서비스가 중지 되 고 설명서로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="e75ce-125">이렇게 하면 호출 오류가 발생할 수 있는 기기로의 호출이 차단 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="e75ce-126">클라우드 커넥터 관리 서비스는 다음과 같이 자동 복구를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="e75ce-127">초기 다시 시도 간격은 최대 10 초 간격으로 1 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="e75ce-128">처음 세 가지 복구를 시도 하는 경우 간격 시간은 10 초입니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="e75ce-129">네 번째 다시 시도 부터는 간격 시간이 이전 간격 시간의 2 배가 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="e75ce-130">예를 들어, 네 번째 다시 시도는 20 초, 5 번째는 40 초에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="e75ce-131">한 시간 동안 최대 간격 시간에 도달 하면 한 시간 마다 한 번씩 다시 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="e75ce-132">복구에 성공 하면 간격 및 다시 시도 횟수가 초기 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="e75ce-133">관리 서비스를 다시 시작 하면 간격 및 다시 시도 횟수가 초기 값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="e75ce-134">문제 해결</span><span class="sxs-lookup"><span data-stu-id="e75ce-134">Troubleshooting</span></span>

<span data-ttu-id="e75ce-135">다음은 일반적으로 발생 하는 문제에 대 한 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="e75ce-136">**문제: 배포 스크립트를 실행할 때 배포가 실패 하거나 응답을 멈춥니다. 각 VM에 로그온 한 후에는 관리/내부/외부 NIC에 대해 IP 주소가 누락 되거나 잘못 된 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="e75ce-137">**해결 방법:** 이 문제는 자동으로 해결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="e75ce-138">Nic를 실행 하는 동안 Vm에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="e75ce-139">Hyper-v 관리자에서 이러한 Vm을 종료 하 고 제거한 후 다음 cmdlet을 실행 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e75ce-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="e75ce-140">**문제: Active Directory 서버 및 포리스트를 설치한 후 CMS 서버 및/또는 중재 서버가 도메인에 올바르게 가입 하지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="e75ce-141">**해결 방법:** 이 문제를 해결 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="e75ce-142">Active Directory 서버에 로그온 하 고 도메인이 제대로 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="e75ce-143">CMS/중재 서버에 로그온 하 고 corpnet NIC에서 유효한 IP 주소가 할당 되었으며, 유효한 고정 IP 및 DNS가 AD 서버의 IP 주소로 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="e75ce-144">CMS/중재 서버에 로그온 하 고 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="e75ce-145">Active Directory 서버의 FQDN 및 IP 주소에 대해 ping을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="e75ce-146">사용할 수 없는 경우 IP 주소 충돌이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="e75ce-147">이에 따라 CMS/중재 서버에서 Active Directory에 대 한 새 IP를 할당 하 고 DNS를 업데이트 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="e75ce-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="e75ce-148">**문제: "Remove-VMSwitch: virtual Ethernet 스위치를 제거 하는 동안 다음 오류 메시지가 표시 됩니다. 가상 스위치 ' 클라우드 커넥터 관리 스위치 '은 (는) 실행 중인 가상 컴퓨터에서 사용 중이거나 자식 풀에 할당 되어 있으므로 삭제할 수 없습니다. "**</span><span class="sxs-lookup"><span data-stu-id="e75ce-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="e75ce-149">**해결 방법:** 배포 후에 "클라우드 커넥터 관리 스위치"가 삭제 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="e75ce-150">이 오류가 발생 하는 경우 Hyper-v 관리자로 이동 하 여 여전히 여전히 연결 된 가상 컴퓨터가 없는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e75ce-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="e75ce-151">아직 연결 된 가상 컴퓨터가 있으면 연결을 끊고 관리 스위치를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="e75ce-152">여전히 관리 스위치를 삭제할 수 없으면 호스트 서버를 다시 시작 하 고 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="e75ce-153">**문제: "서비스 RTCMRAUTH을 시작 하지 못했습니다. 라는 오류 메시지가 표시 됩니다. 서비스가 사용 하지 않도록 설정 되어 있는지 확인 하십시오. "**</span><span class="sxs-lookup"><span data-stu-id="e75ce-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e75ce-154">이 문제는 1.4.2 이전 클라우드 커넥터 버전에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="e75ce-155">또한이 프런트 엔드 서버가 이전에 장애 조치 (failover over 사용) 되었기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-155">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="e75ce-156">이 경우에는 장애 복구 (컴퓨터 장애 복구)를 호출 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e75ce-156">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="e75ce-157">**해결 방법:** 이 문제는에 지 서버에서 루트 CA 인증서 또는 중개 CA 인증서를 신뢰 하지 않을 때에 지 서버에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-157">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="e75ce-158">외부 인증서를 가져올 수 있지만 인증서 체인은 손상 된 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-158">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="e75ce-159">이 조건에서는 RTCMRAUTH 및/또는 RTCSRV 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-159">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="e75ce-160">외부 인증서의 루트 CA 인증서 및 모든 중간 CA 인증서를 수동으로에 지 서버에 가져온 다음에 지 서버를 다시 시작 하세요.</span><span class="sxs-lookup"><span data-stu-id="e75ce-160">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="e75ce-161">에 지 서버에서 RTCMRAUTH 및 RTCSRV 서비스가 시작 된 것을 확인 한 후에는 호스트 서버로 돌아가 PowerShell 콘솔을 관리자 권한으로 시작한 후 다음 cmdlet을 실행 하 여 새 배포로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-161">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="e75ce-162">**문제: Windows 업데이트를 적용 했을 때 호스트 서버가 다시 시작 되 고 서버에서 서비스를 제공 하는 통화가 실패 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="e75ce-163">**해결 방법:** 고가용성 환경을 배포한 경우 Microsoft는 Windows update를 수동으로 확인 하 고 설치할 때 하나의 호스트 컴퓨터 (배포 인스턴스)를 현재 토폴로지로 이동 하는 데 도움이 되는 cmdlet을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-163">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="e75ce-164">이 작업을 수행 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-164">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="e75ce-165">호스트 서버에서 PowerShell 콘솔을 관리자 권한으로 시작 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="e75ce-166">업데이트를 확인 하 고 사용 가능한 항목을 모두 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="e75ce-167">PowerShell 콘솔에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="e75ce-168">**문제: PSTN 번호를 사용 하 여 비즈니스용 Skype 클라이언트에서 전화를 건 경우 통화를 다른 PSTN 번호를 초대 하 여 전화 회의로 전달할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="e75ce-169">**해결 방법:** 이 문제를 해결 하려면 [Configure online Hybrid 중재 Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e75ce-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="e75ce-170">**문제: Active Directory server를 설치 하는 경우 Windows Update에 대 한 경고 메시지가 표시 됩니다.-"Windows 자동 업데이트가 사용 되도록 설정 되지 않았습니다. 새로 설치 된 역할 또는 기능이 자동으로 업데이트 되도록 하려면 Windows Update를 설정 합니다. "**</span><span class="sxs-lookup"><span data-stu-id="e75ce-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="e75ce-171">**해결 방법:** 비즈니스용 Skype 테 넌 트 관리자 자격 증명을 사용 하 여 테 넌 트 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행 하 여 사이트의 _Enableautoupdate 업데이트_ 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="e75ce-172">_Enableautoupdate 업데이트_ 를 **True**로 설정한 경우 CCEManagement 서비스는 가상 컴퓨터와 호스트 서버 둘 다에 대해 Windows 업데이트를 다운로드 하 고 설치 하는 것을 처리 하기 때문에이 경고 메시지를 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="e75ce-173">_Enableautoupdate 업데이트_ 를 **False**로 설정 하는 경우 다음 cmdlet을 실행 하 여 **True**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="e75ce-174">또는 수동으로 업데이트를 확인 하 고 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="e75ce-175">다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e75ce-175">See the next section.</span></span>
    
- <span data-ttu-id="e75ce-176">**문제: 현재 입력/구성 \< SiteName \> 또는 \< ApplianceName \> 또는 \< 중재 서버 FQDN \> 또는 \< 중재 서버 IP 주소가 \> 기존 기기와 충돌 하므로 기기를 등록할 수 없습니다. 충돌 하는 기기를 제거 하거나 입력/구성 정보를 업데이트 한 다음 다시 등록 합니다. ' 등록-CcAppliance를 실행 하 여 현재 기기를 온라인에 등록할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="e75ce-177">**해결 방법:** \<ApplianceName \> , \< 중재 서버 FQDN \> 및 중재 서버 IP 주소에 대 한 값은 \< \> 고유 하 고 하나의 기기 등록에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="e75ce-178">기본적으로 \< ApplianceName는 \> 호스트 이름에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="e75ce-179">\<\> \< \> 구성 ini 파일에 정의 된 중재 서버 FQDN 및 중재 서버 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="e75ce-180">예를 들어 (ApplianceName = MyserverNew, 중재 서버 FQDN = 10.10.10.10)를 사용 하 여 SiteName = 내 사이트에 등록 하지만 등록 된 기기가 있는 경우 (ApplianceName = Myserver, 중재 서버 FQDN =, 중재 서버 IP 주소 = 10.10.10.10)이 충돌을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="e75ce-181">먼저 ApplianceRoot directory 섹션에서 CloudConnector .ini 파일을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="e75ce-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="e75ce-182">\< \> \< 파일에서 SiteName, 중재 서버 FQDN \> 및 \< 중재 서버 IP 주소 값 \> 을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="e75ce-183">\<ApplianceName \> 는 호스트 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="e75ce-184">그런 다음 비즈니스용 Skype 테 넌 트 관리자 자격 증명을 사용 하 여 테 넌 트 원격 PowerShell을 시작한 후 다음 cmdlet을 실행 하 여 등록 된 기기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="e75ce-185">충돌을 확인 한 후에는 등록 된 기기와 일치 하는 정보로 CloudConnector .ini 파일을 업데이트 하거나 기존 기기를 등록 취소 하 여 충돌을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="e75ce-186">**문제: 호스트에서 실행 되는 배포 된 기기가 있는 경우 CcRunningVersion cmdlet은 빈 값을 반환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="e75ce-187">**해결 방법:** 1.3.4 또는 1.3.8에서 1.4.1으로 업그레이드할 때 이러한 상황이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="e75ce-188">.Msi와 함께 버전 1.4.1을 설치한 후에는 `Register-CcAppliance` 다른 cmdlet을 실행 하기 전에 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="e75ce-189">`Register-CcAppliance`%UserProfile%\CloudConnector 에서%ProgramData%\CloudConnector.로 모듈 .ini 파일을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="e75ce-190">누락 된 경우%ProgramData%\CloudConnector 폴더에 새 모듈이 생성 되 고 1.3.4 또는 1.3.8의 실행/백업 버전 정보를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="e75ce-191">%UserProfile%\CloudConnector 및%ProgramData%\CloudConnector 폴더에서 .ini 파일을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="e75ce-192">차이점이 있으면%ProgramData%\CloudConnector에서 모듈 .ini 파일을 삭제 하 고 다시 실행 `Register-CcAppliance` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="e75ce-193">올바른 실행 및 백업 버전으로 파일을 수동으로 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="e75ce-194">**문제: CcVersion cmdlet을 실행 하 여 현재 스크립트 버전과 다른 이전 버전으로 전환한 후에는이 이전 버전에 대 한 고가용성이 지원 되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="e75ce-195">**해결 방법:** 예를 들어 1.4.1에서 1.4.2으로 업그레이드 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="e75ce-196">실행 중에 확인할 수 있는 현재 스크립트 버전 및 실행 중인 `Get-CcVersion` 버전 `Get-CcRunningVersion` 은 모두 1.4.2입니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="e75ce-197">현재 `Switch-CcVersion` 실행 중인 버전을 다시 1.4.1으로 전환 하기 위해 실행 하는 경우이 이전 버전에 대 한 고가용성 지원이 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="e75ce-198">전체 고가용성 지원을 받으려면 1.4.2으로 다시 전환 하 여 실행 중인 버전 및 스크립트 버전이 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-198">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="e75ce-199">1.4.2 배포에 문제가 있는 경우에는 가능한 한 빨리 제거한 후 다시 설치 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e75ce-199">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="e75ce-200">**문제: 중앙 관리 저장소, 중재 서버 및에 지 서버에 발급 된 인증 기관 인증서 또는 내부 인증서가 거의 만료 되었거나 손상 되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="e75ce-201">**해결 방법:** 비즈니스용 Skype 인증 기관 인증서는 5 년 동안 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-201">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="e75ce-202">중앙 관리 저장소, 중재 서버 및에 지 서버에 발급 된 내부 인증서는 2 년 동안 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-202">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e75ce-203">클라우드 커넥터 버전 2.0 이상에서 CcServerCertificate cmdlet이 업데이트-CcServerCertificate로 변경 되었으며 CcCACertificate cmdlet이 CcCACertificate로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="e75ce-204">중앙 관리 저장소, 중재 서버 및에 지 서버에 발급 된 내부 인증서가 곧 만료 되거나 손상 되 면, CcServerCertificate 또는 업데이트-CcServerCertificate cmdlet을 실행 하 여 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="e75ce-205">인증 기관 인증서가 곧 만료 되는 경우 CcCACertificate 또는 CcCACertificate cmdlet을 실행 하 여 인증서를 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="e75ce-206">**인증 기관 인증서가 손상 되 고 사이트에 하나의 어플라이언스만 있는 경우** 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="e75ce-207">Enter-CcUpdate cmdlet을 실행 하 여 서비스를 드레이닝 하 고 기기를 유지 관리 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="e75ce-208">다음 cmdlet를 실행 하 여 새 인증 기관 인증서와 모든 내부 서버 인증서를 다시 설정 하 고 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="e75ce-209">2.0 이전 클라우드 커넥터 릴리스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="e75ce-210">또는 클라우드 커넥터 릴리스 2.0 이상에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="e75ce-211">게이트웨이와 중재 서버 간에 TLS를 사용 하는 경우 기기에서 CcRootCertificate cmdlet을 실행 한 다음, 내보낸 인증서를 PSTN 게이트웨이에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="e75ce-212">게이트웨이에서 인증서를 다시 발급 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="e75ce-213">서비스를 시작 하 고 유지 관리 모드를 종료 하려면 CcUpdate cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="e75ce-214">**인증 기관 인증서가 손상 되 고 사이트에 여러 기기가 있는 경우** 사이트의 각 기기에 대해 다음과 같은 순차적 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="e75ce-215">사용량이 많지 않은 시간에 이러한 단계를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="e75ce-216">첫 번째 기기에서 CcCertificationAuthorityFile cmdlet을 실행 하 여 SiteRoot 디렉터리에서 CA 백업 파일을 정리 \< \> 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="e75ce-217">Enter-CcUpdate cmdlet을 실행 하 여 서비스를 드레이닝 하 고 각 기기를 유지 관리 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="e75ce-218">첫 번째 기기에서 다음 cmdlet을 실행 하 여 새 인증 기관 인증서와 모든 내부 서버 인증서를 다시 설정 하 고 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="e75ce-219">2.0 이전 클라우드 커넥터 릴리스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="e75ce-220">또는 클라우드 커넥터 릴리스 2.0 이상에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="e75ce-221">첫 번째 기기에서 다음 cmdlet을 실행 하 여 CA 파일을 SiteRoot 폴더에 백업 \< 합니다 \> .</span><span class="sxs-lookup"><span data-stu-id="e75ce-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="e75ce-222">같은 사이트에 있는 다른 모든 기기의 경우 다음 명령을 실행 하 여 CA 백업 파일을 사용 하 고 해당 기기가 모두 동일한 루트 인증서를 사용 하도록 설정한 다음 새 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="e75ce-223">게이트웨이와 중재 서버 간에 TLS를 사용 하는 경우 사이트의 모든 기기에서 CcRootCertificate cmdlet을 실행 한 다음, 내보낸 인증서를 PSTN 게이트웨이에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="e75ce-224">게이트웨이에서 인증서를 다시 발급 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="e75ce-225">서비스를 시작 하 고 유지 관리 모드를 종료 하려면 CcUpdate cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="e75ce-226">**문제: 클라우드 커넥터 관리 서비스 로그, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0: 상태를 온라인으로 보고할 때 예기치 않은 예외가 발생 했습니다. CmdletInvocationException: 사용자 \< 전역 테 넌 트 관리자에 대해 로그온에 실패 \> 했습니다. 새 credential 개체를 만들어 올바른 사용자 이름과 암호를 사용 했는지 확인 하십시오. ---\>**</span><span class="sxs-lookup"><span data-stu-id="e75ce-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="e75ce-227">**해결 방법:** 클라우드 커넥터 기기가 등록 된 이후 Microsoft 365 또는 Office 365 전역 테 넌 트 관리자 자격 증명이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-227">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="e75ce-228">클라우드 커넥터 기기에서 로컬로 저장 된 자격 증명을 업데이트 하려면 호스트 기기의 관리자 PowerShell에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="e75ce-229">**문제: 배포에 사용한 호스트 서버 계정의 암호를 변경한 후에는 "ConvertTo-SecureString: 키를 지정한 상태에서 사용할 수 없습니다." 라는 오류 메시지가 표시 됩니다. "for Business Cloud Connector Edition\ManagementService\CceManagementService.log 또는%ProgramFiles%\Skype Get-CcCredential cmdlet을 실행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="e75ce-230">**해결 방법:** 모든 클라우드 커넥터 자격 증명은 "%SystemDrive%\Programdata\Cloudconnector\credentials. \< " 파일에 저장 됩니다. CurrentUser \> "가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="e75ce-231">호스트 서버의 암호가 변경 되 면 로컬로 저장 된 자격 증명을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="e75ce-232">**클라우드 커넥터 버전 1.4.2을 실행 하는 경우** 다음 단계를 수행 하 여 모든 클라우드 커넥터 암호를 다시 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="e75ce-233">호스트 서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="e75ce-234">다음 파일을 삭제 합니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> "가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="e75ce-235">PowerShell 콘솔을 관리자 권한으로 시작한 다음 "레지스터-CcAppliance-Local"을 실행 하 여 설명에 해당 하는 암호를 다시 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="e75ce-236">클라우드 커넥터 배포 전에 입력 한 것과 동일한 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="e75ce-237">**클라우드 커넥터 버전 2.0 이상을 실행 하는 경우** 다음 단계를 수행 하 여 모든 클라우드 커넥터 암호를 다시 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="e75ce-238">호스트 서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="e75ce-239">다음 파일을 삭제 합니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> "가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="e75ce-240">PowerShell 콘솔을 관리자 권한으로 시작한 다음 "레지스터-CcAppliance-Local"을 실행 하 여 설명에 해당 하는 암호를 다시 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="e75ce-241">클라우드 커넥터 버전 1.4.2를 사용 하 여 캐시 된 암호 파일을 생성 한 경우에는 메시지가 표시 되 면 CceService 암호에 대 한 VMAdmin 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-241">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="e75ce-242">다른 모든 계정의 클라우드 커넥터 배포 전에 입력 한 것과 동일한 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-242">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="e75ce-243">클라우드 커넥터 버전 1.4.2와 함께 캐시 된 암호 파일을 생성 하 고 DomainAdmin 및 VMAdmin 암호가 서로 다른 경우에는 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="e75ce-244">Set-CcCredential-AccountType DomainAdmin을 다음과 같이 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="e75ce-245">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="e75ce-246">새 계정 자격 증명을 묻는 메시지가 표시 되 면 이전에 사용한 DomainAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="e75ce-247">클라우드 커넥터 버전 2.0 이상으로 캐시 된 암호 파일을 생성 한 경우, 기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="e75ce-248">DomainAdmin 및 VMAdmin 암호를 변경한 경우에는 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="e75ce-249">Set-CcCredential-AccountType DomainAdmin을 다음과 같이 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="e75ce-250">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="e75ce-251">새 계정 자격 증명을 묻는 메시지가 표시 되 면 이전에 사용한 DomainAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="e75ce-252">다음과 같이 Set-CcCredential-AccountType VmAdmin을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="e75ce-253">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="e75ce-254">새 계정 자격 증명을 묻는 메시지가 표시 되 면 이전에 사용한 VmAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="e75ce-255">**문제: 클라우드 커넥터 버전 2.1 이상을 사용 하는 경우 기기에서 등록-CcAppliance 기타 cmdlet을 실행 하면 "For Each-Object:이 개체에서 ' Common ' 속성을 찾을 수 없습니다. 라는 오류 메시지가 표시 됩니다. 속성이 있는지 확인 합니다. C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="e75ce-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="e75ce-256">**해결 방법:** 클라우드 커넥터 2.1 이상에는 .NET Framework 4.6.1 이상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="e75ce-257">기기의 .NET Framework를 버전 4.6.1 이상으로 업데이트 하 고 cmdlet을 다시 실행 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e75ce-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="e75ce-258">**문제: 클라우드 커넥터 에디션 2.1을 사용 하 여 설치-CcAppliance를 실행 하는 경우 "오류가 발생 하 여 새 인스턴스를 설치 하지 못했습니다." 라는 오류 메시지가 표시 됩니다. "State"를 설정할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="e75ce-259">**해결 방법:** Cloudconnector .ini의 [Common] 섹션에 있는 "State" config를 아래와 같이 추가 하십시오. CountryCode = US State = WA 구/군/시 = Redmond</span><span class="sxs-lookup"><span data-stu-id="e75ce-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="e75ce-260">"State" 줄이 값을 갖는 것은 필수가 아니며, Cloudconnector .ini 파일에서 "State" 줄을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="e75ce-261">**문제: "WindowsImage: WindowsImage에 오류가 발생 하 여 다음 오류 메시지가 나타납니다. 클라우드 커넥터 버전을 설치 또는 업그레이드할 때 오류 코드 = 0xc1550115 "입니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="e75ce-262">**해결 방법:** PowerShell 콘솔을 관리자 권한으로 시작 하 고 "DISM-Cleanup-.Wim '"을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="e75ce-263">이렇게 하면 모든 troubled 이미지가 정리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-263">This will clean up all troubled images.</span></span> <span data-ttu-id="e75ce-264">설치-CcAppliance를 다시 실행 하거나 bits가 자동으로 업그레이드 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="e75ce-265">**문제: HA 환경에서 첫 번째 클라우드 커넥터 기기의 배포가 실패 함**</span><span class="sxs-lookup"><span data-stu-id="e75ce-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="e75ce-266">**해결 방법:** 수행 하는 단계는 배포에 실패 한 이유에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="e75ce-267">첫 번째 클라우드 커넥터 기기가 실패 하 고 실패 이유를 확인할 수 없는 경우 배포가 성공할 때까지 기기를 다시 설치한 다음 다른 기기를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="e75ce-268">첫 번째 클라우드 커넥터 기기가 오류가 발생 하는 경우 (예: 외부 인증서 문제) 기기를 다시 설치 하지 않고도 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="e75ce-269">그런 다음 테 넌 트 원격 PowerShell을 사용 하 여 배포를 다음과 같이 성공한 것으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="e75ce-270">(첫 번째 배포가 성공한 경우에는 다음 단계를 사용할 수도 있지만, 어떤 이유로 클라우드 커넥터가 성공으로 배포를 보고 하지 못할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="e75ce-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="e75ce-271">첫 번째 클라우드 커넥터 기기의 Id (GUID)를 가져오려면 CsHybridPSTNAppliance cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="e75ce-272">기기를 성공적으로 배포 된 것으로 표시 하려면 다음과 같이 CsCceApplianceDeploymentStatus를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="e75ce-273">**문제: 호스트 서버 또는 가상 컴퓨터에서 Windows 업데이트를 확인 하 고 수동으로 설치 해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="e75ce-274">**해결 방법:** 비즈니스용 Skype 클라우드 커넥터 Edition에서 제공 하는 자동화 된 OS 업데이트를 활용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-274">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="e75ce-275">온라인 관리를 위해 기기가 등록 되 고 자동 OS 업데이트가 사용 하도록 설정 되 면 호스트 서버와 가상 컴퓨터는 OS 업데이트 시간 창 설정에 따라 Windows 업데이트를 자동으로 확인 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-275">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="e75ce-276">Windows 업데이트를 확인 하 고 설치 해야 하는 경우이 섹션의 배포 유형에 적용 되는 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-276">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="e75ce-277">업데이트에 필요한 가동 중지 시간을 최소화 하기 위해 동시에 실행 되는 호스트 서버와 가상 컴퓨터를 모두 업데이트 하는 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-277">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="e75ce-278">원하는 경우 WSUS (Windows Server Update Services) 서버를 사용 하 여 클라우드 커넥터 서버에 대 한 업데이트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-278">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="e75ce-279">Windows 업데이트가 자동으로 설치 **되지** 않도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-279">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="e75ce-280">클라우드 커넥터 배포를 수동으로 업데이트 하는 방법에 대 한 자세한 내용은 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e75ce-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="e75ce-281">**문제: 클라우드 커넥터가 새 빌드로 업데이트 되 면 클라우드 커넥터 cmdlet이 업데이트 되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="e75ce-282">자동 업데이트가 발생할 때 PowerShell 창이 열려 있으면이 문제가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="e75ce-283">**해결 방법:** 업데이트 된 cmdlet을 로드 하려면 다음 단계 중 하나를 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="e75ce-284">클라우드 커넥터 기기에서 PowerShell을 닫고 PowerShell을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="e75ce-285">또는 Import-Module CloudConnector-Force를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="e75ce-286">**Issue: "' Stop-CsWindowsService ' 용어가 cmdlet, 함수, 스크립트 파일 또는 실행 가능한 프로그램의 이름으로 인식 되지 않습니다." 라는 오류가 발생 했습니다.**</span><span class="sxs-lookup"><span data-stu-id="e75ce-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="e75ce-287">**해결 방법:** $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 파일을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="e75ce-288">PowerShell은이 파일을 발견 하는 모듈의 cmdlet 캐시로 만들며, 따라서 시간이 오래 걸릴 때마다 모든 모듈을 다시 분석 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="e75ce-289">대부분의 경우 해당 캐시에서 다시 읽어 오는 경우 PowerShell에 잘못 된 결과가 제공 되는 일부 파일 손상이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="e75ce-290">**문제: "Import-Module CloudConnector" 오류가 발생 합니다. "가져오기-모듈: 모듈 디렉터리에서 올바른 모듈 파일을 찾을 수 없기 때문에 지정 된 모듈" CloudConnector "가 로드 되지 않았습니다."**</span><span class="sxs-lookup"><span data-stu-id="e75ce-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="e75ce-291">**해결 방법:**</span><span class="sxs-lookup"><span data-stu-id="e75ce-291">**Resolution:**</span></span>
    - <span data-ttu-id="e75ce-292">정말로 c:\Program Files\WindowsPowerShell\Modules에 있는 CloudConnector 모듈이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="e75ce-293">이 위치에 CloudConnector 모듈이 있는지 확인 한 후에는 모듈 위치에 대 한 경로를 저장 하는 PSModulePath 환경 변수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="e75ce-294">a.</span><span class="sxs-lookup"><span data-stu-id="e75ce-294">a.</span></span> <span data-ttu-id="e75ce-295">임시 변경: 관리자 권한으로 Powershell을 시작 하 고 $env:P SModulePath = $env:P SModulePath + "명령을 실행 합니다. C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="e75ce-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="e75ce-296">b.</span><span class="sxs-lookup"><span data-stu-id="e75ce-296">b.</span></span> <span data-ttu-id="e75ce-297">영구적으로 변경 하려면 PowerShell을 관리자 권한으로 시작 하 고 다음 명령을 하나씩 실행 합니다. $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + ";) C:\Program Files\WindowsPowerShell\Modules "," Machine ")</span><span class="sxs-lookup"><span data-stu-id="e75ce-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="e75ce-298">수동으로 Windows 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="e75ce-298">Install Windows updates manually</span></span>

<span data-ttu-id="e75ce-299">사용자 환경에서 자동 업데이트를 사용 하지 않으려면 다음 단계를 수행 하 여 Windows 업데이트를 수동으로 확인 하 고 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="e75ce-300">Windows 업데이트를 확인 하 고 설치 하려면 서버를 다시 시작 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="e75ce-301">호스트 서버를 다시 시작 하면 사용자가 클라우드 커넥터를 사용 하 여 전화를 걸거나 받을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="e75ce-302">업데이트를 수동으로 확인 하 고 설치한 후 업데이트가 수행 되는 시기를 제어할 수 있으며, 서비스 중단을 방지 하기 위해 필요한 경우 컴퓨터를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="e75ce-303">업데이트를 수동으로 확인 하려면 각 호스트 서버에 연결 하 고 **제어판**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="e75ce-304">**시스템 및 보안 \> Windows Update**를 선택한 다음 환경에 맞게 업데이트 및 서버 다시 시작을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="e75ce-305">사이트에 기기가 하나뿐인 경우 각 가상 컴퓨터에 연결 하 고 **제어판**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="e75ce-306">**시스템 및 보안 \> Windows 업데이트**를 선택 하 고 적절 하 게 업데이트 및 서버 다시 시작을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="e75ce-307">사이트에 기기가 두 개 이상 있는 경우 업데이트 하 고 다시 시작 하는 인스턴스를 업데이트할 때 사용자가 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-307">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="e75ce-308">사용자는 모든 가상 컴퓨터와 모든 비즈니스용 Skype 서비스가 업데이트를 완료 한 후에 시작할 때까지 배포의 다른 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-308">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="e75ce-309">서비스 중단 가능성을 방지 하려면 업데이트를 적용 하는 동안 HA에서 인스턴스를 제거한 다음 완료 되 면 복원 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-309">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="e75ce-310">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-310">To do so:</span></span>
    
1. <span data-ttu-id="e75ce-311">각 호스트 서버에서 PowerShell 콘솔을 관리자 권한으로 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="e75ce-312">다음 cmdlet을 사용 하 여 HA에서 인스턴스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="e75ce-313">단일 인스턴스에 대 한 단계를 수행 하 여 업데이트를 수동으로 적용 하 고 가상 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="e75ce-314">다음 cmdlet을 사용 하 여 인스턴스를 다시 HA로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="e75ce-315">다중 사이트 배포의 경우 배포의 각 사이트에 대해 단일 사이트에 대 한 단계를 수행 하 여 한 번에 한 사이트에 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="e75ce-316">클라우드 커넥터 호스트 컴퓨터에 바이러스 백신 소프트웨어를 설치할 때의 팁</span><span class="sxs-lookup"><span data-stu-id="e75ce-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="e75ce-317">클라우드 커넥터 호스트 컴퓨터에 바이러스 백신 소프트웨어를 설치 해야 하는 경우 다음 제외 항목을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="e75ce-318">각 컴퓨터의 로컬 기기 디렉터리</span><span class="sxs-lookup"><span data-stu-id="e75ce-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="e75ce-319">각 컴퓨터의 원격 사이트 디렉터리</span><span class="sxs-lookup"><span data-stu-id="e75ce-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="e75ce-320">컴퓨터의 로컬 사이트 디렉터리가 공유 사이트 루트 폴더를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="e75ce-321">비즈니스용%ProgramFiles%\Skype Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="e75ce-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="e75ce-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="e75ce-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="e75ce-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="e75ce-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="e75ce-324">CCE. ManagementService를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e75ce-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
