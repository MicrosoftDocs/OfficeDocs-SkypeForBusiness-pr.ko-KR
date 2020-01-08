---
title: Lync Server 2013 스트레스 및 성능 도구 FAQ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="f270a-102">Lync Server 2013 스트레스 및 성능 도구 FAQ</span><span class="sxs-lookup"><span data-stu-id="f270a-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f270a-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="f270a-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f270a-104">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="f270a-104">Frequently Asked Questions</span></span>

<span data-ttu-id="f270a-105">Lync Server 2013 스트레스 및 성능 도구에 대 한 몇 가지 질문과 대답이 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="f270a-106">실제 환경에서 L Cperftool을 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="f270a-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="f270a-107">이 방법은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-107">We do not recommend this.</span></span> <span data-ttu-id="f270a-108">이 도구는 서버 성능, 보안 및 사용자 환경에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="f270a-109">처음으로 사용자를 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="f270a-110">이러한 로드가 높을 때 서버가 실행 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f270a-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="f270a-111">사용자가 처음 로그온 할 때 발생 하는 추가 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="f270a-112">결과적으로 Microsoft SQL Server 백 엔드 서버의 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="f270a-113">모든 사용자에 게 기록 하는 짧은 테스트를 실행 한 다음 결과를 측정 하기 전에 클라이언트를 다시 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="f270a-114">초당 최대 12 개의 동시 사용자 로그온 세션을 지원 하지는 않지만 하드웨어 구성에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="f270a-115">클라이언트의 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-115">My clients are running out of memory.</span></span> <span data-ttu-id="f270a-116">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="f270a-116">What should I do?</span></span>

<span data-ttu-id="f270a-117">클라이언트의 메모리가 부족 한 경우 컴퓨터 당 사용자 수를 줄여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="f270a-118">클라이언트가 항상 100%의 CPU에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="f270a-119">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="f270a-119">What should I do?</span></span>

<span data-ttu-id="f270a-120">모든 사용자가 로그온 한 후에 클라이언트가 매우 높은 CPU로 실행 되는 경우 컴퓨터 당 사용자 수를 줄여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="f270a-121">높은 CPU 스파이크는 허용 되지만, 유지 되는 경우 부하를 줄여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="f270a-122">서버 자체에서 도구를 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="f270a-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="f270a-123">아니요.</span><span class="sxs-lookup"><span data-stu-id="f270a-123">No.</span></span> <span data-ttu-id="f270a-124">이 시나리오는 지원 되지 않으며 이진 불일치로 인해 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="f270a-125">또한 서버에서 리소스 소모를 측정 하는 것이 점에서 도구를 실행 하는 것 이기 때문에 측정값을 의미 없는 값으로 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="f270a-126">가상 서버나 Microsoft Hyper-v Server 2008/2012에서 L<c13> Cperftool을 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="f270a-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="f270a-127">예.</span><span class="sxs-lookup"><span data-stu-id="f270a-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="f270a-128">MPOP 무엇을 의미 하나요?</span><span class="sxs-lookup"><span data-stu-id="f270a-128">What does MPOP mean?</span></span>

<span data-ttu-id="f270a-129">MPOP는 여러 개의 현재 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="f270a-130">이는 사용자가 여러 컴퓨터에서 Lync 2013에 로그온 하는 시나리오를 시뮬레이트하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="f270a-131">L<c13> Cperftool .exe에서는 각 끝점이 기본 프로필을 사용 합니다 (즉, 프로필이 두 지점 사이에 분할 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="f270a-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="f270a-132">죄송 합니다. exe를 시작 했지만 아무런 변화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="f270a-133">무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="f270a-133">What’s going on?</span></span>

<span data-ttu-id="f270a-134">사용자가 연결 되어 있는지 확인 하려면 클라이언트의 총 활성 끝점 카운터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="f270a-135">사용자가 연결 되지 않은 경우에는 Lync Server 2013 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="f270a-136">일반적으로이 문제는 서버 이름, 사용자 접두사 또는 암호가 올바르지 않기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="f270a-137">외부 클라이언트에서 액세스 프록시를 TargetServer 값으로 지정 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f270a-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="f270a-138">구성 파일의 포트를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="f270a-139">무슨 일이 발생 하 고 있는지 어떻게 알 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="f270a-139">How do I know something is happening?</span></span>

<span data-ttu-id="f270a-140">다양 한 L<c13> Cperftool 성능 카운터는 사용자가 연결 하 고 작업을 수행 하 고 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="f270a-141">그러나 쉽게 확인할 수 있는 방법은 Lync 2013를 사용 하 여 계정 중 하나에 로그온 하 고 원하는 작업을 수행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="f270a-142">Live Communications Server 2007 R2 용량 계획 도구 및/또는 Lync Server 2010이 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="f270a-143">이 게 정상 인가요?</span><span class="sxs-lookup"><span data-stu-id="f270a-143">Is that OK?</span></span>

<span data-ttu-id="f270a-144">아니요.</span><span class="sxs-lookup"><span data-stu-id="f270a-144">No.</span></span> <span data-ttu-id="f270a-145">상호 운용성 문제가 있으므로이 제품의 모든 이전 버전을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="f270a-146">스트레스 및 성능 도구가 CAA Call 정보 서버 토폴로지를 설정 하나요?</span><span class="sxs-lookup"><span data-stu-id="f270a-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="f270a-147">아니요.</span><span class="sxs-lookup"><span data-stu-id="f270a-147">No.</span></span> <span data-ttu-id="f270a-148">이 도구는 사용자, 연락처 및 메일 그룹을 만들고 사용자 부하를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="f270a-149">도구가 지 원하는 최대 사용자 수는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f270a-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="f270a-150">이 도구를 사용 하 여 총 8만 명의 사용자를 만들고 3만 테스트를 실행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="f270a-151">사용 가능한 클라이언트 및 서버 하드웨어에 따라 기술적 제한으로 더 높은 값이 허용 되지만, 최대 12만 명의 사용자를 추천 합니다.</span><span class="sxs-lookup"><span data-stu-id="f270a-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

