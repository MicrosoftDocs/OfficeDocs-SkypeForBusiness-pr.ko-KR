---
title: 'Lync Server 2013: 서비스 수준 계약'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ae1a80975cf13030e51d711f00a70b80a54718
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="9cfcd-102">Lync Server 2013의 서비스 수준 계약</span><span class="sxs-lookup"><span data-stu-id="9cfcd-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cfcd-103">_**마지막으로 수정 된 항목:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="9cfcd-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="9cfcd-104">SLA는 고객이 기대 하는 서비스를 정의 하는 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="9cfcd-105">이 문서의 복잡도와 콘텐츠는 고객이 내부 (환경 내) 인지 외부에 있는지 여부에 따라 크게 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="9cfcd-106">외부 고객</span><span class="sxs-lookup"><span data-stu-id="9cfcd-106">External Customers</span></span>

<span data-ttu-id="9cfcd-107">고객이 외부에 있는 경우 SLA는 정의 된 서비스 수준에 해당 하는 성능에 대 한 재정 및 페널티의 법적 계약에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="9cfcd-108">이러한 서비스 수준을 정의 하는 것은 전체 계약 협상에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="9cfcd-109">모든 계약과 마찬가지로 두 당사자가 기대치를 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="9cfcd-110">SLA는 이러한 기대치를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-110">The SLA defines these expectations.</span></span> <span data-ttu-id="9cfcd-111">문서의 내용은 고객과의 협상으로 인해 자주 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="9cfcd-112">내부 고객</span><span class="sxs-lookup"><span data-stu-id="9cfcd-112">Internal Customers</span></span>

<span data-ttu-id="9cfcd-113">고객이 내부에 있는 경우에도 운영 팀과 IT 시스템에서 예상 되는 서비스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="9cfcd-114">SLA는 운영 직원 들이 만들 수 있으며, 조직 내 IT 서비스의 가용성을 위한 목표 집합으로 예정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="9cfcd-115">또는 관리를 통해 성능 수준을 설정 하 여 직원의 성과를 평가할 때 벤치 마크로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="9cfcd-116">일반 조건</span><span class="sxs-lookup"><span data-stu-id="9cfcd-116">Typical Criteria</span></span>

<span data-ttu-id="9cfcd-117">Sla에는 최소 수준의 가용성, 지원 및 용량 기준을 정의 하는 섹션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="9cfcd-118">**가용성**   사이트 및 기타 Lync services를 사용할 수 있는 시간 및 운영 체제를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="9cfcd-119">서비스 가용성에 영향을 주는 모든 루틴 유지 관리는 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="9cfcd-120">서비스에 영향을 주는 외부 요인 (예: 인터넷 연결 손실)을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="9cfcd-121">**지원**   시스템에 대 한 지원이 제공 되는 시간을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="9cfcd-122">고객이 지원 담당자에 게 연락 하 고, 인시던트를 그룹화 하 고, 응답 하 고, 문제를 해결할 시간을 지정할 수 있는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="9cfcd-123">고객에 대 한 의견의 빈도 및 콘텐츠를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="9cfcd-124">**용량은**   Lync 사이트의 최대 사용 가능 크기와 제한 값을 초과 하는 경우 수행할 단계를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="9cfcd-125">표준 작업을 수행 하는 데 사용할 수 있는 최대 시간 (예: 문서 라이브러리에서 문서를 검색 하는 시간)을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="9cfcd-126">Lync 풀 당 최대 사용자 수를 정의 하 고 더 많은 사용자를 추가할 경우 용량을 늘리기 위해 프로세스에 동의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cfcd-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

