---
title: 비즈니스용 Skype 서버 통계 관리자 문제 해결
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 통계 관리자 배포 문제를 해결합니다.'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821778"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="0bbae-103">비즈니스용 Skype 서버 통계 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0bbae-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="0bbae-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 통계 관리자 배포 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="0bbae-105">이 항목에서는 응용 프로그램 이벤트 로그에 표시될 수 있는 이벤트와 이벤트를 해결하기 위해 수행할 수 있는 적절한 작업을 설명하여 Statistics Manager 배포 문제를 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="0bbae-106">이 항목에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="0bbae-107">에이전트 이벤트</span><span class="sxs-lookup"><span data-stu-id="0bbae-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="0bbae-108">수신기 이벤트</span><span class="sxs-lookup"><span data-stu-id="0bbae-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="0bbae-109">웹 사이트 문제</span><span class="sxs-lookup"><span data-stu-id="0bbae-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="0bbae-110">에이전트 이벤트</span><span class="sxs-lookup"><span data-stu-id="0bbae-110">Agent events</span></span>
<span data-ttu-id="0bbae-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="0bbae-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="0bbae-112">**1000** — 프로세서 제한기(작업 개체)를 설정하지 못했습니다. 알 수 없는 이유</span><span class="sxs-lookup"><span data-stu-id="0bbae-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="0bbae-113">**1001** — 프로세스에서 프로세스 제한이 허용되지 않습니다(이미 작업 개체 내부에 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="0bbae-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="0bbae-114">에이전트는 Windows 작업 개체 내에서 실행되어 메모리 사용 공간은 자동으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="0bbae-115">에이전트가 시작되지 않는 경우 이러한 이벤트 항목이 이벤트 로그에 있는 경우 서버에서 Job 개체를 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="0bbae-116">이를 해결하기 위해 구성 파일에서 값을 변경하여 상한 메모리 제한을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="0bbae-117">"MaxProcessMemoryMB"를 검색하고 표시된 값을 "0"으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="0bbae-118">이 변경이 진행되는 경우 에이전트는 일반적으로 100MB의 메모리를 사용하나 기본적으로 \< 300MB로 강제로 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="0bbae-119">이러한 변경이 이행되는 경우 에이전트가 호스트 컴퓨터의 많은 양의 메모리를 소비하지 않도록 메모리 사용량을 면밀하게 모니터링하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="0bbae-120">**2000** — 클라이언트 초기화 실패</span><span class="sxs-lookup"><span data-stu-id="0bbae-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="0bbae-121">**2001**— 원본 IP의 서비스에 연결되지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="0bbae-122">에이전트가 수신기 컴퓨터에 연결할 수 없는 경우 다음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
    1. <span data-ttu-id="0bbae-123">수신기 컴퓨터에서 수신기 서비스가 실행 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="0bbae-124">그렇지 않은 경우 Redis가 해당 서버에서 실행 중인지 확인한 다음 수신기 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
        
        <span data-ttu-id="0bbae-125">수신기 컴퓨터에서 Statistics Manager 이벤트 로그를 확인하여 Statistics Manager 수신기 서비스 자체에 문제가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
        
    2. <span data-ttu-id="0bbae-126">텔넷과 같은 연결 도구를 사용하여 에이전트 컴퓨터에서 올바른 포트의 수신기 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
        
        <span data-ttu-id="0bbae-127">그렇지 않은 경우 수신기 컴퓨터가 연결된 네트워크 유형(개인/공용/도메인)에 대해 수신기 컴퓨터에서 들어오는 방화벽 규칙을 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="0bbae-128">수신기 컴퓨터가 도메인에 가입되어 있지 않은 경우 네트워크가 공용으로 나열될 수 있으며, 이 경우 Statistics Manager와 함께 설치된 방화벽 규칙은 기본적으로 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="0bbae-129">**4000** — 수신기에서 서버 정보 다운로드 실패(알 수 없는 이유)</span><span class="sxs-lookup"><span data-stu-id="0bbae-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="0bbae-130">**4001** — 수신기 토폴로지에서 서버를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="0bbae-131">이 오류는 서버가 수신기에 성공적으로 연결되지만 서버가 수신기 캐시의 토폴로지에 추가되지 않은 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="0bbae-132">해결 옵션:</span><span class="sxs-lookup"><span data-stu-id="0bbae-132">Resolution options:</span></span>
    
  - <span data-ttu-id="0bbae-133">토폴로지 가져오기 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="0bbae-134">[토폴로지 가져오기](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="0bbae-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="0bbae-135">에이전트가 토폴로지에 나열되지 않은 서버(예: SQL AlwaysOn 클러스터의 노드)에 있는 경우 토폴로지 가져오기 지침에 따라 에이전트를 수동으로 [추가해야 합니다.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="0bbae-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="0bbae-136">**4002** — 잘못된 수신기 암호</span><span class="sxs-lookup"><span data-stu-id="0bbae-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="0bbae-137">에이전트가 사용하려는 암호화된 암호가 수신기 자체의 서비스 암호와 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="0bbae-138">에이전트를 제거하고 올바른 서비스 암호를 사용하여 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="0bbae-139">**4003** — 인증서 지문 불일치</span><span class="sxs-lookup"><span data-stu-id="0bbae-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="0bbae-140">설치 시 에이전트에게 제공된 인증서 지문이 수신기에서 현재 사용 중인 인증서의 지문과 일치하지 않습니다. 따라서 연결이 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="0bbae-141">에이전트를 제거하고 올바른 인증서 지문을 사용하여 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="0bbae-142">**4004** — 잘못된 응답 또는 HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="0bbae-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="0bbae-143">수신기에서 예상된 상태로 응답하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="0bbae-144">연결이 프록시된 경우 프록시 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="0bbae-145">수신기 컴퓨터의 StatsMan 로그에서 구성 관련 문제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="0bbae-146">**4005** — XML을 직렬화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="0bbae-147">수신기 서버의 서버 정보가 손상되거나 에이전트와 수신기 컴퓨터 간에 버전이 불일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="0bbae-148">버전이 일치하는지 확인하고 수신기 이벤트 로그에서 문제를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="0bbae-149">수신기 이벤트</span><span class="sxs-lookup"><span data-stu-id="0bbae-149">Listener events</span></span>
<span data-ttu-id="0bbae-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="0bbae-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="0bbae-151">**10000** — 시작 실패 알 수 없는 이유(복구할 수 없음 및 그 결과 서비스가 중지/충돌)</span><span class="sxs-lookup"><span data-stu-id="0bbae-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="0bbae-152">**10001** — 구성 문제</span><span class="sxs-lookup"><span data-stu-id="0bbae-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="0bbae-153">일반적으로 [listener_install_location]\PerfAgentListener.exe.config 파일을 수정하여 응용 프로그램에서 읽을 수 없는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="0bbae-154">**10002** — HTTP 수신기 초기화 오류</span><span class="sxs-lookup"><span data-stu-id="0bbae-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="0bbae-155">이 이벤트는 일반적으로 설치 중에 URL ACL이 제대로 설정되지 않은 경우 또는 SSL Cert가 유효하지 않은 경우 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="0bbae-156">구성의 인증서가 올바른지 확인</span><span class="sxs-lookup"><span data-stu-id="0bbae-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="0bbae-157">이 경우 통계 관리자 배포의 지침에 따라 수신기 [다시 설치합니다.](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="0bbae-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="0bbae-158">**10003** — 재배포 실패</span><span class="sxs-lookup"><span data-stu-id="0bbae-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="0bbae-159">**10004** — 인프라 오류 캐싱</span><span class="sxs-lookup"><span data-stu-id="0bbae-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="0bbae-160">**10007** - 설정(재배포에 저장)</span><span class="sxs-lookup"><span data-stu-id="0bbae-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="0bbae-161">수신기에서 Redis에 연락하거나 캐시에서 잘 형성된 데이터를 검색할 수 없는 경우 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="0bbae-162">Redis 서비스가 서버에서 제대로 시작 및 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="0bbae-163">**10005** — 서버 정보 검색/구문 분석</span><span class="sxs-lookup"><span data-stu-id="0bbae-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="0bbae-164">Redis 캐시의 토폴로지 정보가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="0bbae-165">먼저 Redis 및 수신기 다시 시작을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="0bbae-166">오류가 계속되면 [토폴로지](deploy.md#BKMK_ImportTopology) 가져오기에서 토폴로지 데이터를 다시 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="0bbae-167">**10100** — Redis PING 중지</span><span class="sxs-lookup"><span data-stu-id="0bbae-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="0bbae-168">**10101** — Redis PING 계속 중지(60초마다)</span><span class="sxs-lookup"><span data-stu-id="0bbae-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="0bbae-169">**30100** — Redis PING 중지 복원</span><span class="sxs-lookup"><span data-stu-id="0bbae-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="0bbae-170">수신기에서 Redis에 연결할 수 없는 경우 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="0bbae-171">Redis가 시작된 후 수신기 및 Redis 간의 네트워크 연결을 사용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="0bbae-172">**10200** — Redis Write outage</span><span class="sxs-lookup"><span data-stu-id="0bbae-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="0bbae-173">**10201** — Redis 쓰기가 계속되었습니다(60초마다).</span><span class="sxs-lookup"><span data-stu-id="0bbae-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="0bbae-174">**30100** — Redis 쓰기가 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="0bbae-175">수신기에서 Redis 캐시에 쓸 수 없는 경우 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="0bbae-176">Redis가 시작된 후 수신기 및 Redis 간의 네트워크 연결을 사용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="0bbae-177">**30000** — 성공적으로 시작</span><span class="sxs-lookup"><span data-stu-id="0bbae-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="0bbae-178">수신기 시작 시 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="0bbae-179">**22000** — 통계 관리자 에이전트의 초기화가 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="0bbae-180">**23000** — EventLogQueryManager 초기화 성공(처음 또는 실패한 후)</span><span class="sxs-lookup"><span data-stu-id="0bbae-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="0bbae-181">**24000** — serverinfo 초기화 성공(처음 또는 실패한 후)</span><span class="sxs-lookup"><span data-stu-id="0bbae-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="0bbae-182">**25000** — 게시에 실패한 후(또는 처음 성공한 게시물) 리스너가 온라인으로 다시 돌아오기</span><span class="sxs-lookup"><span data-stu-id="0bbae-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="0bbae-183">**5000** — 데이터 게시를 위한 오프라인으로 수신기 시작</span><span class="sxs-lookup"><span data-stu-id="0bbae-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="0bbae-184">**5001** — 수신기 사용 기간이 연장된 동안 계속 오프라인 상태</span><span class="sxs-lookup"><span data-stu-id="0bbae-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="0bbae-185">이러한 이벤트는 문제를 모니터링/경고/지우는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="0bbae-186">웹 사이트 문제</span><span class="sxs-lookup"><span data-stu-id="0bbae-186">Website issues</span></span>
<span data-ttu-id="0bbae-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="0bbae-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="0bbae-188">Chrome의 반복적인 로그인 프롬프트 - 버전 1.1에서 해결된 버그입니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="0bbae-189">Chrome 브라우저에 반복되는 로그인 프롬프트가 표시될 경우 최신 버전의 통계 관리자로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="0bbae-190">실행 중인 웹 사이트의 버전을 확인:</span><span class="sxs-lookup"><span data-stu-id="0bbae-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="0bbae-191">파일 탐색기에서 열기(기본 디렉터리)</span><span class="sxs-lookup"><span data-stu-id="0bbae-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="0bbae-192">마우스 오른쪽 단추로 StatsManHubWebSite.dll 속성을 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="0bbae-193">KHI 가로 보기 또는 카운터 세부 정보 보기에서 컴퓨터를 찾을 수 없는 경우 해당 컴퓨터가 사이트 및 풀의 구성원인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="0bbae-194">그렇지 않은 경우 해당 보기에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="0bbae-195">토폴로지에서 서버의 사이트 및 풀을 정의하는 데 대한 자세한 내용은 토폴로지 [가져오기를 참조하십시오.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="0bbae-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="0bbae-196">제품 버전이 설명 세부 정보에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbae-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="0bbae-197">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="0bbae-197">For more information</span></span>
<span data-ttu-id="0bbae-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="0bbae-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="0bbae-199">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bbae-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="0bbae-200">비즈니스용 Skype 서버 통계 관리자에 대한 계획</span><span class="sxs-lookup"><span data-stu-id="0bbae-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="0bbae-201">비즈니스용 Skype 서버 통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="0bbae-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="0bbae-202">비즈니스용 Skype 서버 통계 관리자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="0bbae-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
