---
title: 'Lync Server 2013: 네트워크 구성 다이어그램 편집'
description: 'Lync Server 2013: 네트워크 구성 다이어그램을 편집 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead2b0b47ec0cb0a98c33d7fff0a644f05f92c71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570594"
---
# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="3aeec-103">Lync Server 2013에서 네트워크 구성 다이어그램 편집</span><span class="sxs-lookup"><span data-stu-id="3aeec-103">Editing the network configuration diagram in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3aeec-104">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3aeec-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3aeec-105">디자이너가 Lync Server 2013에서 수행 하는 대부분의 작업은 계획 도구에서 IP 주소에 대 한 항목과 네트워크 다이어그램의 항목에 대 한 Fqdn (정규화 된 도메인 이름)을 정의 하는 것으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-105">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="3aeec-106">이 페이지에서 입력 한 정보는 계획 도구에 포함 된 보고서 및 기타 정보로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-106">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="3aeec-107">![계획 도구 네트워크 다이어그램](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "계획 도구 네트워크 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="3aeec-107">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="3aeec-108">계획 도구는 IP 주소 및 Fqdn에 대 한 기본 텍스트가 포함 된 네트워크 다이어그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-108">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="3aeec-109">네트워크 다이어그램과 입력 값을 편집하려면</span><span class="sxs-lookup"><span data-stu-id="3aeec-109">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="3aeec-110">작업을 시작할 네트워크 섹션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-110">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="3aeec-111">예를 들어 **access1.contoso.com**텍스트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-111">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="3aeec-112">열리는 대화 상자에서 서버 access1.contoso.com의 실제 FQDN과 실제 IP 주소를 입력 하 고 131.107.155.3를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-112">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="3aeec-113">**확인**을 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-113">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="3aeec-114">하드웨어 부하 분산 장치의 가상 IP 주소를 제공하거나 풀의 서버에 대한 DNS(Domain Name System) 부하 분산용 서버 항목을 제공하여 IP 주소 및 FQDN을 계속 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-114">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="3aeec-p103">계획 도구의 유용한 기능은 디자이너가 풀의 각 서버를 별도로 편집할 필요 없이 IP 주소 범위 및 서버 호스트 이름을 점진적으로 할당할 수 있다는 것입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="3aeec-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="3aeec-117">풀링된 프런트 엔드 서버를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-117">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="3aeec-118">대화 상자가 열리면 **IP 및 FQDN을 이 클러스터에 있는 모든 동일한 서버의 시작 지점으로 사용하시겠습니까?** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-118">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="3aeec-119">예를 들어 첫 번째 서버의 시작 값은 fe0101.contoso.com이 고 IP 주소는 192.168.21.122입니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-119">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="3aeec-120">**프런트 엔드 서버 FQDN**에 **fe0.contoso.com** 을 입력 하 고 **프런트 엔드 서버 IP 주소**에 **192.168.21.131** 를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-120">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="3aeec-121">자동 증분 기능은 풀에 있는 모든 서버를 fe01를 통해 f e으로 업데이트 하 고, 192.168.21.131에서 136 까지의 모든 IP 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-121">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="3aeec-122">모든 편집을 완료 한 후에는 다음 단계를 완료 하 여 토폴로지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-122">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="3aeec-123">계획 도구 디자인을 저장 하려면 **파일**을 클릭 하 고 **토폴로지 저장** 또는 **토폴로지를 다른 이름으로 저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-123">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="3aeec-124">**다른 이름으로 계획 도구 저장** 대화 상자가 나타나면 **파일 이름**에 파일 이름을 입력한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3aeec-124">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3aeec-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3aeec-125">See Also</span></span>


[<span data-ttu-id="3aeec-126">Lync Server 2013에서 디자인 편집</span><span class="sxs-lookup"><span data-stu-id="3aeec-126">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

