---
title: 'Lync Server 2013: CAC에 대 한 네트워크 지역 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acafaca86af1943d2614349ff42f04fa87faddaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="0d9a8-102">Lync Server 2013에서 CAC에 대 한 네트워크 지역 구성</span><span class="sxs-lookup"><span data-stu-id="0d9a8-102">Configure network regions for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d9a8-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0d9a8-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0d9a8-104">E9-1-1 또는 미디어 바이패스에 대 한 네트워크 지역을 이미 만든 경우에는 <STRONG>CsNetworkRegion</STRONG> cmdlet을 사용 하 여 CAC (통화 허용 제어)에 대 한 설정을 추가 하 여 기존 네트워크 지역을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-104">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="0d9a8-105">네트워크 지역을 수정 하는 방법에 대 한 예는 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync Server 2013에서 네트워크 지역 만들기 또는 수정을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-105">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="0d9a8-106">*네트워크 지역은* CAC, E9-1 및 미디어 바이패스를 구성 하는 데 사용 되는 네트워크 허브나 백본입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-106">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="0d9a8-107">다음 절차에 따라 CAC 용 네트워크 토폴로지 예제에서 네트워크 지역에 맞는 네트워크 지역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-107">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="0d9a8-108">예제 네트워크 토폴로지를 보려면 계획 설명서에서 [예제: Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-108">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="0d9a8-109">CAC의 네트워크 토폴로지 예에는 북미, EMEA 및 APAC 라는 세 가지 영역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-109">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="0d9a8-110">각 지역에는 지정 된 중앙 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-110">Each region has a specified central site.</span></span> <span data-ttu-id="0d9a8-111">북미 지역의 경우 지정 된 중앙 사이트 이름은 시카고입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-111">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="0d9a8-112">다음 절차에서는 **새 CsNetworkRegion** cmdlet을 사용 하 여 북미 지역을 만드는 방법의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-112">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d9a8-113">다음 절차에서는 Lync Server 관리 셸을 사용 하 여 네트워크 지역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-113">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="0d9a8-114">Lync Server 제어판을 사용 하 여 네트워크 지역을 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013에서 네트워크 지역 만들기 또는 수정을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-114">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="0d9a8-115">통화 허용 제어에 대 한 네트워크 지역 만들기</span><span class="sxs-lookup"><span data-stu-id="0d9a8-115">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="0d9a8-116">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0d9a8-117">만들어야 하는 각 지역에 대해 **새-CsNetworkRegion** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-117">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="0d9a8-118">예를 들어 북미 지역을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-118">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="0d9a8-119">2 단계를 반복 하 여 네트워크 지역 EMEA 및 APAC를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d9a8-119">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

