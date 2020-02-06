---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 질문과 대답
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: 비즈니스용 Skype 2015 스트레스 및 성능 도구 자주 묻는 질문 (FAQ), 지원 되는 도구 구성, 문제 해결 도구 문제, 스트레스 및 성능 도구를 실행할 때 표시 될 수 있는 상세한 behaviours에 대해 알아보기 .
ms.openlocfilehash: 2847ecd54389f64d6961cc72ecb94d87e847b0b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816187"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="69b68-103">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="69b68-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="69b68-104">비즈니스용 Skype 2015 스트레스 및 성능 도구 자주 묻는 질문 (FAQ), 지원 되는 도구 구성, 문제 해결 도구 문제, 스트레스 및 성능 도구를 실행할 때 표시 될 수 있는 상세한 behaviours에 대해 알아보기 .</span><span class="sxs-lookup"><span data-stu-id="69b68-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="69b68-105">이 FAQ는 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대해 자주 묻는 질문 중 몇 가지를 다루며 문제 해결 및 도구 구성 선택에 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="69b68-106">실제 환경에서 L Cperftool을 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="69b68-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="69b68-107">이 방법은 권장 **되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-107">This is **not** recommended.</span></span> <span data-ttu-id="69b68-108">이 도구는 프로덕션 서버 성능, 보안 및 최종 사용자 환경에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="69b68-109">사용자를 처음으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="69b68-110">서버가 높은 부하를 실행 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="69b68-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="69b68-111">사용자가 처음 로그온 할 때 백그라운드에서 추가 작업이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="69b68-112">결과적으로 Microsoft SQL Server 백 엔드 서버의 성능이 떨어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="69b68-113">모든 사용자에 게 기록 하는 짧은 테스트를 실행 한 다음 도구를 사용 하 여 결과 측정을 시작 하기 전에 클라이언트를 다시 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="69b68-114">비즈니스용 Skype 서버는 초당 12 대의 동시 사용자 로그온 세션을 지원 하지 않지만, 서버에서 처리할 수 있는 실제 숫자는 하드웨어 구성에 따라 다르며 지원 되는 값 보다 낮을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="69b68-115">내 클라이언트의 메모리가 부족 합니다!</span><span class="sxs-lookup"><span data-stu-id="69b68-115">My clients are running out of memory!</span></span> <span data-ttu-id="69b68-116">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="69b68-116">What should I do?</span></span>

<span data-ttu-id="69b68-117">클라이언트의 메모리가 부족 한 경우 비즈니스용 Skype Server 프런트 엔드 풀에 로그온 한 사용자 수를 줄여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="69b68-118">문제가 지속 되는 경우 프런트 엔드 풀을 확장 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="69b68-119">비즈니스용 Skype 서버에서이 도구를 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="69b68-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="69b68-120">이 작업을 수행 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="69b68-120">You shouldn't do that.</span></span> <span data-ttu-id="69b68-121">이 시나리오는 이진 불일치로 인해 실패할 수 있고 서버에서 리소스 소모를 측정 하는 것이 목표 때문에 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="69b68-122">실제로이 도구를 실행 하면 서버 성능에 영향을 줄 수 있고 데이터와 측정법을 무효화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="69b68-123">가상 서버나 Microsoft Hyper-v Server 2008/2012에서 L<c13> Cperftool을 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="69b68-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="69b68-124">네 당신은 할 수 있어요.</span><span class="sxs-lookup"><span data-stu-id="69b68-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="69b68-125">MPOP 무엇을 의미 하나요?</span><span class="sxs-lookup"><span data-stu-id="69b68-125">What does MPOP mean?</span></span>

<span data-ttu-id="69b68-126">MPOP "여러 지점을 표시" 하는 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="69b68-127">MPOP는 사용자가 여러 컴퓨터 또는 장치에서 비즈니스용 Skype 2015 클라이언트에 로그온 하는 시나리오를 시뮬레이트하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="69b68-128">모든 끝점에서 기본 프로필을 사용 하는 L<c13> Cperftool.</span><span class="sxs-lookup"><span data-stu-id="69b68-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="69b68-129">즉, 프로필이 두 지점 사이에 분할 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="69b68-130">죄송 합니다. exe를 시작 했지만 아무런 변화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="69b68-131">무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="69b68-131">What's going on?</span></span>

<span data-ttu-id="69b68-132">사용자가 연결 되어 있는지 확인 하려면 서버의 총 활성 끝점 카운터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="69b68-133">사용자가 연결 되지 않은 경우 비즈니스용 Skype Server 2015 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="69b68-134">일반적으로 표시 되는 문제는 서버 이름, 사용자 접두사 또는 암호 중 하나가 올바르지 않기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="69b68-135">외부 클라이언트에서 액세스 프록시와 TargetServer 값을 지정 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="69b68-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="69b68-136">구성 파일의 포트 번호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="69b68-137">무엇을 측정 하 고 있는지 확인 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="69b68-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="69b68-138">사용자가 연결 하 고 작업을 수행 하 고 있는지 여부를 나타내는 L의사 Cperftool 성능 카운터가 있지만 작업이 측정 되는 가장 쉬운 방법은 비즈니스용 Skype 2015 클라이언트를 사용 하 여 계정 중 하나에 로그온 하 여 수행 하는 것입니다. 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="69b68-139">측정을 확인 하기 위해 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="69b68-140">Lync Server 2010 용량 계획 도구 및/또는 Lync Server 2013 용량 계획 도구가 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="69b68-141">그 게 괜 찮 나요?</span><span class="sxs-lookup"><span data-stu-id="69b68-141">Is that okay?</span></span>

 <span data-ttu-id="69b68-142">이러한 도구에는 상호 운용성 문제가 있습니다!</span><span class="sxs-lookup"><span data-stu-id="69b68-142">These tools have interoperability issues!</span></span> <span data-ttu-id="69b68-143">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에서 유효한 데이터를 얻으려면 이전 버전의이 도구를 모두 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="69b68-144">스트레스 및 성능 도구가 CAA Call 정보 서버 토폴로지를 설정 하나요?</span><span class="sxs-lookup"><span data-stu-id="69b68-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="69b68-145">아니요, 도구가이 작업을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-145">No, the tools won't do this.</span></span> <span data-ttu-id="69b68-146">이 도구는 사용자 부하를 시뮬레이트하기 위해 사용자, 연락처 및 메일 목록만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="69b68-147">도구가 지 원하는 최대 사용자 수는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="69b68-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="69b68-148">테스트를 통해 총 8만 명의 사용자를 만들고,이 도구를 실행 하는 전체 3만 사용자 테스트를 실행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="69b68-149">기술적 제한 때문에 더 높은 값을 사용할 수 있지만 최대 12만 명의 사용자를 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="69b68-150">이러한 값은 사용자 환경의 서버와 하드웨어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="69b68-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

