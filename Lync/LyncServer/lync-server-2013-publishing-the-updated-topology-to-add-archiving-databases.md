---
title: 'Lync Server 2013: 업데이트 된 토폴로지를 게시 하 여 보관 데이터베이스 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5834c6c7d0386f7943c523a184ea63f8ba129a89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512245"
---
# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="5a6c1-102">Lync Server 2013에서 보관 데이터베이스를 추가 하도록 업데이트 된 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="5a6c1-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a6c1-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5a6c1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5a6c1-104">토폴로지 작성기에서 토폴로지를 업데이트 한 후에는 보관을 구성 및 사용 하기 전에 토폴로지를 중앙 관리 저장소에 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="5a6c1-105">모든 서버를 토폴로지 및 기타 구성 변경 내용과 동기화된 상태로 유지하기 위해 데이터의 읽기 전용 복사본이 토폴로지의 모든 서버에 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="5a6c1-106">업데이트된 토폴로지를 게시하려면</span><span class="sxs-lookup"><span data-stu-id="5a6c1-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="5a6c1-107">Lync Server 2013을 실행 중이거나 Lync Server 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정 또는 이와 동등한 사용자 권한이 있는 계정으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a6c1-108">로컬 Users 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지에 서버를 추가 하는 데 필요한 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정을 사용 해야 합니다. 여기에는 Lync server 2013 파일 저장소에 사용 하는 파일 공유에 대 한 모든 권한 (읽기, 쓰기 및 수정)이 있으며, 토폴로지 작성기가 필요한 dacl (임의 액세스 제어 목록)을 구성할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="5a6c1-109">토폴로지 작성기를 사용 하 여 이전 섹션에서 만든 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="5a6c1-110">콘솔 트리에서 **Lync Server 2013**를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="5a6c1-111">**토폴로지 게시** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="5a6c1-112">**데이터베이스 만들기** 페이지에서 데이터베이스가 선택되었는지 확인하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a6c1-113">데이터베이스를 만드는 데 적합한 권한이 없으면 데이터베이스 선택을 취소하고 적합한 권한이 있는 다른 사용자가 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="5a6c1-114">필요한 관리자 권한 및 사용 권한에 대 한 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013의 SQL Server에 대 한 배포 권한을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="5a6c1-115">전용 SQL Server 서버의 데이터베이스만 토폴로지 작성기를 사용 하 여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="5a6c1-116">다른 서버 구성 요소와 배치 된 SQL Server 서버의 데이터베이스는 해당 컴퓨터에서 로컬 설치 프로그램을 실행 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="5a6c1-117">**게시 마법사 완료** 페이지에서 토폴로지가 게시되었는지 확인하고 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5a6c1-118">토폴로지를 게시한 후 콘텐츠를 보관할 수 있으려면 먼저 보관에 대한 옵션 및 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="5a6c1-119">자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013에서 보관에 대 한 지원 구성을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a6c1-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

