---
title: 'Lync Server 2013: 토폴로지에서 선택적 디렉터 토폴로지 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a07bf43552066260d55c8f5461a091d41732e46c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="adc19-102">Lync Server 2013의 토폴로지에서 선택적 디렉터 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="adc19-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adc19-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="adc19-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="adc19-104">Lync Server 2013 디렉터는 단일 인스턴스 서버 이거나 고가용성 및 용량을 위해 부하 분산 풀로 여러 디렉터로 설치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="adc19-105">하드웨어 부하 분산 및 DNS (Domain Name System) 부하 분산이 모두 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="adc19-106">이 항목에서는 디렉터 풀에 대해 DNS 부하 분산을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="adc19-107">서버 역할을 추가하거나 제거할 때 토폴로지를 제대로 게시, 사용하도록 설정 또는 사용하지 않도록 설정하려면 **RTCUniversalServerAdmins** 및 **Domain Admins** 그룹의 구성원인 사용자로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="adc19-108">또한 서버 역할 추가에 대한 적절한 관리자 권한 및 권한을 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="adc19-109">자세한 내용은 Standard Edition server 또는 Enterprise Edition server 배포 설명서에서 [Lync Server 2013의 대리인 설치 권한](lync-server-2013-delegate-setup-permissions.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="adc19-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="adc19-110">다른 구성 변경에는 **RTCUniversalServerAdmins** 그룹의 구성원 자격만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="adc19-111">이 항목에서는 두 개의 디렉터 토폴로지에 대 한 토폴로지를 정의 하 고 게시 하는 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="adc19-112">디렉터(단일 인스턴스)를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="adc19-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="adc19-113">디렉터(여러 디렉터 풀)를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="adc19-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="adc19-114">디렉터(단일 인스턴스)를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="adc19-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="adc19-115">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="adc19-116">시작 페이지에서 **기존 배포에서 토폴로지 다운로드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="adc19-117">**토폴로지를 다른 이름으로 저장** 대화 상자에서 기존 토폴로지의 이름 및 로컬 복사본 위치를 입력한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="adc19-118">디렉터를 추가할 사이트를 확장하고 **디렉터 풀**을 마우스 오른쪽 단추로 클릭한 다음 **새 디렉터 풀**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="adc19-119">**디렉터 풀 FQDN 정의** 대화 상자에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="adc19-120">**풀 FQDN**에 디렉터 풀의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="adc19-121">**단일 컴퓨터 풀**을 클릭한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="adc19-122">**파일 공유 정의** 대화 상자에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="adc19-123">기존 파일 공유를 사용하려면 **이전에 정의된 파일 공유 사용**을 클릭하고 목록에서 파일 공유를 선택한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="adc19-124">새 파일 공유를 만들려면 **새 파일 공유 정의**를 클릭하고 **파일 서버 FQDN**에 파일 공유 위치의 FQDN을 입력하고 **파일 공유**에 공유 이름을 입력한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="adc19-125">이 단계에서 지정하거나 만든 파일 공유는 토폴로지를 게시하기 전에 있거나 만들어져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="adc19-126">디렉터에 지정된 파일 공유는 실제로 사용되지 않으므로 조직의 아무 풀에 대한 파일 공유를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="adc19-127">**웹 서비스 URL 지정** 대화 상자에서 **외부 기본 URL**에 디렉터의 FQDN을 지정한 다음 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="adc19-128">이름은 인터넷 DNS 서버에서 확인 가능하고 역방향 프록시의 공용 IP 주소를 가리켜야 합니다. 역방향 프록시는 해당 URL에 대한 HTTP/HTTPS 요청을 수신 대기하여 해당 디렉터의 외부 웹 서비스 가상 디렉터리로 프록시합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="adc19-129">프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="adc19-130">예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="adc19-131">디렉터를 배포 하는 경우에는 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프런트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="adc19-132">내부 웹 서비스를 자체 정의 된 FQDN으로 다시 정의 하려는 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="adc19-133">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="adc19-134">디렉터(여러 디렉터 풀)를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="adc19-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="adc19-135">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="adc19-136">시작 페이지에서 **기존 배포에서 토폴로지 다운로드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="adc19-137">**토폴로지를 다른 이름으로 저장** 대화 상자에서 기존 토폴로지의 이름 및 로컬 복사본 위치를 입력한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="adc19-138">디렉터를 추가할 사이트를 확장하고 **디렉터 풀**을 마우스 오른쪽 단추로 클릭한 다음 **새 디렉터 풀**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="adc19-139">**디렉터 풀 FQDN 정의** 대화 상자에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="adc19-140">**풀 FQDN**에 디렉터 풀의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="adc19-141">**다중 컴퓨터 풀**을 클릭한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="adc19-142">**이 풀의 컴퓨터 정의** 대화 상자에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="adc19-143">첫 번째 풀 구성원의 컴퓨터 FQDN을 지정하고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="adc19-p104">추가할 각 컴퓨터에 대해 이전 단계를 반복합니다. 완료되면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-p104">Repeat the previous step for each computer that you want to add. When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="adc19-146">**파일 공유 정의** 대화 상자에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="adc19-147">기존 파일 공유를 사용하려면 **이전에 정의된 파일 공유 사용**을 클릭하고 목록에서 파일 공유를 선택한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="adc19-148">새 파일 공유를 만들려면 **새 파일 공유 정의**를 클릭하고 **파일 서버 FQDN**에 파일 공유 위치의 FQDN을 입력하고 **파일 공유**에 공유 이름을 입력한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="adc19-149">이 단계에서 지정하거나 만든 파일 공유는 토폴로지를 게시하기 전에 있거나 만들어져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="adc19-150">디렉터에 지정된 파일 공유는 실제로 사용되지 않으므로 조직의 아무 풀에 대한 파일 공유를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="adc19-151">**웹 서비스 URL 지정** 대화 상자에서 **외부 기본 URL**에 디렉터의 FQDN을 지정한 다음 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="adc19-152">이름은 인터넷 DNS 서버에서 확인할 수 있어야 하며, 해당 URL로 보낸 HTTP/HTTPS 요청을 수신하고 이 요청을 해당 디렉터 풀의 외부 웹 서비스 가상 디렉터리에 프록시하는 역방향 프록시의 공용 IP 주소를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="adc19-153">프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="adc19-154">예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="adc19-155">디렉터를 배포 하는 경우에는 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프런트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="adc19-156">내부 웹 서비스를 자체 정의 된 FQDN으로 다시 정의 하려는 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="adc19-157">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="adc19-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

