---
title: 공존 시나리오에서 Lync Server 2010 관리 팩 사용
description: 공존 시나리오에서 Lync Server 2010 관리 팩 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f6e76f49b74badd0f40d115101abb38aa35172
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556074"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="cc9c3-103">공존 시나리오에서 Lync Server 2010 관리 팩 사용</span><span class="sxs-lookup"><span data-stu-id="cc9c3-103">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc9c3-104">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="cc9c3-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="cc9c3-105">대부분의 고객은 사용자가 Microsoft Lync Server 2010에서 Lync Server 2013로 점진적으로 마이그레이션되는 기업 내부에 롤아웃 프로그램을 채택 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-105">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="cc9c3-106">이러한 회사의 관리자는 두 버전의 Lync Server를 모니터링 하 여 모든 최종 사용자가 최상의 통신 환경을 얻을 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-106">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="cc9c3-107">이 시나리오의 경우 Lync Server 2013 관리 팩은 Lync Server 2010 관리 팩과 함께 병행 마이그레이션 경로를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-107">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="cc9c3-108">Lync Server 2010에서는 중앙 관리 저장소와 함께 저장 된 토폴로지 문서를 통해 Lync Server 컴퓨터를 검색 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-108">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="cc9c3-109">이 구성에서는 단일 컴퓨터에서 다른 모든 Lync Server 컴퓨터가 있는지 여부를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-109">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="cc9c3-110">Lync Server 2013의 관리 팩은 이제 Lync Server 2010에서 사용 된 중앙 검색 메커니즘 대신 컴퓨터 수준 검색을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-110">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="cc9c3-111">즉, 각 System Center 에이전트가 자신의 상태를 검색해서 이를 System Center Operations Manager에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-111">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="cc9c3-112">컴퓨터 수준 검색을 사용 하면 시스템 센터 인프라를 간편 하 게 관리할 수 있으며 lync server 관리 팩 (예: lync server 2010 및 Lync Server 2013 용 관리 팩)의 다양 한 버전을 보다 편리 하 게 사용 하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-112">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="cc9c3-113">이 마이그레이션을 지원 하려면 먼저 기존 Lync Server 2010 모니터링을 업그레이드 하 여 범위에 대 한 차이를 방지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-113">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="cc9c3-114">이렇게 하려면 중앙 관리 저장소를 Lync Server 2013로 업그레이드 하기 전에 Lync Server 2010에 대 한 중앙 검색 스크립트를 서비스 하기 위해 기존 Lync Server 2010 컴퓨터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-114">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="cc9c3-115">이 프로세스는 다음 4단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-115">This is a four-step process:</span></span>

