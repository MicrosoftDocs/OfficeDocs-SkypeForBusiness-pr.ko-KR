---
title: 백 엔드 서버 또는 Standard Edition 서버 업그레이드 또는 업데이트
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
ms.openlocfilehash: 0526cc7ba6a6abefd066bf07d845ffed3a4107ca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="bcb66-102">Lync Server 2013에서 백 엔드 서버 또는 Standard Edition 서버 업그레이드 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="bcb66-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcb66-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bcb66-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bcb66-104">이 항목에서는 Enterprise Edition 백 엔드 서버 또는 Standard Edition 서버에 업데이트를 설치 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="bcb66-105">업그레이드 하는 동안 백 엔드 서버가 최소 30 분 동안 중단 되 면 사용자가 복원 모드로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-105">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="bcb66-106">업그레이드가 완료 되 고 백 엔드 서버가 풀의 프런트 엔드 서버와 다시 연결 되 면 사용자가 전체 기능으로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-106">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="bcb66-107">업그레이드 시간이 30 분 미만이 되 면 사용자에 게 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-107">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="bcb66-108">백 엔드 서버 또는 Standard Edition 서버를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="bcb66-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="bcb66-109">CsAdministrator 역할의 구성원으로 업그레이드 하는 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="bcb66-110">업데이트를 다운로드 하 고 로컬 하드 디스크에 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="bcb66-111">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="bcb66-112">Lync Server 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-112">Stop Lync Server services.</span></span> <span data-ttu-id="bcb66-113">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-113">At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="bcb66-114">World Wide Web 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-114">Stop the World Wide Web service.</span></span> <span data-ttu-id="bcb66-115">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-115">At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="bcb66-116">모든 Lync Server Management 셸 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="bcb66-117">업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-117">Install the update.</span></span>

8.  <span data-ttu-id="bcb66-118">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="bcb66-119">Lync Server 서비스를 다시 중지 하 여 GAC (전역 어셈블리 캐시) – d 어셈블리를 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-119">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies.</span></span> <span data-ttu-id="bcb66-120">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-120">At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="bcb66-121">World Wide Web 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-121">Restart the World Wide Web service.</span></span> <span data-ttu-id="bcb66-122">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-122">At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="bcb66-123">다음 중 하나를 수행 하 여 LyncServerUpdateInstaller에의 한 변경 내용을 SQL Server 데이터베이스에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="bcb66-124">Enterprise Edition 백 엔드 서버이 고 데이터베이스 보관 또는 모니터링 등의 collocated 데이터베이스가 없는 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="bcb66-125">Enterprise Edition 백 엔드 서버이 고이 서버에 collocated 데이터베이스가 있는 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="bcb66-126">스탠더드 버전 서버인 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb66-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

