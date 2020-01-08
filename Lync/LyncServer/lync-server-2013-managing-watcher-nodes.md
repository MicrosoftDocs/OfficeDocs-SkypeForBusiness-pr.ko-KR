---
title: 'Lync Server 2013: 감시자 노드 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7edddd1a1bb67dc4bf3df5b7809aa76b2397e56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="ee330-102">Lync Server 2013에서 감시자 노드 관리</span><span class="sxs-lookup"><span data-stu-id="ee330-102">Managing watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee330-103">_**마지막으로 수정한 주제:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ee330-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ee330-104">감시자 노드에서 실행 되는 가상 트랜잭션을 수정 하는 것 외에도 관리자는 **CsWatcherNodeConfiguration** cmdlet을 사용 하 여 감시자 노드의 사용 여부를 설정 하거나 해제 하 고 해당 테스트를 실행할 때 내부 url 또는 외부 url을 사용 하도록 감시자 노드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-104">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="ee330-105">기본적으로 감시자 노드는 사용 하도록 설정 된 모든 가상 트랜잭션을 정기적으로 실행 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-105">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="ee330-106">그러나 경우에 따라 해당 트랜잭션을 일시 중단 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-106">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="ee330-107">예를 들어 감시자 노드가 네트워크에서 일시적으로 연결이 끊어지면 가상 트랜잭션을 실행할 이유가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-107">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="ee330-108">네트워크 연결이 없으면 해당 트랜잭션이 실패 하는 것으로 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-108">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="ee330-109">감시자 노드를 일시적으로 사용 하지 않도록 설정 하려는 경우 Lync Server 관리 셸에서 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-109">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="ee330-110">이 명령은 감시자 노드 atl-001.litwareinc.com에서 가상 트랜잭션의 실행을 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-110">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com.</span></span> <span data-ttu-id="ee330-111">가상 트랜잭션의 실행을 다시 시작 하려면 Enabled 속성을 다시 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-111">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="ee330-112">Enabled 속성을 사용 하 여 감시자 노드를 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-112">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="ee330-113">감시자 노드를 영구적으로 삭제 하려면 <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-113">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="ee330-114">제거-CsWatcherNodeConfiguration – Id "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="ee330-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="ee330-115">이 명령은 지정 된 컴퓨터에서 모든 감시자 노드 구성 설정을 제거 하 여 컴퓨터에서 가상 트랜잭션을 자동으로 실행 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-115">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="ee330-116">그러나이 명령은 System Center 에이전트 파일 또는 Lync Server 2013 시스템 파일을 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-116">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="ee330-117">기본적으로 감시자 노드는 테스트를 수행할 때 조직의 외부 Url을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-117">By default, watcher nodes use an organization's external URLs when conducting their tests.</span></span> <span data-ttu-id="ee330-118">그러나 조직의 내부 Url을 사용 하도록 감시자 노드를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-118">However, watcher nodes can also be configured to use the organization's internal URLs.</span></span> <span data-ttu-id="ee330-119">이렇게 하면 관리자가 경계 네트워크 내에 있는 사용자의 URL 액세스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-119">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="ee330-120">외부 Url 대신 내부 Url을 사용 하도록 감시자 노드를 구성 하려면 UseInternalWebUrls 속성을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-120">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="ee330-121">이 속성을 기본값인 False ($False)로 다시 설정 하면 감시자가 외부 Url을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee330-121">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

