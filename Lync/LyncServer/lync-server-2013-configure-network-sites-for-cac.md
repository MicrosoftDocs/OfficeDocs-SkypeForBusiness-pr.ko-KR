---
title: 'Lync Server 2013: CAC에 대 한 네트워크 사이트 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f449d26515c6790ec8582676ca57ed897f12dc40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="64b10-102">Lync Server 2013에서 CAC에 대 한 네트워크 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="64b10-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64b10-103">_**마지막으로 수정 된 항목:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="64b10-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="64b10-104">E9-1-1 또는 미디어 바이패스에 대 한 네트워크 사이트를 이미 만든 경우에는 <STRONG>CsNetworkSite</STRONG> cmdlet을 사용 하 여 기존 네트워크 사이트를 수정 하 여 대역폭 정책 프로필을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="64b10-105">네트워크 사이트를 수정 하는 방법에 대 한 예는 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64b10-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="64b10-106">*네트워크 사이트* 는 CAC (통화 허용 제어), E9-1-1 및 미디어 바이패스 배포의 각 네트워크 지역 내의 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="64b10-107">다음 절차에 따라 CAC에 대 한 네트워크 토폴로지 예에서 네트워크 사이트에 맞춘 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="64b10-108">다음 절차에서는 WAN 대역폭에 의해 제한 되는 네트워크 사이트를 만들고 구성 하는 방법을 보여 주고, 따라서 실시간 오디오 또는 비디오 트래픽 흐름을 제한 하는 대역폭 정책이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="64b10-109">예제 CAC 배포의 경우 북미 지역에는 6 개의 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="64b10-110">이러한 사이트 중 3 개는 WAN 대역폭 (리노, 포틀랜드 및 앨버커키)의 제약을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="64b10-111">다른 3 개 사이트 (WAN 대역폭으로 제한 *되지 않음* ): 뉴욕, 시카고 및 디트로이트</span><span class="sxs-lookup"><span data-stu-id="64b10-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="64b10-112">다른 네트워크 사이트를 만들거나 수정 하는 방법의 예는 [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-site.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64b10-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="64b10-113">예제 네트워크 토폴로지를 보려면 계획 설명서에서 [예제: Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64b10-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="64b10-114">다음 절차에서는 Lync Server 관리 셸을 사용 하 여 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="64b10-115">Lync Server 제어판을 사용 하 여 네트워크 사이트를 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64b10-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="64b10-116">통화 허용 제어에 대 한 네트워크 사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="64b10-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="64b10-117">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="64b10-118">**새-CsNetworkSite** cmdlet을 실행 하 여 네트워크 사이트를 만들고 각 사이트에 적절 한 대역폭 정책 프로필을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="64b10-119">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="64b10-120">전체 예제 토폴로지에 대 한 네트워크 사이트 만들기를 완료 하려면 EMEA 및 APAC 지역의 대역폭 제한 네트워크 사이트에 대해 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b10-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

