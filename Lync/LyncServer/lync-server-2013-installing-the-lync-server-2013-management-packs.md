---
title: 'Lync Server 2013: Lync Server 2013 관리 팩 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffc102eccdbaa941e2691df88899c0cc01348838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="5996f-102">Lync Server 2013 관리 팩 설치</span><span class="sxs-lookup"><span data-stu-id="5996f-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5996f-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5996f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5996f-104">System Center Operations Manager에는 Windows 운영 체제의 일부만 모니터링 하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="5996f-105">그러나 관리 팩을 설치 하 여 system center operations Manager에서 모니터링할 수 있는 항목을 지정 하는 소프트웨어, 해당 항목을 모니터링 하는 방법, 알림 메시지의 종류를 비롯 하 여 시스템 센터 Operations Manager의 기능을 확장할 수 있습니다. 트리거 및 보고 됨.</span><span class="sxs-lookup"><span data-stu-id="5996f-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="5996f-106">Microsoft Lync Server 2013에는 다음과 같은 기능을 제공 하는 두 가지 System Center Operations Manager 관리 팩이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="5996f-107">구성 요소 및 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp (사용자 관리 팩)는 이벤트 로그에 기록 된 Lync Server 문제 (성능 카운터에 의해 등록 됨) 또는 CDR (통화 정보 기록) 또는 체험 지 (체감 품질)를 추적 합니다. databases.</span><span class="sxs-lookup"><span data-stu-id="5996f-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="5996f-108">중요 한 문제가 발생 하는 경우 관리자에 게 전자 메일, 인스턴트 메시지 또는 SMS (짧은 메시지 서비스) 메시징을 통해 즉시 알리려면 System Center Operations Manager를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="5996f-109">SMS는 모바일 장치 간에 문자 메시지를 전송 하는 데 사용 되는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5996f-110">Operations Manager 알림을 구성 하는 방법에 대 한 자세한 내용은의 TechNet 라이브러리에서 알림 <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5996f-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="5996f-111">Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp (액티브 모니터링 팩)는 시스템에 로그인 하거나 인스턴트 메시지를 교환 하거나 공개 교환 전화에서 휴대폰으로 전화를 거는 등의 키 Lync Server 구성 요소를 사전에 테스트 합니다. 네트워크 (PSTN).</span><span class="sxs-lookup"><span data-stu-id="5996f-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="5996f-112">이러한 테스트는 Lync Server 가상 트랜잭션 cmdlet을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="5996f-113">예를 들어 **test-CsIM** cmdlet은 한 쌍의 테스트 사용자 간에 인스턴트 메시징 대화를 시뮬레이트하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="5996f-114">이 시뮬레이션 된 메시징 대화에 실패 하면 경고가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="5996f-115">Lync Server 2013에 포함 된 두 관리 팩에는 Microsoft Lync Server 2010에 사용 되는 관리 팩에 대 한 많은 향상 된 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="5996f-116">예를 들어 Lync Server 2013 구성 요소 관리 팩은 Lync Server 자체의 모니터링으로 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="5996f-117">구성 요소 관리 팩은 Lync Server에 대 한 이벤트 로그 및 성능 카운터를 모니터링 하는 것 외에도 다음과 같은 중요 한 항목에 대 한 경고의 성과를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="5996f-118">**인터넷 정보 서비스가 오프 라인일 경우 IIS (인터넷 정보 서비스)**   경고가 발행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="5996f-119">이는 Lync Server 웹 서비스가 IIS를 사용 하기 때문에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="5996f-120">\*\*\*\*   시스템 리소스 (사용 가능한 메모리 등)가 낮음으로 시작 되 면 프로세스 사용 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="5996f-121">이 경고는 Lync Server가 높은 시스템 사용량에 대해 책임을 지지 않은 경우에도 발급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="5996f-122">\*\*\*\*   서버의 실행 가능 여부를 threatens 하는 하드웨어 또는 소프트웨어 문제 시 컴퓨터 오류 이벤트 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="5996f-123">예를 들어 서버에 하드 디스크 오류가 발생 하는 경우 Lync 서버 관리자에 게 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="5996f-124">새로운 관리 팩에는 향상 된 보고 기능도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="5996f-125">Lync Server 2013의 새 보고서에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="5996f-126">**End to end 시나리오 가용성 보고서**   이 보고서에는 등록 또는 현재 상태와 같은 주요 Lync Server 서비스의 가용성/가동 시간이 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="5996f-127">**용량 보고서**   성능 카운터 정보를 사용 하 여이 보고서에는 메모리 가용성 및 프로세서 사용량 같은 시스템 구성 요소에 대 한 추세가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="5996f-128">**구성 요소 보고서**   이 보고서에는 Lync Server 구성 요소로 그룹화 된 최상위 알림 생성기가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="5996f-129">이러한 미리 디자인 된 보고서 외에도 Lync Server 2013의 관리 팩은 호출 안정성 (통화 정보 기록으로 측정 되는 메트릭) 및 체감 품질 states (환경에 따라 측정 되는 메트릭)에 대 한 알림을 자동으로 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="5996f-130">통화 정보 기록을 사용 하도록 설정한 경우 System Center Operations Manager 콘솔에서 다음 절차를 완료 하 여 호출 안정성 알림을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="5996f-131">**모니터링**을 확장 하 고 **Microsoft Lync Server 2013 상태**, **통화 안정성 및 미디어 품질**을 확장 한 다음, **통화 안정성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="5996f-132">경력 수준의 알림을 보려면 System Center Operations Manager 콘솔에서 다음 절차를 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="5996f-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="5996f-133">**모니터링**을 확장 하 고 **Microsoft Lync Server 2013 상태**를 확장 하 고, **통화 안정성 및 미디어 품질**을 확장 한 다음 **미디어 품질**을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="5996f-134">Lync Server 2013의 관리 팩은 이제 Microsoft Lync Server 2010에 사용 되는 중앙 검색 메커니즘 대신 컴퓨터 수준 검색을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="5996f-135">즉, 각 System Center agent가 자체적으로 자체 검색을 하 고 중앙 관리 서버에 해당 존재를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5996f-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="5996f-136">컴퓨터 수준 검색을 사용 하 여 시스템 센터 인프라의 관리를 간소화 하 고 lync server 관리 팩 (예: lync server 2010 및 Lync Server 2013 관리 팩 용 관리 팩)의 여러 버전을 사용할 수 있습니다. 배치.</span><span class="sxs-lookup"><span data-stu-id="5996f-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

