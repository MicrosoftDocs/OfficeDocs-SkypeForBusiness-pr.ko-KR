---
title: 비즈니스용 Skype 서버 통계 관리자 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: '요약: 비즈니스용 Skype 서버용 통계 관리자를 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: 44aad14970716f00550255855d251919a767a268
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803968"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="3de58-103">비즈니스용 Skype 서버 통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="3de58-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="3de58-104">**요약:** 비즈니스용 Skype 서버용 통계 관리자를 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3de58-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="3de58-105">비즈니스용 Skype Server의 통계 관리자는 비즈니스용 Skype 서버 상태 및 성능 데이터를 실시간으로 볼 수 있는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="3de58-106">여러 서버에서 성능 데이터를 몇 초 마다 폴링하거나 통계 관리자 웹 사이트에서 즉시 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="3de58-107">통계 관리자를 설치 하려고 하기 전에 소프트웨어, 네트워킹 및 하드웨어 요구 사항에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="3de58-108">자세한 내용은 [비즈니스용 Skype 서버에 대 한 통계 관리자 계획](plan.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3de58-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3de58-109">이전 버전의 통계 관리자에서 업그레이드 하는 경우 [비즈니스용 Skype 서버용 업데이트 통계 관리자](upgrade.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3de58-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3de58-110">통계 관리자 웹 사이트는 Internet Explorer 11 이상, Edge 20.10240 +, Chrome 46 + (현재 11 번째 버전)에서 테스트 되어 올바르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="3de58-111">에서 [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)다운로드 가능한 통계 관리자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="3de58-112">이 항목에서는 다음 섹션을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="3de58-113">통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="3de58-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="3de58-114">배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3de58-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="3de58-115">자체 서명 된 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="3de58-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="3de58-116">통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="3de58-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="3de58-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="3de58-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="3de58-118">통계 관리자를 배포 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="3de58-119">Redis 메모리 내 캐싱 시스템을 설치 하 고 적절 한 인증서가 설치 되었는지 확인 하 여 수신기 호스트 컴퓨터를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="3de58-120">호스트 컴퓨터에 수신기 서비스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="3de58-121">호스트 컴퓨터에 웹 사이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="3de58-122">모니터링할 각 비즈니스용 Skype 서버 컴퓨터에 에이전트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="3de58-123">모니터링 하는 서버에 대 한 토폴로지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3de58-124">Redis, 수신기 서비스 및 웹 사이트가 모두 동일한 호스트 컴퓨터에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="3de58-125">호스트 컴퓨터에 비즈니스용 Skype 서버가 설치 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="3de58-126">수신기 호스트 컴퓨터 준비</span><span class="sxs-lookup"><span data-stu-id="3de58-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="3de58-127">호스트 컴퓨터를 준비 하려면 Redis 메모리 내 캐싱 시스템을 설치 하 고 올바른 인증서가 컴퓨터에 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="3de58-128">Microsoft는 Redis 3.0의 최신 안정적인 빌드를 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="3de58-129">통계 관리자 버전 2.0 Redis 3.2.100에서 테스트를 거쳤습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="3de58-130">다음 사이트에서 Redis을 다운로드 합니다 [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span><span class="sxs-lookup"><span data-stu-id="3de58-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="3de58-131">서명 되지 않은 설치 관리자는 다음에서 다운로드할 수 있습니다.[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="3de58-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="3de58-132">필요한 경우 인기 있는 패키지 관리자: [Nuget](https://www.nuget.org/packages/Redis-64/) 및 [Choclatey](https://chocolatey.org/packages/redis-64)에서 서명 된 이진 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="3de58-133">제공 된 msi를 실행 하 고 화면의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="3de58-134">방화벽 규칙 추가 확인란을 선택 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3de58-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="3de58-135">수신기 서비스에는 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="3de58-136">Microsoft는 신뢰할 수 있는 인증 기관에서 서명한 인증서를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="3de58-137">랩에서 테스트 목적으로 자체 서명 된 인증서를 사용 하려는 경우 (예: [자체 서명 된 인증서 만들기](deploy.md#BKMK_SelfCert))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3de58-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="3de58-138">에이전트는 체인 확인 대신 인증서 지문 확인을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="3de58-139">자체 서명 된 인증서를 사용할 수 있기 때문에 전체 인증서 유효성 검사를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="3de58-140">수신기 서비스 설치</span><span class="sxs-lookup"><span data-stu-id="3de58-140">Install the Listener service</span></span>

<span data-ttu-id="3de58-141">Stats마나트 Cpagentlistener를 실행 하 고 다음을 지정 하 여 호스트 컴퓨터에 수신기 서비스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="3de58-142">사용권 계약을 검토 하 고 동의할 경우 **사용권 계약에 동의 함을**선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="3de58-143">다음 페이지에서 다음 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="3de58-144">**서비스 비밀 번호:** 원격 에이전트가 수신기 서비스에 인증 하는 데 사용할 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="3de58-145">**서비스 포트:** 이는 수신기가 에이전트와 통신 하는 데 사용할 HTTPS 포트 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="3de58-146">설치 중에이 포트는 로컬 방화벽을 통해 허용 되 고, URL ACL이 만들어지고, SSL 인증서가이 포트에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="3de58-147">기본값은 8443입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="3de58-148">**인증서 지문:** 이는 수신기가 HTTPS 프로토콜을 암호화 하는 데 사용할 인증서 지문입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="3de58-149">네트워크 서비스에는 개인 키에 대 한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="3de58-150">**선택 ...** 단추를 클릭 하 여 지문을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="3de58-151">인증서 관리자를 사용 하거나 다음 PowerShell 명령을 사용 하 여 인증서 지문을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```PowerShell
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="3de58-152">**설치 디렉터리:** 바이너리가 설치 될 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="3de58-153">**찾아보기를** 클릭 하 여 기본값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="3de58-154">**AppData Dir:** 로그 폴더와 다른 데이터가 저장 되는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="3de58-155">기본값에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-155">You may change it from the default.</span></span> <span data-ttu-id="3de58-156">제거 시에 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="3de58-157">**설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-157">Click **Install**.</span></span>
    
<span data-ttu-id="3de58-158">설치의 유효성을 검사 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="3de58-159">브라우저를 열고 다음으로 이동 합니다.https://localhost:\<service-port\>/healthcheck/</span><span class="sxs-lookup"><span data-stu-id="3de58-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="3de58-160">기본적으로 서비스 포트는 8443입니다 (다른 포트를 지정 하지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="3de58-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="3de58-161">수신기가 제대로 설치 되었는지 확인 하려면 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="3de58-162">Healthcheck 페이지가 표시 되 면 수신기가 성공적으로 설치 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="3de58-163">KnownServerCount가 1 이상인 경우 Redis에 대 한 연결이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="3de58-164">몇 분 정도 기다렸다가 하나 이상의 에이전트가 설치 된 후에는 Value쓰여진 카운터가 증가 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="3de58-165">웹 사이트 설치</span><span class="sxs-lookup"><span data-stu-id="3de58-165">Install the Website</span></span>

<span data-ttu-id="3de58-166">[비즈니스용 Skype Server, 실시간 통계 관리자 (64 비트)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) 및 다음을 지정 하 여 Stats마나트 웹 사이트 (msi)를 실행 하 여 호스트 컴퓨터에 웹 사이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="3de58-167">사용권 계약을 검토 하 고 동의할 경우 **사용권 계약에 동의 함을**선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="3de58-168">다음 페이지에서 다음 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="3de58-169">**서비스 포트:** 웹 사이트가 수신 대기 하는 포트 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="3de58-170">나중에 IIS 관리자 바인딩을 사용 하 여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="3de58-171">설치 중에이 포트는 로컬 방화벽을 통해 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="3de58-172">**설치 디렉터리:** 바이너리가 설치 되는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="3de58-173">**찾아보기를** 클릭 하 여 기본값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="3de58-174">**AppData Dir:** 로그 폴더와 다른 데이터가 저장 되는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="3de58-175">기본값에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-175">You may change it from the default.</span></span> <span data-ttu-id="3de58-176">제거 시에 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="3de58-177">**설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-177">Click **Install**.</span></span>
    
<span data-ttu-id="3de58-178">웹 사이트를 보려면 브라우저를 열고 http://localhost,, webport\>/.를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="3de58-179">상태 정보만 보려면 브라우저를 열고 다음 http://localhost:\<webport\>/healthcheck/으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="3de58-180">기본적으로 웹 포트 번호는 8080입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="3de58-181">IIS 관리자를 사용 하 여 웹 사이트의 포트 바인딩을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="3de58-182">웹 설치 관리자가 StatsManWebSiteUsers 이라는 로컬 보안 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="3de58-183">이 보안 그룹에 계정을 추가 하 여 웹 사이트에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="3de58-184">에이전트 설치</span><span class="sxs-lookup"><span data-stu-id="3de58-184">Install the Agents</span></span>

<span data-ttu-id="3de58-185">Stats Perfagent를 실행 하 고 다음을 지정 하 여 모니터링할 각 비즈니스용 Skype 서버에 에이전트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="3de58-186">사용권 계약을 검토 하 고 동의할 경우 **사용권 계약에 동의 함을**선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="3de58-187">다음 페이지에서 다음 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="3de58-188">**서비스 비밀 번호:** 원격 에이전트가 수신기 서비스에 인증 하는 데 사용할 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="3de58-189">**서비스 URI:** 수신기가 상주 하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="3de58-190">https://name:port 형식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="3de58-191">NETBIOS 이름 또는 FQDN을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="3de58-192">수신기 서비스에서 인증서의 **주체 또는** **주체의 대체 이름** 으로도 지정 된 이름을 사용할 수 있지만, 반드시 그럴 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="3de58-193">**서비스 지문:** 수신기가 사용 하는 SSL 인증서의 지문입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="3de58-194">에이전트는이 지문을 사용 하 여 수신기를 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="3de58-195">(자체 서명 된 인증서를 사용할 수 있기 때문에 전체 인증서 유효성 검사를 수행 하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="3de58-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="3de58-196">**설치 디렉터리:** 바이너리가 설치 될 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="3de58-197">**찾아보기를** 클릭 하 여 기본값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="3de58-198">**AppData Dir:** 로그 폴더와 암호화 된 암호 .txt 파일이 저장 되는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="3de58-199">기본값에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-199">You may thanks change it from the default.</span></span> <span data-ttu-id="3de58-200">제거 시에 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="3de58-201">**설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-201">Click **Install**.</span></span>
    
<span data-ttu-id="3de58-202">여러 컴퓨터에 에이전트를 설치 하는 경우 무인 모드에서이 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="3de58-203">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-203">For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="3de58-204">토폴로지 가져오기</span><span class="sxs-lookup"><span data-stu-id="3de58-204">Import the topology</span></span>
<span data-ttu-id="3de58-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="3de58-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="3de58-206">통계 관리자를 설치 하 고 실행 한 후에는 통계 관리자가 각 서버의 사이트, 풀 및 역할을 인식할 수 있도록 비즈니스용 Skype 서버 토폴로지를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="3de58-207">비즈니스용 Skype 서버 토폴로지를 가져오려면 [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet을 사용 하 여 조직에서 사용 중인 각 풀에 대 한 정보를 검색 한 다음이 정보를 통계 관리자로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="3de58-208">비즈니스용 Skype 서버 토폴로지를 가져오려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="3de58-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="3de58-209">비즈니스용 Skype Server PowerShell cmdlet이 있는 호스트에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="3de58-210">에서.</span><span class="sxs-lookup"><span data-stu-id="3de58-210">a.</span></span> <span data-ttu-id="3de58-211">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="3de58-212">b.</span><span class="sxs-lookup"><span data-stu-id="3de58-212">b.</span></span> <span data-ttu-id="3de58-213">"Mypoolinfo" 파일을 수신기를 실행 하는 서버에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="3de58-214">수신기를 실행 하는 호스트에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="3de58-215">에서.</span><span class="sxs-lookup"><span data-stu-id="3de58-215">a.</span></span> <span data-ttu-id="3de58-216">PowerShell을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="3de58-217">b.</span><span class="sxs-lookup"><span data-stu-id="3de58-217">b.</span></span> <span data-ttu-id="3de58-218">수신기가 설치 된 디렉터리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="3de58-219">기본값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-219">The default is:</span></span> 
    
   ```PowerShell
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="3de58-220">추가 되 고 업데이트 되는 서버를 확인 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```PowerShell
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="3de58-221">다음 명령을 사용 하 여 모든 옵션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-221">The following command enables you to view all options:</span></span>
  
```PowerShell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="3de58-222">현재 가져온 서버 정보를 보려면 다음 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-222">To see your currently imported server information, run the following script:</span></span> 
  
```PowerShell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="3de58-223">비즈니스용 Skype 서버 토폴로지에 없는 서버 (예: Exchange 서버)를 모니터링 하려는 경우 수신기를 실행 하는 호스트에서 단일 서버 가져오기를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="3de58-224">단일 서버 가져오기를 수행 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="3de58-225">수신기가 설치 된 디렉터리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="3de58-226">기본값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="3de58-227">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="3de58-228">배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3de58-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="3de58-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="3de58-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="3de58-230">에이전트가 시작 되지 않으면 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="3de58-231">에이전트가 통계 관리자에 등록 되어 있습니까?</span><span class="sxs-lookup"><span data-stu-id="3de58-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="3de58-232">토폴로지 가져오기에 대 한 지침을 따랐는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="3de58-233">[토폴로지 가져오기를](deploy.md#BKMK_ImportTopology)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3de58-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="3de58-234">에이전트가 토폴로지에 나열 되지 않은 서버 (예: SQL AlwaysOn 클러스터의 노드)에 있는 경우 [토폴로지 가져오기](deploy.md#BKMK_ImportTopology)의 지침에 따라 에이전트를 수동으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="3de58-235">에이전트가 수신기에 연결할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="3de58-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="3de58-236">수신기 서비스가 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="3de58-237">실행 중이지 않은 경우 Redis가 실행 중인지 확인 한 다음 수신기를 다시 시작 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="3de58-238">포트가 수신기 서비스에 열려 있고 에이전트 컴퓨터가 포트와 통신할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="3de58-239">통계 관리자가 데이터를 수집 하 고 있는지 확인 하려면 다음과 같이 CSV 파일을 확인 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="3de58-240">다음 명령은 카운터 저장소 이름을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="3de58-241">다음 명령은 지정 된 카운터의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="3de58-242">응용 프로그램 이벤트 로그에 표시 될 수 있는 모든 이벤트에 대 한 자세한 내용은 비즈니스용 [Skype 서버에 대 한 통계 관리자 문제 해결](troubleshoot.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3de58-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="3de58-243">자체 서명 된 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="3de58-243">Create a self-signed certificate</span></span>
<span data-ttu-id="3de58-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="3de58-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="3de58-245">Microsoft는 신뢰할 수 있는 인증 기관에서 서명한 인증서를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="3de58-246">그러나 테스트 목적으로 자체 서명 된 인증서를 사용 하려는 경우에는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="3de58-247">관리자로 로그온 한 상태에서 PowerShell 콘솔에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```PowerShell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="3de58-248">형식을 `certlm.msc`입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="3de58-249">로컬 컴퓨터의 인증서 관리자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="3de58-250">**개인**으로 이동한 다음 **인증서**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="3de58-251">**Stats마나트 수신기\>-모든 작업-\>개인 키 관리 ...** 를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="3de58-252">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="3de58-253">**선택할 개체 이름 입력** 상자에 다음을 입력 합니다. 네트워크 서비스</span><span class="sxs-lookup"><span data-stu-id="3de58-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="3de58-254">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="3de58-255">**모든 권한**에서 **허용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="3de58-256">(읽기 액세스만 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="3de58-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="3de58-257">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3de58-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="3de58-258">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="3de58-258">For more information</span></span>
<span data-ttu-id="3de58-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="3de58-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="3de58-260">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3de58-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="3de58-261">비즈니스용 Skype 서버 통계 관리자에 대한 계획</span><span class="sxs-lookup"><span data-stu-id="3de58-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="3de58-262">비즈니스용 Skype 서버 통계 관리자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="3de58-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="3de58-263">[비즈니스용 Skype Server ß의 통계 관리자 문제 해결](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="3de58-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
