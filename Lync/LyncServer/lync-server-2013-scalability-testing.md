---
title: Lync Server 2013 확장성 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4495524d7ac4e6348f86b84a8b5f860bd9a1db3f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="c2a28-102">Lync Server 2013의 확장성 테스트</span><span class="sxs-lookup"><span data-stu-id="c2a28-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2a28-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c2a28-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c2a28-104">Lync Server 2013에서는 IM (인스턴트 메시징) 및 현재 상태, 회의 및 Enterprise Voice를 비롯 한 모든 Lync Server 실시간 통신에 대 한 서버 인프라를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="c2a28-105">여기에는 Lync Server 2013 풀의 하드웨어 리소스를 사용 하는 모든 기능이 포함 되며, 따라서 성능 및 확장에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="c2a28-106">조직에 따라 기능을 사용하는 방식이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="c2a28-107">예를 들어 일부 조직에서는 너무 많이 전화 회의에서 비디오를 사용할 수도 있고, 일부 경우에는 비디오 사용이 거의 없거나 전혀 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="c2a28-108">일부 조직은 PowerPoint 슬라이드 공유에 응용 프로그램 공유를 선호 하지만 그 반대를 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="c2a28-109">Enterprise Voice를 배포 하는 조직은 응답 그룹 응용 프로그램을 크게 사용 하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="c2a28-110">대부분의 조직은 모니터링 서버를 배포 하지만 대부분의 조직에서는 보관 서버를 배포 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="c2a28-111">또한 조직에는 하드웨어 용량, 네트워크 용량, 배포 된 풀 수 및 크기와 같은 인프라가 모두 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="c2a28-112">기능 및 인프라의 다양성은 확장성 테스트를 위한 과제 이며, 모든 가능한 기능 및 인프라 조합을 시뮬레이션할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="c2a28-113">Lync Server에 대 한 확장성 지원을 확인 하기 위해 평균 사용 모델 (사용자 모델)을 기반으로 모든 Lync Server 기능을 동시에 사용 하 여 테스트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="c2a28-114">Lync Server 작업에 적합 한 사용자 모델을 결정 하기 위해 Microsoft는 고객 환경 개선 프로그램의 피드백, Microsoft의 내부 IT 부서에서 제공 하는 Lync Server usage data 등의 다양 한 데이터 요소를 분석 합니다. Live Meeting 서비스에서 찾은 데이터</span><span class="sxs-lookup"><span data-stu-id="c2a28-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="c2a28-115">대부분의 경우 사용자 모델은 조직에 넉넉한 사용 여유를 제공하도록 보다 큰 부하를 위주로 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="c2a28-116">이 확장성 테스트에서는 Active Directory 도메인 서비스, 하드웨어 부하 분산 장치 및 방화벽과 같은 인프라 구성 요소를 비롯 하 여 권장 되는 하드웨어 및 소프트웨어 사양에 따라 Lync Server 2013 풀을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="c2a28-117">일반적인 실제 환경에 최대한 근접 하 게 Lync Server 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="c2a28-118">그런 다음 Lync Server 2013 스트레스 및 성능 도구를 사용 하 여 Lync Server 2013 부하를 시뮬레이트할 수 있습니다 (사용자 모델에 따라).</span><span class="sxs-lookup"><span data-stu-id="c2a28-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="c2a28-119">.</span><span class="sxs-lookup"><span data-stu-id="c2a28-119">.</span></span>

<span data-ttu-id="c2a28-p105">Microsoft에서는 3주에 걸친 여러 차례의 테스트 실행을 포함하여 확장성 테스트를 여러 번 반복하며, 모든 테스트 결과를 사용하여 성능 조정을 개선하고 사용자 모델의 확장성 수치가 지원되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a28-p105">We do multiple iterations of scalability tests (including multiple three-week test runs). We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

