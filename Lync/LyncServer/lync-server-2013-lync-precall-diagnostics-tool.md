---
title: 'Lync Server 2013: Lync PreCall Diagnostics 도구'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19051eb183dc12f091de0d90ebb707bc6cee8fc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525155"
---
# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="b8548-102">Lync Server 2013의 lync PreCall 진단 도구</span><span class="sxs-lookup"><span data-stu-id="b8548-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8548-103">_**마지막으로 수정 된 항목:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="b8548-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="b8548-104">.PCD (Lync PreCall Diagnostics Tool)는 네트워크의 현재 상태가 예정 된 Enterprise Voice 통화에서 오디오 품질에 어떤 영향을 줄 수 있는지 확인할 수 있도록 하는 클라이언트 기반 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="b8548-105">.PCD는 네트워크의 마지막 홉이 가장 취약 한 상황 (예: 공용 WiFi 네트워크 또는 가정 사용자에 대 한 랩톱) 일 때 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="b8548-106">.PCD는 네트워크의 마지막 다리를 통과 하는 작은 패킷 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="b8548-107">그런 다음이 도구는 패킷 스트림을 분석 하 여이 레그에 따른 지터 및 손실이 통화 품질에 영향을 줄 수 있는 방식을 예측 하 고 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="b8548-108">호출이 발생 하는 동안에도 클라이언트에서 .PCD를 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="b8548-109">패킷 스트림은 대역폭에 큰 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="b8548-110">**.PCD 버전 1.1의 최신 릴리스에는 다음과 같은 향상 된 기능이 포함 되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b8548-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="b8548-111">더 긴 암호 지원 (이제 최대 127 자까지 가능)</span><span class="sxs-lookup"><span data-stu-id="b8548-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="b8548-112">인증 로그인 문제에 대 한 추가 진단</span><span class="sxs-lookup"><span data-stu-id="b8548-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="b8548-113">Lync 하이브리드 배포에 대 한 향상 된 지원</span><span class="sxs-lookup"><span data-stu-id="b8548-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="b8548-114">자격 증명 선택에 대 한 업데이트</span><span class="sxs-lookup"><span data-stu-id="b8548-114">Updates to credential picker</span></span>

  - <span data-ttu-id="b8548-115">향상 된 안정성</span><span class="sxs-lookup"><span data-stu-id="b8548-115">Stability improvements</span></span>

<span data-ttu-id="b8548-116">의견을 보내주셔서 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-116">We appreciate any feedback.</span></span> <span data-ttu-id="b8548-117">모든 지원 질문이 나 문제를의 [.Pcd 피드백](mailto:pcdfb@microsoft.com) 별칭으로 보내 주시기 바랍니다 <pcdfb@microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="b8548-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="b8548-118">이 항목에는 다음 섹션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="b8548-119">Lync .PCD 버전</span><span class="sxs-lookup"><span data-stu-id="b8548-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="b8548-120">Lync .PCD 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8548-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="b8548-121">Lync .PCD 기능</span><span class="sxs-lookup"><span data-stu-id="b8548-121">Lync PCD Features</span></span>

  - <span data-ttu-id="b8548-122">Lync .PCD 실행</span><span class="sxs-lookup"><span data-stu-id="b8548-122">Running Lync PCD</span></span>

  - <span data-ttu-id="b8548-123">Lync .PCD 제거</span><span class="sxs-lookup"><span data-stu-id="b8548-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="b8548-124">Lync .PCD 버전</span><span class="sxs-lookup"><span data-stu-id="b8548-124">Lync PCD Versions</span></span>

