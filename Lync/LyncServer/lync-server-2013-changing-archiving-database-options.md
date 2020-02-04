---
title: 'Lync Server 2013: 보관 데이터베이스 옵션 변경'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198e2abff6118197167f0f017ace22fc2ad76381
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="9377a-102">Lync Server 2013에서 데이터베이스 보관 옵션 변경</span><span class="sxs-lookup"><span data-stu-id="9377a-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9377a-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9377a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9377a-104">사용자의 저장소 보관을 위해 SQL Server 저장소를 사용 하 여 보관을 배포 하는 경우 다음과 같은 데이터베이스 저장소 변경 내용을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="9377a-105">보관 저장소에 다른 SQL Server 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="9377a-106">여기에는 기본 보관 데이터베이스와 SQL Server 미러링에 사용 하는 데이터베이스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="9377a-107">Exchange 2013 서버에 보관 데이터 및 파일을 저장 하려면 Microsoft Exchange 통합으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="9377a-108">모든 사용자가 Exchange 2013 서버에 있고 배포의 모든 사용자에 대해 Microsoft Exchange 저장소를 사용 하려는 경우에는 토폴로지에서 SQL Server 스토어 데이터베이스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="9377a-109">이러한 변경 작업을 수행 하려면 토폴로지 작성기를 실행 하 고 변경한 다음 토폴로지를 다시 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="9377a-110">토폴로지 작성기를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="9377a-111">Exchange 2013 서버에 있지 않은 Lync 사용자가 없는 경우 **Sql server 저장소 보관** 을 지정 하거나 **sql server 저장소 미러링 정보를 사용 하도록 설정** 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9377a-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="9377a-112">보관 데이터베이스 옵션을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="9377a-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="9377a-113">Lync Server 2013을 실행 중이거나 Lync Server 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정이 나 해당 사용자 권한이 있는 계정으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9377a-114">로컬 사용자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지에 구성 요소를 추가 하는 데 필요한 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정을 사용 해야 하며, Lync Server 2013 파일 저장소에 사용 하는 파일 공유에 대 한 모든 권한 (즉, 읽기, 쓰기 및 수정)이 있는 경우 (즉, 토폴로지 작성기가 필요한 임의 액세스 제어 목록을 구성할 수 있도록 합니다. Dacl) 또는 해당 권한이 있는 계정</span><span class="sxs-lookup"><span data-stu-id="9377a-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="9377a-115">토폴로지 작성기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="9377a-116">콘솔 트리에서 보관을 배포한 프런트 엔드 풀로 이동한 다음 데이터베이스 옵션을 변경 하려는 프런트 엔드 풀의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="9377a-117">**작업** 메뉴에서 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="9377a-118">**속성 편집** 대화 상자에서 **일반**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="9377a-119">아래로 스크롤하여 **보관**합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="9377a-120">**보관**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="9377a-121">다른 기존 SQL Server 저장소로 변경 하려면 **Sql server Store 보관**아래에 있는 드롭다운 목록 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="9377a-122">기존 SQL Server 저장소를 사용 하려면 드롭다운 목록 상자에서 사용 하려는 SQL Server 저장소의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="9377a-123">새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 Sql server 저장소 정의** 대화 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="9377a-124">기존 SQL Server 저장소를 사용 하려면 드롭다운 목록 상자에서 사용 하려는 SQL Server 저장소의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="9377a-125">새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 Sql server 저장소 정의** 대화 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="9377a-126">**Sql SERVER fqdn**에서 새 SQL server 저장소를 만들 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="9377a-127">기본 인스턴스 **를 클릭 하** 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 사용할 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="9377a-128">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="9377a-129">미러링 용 SQL Server 저장소를 추가 하거나 SQL server 스토어 미러링을 위해 다른 기존 SQL Server 저장소에 변경 하려면 **Sql server 스토어 미러링을 사용 하도록**선택 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="9377a-130">미러링에 대 한 기존 SQL Server 저장소를 사용 하려면 **Sql server 저장소 미러 서버 보관** 드롭다운 목록 상자에서 미러링에 사용할 SQL Server 저장소의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="9377a-131">미러링할 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 한 다음 **새 SQL server 저장소 정의** 대화 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="9377a-132">**Sql SERVER fqdn**에서 새 sql server 저장소를 만들 sql SERVER의 fqdn을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="9377a-133">기본 인스턴스 **를 클릭 하** 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 사용할 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="9377a-134">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="9377a-135">SQL Server 미러링 기능을 사용 하도록 설정 하 고 SQL Server 미러링 모니터를 추가 하거나 변경 하려면 (기본 SQL Server server 서버와 미러 인스턴스의 상태를 검색할 수 있는 별도의 SQL Server 인스턴스), **Sql server 미러링 미러링 모니터를 사용 하 여 자동 장애 조치 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="9377a-136">**Sql SERVER fqdn**에서 새 SQL server 미러링 감시를 만들 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="9377a-137">기본 인스턴스 **를 클릭 하** 여 기본 인스턴스를 사용 하거나 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 클릭 한 다음 미러링 모니터에 사용할 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="9377a-138">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스는 미러링 관계에 있는** 확인란을 선택한 다음 **미러 포트 번호**에서 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="9377a-139">Exchange 2013 서버에 보관 데이터 및 파일을 저장 하는 Microsoft Exchange 통합으로 전환 하려면 (배포의 모든 사용자가 Exchange 2013 서버에 속한 경우) 데이터베이스 보관을 위한 모든 정보를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9377a-140">Exchange 2013 서버에 홈이 아닌 Lync 사용자가 있는 경우 SQL Server 저장소 정보를 삭제 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9377a-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="9377a-141">구성을 저장 하려면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9377a-142">토폴로지 작성기에서 변경한 내용은 새 토폴로지를 게시할 때까지 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9377a-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="9377a-143">자세한 내용은 배포 설명서의 <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Lync Server 2013에서 보관 데이터베이스 추가를 위해 업데이트 된 토폴로지 게시를</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9377a-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

