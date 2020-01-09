---
title: 비즈니스용 Skype 서버 통계 관리자 문제 해결
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: '요약: 비즈니스용 Skype 서버용 통계 관리자 배포 문제를 해결 하려면이 항목을 읽으십시오.'
ms.openlocfilehash: 7d9ea061453998f2df01cd2ec31e792600697ee1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992515"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="a8d74-103">비즈니스용 Skype 서버 통계 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a8d74-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="a8d74-104">**요약:** 이 항목을 읽으면 비즈니스용 Skype 서버용 통계 관리자 배포 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="a8d74-105">이 항목에서는 응용 프로그램 이벤트 로그에 표시 될 수 있는 이벤트와 이벤트를 수정 하는 데 수행할 수 있는 적절 한 작업을 설명 하 여 통계 관리자 배포 문제를 해결 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="a8d74-106">이 항목에서는 다음 섹션을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="a8d74-107">에이전트 이벤트</span><span class="sxs-lookup"><span data-stu-id="a8d74-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="a8d74-108">리스너 이벤트</span><span class="sxs-lookup"><span data-stu-id="a8d74-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="a8d74-109">웹 사이트 문제</span><span class="sxs-lookup"><span data-stu-id="a8d74-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="a8d74-110">에이전트 이벤트</span><span class="sxs-lookup"><span data-stu-id="a8d74-110">Agent events</span></span>
<span data-ttu-id="a8d74-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="a8d74-111"></span></span>

