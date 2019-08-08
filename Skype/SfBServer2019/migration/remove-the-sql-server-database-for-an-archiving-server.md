---
title: 보관 서버용 SQL Server 데이터베이스 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 보관 서버를 제거한 후에는 풀 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다. 토폴로지 작성기에서 정의를 제거 하려면 다음 절차를 사용 하 여 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.
ms.openlocfilehash: ab76c8ebc629206827be0a4c0a5477eff54a0923
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241816"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="b07ff-104">보관 서버용 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="b07ff-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="b07ff-105">보관 서버를 제거한 후에는 풀 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07ff-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="b07ff-106">토폴로지 작성기에서 정의를 제거 하려면 다음 절차를 사용 하 여 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ff-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="b07ff-107">토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="b07ff-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="b07ff-108">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b07ff-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="b07ff-109">토폴로지 작성기에서 **공유 구성 요소** 를 탐색 하 고 **sql server 저장소**로 이동한 다음 제거 되거나 다시 구성 된 보관 서버와 연결 된 sql server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ff-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="b07ff-110">토폴로지를 게시 한 다음 복제 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ff-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="b07ff-111">SQL Server에서 데이터베이스 파일을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="b07ff-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="b07ff-112">SQL Server에서 데이터베이스를 제거 하려면 데이터베이스 파일을 제거 하려는 SQL Server에 대 한 SQL Server sysadmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ff-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="b07ff-113">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b07ff-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="b07ff-114">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ff-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="b07ff-115">여기서 _ \<fqdn\> _ 은 데이터베이스 서버의 fqdn (정규화 된 도메인 이름)이 고 _ \<인스턴스\> _ 는 명명 된 데이터베이스 인스턴스 (즉, 정의 된 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="b07ff-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="b07ff-116">**제거-CsDataBase** cmdlet에서 작업을 확인 하 라는 메시지가 표시 되 면 정보를 읽은 다음 Y (또는 enter) 키를 눌러 계속 진행 하거나 N 키를 누른 다음 cmdlet을 중지 하려는 경우 (오류가 있는 경우)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ff-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

