---
title: 비즈니스용 Skype 서버의 보관 데이터베이스 옵션 변경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: '요약: 비즈니스용 Skype 서버에 대 한 보관 데이터베이스 옵션을 변경 하는 방법을 알아보세요.'
ms.openlocfilehash: 56aa29ef185176ce3b080572723c566455731dc4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197061"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="2b9fe-103">비즈니스용 Skype 서버의 보관 데이터베이스 옵션 변경</span><span class="sxs-lookup"><span data-stu-id="2b9fe-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="2b9fe-104">**요약:** 비즈니스용 Skype 서버에 대 한 보관 데이터베이스 옵션을 변경 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="2b9fe-105">사용자의 저장소 보관을 위해 SQL Server 저장소를 사용 하 여 보관을 배포 하는 경우 다음과 같은 데이터베이스 저장소 변경 내용을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="2b9fe-106">보관 저장소에 다른 SQL Server 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="2b9fe-107">여기에는 기본 보관 데이터베이스와 SQL Server 미러링에 사용 하는 데이터베이스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="2b9fe-108">Exchange 서버에 보관 데이터 및 파일을 저장 하려면 Microsoft Exchange 통합으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="2b9fe-109">모든 사용자가 Exchange 서버에 있고 배포의 모든 사용자에 대해 Microsoft Exchange 저장소를 사용 하려는 경우에는 토폴로지에서 SQL Server 스토어 데이터베이스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="2b9fe-110">이러한 변경 작업을 수행 하려면 토폴로지 작성기를 실행 하 고 변경한 다음 토폴로지를 다시 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="2b9fe-111">Exchange 서버에 있지 않은 비즈니스용 Skype 사용자가 없는 경우 **Sql server 저장소 보관** 을 지정 하거나 **sql server 저장소 미러링 정보를 사용 하도록 설정** 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="2b9fe-112">보관 데이터베이스 옵션 변경</span><span class="sxs-lookup"><span data-stu-id="2b9fe-112">Change Archiving database options</span></span>

