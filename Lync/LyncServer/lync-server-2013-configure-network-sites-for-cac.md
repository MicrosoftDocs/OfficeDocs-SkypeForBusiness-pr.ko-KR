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
ms.openlocfilehash: 0958c74d6f1ce587886b7a8456aee44381c00ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="e9640-102">Lync Server 2013에서 CAC에 대 한 네트워크 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="e9640-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9640-103">_**마지막으로 수정한 주제:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="e9640-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="e9640-104">E9-1-1 또는 미디어 바이패스에 대 한 네트워크 사이트를 이미 만든 경우에는 <STRONG>설정 된 CsNetworkSite</STRONG> cmdlet을 사용 하 여 기존 네트워크 사이트를 수정 하 여 대역폭 정책 프로필을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="e9640-105">네트워크 사이트를 수정 하는 방법에 대 한 예는 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9640-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e9640-106">*네트워크 사이트* 는 호출 허용 제어 (CAC), E9-1-1, 미디어 바이패스 배포의 각 네트워크 영역 내에 있는 사무실 또는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="e9640-107">다음 절차를 사용 하 여 CAC의 네트워크 토폴로지에 대 한 네트워크 사이트에 맞춘 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="e9640-108">다음 절차에서는 WAN 대역폭에 의해 제한 되는 네트워크 사이트를 만들고 구성 하는 방법을 보여 주고, 따라서 실시간 오디오 또는 비디오 트래픽 흐름을 제한 하는 대역폭 정책이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="e9640-109">예제 CAC 배포의 경우 북미 지역에는 6 개의 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="e9640-110">다음의 세 사이트는 WAN 대역폭 (Reno, 포틀랜드, Albuquerque)에 의해 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="e9640-111">WAN 대역폭으로 제한 *되지* 않는 다른 세 개의 사이트: 뉴욕, 시카고, 디트로이트.</span><span class="sxs-lookup"><span data-stu-id="e9640-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="e9640-112">다른 네트워크 사이트를 만들거나 수정 하는 방법에 대 한 예는 [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-site.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9640-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="e9640-113">예제 네트워크 토폴로지를 보려면 계획 설명서의 [Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집 예제](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9640-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="e9640-114">다음 절차에서는 Lync Server Management Shell을 사용 하 여 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="e9640-115">Lync Server 제어판을 사용 하 여 네트워크 사이트를 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9640-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="e9640-116">통화 허용 제어를 위한 네트워크 사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e9640-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="e9640-117">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9640-118">**새로운 CsNetworkSite** cmdlet을 실행 하 여 네트워크 사이트를 만들고 각 사이트에 적절 한 대역폭 정책 프로필을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="e9640-119">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="e9640-120">전체 예제 토폴로지에 대 한 네트워크 사이트 만들기를 마치려면 EMEA 및 APAC 지역에서 대역폭이 제한 된 네트워크 사이트에 대해 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9640-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

