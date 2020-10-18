---
title: 'Lync Server 2013: 웹 서비스 URL 변경'
description: 'Lync Server 2013: 웹 서비스 URL을 변경 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78a7a9b70d475aa952a43d215a8e5cd2068911e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576354"
---
# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="f6db1-103">Lync Server 2013에서 웹 서비스 URL 변경</span><span class="sxs-lookup"><span data-stu-id="f6db1-103">Change the Web Services URL in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6db1-104">_**마지막으로 수정 된 항목:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="f6db1-104">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="f6db1-105">프런트 엔드 풀 및 Standard Edition 서버를 설정할 때 외부 웹 팜 FQDN(정규화된 도메인 이름) 및 관련 포트를 구성할 수 있는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-105">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="f6db1-106">Lync Server 배포 마법사를 실행할 때이 URL을 구성 하지 않은 경우 이러한 설정을 수동으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-106">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="f6db1-107">이러한 설정은 권장 설정이며 기본 포트이므로 일반적으로 관리자가 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-107">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6db1-108">Standard Edition server를 구성 하는 동안 다음 스크린샷은 FQDN 재정의 옵션이 사용 되지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-108">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="f6db1-109">이 옵션은 프런트 엔드 풀에서 Enterprise Edition 서버를 구성할 때 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-109">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="f6db1-110">![웹 서비스 풀 설정 편집](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "웹 서비스 풀 설정 편집")</span><span class="sxs-lookup"><span data-stu-id="f6db1-110">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="f6db1-111">웹 서비스를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="f6db1-111">To configure web services</span></span>

1.  <span data-ttu-id="f6db1-112">토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="f6db1-113">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="f6db1-114">토폴로지 작성기의 콘솔 트리 **Standard Edition 프런트 엔드 서버**, **Enterprise Edition 프런트 엔드 풀**및 **디렉터리 풀**에서 풀 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-114">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="f6db1-115">이름을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 한 다음 **웹 서비스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-115">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="f6db1-116">**외부 웹 서비스 FQDN**을 추가 하거나 편집한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-116">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f6db1-117">프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-117">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="f6db1-118">예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-118">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="f6db1-119">디렉터를 배포 하는 경우에는 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프런트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-119">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="f6db1-120">수신 대기 및 게시 된 포트가 환경에 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-120">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="f6db1-121">해당 환경의 모든 Standard Edition server, 프런트 엔드 풀 및 디렉터 풀에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-121">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="f6db1-122">콘솔 트리에서 **Lync Server 2013**을 클릭 한 다음 **작업** 창에서 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-122">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="f6db1-123">수신 대기 및 게시 포트를 구성할 때 알아야 할 몇 가지 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-123">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="f6db1-124">표시 되는 수신 대기 포트는 각 프런트 엔드 서버에서 IIS (인터넷 정보 서버)에 대해 구성 된 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-124">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="f6db1-125">IIS에서는 내부 및 외부 수신 대기 포트가 서로 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-125">The internal and external listening ports must be different for IIS.</span></span> <span data-ttu-id="f6db1-126">외부 수신 대기 포트는 내부 웹 트래픽에 대 한 하드웨어 부하 분산 장치를 나타내며 하나는 외부 웹 트래픽에 대 한 역방향 프록시 서버를 나타내기 때문에 일반적으로 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-126">For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="f6db1-127">프런트 엔드 풀, 디렉터 또는 디렉터 풀의 내부 웹 서비스를 재정의 하 고 자체 FQDN을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-127">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f6db1-128">내부 웹 서비스를 자체 정의 된 FQDN으로 재정의 하려는 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-128">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="f6db1-129">게시 된 포트는 역방향 프록시 또는 하드웨어 부하 분산 장치에서 수신 대기 포트로 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-129">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="f6db1-130">프런트 엔드 풀 (예제에 표시 되지 않음)의 경우 웹 트래픽이 하드웨어 부하 분산 장치를 통해 제공 되 고 내부 SIP 풀 트래픽 이동이 DNS 부하 분산 장치를 통과 하기 때문에 내부 SIP 풀 FQDN은 내부 웹 서비스 FQDN과 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-130">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer.</span></span> <span data-ttu-id="f6db1-131">이 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-131">This requirement must be met.</span></span>

  - <span data-ttu-id="f6db1-132">Lync Server Standard Edition 배포에서는이 서버의 부하를 분산할 수 없으므로 내부 웹 서비스 FQDN을 재정의 하거나 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-132">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="f6db1-133">내부 SIP 및 웹 트래픽 모두에 사용 하는 하드웨어 부하 분산 장치가 환경에 있는 경우 토폴로지 작성기가이를 구별할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-133">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="f6db1-134">웹 서비스 Fqdn은 서로 쉽게 구별할 수 있어야 합니다. 이를 통해 URL 리디렉션이 해당 서버에 연결 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-134">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="f6db1-135">예를 들어 Fqdn이 두 개인 경우 하나의 meeting.contoso.com 및 다른 conferencing.contoso.com을 명명 하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-135">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="f6db1-136">Meet1.contoso.com 및 meet2.contoso.com와 같이 이름이 비슷한 Fqdn이 있는 경우 리디렉션 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-136">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="f6db1-137">외부 웹 서비스는 경계 네트워크에서 역방향 프록시와 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-137">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="f6db1-138">이러한 웹 서비스를 사용 하 여 클라이언트에 대 한 외부 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-138">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="f6db1-139">여기에 구성 된 Fqdn은 로그온 할 때 클라이언트에 전송 되며, 원격으로 연결할 때 HTTPS 연결을 다시 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-139">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="f6db1-140">역방향 프록시 서버는 외부 웹 서비스 FQDN을 내부 하드웨어 부하 분산 장치 또는 풀에 직접 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-140">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="f6db1-141">역방향 프록시는 내부 웹 서버의 IP 주소에 대 한 외부 웹 서비스 FQDN을 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-141">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="f6db1-142">공용 인터넷에서 외부 웹 서비스 FDQN를 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-142">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="f6db1-143">내부 서버가 Standard Edition 서버인 경우 내부 FQDN은 Standard Edition 서버 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-143">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="f6db1-144">내부 서버가 프런트 엔드 풀 인 경우 FQDN은 내부 웹 팜 서버의 부하를 분산 하는 하드웨어 부하 분산 장치 VIP (가상 IP)입니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-144">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="f6db1-145">두 개 이상의 Enterprise Edition server를 포함 하는 프런트 엔드 풀에는 하드웨어 부하 분산 장치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-145">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="f6db1-146">Standard Edition 서버 또는 단일 Enterprise Edition 프런트 엔드 서버에는 부하 분산 장치를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db1-146">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

