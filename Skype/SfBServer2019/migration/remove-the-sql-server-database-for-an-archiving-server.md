---
title: 보관 서버용 SQL Server 데이터베이스 제거
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
description: 보관 서버를 제거한 후 풀 데이터를 호스팅한 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거한 다음 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거합니다.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753310"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="ffb14-104">보관 서버용 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="ffb14-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="ffb14-105">보관 서버를 제거한 후 풀 데이터를 호스팅한 SQL Server 데이터베이스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffb14-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="ffb14-106">다음 절차에 따라 토폴로지 작성기에서 정의를 제거한 다음 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb14-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="ffb14-107">토폴로지 작성기를 SQL Server 데이터베이스를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="ffb14-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="ffb14-108">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기 를 여는 경우</span><span class="sxs-lookup"><span data-stu-id="ffb14-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="ffb14-109">토폴로지 작성기에서  공유 구성 요소로 이동한 다음 저장소를 SQL Server 제거되거나 다시 구성된 보관 서버와 연결된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭한 다음 **삭제를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb14-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="ffb14-110">토폴로지를 게시한 후 복제 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb14-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="ffb14-111">SQL Server에서 데이터베이스 파일을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="ffb14-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="ffb14-112">SQL Server에서 데이터베이스를 제거하려면 사용자가 데이터베이스 파일을 제거하려는 SQL Server에 대해 SQL Server sysadmins 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb14-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="ffb14-113">비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffb14-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="ffb14-114">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb14-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="ffb14-115">여기서 _\<FQDN\>_ 데이터베이스 서버의 FQDN(정식 도메인 이름)이고 명명된 데이터베이스 인스턴스(즉, 정의된 경우)입니다. _\<instance\>_</span><span class="sxs-lookup"><span data-stu-id="ffb14-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="ffb14-116">**Uninstall-CsDataBase** cmdlet에 작업을 확인하라는 메시지가 표시되면 정보를 읽은 다음 Y(또는 Enter)를 눌러 계속하거나 N을 누를 경우 cmdlet을 중지하려는 경우 Enter를 누를 수 있습니다(오류가 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="ffb14-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

