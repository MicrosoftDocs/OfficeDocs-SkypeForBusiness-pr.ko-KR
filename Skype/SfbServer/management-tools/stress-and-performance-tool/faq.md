---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 FAQ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 비즈니스용 Skype 2015 스트레스 및 성능 도구는 FAQ(질문과 대답)를 제공합니다. 이 질문은 지원되는 도구 구성을 찾은 후 도구 문제를 해결하고 스트레스 및 성능 도구를 실행하면 표시될 수 있는 행동을 명확히 하는 데 유용합니다.
ms.openlocfilehash: 4c9a8acca21e4e4bb8f6b6e0a5ff1f68484e6b1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814968"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="d5377-103">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="d5377-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="d5377-104">비즈니스용 Skype 2015 스트레스 및 성능 도구는 FAQ(질문과 대답)를 제공합니다. 이 질문은 지원되는 도구 구성을 찾은 후 도구 문제를 해결하고 스트레스 및 성능 도구를 실행하면 표시될 수 있는 행동을 명확히 하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="d5377-105">이 FAQ에서는 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 가장 자주 묻는 질문에 대해 설명하며 문제 해결 및 도구 구성 선택에 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="d5377-106">프로덕션에서 LyncPerfTool.exe 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d5377-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="d5377-107">이는 **권장되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-107">This is **not** recommended.</span></span> <span data-ttu-id="d5377-108">이 도구는 프로덕션 서버 성능, 보안 및 최종 사용자 환경에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="d5377-109">사용자를 처음으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="d5377-110">서버가 높은 부하를 실행하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d5377-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="d5377-111">사용자가 처음 로그온할 때 백그라운드에서 추가 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="d5377-112">따라서 백 엔드 서버의 Microsoft SQL Server 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="d5377-113">모든 사용자에 대해 로그온하는 짧은 테스트를 실행한 다음 도구를 사용하여 결과를 측정하기 전에 클라이언트를 다시 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="d5377-114">비즈니스용 Skype 서버는 초당 12개 이상의 동시 사용자 로그온 세션을 지원하지 않지만 서버에서 처리할 수 있는 실제 수는 하드웨어 구성에 따라 달라지며 지원되는 값보다 낮을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="d5377-115">클라이언트의 메모리가 부족합니다!</span><span class="sxs-lookup"><span data-stu-id="d5377-115">My clients are running out of memory!</span></span> <span data-ttu-id="d5377-116">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d5377-116">What should I do?</span></span>

<span data-ttu-id="d5377-117">클라이언트의 메모리가 부족한 경우 비즈니스용 Skype 서버 프런트 엔드 풀당 로그온한 사용자 수를 줄여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="d5377-118">문제가 지속되는 경우 프런트 엔드 풀을 수 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="d5377-119">비즈니스용 Skype 서버에서 이 도구를 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d5377-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="d5377-120">이 작업을 하지 말아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-120">You shouldn't do that.</span></span> <span data-ttu-id="d5377-121">이 시나리오는 이진 불일치로 인해 실패할 수 있으며 서버에서 리소스 소비를 측정하는 것이 목표이기 때문에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="d5377-122">실제로 이 도구를 실행하면 서버 성능에 영향을 미치고 데이터와 측정값이 무효화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="d5377-123">가상 서버 또는 LyncPerfTool.exe 또는 Microsoft Hyper-V Server 2008/2012에서 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d5377-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="d5377-124">네 당신은 할 수 있어요.</span><span class="sxs-lookup"><span data-stu-id="d5377-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="d5377-125">MPOP는 무엇을 의미하나요?</span><span class="sxs-lookup"><span data-stu-id="d5377-125">What does MPOP mean?</span></span>

<span data-ttu-id="d5377-126">MPOP는 "여러 현재 상태 지점"을 짧게 말한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="d5377-127">MPOP는 사용자가 여러 컴퓨터 또는 장치에서 비즈니스용 Skype 2015 클라이언트에 로그온하는 시나리오를 시뮬레이트하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="d5377-128">각 끝점은 LyncPerfTool.exe 프로필을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="d5377-129">즉, 프로필이 두 개의 현재 상태 지점으로 분할되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="d5377-130">I started LyncPerfTool.exe but nothing is happening.</span><span class="sxs-lookup"><span data-stu-id="d5377-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="d5377-131">무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="d5377-131">What's going on?</span></span>

<span data-ttu-id="d5377-132">서버에서 총 활성 끝점 카운터를 확인하여 사용자가 연결하고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="d5377-133">사용자가 연결되지 않는 경우 비즈니스용 Skype 서버 2015 구성을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="d5377-134">일반적으로 발생하는 문제는 서버 이름, 사용자 prefix 또는 암호 중 하나에 잘못된 것이기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="d5377-135">외부 클라이언트는 액세스 프록시 및 TargetServer 값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="d5377-136">구성 파일의 포트 번호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="d5377-137">어떤 것이 측정되고 있는지 어떻게 확신할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d5377-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="d5377-138">사용자가 작업을 연결하고 수행하고 있는지 여부를 나타내는 LyncPerfTool 성능 카운터가 있지만 작업을 측정하는 가장 쉬운 방법은 비즈니스용 Skype 2015 클라이언트를 사용하여 계정 중 하나에 로그온한 후 직접 해당 작업을 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="d5377-139">결과를 확인하여 측정이 수행된 것이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="d5377-140">Lync Server 2010 용량 계획 도구 및/또는 Lync Server 2013 용량 계획 도구가 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="d5377-141">괜찮습니까?</span><span class="sxs-lookup"><span data-stu-id="d5377-141">Is that okay?</span></span>

 <span data-ttu-id="d5377-142">이러한 도구에는 상호 관리 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-142">These tools have interoperability issues!</span></span> <span data-ttu-id="d5377-143">이러한 도구의 이전 버전을 모두 제거하여 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에서 유효한 데이터를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="d5377-144">스트레스 및 성능 도구에서 CAA 통화 정보 서버 토폴로지가 설정되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="d5377-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="d5377-145">아니요. 도구는 이 작업을 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-145">No, the tools won't do this.</span></span> <span data-ttu-id="d5377-146">이 도구는 사용자 부하를 시뮬레이트하기 위해 사용자, 연락처 및 메일 목록만 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="d5377-147">도구에서 지원하는 최대 사용자 수는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="d5377-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="d5377-148">테스트에서는 총 80,000명까지 사용자를 만들며 총 30,000명에 달하는 테스트를 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="d5377-149">기술 제한에 따라 더 높은 값을 허용할 수 있는 사용자 수가 최대 120,000명인 것이 120,000명입니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="d5377-150">이러한 값은 환경의 서버 및 하드웨어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d5377-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

