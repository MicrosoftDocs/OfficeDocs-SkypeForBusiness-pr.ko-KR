---
title: 'Lync Server 2013: 네트워크 지역 링크 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ef56e2b71e1692b4343515613dec37b2a30621b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="390d1-102">Lync Server 2013에서 네트워크 지역 링크 만들기</span><span class="sxs-lookup"><span data-stu-id="390d1-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="390d1-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="390d1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="390d1-p101">네트워크 내의 지역은 실제 WAN 연결을 통해 연결됩니다. *네트워크 지역 링크*는 CAC(통화 허용 제어)에 대해 구성된 두 개의 지역 간 링크를 만들며, 이 지역 간 오디오 및 비디오 트래픽에 대한 대역폭 제한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-p101">Regions within a network are linked through physical WAN connectivity. A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="390d1-106">네트워크 지역 링크 작업에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="390d1-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="390d1-107">새-Csnetwork지역 링크</span><span class="sxs-lookup"><span data-stu-id="390d1-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="390d1-108">Get-Csnetwork지역 링크</span><span class="sxs-lookup"><span data-stu-id="390d1-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="390d1-109">설정-Csnetwork지역 링크</span><span class="sxs-lookup"><span data-stu-id="390d1-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="390d1-110">-Csnetwork지역 링크 제거</span><span class="sxs-lookup"><span data-stu-id="390d1-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="390d1-111">이 토폴로지 예에는 북미와 APAC 지역 간 링크 및 EMEA와 APAC 지역 간 링크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="390d1-112">이러한 각 지역 링크는 계획 설명서의 [Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 섹션의 지역 링크 대역폭 정보 표에서 설명 하는 대로 WAN 대역폭에 따라 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="390d1-113">Lync Server 관리 셸을 사용하여 네트워크 지역 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="390d1-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="390d1-114">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="390d1-p103">New-CsNetworkRegionLink cmdlet를 실행하여 지역 링크를 만들고 적합한 대역폭 정책 프로필을 적용합니다. 예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-p103">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles. For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="390d1-117">Lync Server 제어판을 사용하여 네트워크 지역 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="390d1-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="390d1-118">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="390d1-119">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="390d1-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="390d1-120">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="390d1-121">**지역 링크** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="390d1-122">**새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-122">Click **New**.</span></span>

5.  <span data-ttu-id="390d1-123">**새 지역 링크** 페이지에서 **이름**을 클릭하고 네트워크 지역 링크에 대한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="390d1-124">**네트워크 지역 \#1**을 클릭 하 고 목록에서 네트워크 지역 \#2에 연결할 네트워크 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="390d1-125">**네트워크 지역 \#2**를 클릭 하 고 목록에서 네트워크 지역 \#1에 연결할 네트워크 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="390d1-126">(선택 사항) **대역폭 정책**을 클릭하고 네트워크 지역 링크에 적용할 대역폭 정책 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="390d1-127">네트워크 지역 링크에 대역폭 제한이 있고 CAC를 사용하여 해당 링크에 대해 미디어 트래픽을 제어할 경우에만 대역폭 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="390d1-128">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-128">Click **Commit**.</span></span>

10. <span data-ttu-id="390d1-129">토폴로지에 대한 네트워크 지역 링크 만들기를 종료하려면 다른 지역에 대한 설정을 사용하여 4-9단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="390d1-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
