---
title: 'Lync Server 2013: Lync Server 2013 토폴로지에 보관 데이터베이스 추가'
description: 'Lync Server 2013: Lync Server 2013 토폴로지에 보관 데이터베이스를 추가 하는 중입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12387c06bc55775ef824c061228a68021046c113
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573046"
---
# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="a849d-103">Lync Server 2013 토폴로지에 보관 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="a849d-103">Adding Archiving databases to the Lync Server 2013 topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a849d-104">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="a849d-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="a849d-105">보관을 지원하도록 배포를 구성하려면 먼저 토폴로지에 보관을 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="a849d-106">이 항목의 정보에서는 토폴로지 작성기를 사용 하 여 기존 토폴로지에 보관을 추가 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-106">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a849d-107">Microsoft Exchange 통합을 사용 하 여 배포의 모든 사용자에 대해 Exchange 2013 서버에 보관 데이터 및 파일을 저장 하려면 <STRONG>보관 Sql server 저장소</STRONG> 를 지정 하거나 <STRONG>sql server 저장소 미러링</STRONG> 정보를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a849d-107">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="a849d-108">토폴로지에 보관 데이터베이스 지원을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a849d-108">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="a849d-109">Lync Server 2013을 실행 중이거나 Lync Server 관리 도구가 설치 된 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정 또는 이와 동등한 사용자 권한을 가진 계정을 사용 하 여 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-109">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a849d-110">로컬 Users 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지에 서버를 추가 하는 데 필요한 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정을 사용 해야 합니다. 여기에는 Lync server 2013 파일 저장소에 사용 하는 파일 공유에 대 한 모든 권한 (읽기, 쓰기 및 수정)이 있으며, 토폴로지 작성기가 필요한 dacl (임의 액세스 제어 목록)을 구성할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-110">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="a849d-111">토폴로지 작성기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-111">Start Topology Builder.</span></span>

3.  <span data-ttu-id="a849d-112">콘솔 트리에서 보관을 배포할 프런트 엔드 풀로 이동한 다음 보관을 배포할 프런트 엔드 풀의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-112">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="a849d-113">**동작** 메뉴에서 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-113">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="a849d-114">**속성 편집** 대화 상자에서 **일반**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-114">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="a849d-115">아래쪽의 **보관**으로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-115">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="a849d-116">**보관** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-116">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="a849d-117">**SQL Server 저장소 보관** 에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-117">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="a849d-118">기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-118">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="a849d-119">모든 사용자가 Microsoft Exchange Server 2013 이상에 있는 경우 Exchange의 모든 사용자에 대 한 Lync 통신을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-119">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="a849d-120">이 경우 SQL Server 보관 저장소를 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-120">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="a849d-121">새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 하 고 **새 Sql server 저장소 정의** 대화 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-121">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="a849d-122">**Sql SERVER fqdn**에서 새 SQL Server 저장소를 만들 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-122">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="a849d-123">**기본 인스턴스**를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 클릭하고 사용할 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-123">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="a849d-124">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스가 미러링 관계에** 있습니다. 확인란을 선택한 다음 **미러 포트 번호**에 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-124">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="a849d-125">SQL Server 저장소 미러링을 사용 하려면 **Sql Server 저장소 미러링 사용**을 선택 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-125">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="a849d-126">미러링에 대해 기존 SQL Server 저장소를 사용 하려면 **보관 SQL server 저장소 미러** 드롭다운 목록 상자에서 미러링에 사용할 sql Server 저장소의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-126">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="a849d-127">미러링 용으로 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 하 고 **새 SQL server 저장소 정의** 대화 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-127">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="a849d-128">**Sql SERVER fqdn**에서 새 sql server 저장소를 만들 sql SERVER의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-128">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="a849d-129">**기본 인스턴스**를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 클릭하고 사용할 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-129">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="a849d-130">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스가 미러링 관계에** 있습니다. 확인란을 선택한 다음 **미러 포트 번호**에 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-130">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="a849d-131">SQL Server 미러링을 사용 하도록 설정 하 고 SQL Server 미러링 모니터 서버를 포함 하려면 (기본 SQL Server server 및 미러 인스턴스의 상태를 검색할 수 있는 세 개의 별도 SQL Server 인스턴스), **Sql server 미러링 모니터 서버가 자동 장애 조치 (failover** )를 사용 하도록 설정 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-131">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="a849d-132">**Sql SERVER fqdn**에서 새 SQL Server 미러링 모니터 서버를 만들 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-132">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="a849d-133">**기본 인스턴스**를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 클릭하고 미러링 모니터 서버에 사용할 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="a849d-134">지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스가 미러링 관계에** 있습니다. 확인란을 선택한 다음 **미러 포트 번호**에 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="a849d-135">구성을 저장하려면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a849d-135">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

