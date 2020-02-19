---
title: 타사 PSTN 게이트웨이 또는 PBX에 대 한 통화 허용 제어
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85a35bafa8f3311d19633f044ec4bde0437993db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="97f82-102">타사 PSTN 게이트웨이 또는 PBX가 있는 Lync Server 2013의 통화 허용 제어</span><span class="sxs-lookup"><span data-stu-id="97f82-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97f82-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="97f82-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="97f82-104">이 항목에서는 중재 서버의 게이트웨이 인터페이스와 타사 PSTN(공중 전화망) 게이트웨이 또는 PBX(Private Branch Exchange) 간의 링크에 CAC(통화 허용 제어)를 배포할 수 있는 방법에 대한 예를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="97f82-105">사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC</span><span class="sxs-lookup"><span data-stu-id="97f82-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="97f82-106">중재 서버의 게이트웨이 인터페이스에서 타사 PBX 또는 PSTN 게이트웨이로 연결되는 WAN 링크에 CAC를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="97f82-107">**사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC**</span><span class="sxs-lookup"><span data-stu-id="97f82-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="97f82-108">![사례 1: 중재 서버 PSTN 게이트웨이 간의 CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "사례 1: 중재 서버 PSTN 게이트웨이 간의 CAC")</span><span class="sxs-lookup"><span data-stu-id="97f82-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="97f82-p101">이 예에서 CAC는 중재 서버와 PSTN 게이트웨이 간에 적용됩니다. 네트워크 사이트 1의 Lync 클라이언트 사용자가 네트워크 사이트 2의 PSTN 게이트웨이를 통해 PSTN 전화를 걸면 미디어가 WAN 링크를 통해 이동합니다. 따라서 각 PSTN 세션에 대해 두 번의 CAC 확인이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-p101">In this example, CAC is applied between the Mediation Server and a PSTN gateway. If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link. Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="97f82-112">Lync 클라이언트 응용 프로그램과 중재 서버 간</span><span class="sxs-lookup"><span data-stu-id="97f82-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="97f82-113">중재 서버와 PSTN 게이트웨이 간</span><span class="sxs-lookup"><span data-stu-id="97f82-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="97f82-114">이 작업은 네트워크 사이트 1의 클라이언트로 걸려 오는 수신 PSTN 전화와 네트워크 사이트 1의 클라이언트 응용 프로그램에서 거는 발신 PSTN 전화 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="97f82-115">PSTN 게이트웨이가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="97f82-116">중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="97f82-117">자세한 내용은 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013에서 a 서브넷을 네트워크 사이트에 연결</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="97f82-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="97f82-118">사례 2: 중재 서버와 미디어 종료 지점이 있는 타사 PBX 간의 CAC</span><span class="sxs-lookup"><span data-stu-id="97f82-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="97f82-p102">이 구성은 사례 1과 유사합니다. 두 사례 모두 중재 서버에서 장치가 WAN 링크의 반대쪽 끝에서 미디어를 종료함을 인식하며, MTP(미디어 종료 지점)가 있는 PBX 또는 PSTN 게이트웨이의 IP 주소가 중재 서버에 다음 홉으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-p102">This configuration is similar to Case 1. In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="97f82-121">**사례 2: 중재 서버와 MTP가 있는 타사 PBX 간의 CAC**</span><span class="sxs-lookup"><span data-stu-id="97f82-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="97f82-122">![사례 2: 중재 서버 PBX (MTP 포함) 간의 CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "사례 2: 중재 서버 PBX (MTP 포함) 간의 CAC")</span><span class="sxs-lookup"><span data-stu-id="97f82-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="97f82-p103">이 예에서 CAC는 중재 서버와 PBX/MTP 간에 적용됩니다. 네트워크 사이트 1의 Lync 클라이언트 사용자가 네트워크 사이트 2에 있는 PBX/MTP를 통해 PSTN 전화를 걸면 미디어가 WAN 링크를 통해 이동합니다. 따라서 각 PSTN 세션에 대해 두 번의 CAC 확인이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-p103">In this example, CAC is applied between the Mediation Server and the PBX/MTP. If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link. Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="97f82-126">Lync 클라이언트 응용 프로그램과 중재 서버 간</span><span class="sxs-lookup"><span data-stu-id="97f82-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="97f82-127">중재 서버와 PBX/MTP 간</span><span class="sxs-lookup"><span data-stu-id="97f82-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="97f82-128">이 작업은 네트워크 사이트 1의 클라이언트로 걸려 오는 수신 PSTN 전화와 네트워크 사이트 1의 클라이언트에서 거는 발신 PSTN 전화 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="97f82-129">MTP가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="97f82-130">중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="97f82-131">자세한 내용은 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013에서 a 서브넷을 네트워크 사이트에 연결</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="97f82-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="97f82-132">사례 3: 중재 서버와 미디어 종료 지점이 없는 타사 PBX 간의 CAC</span><span class="sxs-lookup"><span data-stu-id="97f82-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="97f82-p104">사례 3은 처음 두 사례와 약간 다릅니다. 타사 PBX에 MTP가 없는 경우 타사 PBX에 대한 발신 세션 요청에 대해 중재 서버에서 미디어가 종료되는 PBX 경계 내 위치를 알지 못합니다. 이 경우 미디어가 중재 서버와 타사 끝점 장치 간에 직접 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-p104">Case 3 is slightly different from the first two cases. If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary. In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="97f82-136">**사례 3: 중재 서버와 MTP가 없는 타사 PBX 간의 CAC**</span><span class="sxs-lookup"><span data-stu-id="97f82-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="97f82-137">![사례 3: 중재 서버 PBX (MTP 없음) 간의 CAC](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "사례 3: 중재 서버 PBX (MTP 없음) 간의 CAC")</span><span class="sxs-lookup"><span data-stu-id="97f82-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="97f82-p105">이 예에서는 네트워크 사이트 1의 Lync 클라이언트 사용자가 PBX를 통해 전화를 걸면 중재 서버에서 프록시 레그(Lync 클라이언트 응용 프로그램과 중재 서버 간)에서만 CAC 확인을 수행할 수 있습니다. 세션이 요청되는 동안 중재 서버에 끝점 장치에 대한 정보가 없으므로 통화가 연결되기 전에 WAN 링크(중재 서버와 타사 끝점 간)에서 CAC 확인을 수행할 수 없습니다. 그러나 세션이 설정된 후에는 중재 서버가 트렁크에서 사용되는 대역폭 관리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-p105">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server). Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment. After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="97f82-141">타사 끝점에서 발신된 전화의 경우에는 세션 요청 시 해당 끝점 장치에 대한 정보를 사용할 수 있으므로 중재 서버의 양쪽에서 CAC 확인을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="97f82-142">끝점 장치가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="97f82-143">중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97f82-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="97f82-144">자세한 내용은 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013에서 a 서브넷을 네트워크 사이트에 연결</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="97f82-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

