---
title: 서버 유지 관리를 위한 Lync Server의 새 연결 금지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3678414e45e556eb7092b923fab4b737bfd4842
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="e7659-102">서버 유지 관리를 위해 Lync Server 2013에 대 한 새 연결 차단</span><span class="sxs-lookup"><span data-stu-id="e7659-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7659-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e7659-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e7659-104">Lync Server를 사용 하면 사용자에 대 한 서비스 손실 없이도 서버를 오프 라인으로 설정 (예: 소프트웨어 또는 하드웨어 업그레이드 적용) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="e7659-105">풀의 서버에 대한 새 연결 또는 통화를 방지하기 위한 옵션을 지정하면 이 옵션을 구현하는 즉시 새 연결 및 호출 수행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-105">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="e7659-106">이러한 새 연결 및 통화는 풀의 다른 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-106">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="e7659-107">새 연결을 방지하는 서버는 기존 연결의 세션을 자연적으로 종료될 때까지 둡니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-107">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="e7659-108">모든 기존 세션이 종료되면 서버를 오프라인으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-108">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="e7659-109">프런트 엔드 서버에 대 한 새 연결을 차단 하면 일부 Lync Server 기능 및 서비스가 DNS 부하 분산을 사용 하 여 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="e7659-110">풀에서 DNS 부하 분산을 사용하지 않는 경우, 이러한 서비스를 통한 연결이 서버가 새 연결을 방지하는 기간 동안 다른 서버로 다시 라우팅되지 않아 서버가 오프라인으로 설정될 때 일부 세션 및 통화가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="e7659-111">이 옵션이 적절하게 작동하도록 하기 위해 DNS 부하 분산을 사용하는 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="e7659-112">교환</span><span class="sxs-lookup"><span data-stu-id="e7659-112">Attendant</span></span>

  - <span data-ttu-id="e7659-113">회의 알림 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e7659-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="e7659-114">응답 그룹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e7659-114">Response Group application</span></span>

  - <span data-ttu-id="e7659-115">Announcement application(알림 응용 프로그램)</span><span class="sxs-lookup"><span data-stu-id="e7659-115">Announcement application</span></span>

  - <span data-ttu-id="e7659-116">통화 대기 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e7659-116">Call Park application</span></span>

<span data-ttu-id="e7659-117">DNS 부하 분산에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 dns 부하 분산](lync-server-2013-dns-load-balancing.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7659-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="e7659-118">Lync Server를 실행 하는 서버의 모든 서비스에 대 한 새 연결을 차단 하는 것 외에, 개별 Lync Server 서비스에 대 한 새 연결을 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="e7659-119">예를 들어이 방법은 전체 서버를 종료할 필요가 없는 Lync Server 업데이트를 적용 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="e7659-120">특정 서비스에 대한 연결을 방지할 때는 Windows 서비스 목록에서 그룹화되어 표시되는 서비스를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="e7659-121">예를 들어, Lync Server 프런트 엔드 서비스와 모니터링에 대 한 데이터 수집 에이전트는 별도의 Lync Server 서비스 이지만 Windows 서비스 목록에서 통합 되어 Lync Server 프런트 엔드 서비스로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="e7659-122">Lync Server 프런트 엔드 서비스에 대 한 새 연결이 차단 되지만 이러한 두 가지 개별 Lync Server 서비스에 대 한 새 연결은 별도로 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e7659-p104">새 연결을 차단하도록 서버를 설정한 후에 서버를 다시 시작하면 기본적으로 서버가 시작된 직후 새 연결을 허용하기 시작합니다. 이러한 현상을 방지하려면 서버를 다시 시작하기 전에 서버를 수동으로만 일시 중지 및 다시 시작하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="e7659-125">Lync Server에 대 한 새 연결을 차단 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="e7659-126">Administrators 그룹의 구성원으로 로컬 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="e7659-127">**시작**을 클릭 하 고 **모든 프로그램**, **관리 도구**를 차례로 가리킨 다음 **서비스**를 클릭 하 여 서비스 스냅인 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="e7659-128">목록에서 새 연결을 금지할 Lync Server Windows 서비스를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="e7659-129">속성 대화 상자의 **서비스 상태: 시작 됨**에서 **일시 중지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="e7659-130">또는 **시작 유형**옆의 **수동**을 클릭 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="e7659-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e7659-p105">새 연결을 차단하도록 서버를 설정한 후에 서버를 다시 시작하면 기본적으로 서버가 시작된 직후 새 연결을 허용하기 시작합니다. 이러한 현상을 방지하려면 서버를 다시 시작하기 전에 서버를 수동으로만 일시 중지 및 다시 시작하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="e7659-133">작업이 끝나면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e7659-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