- <span data-ttu-id="a8d74-112">**1000** -프로세서 limiter를 설정할 수 없음 (Job 개체) — 알 수 없는 이유</span><span class="sxs-lookup"><span data-stu-id="a8d74-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="a8d74-113">**1001** — 프로세스에 대 한 제한 처리가 허용 되지 않음 (이미 작업 개체 내부에 있을 수 있음)</span><span class="sxs-lookup"><span data-stu-id="a8d74-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="a8d74-114">에이전트는 Windows 작업 개체의 내부를 실행 하 여 메모리 공간을 자동으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="a8d74-115">에이전트가 시작 되지 않고 이러한 이벤트 항목이 이벤트 로그에 있으면 작업 개체를 서버에서 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="a8d74-116">이 문제를 해결 하려면 구성 파일에서 값을 변경 하 여 상한 메모리 제한을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="a8d74-117">"MaxProcessMemoryMB"를 검색 하 고 다음과 같이 값을 "0"으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```console
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="a8d74-118">이 변경이 이루어지면 에이전트는 일반적으로 100 MB의 메모리를 \< 사용 하지만 기본값 처럼 강제로 300 mb로 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="a8d74-119">이러한 변경이 이루어지면 에이전트에서 호스트 컴퓨터에 많은 양의 메모리를 소모 하지 않도록 메모리 사용을 면밀 하 게 모니터링 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="a8d74-120">**2000** -클라이언트 초기화 실패</span><span class="sxs-lookup"><span data-stu-id="a8d74-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="a8d74-121">**2001**-원본 IP에서 서비스에 대 한 연결을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="a8d74-122">에이전트가 수신기 컴퓨터에 연결할 수 없는 경우 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
1. <span data-ttu-id="a8d74-123">수신기 서비스가 수신기 컴퓨터에서 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="a8d74-124">그렇지 않으면 해당 서버에서 Redis가 실행 중인지 확인 한 다음 수신기 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
    
    <span data-ttu-id="a8d74-125">수신기 컴퓨터의 통계 관리자 이벤트 로그를 확인 하 여 통계 관리자 수신기 서비스 자체에 문제가 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
    
2. <span data-ttu-id="a8d74-126">Telnet 등의 연결 도구를 사용 하 여 에이전트 컴퓨터에서 올바른 포트의 수신기에 대 한 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
    
    <span data-ttu-id="a8d74-127">그렇지 않은 경우 수신기 컴퓨터가 연결 된 네트워크 종류 (비공개/공용/도메인)에 대 한 수신 방화벽 규칙이 수신기 컴퓨터에서 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="a8d74-128">수신기 컴퓨터가 도메인에 가입 되어 있지 않은 경우 네트워크는 공개로 나열 될 수 있으며,이 경우 통계 관리자와 함께 설치 된 방화벽 규칙이 기본적으로 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="a8d74-129">**4000** — 수신기에서 서버 정보를 다운로드 하지 못했습니다 (알 수 없는 이유).</span><span class="sxs-lookup"><span data-stu-id="a8d74-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="a8d74-130">**4001** -수신기 토폴로지에서 서버를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="a8d74-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="a8d74-131">이 오류는 서버가 수신기에 성공적으로 연결 중이지만 수신기 캐시의 토폴로지에 서버가 추가 되지 않은 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="a8d74-132">해결 옵션:</span><span class="sxs-lookup"><span data-stu-id="a8d74-132">Resolution options:</span></span>
    
  - <span data-ttu-id="a8d74-133">토폴로지 가져오기에 대 한 지침을 따랐는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="a8d74-134">[토폴로지 가져오기를](deploy.md#BKMK_ImportTopology)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8d74-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="a8d74-135">에이전트가 토폴로지에 나열 되지 않은 서버 (예: SQL AlwaysOn 클러스터의 노드)에 있는 경우 [토폴로지 가져오기](deploy.md#BKMK_ImportTopology)의 지침에 따라 에이전트를 수동으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="a8d74-136">**4002** -잘못 된 수신기 암호</span><span class="sxs-lookup"><span data-stu-id="a8d74-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="a8d74-137">에이전트가 사용 하려고 하는 암호화 된 암호가 수신기 자체의 서비스 암호와 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="a8d74-138">에이전트를 제거 하 고 올바른 서비스 암호를 사용 하 여 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="a8d74-139">**4003** -인증서 지문이 일치 하지 않음</span><span class="sxs-lookup"><span data-stu-id="a8d74-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="a8d74-140">설치할 때 에이전트에 주어진 인증서 지문이 수신기가 현재 사용 중인 인증서의 지문과 일치 하지 않으므로 연결이 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="a8d74-141">에이전트를 제거 하 고 올바른 인증서 지문을 사용 하 여 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="a8d74-142">**4004** — 잘못 된 응답 또는 HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="a8d74-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="a8d74-143">수신기가 예상 상태로 응답 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="a8d74-144">연결이 프록시 된 경우 프록시 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="a8d74-145">수신기 컴퓨터의 StatsMan 로그에 해당 구성과 관련 된 문제가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="a8d74-146">**4005** -XML을 역직렬화 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="a8d74-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="a8d74-147">수신기 서버의 서버 정보가 손상 되었거나 에이전트와 수신기 컴퓨터 간에 버전이 일치 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="a8d74-148">버전이 일치 하는지 확인 하 고 수신기 이벤트 로그에서 문제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="a8d74-149">리스너 이벤트</span><span class="sxs-lookup"><span data-stu-id="a8d74-149">Listener events</span></span>
<span data-ttu-id="a8d74-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="a8d74-150"></span></span>

- <span data-ttu-id="a8d74-151">**1만** -시작 실패 알 수 없는 이유 (이는 복구할 수 없으며 서비스가 중지 되거나 결과적으로 중단 됨)</span><span class="sxs-lookup"><span data-stu-id="a8d74-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="a8d74-152">**10001** -구성 문제</span><span class="sxs-lookup"><span data-stu-id="a8d74-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="a8d74-153">일반적으로이 오류는 [listener_install_location] \PerfAgentListener.exe.config 파일을 직접 수정 하 여 응용 프로그램에서 읽을 수 없는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="a8d74-154">**10002** -HTTP 수신기 초기화 오류</span><span class="sxs-lookup"><span data-stu-id="a8d74-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="a8d74-155">이 이벤트는 일반적으로 URL ACL이 설치 중 올바르게 설정 되지 않았거나 SSL 인증서가 유효 하지 않은 경우에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="a8d74-156">구성의 인증서가 유효한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="a8d74-157">인 경우 [통계 관리자 배포](deploy.md#BKMK_Deploy)의 지침에 따라 수신기를 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="a8d74-158">**10003** — Redis 오류</span><span class="sxs-lookup"><span data-stu-id="a8d74-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="a8d74-159">**10004** — 인프라 오류 캐싱</span><span class="sxs-lookup"><span data-stu-id="a8d74-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="a8d74-160">**10007** -설정 (redis에 저장)</span><span class="sxs-lookup"><span data-stu-id="a8d74-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="a8d74-161">수신기가 Redis에 연결할 수 없거나 캐시에서 올바른 형식의 데이터를 검색 하는 것을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="a8d74-162">Redis 서비스가 시작 되어 서버에서 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="a8d74-163">**10005** -서버 정보 검색/구문 분석</span><span class="sxs-lookup"><span data-stu-id="a8d74-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="a8d74-164">Redis cache의 토폴로지 정보가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="a8d74-165">먼저 Redis 및 수신기 다시 시작을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="a8d74-166">오류가 계속 되 면 토폴로지 [가져오기를](deploy.md#BKMK_ImportTopology) 참조 하 여 토폴로지 데이터를 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="a8d74-167">**10100** — Redis PING 작동 중지</span><span class="sxs-lookup"><span data-stu-id="a8d74-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="a8d74-168">**10101** — Redis PING 계속 중단 (매 60 초)</span><span class="sxs-lookup"><span data-stu-id="a8d74-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="a8d74-169">**30100** — Redis PING 작동 중지 복원 됨</span><span class="sxs-lookup"><span data-stu-id="a8d74-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="a8d74-170">이는 수신기가 Redis에 연결할 수 없을 때 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="a8d74-171">Redis가 시작 되 고 수신기와 Redis 간의 네트워크 연결을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="a8d74-172">**10200** -Redis 쓰기 중단</span><span class="sxs-lookup"><span data-stu-id="a8d74-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="a8d74-173">**10201** -Redis 쓰기 중단 계속 (60 초 마다)</span><span class="sxs-lookup"><span data-stu-id="a8d74-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="a8d74-174">**30100** -Redis 쓰기 중단이 해결 됨</span><span class="sxs-lookup"><span data-stu-id="a8d74-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="a8d74-175">이는 수신기가 Redis cache에 쓸 수 없을 때 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="a8d74-176">Redis가 시작 되 고 수신기와 Redis 간의 네트워크 연결을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="a8d74-177">**3만** -성공적으로 시작 됨</span><span class="sxs-lookup"><span data-stu-id="a8d74-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="a8d74-178">수신기가 시작 될 때마다 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="a8d74-179">**22000** -통계 관리자 에이전트의 초기화에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="a8d74-180">**23000** — EventLogQueryManager의 초기화 성공 (첫 번 또는 실패 후)</span><span class="sxs-lookup"><span data-stu-id="a8d74-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="a8d74-181">**24000** — serverinfo의 초기화 성공 (첫 번 또는 실패 후)</span><span class="sxs-lookup"><span data-stu-id="a8d74-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="a8d74-182">**25000** — post 실패 후 수신기가 다시 온라인 상태가 되는 경우 (또는 첫 번째 성공한 게시물)</span><span class="sxs-lookup"><span data-stu-id="a8d74-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="a8d74-183">**5000** -데이터 게시를 위해 수신기를 오프 라인으로 시작</span><span class="sxs-lookup"><span data-stu-id="a8d74-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="a8d74-184">**5001** — 오랜 기간 동안 수신기가 계속 오프 라인 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="a8d74-185">이러한 이벤트는 모니터링/경고/지우기 문제에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="a8d74-186">웹 사이트 문제</span><span class="sxs-lookup"><span data-stu-id="a8d74-186">Website issues</span></span>
<span data-ttu-id="a8d74-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="a8d74-187"></span></span>

- <span data-ttu-id="a8d74-188">Chrome에서 반복 되는 로그인 메시지-버전 1.1에서 해결 된 버그입니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="a8d74-189">Chrome 브라우저에서 반복 되는 로그인 메시지가 표시 되는 경우에는 최신 버전의 통계 관리자로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="a8d74-190">실행 중인 웹 사이트 버전을 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="a8d74-191">파일 탐색기에서 열기 (기본 디렉터리)</span><span class="sxs-lookup"><span data-stu-id="a8d74-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="a8d74-192">StatsManHubWebSite를 마우스 오른쪽 단추로 클릭 하 고 속성을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="a8d74-193">KHI 가로 보기 또는 카운터 세부 정보 보기에서 컴퓨터를 찾을 수 없는 경우 사이트 및 풀의 구성원 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="a8d74-194">그렇지 않은 경우에는 해당 보기에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="a8d74-195">토폴로지에서 서버의 사이트 및 풀을 정의 하는 방법에 대 한 자세한 내용은 [토폴로지 가져오기를](deploy.md#BKMK_ImportTopology)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8d74-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="a8d74-196">제품 버전이 설명 세부 정보에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8d74-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="a8d74-197">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="a8d74-197">For more information</span></span>
<span data-ttu-id="a8d74-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="a8d74-198"></span></span>

<span data-ttu-id="a8d74-199">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8d74-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="a8d74-200">비즈니스용 Skype 서버 통계 관리자에 대한 계획</span><span class="sxs-lookup"><span data-stu-id="a8d74-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="a8d74-201">비즈니스용 Skype 서버 통계 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="a8d74-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="a8d74-202">비즈니스용 Skype 서버 통계 관리자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="a8d74-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
