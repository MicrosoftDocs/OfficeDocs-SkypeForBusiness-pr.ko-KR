---
title: 비즈니스용 Skype 서버 통계 관리자 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 통계 관리자를 배포하는 방법을 배워 읽습니다.'
ms.openlocfilehash: 79e07c29a5df4a5da239687708a9bb52e995d191
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814818"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="84006-103">비즈니스용 Skype 서버 통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="84006-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="84006-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 통계 관리자를 배포하는 방법을 배워 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="84006-105">비즈니스용 Skype 서버 통계 관리자는 비즈니스용 Skype 서버 상태 및 성능 데이터를 실시간으로 볼 수 있는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="84006-106">몇 초마다 수백 대의 서버로 성능 데이터를 폴링하고 통계 관리자 웹 사이트에서 결과를 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="84006-107">Statistics Manager를 설치하기 전에 소프트웨어, 네트워킹 및 하드웨어 요구 사항에 익숙해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="84006-108">자세한 내용은 비즈니스용 Skype 서버 통계 관리자 [계획(Plan for Statistics Manager)을 참조하십시오.](plan.md)</span><span class="sxs-lookup"><span data-stu-id="84006-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="84006-109">이전 버전의 통계 관리자에서 업그레이드하는 경우 비즈니스용 Skype 서버의 업그레이드 통계 관리자를 [참조하세요.](upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="84006-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="84006-110">Statistics Manager 웹 사이트가 테스트되어 Internet Explorer 11+, Edge 20.10240+ 및 Chrome 46+(현재 버전)에서 올바르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="84006-111">통계 관리자는 에서 다운로드할 수 [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="84006-112">이 항목에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="84006-113">통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="84006-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="84006-114">배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="84006-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="84006-115">자체 서명된 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="84006-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="84006-116">통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="84006-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="84006-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="84006-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="84006-118">통계 관리자를 배포하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="84006-119">Redis 인 메모리 캐싱 시스템을 설치하고 적절한 인증서를 설치하여 수신기 호스트 시스템을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="84006-120">호스트 컴퓨터에 수신기 서비스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="84006-121">호스트 컴퓨터에 웹 사이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="84006-122">모니터링할 각 비즈니스용 Skype 서버 컴퓨터에 에이전트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="84006-123">모니터링할 서버의 토폴로지 가져오기</span><span class="sxs-lookup"><span data-stu-id="84006-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="84006-124">Redis, 수신기 서비스 및 웹 사이트를 모두 동일한 호스트 컴퓨터에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="84006-125">호스트 컴퓨터에 비즈니스용 Skype 서버가 설치되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="84006-126">수신기 호스트 컴퓨터 준비</span><span class="sxs-lookup"><span data-stu-id="84006-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="84006-127">호스트 시스템을 준비하려면 Redis 인 메모리 내 캐싱 시스템을 설치하고 컴퓨터에 유효한 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="84006-128">Redis 3.0의 최신 안정 빌드를 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="84006-129">Statistics Manager 버전 2.0은 Redis 3.2.100으로 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="84006-130">다음 사이트에서 Redis를 [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="84006-131">부호 없는 설치 관리자를 다운로드할 수 있습니다. [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="84006-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="84006-132">필요한 경우 인기 패키지 관리자 [Nuget](https://www.nuget.org/packages/Redis-64/) 및 [Choclatey를](https://chocolatey.org/packages/redis-64)통해 서명된 이진을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="84006-133">제공된 msi를 실행하고 프롬프트를 따르습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="84006-134">방화벽 규칙을 추가하기 위해 확인란을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="84006-135">수신기 서비스에 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="84006-136">신뢰할 수 있는 인증 기관에서 서명한 인증서가 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="84006-137">테스트 목적으로 자체 서명된 인증서를 사용하려는 경우(예: 자체 서명된 인증서 [만들기](deploy.md#BKMK_SelfCert)참조).</span><span class="sxs-lookup"><span data-stu-id="84006-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="84006-138">에이전트는 체인 확인 대신 인증서 지문 확인을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="84006-139">자체 서명된 인증서를 사용할 수 있기 때문에 전체 인증서 유효성 검사를 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="84006-140">수신기 서비스 설치</span><span class="sxs-lookup"><span data-stu-id="84006-140">Install the Listener service</span></span>

<span data-ttu-id="84006-141">수신기 서비스를 실행하고 다음을 지정하여 StatsManPerfAgentListener.msi 수신기 서비스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="84006-142">사용권 계약을 검토하고 동의하는 경우 사용권 계약에 동의한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84006-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="84006-143">다음 페이지에서 다음 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="84006-144">**서비스 암호:** 원격 에이전트가 수신기 서비스에 인증하는 데 사용하는 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="84006-145">**서비스 포트:** 수신기에서 에이전트와 통신하는 데 사용할 HTTPS 포트 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="84006-146">설치하는 동안 이 포트는 로컬 방화벽을 통해 허용됩니다. URL ACL이 만들어지며 SSL 인증이 이 포트에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="84006-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="84006-147">기본값은 8443입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="84006-148">**인증서 지문:** 수신기에서 HTTPS 프로토콜을 암호화하는 데 사용할 인증서 지문입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="84006-149">네트워크 서비스에는 개인 키에 대한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="84006-150">선택... **단추를** 클릭하여 지문을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="84006-151">인증서 관리자 또는 다음 PowerShell 명령을 사용하여 인증서 지문을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - <span data-ttu-id="84006-152">**Dir 설치:** 이 디렉터리는 이진을 설치할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="84006-153">찾아보기 단추를 사용하여 기본값에서 변경할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="84006-154">**AppData Dir:** Logs 폴더 및 기타 데이터가 저장되는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="84006-155">기본값에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-155">You may change it from the default.</span></span> <span data-ttu-id="84006-156">제거 시 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="84006-157">**설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-157">Click **Install**.</span></span>
    
<span data-ttu-id="84006-158">설치의 유효성을 검사하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="84006-159">브라우저를 열고 https://localhost: \<service-port\> /healthcheck/</span><span class="sxs-lookup"><span data-stu-id="84006-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="84006-160">기본적으로 서비스 포트는 8443입니다(다른 포트를 지정하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="84006-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="84006-161">수신기에서 제대로 설치되었는지 확인하려면 다음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="84006-162">상태 확인 페이지가 표시된 경우 수신기 설치가 성공한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="84006-163">KnownServerCount가 1 이상이면 Redis에 대한 연결이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="84006-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="84006-164">몇 분 정도 기다렸다가 하나 이상의 에이전트가 설치된 후 ValuesWritten 카운터가 증분하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="84006-165">웹 사이트 설치</span><span class="sxs-lookup"><span data-stu-id="84006-165">Install the Website</span></span>

<span data-ttu-id="84006-166">웹 사이트를 실행하고(비즈니스용 Skype StatsManWebSite.msi 통계 [관리자(64비트) 포함)를](https://www.microsoft.com/en-in/download/details.aspx?id=57518)실행하고 다음을 지정하여 호스트 Real-Time 컴퓨터에 웹 사이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="84006-167">사용권 계약을 검토하고 동의하는 경우 사용권 계약에 동의한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84006-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="84006-168">다음 페이지에서 다음 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="84006-169">**서비스 포트:** 웹 사이트에서 수신할 포트 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="84006-170">나중에 IIS 관리자 바인딩을 사용하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="84006-171">설치하는 동안 이 포트는 로컬 방화벽을 통해 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84006-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="84006-172">**Dir 설치:** 이 디렉터리는 이진을 설치할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="84006-173">찾아보기 단추를 사용하여 기본값에서 변경할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="84006-174">**AppData Dir:** Logs 폴더 및 기타 데이터가 저장되는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="84006-175">기본값에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-175">You may change it from the default.</span></span> <span data-ttu-id="84006-176">제거 시 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="84006-177">**설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-177">Click **Install**.</span></span>
    
<span data-ttu-id="84006-178">웹 사이트를 보고 브라우저를 열고 http://localhost 다음으로 이동합니다. ,webport \> /.</span><span class="sxs-lookup"><span data-stu-id="84006-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="84006-179">상태 정보만 보기 위해 브라우저를 열고 http://localhost: \<webport\> /healthcheck/로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="84006-180">기본적으로 웹 포트 번호는 8080입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="84006-181">IIS 관리자를 사용하여 웹 사이트의 포트 바인딩을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="84006-182">웹 설치 관리자에서 StatsManWebSiteUsers라는 로컬 보안 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="84006-183">이 보안 그룹에 계정을 추가하여 웹 사이트에 대한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="84006-184">에이전트 설치</span><span class="sxs-lookup"><span data-stu-id="84006-184">Install the Agents</span></span>

<span data-ttu-id="84006-185">다음을 지정하여 모니터링할 각 비즈니스용 Skype 서버에 StatsManPerfAgent.msi 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="84006-186">사용권 계약을 검토하고 동의하는 경우 사용권 계약에 동의한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84006-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="84006-187">다음 페이지에서 다음 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="84006-188">**서비스 암호:** 원격 에이전트가 수신기 서비스에 인증하는 데 사용할 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="84006-189">**서비스 URI:** 수신기 위치는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="84006-190">형식을 사용해야 https://name:port 합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="84006-191">NETBIOS 이름 또는 FQDN을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="84006-192">수신기 서비스에서 인증서의 주체  또는  주체 대체 이름으로도 지정된 이름을 사용할 수 있지만 이 이름은 필수 사항이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="84006-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="84006-193">**서비스 지문:** 수신기에서 사용하는 SSL 인증서의 지문입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="84006-194">에이전트는 이 지문을 사용하여 수신기 인증을 합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="84006-195">자체 서명된 인증서를 사용할 수 있기 때문에 전체 인증서 유효성 검사를 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="84006-196">**Dir 설치:** 이 디렉터리는 이진을 설치할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="84006-197">찾아보기 단추를 사용하여 기본값에서 변경할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="84006-198">**AppData Dir:** 이 디렉터리는 Logs 폴더 및 암호화된 password.txt 저장할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="84006-199">기본값에서 변경해주신 덕분에 감사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-199">You may thanks change it from the default.</span></span> <span data-ttu-id="84006-200">제거 시 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="84006-201">**설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-201">Click **Install**.</span></span>
    
<span data-ttu-id="84006-202">많은 컴퓨터에 에이전트를 설치하는 경우 무인 모드에서 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="84006-203">예시:</span><span class="sxs-lookup"><span data-stu-id="84006-203">For example:</span></span> 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="84006-204">토폴로지 가져오기</span><span class="sxs-lookup"><span data-stu-id="84006-204">Import the topology</span></span>
<span data-ttu-id="84006-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="84006-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="84006-206">Statistics Manager를 설치하고 실행한 후 통계 관리자가 각 서버의 사이트, 풀 및 역할을 알 수 있도록 비즈니스용 Skype 서버 토폴로지로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="84006-207">비즈니스용 Skype 서버 토폴로지 가져오기 위해 [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet을 사용하여 조직에서 사용 중인 각 풀에 대한 정보를 검색한 다음 이 정보를 통계 관리자로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="84006-208">비즈니스용 Skype 서버 토폴로지 가져오기에는 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="84006-209">비즈니스용 Skype 서버 PowerShell cmdlet이 있는 호스트:</span><span class="sxs-lookup"><span data-stu-id="84006-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="84006-210">a.</span><span class="sxs-lookup"><span data-stu-id="84006-210">a.</span></span> <span data-ttu-id="84006-211">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="84006-212">b.</span><span class="sxs-lookup"><span data-stu-id="84006-212">b.</span></span> <span data-ttu-id="84006-213">"mypoolinfo.xml" 파일을 수신기 실행 서버에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="84006-214">수신기 실행 호스트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="84006-215">a.</span><span class="sxs-lookup"><span data-stu-id="84006-215">a.</span></span> <span data-ttu-id="84006-216">PowerShell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="84006-217">b.</span><span class="sxs-lookup"><span data-stu-id="84006-217">b.</span></span> <span data-ttu-id="84006-218">수신기 설치 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="84006-219">기본값은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-219">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="84006-220">추가 및 업데이트되는 서버를 확인하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="84006-221">다음 명령을 사용하면 모든 옵션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-221">The following command enables you to view all options:</span></span>
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="84006-222">현재 가져온 서버 정보를 확인한 후 다음 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-222">To see your currently imported server information, run the following script:</span></span> 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="84006-223">비즈니스용 Skype 서버 토폴로지(예: Exchange Server)에 없는 서버를 모니터링할 경우 수신기 실행 호스트에서 단일 서버 가져오기 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="84006-224">단일 서버 가져오기 작업을 수행하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="84006-225">수신기 설치 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="84006-226">기본값은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-226">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="84006-227">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-227">Run the following command:</span></span>
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="84006-228">배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="84006-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="84006-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="84006-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="84006-230">에이전트를 시작하지 못하면 다음을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="84006-231">에이전트가 통계 관리자에 등록되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="84006-231">Is the agent registered in Statistics Manager?</span></span>
    
    1. <span data-ttu-id="84006-232">토폴로지 가져오기 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="84006-233">[토폴로지 가져오기](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="84006-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
        
    2. <span data-ttu-id="84006-234">에이전트가 토폴로지에 나열되지 않은 서버(예: SQL AlwaysOn 클러스터의 노드)에 있는 경우 토폴로지 가져오기 지침에 따라 에이전트를 수동으로 [추가해야 합니다.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="84006-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="84006-235">에이전트가 수신기에 연락할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="84006-235">Can the Agent contact the Listener?</span></span>
    
    1. <span data-ttu-id="84006-236">수신기 서비스가 실행되고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="84006-236">Make sure the Listener service is running.</span></span> 
        
        <span data-ttu-id="84006-237">실행되고 있지 않은 경우 Redis가 실행되고 있는지 확인한 다음 수신기 다시 시작을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
        
    2. <span data-ttu-id="84006-238">수신기 서비스에 포트가 열려 있는지, 에이전트 컴퓨터가 포트와 통신할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="84006-239">통계 관리자가 데이터를 수집하는지 확인하기 위해 다음과 같이 CSV 파일을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="84006-240">다음 명령은 카운터 저장소 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-240">The following command retrieves the counter storage names:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="84006-241">다음 명령은 지정된 카운터의 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="84006-242">응용 프로그램 이벤트 로그에 표시될 수 있는 모든 이벤트에 대한 자세한 내용은 비즈니스용 Skype 서버 통계 관리자 문제 [해결을 참조하세요.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="84006-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="84006-243">자체 서명된 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="84006-243">Create a self-signed certificate</span></span>
<span data-ttu-id="84006-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="84006-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="84006-245">신뢰할 수 있는 인증 기관에서 서명한 인증서를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="84006-246">그러나 테스트 목적으로 자체 서명된 인증서를 사용하려는 경우 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="84006-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="84006-247">관리자로 로그온한 동안 PowerShell 콘솔에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="84006-248">를  `certlm.msc` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="84006-249">그러면 로컬 컴퓨터의 인증서 관리자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="84006-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="84006-250">개인 **인증서로** 이동한 다음 **인증서를 여는 중입니다.**</span><span class="sxs-lookup"><span data-stu-id="84006-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="84006-251">**StatsManListener - 모든 작업 - 개인 키 \> \> 관리...**</span><span class="sxs-lookup"><span data-stu-id="84006-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="84006-252">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="84006-253">선택할 개체 **이름** 입력 상자에 Network Service를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="84006-254">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="84006-255">모든 **제어 아래에서** 허용 확인란을  선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84006-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="84006-256">읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="84006-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="84006-257">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84006-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="84006-258">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="84006-258">For more information</span></span>
<span data-ttu-id="84006-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="84006-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="84006-260">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84006-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="84006-261">비즈니스용 Skype 서버 통계 관리자에 대한 계획</span><span class="sxs-lookup"><span data-stu-id="84006-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="84006-262">비즈니스용 Skype 서버 통계 관리자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="84006-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="84006-263">[비즈니스용 Skype 서버 통계 관리자](troubleshoot.md) 문제 해결</span><span class="sxs-lookup"><span data-stu-id="84006-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
