---
title: 백 엔드 서버 또는 Standard Edition Server 업그레이드 또는 업데이트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd3617098c42cd38e9928f055a6348a7bf2f9342
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="f33a1-102">Lync Server 2013에서 백 엔드 서버 또는 Standard Edition 서버 업그레이드 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="f33a1-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f33a1-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f33a1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f33a1-104">이 항목에서는 Enterprise Edition 백 엔드 서버 또는 Standard Edition 서버에 업데이트를 설치 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="f33a1-p101">업그레이드하는 동안 백 엔드 서버가 30분 이상 중단되는 경우에는 사용자가 복구 모드로 전환될 수 있습니다. 업그레이드가 완료되고 백 엔드 서버가 다시 풀의 프런트 엔드 서버에 연결되면 사용자가 전체 기능 모드로 복구됩니다. 업그레이드에 30분 미만이 걸리는 경우에는 사용자에게 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="f33a1-108">백 엔드 서버 또는 Standard Edition server를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="f33a1-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="f33a1-109">CsAdministrator 역할의 구성원으로 업그레이드할 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="f33a1-110">업데이트를 다운로드한 후 로컬 하드 디스크로 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="f33a1-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="f33a1-p102">명령줄에 다음을 입력하여 Lync Server 서비스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-p102">Stop Lync Server services. At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="f33a1-p103">명령줄에 다음을 입력하여 World Wide Web 서비스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="f33a1-116">모든 Communications Server 관리 셸 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="f33a1-117">업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-117">Install the update.</span></span>

8.  <span data-ttu-id="f33a1-118">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="f33a1-p104">Lync Server 서비스를 다시 중지하여 GAC(전역 어셈블리 캐시) -d 어셈블리를 catch합니다. 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-p104">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies. At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="f33a1-p105">명령줄에 다음을 입력하여 World Wide Web 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="f33a1-123">다음 중 하나를 수행하여 LyncServerUpdateInstaller.exe에서 SQL Server 데이터베이스에 대해 수행한 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="f33a1-124">Enterprise Edition 백 엔드 서버인 경우 보관 또는 모니터링 데이터베이스와 같이이 서버에 배치 된 데이터베이스가 없는 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="f33a1-125">Enterprise Edition 백 엔드 서버이 고이 서버에 배치 된 데이터베이스가 있는 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="f33a1-126">Standard Edition server 인 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

