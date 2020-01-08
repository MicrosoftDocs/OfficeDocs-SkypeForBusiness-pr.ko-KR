---
title: Lync Server 2013 확장성 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f454ad3d78affb7106bcd0e750adae13624d9c9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="c2c2e-102">Lync Server 2013의 확장성 테스트</span><span class="sxs-lookup"><span data-stu-id="c2c2e-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2c2e-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c2c2e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c2c2e-104">Lync Server 2013는 IM (인스턴트 메시징) 및 현재 상태, 회의, 엔터프라이즈 음성을 비롯 한 모든 Lync Server 실시간 통신에 대 한 서버 인프라를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="c2c2e-105">여기에는 Lync Server 2013 풀의 하드웨어 리소스를 사용 하는 모든 기능이 포함 되어 있으므로 성능 및 배율에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="c2c2e-106">모든 조직은 모든 기능을 동등 하 게 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="c2c2e-107">예를 들어 일부 조직의 경우 매우 많은 양의 회의에서 비디오를 사용할 수 있으며, 다른 사용자는 영상 사용이 거의 없거나 전혀 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="c2c2e-108">일부 조직에서는 PowerPoint 슬라이드를 응용 프로그램 공유에 공유 하 고 다른 사용자는 반대쪽을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="c2c2e-109">엔터프라이즈 음성을 배포 하는 조직에서는 응답 그룹 응용 프로그램을 크게 사용 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="c2c2e-110">대부분의 조직에서는 모니터링 서버를 배포 하지만 대부분의 조직은 보관 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="c2c2e-111">또한 조직에는 하드웨어 용량, 네트워크 용량, 배포 된 풀의 수 및 크기를 비롯 하 여 모두 동일한 인프라가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="c2c2e-112">다양 한 기능과 인프라를 통해 확장성 테스트를 할 수 있으며, 모든 기능을 사용할 수 있는 기능과 인프라의 모든 조합을 시뮬레이트하는 것은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="c2c2e-113">Lync Server에 대 한 확장성 지원을 확인 하려면 평균 사용 모델 (사용자 모델)에 따라 모든 Lync Server 기능을 동시에 사용 하 여 테스트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="c2c2e-114">Lync Server 작업에 적합 한 사용자 모델을 결정 하기 위해 고객의 설문 조사, Microsoft 사용자 환경 개선 프로그램의 피드백, Microsoft의 내부 IT 부서에서 제공 하는 Lync Server 사용 데이터 등 다양 한 데이터 요소를 분석 합니다. Live Meeting 서비스에서 찾은 데이터</span><span class="sxs-lookup"><span data-stu-id="c2c2e-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="c2c2e-115">대부분의 경우 사용자 모델에는 더 무거운 부하를 보정 하 여 조직 내에서 사용 하기에 적합 한 여백을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="c2c2e-116">이 확장성 테스트에서는 Active Directory 도메인 서비스, 하드웨어 부하 분산 장치, 방화벽 등의 인프라 구성 요소를 포함 하 여 권장 하드웨어 및 소프트웨어 사양에 따라 Lync Server 2013 풀을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="c2c2e-117">Lync 서버 환경을 일반적인 실제 환경과 최대한 유사 하 게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="c2c2e-118">그런 다음 Lync Server 2013 스트레스 및 성능 도구를 사용 하 여 Lync Server 2013 부하를 시뮬레이트합니다 (사용자 모델에 기반).</span><span class="sxs-lookup"><span data-stu-id="c2c2e-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="c2c2e-119">.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-119"></span></span>

<span data-ttu-id="c2c2e-120">여러 3 주 테스트 실행을 비롯 한 확장성 테스트의 여러 번 반복을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-120">We do multiple iterations of scalability tests (including multiple three-week test runs).</span></span> <span data-ttu-id="c2c2e-121">성능 조정을 위해 모든 테스트의 결과를 사용 하 고 사용자 모델의 확장성 번호에 대 한 지원을 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2c2e-121">We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

