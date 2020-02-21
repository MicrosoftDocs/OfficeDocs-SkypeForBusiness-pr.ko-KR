---
title: Lync Server 2013:에 지 서버에 IP 주소 유형 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400a7ab688b3fae4c7bded753341d4d04d0fd835
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="b7deb-102">Lync Server 2013에 대 한에 지 서버에 IP 주소 유형 배포</span><span class="sxs-lookup"><span data-stu-id="b7deb-102">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7deb-103">_**마지막으로 수정 된 항목:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="b7deb-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="b7deb-104">토폴로지 작성기를 사용 하 여에 지 서버에 IP 주소 유형을 배포 하려면 다음 절차의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="b7deb-105">에 지 서버에 IP 주소 유형을 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="b7deb-105">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="b7deb-106">토폴로지 작성기의에 **지 풀**에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-106">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="b7deb-107">또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="b7deb-108">**속성 편집** 창에서 지원 하려는 IP 주소 구성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-108">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span> <span data-ttu-id="b7deb-109">다음 그림에서는 내부 인터페이스 및 외부 인터페이스에 대 한 이중 스택 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-109">The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="b7deb-110">**이중 스택 되는에 지 서버 내부 인터페이스**</span><span class="sxs-lookup"><span data-stu-id="b7deb-110">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="b7deb-111">![Lync Server 일반 속성 페이지](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server 일반 속성 페이지")</span><span class="sxs-lookup"><span data-stu-id="b7deb-111">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="b7deb-112">**이중 스택 되는에 지 서버 외부 인터페이스**</span><span class="sxs-lookup"><span data-stu-id="b7deb-112">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="b7deb-113">![Lync Server 다음 홉/외부 구성 페이지](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server 다음 홉/외부 구성 페이지")</span><span class="sxs-lookup"><span data-stu-id="b7deb-113">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="b7deb-114">선택한 각 주소 유형에 대해 적합 한 내부 및 외부 주소를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-114">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

