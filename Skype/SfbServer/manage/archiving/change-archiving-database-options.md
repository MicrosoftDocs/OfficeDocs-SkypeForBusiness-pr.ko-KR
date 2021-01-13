---
title: 비즈니스용 Skype 서버에서 보관 데이터베이스 옵션 변경
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: '요약: 비즈니스용 Skype 서버의 보관 데이터베이스 옵션을 변경하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817698"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="367f8-103">비즈니스용 Skype 서버에서 보관 데이터베이스 옵션 변경</span><span class="sxs-lookup"><span data-stu-id="367f8-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="367f8-104">**요약:** 비즈니스용 Skype 서버의 보관 데이터베이스 옵션을 변경하는 방법을 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="367f8-105">사용자에 대해 보관 저장소에 SQL Server 저장소를 사용하여 보관을 배포하는 경우 다음과 같은 데이터베이스 저장소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="367f8-106">보관 저장소에 다른 SQL Server 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="367f8-107">여기에는 기본 보관 데이터베이스와 기본 미러링에 사용하는 SQL Server 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="367f8-108">Microsoft Exchange 통합으로 전환하여 Exchange 서버에 보관 데이터 및 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="367f8-109">모든 사용자가 Exchange 서버에 있으며 배포의 모든 사용자에 대해 Microsoft Exchange 저장소를 사용하려는 경우 토폴로지에서 SQL Server 저장소 데이터베이스를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="367f8-110">이러한 변경 내용을 적용하려면 토폴로지 작성기에서 변경한 다음 토폴로지 다시 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="367f8-111">Exchange 서버에  SQL Server 비즈니스용 Skype 사용자가  있는 경우를 SQL Server 미러링 정보를 저장하도록 설정하거나 보관 저장소를 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="367f8-112">보관 데이터베이스 옵션 변경</span><span class="sxs-lookup"><span data-stu-id="367f8-112">Change Archiving database options</span></span>

