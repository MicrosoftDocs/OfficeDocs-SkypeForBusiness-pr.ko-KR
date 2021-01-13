---
title: 비즈니스용 Skype 서버에서 기존 배포에 보관 데이터베이스 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: '요약: 이 항목을 읽고 보관 데이터베이스를 비즈니스용 Skype 서버 배포에 추가하는 방법을 설명합니다.'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820678"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="a8718-103">비즈니스용 Skype 서버에서 기존 배포에 보관 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="a8718-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="a8718-104">**요약:** 이 항목을 읽고 보관 데이터베이스를 비즈니스용 Skype 서버 배포에 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="a8718-105">보관을 지원하도록 배포를 구성하려면 먼저 토폴로지에 보관을 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="a8718-106">이 항목의 정보는 토폴로지 작성기에서 다음을 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="a8718-107">토폴로지에 보관 데이터베이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="a8718-108">업데이트된 토폴로지 게시를 통해 보관 데이터베이스를 비즈니스용 Skype 서버 배포에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a8718-109">Microsoft Exchange 통합을 사용하여 배포의 모든 사용자에 대해 Exchange 서버에 보관 데이터 및 파일을  저장하려면 보관 저장소 또는 SQL Server 저장소 미러링 SQL Server 지정하지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="a8718-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="a8718-110">토폴로지에 보관 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="a8718-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="a8718-111">비즈니스용 Skype 서버를 실행하는 컴퓨터 또는 비즈니스용 Skype 서버 관리 도구가 설치된 컴퓨터에서 로컬 Users 그룹의 구성원인 계정(또는 동등한 사용자 권한을 가지는 계정)을 사용하여 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="a8718-112">토폴로지 작성기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="a8718-113">콘솔 트리에서 보관을 배포할 프런트 엔드 풀로 이동한 다음 보관을 배포할 프런트 엔드 풀의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="a8718-114">**동작** 메뉴에서 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="a8718-115">**속성 편집** 대화 상자에서 **일반** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="a8718-116">아래쪽의 **보관** 으로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="a8718-117">**보관** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="a8718-118">보관 **SQL Server 저장소에서 다음** 중 하나를 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="a8718-119">기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="a8718-120">모든 사용자가 Microsoft Exchange Server 2013 이상에 있는 경우 Exchange의 모든 사용자에 대한 비즈니스용 Skype 통신을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="a8718-121">이 경우 보관 저장소를 구성할 SQL Server 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="a8718-122">새 SQL Server 저장소를 지정하려면 새로하기를 클릭한 다음 새 SQL Server **저장소** 정의 대화 상자에서 다음을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="a8718-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="a8718-123">FQDN의 SQL Server 저장소를 만들 서버의 **FQDN을** SQL Server 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="a8718-124">**기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 사용할 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="a8718-125">지정된 SQL Server 인스턴스가 미러링 관계에 있는 경우  이 SQL 인스턴스가 미러링 관계 확인란에 있는 경우 미러 포트 번호에서 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="a8718-126">저장소 미러링을 SQL Server 사용하려면 SQL Server 저장소 미러링 **사용을** 선택하고 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="a8718-127">기존 SQL Server 저장소를 미러링에 사용하려면  보관 SQL Server 저장소 미러 드롭다운 목록 상자에서 미러링에 사용할 SQL Server 저장소의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="a8718-128">미러링에 사용할 새 SQL Server 저장소를 지정하려면 새로 고침을 클릭한 다음 새 SQL Server 저장소 정의 **대화** 상자에서 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="a8718-129">a.</span><span class="sxs-lookup"><span data-stu-id="a8718-129">a.</span></span> <span data-ttu-id="a8718-130">FQDN의 SQL Server 저장소를 만들 SQL Server **FQDN을** SQL Server 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="a8718-131">b.</span><span class="sxs-lookup"><span data-stu-id="a8718-131">b.</span></span> <span data-ttu-id="a8718-132">**기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 사용할 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="a8718-133">c.</span><span class="sxs-lookup"><span data-stu-id="a8718-133">c.</span></span> <span data-ttu-id="a8718-134">지정한 SQL Server 인스턴스가 미러링 관계에 있는  경우 이 SQL 인스턴스가 미러링 관계 확인란에 있는 경우 미러 포트 번호에서 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="a8718-135">SQL Server 미러링을 사용하도록 설정하고 SQL Server 미러링 서버(기본 SQL Server 및 미러 인스턴스의 상태 검색이 가능하도록 별도의 세 번째 SQL Server 인스턴스)를 포함하려면 SQL Server 미러링크 사용 확인란을 선택하고 다음 중 하나를 수행하십시오. </span><span class="sxs-lookup"><span data-stu-id="a8718-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="a8718-136">a.</span><span class="sxs-lookup"><span data-stu-id="a8718-136">a.</span></span> <span data-ttu-id="a8718-137">FQDN을 SQL Server 새 미러링 SQL Server 만들 서버의 **FQDN을** 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="a8718-138">b.</span><span class="sxs-lookup"><span data-stu-id="a8718-138">b.</span></span> <span data-ttu-id="a8718-139">**기본 인스턴스** 를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 클릭하고 미러링 모니터 서버에 사용할 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="a8718-140">c.</span><span class="sxs-lookup"><span data-stu-id="a8718-140">c.</span></span> <span data-ttu-id="a8718-141">지정된 SQL Server 인스턴스가 미러링 관계에 있는 경우  이 SQL 인스턴스가 미러링 관계 확인란에 있는 경우 미러 포트 번호에서 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="a8718-142">구성을 저장하려면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="a8718-143">업데이트된 토폴로지 게시를 통해 배포에 보관 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="a8718-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="a8718-144">비즈니스용 Skype 서버를 실행하는 컴퓨터 또는 비즈니스용 Skype 서버 관리 도구가 설치된 컴퓨터에서 로컬 Users 그룹의 구성원인 계정(또는 동등한 사용자 권한을 가지는 계정)을 사용하여 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a8718-145">로컬 Users 그룹의 구성원이지만 토폴로지 게시를 위해 계정을 사용하여 토폴로지 정의할 수 있습니다. 토폴로지 작성기에서 필요한 경우 **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원인 계정을 사용하고 비즈니스용 Skype 서버 파일 저장소에 사용중인 파일 공유에 대한 모든 권한(읽기, 쓰기 및 수정)을 가진 계정을 사용(토폴로지 작성기에서 필요한 DACL(사용자 지정 액세스 제어 목록)을 구성할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="a8718-146">토폴로지 작성기에서 이전 섹션에서 만든 토폴로지 열기</span><span class="sxs-lookup"><span data-stu-id="a8718-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="a8718-147">콘솔 트리에서 비즈니스용 **Skype** 서버를 마우스 오른쪽 단추로 클릭한 다음 토폴로지 **게시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8718-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="a8718-148">**토폴로지 게시** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="a8718-149">**데이터베이스 만들기** 페이지에서 데이터베이스가 선택되었는지 확인하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a8718-150">데이터베이스를 만드는 데 적합한 권한이 없으면 데이터베이스 선택을 취소하고 적합한 권한이 있는 다른 사용자가 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="a8718-151">> 토폴로지 작성기에서 전용 SQL 서버의 데이터베이스만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="a8718-152">다른 서버 구성 요소와 함께 배치된 SQL Server의 데이터베이스는 해당 컴퓨터의 로컬 설정을 실행하여 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="a8718-153">**게시 마법사 완료** 페이지에서 토폴로지가 게시되었는지 확인하고 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a8718-154">토폴로지를 게시한 후 콘텐츠를 보관할 수 있으려면 먼저 보관에 대한 옵션 및 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8718-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="a8718-155">자세한 내용은 비즈니스용 Skype 서버에 대한 보관 옵션 구성 및 비즈니스용 [Skype](configure-archiving-options.md) 서버에 대한 보관 정책 [구성을 참조하세요.](configure-archiving-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a8718-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

