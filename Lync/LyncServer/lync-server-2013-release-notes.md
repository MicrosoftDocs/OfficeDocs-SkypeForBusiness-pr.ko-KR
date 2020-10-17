---
title: Lync Server 2013 릴리스 정보
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f98a19e81ebf52d97b4c6807dbb97dc8110b0f34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536565"
---
# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="9bcdc-102">Lync Server 2013 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="9bcdc-102">Release notes for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bcdc-103">_**마지막으로 수정 된 항목:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="9bcdc-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="9bcdc-104">Lync Server 2013 릴리스 정보에 오신 것을 환영 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="9bcdc-105">Lync Server 2013의 알려진 문제에 대 한 정보는이 파일을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="9bcdc-106">문서 정보</span><span class="sxs-lookup"><span data-stu-id="9bcdc-106">About this document</span></span>

<span data-ttu-id="9bcdc-107">이 문서에는 Lync Server 2013를 배포 하 고 사용 하기 전에 알아야 할 중요 한 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="9bcdc-108">Lync Server 2013에 대 한 자세한 내용은 [Microsoft Lync server 2013](microsoft-lync-server-2013.md) 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="9bcdc-109">이 문서에서 다루는 섹션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="9bcdc-110">Lync 2013 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9bcdc-110">Lync 2013 client</span></span>

  - <span data-ttu-id="9bcdc-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="9bcdc-111">Lync Server</span></span>

  - <span data-ttu-id="9bcdc-112">설치</span><span class="sxs-lookup"><span data-stu-id="9bcdc-112">Installation</span></span>

  - <span data-ttu-id="9bcdc-113">이동성</span><span class="sxs-lookup"><span data-stu-id="9bcdc-113">Mobility</span></span>

  - <span data-ttu-id="9bcdc-114">회의</span><span class="sxs-lookup"><span data-stu-id="9bcdc-114">Conferencing</span></span>

  - <span data-ttu-id="9bcdc-115">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="9bcdc-115">Enterprise Voice</span></span>

  - <span data-ttu-id="9bcdc-116">이들의</span><span class="sxs-lookup"><span data-stu-id="9bcdc-116">Presence</span></span>

  - <span data-ttu-id="9bcdc-117">응답 그룹 응용 프로그램 및 통화 대기 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9bcdc-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="9bcdc-118">Lync Server 제어판, 토폴로지 작성기 및 계획 도구</span><span class="sxs-lookup"><span data-stu-id="9bcdc-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="9bcdc-119">따른</span><span class="sxs-lookup"><span data-stu-id="9bcdc-119">Localization</span></span>

  - <span data-ttu-id="9bcdc-120">저작권법과</span><span class="sxs-lookup"><span data-stu-id="9bcdc-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="9bcdc-121">Lync 2013 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9bcdc-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="9bcdc-122">파일이 다른 응용 프로그램에서 열려 있는 경우 인스턴트 메시지에서 파일을 전송 하지 못한다</span><span class="sxs-lookup"><span data-stu-id="9bcdc-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="9bcdc-123">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-123">**Issue:**</span></span>

<span data-ttu-id="9bcdc-124">Word 문서와 같은 파일을 다른 Lync 사용자에 게 인스턴트 메시지에 포함 하 여 전송 하려고 하면 전송에 성공 하는 것으로 나타나지만 실제로 파일을 전송 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="9bcdc-125">파일 형식에 대 한 아이콘은 Lync 클라이언트에 표시 되지만 해당 수신자가 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="9bcdc-126">전송에 실패 했음을 알리는 오류 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="9bcdc-127">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-127">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-128">이 문제를 해결 하려면 인스턴트 메시지에서 파일을 전송 하기 전에 열려 있는 열린 파일 또는 응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="9bcdc-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="9bcdc-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="9bcdc-130">Lync Server 저장소 서비스 데이터 복제가 실패 하면 관리자가 오래 된 저장소 서비스 큐 항목에 대 한 성능 카운터를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="9bcdc-131">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-131">**Issue:**</span></span>

