---
title: 'Lync Server 2013: 보관에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="1f224-102">Lync Server 2013의 보관에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f224-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f224-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="1f224-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="1f224-104">Lync Server 2013 기술 요구 사항에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="1f224-105">인프라 요구 사항.</span><span class="sxs-lookup"><span data-stu-id="1f224-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="1f224-106">보관을 위해 설치 해야 하는 필수 구성 요소 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="1f224-107">보관을 위한 데이터 저장소 요구 사항.</span><span class="sxs-lookup"><span data-stu-id="1f224-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="1f224-108">보관 배포에 대 한 확장 요구 사항 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="1f224-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="1f224-109">보관 데이터베이스에 대 한 성능 요구 사항 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="1f224-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f224-110">이 Lync Server 2013 릴리스에서는 크기 조정 및 성능 정보를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="1f224-111">인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f224-111">Infrastructure Requirements</span></span>

<span data-ttu-id="1f224-112">Lync Server 2013 아카이빙 인프라 요구 사항은 Lync Server 2013를 배포 하는 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="1f224-113">자세한 내용은 계획 설명서에서 [Lync Server 2013의 인프라 요구 사항 확인](lync-server-2013-determining-your-infrastructure-requirements.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1f224-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="1f224-114">필수 구성 요소 보관</span><span class="sxs-lookup"><span data-stu-id="1f224-114">Archiving Prerequisites</span></span>

<span data-ttu-id="1f224-115">Lync Server 2013는 다음과 같은 이유로 보관을 위한 필수 구성 요소를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="1f224-116">보관 서버는 더 이상 서버 역할이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-116">Archiving Server is no longer a server role.</span></span> <span data-ttu-id="1f224-117">대신 통합 데이터 수집 에이전트는 풀 및 Standard Edition 서버의 프런트 엔드 서버에서 보관을 위해 데이터를 캡처하기 위해 실행 되므로 보관을 위해 별도의 시스템 플랫폼을 설정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-117">Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="1f224-118">보관은 Lync Server 2013 파일 저장소를 사용 하 여 모임 콘텐츠 파일을 임시로 저장 하므로 보관을 위해 별도의 파일 저장소를 설정 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="1f224-119">Lync Server 2013에서는 메시지 대기열이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="1f224-120">보관을 위한 데이터 저장소 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f224-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="1f224-121">또한 저장소 보관을 위한 인프라를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-121">Additionally, you need to set up the infrastructure for Archiving storage.</span></span> <span data-ttu-id="1f224-122">여기에는 다음 중 하나 또는 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-122">This includes one or both of the following:</span></span>

  - <span data-ttu-id="1f224-123">**Microsoft Exchange 저장소**.</span><span class="sxs-lookup"><span data-stu-id="1f224-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="1f224-124">PowerPoint 프레젠테이션과 같은 모임 콘텐츠 파일은 첨부 파일로 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="1f224-125">Lync 보관 데이터가 Exchange 준수 데이터와 함께 저장 되도록 Microsoft Exchange 통합을 사용 하려는 경우 exchange 배포에 Exchange 2013를 사용 하 고 최대 저장소 크기가 모임 콘텐츠 파일의 저장소를 지원 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="1f224-126">Microsoft Exchange 통합 옵션을 사용 하 여 보관을 배포 하는 경우 Lync 보관 데이터는 exchange 2013 서버에 속한 사용자 에게만 Exchange 2013 준수 데이터와 함께 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="1f224-127">Microsoft Exchange 통합 옵션을 사용 하 여 보관을 배포 하 고 사용 하기 전에 Exchange 2013를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="1f224-128">Exchange 2013 저장소를 사용 하도록 선택한 경우 Exchange 2013 서버에서 홈이 아닌 Lync 사용자가 없는 경우 보관을 위해 별도의 SQL Server 데이터베이스를 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="1f224-129">**보관을 위한 SQL Server 데이터베이스 저장소**.</span><span class="sxs-lookup"><span data-stu-id="1f224-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="1f224-130">Exchange 2013 서버에 속하지 않는 사용자를 지원 하거나 Microsoft Exchange 통합 옵션을 사용 하지 않으려는 경우 SQL Server 데이터베이스를 사용 하 여 보관 저장소를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="1f224-131">Lync Server 2013는 다음과 같은 64 비트 버전의 SQL Server를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="1f224-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1f224-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="1f224-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="1f224-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="1f224-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1f224-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="1f224-135">Microsoft SQL Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="1f224-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f224-136">Microsoft SQL Server 2008 R2 Express 및 Microsoft SQL Server 2012 Express는 보관에 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="1f224-137">32 비트 버전의 SQL Server는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="1f224-138">SQL Server 요구 사항에 대 한 자세한 내용은 계획 문서 또는 지원 가능성 설명서의 <A href="lync-server-2013-database-software-support.md">Lync Server 2013에서 데이터베이스 소프트웨어 지원을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1f224-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="1f224-139">보관을 배포 하 고 사용 하기 전에 SQL Server 플랫폼을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="1f224-140">토폴로지를 게시 하는 데 사용 되는 계정에 적절 한 관리자 권한과 사용 권한이 있는 경우, 토폴로지를 게시할 때 LcsLog (보관 데이터베이스)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="1f224-141">나중에 설치 절차의 일부로 포함 하 여 데이터베이스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f224-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="1f224-142">SQL Server에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)Sql server TechCenter을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1f224-142">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