1. <span data-ttu-id="367f8-113">비즈니스용 Skype 서버를 실행하는 컴퓨터 또는 비즈니스용 Skype 서버 관리 도구가 설치된 컴퓨터에서 로컬 Users 그룹의 구성원인 계정(또는 동등한 사용자 권한을 가지는 계정)을 사용하여 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="367f8-114">로컬 Users 그룹의 구성원인 계정을 사용하여 토폴로지 정의할 수 있지만 토폴로지 게시를 위해 토폴로지(토폴로지에 구성 요소를 추가하는 데 필요) **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원인 계정을 사용하고 비즈니스용 Skype 서버 파일 저장소에 사용하는 파일 공유에 대한 모든 권한(즉, 읽기, 쓰기 및 수정)을 가진 계정을 사용하거나 토폴로지 작성기에서 필요한 DACL(사용자 지정 액세스 제어 목록)을 구성할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="367f8-115">토폴로지 작성기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="367f8-116">콘솔 트리에서 보관을 배포한 프런트 엔드 풀로 이동한 다음 데이터베이스 옵션을 변경할 프런트 엔드 풀의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="367f8-117">**동작** 메뉴에서 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="367f8-118">**속성 편집** 대화 상자에서 **일반** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="367f8-119">아래쪽의 **보관** 으로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="367f8-120">**보관** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="367f8-121">다른 기존 SQL Server 저장소로 변경하려면 **보관 SQL Server 저장소** 아래 드롭다운 목록 상자에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="367f8-122">기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="367f8-123">새 SQL Server 저장소를 지정하려면 **새로 만들기** 를 클릭하고 **새 SQL Server 저장소 정의** 대화 상자에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="367f8-124">기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="367f8-125">새 SQL Server 저장소를 지정하려면 새로하기를 클릭한 다음 새 SQL Server **저장소** 정의 대화 상자에서 다음을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="367f8-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="367f8-126">FQDN의 SQL Server 저장소를 만들 서버의 **FQDN을** SQL Server 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="367f8-127">**기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 사용할 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="367f8-128">지정한 SQL Server 인스턴스가 미러링 관계에 있는  경우 이 SQL 인스턴스가 미러링 관계 확인란에 있는 경우 미러 포트 번호에서 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="367f8-129">미러링용으로 SQL Server 저장소를 추가하거나 SQL Server 저장소 미러링을 위해 다른 기존 SQL Server 저장소로 변경하려면 **SQL Server 저장소 미러링 사용** 을 선택하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="367f8-130">기존 SQL Server 저장소를 미러링에 사용하려면  보관 SQL Server 저장소 미러 드롭다운 목록 상자에서 미러링에 사용할 SQL Server 저장소의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="367f8-131">미러링에 SQL Server 새 저장소를 지정하려면 새로 고침을 클릭한 다음 새 SQL Server 저장소 정의 **대화** 상자에서 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="367f8-132">a.</span><span class="sxs-lookup"><span data-stu-id="367f8-132">a.</span></span> <span data-ttu-id="367f8-133">FQDN의 SQL Server 저장소를 만들 SQL Server **FQDN을** SQL Server 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="367f8-134">b.</span><span class="sxs-lookup"><span data-stu-id="367f8-134">b.</span></span> <span data-ttu-id="367f8-135">**기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 사용할 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="367f8-136">c.</span><span class="sxs-lookup"><span data-stu-id="367f8-136">c.</span></span> <span data-ttu-id="367f8-137">지정한 SQL Server 인스턴스가 미러링 관계에 있는  경우 이 SQL 인스턴스가 미러링 관계 확인란에 있는 경우 미러 포트 번호에서 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="367f8-138">SQL Server 미러링을 사용하도록 설정하고 SQL Server 미러링크를 추가하거나 변경하려면(주 SQL Server 서버 및 미러 인스턴스의 상태 검색이 가능하도록 별도의 세 번째  SQL Server 인스턴스) SQL Server 미러링크 사용 확인란을 선택하고 다음 중 하나를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="367f8-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="367f8-139">a.</span><span class="sxs-lookup"><span data-stu-id="367f8-139">a.</span></span> <span data-ttu-id="367f8-140">FQDN을 SQL Server 새 미러링 SQL Server 만들 서버의 **FQDN을** 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="367f8-141">b.</span><span class="sxs-lookup"><span data-stu-id="367f8-141">b.</span></span> <span data-ttu-id="367f8-142">**기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 미러링 모니터 서버에 사용할 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="367f8-143">c.</span><span class="sxs-lookup"><span data-stu-id="367f8-143">c.</span></span> <span data-ttu-id="367f8-144">지정한 SQL Server 인스턴스가 미러링 관계에 있는  경우 이 SQL 인스턴스가 미러링 관계 확인란에 있는 경우 미러 포트 번호에서 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="367f8-145">Microsoft Exchange 통합으로 전환하여 Exchange 서버에 보관 데이터 및 파일을 저장하려면(배포의 모든 사용자가 Exchange 서버에 있는 경우) 보관 데이터베이스에 대한 모든 정보를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="367f8-146">Exchange 서버에 있지 않은 비즈니스용 Skype 사용자가 있는 경우 저장소 정보를 삭제하지 SQL Server 않습니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="367f8-147">구성을 저장하려면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="367f8-148">토폴로지 작성기에서 변경한 내용은 새 토폴로지 게시 전까지는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="367f8-149">자세한 내용은 비즈니스용 Skype 서버에서 기존 배포에 보관 데이터베이스 [추가를 참조하세요.](../../deploy/deploy-archiving/add-archiving-databases.md)</span><span class="sxs-lookup"><span data-stu-id="367f8-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="367f8-150">보관 데이터베이스의 위치를 변경하려면 다음을 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="367f8-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="367f8-151">대부분의 경우 보관 서버를 설치할 때 지정된 보관 데이터베이스의 위치를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="367f8-152">그러나 하드웨어 오류 또는 기타 문제가 발생할 경우 **Set-CsArchivingServer** cmdlet을 사용하여 보관 서버를 새 데이터베이스로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="367f8-153">다음 예제에서는 보관 서버:atl-cs-001.contoso.com 보관 데이터베이스의 위치를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="367f8-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="367f8-154">이 예제에서 새 데이터베이스는 ArchivingDatabase:atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="367f8-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


