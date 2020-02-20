---
title: 'Lync Server 2013: 전역 미디어 바이패스 옵션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0166bee22684c32581acdd1241b2b2442cd460ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="d97af-102">Lync Server 2013의 글로벌 미디어 바이패스 옵션</span><span class="sxs-lookup"><span data-stu-id="d97af-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d97af-103">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d97af-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d97af-104">이 항목에서는 특정 사이트 또는 서비스에 대해 모든 트렁크에 대 한 미디어 바이패스를 피어 (IP (공중 전화망) 게이트웨이, ip-pbx 또는 인터넷 전화 통신 서비스 공급자의 SBC (세션 경계 컨트롤러)에 이미 구성 했다고 가정 합니다. 미디어에서 중재 서버를 바이패스 하도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="d97af-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="d97af-105">피어와 연결 된 개별 트렁크 연결에 미디어 바이패스를 사용 하도록 설정 하는 것 외에도 미디어 바이패스를 전역적으로 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-105">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="d97af-106">전역 미디어 바이패스 설정에서는 미디어 바이패스를 PSTN 통화에 대해 항상 시도 하도록 지정할 수도 있고, 통화 허용 제어에서 수행 하는 것과 비슷한 방식으로 네트워크 사이트 및 네트워크 지역에 서브넷 매핑을 사용 하 여 미디어 바이패스가 적용 됨을 지정 하는 방법 고급 음성 기능</span><span class="sxs-lookup"><span data-stu-id="d97af-106">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="d97af-107">미디어 바이패스 및 통화 허용 제어를 둘 다 사용 하는 경우 통화 허용 제어에 지정 된 네트워크 지역, 네트워크 사이트 및 서브넷 정보는 미디어 바이패스를 사용할지 여부를 결정할 때 자동으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-107">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="d97af-108">즉, 통화 허용 제어를 사용 하도록 설정 된 경우 PSTN을 호출 하는 경우에는 미디어 바이패스를 항상 시도 하도록 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-108">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="d97af-109">이 항목에서는 Lync Server 제어판과 Lync Server 관리 셸을 함께 사용 하 여 전역 미디어 바이패스 설정을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d97af-110">여기서 설명하는 단계를 사용하여 미디어 바이패스를 구성하는 경우, 클라이언트와 중재 서버 피어(예: SIP 트렁크 공급자의 SBC, IP-PBX 또는 PSTN 게이트웨이) 간의 연결이 원활하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="d97af-111">링크에 대한 대역폭 제한이 있는 경우에는 미디어 바이패스를 통화에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="d97af-112">미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="d97af-113">Microsoft는 인증 된 파트너와의 PSTN 게이트웨이 및 국내 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 몇 가지 테스트를 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="d97af-114">미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램-Lync Server에 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>나열 된 제품 및 버전 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="d97af-115">다음 단계: 전역 미디어 바이패스 설정 선택</span><span class="sxs-lookup"><span data-stu-id="d97af-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="d97af-116">특정 사이트 또는 서비스에서 피어로의 트렁크 연결에 미디어 바이패스를 사용하도록 설정한 후에는 다음 콘텐츠를 참조하여 각 작업을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="d97af-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="d97af-117">항상 [중재 서버를 바이패스 하도록 Lync server 2013의 Configure media bypass](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)에 설명 된 대로 미디어 바이패스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="d97af-118">또는 [사이트 및 지역 정보를 사용 하도록 Lync Server 2013의 미디어 바이패스 전역 설정 구성](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)에 설명 된 대로 사이트 및 지역 정보를 사용 하도록 미디어 바이패스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d97af-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d97af-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d97af-119">See Also</span></span>


[<span data-ttu-id="d97af-120">Lync Server 2013의 미디어 바이패스로 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="d97af-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="d97af-121">Lync Server 2013에서 서브넷을 네트워크 사이트에 연결</span><span class="sxs-lookup"><span data-stu-id="d97af-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="d97af-122">Lync Server 2013에서 미디어 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="d97af-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="d97af-123">Lync Server 2013의 미디어 바이패스 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="d97af-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

