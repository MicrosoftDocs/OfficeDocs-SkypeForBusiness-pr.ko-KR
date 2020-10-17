---
title: 'Lync Server 2013: SIP 트렁크에 대 한 통화 허용 제어'
description: 'Lync Server 2013: SIP 트렁크에 대 한 통화 허용 제어'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3667ef4608b221a1607b6bbe0d89d390cb1dd402
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563164"
---
# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="82877-103">Lync Server 2013의 SIP 트렁크에 대 한 통화 허용 제어</span><span class="sxs-lookup"><span data-stu-id="82877-103">Call admission control on a SIP trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82877-104">_**마지막으로 수정 된 항목:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="82877-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="82877-p101">SIP 트렁크에 CAC(통화 허용 제어)를 배포하려면 ITSP(인터넷 전화 통신 서비스 공급자)를 나타내는 네트워크 사이트를 만듭니다. SIP 트렁크에 대역폭 정책 값을 적용하려면 엔터프라이즈의 네트워크 사이트와 ITSP를 나타내기 위해 만든 네트워크 사이트 간의 사이트 간 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82877-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="82877-107">다음 그림에서는 SIP 트렁크에 대한 예제 CAC 배포를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82877-107">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="82877-108">**SIP 트렁크에 대한 CAC 구성**</span><span class="sxs-lookup"><span data-stu-id="82877-108">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="82877-109">![통화 허용 제어 SIP 트렁크 다이어그램](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "통화 허용 제어 SIP 트렁크 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="82877-109">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="82877-110">SIP 트렁크에 CAC를 구성하려면 CAC 배포 중에 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82877-110">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="82877-111">ITSP를 나타내는 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82877-111">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="82877-112">네트워크 사이트를 적절한 네트워크 지역에 연결하고 이 네트워크 사이트에 오디오 및 비디오 대역폭으로 0을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="82877-112">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="82877-113">자세한 내용은 배포 설명서에서 [Lync Server 2013의 CAC에 대 한 네트워크 사이트 구성을](lync-server-2013-configure-network-sites-for-cac.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="82877-113">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82877-114">ITSP에 대해서는 이 네트워크 사이트 구성이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82877-114">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="82877-115">대역폭 정책 값은 2단계에서 실제로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="82877-115">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="82877-116">1단계에서 만든 사이트에 대한 관련 매개 변수 값을 사용하여 SIP 트렁크에 대한 사이트 간 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82877-116">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="82877-117">예를 들어 엔터프라이즈의 네트워크 사이트 이름을 NetworkSiteID1 매개 변수 값으로 사용하고 ITSP 네트워크 사이트를 NetworkSiteID2 매개 변수 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="82877-117">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="82877-118">자세한 내용은 배포 설명서의 [Lync Server 2013에서 네트워크 사이트 간 정책 만들기](lync-server-2013-create-network-intersite-policies.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="82877-118">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="82877-119">또한 New-CsNetworkInterSitePolicy cmdlet에 대 한 Lync Server 관리 셸 설명서도 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="82877-119">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="82877-120">ITSP로부터 SCB(세션 경계 컨트롤러) 미디어 종료 지점의 IP 주소를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="82877-120">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="82877-121">해당 IP 주소(서브넷 마스크 32 포함)를 ITSP를 나타내는 네트워크 사이트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="82877-121">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="82877-122">자세한 내용은 [Lync Server 2013에서 a 서브넷을 네트워크 사이트에 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="82877-122">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