<span data-ttu-id="9bcdc-132">Lync Server 저장소 서비스는 복제에 Windows Fabric을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="9bcdc-133">기본 프런트 엔드 서버에서 데이터가 삭제 되었지만 보조 프런트 엔드 서버의 삭제가 실패 하는 경우 (예: 프런트 엔드 서버에서 예기치 않은 종료 또는 오류가 발생 한 경우에는 데이터를 "고아"로 유지할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="9bcdc-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="9bcdc-134">분리된 데이터로 인해 성능이 저하되고 드라이브 공간이 낭비될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="9bcdc-135">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-135">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-136">이 문제를 해결 하기 위해 이벤트 LYSS \_ db \_ 공간 \_ 사용 \_ 오류 (id = 32058) 및 lyss \_ db Space used \_ for \_ \_ CRITICAL (id = 32059)이 event log에 생성 되는 경우 관리자는 이름이 **lyss**인 **storage service API** 의 프런트 엔드 서버의 성능 카운터를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="9bcdc-137">이 성능 카운터의 값이 높은 경우 (예: 50000 보다 큰 경우) 관리자는 Lync Server 2013 Resource Kit에서 CleanuUpStorageServiceData.exe 도구를 실행 하 여 풀에서 분리 된 모든 데이터를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="9bcdc-138">도구에 대 한 자세한 내용은 Lync Server 2013 Resource Kit 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="9bcdc-139">서버 또는 풀에 대해 IP 주소 구성이 변경 될 때마다 Lync Server 서비스를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="9bcdc-140">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-140">**Issue:**</span></span>

<span data-ttu-id="9bcdc-141">IPv4에서 이중 스택으로 변경 하는 것과 같이 Lync Server 2013 배포에 대해 IP 주소 구성을 변경 하는 경우에는 모든 서버 구성 요소가 서비스를 다시 시작할 때까지 구성 변경을 선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="9bcdc-142">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-142">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-143">이 문제를 해결 하려면 배포에 대 한 IP 주소 구성을 변경한 후 Lync Server 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="9bcdc-144">이렇게 하려면 Lync Server 관리 셸에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="9bcdc-145">Lync Server 2013 관리 팩에서 전화 접속 회의 가상 트랜잭션 cmdlet을 더 이상 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="9bcdc-146">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-146">**Issue:**</span></span>

<span data-ttu-id="9bcdc-147">Lync Server 2013 관리 팩에서는 전화 접속 회의 가상 트랜잭션 cmdlet **test-csdialinconferencing** 를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="9bcdc-148">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-148">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-149">전화 접속 회의 가상 트랜잭션 cmdlet **Test-CsDialInConferencing**은 단지 기업에서 내부적으로 사용하도록 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="9bcdc-150">관리자는 문제 해결을 위해 Lync Server 관리 셸에서 cmdlet을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="9bcdc-151">필요한 경우 기업에서 내부적으로 이 cmdlet을 실행하기 위한 전용 관리 팩을 개발할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="9bcdc-152">로그 파일이 네트워크 공유로 복사 되는 동안 네트워크 트래픽이 중단 되는 경우 중앙 로깅 서비스가 중지 됨</span><span class="sxs-lookup"><span data-stu-id="9bcdc-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="9bcdc-153">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-153">**Issue:**</span></span>

<span data-ttu-id="9bcdc-154">네트워크 경로를 사용하도록 중앙 로깅 서비스를 구성한 경우(**Get-CsClsConfiguration** cmdlet의 CacheFileNetworkFolder 매개 변수 값이 올바른 UNC 경로임) 캐시된 로그 파일이 네트워크 공유로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="9bcdc-155">파일이 복사되는 동안 네트워크 트래픽이 중단될 경우 예외가 발생하여 중앙 로깅 서비스가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="9bcdc-156">이 서비스는 최대 세 번 자동으로 다시 시작되도록 구성되어 있습니다. 따라서 처음 세 번의 예외 발생 후에는 서비스가 복구됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="9bcdc-157">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-157">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-158">이 문제에 대한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-158">There is no workaround for this issue.</span></span> <span data-ttu-id="9bcdc-159">문제를 확인 하려면 "Lync Server 중앙화 된 로깅 서비스 에이전트" 서비스가 갑자기 종료 되는 경우를 기록 하는 "서비스 제어 관리자"에서 이벤트 ID 7031에 대 한 이벤트 로그를 모니터링 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="9bcdc-160">이 이벤트가 세 번 넘게 로깅될 경우 **Start-CsWindowService** cmdlet을 사용하여 서비스를 수동으로 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="9bcdc-161">저장소 서비스 큐 항목을 수동으로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="9bcdc-162">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-162">**Issue:**</span></span>

<span data-ttu-id="9bcdc-163">Lync Server 2013에서는 각 프런트 엔드 서버의 데이터베이스에 보관 된 메시지 및 CDR (통화 정보 기록)과 같은 회의 및 인스턴트 메시징에 대 한 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="9bcdc-164">데이터는 대상 위치로 배달 되기 전에 처리 되는 동안 데이터베이스에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="9bcdc-165">성능을 개선 하기 위해 Lync Server 2013는 장시간 동안 처리 되지 않은 로컬 데이터베이스에서 큐 항목을 주기적으로 내보낸 다음 파일 저장소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="9bcdc-166">파일 저장소를 사용할 수 없으면 각 프런트 엔드 서버에 항목이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="9bcdc-167">풀 장애 조치(failover) 시에도 데이터 손실을 방지하기 위한 동일한 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="9bcdc-168">내보내기 작업 중에 Lync Server 저장소 서비스는 이벤트 Id가 32075 인 이벤트 로그의 모든 단계를 (전체 플러시 작업 시작), 32076 (전체 플러시 완료), 32082 (유지 관리 수준 플러시 시작), 32083 (유지 관리 수준 플러시 완료), 32089 (데이터베이스 꽉 찰 때 플러시가 발생 함)을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="9bcdc-169">이 데이터는 처리 하 여 최종 대상 (SQL Server 또는 Exchange 서버)에 배달 하기 위해 시스템으로 다시 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="9bcdc-170">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-170">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-171">시스템으로 데이터를 가져오려면 관리자는 Lync Server Resource Kit의 ImportStorageServiceData 도구를 사용 하 여 시스템에 데이터를 다시 추가 하 여 처리 하 고 최종 대상으로 배달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="9bcdc-172">UseNormalizationRules의 기본값을 False로 변경 하면 주소록 웹 쿼리 검색이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="9bcdc-173">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-173">**Issue:**</span></span>

<span data-ttu-id="9bcdc-p112">UseNormalizationRules의 기본값을 False로 변경할 경우 주소록 웹 쿼리 검색이 실패합니다. 다시 말해서 기본값이 변경된 후에는 Lync Client 사용자가 Lync 주소록 웹 쿼리 검색을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p112">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail. After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="9bcdc-176">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-176">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-177">UseNormalizationRules의 기본값을 False로 설정 하 여 사용자가 Lync Server 2013 정규화 규칙을 적용 하지 않고 Active Directory 도메인 서비스에 정의 된 대로 전화 번호를 사용할 수 있도록 하려면 다음을 수행 하 여이 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="9bcdc-178">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9bcdc-179">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="9bcdc-180">배포에 Lync Server 2013 서버만 포함 되는 경우 전역 수준에서 다음 cmdlet을 실행 하 여 UseNormalizationRules 및 IgnoreGenericRules의 값을 True로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="9bcdc-181">배포에 Lync Server 2013 및 Lync Server 2010 또는 Office Communications Server 2007 r 2의 조합이 포함 된 경우 다음 cmdlet을 실행 하 여 토폴로지의 각 Lync Server 2013 pool에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="9bcdc-182">모든 풀에서 CMS 복제가 수행될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="9bcdc-183">배포의 전화 정규화 규칙 파일에 들어 있는 내용을 삭제하여 이 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="9bcdc-184">파일이 각 Lync Server 2013 풀의 파일 공유에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="9bcdc-185">파일이 없으면 "회사 \_ 전화 \_ 번호 \_ 정규화 \_Rules.txt" 라는 빈 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="9bcdc-186">모든 프런트 엔드 풀에서 새 파일을 읽을 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="9bcdc-187">배포의 각 Lync Server 2013 풀에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="9bcdc-188">각 Lync 2013 풀에 대해 하루에 한 번씩 주소록 서버 오류 이벤트 21054이 생성 됨</span><span class="sxs-lookup"><span data-stu-id="9bcdc-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="9bcdc-189">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-189">**Issue:**</span></span>

<span data-ttu-id="9bcdc-190">Lync Server 2013 주소록 서버는 매일 유지 관리를 수행 하는 동안 매일 오류 이벤트 21054를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="9bcdc-191">또한 업데이트에 성공 하면 관리자가 **update-csaddressbook** cmdlet을 실행할 때마다 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="9bcdc-192">그러나 업데이트가 완료 되 면이 오류 이벤트를 무시 해도 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="9bcdc-193">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-193">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-194">이 오류 이벤트가 발생할 경우 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="9bcdc-195">Cmdlet이 인덱싱되지 않았거나 중단 된 개체를 보고 하지 않는 경우 오류 이벤트 21054를 무시 해도 안전 하 게 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="9bcdc-196">또한 System Center Operations Manager에서 KHI(Key Health Indicator) "Address Book Users Correctly Indexed"(주소록 사용자가 올바르게 인덱싱되지 않음)를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="9bcdc-197">에 지 풀에 대 한 IPv6이 구성 된 경우 요청이 실패할 수 있음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="9bcdc-198">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-198">**Issue:**</span></span>

<span data-ttu-id="9bcdc-199">에지 풀에서 IPv6가 구성된 경우 에지 풀에 대한 일부 요청이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="9bcdc-200">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-200">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-201">이 문제를 해결하려면 IPv6를 사용하여 에지 풀을 구성하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="9bcdc-202">풀 장애 복구 (failback) 시 Invoke-cspoolfailback cmdlet이 실패할 수 있음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="9bcdc-203">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-203">**Issue:**</span></span>

<span data-ttu-id="9bcdc-204">풀을 장애 복구하려고 할 때 **invoke-csPoolFailback** cmdlet이 실패하며 "Failed to complete hydration process after repeated attempts."(여러 차례 시도했으나 하이드레이션 프로세스를 완료하지 못했습니다.)라는 오류 메시지가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="9bcdc-205">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-205">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-p115">이 문제를 해결하려면 이 cmdlet을 다시 실행하고 cmdlet이 성공할 때까지 기다립니다. 장애 조치 프로세스가 완료되려면 몇 분 정도 걸릴 수 있으며, 20,000명의 사용자가 있는 풀의 경우 최대 60분이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p115">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds. Note that the failback process can take several minutes to complete. It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="9bcdc-209">이미 설정 된 풀에 프런트 엔드 서버를 추가 하면 데이터 손실이 발생할 수 있음-Hybrid, 비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="9bcdc-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="9bcdc-210">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-210">**Issue:**</span></span>

<span data-ttu-id="9bcdc-211">풀에 프런트 엔드 서버가 두 개 이상 있고 프런트 엔드 서버 중 하나를 다시 시작 하거나 이전에 풀에 속하지 않은 새 프런트 엔드 서버를 추가 하는 환경에서이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="9bcdc-p116">데이터를 보관 중인 사용자는 풀에 대한 안정적인 데이터 보관 배포가 설정될 때까지 데이터 손실을 경험할 수 있습니다. 이러한 잠재적인 데이터 손실 기간은 개인 간 대화의 경우 최대 15분, 회의의 경우 최대 30분입니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p116">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool. This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="9bcdc-214">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-214">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-215">유지 관리를 수행 하는 경우 풀에서 프런트 엔드 서버를 하나씩 시작 하는 대신 풀을 다른 풀로 장애 조치 (failover) 한 다음 서버에서 유지 관리 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="9bcdc-216">또한 유지 관리 작업 중에 서비스를 사용할 수 없게 설정하고 유지 관리가 완료된 후에 다시 사용할 수 있게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="9bcdc-217">관리자는 Get-CsClientAccessLicense cmdlet을 사용 하 여 라이선스 사용자 수를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="9bcdc-218">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-218">**Issue:**</span></span>

<span data-ttu-id="9bcdc-219">관리자가 **Get-CsClientAccessLicense** cmdlet을 사용하여 정확한 클라이언트 라이선스 사용 현황을 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="9bcdc-220">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-220">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-221">서버 라이선스 유형을 확인 하려면 FDQNs **서비스** cmdlet을 실행 하 여 모든 데이터베이스의 fqdn (정규화 된 도메인 이름)을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="9bcdc-222">프런트 엔드 서버의 FQDN이 백 엔드 데이터베이스의 FQDN과 같으면 라이선스는 Standard edition 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="9bcdc-223">그렇지 않으면 라이선스가 Enterprise edition 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="9bcdc-224">클라이언트 라이선스 수를 정확 하 게 보고 하지 않음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="9bcdc-225">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-225">**Issue:**</span></span>

<span data-ttu-id="9bcdc-226">클라이언트 라이선스 수를 확인할 때 다음과 같은 상태를 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="9bcdc-227">**모바일 사용자의 라이선스 수가 부정확함**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="9bcdc-p119">라이선스 수는 장치 기반 사용자의 고유 IP 주소 수를 기준으로 합니다. 이 라이선스 수 계산에는 다음과 같은 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p119">The license count is based on the number of unique IP addresses for device-based users. The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="9bcdc-230">Lync 세션 중에 사용자의 IP 주소가 변경될 경우 라이선스 수가 실제보다 많이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="9bcdc-231">사용자가 데스크톱 클라이언트를 사용 하 여 두 개 이상의 위치에서 Lync Server에 연결할 때이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="9bcdc-232">사용자가 모바일 클라이언트를 사용하여 연결할 경우 장치의 IP 주소를 확인할 수 없기 때문에 라이선스 수가 실제보다 적게 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="9bcdc-233">**PSTN(공중 전화망)에서 Lync 클라이언트로 전화하거나, Lync 클라이언트에서 PSTN 회선으로 전화하거나, Lync 전화를 PSTN 회선으로 착신 전환할 경우 라이선스가 두 번 계산됨**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="9bcdc-p121">다음 시나리오에서는 사용되는 라이선스 수를 확인하기 위해 전화 번호와 Lync 사용자가 모두 계산되기 때문에 하나가 아닌 두 개의 추가 라이선스가 계산됩니다. 정확한 라이선스 데이터를 얻으려면 전화 번호로 인해 계산되는 라이선스를 수동으로 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p121">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used. To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="9bcdc-236">PSTN에서 Lync로 전화</span><span class="sxs-lookup"><span data-stu-id="9bcdc-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="9bcdc-237">Lync에서 PSTN 회선으로 전화</span><span class="sxs-lookup"><span data-stu-id="9bcdc-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="9bcdc-p122">PSTN에서 Lync로 전화하고 Lync에서 해당 전화를 PSTN 회선으로 착신 전환. PSTN 회선 중 하나가 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p122">A PSTN call to Lync, and then Lync forwards the call to a PSTN line. One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="9bcdc-240">**로그온된 Lync 전화에 대해서는 라이선스가 계산되지 않음**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="9bcdc-241">사용자가 Lync 인증 전화를 사용하고 이 전화로 로그인하여 연결 상태(즉 로그온 상태)를 유지하는 경우, 전화 로그인 후 라이선스 쿼리를 수행할 때 전화가 라이선스를 사용하는 것으로 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="9bcdc-242">**회의에 참가하는 PSTN 전화에 대해 라이선스가 계산됨**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="9bcdc-p123">사용자가 PSTN 전화를 사용하여 회의에 참가하는 경우 회의 참가에 대해 라이선스가 계산되는데, 이는 부정확한 계산이며 PSTN 전화로 회의를 참가하는 데는 라이선스가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p123">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference. However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="9bcdc-245">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-245">**Workaround:**</span></span>

1.  <span data-ttu-id="9bcdc-246">**모바일 사용자의 라이선스 수가 부정확함**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="9bcdc-247">동일한 장치에 속한 IP 주소를 수동으로 파악한 후에 그 중 하나를 라이선스 수에서 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="9bcdc-248">모바일 장치를 사용하여 Lync 클라이언트에 연결하는 경우 이 문제에 대한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="9bcdc-249">**PSTN에서 Lync 클라이언트로 전화하거나, Lync 클라이언트에서 PSTN 회선으로 전화하거나, Lync 전화를 PSTN 회선으로 착신 전환할 경우 라이선스가 두 번 계산됨**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="9bcdc-250">PSTN 전화 번호를 수동으로 파악하여 이로 인해 계산되는 라이선스 수를 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="9bcdc-251">**로그인된 Lync 전화에 대해서는 라이선스가 계산되지 않음**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="9bcdc-252">Lync 전화가 정기적 간격(예: 3분마다) 로그오프된 후에 다시 로그온되도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="9bcdc-253">**회의에 참가하는 PSTN 전화에 대해 라이선스가 계산됨**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="9bcdc-254">회의에 참가하는 데 사용되는 PSTN 전화 번호를 수동으로 파악하여 해당 전화 번호로 인해 계산되는 라이선스 수를 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="9bcdc-255">Lync Server 제어판이 Silverlight 5로 업그레이드 한 후 VMware 환경에서 작동이 중지 됨</span><span class="sxs-lookup"><span data-stu-id="9bcdc-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="9bcdc-256">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-256">**Issue:**</span></span>

<span data-ttu-id="9bcdc-257">VMware 환경에서 Lync Server 제어판을 사용 하는 경우에는 Microsoft Silverlight를 버전 5로 업그레이드 한 후 Lync Server 제어판이 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="9bcdc-258">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-258">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-259">이 문제를 해결하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="9bcdc-260">Silverlight 5를 제거 하 고에서 Silverlight 4를 설치 [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="9bcdc-261">VMware virtual computer가 아닌 컴퓨터에서 Lync Server 제어판에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="9bcdc-262">이렇게 하려면 Lync Server 관리 도구가 컴퓨터에 설치 되어 있는 경우 서버의 Windows **시작** 메뉴에서 Lync server 제어판을 시작 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="9bcdc-263">웹 브라우저를 사용 하 여 Lync Server 제어판에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="9bcdc-264">URL은 https:///cscp.와 유사 합니다. \<frontend\_pool\_fqdn\></span><span class="sxs-lookup"><span data-stu-id="9bcdc-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="9bcdc-265">Active Directory에서 사용자의 고유 이름을 수정한 후에 주소록 서비스의 사용자 정보가 업데이트 되지 않음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="9bcdc-266">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-266">**Issue:**</span></span>

<span data-ttu-id="9bcdc-267">Active Directory 도메인 서비스에서 사용자의 고유 이름 (DN이 라고도 함)이 변경 되 면 추가 변경 내용이 ABS (주소록 서비스)에서 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="9bcdc-268">이는 사용자의 로그인 또는 현재 상태에 영향을 미치지 않지만 SIP 주소도 변경된 경우 검색 시 오래된 SIP 주소가 반환되므로 사용자에 대한 통신이 불가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="9bcdc-269">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-269">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-p126">이 문제를 해결하려면 사용자의 DN을 변경하지 마십시오. 사용자의 DN을 이전 값으로 되돌리면 주소록 서비스에 업데이트 내용이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p126">To work around this issue, do not change a user’s DN. If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="9bcdc-272">설치</span><span class="sxs-lookup"><span data-stu-id="9bcdc-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="9bcdc-273">ASCII 문자가 아닌 문자를 사용 하면 Lync server가 시작 되지 않을 수 있음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="9bcdc-274">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-274">**Issue:**</span></span>

<span data-ttu-id="9bcdc-275">대상 폴더 이름에 ASCII가 아닌 문자 (유니코드, DBCS (더블 바이트 문자 집합), UTF-8 및 u t f-16)가 포함 되어 있으면 설치가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="9bcdc-276">또한 설치가 완료 될 수 있지만 ASCII가 아닌 문자가 다음 중 하나에 포함 된 경우에는 서버가 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="9bcdc-277">컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="9bcdc-277">Computer name</span></span>

  - <span data-ttu-id="9bcdc-278">Domain name</span><span class="sxs-lookup"><span data-stu-id="9bcdc-278">Domain name</span></span>

  - <span data-ttu-id="9bcdc-279">사용자 이름</span><span class="sxs-lookup"><span data-stu-id="9bcdc-279">User name</span></span>

  - <span data-ttu-id="9bcdc-280">사용자 SIP URI</span><span class="sxs-lookup"><span data-stu-id="9bcdc-280">User SIP URI</span></span>

  - <span data-ttu-id="9bcdc-281">서비스 계정 이름</span><span class="sxs-lookup"><span data-stu-id="9bcdc-281">Service account name</span></span>

<span data-ttu-id="9bcdc-282">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-282">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-283">대상 폴더 이름, 컴퓨터 이름, 도메인 이름, 사용자 이름, 사용자 SIP URI 및 서비스 계정 이름에 ASCII 문자만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="9bcdc-284">Lync Server 2013을 설치 하기 전에 모듈이 IIS 7.5에서 InsertEntityBody 메서드를 호출 하면 "힙 손상이 발생 합니다." 라는 핫픽스가 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="9bcdc-285">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-285">**Issue:**</span></span>

<span data-ttu-id="9bcdc-286">"힙 손상은 모듈에서 Microsoft 기술 자료 문서 264886 ()에 설명 된 대로 InsertEntityBody 7.5 메서드를 호출 하면 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) Lync Server 2013을 설치 하기 전에 설치 해야 할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="9bcdc-287">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-287">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-288">Microsoft 다운로드 센터에서 핫픽스를 다운로드 하 여 설치 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="9bcdc-289">Lync Server 2013을 ITA에 설치 하지 못한다 Windows Server 2012 OS RTM 버전</span><span class="sxs-lookup"><span data-stu-id="9bcdc-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="9bcdc-290">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-290">**Issue:**</span></span>

<span data-ttu-id="9bcdc-291">Windows Fabric 설치 실패로 인해 ITA Windows Server 2012에서 Lync Server 2013 설치가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="9bcdc-p128">HH:MM:SS 시간 형식을 사용할 경우 패브릭 추적이 만들어지므로 Windows Fabric 설치가 실패합니다. 그런데 ITA Windows Server에서는 HH.MM.SS 시간 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p128">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS. However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="9bcdc-294">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-294">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-295">이 문제를 해결 하려면 Lync Server 2013을 설치 하기 전에 시스템 레지스트리를 업데이트 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="9bcdc-296">업데이트 해야 하는 레지스트리 키는 HKEY \_ USERS \\ 입니다. 기본 \\ 제어판 \\ 국제 \\ sTimeFormat</span><span class="sxs-lookup"><span data-stu-id="9bcdc-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="9bcdc-297">Windows PowerShell 명령줄 인터페이스를 다음과 같이 사용 하 여 sTimeFormat 값을 HH: mm: ss로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="9bcdc-298">Windows PowerShell을 시작 하 고 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="9bcdc-299">현재 값을 보려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="9bcdc-300">설치가 완료된 후에 복원할 수 있도록 sTimeFormat의 현재 값을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="9bcdc-301">새 값으로 설정하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="9bcdc-302">Lync Server 2013이 성공적으로 설치 된 후에는 다음 cmdlet을 실행 하 여 sTimeFormat의 원래 값을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="9bcdc-303">Set-ItemProperty $a-Name sTimeFormat-Value "<3 단계에서 적어 둔 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="9bcdc-304">> 위 "</span><span class="sxs-lookup"><span data-stu-id="9bcdc-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="9bcdc-305">이동성</span><span class="sxs-lookup"><span data-stu-id="9bcdc-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="9bcdc-306">서버 장애 조치 (failover) 프로세스 중 모바일 클라이언트 문제</span><span class="sxs-lookup"><span data-stu-id="9bcdc-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="9bcdc-307">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-307">**Issue:**</span></span>

<span data-ttu-id="9bcdc-308">Lync Server에 오류가 발생 하 여 장애 조치 (failover) 프로세스가 시작 되 면 모바일 클라이언트 사용자에 게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="9bcdc-309">장애 조치 (failover)가 시작 된 후 최대 10 분 동안 들어오는 Lync 호출이 나 신호가 없음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="9bcdc-310">들어오는 채팅 요청을 수락할 수 없음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="9bcdc-311">오류가 발생 한 서버가 사용자의 홈 서버인 경우 모임에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="9bcdc-312">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-312">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-313">이 문제에 대한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-313">There is no workaround for this issue.</span></span> <span data-ttu-id="9bcdc-314">장애 조치 (failover) 프로세스가 완료 되 면 정상 기능이 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="9bcdc-315">모바일 사용자가 다른 Lync 끝점에서 수신 전화를 거절 하면 통화가 Lync Mobile 클라이언트에서 누락 된 변환으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="9bcdc-316">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-316">**Issue:**</span></span>

<span data-ttu-id="9bcdc-317">모바일 사용자가 수신 전화를 거절 하 고 통화가 다른 Lync 끝점에서 시작 된 경우에는 통화가 장치 통화 목록에 있는 통화 대신 Lync 모바일 클라이언트에서 부재 중 대화로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="9bcdc-318">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-318">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-319">이 문제에 대한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="9bcdc-320">모바일 클라이언트에서 연락처를 검색할 때 페더레이션 대화 상대의 표시 이름을 표시 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="9bcdc-321">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-321">**Issue:**</span></span>

<span data-ttu-id="9bcdc-322">연락처 목록에서 페더레이션 대화 상대를 검색할 때와 같은 일부 시나리오에서는 페더레이션 연락처의 표시 이름이 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="9bcdc-323">Lync mobile 클라이언트에서 연락처에 대 한 활성 현재 상태 구독이 없는 경우 이러한 상황이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="9bcdc-324">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-324">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-325">이 문제에 대한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="9bcdc-326">모바일 클라이언트에서 회의 초대에 해당 하는 부재 중 대화의 초대 대 상자 및 타임 스탬프 정보가 누락 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="9bcdc-327">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-327">**Issue:**</span></span>

<span data-ttu-id="9bcdc-328">모바일 클라이언트에서 부재 중 대화가 회의 초대 이면 부재 중 대화 메시지에서 초대 대 상자 및 타임 스탬프 정보가 누락 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="9bcdc-329">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-329">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-330">이 문제에 대한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="9bcdc-331">모바일 클라이언트 사용자가 VoIP를 사용 하 여 전화를 건 경우 Exchange 2010 또는 이전 버전에서 음성 메일이 구성 되어 있는 사용자에 대해 음성 메일을 남길 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="9bcdc-332">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-332">**Issue:**</span></span>

<span data-ttu-id="9bcdc-333">모바일 클라이언트 사용자가 VoIP를 사용 하 여 전화를 걸 경우 사용자는 Microsoft Exchange Server 2007 또는 Microsoft Exchange Server 2010에서 음성 메일을 사용 하도록 구성 된 사용자에 대해 음성 메일 메시지를 남길 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="9bcdc-334">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-334">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-335">이 문제를 해결 하려면 Exchange 2010을 SP1 이상 버전의 Microsoft Exchange Server와 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="9bcdc-336">모바일 클라이언트의 클라이언트 버전 구성에 대 한 URL과 함께 Block을 사용 하는 경우 잘못 된 오류 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="9bcdc-337">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-337">**Issue:**</span></span>

<span data-ttu-id="9bcdc-338">모바일 클라이언트의 클라이언트 버전 구성에 대해 **URL과 함께 Block** 을 사용 하는 경우 클라이언트 버전을 지원 하지 않을 때 잘못 된 오류 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="9bcdc-339">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-339">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-340">이 문제를 해결 하려면 **URL로 차단**대신 **block** 을 사용 하도록 클라이언트 버전 구성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="9bcdc-341">회의</span><span class="sxs-lookup"><span data-stu-id="9bcdc-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="9bcdc-342">Lync Server 2013 프런트 엔드 서버에서 실행 되는 바이러스 백신 소프트웨어는 Lync Web App 2013, Lync 모바일 2010 및 Lync 모바일 2013 클라이언트에 대 한 서비스를 일시적으로 중단 하는 응용 프로그램 도메인 재생을 유발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="9bcdc-343">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-343">**Issue:**</span></span>

<span data-ttu-id="9bcdc-344">바이러스 백신 소프트웨어로 인해 응용 프로그램 도메인 다시 시작이 트리거되어 Lync Mobility Service 2013 및 UC (통합 통신) 웹 API 클라이언트 응용 프로그램 (Lync Web App 2013, Lync 모바일 2010 및 Lync Mobile 2013)의 상태가 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="9bcdc-345">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-345">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-346">이 문제를 해결하려면 웹 구성 요소와 .NET Framework가 포함된 폴더를 바이러스 백신 검사에서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="9bcdc-347">자세한 내용은 Microsoft 기술 자료 문서 312592, "PRB: 임의 응용 프로그램을 다시 시작 합니다. ' 응용 프로그램을 다시 시작 하는 중 ' ASP.NET의 오류 발생" (at)을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) .</span><span class="sxs-lookup"><span data-stu-id="9bcdc-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="9bcdc-348">다음 폴더를 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="9bcdc-349">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ 웹 구성 요소 \\ mcx \\ Ext</span><span class="sxs-lookup"><span data-stu-id="9bcdc-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="9bcdc-350">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ 웹 구성 요소 \\ mcx \\ Int</span><span class="sxs-lookup"><span data-stu-id="9bcdc-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="9bcdc-351">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ 웹 구성 요소- \\ wa \\ Int</span><span class="sxs-lookup"><span data-stu-id="9bcdc-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="9bcdc-352">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ 웹 구성 요소- \\ wa \\ Ext</span><span class="sxs-lookup"><span data-stu-id="9bcdc-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="9bcdc-353">% Windir% \\ Microsoft.NET \\ Framework64 \\ v v4.0.30319 \\ Config</span><span class="sxs-lookup"><span data-stu-id="9bcdc-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="9bcdc-354">전화 회의에 성공적으로 참가 하려면 Windows Internet Explorer에서 ActiveX 컨트롤 또는 네이티브 XMLHTTP 지원을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="9bcdc-355">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-355">**Issue:**</span></span>

<span data-ttu-id="9bcdc-356">사용자가 Windows Internet Explorer 브라우저 설정에서 ActiveX 컨트롤 또는 네이티브 XMLHTTP 지원을 둘 다 사용하지 않도록 설정하면 Internet Explorer를 기본 브라우저로 선택한 경우 모임에 참가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="9bcdc-357">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-357">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-358">Internet Explorer에서 Active X 컨트롤 또는 "네이티브 XMLHTTP 지원" 중 하나라도 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="9bcdc-359">Lync Server 웹 회의 서비스가 중요 모드에서 복구할 수 없음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="9bcdc-360">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-360">**Issue:**</span></span>

<span data-ttu-id="9bcdc-p134">시스템 오류 시 보관에 대해 중요 모드를 설정하는 경우 중요 모드가 시작된 후 참가자들에게 회의가 더 이상 작동하지 않습니다. 관리자가 시스템 오류를 해결한(예: 데이터베이스 문제 해결) 후에도 데이터 회의 서비스가 자동으로 복구되지 않으며 회의를 다시 재개하려면 관리자가 회의 서비스를 수동으로 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p134">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants. After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="9bcdc-363">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-363">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-364">시스템 오류가 해결된 후에 관리자가 회의 서비스를 수동으로 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="9bcdc-365">웹 회의 서비스가 외부 Office Web App 서버에 대 한 HTTP 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="9bcdc-366">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-366">**Issue:**</span></span>

<span data-ttu-id="9bcdc-367">인터넷, 경계 네트워크 및 웹 회의 서비스 외부에 있는 Office Web Apps 서버 (즉, 내부 회사 네트워크에 없는 서버)가이에 연결 하기 위해 HTTP 프록시를 사용 해야 하는 경우에는 Office Web Apps 서버 검색이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="9bcdc-368">웹 회의 서비스는 Office Web Apps 서버 설치에 대 한 토폴로지 작성기에 정의 된 대로 HTTP 프록시 설정을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="9bcdc-369">따라서 Lync 클라이언트는 전화 회의의 다른 참가자와 Microsoft PowerPoint 2010을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="9bcdc-370">Lync Server 온-프레미스를 설치 하 고 내부 네트워크에서 온-프레미스로 Office Web Apps 서버를 구성 하는 경우에는 프록시 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="9bcdc-371">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-371">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-372">유일한 해결 방법은 외부 Office Web Apps 서버와 통신 하기 위해 HTTP 프록시를 사용 해야 하는 배포 구성을 사용 하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="9bcdc-373">오디오 회의 공급자 회의에 비디오를 추가 하는 것은 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="9bcdc-374">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-374">**Issue:**</span></span>

<span data-ttu-id="9bcdc-375">사용자가 오디오 회의 공급자 회의의 오디오 부분에 참가하는 경우 비디오 추가가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="9bcdc-376">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-376">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-377">이 문제에 대한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="9bcdc-378">IPv6을 사용 하도록 설정 된 토폴로지에서 lync web app Silverlight 플러그 인 자동 업데이트를 사용 하 여 Lync 웹 앱에서 화면 공유 기능을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="9bcdc-379">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-379">**Issue:**</span></span>

<span data-ttu-id="9bcdc-380">IPv6을 사용 하 여 토폴로지를 구성 하면 이전 버전의 화면 공유 플러그 인이 이미 설치 되어 있는 경우 사용자가 Lync 웹 앱 클라이언트에서 해당 화면을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="9bcdc-381">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-381">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-382">Lync Web App를 통해 모임에 참가할 때 화면 공유 플러그 인의 최신 버전을 강제로 업데이트 하려면 다음의 두 파일에서 **MinSupportedBuildVersion** 의 값을 "4.0.7577.380"에서 "4.0.7457.0"로 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="9bcdc-383">% ProgramFiles% \\ Microsoft Lync Server 15 \\ 웹 구성 \\ 요소가 \\ Int \\ 클라이언트 \\ 플러그 인에 도달 \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="9bcdc-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="9bcdc-384">% ProgramFiles% \\ Microsoft Lync Server 15 \\ 웹 구성 \\ 요소가 \\ Ext \\ 클라이언트 \\ 플러그 인에 도달 했습니다 \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="9bcdc-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="9bcdc-385">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="9bcdc-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="9bcdc-386">IPv4 및 IPv6 이중 스택을 사용 하도록 구성 된 컴퓨터에서 실행 되는 Lync 클라이언트가 E911, 미디어 바이패스, 통화 허용 제어 및 위치 기반 라우팅과 같은 컴퓨터의 IP 서브넷에 의존 하는 기능을 지원 하지 않을 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9bcdc-387">이 섹션의 정보는 Lync Server 2013:2 월 2013에 대 한 누적 업데이트와 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="9bcdc-388">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-388">**Issue:**</span></span>

<span data-ttu-id="9bcdc-389">IPv4 및 IPv6 이중 스택과 프록시 서버의 DNS 확인을 기반으로 하는 컴퓨터에서 Lync 클라이언트를 실행 하는 경우 클라이언트는 컴퓨터의 IPv6 주소를 사용 하 여 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="9bcdc-390">이 작업을 수행한 후 Lync 클라이언트는 E911, 미디어 바이패스, 통화 허용 제어 및 위치 기반 라우팅을 제외 하는 IPv6에 대해 지원 되는 기능만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="9bcdc-391">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-391">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-392">이 문제를 해결 하려면 클라이언트 컴퓨터에서 IPv6 지원을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="9bcdc-393">Enterprise Voice가 사용자에 대해 구성 되지 않은 경우 사용자는 E164 형식을 사용 하 여 회의에서 전화를 걸지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="9bcdc-394">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-394">**Issue:**</span></span>

<span data-ttu-id="9bcdc-395">Enterprise Voice가 사용자에 대해 구성 되지 않은 경우에는 해당 사용자가 E164 형식을 사용 하 여 회의에서 전화를 성공적으로 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="9bcdc-396">E164 형식을 사용하지 않는 사용자는 회의에서 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="9bcdc-397">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-397">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-398">이 문제를 해결 하기 위해 Enterprise Voice를 사용 하도록 설정 하지 않은 사용자는 E164 형식의 숫자를 사용 하 여 전화 회의에 전화로 접속 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="9bcdc-399">이들의</span><span class="sxs-lookup"><span data-stu-id="9bcdc-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="9bcdc-400">사용자에 대해 통합 연락처 저장소가 설정 되어 있는 동안 사용자가 "모든 초대 및 통신 차단"을 선택한 경우 현재 상태는 거부 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="9bcdc-401">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-401">**Issue:**</span></span>

<span data-ttu-id="9bcdc-402">사용자에 대해 통합 연락처 저장소가 설정되어 있는 동안 사용자가 "모든 초대 및 통신 차단"을 선택할 경우 현재 상태가 거부되어야 할 때 거부되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="9bcdc-403">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-403">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-p138">이 문제를 해결하려면 사용자에 대해 통합 연락처 저장소를 사용하지 않도록 설정해야 합니다. 이렇게 하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p138">To work around this issue, you can turn off the unified contact store for the user. To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="9bcdc-406">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="9bcdc-407">Office Communications Server 2007 R2 온-프레미스 사용자가 하이브리드 배포에서 비즈니스용 Skype Online 사용자의 현재 상태를 볼 수 없음-하이브리드</span><span class="sxs-lookup"><span data-stu-id="9bcdc-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="9bcdc-408">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-408">**Issue:**</span></span>

<span data-ttu-id="9bcdc-409">Lync Server 2013 디렉터를 사용 하는 경우 하이브리드 배포에서 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="9bcdc-410">비즈니스용 Skype Online에 속한 사용자의 현재 상태는 온-프레미스 사용자의 현재 상태를 알 수 없음으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="9bcdc-411">또한 비즈니스용 Skype 온라인으로 로그인 한 사용자는 Office Communications Server R2 온-프레미스 사용자의 현재 상태를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="9bcdc-412">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-412">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-413">이 문제를 부분적으로 해결 하려면 Lync Server 2013 디렉터 대신 Lync Server 2013 온-프레미스 풀을 가리키도록 비즈니스용 Skype 온라인 사용자의 홈 서버 (msrtcsip-gateways-presencehomeserver)를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="9bcdc-414">온-프레미스 프런트 엔드 서버에서이 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="9bcdc-415">이 대안은 Office Communications Server 2007 2에 속한 사용자의 현재 상태를 비즈니스용 Skype Online 사용자에 게 올바르게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="9bcdc-416">응답 그룹 응용 프로그램, 통화 대기 응용 프로그램 및 그룹 통화 픽업</span><span class="sxs-lookup"><span data-stu-id="9bcdc-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="9bcdc-417">발신자가 파티를 검색 하는 통화를 설정 하는 동안 음악 대기 중 1 초를 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9bcdc-418">이 섹션의 정보는 Lync Server 2013:2 월 2013에 대 한 누적 업데이트와 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="9bcdc-419">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-419">**Issue:**</span></span>

<span data-ttu-id="9bcdc-420">그룹 통화 픽업을 통해 통화를 검색 하는 경우 검색기 파티와 통화를 설정 하는 동안 발신자가 대기 음악 중 1 초를 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="9bcdc-421">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-421">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-422">이 문제에 대한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="9bcdc-423">응답 그룹 에이전트는 lync server 2010 에이전트 콘솔을 통해 Lync Server 2010 공식 에이전트 그룹에만 로그인 하 고 로그 아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="9bcdc-424">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-424">**Issue:**</span></span>

<span data-ttu-id="9bcdc-425">Lync Server 2013 응답 그룹 에이전트는 lync server 2010 에이전트 콘솔을 통해 lync server 2010 형식 에이전트 그룹에만 로그인 하 고 로그 아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="9bcdc-426">Lync Server 2010 에이전트 콘솔에서 사용자는 자신이 속한 Lync Server 2010 응답 그룹만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="9bcdc-427">사용자가 속한 Lync Server 2013 Response 그룹은 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="9bcdc-428">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-428">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-429">응답 그룹 에이전트가 Lync Server 2013 사용자이 고 Lync Server 2013 공식 에이전트 그룹의 일부인 경우 사용자는 브라우저의 웹 링크를 통해 Lync server 2013 에이전트 콘솔에 직접 액세스 하 여 Lync Server 2013 에이전트 그룹에 로그인 하 고 로그 아웃 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="9bcdc-430">Lync Server 2010 응답 그룹 에이전트가 Lync Server 2013 응답 그룹을 대신 하 여 전화를 걸 수 없음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="9bcdc-431">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-431">**Issue:**</span></span>

<span data-ttu-id="9bcdc-432">Lync server 2013 Response 그룹의 에이전트는 응답 그룹을 대신 하 여 전화를 걸 수 없습니다. 2010</span><span class="sxs-lookup"><span data-stu-id="9bcdc-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="9bcdc-433">Lync Server 2013 Response 그룹을 Lync 클라이언트에서 사용 하 여 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="9bcdc-434">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-434">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-435">이 문제를 해결 하려면 Lync Server 2010 사용자를 Lync Server 2013로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="9bcdc-436">Lync server 2013로 마이그레이션된 후 Lync 서버 2010에서 응답 그룹을 제거 하면 응답 그룹이 들어오는 호출을 수락 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="9bcdc-437">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-437">**Issue:**</span></span>

<span data-ttu-id="9bcdc-438">Lync server 2010에서 Lync Server 2013로 마이그레이션된 응답 그룹을 lync server 제어판 또는 Lync Server 관리 셸을 통해 Lync Server 2010에서 제거한 경우 Lync Server 2013의 응답 그룹은 들어오는 호출 수신을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="9bcdc-439">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-439">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-440">이 문제를 해결 하려면 Lync server 2010에서 Lync Server 2013으로 마이그레이션된 Lync Server 2010에서 응답 그룹을 제거 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="9bcdc-441">응답 그룹을 이미 제거한 경우 Lync Server 2013에서 다시 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="9bcdc-442">관리 되는 새 워크플로를 만들 때 비활성으로 설정 하면 워크플로 배포가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="9bcdc-443">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-443">**Issue:**</span></span>

<span data-ttu-id="9bcdc-p143">새 관리 워크플로를 만들 때 비활성으로 설정할 경우 워크플로 배포가 실패합니다. 이 문제는 워크플로를 만들 때 비활성으로 설정할 경우 발생하며 배포된 후에 비활성으로 설정을 수정한 워크플로에는 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p143">When a new managed workflow is set to inactive when created, deployment of the workflow will fail. This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="9bcdc-446">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-446">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-p144">워크플로를 만들고 배포할 때 워크플로를 활성으로 설정한 후에 배포합니다. 워크플로가 성공적으로 배포되고 나서 워크플로 설정을 비활성으로 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p144">When creating and deploying a workflow, set the workflow as active and then deploy it. After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="9bcdc-449">소유자 풀에서 응답 그룹을 제거 하면 응답 그룹을 백업 풀로 가져온 경우 백업 풀의 응답 그룹이 장애 조치 (failover) 중에 들어오는 호출을 수락 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="9bcdc-450">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-450">**Issue:**</span></span>

<span data-ttu-id="9bcdc-451">소유자를 덮어쓰지 않고 기본 풀이 소유한 응답 그룹을 백업 풀로 가져온 경우 응답 그룹이 소유자 풀에서 제거 되 면 백업 풀의 응답 그룹은 장애 조치 (failover) 중에 들어오는 호출을 수락 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="9bcdc-452">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-452">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-453">응답 그룹을 기본 풀에 다시 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="9bcdc-454">그런 다음 주 풀에서 응답 그룹 구성을 내보내고이를 백업 풀로 다시 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="9bcdc-455">백업 풀에 응답 그룹을 다시 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="9bcdc-456">이 경우 백업 풀은 응답 그룹의 소유자 풀이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="9bcdc-457">응답 그룹을 대신 하 여 검색 요청이 완료 되 면 통화 대기 응용 프로그램에서 대기 된 통화를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="9bcdc-458">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-458">**Issue:**</span></span>

<span data-ttu-id="9bcdc-459">다음과 같은 조건에서는 대기 통화에 대한 재개 요청이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="9bcdc-460">에이전트가 익명 응답 그룹의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="9bcdc-461">에이전트가 익명 응답 그룹을 통해 통화 대기 응용 프로그램에서 대기 된 통화를 검색 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="9bcdc-462">에이전트가 대신 전화(Call On Behalf) 옵션 또는 Lync Attendant 클라이언트의 이 옵션을 통해 파킹된 통화 번호로 전화를 걸어 통화를 재개하려고 함</span><span class="sxs-lookup"><span data-stu-id="9bcdc-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="9bcdc-463">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-463">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-464">이 문제에 대한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="9bcdc-465">대기 통화는 응답 그룹 대신이 작업을 수행 하지 않고 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="9bcdc-466">Lync Server 제어판, 토폴로지 작성기 및 계획 도구</span><span class="sxs-lookup"><span data-stu-id="9bcdc-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="9bcdc-467">계획 도구 제한 사항</span><span class="sxs-lookup"><span data-stu-id="9bcdc-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9bcdc-468">이 섹션의 정보는 Lync Server 2013:2 월 2013에 대 한 누적 업데이트와 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="9bcdc-469">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-469">**Issue:**</span></span>

<span data-ttu-id="9bcdc-470">배포를 계획할 때 계획 도구에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="9bcdc-471">최대 10 개의 중앙 사이트가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="9bcdc-472">각 중앙 사이트에 최대 14 개의 분기 사이트를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="9bcdc-473">각 중앙 사이트에는 최대 24만 명의 사용자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="9bcdc-474">또한 권장 토폴로지를 계산할 때 계획 도구에는 다음에 대 한 값이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="9bcdc-475">온라인 상태인 사용자 수</span><span class="sxs-lookup"><span data-stu-id="9bcdc-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="9bcdc-476">XMPP 페더레이션에 대해 사용 하도록 설정 된 사용자의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="9bcdc-477">Lync Web App을 사용 하는 사용자 비율</span><span class="sxs-lookup"><span data-stu-id="9bcdc-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="9bcdc-478">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-478">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-479">이러한 문제에 대 한 해결 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-479">There is no workaround for these issues.</span></span> <span data-ttu-id="9bcdc-480">계획 도구에 대 한 자세한 내용은 [계획 도구를 사용 하 여 Lync Server 2013에 대 한 토폴로지 디자인](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="9bcdc-481">계획 도구에서 옵션을 업데이트할 때에는 이전에 정의 된 IP 주소가에 지 네트워크에 사용 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="9bcdc-482">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-482">**Issue:**</span></span>

<span data-ttu-id="9bcdc-483">계획 도구를 사용 하 여 디자인을 완료 한 후에는에 지 네트워크 옵션을 변경 하는 경우 기존 IP 주소를 업데이트 하는 대신 추가 IP 주소를 디자인에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="9bcdc-484">이 문제는에 지 네트워크 다이어그램의 세부 정보를 볼 때 **여기를 클릭 하 여 옵션을 업데이트 하**고, 구성 옵션 대화 상자에서에 지 네트워크에서 **동일한 fqdn 및 IP 주소를 사용 하 고,에 지 서버의에 지 서비스에 대해 서로 다른 포트**를 선택 하려는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="9bcdc-485">변경 내용을 적용 하면 새 IP 주소 및에 지 서버가 디자인에 추가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="9bcdc-486">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-486">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-487">지금은이 문제에 대 한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="9bcdc-488">Lync Server 제어판에서 "모든 사용자를 풀로 이동"이 예상 대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="9bcdc-489">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-489">**Issue:**</span></span>

<span data-ttu-id="9bcdc-490">Lync Server 제어판을 사용 하 여 모든 사용자를 한 풀에서 다른 풀로 이동 하는 경우 (예: 여러 도메인 컨트롤러 및 부모/자식 도메인이 있는 경우) "지정 된 사용자가 레거시 사용자가 아님," 대신 Move-CsUser cmdlet 사용 "이라는 오류 메시지가 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="9bcdc-491">복잡 한 Active Directory 환경의 복제 시간이 길어질 때의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="9bcdc-492">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-492">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-493">이 문제를 해결하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="9bcdc-494">Lync Server 제어판의 필터를 사용 하 여 레거시 사용자를 검색 하 고 해당 사용자를 선택한 다음 **모든 사용자를 풀로 이동**하는 대신 **선택한 사용자를 풀로 이동 명령을** 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="9bcdc-495">Lync server cmdlet을 사용 하 여 레거시 사용자를 일괄적으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="9bcdc-496">Microsoft Silverlight 브라우저 플러그 인을 버전 5로 업데이트 하면 Lync Server 제어판이 VMware 환경에서 중지 됨</span><span class="sxs-lookup"><span data-stu-id="9bcdc-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="9bcdc-497">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-497">**Issue:**</span></span>

<span data-ttu-id="9bcdc-498">VMware 환경에서 Lync Server 제어판을 사용 하는 경우 Silverlight를 버전 5로 업그레이드 한 후 Lync Server 제어판이 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="9bcdc-499">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-499">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-500">이 문제를 해결하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="9bcdc-501">Silverlight 5를 제거한 다음에서 Silverlight 4를 설치 [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="9bcdc-502">VMware 가상 컴퓨터가 아닌 컴퓨터에서 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="9bcdc-503">원격 컴퓨터에서 Lync Server 제어판을 열려면 컴퓨터에 Lync Server 관리 도구를 설치한 다음 Windows **시작** 메뉴에서 Lync server 제어판을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="9bcdc-504">웹 브라우저에 URL을 입력 하 여 Lync Server 제어판을 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="9bcdc-505">URL은 https:///cscp.와 유사 합니다. \<frontend\_pool\_fqdn\></span><span class="sxs-lookup"><span data-stu-id="9bcdc-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="9bcdc-506">토폴로지 작성기에서 미러링 데이터베이스를 제거한 후에 관리자가 Uninstall-csmirrordb cmdlet을 실행할 수 없음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="9bcdc-507">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-507">**Issue:**</span></span>

<span data-ttu-id="9bcdc-508">관리자가 토폴로지 작성기에서 미러링 데이터베이스를 사용 하지 않도록 설정한 다음 토폴로지 작성기에서 미러링 데이터베이스를 삭제 하면 관리자가 **csMirrorDatabase** cmdlet을 실행 하 여 SQL Server에서 미러링을 제거 하기 위한 메시지가 작업 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="9bcdc-509">그런데 관리자가 이 cmdlet을 실행하려고 하면 cmdlet이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="9bcdc-510">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-510">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-511">토폴로지 작성기에서 풀의 SQL 미러링을 제거 하려면 먼저 cmdlet을 사용 하 여 SQL Server에서 미러를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="9bcdc-512">그런 후 토폴로지 작성기를 사용해서 토폴로지에서 미러를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="9bcdc-513">SQL Server에서 미러를 제거하려면 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="9bcdc-514">예를 들어 사용자 데이터베이스의 미러링을 제거하고 데이터베이스를 삭제하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="9bcdc-515">*DropExistingDatabasesOnMirror* 매개 변수를 사용하면 해당 데이터베이스가 미러에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="9bcdc-516">그런 후 토폴로지에서 미러를 제거하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="9bcdc-517">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭하고 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="9bcdc-518">**SQL 저장소 미러링 사용**의 선택을 취소한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="9bcdc-519">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="9bcdc-520">백 엔드 데이터베이스 미러링 관계를 변경할 때마다 풀에서 모든 프런트 엔드 서버를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="9bcdc-521">관리자가 연결 된 감시 저장소가 있는 프런트 엔드 풀을 사용 하 여 배포를 제거 하려고 하면 토폴로지 작성기에 유효성 검사 오류가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="9bcdc-522">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-522">**Issue:**</span></span>

<span data-ttu-id="9bcdc-523">관리자가 토폴로지 작성기에서 **배포 제거** 명령을 사용 하 여 연결 된 감시 저장소와 함께 프런트 엔드 풀을 포함 하는 배포를 제거 하려고 하면 토폴로지 작성기에 유효성 검사 오류가 표시 되 고 작업이 진행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="9bcdc-524">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-524">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-525">이 문제를 해결하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="9bcdc-526">배포를 제거하기 전에 먼저 감시 저장소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="9bcdc-527">프런트 엔드 풀의 감시 저장소를 추가한 후에 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="9bcdc-528">계획 도구와 토폴로지 작성기 간에 영구 채팅 서버 배포 정보가 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="9bcdc-529">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-529">**Issue:**</span></span>

<span data-ttu-id="9bcdc-530">Lync Server 2013, 계획 도구에서 재해 복구를 사용 하 여 영구 채팅 서버 배포에 대 한 사이트 토폴로지 다이어그램을 출력 하는 경우 사이트 토폴로지 다이어그램에는 여러 개의 (실제) 사이트가 있으며 각 사이트에서 일관 되 게 영구 채팅 서버가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="9bcdc-531">토폴로지 작성기에서 모든 영구 채팅 서버는 단일 (논리적) 사이트에 속하는 것으로 표시 되며 동일한 영구 채팅 서버 풀 노드에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="9bcdc-532">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-532">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-533">현재까지는 이 문제에 대한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="9bcdc-534">사용자는 영구 채팅 서버 배포에 대 한 계획 도구의 출력을 분석 하 고 특정 요구 사항에 맞게 계획을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="9bcdc-535">따른</span><span class="sxs-lookup"><span data-stu-id="9bcdc-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="9bcdc-536">모니터링</span><span class="sxs-lookup"><span data-stu-id="9bcdc-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="9bcdc-537">동아시아 언어 버전의 Lync Server를 사용 하는 경우 특정 상황에서 모니터링 보고서 배포 마법사에 잘못 된 문자가 표시 됨</span><span class="sxs-lookup"><span data-stu-id="9bcdc-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="9bcdc-538">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-538">**Issue:**</span></span>

<span data-ttu-id="9bcdc-539">시스템 로캘이 동아시아 언어로 설정 되지 않은 운영 체제에서 한국어 (중국어 간체), 중국어 (번체), 일본어 또는 한국어와 같은 동아시아 버전을 사용 하는 경우에는 모니터링 보고서 배포 마법사에서 지역화 된 메시지 대신 물음표나 기타 문자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="9bcdc-540">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-540">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-541">이 문제를 해결 하려면 운영 체제 및 Lync Server 2013의 로캘을 같은 언어로 설정 하면 모든 메시지가 올바르게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="9bcdc-542">Lync Server 제어판</span><span class="sxs-lookup"><span data-stu-id="9bcdc-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="9bcdc-543">경우에 따라 위쪽 탐색 모음의 마지막 항목을 클릭 하면 Lync Server 제어판의 페이지에 있는 위쪽 탐색 모음의 첫 번째 항목이 사라지는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="9bcdc-544">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-544">**Issue:**</span></span>

<span data-ttu-id="9bcdc-545">Lync Server 제어판의 페이지에서 위쪽 탐색 모음의 마지막 항목을 클릭 하면 위쪽 탐색 모음의 첫 번째 항목이 사라질 수 있는 세 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="9bcdc-546">프랑스어 버전에서 "Féderation et accès externe" 페이지의 "Partenaires fédérés XMPP"를 클릭하면 "Stratégie d'accès externe" 항목이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="9bcdc-547">독일어 버전에서 "Clients" 페이지의 "Pushbenachrichtigungskonfiguration"을 클릭하면 "Clientversionskonfiguration" 항목이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="9bcdc-548">러시아어 버전에서 "Конфигурация сети" 페이지의 "Маршрут региона"를 클릭하면 "Глобально" 항목이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="9bcdc-549">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-549">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-550">이 문제를 해결 하려면 브라우저에서 Lync Server 제어판의 페이지를 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="9bcdc-551">그러면 브라우저에서 페이지가 로드될 때 상위 탐색 모음에 있는 모든 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="9bcdc-552">주소록</span><span class="sxs-lookup"><span data-stu-id="9bcdc-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="9bcdc-553">일부 언어에서는 주소록의 인덱싱이 예상 대로 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9bcdc-554">이 섹션의 정보는 Lync Server 2013:2 월 2013에 대 한 누적 업데이트와 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="9bcdc-555">사용자 속성에 인덱싱된 필드가 있고 해당 필드에 인덱싱할 수 없는 문자만 포함 되어 있으면 사용자가 주소록에서 수행한 검색에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="9bcdc-556">다음 문자와 로캘을 인덱싱할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="9bcdc-557">대문자 키릴 자모, 그리스어 및 아르메니아어 문자</span><span class="sxs-lookup"><span data-stu-id="9bcdc-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="9bcdc-558">악센트 부호가 있는 문자</span><span class="sxs-lookup"><span data-stu-id="9bcdc-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="9bcdc-559">태국어</span><span class="sxs-lookup"><span data-stu-id="9bcdc-559">Thai</span></span>

  - <span data-ttu-id="9bcdc-560">라오스어</span><span class="sxs-lookup"><span data-stu-id="9bcdc-560">Lao</span></span>

  - <span data-ttu-id="9bcdc-561">미얀마</span><span class="sxs-lookup"><span data-stu-id="9bcdc-561">Myanmar</span></span>

  - <span data-ttu-id="9bcdc-562">데바나가리</span><span class="sxs-lookup"><span data-stu-id="9bcdc-562">Devanagari</span></span>

  - <span data-ttu-id="9bcdc-563">에티오피아)</span><span class="sxs-lookup"><span data-stu-id="9bcdc-563">Ethiopic</span></span>

  - <span data-ttu-id="9bcdc-564">티베트어</span><span class="sxs-lookup"><span data-stu-id="9bcdc-564">Tibetan</span></span>

  - <span data-ttu-id="9bcdc-565">벵골어</span><span class="sxs-lookup"><span data-stu-id="9bcdc-565">Bengali</span></span>

  - <span data-ttu-id="9bcdc-566">구자라트어</span><span class="sxs-lookup"><span data-stu-id="9bcdc-566">Gujarati</span></span>

  - <span data-ttu-id="9bcdc-567">텔루구어</span><span class="sxs-lookup"><span data-stu-id="9bcdc-567">Telugu</span></span>

  - <span data-ttu-id="9bcdc-568">다른 모든 인도어 스크립트</span><span class="sxs-lookup"><span data-stu-id="9bcdc-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="9bcdc-569">Lync Web App, 웹 스케줄러 및 웹 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9bcdc-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="9bcdc-570">Lync Web Scheduler, 전화 접속, 참가 시작 관리자, 영구 채팅 방 관리 및 OCTab의 특정 언어에 대 한 언어 대체 기능이 예상 대로 작동 하지 않을 수 있음</span><span class="sxs-lookup"><span data-stu-id="9bcdc-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="9bcdc-571">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-571">**Issue:**</span></span>

<span data-ttu-id="9bcdc-572">Internet Explorer에서 웹 브라우저의 중립 로캘을 선택할 때 예를 들어 \[ \] 언어, 스크립트 및 로캘 (예: "노르웨이어, 복말 (노르웨이) NB-아니요")을 지정 하는 로캘 대신 "노르웨이어"와 같은 추가 사양이 없는 언어 이름을 사용 하면 \[ \] Lync Web Scheduler, 전화 접속, 참가 시작 관리자, 영구 채팅 공간 관리 및 octab의 특정 언어에 대 한 예기치 않은 표시 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="9bcdc-573">예를 들어 다음 언어 중 하나를 선택할 때 영어 페이지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="9bcdc-574">노르웨이어</span><span class="sxs-lookup"><span data-stu-id="9bcdc-574">Norwegian</span></span>

  - <span data-ttu-id="9bcdc-575">포르투갈어</span><span class="sxs-lookup"><span data-stu-id="9bcdc-575">Portuguese</span></span>

  - <span data-ttu-id="9bcdc-576">세르비아어</span><span class="sxs-lookup"><span data-stu-id="9bcdc-576">Serbian</span></span>

<span data-ttu-id="9bcdc-577">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-577">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-578">중립 로캘을 사용하여 언어를 선택하려는 경우 브라우저의 언어 기본 설정 목록에서 추가 언어로 특정 로캘(스크립트 및/또는 국가 코드 포함)을 사용하여 해당 언어를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="9bcdc-579">일부 웹 브라우저에서 Lync 웹 스케줄러, 전화 접속, 참가 시작 관리자, 영구 채팅 공간 관리 및 OCTab을 사용 하는 경우 아제리어 및 우즈베크어 로캘을 제한적으로 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9bcdc-580">이 섹션의 정보는 Lync Server 2013:2 월 2013에 대 한 누적 업데이트와 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="9bcdc-581">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-581">**Issue:**</span></span>

<span data-ttu-id="9bcdc-582">Internet Explorer 8 또는 Internet Explorer 9를 사용 하 고 브라우저 언어를 아제리어 (라틴 문자) 또는 우즈베크어 (라틴 문자)로 설정 하면 전화 접속 및 참가 시작 관리자 페이지가 영어로 표시 되 고 브라우저의 기본 설정 언어 집합으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="9bcdc-583">Firefox 또는 Chrome 브라우저를 사용 하 고 브라우저 언어를 아제리어 (라틴 문자) 또는 우즈베크어 (라틴 문자)로 설정 하면 Lync 웹 앱, Lync 웹 스케줄러 및 RGS Ocx 탭이 브라우저의 영어 또는 기본 언어 집합으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="9bcdc-584">우즈베크어 (라틴 문자) 로캘은 Safari 브라우저에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="9bcdc-585">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-585">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-586">이러한 문제에 대 한 해결 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="9bcdc-587">Lync 웹 응용 프로그램 루마니아어 버전의 "모임 시작" 목록에 드롭다운 화살표가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="9bcdc-588">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-588">**Issue:**</span></span>

<span data-ttu-id="9bcdc-589">루마니아어 버전의 Lync Web App을 사용 하는 사용자가 다음 단계를 수행 하는 경우 드롭다운 목록에 **참가 모임** 에 대 한 드롭다운 화살표가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="9bcdc-590">**일반** 탭에서 **이 컴퓨터에 사용자 이름 및 암호 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="9bcdc-591">**전화** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="9bcdc-592">**모임 참가 위치**의 드롭다운 목록을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="9bcdc-593">사용자에 게는 기본 **Lync 웹 앱**보다 더 많은 옵션이 있음을 나타내는 화살표가 **표시 되지 않습니다 (예: 루마니아어** , "뉴 se asociaža la componenta Audio") 및 **새 번호**"(루마니아어," Număr nou ").</span><span class="sxs-lookup"><span data-stu-id="9bcdc-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="9bcdc-594">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-594">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-595">이 드롭다운 목록의 화살표가 표시되지 않더라도 사용자는 기본값을 클릭하여 목록에서 추가 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="9bcdc-596">터키어 버전의 Lync Web Scheduler를 사용 하는 경우 "발표자" 아래에 있는 "내가 선택한 사용자" 옵션을 사용할 때 모임을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="9bcdc-597">**문제점과**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-597">**Issue:**</span></span>

<span data-ttu-id="9bcdc-p159">터키어 버전의 Lync Web Scheduler에서 모임을 만들거나 편집하는 경우 "발표자" 아래에 있는 "내가 선택한 사용자" 옵션이 지원되지 않습니다. 이 옵션을 선택할 경우 모임을 저장할 수 없으며, 하나 이상의 사용자가 발표자가 될 수 없다는 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p159">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported. When this option is selected, the meeting can't be saved. Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="9bcdc-601">**여기서**</span><span class="sxs-lookup"><span data-stu-id="9bcdc-601">**Workaround:**</span></span>

<span data-ttu-id="9bcdc-p160">이 문제를 해결하려면 기본 옵션인 "내 회사의 사용자" 또는 "이끌이만", "이끌이의 회사 외부 사람을 포함한 모든 사용자"를 비롯한 기타 옵션을 사용하면 됩니다. 이끌이는 사용자가 모임에 참가한 후에 올바른 역할로 강등 또는 승격할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p160">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company." The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="9bcdc-604">또는 다른 언어를 이해하는 사용자의 경우 브라우저에서 지원되는 43개의 다른 언어로 언어 선택을 변경한 후에 "내가 선택한 사용자"를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="9bcdc-605">저작권법과</span><span class="sxs-lookup"><span data-stu-id="9bcdc-605">Copyright</span></span>

<span data-ttu-id="9bcdc-p161">이 문서는 최종 상업적 출시 이전에 상당 부분 변경될 수 있는 예비 릴리스 소프트웨어 제품에 대한 지원 문서이며 Microsoft Corporation이 소유한 기밀 정보입니다. 이 문서는 수취자와 Microsoft 간의 비공개 계약에 따라서만 공개할 수 있습니다. 이 문서는 정보 제공 용도로만 사용되며 Microsoft는 이 설명서에서 명시적 또는 암시적인 어떠한 보증도 하지 않습니다. 이 설명서에 나와 있는 URL 및 기타 인터넷 웹 사이트 참조 등의 정보는 공지 없이 변경될 수 있습니다. 이 문서의 사용이나 사용 결과에 따른 책임은 전적으로 사용자에게 있습니다. 달리 명시하지 않은 경우 여기에서 설명하는 회사, 조직, 제품, 도메인 이름, 전자 메일 주소, 로고, 사람, 장소 및 이벤트 등의 예는 실제 데이터가 아닙니다. 어떠한 실제 회사, 조직, 제품, 도메인 이름, 전자 메일 주소, 로고, 사람, 장소 또는 이벤트와도 연관시킬 의도가 없으며 그렇게 유추해서도 안 됩니다. 해당 저작권법을 준수하는 것은 사용자의 책임입니다. 저작권에서의 권리와는 별도로, 이 문서의 어떠한 부분도 Microsoft의 명시적인 서면 승인 없이는 어떠한 형식이나 수단(전자적, 기계적, 복사기에 의한 복사, 기록 또는 다른 방법) 또는 목적으로도 복제되거나, 검색 시스템에 저장 또는 도입되거나, 전송될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p161">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation. It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft. This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document. Information in this document, including URL and other Internet website references, is subject to change without notice. The entire risk of the use or the results from the use of this document remains with the user. Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious. No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="9bcdc-p162">Microsoft가 이 문서 본 안에 관련된 특허권, 상표권, 저작권 또는 기타 지적 재산권 등을 보유할 수도 있습니다. 서면 사용권 계약에 따라 Microsoft로부터 귀하에게 명시적으로 제공된 권리 이외에, 이 문서의 제공은 귀하에게 이러한 특허권, 상표권, 저작권 또는 기타 지적 재산권 등에 대한 어떠한 사용권도 허여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="9bcdc-p163">© 2012 Microsoft Corporation. 모든 권리 보유.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-p163">© 2012 Microsoft Corporation. All rights reserved.</span></span>

<span data-ttu-id="9bcdc-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook 및 SQL Server는 미국, 대한민국 및/또는 기타 국가에서의 Microsoft Corporation 등록 상표 또는 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="9bcdc-620">기타 모든 상표의 소유권은 해당 소유자에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcdc-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

