---
title: 프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거
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
description: 프런트 엔드 풀을 제거하거나 다른 데이터베이스를 사용하기 위해 풀을 다시 구성한 후 풀 데이터를 호스팅한 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거한 다음 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거합니다.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753410"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="3dcc1-104">프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="3dcc1-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="3dcc1-105">프런트 엔드 풀을 제거하거나 다른 데이터베이스를 사용하기 위해 풀을 다시 구성한 후 풀 데이터를 호스팅한 SQL Server 데이터베이스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc1-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="3dcc1-106">다음 절차에 따라 토폴로지 작성기에서 정의를 제거한 다음 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc1-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="3dcc1-107">토폴로지 작성기를 SQL Server 데이터베이스를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="3dcc1-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="3dcc1-108">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기 및 기존 토폴로지 다운로드</span><span class="sxs-lookup"><span data-stu-id="3dcc1-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="3dcc1-109">토폴로지 작성기에서  공유 구성 요소로 이동한 다음 저장소를 SQL Server 제거되거나 다시 구성한 프런트 엔드 풀과 연결된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭한 다음 **삭제를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc1-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="3dcc1-110">토폴로지 게시 후 복제 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc1-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="3dcc1-111">사용자 및 응용 프로그램 데이터베이스를 SQL 서버</span><span class="sxs-lookup"><span data-stu-id="3dcc1-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="3dcc1-112">SQL 서버에서 데이터베이스를 제거하려면 데이터베이스 파일을 제거할 SQL Server 서버의 SQL sysadmins 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc1-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="3dcc1-113">비즈니스용 Skype 서버 관리 셸을 여는 경우</span><span class="sxs-lookup"><span data-stu-id="3dcc1-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="3dcc1-114">풀 사용자 저장소의 데이터베이스를 제거하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc1-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="3dcc1-115">여기서 _\<FQDN\>_ 데이터베이스 서버의 FQDN(정식 도메인 이름)이고 명명된 데이터베이스 인스턴스(즉, 정의된 경우)입니다. _\<instance\>_</span><span class="sxs-lookup"><span data-stu-id="3dcc1-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="3dcc1-116">풀 응용 프로그램 저장소의 데이터베이스를 제거하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc1-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="3dcc1-117">여기서 데이터베이스 서버의 FQDN은 명명된 데이터베이스 인스턴스(즉, 정의된  _\<FQDN\>_  _\<instance\>_ 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc1-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="3dcc1-118">**Uninstall-CsDataBase** cmdlet에 작업을 확인하라는 메시지가 표시되면 정보를 읽은 다음 Y(또는 Enter)를 눌러 계속하거나 N을 누를 경우 cmdlet을 중지하려는 경우 Enter를 누를 수 있습니다(오류가 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="3dcc1-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