1.  <span data-ttu-id="cc9c3-116">Lync Server 2010 관리 팩을 누적 업데이트 7로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-116">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="cc9c3-117">Lync Server 2010 컴퓨터에 중앙 검색 스크립트를 실행 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-117">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="cc9c3-118">Microsoft Lync Server 2010 관리 팩의 중앙 검색 후보를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-118">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="cc9c3-119">새 중앙 검색 후보가 검색되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-119">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="cc9c3-120">중앙 검색 스크립트를 실행할 Lync Server 2010 컴퓨터 지정</span><span class="sxs-lookup"><span data-stu-id="cc9c3-120">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="cc9c3-121">중앙 검색을 처리 하기 위해 중앙 집중식 관리 저장소 컴퓨터 (예: Lync Server 프런트 엔드) 서버를 위한 비 중앙 관리 저장소 서버에 다음과 같은 레지스트리 키를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-121">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="cc9c3-122">HKLM \\ Software \\ Microsoft \\ 실시간 통신 \\ 상태 \\ 만들어졌으면 centraldiscoverycandidate</span><span class="sxs-lookup"><span data-stu-id="cc9c3-122">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="cc9c3-123">이 레지스트리 키는 다음 절차에 따라 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-123">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="cc9c3-124">**시작**을 클릭한 다음 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-124">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="cc9c3-125">**실행** 대화 상자에 **regedit**를 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-125">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="cc9c3-126">레지스트리 편집기에서 **HKEY \_ 로컬 \_ 컴퓨터**를 확장 하 고 **소프트웨어**, **Microsoft**를 차례로 확장 한 다음 **실시간 통신**을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-126">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="cc9c3-p105">**Health**를 마우스 오른쪽 단추로 클릭하고, **새로 만들기**를 클릭한 후 **키**를 클릭합니다. **Health** 키가 없으면 **Real-Time Communications**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 후 **키**를 클릭합니다. 새 키가 만들어졌으면 Health를 입력한 후 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-p105">Right-click **Health**, click **New**, and then click **Key**. If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**. When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="cc9c3-130">새 키가 만들어졌으면 **CentralDiscoveryCandidate**를 입력한 후 Enter 키를 눌러서 키 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-130">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="cc9c3-131">컴퓨터에서 이 변경 내용을 선택하려면 몇 시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-131">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="cc9c3-132">변경 내용을 즉시 적용하려면 상태 에이전트 서비스를 중지한 후 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-132">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="cc9c3-133">상태 에이전트 서비스를 다시 시작 하려면 Lync Server 2010 컴퓨터에서 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-133">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="cc9c3-134">**시작**, **모든 프로그램**, **보조 프로그램**을 차례로 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-134">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="cc9c3-135">콘솔 창에 다음 명령을 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-135">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="cc9c3-p107">"System Center 관리 서비스를 중지하는 중입니다."라는 메시지가 표시되고 이후 서비스가 중지되었다는 메시지가 나타납니다. 서비스가 중지된 후 다음 명령을 입력하고 Enter 키를 눌러서 서비스를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-p107">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="cc9c3-138">Lync Server 2010 관리 팩의 중앙 검색 후보 재정의</span><span class="sxs-lookup"><span data-stu-id="cc9c3-138">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="cc9c3-139">Lync server 2010 컴퓨터에 Lync Server 2010 컴퓨터에 대 한 보고를 한 후에는이 변경 사항에 대 한 정보를 Lync Server 2010 관리 팩에도 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-139">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="cc9c3-140">이렇게 하려면 관리 팩에서 재정의를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-140">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="cc9c3-141">이 작업은 다음 절차에 따라 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-141">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="cc9c3-142">Operations Manager 콘솔에서 **제작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-142">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="cc9c3-143">제작 탭에서 **관리 팩 개체**를 확장하고, **개체 검색**을 클릭한 후 **범위**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-143">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="cc9c3-144">**관리 팩 개체 범위 지정** 대화 상자에서 대상 **LS 검색 후보**가 포함된 항목을 선택한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-144">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="cc9c3-145">LS 검색 후보는 Lync Server 2010 관리 팩을 설치한 경우에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-145">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="cc9c3-146">Operations Manager 콘솔에서 **LS 검색 후보**를 마우스 오른쪽 단추로 클릭하고 **재정의**, **개체 검색 재정의**를 가리킨 후 **클래스의 모든 개체: LS 검색 후보**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-146">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="cc9c3-147">**재정의 속성** 대화 상자에서 **중앙 검색 감시자 노드 FQDN** 매개 변수 옆에 있는 **재정의** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-147">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="cc9c3-148">**값 재정의** 및 **유효 값** 상자에 Lync Server 2010 컴퓨터의 정규화 된 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-148">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="cc9c3-149">**적용** 확인란을 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-149">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="cc9c3-p111">재정의를 만든 후에는 루트 관리 서버의 상태 서비스를 다시 시작해야 합니다. 상태 서비스를 다시 시작하려면 루트 관리 서버에서 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-p111">After you have created the override, you need to restart the health service on the Root Management Server. To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="cc9c3-152">**시작**, **모든 프로그램**, **보조 프로그램**을 차례로 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-152">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="cc9c3-153">콘솔 창에 다음 명령을 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-153">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="cc9c3-p112">"System Center 관리 서비스를 중지하는 중입니다."라는 메시지가 표시되고 이후 서비스가 중지되었다는 메시지가 나타납니다. 서비스가 중지된 후 다음 명령을 입력하고 Enter 키를 눌러서 서비스를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-p112">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="cc9c3-156">새 중앙 검색 후보가 검색되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="cc9c3-156">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="cc9c3-157">중앙 관리 저장소를 업그레이드 하기 전 마지막 단계는 새 중앙 검색 후보가 Lync Server 2010 관리 팩에서 검색 되었는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-157">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="cc9c3-158">이를 위해서는 Operations Manager 콘솔을 열고 모니터링을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-158">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="cc9c3-159">모니터링 탭에서 **Microsoft Lync Server 2010 Health**, **토폴로지 검색**을 확장한 후 **검색 상태 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-159">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="cc9c3-160">디스플레이의 행에 중앙 검색 후보의 FQDN(정규화된 도메인 이름)이 나열된 **경로**가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-160">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="cc9c3-161">또한 컴퓨터 상태가 **정상**으로 보고되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c3-161">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

