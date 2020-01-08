---
title: 신뢰 된 서버 인증을 사용 하도록 감시자 노드 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="42c5e-102">신뢰할 수 있는 서버 인증을 사용 하도록 Lync Server 2013에서 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="42c5e-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42c5e-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="42c5e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="42c5e-104">감시자 노드 컴퓨터가 경계 네트워크 내에 있는 경우 신뢰할 수 있는 서버 인증을 사용 하면 수많은 사용자 계정 암호 보다는 단일 인증서를 유지 관리 하기 위해 관리자 세금이 대폭 감소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="42c5e-105">신뢰 된 서버 인증을 구성 하는 첫 번째 단계는 신뢰할 수 있는 응용 프로그램 풀을 만들어 감시자 노드 컴퓨터를 호스트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-105">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="42c5e-106">신뢰할 수 있는 응용 프로그램 풀을 만든 후에는 해당 감시자 노드에서 가상 트랜잭션을 구성 하 여 신뢰할 수 있는 응용 프로그램으로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-106">After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="42c5e-107">신뢰할 수 있는 응용 프로그램은 Lync Server 2013의 일부로 실행할 신뢰할 수 있는 상태를 지정 하는 응용 프로그램 이지만 제품의 기본 제공 부분이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="42c5e-108">신뢰할 수 있는 상태는 응용 프로그램이 실행 될 때마다 인증에 대해 challenge 되지 않는다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="42c5e-109">신뢰할 수 있는 응용 프로그램 풀을 만들려면 Lync Server 2013 관리 셸을 열고 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="42c5e-110">앞의 명령에 사용 되는 매개 변수에 대 한 자세한 내용은 Lync Server Management Shell 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="42c5e-111">Get-help 신규-CsTrustedApplicationPool-Full | 자세한</span><span class="sxs-lookup"><span data-stu-id="42c5e-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="42c5e-112">신뢰할 수 있는 응용 프로그램 풀을 만든 후에는 신뢰할 수 있는 응용 프로그램으로 가상 트랜잭션을 실행 하도록 감시자 노드 컴퓨터를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="42c5e-113">이 작업은 **CsTrustedApplication** cmdlet 및 다음과 유사한 명령을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="42c5e-114">앞의 명령이 완료 되 고 신뢰할 수 있는 응용 프로그램이 만들어졌으면 Enable-CsTopology를 실행 하 여 변경 내용이 적용 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="42c5e-115">Enable-CsTopology을 실행 한 후 컴퓨터를 다시 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="42c5e-116">신뢰할 수 있는 새 응용 프로그램이 만들어졌는지 확인 하려면 Lync Server 관리 셸 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="42c5e-117">감시자 노드에 대 한 기본 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="42c5e-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="42c5e-118">각 감시자 노드에는 Lync Server 배포 마법사를 사용 하 여 할당 된 기본 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="42c5e-119">**기본 인증서를 할당 하려면**</span><span class="sxs-lookup"><span data-stu-id="42c5e-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="42c5e-120">**시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **lync Server**를 클릭 하 고 **lync 서버 배포 마법사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="42c5e-121">Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트** 를 클릭 한 다음 제목 **요청, 설치 또는 인증서 지정**에서 **실행** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="42c5e-122"><STRONG>실행</STRONG> 단추를 사용할 수 없는 경우 먼저 <STRONG>로컬 구성 저장소 설치</STRONG>에서 <STRONG>실행</STRONG> 을 클릭 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="42c5e-123">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="42c5e-124">기본 인증서로 사용할 수 있는 인증서가 이미 있는 경우 인증서 마법사에서 **기본값** 을 클릭 한 다음 **할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-124">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**.</span></span> <span data-ttu-id="42c5e-125">인증서 할당 마법사의 단계에 따라 해당 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-125">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="42c5e-126">기본 인증서를 사용 하기 위해 인증서를 요청 해야 하는 경우 **요청** 을 클릭 한 다음 인증서 요청 마법사의 단계에 따라 해당 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-126">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="42c5e-127">웹 서버 인증서에 대 한 기본값을 사용 하는 경우에는 기본 인증서로 할당할 수 있는 인증서를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-127">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="42c5e-128">감시자 노드 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="42c5e-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="42c5e-129">감시자 노드 컴퓨터를 다시 시작 하 고 인증서를 구성한 후에는 Watchernode 파일을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="42c5e-130">(Operations Manager 에이전트 파일과 Lync Server 2013 core 구성 요소가 설치 되어 있는 컴퓨터에서 Watchernode을 실행 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="42c5e-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="42c5e-131">**감시자 노드를 설치 하 고 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="42c5e-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="42c5e-132">**시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 lync **Server**를 클릭 하 고 **lync Server Management Shell**을 클릭 하 여 lync server management shell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="42c5e-133">Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다 (Watchernode 복사본의 실제 경로 지정).</span><span class="sxs-lookup"><span data-stu-id="42c5e-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="42c5e-134">명령 창에서 Watchernode를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-134">You can also run Watchernode.msi from a command window.</span></span> <span data-ttu-id="42c5e-135">명령 창을 열려면 <STRONG>시작</STRONG>을 클릭 하 고 <STRONG>명령 프롬프트</STRONG>를 마우스 오른쪽 단추로 클릭 한 다음 <STRONG>관리자 권한으로 실행</STRONG>을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-135">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="42c5e-136">명령 창이 열리면 앞의 동일한 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-136">When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="42c5e-137">앞의 명령 인증 =로 서버에서 이름/값 쌍은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-137">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="42c5e-138">표시 된 대로 정확 하 게 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-138">You must type it exactly as shown.</span></span> <span data-ttu-id="42c5e-139">다음 명령은 올바른 문자 대/소문자를 사용 하지 않기 때문에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-139">The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="42c5e-140">C:\\도구\\Watchernode 인증 = (대상 서버)</span><span class="sxs-lookup"><span data-stu-id="42c5e-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="42c5e-141">외곽 네트워크 내에 있는 컴퓨터에만이 지 있는 서버 모드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-141">You can use TrustedServer mode only with computers that are located within the perimeter network.</span></span> <span data-ttu-id="42c5e-142">감시자 노드가 (가)로 서버 모드에서 실행 되는 경우 관리자는 컴퓨터에서 테스트 사용자 암호를 유지할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42c5e-142">When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

