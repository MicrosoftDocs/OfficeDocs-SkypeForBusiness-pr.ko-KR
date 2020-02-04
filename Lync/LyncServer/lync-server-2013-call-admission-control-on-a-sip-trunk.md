---
title: 'Lync Server 2013: SIP 트렁크에 대한 통화 허용 제어 서비스'
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
ms.openlocfilehash: ab8196070bbb7992aed915cf188d67e95912524a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="601fd-102">Lync Server 2013의 SIP 트렁크에 대한 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="601fd-102">Call admission control on a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="601fd-103">_**마지막으로 수정한 주제:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="601fd-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="601fd-104">SIP 트렁크에 CAC (call 허용 제어)를 배포 하려면 네트워크 사이트를 만들어 인터넷 통신 서비스 공급자 (ITSP)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-104">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP).</span></span> <span data-ttu-id="601fd-105">SIP 트렁크에 대역폭 정책 값을 적용 하려면 엔터프라이즈의 네트워크 사이트와 ITSP를 나타내기 위해 만드는 네트워크 사이트 간에 사이트 간 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-105">To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="601fd-106">다음 그림에서는 SIP 트렁크에 대 한 CAC 배포의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-106">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="601fd-107">**SIP 트렁크의 CAC 구성**</span><span class="sxs-lookup"><span data-stu-id="601fd-107">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="601fd-108">![통화 허용 제어 SIP 트렁크 다이어그램](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "통화 허용 제어 SIP 트렁크 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="601fd-108">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="601fd-109">SIP 트렁크에서 CAC를 구성 하려면 CAC 배포 중에 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-109">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="601fd-110">ITSP를 나타내는 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-110">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="601fd-111">네트워크 사이트를 적절 한 네트워크 영역에 연결 하 고이 네트워크 사이트의 오디오 및 비디오에 대 한 대역폭을 0으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-111">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="601fd-112">자세한 내용은 배포 설명서의 [Lync Server 2013에서 CAC에 대 한 네트워크 사이트 구성을](lync-server-2013-configure-network-sites-for-cac.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="601fd-112">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="601fd-113">ITSP의 경우이 네트워크 사이트 구성은 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-113">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="601fd-114">대역폭 정책 값은 2 단계에서 실제로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-114">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="601fd-115">1 단계에서 만든 사이트의 관련 매개 변수 값을 사용 하 여 SIP 트렁크에 대 한 사이트 간 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-115">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="601fd-116">예를 들어 엔터프라이즈의 네트워크 사이트 이름을 NetworkSiteID1 매개 변수 값으로 사용 하 고 ITSP 네트워크 사이트의 NetworkSiteID2 매개 변수 값으로 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-116">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="601fd-117">자세한 내용은 배포 설명서의 [Lync Server 2013에서 네트워크 사이트 간 정책 만들기](lync-server-2013-create-network-intersite-policies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="601fd-117">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="601fd-118">또한 새 CsNetworkInterSitePolicy cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="601fd-118">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="601fd-119">ITSP에서 SCB (세션 경계 컨트롤러) 미디어 종료 지점의 IP 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-119">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="601fd-120">ITSP를 나타내는 네트워크 사이트에 32의 서브넷 마스크를 사용 하 여 해당 IP 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="601fd-120">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="601fd-121">자세한 내용은 [Lync Server 2013에서 서브넷을 네트워크 사이트와 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="601fd-121">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

