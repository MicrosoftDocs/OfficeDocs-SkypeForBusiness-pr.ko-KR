---
title: 비즈니스용 Skype 서버에서 기존 배포에 보관 데이터베이스 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: '요약: 비즈니스용 Skype 서버 배포에 보관 데이터베이스를 추가 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: 2110a6c82aed473fdc07e5796075aabdb50c7086
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188481"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="6991b-103">비즈니스용 Skype 서버에서 기존 배포에 보관 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="6991b-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="6991b-104">**요약:** 비즈니스용 Skype 서버 배포에 보관 데이터베이스를 추가 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6991b-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="6991b-105">보관을 지원 하도록 배포를 구성 하려면 먼저 토폴로지에 보관을 통합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="6991b-106">이 항목의 정보는 토폴로지 작성기를 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="6991b-107">토폴로지에 보관 데이터베이스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="6991b-108">업데이트 된 토폴로지를 게시 하 여 비즈니스용 Skype 서버 배포에 보관 데이터베이스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6991b-109">Microsoft Exchange 통합을 사용 하 여 배포의 모든 사용자에 대해 Exchange 서버에 보관 데이터 및 파일을 저장 하려면 **Sql server 스토어 보관** 을 지정 하거나 **sql server 스토어 미러링** 정보를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6991b-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="6991b-110">토폴로지에 보관 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="6991b-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="6991b-111">비즈니스용 Skype 서버를 실행 중이거나 비즈니스용 Skype 서버 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정을 사용 하거나 해당 사용자 권한이 있는 계정으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="6991b-112">토폴로지 작성기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="6991b-113">콘솔 트리에서 보관을 배포 하려는 프런트 엔드 풀로 이동한 다음 보관을 배포 하려는 프런트 엔드 풀의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="6991b-114">**작업** 메뉴에서 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="6991b-115">**속성 편집** 대화 상자에서 **일반**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="6991b-116">아래로 스크롤하여 **보관**합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="6991b-117">**보관** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="6991b-118">**SQL Server 스토어 보관** 에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="6991b-119">기존 SQL Server 저장소를 사용 하려면 드롭다운 목록 상자에서 사용 하려는 SQL Server 저장소의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="6991b-120">모든 사용자가 Microsoft Exchange Server 2013 이상에 속한 경우 Exchange의 모든 사용자에 대해 비즈니스용 Skype 통신을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="6991b-121">이 경우 SQL Server 보관 저장소를 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="6991b-122">새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 Sql server 저장소 정의** 대화 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="6991b-123">**Sql SERVER fqdn**에서 새 SQL server 저장소를 만들 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="6991b-124">기본 인스턴스 \*\*\*\* 를 클릭 하 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 사용할 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="6991b-125">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="6991b-126">SQL Server 스토어 미러링을 사용 하려면 **Sql Server 저장소 미러링 사용**을 선택 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="6991b-127">미러링에 대 한 기존 SQL Server 저장소를 사용 하려면 **Sql server 저장소 미러 서버 보관** 드롭다운 목록 상자에서 미러링에 사용할 SQL Server 저장소의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="6991b-128">미러링할 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 SQL server 저장소 정의** 대화 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="6991b-129">에서.</span><span class="sxs-lookup"><span data-stu-id="6991b-129">a.</span></span> <span data-ttu-id="6991b-130">**Sql SERVER fqdn**에서 새 sql server 저장소를 만들 sql SERVER의 fqdn을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="6991b-131">b.</span><span class="sxs-lookup"><span data-stu-id="6991b-131">b.</span></span> <span data-ttu-id="6991b-132">기본 인스턴스 \*\*\*\* 를 클릭 하 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 사용할 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="6991b-133">c.</span><span class="sxs-lookup"><span data-stu-id="6991b-133">c.</span></span> <span data-ttu-id="6991b-134">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="6991b-135">SQL Server 미러링을 사용 하도록 설정 하 고 SQL Server 미러링 감시 (주요 SQL Server 및 미러 인스턴스의 상태를 검색할 수 있는 별도의 SQL Server 인스턴스)를 포함 하려면 **Sql server 미러링 미러링 모니터를 사용 하 여 자동으로 사용을 선택 합니다. 장애 조치** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="6991b-136">에서.</span><span class="sxs-lookup"><span data-stu-id="6991b-136">a.</span></span> <span data-ttu-id="6991b-137">**Sql SERVER fqdn**에서 새 SQL server 미러링 감시를 만들 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="6991b-138">b.</span><span class="sxs-lookup"><span data-stu-id="6991b-138">b.</span></span> <span data-ttu-id="6991b-139">기본 인스턴스 \*\*\*\* 를 클릭 하 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 미러링 모니터에 사용할 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="6991b-140">c.</span><span class="sxs-lookup"><span data-stu-id="6991b-140">c.</span></span> <span data-ttu-id="6991b-141">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="6991b-142">구성을 저장 하려면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="6991b-143">업데이트 된 토폴로지를 게시 하 여 배포에 보관 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="6991b-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="6991b-144">비즈니스용 Skype 서버를 실행 중이거나 비즈니스용 Skype 서버 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정을 사용 하거나 해당 사용자 권한이 있는 계정으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6991b-145">로컬 사용자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지에 서버를 추가 하는 데 필요한 토폴로지를 게시 하려면 **Domain Admins** 그룹의 구성원 인 계정 및 RTCUniversalServer을 사용 해야 합니다. \*\* \*\*관리 그룹과 비즈니스용 Skype 서버 파일 저장소에 사용 하는 파일 공유에 대 한 모든 권한 (읽기, 쓰기 및 수정)이 있으며,이는 토폴로지 작성기가 필요한 dacl (임의 액세스 제어 목록)을 구성할 수 있도록 합니다. 해당 권한이 있는 계정</span><span class="sxs-lookup"><span data-stu-id="6991b-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="6991b-146">토폴로지 작성기를 사용 하 여 이전 섹션에서 만든 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="6991b-147">콘솔 트리에서 **비즈니스용 Skype 서버**를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="6991b-148">**토폴로지 게시** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="6991b-149">**데이터베이스 만들기** 페이지에서 데이터베이스가 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6991b-150">데이터베이스를 만들 수 있는 적절 한 권한이 없는 경우 데이터베이스 선택을 취소 하 고 적절 한 권한이 있는 다른 사용자가 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="6991b-151">> 전용 SQL 서버의 데이터베이스만 토폴로지 작성기를 사용 하 여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="6991b-152">다른 서버 구성 요소와 collocated는 SQL 서버의 데이터베이스는 해당 컴퓨터에서 로컬 설정을 실행 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="6991b-153">**게시 마법사 완료** 페이지에서 토폴로지가 성공적으로 게시 되었는지 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6991b-154">토폴로지를 게시 한 후에는 콘텐츠를 보관 하기 전에 보관을 위한 옵션과 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6991b-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="6991b-155">자세한 내용은 비즈니스용 [Skype 서버에 대 한 보관 옵션 구성](configure-archiving-options.md) 및 비즈니스용 [skype 서버에 대 한 보관 정책 구성을](configure-archiving-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6991b-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