<span data-ttu-id="b8548-125">이 항목에서는 무료 다운로드에 사용할 수 있는 도구의 다음 버전에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="b8548-126">Windows 데스크톱 앱 ( [https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914) )</span><span class="sxs-lookup"><span data-stu-id="b8548-126">Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="b8548-127">Lync .PCD 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8548-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8548-128">.PCD를 사용 하려면 Lync Server 배포에서 모바일 클라이언트를 지원 하기 위해 통합 커뮤니케이션 웹 API (c)를 설치 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="b8548-129">이 경우 Lync Server와 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="b8548-130">Windows 데스크톱 앱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8548-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="b8548-131">모든 버전의 Windows 7 또는 Windows 8 운영 체제</span><span class="sxs-lookup"><span data-stu-id="b8548-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="b8548-132">Microsoft .NET Framework 4.5는 다음 위치에서 제공 됩니다. [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="b8548-132">Microsoft .NET Framework 4.5 available at [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="b8548-133">Lync .PCD 기능</span><span class="sxs-lookup"><span data-stu-id="b8548-133">Lync PCD Features</span></span>

<span data-ttu-id="b8548-134">Lync .PCD에는 다음과 같은 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="b8548-135">필요할 때 기본값으로 실행 (2 분 버스트)</span><span class="sxs-lookup"><span data-stu-id="b8548-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="b8548-136">Always On에서 실행 (맞춰진 보기에서 최대 24 시간) 모드</span><span class="sxs-lookup"><span data-stu-id="b8548-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="b8548-137">테스트 실행의 기록 보기</span><span class="sxs-lookup"><span data-stu-id="b8548-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="b8548-138">로그인 실패 진단 (Windows 8 용 Lync .PCD)</span><span class="sxs-lookup"><span data-stu-id="b8548-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="b8548-139">![Lync .PCD features 로그인 진행 스크린샷](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync .PCD features 로그인 진행 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="b8548-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="b8548-140">네트워크 메트릭의 그래픽 보기-네트워크 MOS, 패킷 손실 및 인터 도착 지터 (전체 화면 및 맞춰진 보기)입니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="b8548-141">**전체 화면 보기**</span><span class="sxs-lookup"><span data-stu-id="b8548-141">**Full screen view**</span></span>

<span data-ttu-id="b8548-142">![PreCall 진단 도구 테스트 결과 그래프](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 진단 도구 테스트 결과 그래프")</span><span class="sxs-lookup"><span data-stu-id="b8548-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="b8548-143">**맞춰진 보기**</span><span class="sxs-lookup"><span data-stu-id="b8548-143">**Snapped view**</span></span>

<span data-ttu-id="b8548-144">![PreCall 진단 도구 사용률 테스트 결과](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 진단 도구 사용률 테스트 결과")</span><span class="sxs-lookup"><span data-stu-id="b8548-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="b8548-145">Lync .PCD 실행</span><span class="sxs-lookup"><span data-stu-id="b8548-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="b8548-146">Windows 데스크톱 앱 실행</span><span class="sxs-lookup"><span data-stu-id="b8548-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="b8548-147">Windows 7 시스템에서 .PCD을 시작 하려면 **시작** 메뉴에서 **PreCall 진단을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="b8548-148">Windows 8 시스템에서 .PCD을 시작 하려면 시작 화면에서 아이콘을 선택 하거나 "PreCall 진단"을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="b8548-149">![PreCall 진단 도구 아이콘](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 진단 도구 아이콘")</span><span class="sxs-lookup"><span data-stu-id="b8548-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="b8548-150">도구가 시작 되 면 기본 자격 증명을 제공 하는 방법을 선택 하 고 **PreCall 진단 도구 옵션** 대화 상자에서 네트워크 운영 모드를 선택한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="b8548-151">**테스트 시작** 단추를 선택 하 여 진단 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="b8548-152">**네트워크 자격 증명 사용** 옵션을 선택한 경우 테스트가 즉시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="b8548-153">**내 자격 증명 입력** 옵션을 선택한 경우 **Windows 보안** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="b8548-154">자격 증명을 입력 하면 테스트가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="b8548-155">Lync .PCD 제거</span><span class="sxs-lookup"><span data-stu-id="b8548-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="b8548-156">Lync .PCD을 제거 하려면 운영 체제에 대 한 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b8548-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="b8548-157">Windows 7 시스템에서 **제어판**을 열고 **프로그램 및 기능**을 선택한 다음 **Lync 2013 PreCall Diagnostics**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="b8548-158">Windows 8 시스템에서 .PCD 타일을 마우스 오른쪽 단추로 클릭 하 고 시작 화면 아래쪽의 앱 표시줄에서 **제거** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8548-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