1. <span data-ttu-id="2b9fe-113">비즈니스용 Skype 서버를 실행 중이거나 비즈니스용 Skype 서버 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정을 사용 하거나 해당 사용자 권한이 있는 계정으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2b9fe-114">로컬 사용자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지에 구성 요소를 추가 하는 데 필요한 토폴로지를 게시 하려면 **Domain Admins** 그룹의 구성원 인 계정과 RTCUniversalSer를 사용 해야 합니다. \*\* verAdmins\*\* 그룹과 비즈니스용 Skype Server 파일 저장소에 사용 하는 파일 공유에 대 한 모든 권한 (즉, 읽기, 쓰기 및 수정)이 있으며,이는 토폴로지 작성기가 필요한 임의 액세스 제어를 구성할 수 있도록 합니다. 목록 (Dacl) 또는 해당 권한이 있는 계정</span><span class="sxs-lookup"><span data-stu-id="2b9fe-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="2b9fe-115">토폴로지 작성기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="2b9fe-116">콘솔 트리에서 보관을 배포한 프런트 엔드 풀로 이동한 다음 데이터베이스 옵션을 변경 하려는 프런트 엔드 풀의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="2b9fe-117">**작업** 메뉴에서 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="2b9fe-118">**속성 편집** 대화 상자에서 **일반**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="2b9fe-119">아래로 스크롤하여 **보관**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="2b9fe-120">**보관**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="2b9fe-121">다른 기존 SQL Server 저장소로 변경 하려면 **Sql server Store 보관**아래에 있는 드롭다운 목록 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="2b9fe-122">기존 SQL Server 저장소를 사용 하려면 드롭다운 목록 상자에서 사용 하려는 SQL Server 저장소의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="2b9fe-123">새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 Sql server 저장소 정의** 대화 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="2b9fe-124">기존 SQL Server 저장소를 사용 하려면 드롭다운 목록 상자에서 사용 하려는 SQL Server 저장소의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="2b9fe-125">새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 Sql server 저장소 정의** 대화 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="2b9fe-126">**Sql SERVER fqdn**에서 새 SQL server 저장소를 만들 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="2b9fe-127">기본 인스턴스 \*\*\*\* 를 클릭 하 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 사용할 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="2b9fe-128">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="2b9fe-129">미러링 용 SQL Server 저장소를 추가 하거나 SQL server 스토어 미러링을 위해 다른 기존 SQL Server 저장소에 변경 하려면 **Sql server 스토어 미러링을 사용 하도록**선택 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="2b9fe-130">미러링에 대 한 기존 SQL Server 저장소를 사용 하려면 **Sql server 저장소 미러 서버 보관** 드롭다운 목록 상자에서 미러링에 사용할 SQL Server 저장소의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="2b9fe-131">미러링할 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 SQL server 저장소 정의** 대화 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="2b9fe-132">에서.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-132">a.</span></span> <span data-ttu-id="2b9fe-133">**Sql SERVER fqdn**에서 새 sql server 저장소를 만들 sql SERVER의 fqdn을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="2b9fe-134">b.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-134">b.</span></span> <span data-ttu-id="2b9fe-135">기본 인스턴스 \*\*\*\* 를 클릭 하 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 사용할 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="2b9fe-136">c.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-136">c.</span></span> <span data-ttu-id="2b9fe-137">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="2b9fe-138">SQL Server 미러링 기능을 사용 하도록 설정 하 고 SQL Server 미러링 모니터를 추가 하거나 변경 하려는 경우 (예를 들어 기본 SQL Server 서버 및 미러 인스턴스의 상태를 검색할 수 있는 별도의 SQL Server 인스턴스), **Sql server 미러링 미러링 모니터 사용을 선택 하 여 자동 장애 조치 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="2b9fe-139">에서.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-139">a.</span></span> <span data-ttu-id="2b9fe-140">**Sql SERVER fqdn**에서 새 SQL server 미러링 감시를 만들 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="2b9fe-141">b.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-141">b.</span></span> <span data-ttu-id="2b9fe-142">기본 인스턴스 \*\*\*\* 를 클릭 하 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 미러링 모니터에 사용할 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="2b9fe-143">c.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-143">c.</span></span> <span data-ttu-id="2b9fe-144">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="2b9fe-145">Exchange 서버에 보관 데이터 및 파일을 저장 하는 Microsoft Exchange 통합으로 전환 하려면 (배포의 모든 사용자가 Exchange 서버에 있는 경우) 데이터베이스 보관에 대 한 모든 정보를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="2b9fe-146">Exchange 서버에 있지 않은 비즈니스용 Skype 사용자가 있는 경우 SQL Server 스토어 정보를 삭제 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="2b9fe-147">구성을 저장 하려면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2b9fe-148">토폴로지 작성기에서 변경한 내용은 새 토폴로지를 게시할 때까지 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="2b9fe-149">자세한 내용은 [비즈니스용 Skype 서버의 기존 배포에 보관 데이터베이스 추가](../../deploy/deploy-archiving/add-archiving-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="2b9fe-150">Windows PowerShell을 사용 하 여 보관 데이터베이스의 위치 변경</span><span class="sxs-lookup"><span data-stu-id="2b9fe-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="2b9fe-151">대부분의 경우 보관 서버를 설치할 때 지정 되는 보관 데이터베이스의 위치를 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="2b9fe-152">그러나 하드웨어 오류 또는 기타 문제가 발생 하는 경우 **Set-CsArchivingServer** cmdlet을 사용 하 여 새 데이터베이스에 서버 보관을 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="2b9fe-153">다음 예에서는 ArchivingServer: atl-cs-001.contoso.com 보관 서버에 대 한 보관 데이터베이스의 위치를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="2b9fe-154">이 예제에서는 새 데이터베이스가 ArchivingDatabase: atl-sql-001.contoso.com:에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fe-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


