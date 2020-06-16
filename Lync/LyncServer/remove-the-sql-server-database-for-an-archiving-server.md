---
title: 보관 서버용 SQL Server 데이터베이스 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c84c15aea6be5ddcc30c357fec5971bf9786c25
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="334c8-102">보관 서버용 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="334c8-102">Remove the SQL Server database for an Archiving server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="334c8-103">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="334c8-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="334c8-104">Microsoft Lync Server 2010 보관 서버를 제거한 후에는 해당 풀 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="334c8-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="334c8-105">다음 절차에 따라 토폴로지 작성기에서 정의를 제거 하 고 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="334c8-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="334c8-106">토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="334c8-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="334c8-107">Lync Server 2013 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="334c8-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="334c8-108">토폴로지 작성기에서 **공유 구성 요소** 를 탐색 하 고 **SQL server 저장소**로 이동한 후 제거 되거나 다시 구성 된 보관 서버와 연결 된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="334c8-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="334c8-109">토폴로지를 게시한 후 복제 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="334c8-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="334c8-110">SQL Server에서 데이터베이스 파일을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="334c8-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="334c8-111">SQL Server에서 데이터베이스를 제거하려면 사용자가 데이터베이스 파일을 제거하려는 SQL Server에 대해 SQL Server sysadmins 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="334c8-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="334c8-112">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="334c8-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="334c8-113">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="334c8-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="334c8-114">여기서 \<FQDN\> 은 데이터베이스 서버의 FQDN (정규화 된 도메인 이름) 이며, \<instance\> 명명 된 데이터베이스 인스턴스 (즉, 정의 된 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="334c8-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="334c8-115">**Uninstall-CsDataBase** cmdlet에서 작업을 확인하라는 메시지가 표시되면 해당 정보를 읽고, 계속하려면 **Y**(또는 Enter 키)를 누르고, cmdlet을 중지하려면 **N**을 누른 후 Enter 키를 누릅니다(즉, 오류가 있을 경우에 대비하여).</span><span class="sxs-lookup"><span data-stu-id="334c8-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

