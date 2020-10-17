---
title: 미러된 Enterprise Edition 백 엔드 서버-미러 복원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e4bbb7d74c6bf660c69a15ff8250d95f04fed98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511585"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="57eae-102">Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-미러</span><span class="sxs-lookup"><span data-stu-id="57eae-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57eae-103">_**마지막으로 수정 된 항목:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="57eae-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="57eae-104">미러된 구성에 Enterprise Edition 백 엔드 서버가 있고 미러만 실패 하는 경우에는이 섹션의 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="57eae-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="57eae-105">주 데이터베이스와 미러 서버에 모두 오류가 발생 하면 [Lync server 2013에서 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57eae-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="57eae-106">기본에만 오류가 발생 하는 경우 [Lync server 2013-primary에서 미러된 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57eae-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="57eae-107">중앙 관리 저장소를 호스트 하는 데이터베이스가 실패 하면 [Lync server 2013에서 중앙 관리 저장소를 호스트 하는 서버 복원을](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57eae-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="57eae-108">백 엔드 서버가 아닌 Enterprise Edition 구성원 서버가 실패 하면 [Lync server 2013에서 Enterprise edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57eae-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="57eae-109">복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="57eae-110">복원 중에 문제가 발생 하는 경우를 대비 하 여이 이미지를 롤백 지점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="57eae-111">운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 후 이미지 복사본을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="57eae-112">Enterprise Edition 백 엔드 서버 미러 데이터베이스를 복원 하려면</span><span class="sxs-lookup"><span data-stu-id="57eae-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="57eae-113">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="57eae-114">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="57eae-115">미러링을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-115">Uninstall mirroring.</span></span> <span data-ttu-id="57eae-116">먼저 다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="57eae-117">예제:</span><span class="sxs-lookup"><span data-stu-id="57eae-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="57eae-118">이 서버의 모든 데이터베이스 유형에 대해이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="57eae-119">오류가 발생 한 컴퓨터와 동일한 FQDN (정규화 된 도메인 이름)을 가진 깨끗 한 서버나 새 서버를 만들고, 운영 체제를 설치한 후 인증서를 복원 하거나 reenroll DB1.contoso.com 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="57eae-120">이 서버는 새 미러에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="57eae-121">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 새 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="57eae-122">SQL Server 2012 또는 SQL Server 2008 r 2를 설치 하 고 인스턴스 이름을 오류 이전과 동일 하 게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="57eae-123">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="57eae-124">토폴로지 작성기를 사용 하 여 미러 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="57eae-125">다음 작업을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="57eae-125">Perform the following:</span></span>
    
      - <span data-ttu-id="57eae-126">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="57eae-127">Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **데이터베이스 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="57eae-128">**데이터베이스 설치** 마법사를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="57eae-129">**데이터베이스 만들기** 페이지에서 다시 만들 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="57eae-130">마법사의 지시에 따라 **미러 데이터베이스 만들기** 메시지가 표시 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="57eae-131">설치 하려는 데이터베이스를 선택 하 고이 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="57eae-132">토폴로지 작성기를 실행 하는 대신 <STRONG>CsMirrorDatabase</STRONG> cmdlet을 사용 하 여 미러링을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57eae-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="57eae-133">자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="57eae-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

