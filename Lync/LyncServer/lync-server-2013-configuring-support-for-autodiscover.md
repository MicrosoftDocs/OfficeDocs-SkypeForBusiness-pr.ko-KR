---
title: 'Lync Server 2013: 자동 검색 지원 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3893ddd2282fd6abdfff716207f99102d09fac31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507545"
---
# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="0f7aa-102">Lync Server 2013에서 자동 검색 지원 구성</span><span class="sxs-lookup"><span data-stu-id="0f7aa-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f7aa-103">_**마지막으로 수정 된 항목:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="0f7aa-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="0f7aa-104">Lync Server 웹 서비스 **자동 검색 서비스** 는 먼저 lync Server 2010 누적 업데이트: 11 월 2011에 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="0f7aa-105">이 업데이트는 Lync 모바일 클라이언트의 초기 릴리스와 함께 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="0f7aa-106">자동 검색 서비스는 Mcx 서비스 라는 이동성 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="0f7aa-107">자동 검색 서비스는 모든 클라이언트가 사용할 수 있는 서비스 및 기능에 대 한 정보를 요청 하 고, 정규화 된 도메인 이름 또는 웹 uniform resource locator 참조를 통해 sevices에 연락 하는 방법에 대 한 단일 위치 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="0f7aa-108">자동 검색 기능은 여러 기능을 제공 하며, 각 클라이언트는 클라이언트에서 사용할 수 있는 기능을 기반으로 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="0f7aa-109">예를 들어 데스크톱 Lync 2013 클라이언트는 autodiscvoer을 사용 하 여 외부 웹 서비스를 확인 하지만 mobility (Mcx) 서비스는 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="0f7aa-110">클라이언트에서 사용할 수 있는 기능을 올바르게 정의 하 고 사용 하도록 설정 하려면 클라이언트가 자동 검색 항목을 효과적으로 찾고 사용할 수 있도록 하는 시나리오를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="0f7aa-111">Autodoscover를 사용 하려면 배포에 역방향 프록시가 Lync server 웹 서비스를 게시 하 고, 해당 DNS 레코드가 Lync Server 자동 검색 서비스 및 Lync Server 웹 서비스에 대 한 DNS 쿼리를 확인 하도록 구성 되어 있으며, 해당 인증서 서비스가 특정 시나리오에 맞게 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0f7aa-112">자동 검색 요청/응답 내의 요소에 대 한 기술 정보는 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013의 자동 검색 이해</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="0f7aa-113">다음 정보와 테이블은 자동 검색 서비스의 전체 및 효과적인 사용을 제공 하기 위해 구현 해야 하는 구성 (있는 경우)을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="0f7aa-114">다음 항목에는 Microsoft Lync Server 2013에 대 한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7aa-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="0f7aa-115">Lync Server 2010에 대 한 모바일 기능을 계획 하는 방법에 대 한 지침은를 참조 하세요 [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113) .</span><span class="sxs-lookup"><span data-stu-id="0f7aa-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="0f7aa-116">Lync Server 2010에 대 한 모바일 기능을 배포 하려면를 참조 하세요. [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="0f7aa-116">To deploy Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f7aa-117">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="0f7aa-117">In This Section</span></span>

  - [<span data-ttu-id="0f7aa-118">Lync Server 2013에서 자동 검색을 위한 DNS 구성</span><span class="sxs-lookup"><span data-stu-id="0f7aa-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="0f7aa-119">Lync Server 2013에서 자동 검색에 대 한 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="0f7aa-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="0f7aa-120">Lync Server 2013에서 자동 검색을 위한 역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="0f7aa-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="0f7aa-121">Lync Server 2013에서 하이브리드 배포에 대 한 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="0f7aa-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

