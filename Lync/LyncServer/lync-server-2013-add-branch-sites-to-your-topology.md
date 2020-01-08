---
title: 'Lync Server 2013: 토폴로지에 분기 사이트 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029627060ff03b804d0d2f76f40fdd4052f0d1c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="b22c1-102">Lync Server 2013에서 토폴로지에 분기 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="b22c1-102">Add branch sites to your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b22c1-103">_**마지막으로 수정한 주제:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="b22c1-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="b22c1-104">지점 사이트는 WAN 링크를 통해 메인 사무실에 연결 된 지사의 실제 지점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-104">Branch sites represent physical branch offices that are connected to your main offices over a WAN link.</span></span> <span data-ttu-id="b22c1-105">Lync 토폴로지에 분기 사이트를 추가 하려면 중앙 사이트에서이 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-105">To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="b22c1-106">토폴로지에 지점 사이트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="b22c1-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="b22c1-107">**시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server**를 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b22c1-108">콘솔 트리에서 중앙 사이트를 확장 하 고 **분기 사이트**를 마우스 오른쪽 단추로 클릭 한 다음 **새 분기 사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="b22c1-109">**새 분기 사이트 정의** 대화 상자에서 **이름을**클릭 한 다음 분기 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="b22c1-110">) **설명을**클릭 한 다음 분기 사이트에 대 한 의미 있는 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="b22c1-111">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-111">Click **Next**.</span></span>

6.  <span data-ttu-id="b22c1-112">) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="b22c1-113">**도시**를 클릭 한 다음 지점 사이트가 있는 도시의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="b22c1-114">**상태/지역을**클릭 한 다음 분기 사이트가 있는 상태 또는 지역의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="b22c1-115">**국가 코드**를 클릭 한 다음 분기 사이트가 있는 국가/지역에 대 한 두 자리 통화 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="b22c1-116">**다음**을 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="b22c1-117">이 사이트에서 Survivable Branch 기기 또는 서버를 사용 하는 경우 **마법사를 닫을 때 새 Survivable 마법사 열기** 확인란을 선택 하 고 **마침을**클릭 한 다음 마법사에서 열리는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="b22c1-118">마법사 항목에 대 한 자세한 내용은 [Lync Server 2013에서 Survivable Branch 기기 또는 서버 정의](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b22c1-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="b22c1-119">이 사이트에서 Survivable Branch 기기 또는 서버를 사용 하 고 있지 않은 경우 마법사를 **닫을 때 새 Survivable 마법사 열기** 확인란의 선택을 취소 하 고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="b22c1-120">토폴로지에 추가 하려는 각 분기 사이트에 대해 앞의 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="b22c1-121">**다음 단계:**</span><span class="sxs-lookup"><span data-stu-id="b22c1-121">**Next step:**</span></span>

<span data-ttu-id="b22c1-122">Survivable Branch 기기 또는 서버의 경우: [Lync Server 2013에서 Survivable Branch 기기 또는 서버 정의](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="b22c1-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="b22c1-123">회복성 있지 않은 PSTN 연결의 경우: [Lync server 2013에서 지점 사이트에 대 한 PSTN 게이트웨이를 정의](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)하 고, [lync server 2013에서 미디어 바이패스를 사용 하 여 트렁크를 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)하거나, [lync server 2013에서 미디어 바이패스 없이 트렁크를 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="b22c1-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

