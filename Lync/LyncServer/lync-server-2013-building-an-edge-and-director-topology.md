---
title: 'Lync Server 2013: 에지 및 디렉터 토폴로지 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae45053e8d9c01cd484da8a052304712f04a06fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="037cf-102">Lync Server 2013에서 에지 및 디렉터 토폴로지 구성</span><span class="sxs-lookup"><span data-stu-id="037cf-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="037cf-103">_**마지막으로 수정한 주제:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="037cf-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="037cf-104">토폴로지 빌드에는 다음과 같은 계획 및 배포 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="037cf-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="037cf-105">**계획을 수립할**   때는 조직의 적절 한 토폴로지를 정의 하 고 배포에 필요한 구성 요소를 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="037cf-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="037cf-106">계획 프로세스의 표준 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="037cf-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="037cf-107">Microsoft Lync Server 2013, Lync Server 2013와 함께 제공 되는 계획 도구를 사용 하면 계획 프로세스를 쉽게 시작할 수 있을 뿐만 아니라 요구 사항과 계획이 완료 됨에 따라 쉽게 변경할 수 있는 기능을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="037cf-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="037cf-108">**배포**   토폴로지 작성기를 사용 하 여 정의한 토폴로지는 Lync server 2013 서버 배포에 반드시 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="037cf-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="037cf-109">계획 노력의 일부로 토폴로지 작성기를 사용 하 여 토폴로지 정의 및 게시를 완료 하지 않은 경우에는이를 완료 하 고 Edge 서버를 배포 하기 전에 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="037cf-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="037cf-110">하나 이상의 내부 풀을 구축할 때까지 Edge 서버 구성 요소를 배포할 수 없으며 내부 풀을 배포 하기 위해 토폴로지 작성기를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="037cf-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="037cf-111">이 섹션에서는 내부 풀에 대 한 설치 프로세스의 일부 이기 때문에 토폴로지 작성기 설치를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="037cf-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="037cf-112">이러한 도구에 대 한 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 대 한 배포 검사 목록을](lync-server-2013-deployment-checklist-for-external-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="037cf-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="037cf-113">이전에 edge 토폴로지를 비롯 한 토폴로지 작성기를 사용 하 여 전체 토폴로지를 정의한 경우 lync server <A href="lync-server-2013-define-your-edge-topology.md">2013에서 edge 토폴로지 정의</A> 를 건너뛰고이 섹션의 <A href="lync-server-2013-publish-your-topology.md">lync server 2013 작업에서 토폴로지를 게시할</A> 수 있지만 <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">lync server 2013 토폴로지 내보내기를 완료 하 고 edge 설치 작업을 위해 외부 미디어에 복사</A> 하는 것이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="037cf-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="037cf-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="037cf-114">In This Section</span></span>

  - [<span data-ttu-id="037cf-115">Lync Server 2013에서 에지 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="037cf-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="037cf-116">Lync Server 2013에 대한 토폴로지에서 선택적 디렉터 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="037cf-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="037cf-117">Lync Server 2013에서 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="037cf-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="037cf-118">Lync Server 2013 토폴로지 내보내기 및 에지 설치용 외부 미디어에 토폴로지 복사</span><span class="sxs-lookup"><span data-stu-id="037cf-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

