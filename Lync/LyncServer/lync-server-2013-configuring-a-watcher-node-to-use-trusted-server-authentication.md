---
title: 신뢰할 수 있는 서버 인증을 사용 하도록 감시자 노드 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8272dc0097205749ca3c0e5d613bc3da853fc7ea
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="4bcde-102">신뢰할 수 있는 서버 인증을 사용 하도록 Lync Server 2013에서 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="4bcde-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bcde-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4bcde-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4bcde-104">감시자 노드 컴퓨터가 경계 네트워크 내에 있을 경우 신뢰할 수 있는 서버 인증을 사용하면 여러 사용자 계정 암호 대신 단일 인증서를 유지 관리하여 관리 부담을 크게 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="4bcde-p101">신뢰할 수 있는 서버 인증 구성의 첫 번째 단계는 감시자 노드 컴퓨터를 호스팅하기 위한 신뢰할 수 있는 응용 프로그램 풀을 만드는 것입니다. 신뢰할 수 있는 응용 프로그램 풀을 만든 후에는 해당 감시자 노드의 가상 트랜잭션이 신뢰할 수 있는 응용 프로그램으로 실행되도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-p101">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer. After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4bcde-107">신뢰할 수 있는 응용 프로그램 이란 Lync Server 2013의 일부로 실행할 신뢰할 수 있는 상태를 제공 하지만 제품의 기본 제공 부분은 아닌 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="4bcde-108">신뢰 상태란 응용 프로그램이 실행될 때마다 응용 프로그램에 인증을 요청하지 않는 상태를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="4bcde-109">신뢰할 수 있는 응용 프로그램 풀을 만들려면 Lync Server 2013 관리 셸을 열고 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="4bcde-110">앞의 명령에 사용 된 매개 변수에 대 한 자세한 내용을 보려면 Lync Server 관리 셸 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="4bcde-111">Get-Help New-CsTrustedApplicationPool -Full | more</span><span class="sxs-lookup"><span data-stu-id="4bcde-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="4bcde-112">신뢰할 수 있는 응용 프로그램 풀을 만든 후에는 가상 트랜잭션을 신뢰할 수 있는 응용 프로그램으로 실행하도록 감시자 노드 컴퓨터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="4bcde-113">이 작업은 **New-CsTrustedApplication** cmdlet 및 다음과 비슷한 명령을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="4bcde-114">앞의 명령이 완료되고 신뢰할 수 있는 응용 프로그램이 만들어지면 Enable-CsTopology를 실행하여 변경 내용이 적용되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="4bcde-115">Enable-CsTopology를 실행한 후에는 컴퓨터를 다시 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="4bcde-116">신뢰할 수 있는 새 응용 프로그램이 만들어졌는지 확인 하려면 Lync Server 관리 셸 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="4bcde-117">감시자 노드에서 기본 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="4bcde-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="4bcde-118">각 감시자 노드에는 Lync Server 배포 마법사를 사용 하 여 할당 된 기본 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="4bcde-119">**기본 인증서를 지정하려면**</span><span class="sxs-lookup"><span data-stu-id="4bcde-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="4bcde-120">**시작**, **모든 프로그램**, **lync server**를 차례로 클릭 한 다음 **lync server 배포 마법사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="4bcde-121">Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트** 를 클릭 한 다음 제목 **요청, 설치 또는 할당**에서 **실행** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4bcde-122"><STRONG>실행</STRONG> 단추가 해제된 경우 <STRONG>로컬 구성 저장소 설치</STRONG> 아래에서 먼저 <STRONG>실행</STRONG>을 클릭해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="4bcde-123">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="4bcde-p104">기본 인증서로 사용할 수 있는 인증서가 이미 있으면 인증서 마법사에서 **기본값**을 클릭하고 **지정**을 클릭합니다. 인증서 지정 마법사의 단계에 따라 해당 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-p104">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="4bcde-p105">기본 인증서를 사용하도록 인증서를 요청해야 할 경우 **요청**을 클릭한 후 인증서 요청 마법사의 단계에 따라 해당 인증서를 요청합니다. 웹 서버 인증서에 대한 기본값을 사용하면 기본 인증서로 지정할 수 있는 인증서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-p105">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="4bcde-128">감시자 노드 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="4bcde-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="4bcde-129">감시자 노드 컴퓨터를 다시 시작하고 인증서를 구성한 후에는 Watchernode.msi 파일을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="4bcde-130">(Operations Manager 에이전트 파일과 Lync Server 2013 핵심 구성 요소가 설치 되어 있는 컴퓨터에서 Watchernode.msi executable를 실행 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="4bcde-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="4bcde-131">**감시자 노드를 설치 및 구성하려면**</span><span class="sxs-lookup"><span data-stu-id="4bcde-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="4bcde-132">**시작**, **모든 프로그램**, **lync server**를 차례로 클릭 한 다음 **Lync Server 관리 셸을**클릭 하 여 lync server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4bcde-133">Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다 (Watchernode.msi executable 복사본의 실제 경로 지정).</span><span class="sxs-lookup"><span data-stu-id="4bcde-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4bcde-p107">또한 명령 창에서 Watchernode.msi를 실행할 수도 있습니다. 명령 창을 열려면 <STRONG>시작</STRONG>을 클릭하고 <STRONG>명령 프롬프트</STRONG>를 마우스 오른쪽 단추로 클릭한 후 <STRONG>관리자로 실행</STRONG>을 클릭합니다. 명령 창이 열리면 앞의 명령과 동일하게 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-p107">You can also run Watchernode.msi from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="4bcde-p108">앞의 명령 Authentication=TrustedServer에서 이름/값 쌍은 대/소문자를 구분합니다. 표시된 것과 정확히 동일하게 입력해야 합니다. 다음 명령은 대/소문자가 올바르지 않기 때문에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-p108">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive. You must type it exactly as shown. The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="4bcde-140">C:\\도구\\watchernode.msi executable 인증 = 서버</span><span class="sxs-lookup"><span data-stu-id="4bcde-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="4bcde-p109">경계 네트워크 내에 있는 컴퓨터에서만 TrustedServer 모드를 사용할 수 있습니다. 감시자 노드가 TrustedServer 모드로 실행될 때는 관리자가 컴퓨터에 테스트 사용자 암호를 유지 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bcde-p109">You can use TrustedServer mode only with computers that are located within the perimeter network. When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

