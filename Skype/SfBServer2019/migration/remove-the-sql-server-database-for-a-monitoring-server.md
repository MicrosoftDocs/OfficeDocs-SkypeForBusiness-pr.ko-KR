---
title: 모니터링 서버용 SQL Server 데이터베이스 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 모니터링 서버를 제거한 후에는 서버 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거 하 고 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753330"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="9be8f-104">모니터링 서버용 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="9be8f-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="9be8f-105">모니터링 서버를 제거한 후에는 서버 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be8f-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="9be8f-106">다음 절차에 따라 토폴로지 작성기에서 정의를 제거 하 고 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be8f-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="9be8f-107">토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="9be8f-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="9be8f-108">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9be8f-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="9be8f-109">토폴로지 작성기에서 **공유 구성 요소** 를 탐색 하 고 **SQL server 저장소**로 이동한 다음, 제거 되거나 다시 구성 된 모니터링 서버에 연결 된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be8f-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="9be8f-110">토폴로지를 게시한 후 복제 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9be8f-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="9be8f-111">SQL Server에서 데이터베이스 파일을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="9be8f-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="9be8f-112">SQL Server 기반 서버에서 데이터베이스를 제거 하려면 데이터베이스 파일을 제거 하려는 SQL Server 서버에 대해 SQL Server sysadmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be8f-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="9be8f-113">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9be8f-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="9be8f-114">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9be8f-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="9be8f-115">여기서 _\<FQDN\>_ 은 데이터베이스 서버의 FQDN (정규화 된 도메인 이름) 이며, _\<instance\>_ 선택적 명명 된 데이터베이스 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="9be8f-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="9be8f-116">**제거-CsDataBase** cmdlet에서 작업을 확인 하 라는 메시지가 표시 되 면 정보를 읽고, 계속 하려면 Y (또는 Enter) 키를 누르고, 오류가 있으면 enter 키를 눌러 cmdlet을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be8f-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

