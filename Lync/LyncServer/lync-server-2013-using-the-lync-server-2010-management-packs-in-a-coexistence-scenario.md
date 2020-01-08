---
title: 공존 시나리오에서 Lync Server 2010 관리 팩 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="1a1af-102">공존 시나리오에서 Lync Server 2010 관리 팩 사용</span><span class="sxs-lookup"><span data-stu-id="1a1af-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a1af-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1a1af-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1a1af-104">대부분의 고객은 사용자가 Microsoft Lync Server 2010에서 Lync Server 2013로 점진적으로 마이그레이션되는 기업 내에 출시 프로그램을 채택 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="1a1af-105">이러한 회사의 관리자는 모든 최종 사용자가 최상의 통신 환경을 제공 하도록 하기 위해 두 버전의 Lync Server를 모니터링 하는 데 신경을 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="1a1af-106">이 시나리오에서는 Lync Server 2013 관리 팩이 Lync Server 2010 관리 팩과 함께 나란히 마이그레이션 경로를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="1a1af-107">Lync Server 2010에서 중앙 관리 저장소와 함께 저장 된 토폴로지 문서를 통해 Lync Server 컴퓨터를 검색 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="1a1af-108">이 구성에서 단일 컴퓨터는 다른 모든 Lync Server 컴퓨터의 존재를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="1a1af-109">Lync Server 2013의 관리 팩은 이제 Lync Server 2010에서 사용 된 중앙 검색 메커니즘 대신 컴퓨터 수준 검색을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="1a1af-110">즉, 각 System Center 에이전트는 본질적으로 자체를 검색 하 고 System Center Operations Manager에 대 한 존재를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="1a1af-111">컴퓨터 수준 검색을 사용 하 여 시스템 센터 인프라의 관리를 간소화 하 고 lync server 관리 팩 (예: lync server 2010 및 Lync Server 2013 관리 팩 용 관리 팩)을 사용 하도록 설정 합니다. 더 쉽게 공존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="1a1af-112">이 마이그레이션을 지원 하려면 먼저 기존 Lync Server 2010 모니터링을 업그레이드 하 여 범위 간격을 방지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="1a1af-113">이렇게 하려면 중앙 관리 저장소를 Lync Server 2013로 업그레이드 하기 전에 Lync server 2010에 대 한 중앙 검색 스크립트를 서비스 하기 위해 기존 Lync Server 2010 컴퓨터를 먼저 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="1a1af-114">4 단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="1a1af-115">Lync Server 2010 관리 팩을 누적 업데이트 7로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="1a1af-116">중앙 검색 스크립트를 실행 하도록 Lync Server 2010 컴퓨터에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="1a1af-117">Microsoft Lync Server 2010 관리 팩의 중앙 검색 후보를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="1a1af-118">새로운 중앙 검색 후보가 검색 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="1a1af-119">Lync Server 2010 컴퓨터에 중앙 검색 스크립트를 실행 하도록 지시</span><span class="sxs-lookup"><span data-stu-id="1a1af-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="1a1af-120">중앙 검색을 처리 하기 위해 중앙 집중화 되지 않은 관리 저장소 컴퓨터 (예: Lync Server 프런트 엔드) 서버를 지명할 중앙 집중화 되지 않은 관리 저장소 서버에 다음 레지스트리 키를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="1a1af-121">HKLM\\소프트웨어\\Microsoft\\실시간 통신\\상태\\CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="1a1af-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="1a1af-122">다음 절차를 완료 하 여이 레지스트리 키를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="1a1af-123">**시작** 을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="1a1af-124">**실행** 대화 상자에서 **regedit** 를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="1a1af-125">레지스트리 편집기에서 **\_HKEY LOCAL\_MACHINE**을 확장 하 고 **소프트웨어**를 확장 한 다음 **Microsoft**를 확장 하 고 **실시간 통신**을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="1a1af-126">**상태**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 클릭 한 다음 **키**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="1a1af-127">**상태** 키가 없는 경우 **실시간 통신**을 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **키**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="1a1af-128">새 키가 만들어지면 체력을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="1a1af-129">새 키를 만든 후 **CentralDiscoveryCandidate** 를 입력 하 고 enter 키를 눌러 키의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="1a1af-130">이 변경 사항을 적용 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="1a1af-131">변경 내용이 즉시 적용 되도록 하려면 상태 에이전트 서비스를 중지 한 다음 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="1a1af-132">상태 에이전트 서비스를 다시 시작 하려면 Lync Server 2010 컴퓨터에서 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="1a1af-133">**시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **보조 프로그램**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="1a1af-134">콘솔 창에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="1a1af-135">"System Center 관리 서비스를 중지 하 고 있습니다" 라는 메시지가 표시 되 고 그 뒤에 서비스가 중지 되었음을 알려 주는 두 번째 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="1a1af-136">서비스가 중단 되 면 다음 명령을 입력 하 고 ENTER 키를 눌러 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="1a1af-137">Lync Server 2010 관리 팩의 중앙 검색 후보 재정의</span><span class="sxs-lookup"><span data-stu-id="1a1af-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="1a1af-138">Lync server 2010 컴퓨터에서 Lync Server 2010 컴퓨터를 보고 하도록 설정한 후에는 Lync Server 2010 관리 팩에이 변경 사항에 대 한 정보를 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="1a1af-139">이렇게 하려면 관리 팩에서 재정의를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="1a1af-140">다음 절차를 완료 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="1a1af-141">Operations Manager 콘솔에서 **작성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="1a1af-142">제작 탭에서 **관리 팩 개체**를 확장 하 고 **개체**검색을 클릭 한 다음 **범위**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="1a1af-143">**범위 관리 팩 개체** 대화 상자에서 대상 **LS 검색 후보가** 있는 항목을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="1a1af-144">LS 검색 후보는 Lync Server 2010 관리 팩을 설치한 경우에만 표시 됨을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a1af-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="1a1af-145">Operations Manager 콘솔에서 **Ls 검색 후보**를 마우스 오른쪽 단추로 클릭 하 고 **재정의**를 가리킨 다음 **개체 검색 재정의**를 가리킨 다음 **Class: LS 검색 후보의 모든 개체를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="1a1af-146">**속성 재정의** 대화 상자에서 매개 변수 **중앙 검색 WatcherNode Fqdn**옆에 있는 **재정의** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="1a1af-147">값 및 **유효 값** **다시 정의** 상자에 Lync Server 2010 컴퓨터의 정규화 된 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="1a1af-148">**적용** 확인란을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="1a1af-149">재정의를 만든 후 루트 관리 서버에서 상태 서비스를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="1a1af-150">상태 서비스를 다시 시작 하려면 루트 관리 서버에서 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="1a1af-151">**시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **보조 프로그램**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="1a1af-152">콘솔 창에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="1a1af-153">"System Center 관리 서비스를 중지 하 고 있습니다" 라는 메시지가 표시 되 고 서비스가 중지 되었음을 알리는 두 번째 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="1a1af-154">서비스가 중단 되 면 다음 명령을 입력 하 고 ENTER 키를 눌러 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="1a1af-155">새 중앙 검색 후보가 검색 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="1a1af-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="1a1af-156">중앙 관리 저장소를 업그레이드 하기 전의 마지막 단계는 Lync Server 2010 관리 팩에서 새 중앙 검색 후보가 검색 되었는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="1a1af-157">이렇게 하려면 Operations Manager 콘솔을 열고 모니터링을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="1a1af-158">모니터링 탭에서 **Microsoft Lync Server 2010 상태**를 확장 하 고 **토폴로지 검색**을 확장 한 다음 **검색 상태 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="1a1af-159">표시의 행에 중앙 검색 후보의 정규화 된 도메인 이름이 나열 되는 **경로가** 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="1a1af-160">또한 컴퓨터 상태가 **정상**으로 보고 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1af-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

