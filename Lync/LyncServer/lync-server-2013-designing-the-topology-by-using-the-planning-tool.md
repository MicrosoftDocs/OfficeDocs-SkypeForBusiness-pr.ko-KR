---
title: 'Lync Server 2013: 계획 도구를 사용 하 여 토폴로지 디자인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09cfa16103f4e6e2ebfa2327edbd330311753609
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="105c4-102">계획 도구를 사용 하 여 Lync Server 2013에 대 한 토폴로지 디자인</span><span class="sxs-lookup"><span data-stu-id="105c4-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="105c4-103">_**마지막으로 수정한 주제:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="105c4-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="105c4-104">Microsoft Lync Server 2013의 계획 도구는 디자인 중인 Lync Server 2013 토폴로지에 대해 질문을 하는 마법사 기반 인터뷰 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="105c4-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="105c4-105">계획 도구는 제공 되는 정보를 사용 하 여 토폴로지 디자인 및 용량에 대 한 기본 방법과 결합 하 여 제공 된 답변에 따라 추천 토폴로지를 제시 합니다.</span><span class="sxs-lookup"><span data-stu-id="105c4-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="105c4-106">Microsoft 다운로드 센터 ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725))에서 계획 도구를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="105c4-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="105c4-107">계획 도구의 목표는 궁극적으로 Lync Server 2013 토폴로지를 디자인 하는 것이 잠재적인 복잡성을 줄이기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="105c4-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="105c4-108">또한이 도구는 Microsoft TechNet 웹 사이트에 연결 하는 데 인터넷 연결을 사용할 수 있는 경우 도구 내부의 계획 및 배포 설명서에 대 한 상황별 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="105c4-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="105c4-109">인프라의 TCP/IP 주소와 Fqdn (정규화 된 도메인 이름)을 사용 하 여 토폴로지를 사용자 지정한 후에는 계획 도구에서 DNS (Domain Name System) 명명, 방화벽 규칙, 인증서 등을 다루는 일련의 보고서를 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="105c4-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="105c4-110">계획 도구는 다음 두 가지 형식의 정보를 내보내는 기능도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="105c4-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="105c4-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="105c4-111">Microsoft Excel</span></span>

  - <span data-ttu-id="105c4-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="105c4-112">Microsoft Visio</span></span>

<span data-ttu-id="105c4-113">다음 항목에서는 계획 도구를 소개 하 고 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="105c4-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="105c4-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="105c4-114">In This Section</span></span>

  - [<span data-ttu-id="105c4-115">Lync Server 2013에서 계획 도구 설치</span><span class="sxs-lookup"><span data-stu-id="105c4-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="105c4-116">Lync Server 2013에서 선택적 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="105c4-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="105c4-117">Lync Server 2013에서 계획 도구 탐색</span><span class="sxs-lookup"><span data-stu-id="105c4-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="105c4-118">Lync Server 2013의 초기 토폴로지 디자인 만들기</span><span class="sxs-lookup"><span data-stu-id="105c4-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="105c4-119">Lync Server 2013에서 관리자 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="105c4-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="105c4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="105c4-120">See Also</span></span>


[<span data-ttu-id="105c4-121">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="105c4-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="105c4-122">Lync Server 2013의 프런트 엔드 서버, 메신저 및 현재 상태 계획</span><span class="sxs-lookup"><span data-stu-id="105c4-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

