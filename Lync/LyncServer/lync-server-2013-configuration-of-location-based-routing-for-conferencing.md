---
title: 'Lync Server 2013: 회의를 위한 위치 기반 라우팅 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bc901b9ef1b4b358771427f44d220631e4a40ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="ce2c0-102">Lync Server 2013에서 회의를 위한 위치 기반 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="ce2c0-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce2c0-103">_**마지막으로 수정 된 항목:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="ce2c0-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="ce2c0-104">위치 기반 라우팅 회의 응용 프로그램은 Lync Server 2013 위치 기반 라우팅의 구성을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="ce2c0-105">기본 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="ce2c0-106">모임에 참가 하는 참가자의 위치는 해당 네트워크 사이트에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="ce2c0-107">위치 기반 라우팅을 적용 하기 위해서는 네트워크 사이트 및 연결 된 네트워크 서브넷을 Lync Server에서 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="ce2c0-108">위치 기반 모임 라우팅을 적용 하려면 위치 기반 라우팅을 위해 Lync 참가자를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="ce2c0-109">모임 참가를 위한 PSTN 끝점의 위치 기반 라우팅을 적용 하려면 위치 기반 라우팅을 위해 PSTN 끝점을 연결 하는 데 사용 되는 SIP 트렁크를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="ce2c0-110">Lync Server 2013 위치 기반 라우팅 배포 및 구성에 대 한 자세한 내용은 [위치 기반 라우팅](lync-server-2013-configuring-location-based-routing.md)구성를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="ce2c0-111">위치 기반 라우팅 회의 응용 프로그램 사용</span><span class="sxs-lookup"><span data-stu-id="ce2c0-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="ce2c0-112">위치 기반 라우팅 회의 응용 프로그램은 기본적으로 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="ce2c0-113">이 응용 프로그램을 사용 하도록 설정 하기 전에 응용 프로그램에 할당할 올바른 우선 순위를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="ce2c0-114">이 우선 순위를 확인 하려면 Lync Server 관리 셸에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="ce2c0-115">Get-CsServerApplication-Identity Service: 등록자:\<풀 FQDN\></span><span class="sxs-lookup"><span data-stu-id="ce2c0-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="ce2c0-116">이 cmdlet에서 \<풀 FQDN\> 은 위치 기반 라우팅 회의 응용 프로그램을 사용 하도록 설정 하는 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="ce2c0-117">이 cmdlet은 Lync Server에서 호스트 되는 응용 프로그램의 목록과 각 작업에 대 한 우선 순위 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="ce2c0-118">위치 기반 라우팅 회의 응용 프로그램에 "DefaultRouting", "ExumRouting" 및 "OutboundRouting" 응용 프로그램 보다 더 작은 우선 순위 값이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="ce2c0-119">위치 기반 라우팅 회의 응용 프로그램에 "UdcAgent" 응용 프로그램의 우선 순위 값 보다 1 포인트가 더 높은 우선 순위 값을 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="ce2c0-120">예를 들어 "UdcAgent" 응용 프로그램의 우선 순위 값이 "2" 인 경우 "DefaultRouting" 응용 프로그램의 우선 순위 값은 "9"이 고 "ExumRouting" 응용 프로그램의 우선 순위 값은 "10"이 고 "OutboundRouting" 응용 프로그램의 우선 순위 값은 "10" 이면 위치 기반 라우팅 회의 응용 프로그램에 우선 순위 값 "3"을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="ce2c0-121">이렇게 하면 응용 프로그램의 우선 순위가 다른 응용 프로그램 (우선 순위: 0 ~ 1), "UdcAgent" (Priority: 2), 위치 기반 라우팅 회의 응용 프로그램 (우선 순위: 3), 기타 응용 프로그램 (우선 순위: 4 ~ 8), " DefaultRouting "(Priority: 9)," ExumRouting "(Priority: 10) 및" OutboundRouting "(Priority: 11)</span><span class="sxs-lookup"><span data-stu-id="ce2c0-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="ce2c0-122">위치 기반 라우팅 회의 응용 프로그램에 대 한 올바른 우선 순위 값을 찾은 후에 위치 기반 라우팅을 사용 하도록 설정 된 사용자를 가정 하는 각 프런트 엔드 풀 또는 Standard Edition 서버에 대해 다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="ce2c0-123">새-CsServerApplication-Identity Service: 등록자:\<Pool FQDN\>/LBRouting-Priority \<응용 프로그램\> 우선 순위-사용 $true-Critical $true-Urihttps://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="ce2c0-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri https://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="ce2c0-124">예:</span><span class="sxs-lookup"><span data-stu-id="ce2c0-124">For example:</span></span>

<span data-ttu-id="ce2c0-125">새-CsServerApplication-Identity Service:Registrar:Ls2013-2lbrpool. s t s/LBRouting-Priority 3-사용 $true-Critical $true-Urihttps://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="ce2c0-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri https://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="ce2c0-126">이 cmdlet을 사용한 후에는 풀의 모든 프런트 엔드 서버 또는 위치 기반 라우팅 회의 응용 프로그램을 사용할 수 있는 Standard Edition 서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ce2c0-127">해당 하는 풀 또는 Standard Edition 서버에 있는 모든 프런트 엔드 서버가 다시 시작 될 때 까지는 전화 회의 또는 문의 후 전송에 대 한 위치 기반 라우팅 enforcements 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="ce2c0-128">위치 기반 라우팅 회의 응용 프로그램을 성공적으로 사용 하도록 설정 하 고 해당 하는 모든 Lync 서버를 다시 시작한 후에는 Lync 사용자가 위치 기반 라우팅을 사용 하도록 설정한 모든 회의가 모니터링 되어 PSTN 유료 바이패스를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2c0-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

