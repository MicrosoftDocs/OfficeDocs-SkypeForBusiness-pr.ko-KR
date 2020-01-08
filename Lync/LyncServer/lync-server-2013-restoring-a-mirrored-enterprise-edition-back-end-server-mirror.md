---
title: 미러된 Enterprise Edition 백 엔드 서버 복원-미러
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 113d69d7aa39673686ff870c36a64bd1a8fe90f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="2017e-102">Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-미러</span><span class="sxs-lookup"><span data-stu-id="2017e-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2017e-103">_**마지막으로 수정한 주제:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="2017e-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="2017e-104">미러된 구성에 Enterprise Edition 백 엔드 서버가 있고 미러만 실패 하는 경우이 섹션의 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="2017e-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="2017e-105">주 데이터베이스와 미러 서버 모두에 오류가 발생 하는 경우 [에는 Lync server 2013에서 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2017e-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="2017e-106">주에만 실패 하는 경우 [Lync server 2013-기본으로 미러된 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2017e-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="2017e-107">중앙 관리 저장소를 호스팅하는 데이터베이스에 오류가 발생 하는 경우 [Lync server 2013에서 중앙 관리 저장소를 호스팅하는 서버 복원을](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2017e-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="2017e-108">백 엔드 서버가 아닌 Enterprise Edition 구성원 서버가 실패 하는 경우 [Lync server 2013에서 Enterprise edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2017e-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="2017e-109">복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="2017e-110">복원 중에 문제가 발생 하는 경우이 이미지를 롤백 시점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="2017e-111">운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 이미지 복사본을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="2017e-112">Enterprise Edition 백 엔드 서버 미러 데이터베이스 복원</span><span class="sxs-lookup"><span data-stu-id="2017e-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="2017e-113">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="2017e-114">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2017e-115">미러링 제거.</span><span class="sxs-lookup"><span data-stu-id="2017e-115">Uninstall mirroring.</span></span> <span data-ttu-id="2017e-116">먼저 다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="2017e-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="2017e-118">이 서버의 모든 데이터베이스 유형에 대해이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="2017e-119">실패 한 컴퓨터와 동일한 FQDN (정규화 된 도메인 이름) (DB1.contoso.com)이 있는 새 서버를 만들고, 운영 체제를 설치한 다음, 인증서를 복원 하거나 reenroll.</span><span class="sxs-lookup"><span data-stu-id="2017e-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="2017e-120">이 서버는 새 미러에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="2017e-121">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 새 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="2017e-122">SQL Server 2012 또는 SQL Server 2008 R2를 설치 하 고 인스턴스 이름을 오류 전과 동일 하 게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="2017e-123">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="2017e-124">토폴로지 작성기를 사용 하 여 미러 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="2017e-125">다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-125">Perform the following:</span></span>
    
      - <span data-ttu-id="2017e-126">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="2017e-127">Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **데이터베이스 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="2017e-128">**데이터베이스 설치** 마법사를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="2017e-129">**데이터베이스 만들기** 페이지에서 다시 만들려는 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="2017e-130">**미러 데이터베이스 만들기** 메시지가 나타날 때까지 마법사를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="2017e-131">설치 하려는 데이터베이스를 선택 하 고이 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="2017e-132">토폴로지 작성기를 실행 하는 대신 <STRONG>CsMirrorDatabase</STRONG> cmdlet을 사용 하 여 미러링을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2017e-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="2017e-133">자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2017e-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

