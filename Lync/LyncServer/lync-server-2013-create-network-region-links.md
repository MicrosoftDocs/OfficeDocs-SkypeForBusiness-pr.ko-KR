---
title: 'Lync Server 2013: 네트워크 지역 링크 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c0f21f599b8afa4f9f31ec16aad82e305c8a08e
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40983116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="bcf57-102">Lync Server 2013에서 네트워크 지역 링크 만들기</span><span class="sxs-lookup"><span data-stu-id="bcf57-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcf57-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="bcf57-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="bcf57-104">네트워크 내의 영역은 실제 WAN 연결을 통해 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-104">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="bcf57-105">*네트워크 지역 링크* 는 CAC (호출 허용 제어)에 대해 구성 된 두 지역 간에 링크를 만들고 이러한 지역 간의 오디오 및 비디오 트래픽에 대 한 대역폭 제한을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-105">A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="bcf57-106">네트워크 지역 링크 작업에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcf57-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="bcf57-107">새-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="bcf57-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="bcf57-108">Get-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="bcf57-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="bcf57-109">Set-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="bcf57-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="bcf57-110">-Csnetwork국가 링크 제거</span><span class="sxs-lookup"><span data-stu-id="bcf57-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="bcf57-111">이 예제 토폴로지에는 북미와 APAC 지역 간의 링크와 EMEA와 APAC 지역 간의 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="bcf57-112">이러한 지역 링크는 다음 예의 지역 링크 대역폭 정보 표에 설명 된 대로 WAN 대역폭에 따라 제한 되며, 계획 설명서의 [Lync Server 2013 섹션에서 통화 허용 제어에 대 한 요구 사항을 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="bcf57-113">Lync Server Management Shell을 사용 하 여 네트워크 지역 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="bcf57-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="bcf57-114">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bcf57-115">새-Csnetworkregion 링크 cmdlet을 실행 하 여 지역 링크를 만들고 적절 한 대역폭 정책 프로필을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-115">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="bcf57-116">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-116">For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="bcf57-117">Lync Server 제어판을 사용 하 여 네트워크 지역 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="bcf57-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bcf57-118">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bcf57-119">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcf57-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="bcf57-120">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="bcf57-121">**지역 링크** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="bcf57-122">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-122">Click **New**.</span></span>

5.  <span data-ttu-id="bcf57-123">**새 지역 링크** 페이지에서 **이름을** 클릭 한 다음 네트워크 지역 링크의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="bcf57-124">**네트워크 지역 \#1**을 클릭 한 다음 목록에서 네트워크 지역 \#2에 연결할 네트워크 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="bcf57-125">**네트워크 지역 \#2**를 클릭 한 다음 목록에서 네트워크 지역 \#1에 연결할 네트워크 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="bcf57-126">필요에 따라 **대역폭 정책을**클릭 한 다음 네트워크 지역 링크에 적용 하려는 대역폭 정책 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="bcf57-127">네트워크 지역 링크에 대역폭이 제한 되어 있고 CAC를 사용 하 여 해당 링크의 미디어 트래픽을 제어 하려는 경우에만 대역폭 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="bcf57-128">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-128">Click **Commit**.</span></span>

10. <span data-ttu-id="bcf57-129">토폴로지에 대 한 네트워크 지역 링크 만들기를 마치려면 다른 지역에 대 한 설정을 사용 하 여 4 ~ 9 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf57-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
