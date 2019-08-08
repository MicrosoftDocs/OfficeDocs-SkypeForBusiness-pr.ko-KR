---
title: 프런트 엔드 풀에 대 한 SQL Server 데이터베이스 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 프런트 엔드 풀을 제거 하거나 다른 데이터베이스를 사용 하도록 풀을 다시 구성한 후에는 풀 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다. 토폴로지 작성기에서 정의를 제거 하려면 다음 절차를 사용 하 여 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.
ms.openlocfilehash: d22a90401bdfa4a2897a18805e8b9c588892c5fb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241841"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="96b66-104">프런트 엔드 풀에 대 한 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="96b66-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="96b66-105">프런트 엔드 풀을 제거 하거나 다른 데이터베이스를 사용 하도록 풀을 다시 구성한 후에는 풀 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="96b66-106">토폴로지 작성기에서 정의를 제거 하려면 다음 절차를 사용 하 여 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="96b66-107">토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="96b66-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="96b66-108">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기를 열고 기존 토폴로지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="96b66-109">토폴로지 작성기에서 **공유 구성 요소** 를 탐색 하 고 **sql server 저장소**로 이동한 다음 제거 되거나 다시 구성 된 프런트 엔드 풀과 연결 된 sql server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="96b66-110">토폴로지를 게시 한 다음 복제 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="96b66-111">SQL server에서 사용자 및 응용 프로그램 데이터베이스를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="96b66-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="96b66-112">SQL server에서 데이터베이스를 제거 하려면 데이터베이스 파일을 제거 하려는 SQL server에 대 한 SQL Server sysadmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="96b66-113">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="96b66-114">풀 사용자 저장소의 데이터베이스를 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-114">To remove the database for the pool user store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="96b66-115">여기서 _ \<fqdn\> _ 은 데이터베이스 서버의 fqdn (정규화 된 도메인 이름)이 고 _ \<인스턴스\> _ 는 명명 된 데이터베이스 인스턴스 (즉, 정의 된 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="96b66-116">풀 응용 프로그램 저장소의 데이터베이스를 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-116">To remove the database for the pool application store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="96b66-117">여기서 _ \<fqdn\> _ 은 데이터베이스 서버의 FQDN이 고 _ \<, 인스턴스\> _ 는 명명 된 데이터베이스 인스턴스 (즉, 정의 된 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="96b66-118">**제거-CsDataBase** cmdlet에서 작업을 확인 하 라는 메시지가 표시 되 면 정보를 읽은 다음 Y (또는 enter) 키를 눌러 계속 진행 하거나 N 키를 누른 다음 cmdlet을 중지 하려는 경우 (오류가 있는 경우)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b66-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

