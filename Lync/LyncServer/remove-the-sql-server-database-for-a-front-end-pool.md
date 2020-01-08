---
title: 프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6dcbe9bcab20438d02fe489666f9b4c0c0f6d0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="7407c-102">프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="7407c-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7407c-103">_**마지막으로 수정한 주제:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="7407c-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="7407c-104">Microsoft Lync Server 2010 프런트 엔드 풀을 제거 하거나 다른 데이터베이스를 사용 하도록 풀을 다시 구성한 후에는 풀 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="7407c-105">토폴로지 작성기에서 정의를 제거 하려면 다음 절차를 사용 하 여 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="7407c-106">토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="7407c-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="7407c-107">Lync Server 2013 프런트 엔드 서버에서 토폴로지 작성기를 열고 기존 토폴로지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="7407c-108">토폴로지 작성기에서 **공유 구성 요소** 를 탐색 하 고 **sql server 저장소**로 이동한 다음 제거 되거나 다시 구성 된 프런트 엔드 풀과 연결 된 sql server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="7407c-109">토폴로지를 게시 한 다음 복제 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="7407c-110">SQL Server에서 사용자 및 응용 프로그램 데이터베이스를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="7407c-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="7407c-111">SQL Server에서 데이터베이스를 제거 하려면 데이터베이스 파일을 제거 하려는 SQL Server에 대 한 SQL Server sysadmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="7407c-112">Lync Server 관리 셸 열기</span><span class="sxs-lookup"><span data-stu-id="7407c-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="7407c-113">풀 사용자 저장소의 데이터베이스를 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="7407c-114">여기서 \<fqdn\> 은 데이터베이스 서버의 fqdn (정규화 된 도메인 이름)이 고 \<인스턴스\> 는 명명 된 데이터베이스 인스턴스 (즉, 정의 된 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="7407c-115">풀 응용 프로그램 저장소의 데이터베이스를 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="7407c-116">여기서 \<fqdn\> 은 데이터베이스 서버의 FQDN이 고 \<, 인스턴스\> 는 명명 된 데이터베이스 인스턴스 (즉, 정의 된 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="7407c-117">**제거-CsDataBase** cmdlet에서 작업을 확인 하 라는 메시지가 표시 되 면 정보를 읽은 다음 **Y** 키를 누르거나 enter 키를 눌러 계속 진행 하거나 **N** 키를 누른 다음 cmdlet을 중지 하려는 경우 (즉, 오류가 발생 하는 경우)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

