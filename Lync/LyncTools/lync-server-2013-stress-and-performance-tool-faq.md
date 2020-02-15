---
title: Lync Server 2013 스트레스 및 성능 도구 FAQ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9de9555f9f009558b700a32ca6e58059eb5ea990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="b080b-102">Lync Server 2013 스트레스 및 성능 도구 FAQ</span><span class="sxs-lookup"><span data-stu-id="b080b-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b080b-103">_**마지막으로 수정 된 항목:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="b080b-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="b080b-104">FAQ</span><span class="sxs-lookup"><span data-stu-id="b080b-104">Frequently Asked Questions</span></span>

<span data-ttu-id="b080b-105">Lync Server 2013 스트레스 및 성능 도구에 대 한 몇 가지 질문과 대답이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="b080b-106">프로덕션 환경에서는 LyncPerfTool를 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="b080b-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="b080b-107">이 방법은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-107">We do not recommend this.</span></span> <span data-ttu-id="b080b-108">이 도구는 서버 성능, 보안 및 사용자 환경에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="b080b-109">처음으로 사용자를 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="b080b-110">서버가 이러한 높은 부하에서 실행 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b080b-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="b080b-111">사용자가 처음 로그온 할 때 추가 작업이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="b080b-112">따라서 Microsoft SQL Server 백 엔드 서버의 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="b080b-113">모든 사용자에 대해 기록 되는 짧은 테스트를 실행 한 다음 결과를 측정 하기 전에 클라이언트를 다시 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="b080b-114">초당 12 개 이상의 동시 사용자 로그온 세션은 지원 되지 않지만 하드웨어 구성에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="b080b-115">클라이언트에 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-115">My clients are running out of memory.</span></span> <span data-ttu-id="b080b-116">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="b080b-116">What should I do?</span></span>

<span data-ttu-id="b080b-117">클라이언트에 메모리가 부족 한 경우 컴퓨터당 사용자 수를 줄여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="b080b-118">클라이언트는 항상 100%의 CPU에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="b080b-119">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="b080b-119">What should I do?</span></span>

<span data-ttu-id="b080b-120">모든 사용자가 로그온 한 후에 클라이언트가 매우 높은 CPU로 실행 되는 경우 컴퓨터당 사용자 수를 줄여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="b080b-121">높은 CPU 스파이크는 사용할 수 있지만 지속적인 경우에는 부하를 줄여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="b080b-122">서버에서 도구를 실행할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="b080b-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="b080b-123">아니요.</span><span class="sxs-lookup"><span data-stu-id="b080b-123">No.</span></span> <span data-ttu-id="b080b-124">이 시나리오는 지원 되지 않으며 이진 불일치로 인해 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="b080b-125">또한 서버에서 리소스 소비를 측정 하는 것 이므로 도구를 실행 하면 측정이 의미가 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="b080b-126">가상 서버나 Microsoft Hyper-v Server 2008/2012에서 LyncPerfTool를 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="b080b-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="b080b-127">예.</span><span class="sxs-lookup"><span data-stu-id="b080b-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="b080b-128">MPOP 무슨 의미 입니까?</span><span class="sxs-lookup"><span data-stu-id="b080b-128">What does MPOP mean?</span></span>

<span data-ttu-id="b080b-129">MPOP는 여러 개의 현재 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="b080b-130">이는 사용자가 여러 컴퓨터에서 Lync 2013에 로그온 하는 시나리오를 시뮬레이션 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="b080b-131">LyncPerfTool 각 끝점은 기본 프로필을 사용 합니다 (즉, 프로필이 두 개의 현재 상태 사이에 분할 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="b080b-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="b080b-132">LyncPerfTool를 시작 했지만 아무 일도 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="b080b-133">어떻게 된 것일까요?</span><span class="sxs-lookup"><span data-stu-id="b080b-133">What’s going on?</span></span>

<span data-ttu-id="b080b-134">사용자가 연결 되어 있는지 여부를 확인 하려면 클라이언트의 총 활성 끝점 카운터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="b080b-135">사용자가 연결 되어 있지 않으면 Lync Server 2013 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="b080b-136">이 문제는 일반적으로 서버 이름, 사용자 접두사 또는 암호가 잘못 되었기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="b080b-137">외부 클라이언트는 액세스 프록시를 TargetServer 값으로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="b080b-138">구성 파일의 포트를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="b080b-139">어떤 일이 진행 되 고 있는지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="b080b-139">How do I know something is happening?</span></span>

<span data-ttu-id="b080b-140">다양 한 LyncPerfTool 성능 카운터는 사용자가 연결 하 고 작업을 수행 하 고 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="b080b-141">그러나 쉽게 확인할 수 있는 방법은 Lync 2013을 사용 하 여 계정 중 하나에 로그온 하 고 원하는 작업을 수행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="b080b-142">Live Communications Server 2007 R2 용량 계획 도구 및/또는 Lync Server 2010가 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="b080b-143">정상 인가요?</span><span class="sxs-lookup"><span data-stu-id="b080b-143">Is that OK?</span></span>

<span data-ttu-id="b080b-144">아니요.</span><span class="sxs-lookup"><span data-stu-id="b080b-144">No.</span></span> <span data-ttu-id="b080b-145">상호 운용성 문제가 있으므로이 제품의 이전 버전을 모두 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="b080b-146">스트레스 및 성능 도구에서 CAA 통화 정보 서버 토폴로지를 설정 합니까?</span><span class="sxs-lookup"><span data-stu-id="b080b-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="b080b-147">아니요.</span><span class="sxs-lookup"><span data-stu-id="b080b-147">No.</span></span> <span data-ttu-id="b080b-148">이 도구는 사용자, 연락처 및 메일 목록만 만들고 사용자 부하를 시뮬레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="b080b-149">도구에서 지 원하는 최대 사용자 수는 얼마나 됩니까?</span><span class="sxs-lookup"><span data-stu-id="b080b-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="b080b-150">이 도구를 사용 하 여 총 8만 명의 사용자를 만들고 전체 3만 사용자 테스트를 실행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="b080b-151">기술적 제한은 사용 가능한 클라이언트 및 서버 하드웨어에 따라 값이 더 높다는 것을 허용 하지만 최대 12만 명의 사용자를 추천 합니다.</span><span class="sxs-lookup"><span data-stu-id="b080b-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

