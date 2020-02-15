---
title: 'Lync Server 2013: 감시자 노드 설치 및 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19a4fad29b29dbec895a2c327ce2ddc054b8202b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="30628-102">Lync Server 2013에서 감시자 노드 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="30628-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30628-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="30628-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="30628-104">*감시자 노드* 는 Lync Server 가상 트랜잭션을 주기적으로 실행 하는 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="30628-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="30628-105">*가상 트랜잭션은* 시스템에 로그인 하는 기능, 또는 인스턴트 메시지를 교환 하는 기능과 같은 주요 최종 사용자 시나리오가 예상 대로 작동 하는지 확인 하는 Windows PowerShell cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="30628-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="30628-106">Lync Server 2013의 경우 System Center Operations Manager는 다음 표에 나와 있는 가상 트랜잭션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="30628-107">이 표에서는 세 가지 서로 다른 가상 트랜잭션 유형을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="30628-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="30628-108">**기본값**입니다.</span><span class="sxs-lookup"><span data-stu-id="30628-108">**Default**.</span></span> <span data-ttu-id="30628-109">감시자 노드가 기본적으로 실행 되는 가상 트랜잭션입니다.</span><span class="sxs-lookup"><span data-stu-id="30628-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="30628-110">새 감시자 노드를 만들 때는 해당 노드가 실행 될 가상 트랜잭션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="30628-111">이는 **get-cswatchernodeconfiguration** cmdlet에서 사용 되는 테스트 매개 변수의 용도입니다. 감시자 노드를 만들 때 테스트 매개 변수를 사용 하지 않으면 기본 가상 트랜잭션이 모두 자동으로 실행 되며 비기본 가상 트랜잭션이 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="30628-112">예를 들어, 감시자 노드가 테스트-CsAddressBookService 테스트를 실행 하도록 구성 되지만 Test-csexumconnectivity 테스트는 실행 하도록 구성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="30628-113">**기본값 아님**</span><span class="sxs-lookup"><span data-stu-id="30628-113">**Non-default**.</span></span> <span data-ttu-id="30628-114">이름 그대로 기본값이 아닌 가상 트랜잭션은 감시자 노드가 기본적으로 실행하지 않는 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="30628-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="30628-115">하지만 감시자 노드가 기본값이 아닌 가상 트랜잭션을 실행하도록 설정할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="30628-116">이러한 설정은 **New-CsWatcherNodeConfiguration** cmdlet을 사용하여 감시자 노드를 만들 때 또는 그 이후 언제라도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="30628-117">기본값이 아닌 가상 트랜잭션은 대부분의 경우 추가 설정 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="30628-118">자세한 내용은 [Lync Server 2013의 가상 트랜잭션에 대 한 특별 설치 지침](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="30628-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="30628-119">**확장**됩니다.</span><span class="sxs-lookup"><span data-stu-id="30628-119">**Extended**.</span></span> <span data-ttu-id="30628-120">확장 테스트는 특별한 유형의 기본값이 아닌 가상 트랜잭션입니다.</span><span class="sxs-lookup"><span data-stu-id="30628-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="30628-121">다른 가상 트랜잭션과 달리 확장 테스트는 한 번의 테스트 과정 중에 여러 번 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="30628-122">이러한 특성은 풀의 여러 PSTN(공중 전화망) 음성 경로와 같은 동작을 확인할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="30628-123">이 테스트는 단순히 확장 테스트의 여러 인스턴스를 감시자 노드에 추가하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="30628-124">다른 가상 트랜잭션을 감시자 노드에 추가 하는 프로세스에 대 한 자세한 내용은 [Lync Server 2013에서 감시자 노드 관리](lync-server-2013-managing-watcher-nodes.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="30628-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="30628-125">Lync Server 관리 셸을 사용 하 여 감시자 노드에서 가상 트랜잭션을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="30628-126">감시자 노드에서 사용할 수 있는 가상 트랜잭션에는 다음 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="30628-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30628-127">Cmdlet 이름(테스트 이름)</span><span class="sxs-lookup"><span data-stu-id="30628-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="30628-128">설명</span><span class="sxs-lookup"><span data-stu-id="30628-128">Description</span></span></th>
<th><span data-ttu-id="30628-129">가상 트랜잭션 유형</span><span class="sxs-lookup"><span data-stu-id="30628-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30628-130">Test-CsAddressBookService(ABS)</span><span class="sxs-lookup"><span data-stu-id="30628-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="30628-131">사용자가 자신의 대화 상대 목록에 없는 사용자를 조회할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="30628-132">기본</span><span class="sxs-lookup"><span data-stu-id="30628-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30628-133">Test-CsAddressBookWebQuery(ABWQ)</span><span class="sxs-lookup"><span data-stu-id="30628-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="30628-134">사용자가 HTTP를 통해 자신의 대화 상대 목록에 없는 사용자를 조회할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="30628-135">기본</span><span class="sxs-lookup"><span data-stu-id="30628-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30628-136">Test-CsIM(IM)</span><span class="sxs-lookup"><span data-stu-id="30628-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="30628-137">사용자가 피어 투 피어 인스턴트 메시지를 보낼 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="30628-138">기본</span><span class="sxs-lookup"><span data-stu-id="30628-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30628-139">Test-csp2pav (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="30628-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="30628-140">사용자가 피어 투 피어 음성 통화를 걸 수 있는지 확인합니다(신호만).</span><span class="sxs-lookup"><span data-stu-id="30628-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="30628-141">기본</span><span class="sxs-lookup"><span data-stu-id="30628-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30628-142">Test-CsPresence(Presence)</span><span class="sxs-lookup"><span data-stu-id="30628-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="30628-143">사용자가 다른 사용자의 현재 상태를 볼 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="30628-144">기본</span><span class="sxs-lookup"><span data-stu-id="30628-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30628-145">Test-CsRegistration(Registration)</span><span class="sxs-lookup"><span data-stu-id="30628-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="30628-146">사용자가 Lync에 로그인할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="30628-147">기본</span><span class="sxs-lookup"><span data-stu-id="30628-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30628-148">Test-CsAudioConferencingProvider(ACP)</span><span class="sxs-lookup"><span data-stu-id="30628-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="30628-149">온-프레미스 버전의 Lync Server 2013와 함께 사용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="30628-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="30628-150">오랜</span><span class="sxs-lookup"><span data-stu-id="30628-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30628-151">Test-CsPstnPeerToPeerCall(PSTN)</span><span class="sxs-lookup"><span data-stu-id="30628-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="30628-152">사용자가 기업 외부에 있는 사용자와 통화를 걸거나 받을 수 있는지 확인합니다(PSTN 번호).</span><span class="sxs-lookup"><span data-stu-id="30628-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="30628-153">기본값이 아님, 확장</span><span class="sxs-lookup"><span data-stu-id="30628-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30628-154">테스트-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="30628-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="30628-155">사용자가 오디오/비디오 회의를 만들고 참가할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="30628-156">기본</span><span class="sxs-lookup"><span data-stu-id="30628-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30628-157">Test-csavedgeconnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="30628-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="30628-158">A/V 에지 서버가 피어 투 피어 통화 및 회의 통화에 대한 연결을 허용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="30628-159">비기본</span><span class="sxs-lookup"><span data-stu-id="30628-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30628-160">Test-csdataconference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="30628-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="30628-161">사용자가 화이트보드 및 설문 조사와 같은 활동을 포함하여 데이터 공동 작업 회의 및 온라인 모임에 참가할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="30628-162">비기본</span><span class="sxs-lookup"><span data-stu-id="30628-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30628-163">Test-csexumconnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="30628-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="30628-164">사용자가 Exchange UM (통합 메시징)에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="30628-165">비기본</span><span class="sxs-lookup"><span data-stu-id="30628-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30628-166">테스트-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="30628-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="30628-167">사용자가 회의 중 인스턴트 메시지를 보내고 3명 이상의 사용자가 포함된 인스턴트 메시지 대화에 참가할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="30628-168">기본</span><span class="sxs-lookup"><span data-stu-id="30628-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30628-169">테스트-CsGroupIM-TestJoinLauncher 관리자 (Join시작 관리자)</span><span class="sxs-lookup"><span data-stu-id="30628-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="30628-170">사용자가 웹 주소 링크를 통해 예약된 모임을 만들고 참가할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="30628-171">비기본</span><span class="sxs-lookup"><span data-stu-id="30628-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30628-172">Test-csmcxp2pim (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="30628-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="30628-173">모바일 장치 사용자가 등록하고 인스턴트 메시지를 보낼 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="30628-174">비기본</span><span class="sxs-lookup"><span data-stu-id="30628-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30628-175">Test-cspersistentchatmessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="30628-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="30628-176">사용자가 영구 채팅 서비스를 사용 하 여 메시지를 교환할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="30628-177">비기본</span><span class="sxs-lookup"><span data-stu-id="30628-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30628-178">Test-csunifiedcontactstore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="30628-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="30628-179">통합 연락처 저장소를 사용해서 사용자의 연락처에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="30628-180">통합 연락처 저장소는 사용자가 Lync 2013, Outlook 및/또는 Outlook Web Access를 사용 하 여 액세스할 수 있는 단일 연락처 집합을 유지 관리 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="30628-181">비기본</span><span class="sxs-lookup"><span data-stu-id="30628-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30628-182">테스트-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="30628-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="30628-183">XMPP(Extensible Messaging and Presence Protocol) 게이트웨이에서 인스턴트 메시지를 전송할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="30628-184">비기본</span><span class="sxs-lookup"><span data-stu-id="30628-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="30628-185">System Center Operations Manager를 사용 하기 위해 감시자 노드를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="30628-186">이러한 노드를 설치 하지 않으면 문제가 발생할 때 Lync Server 2013 구성 요소에서 실시간 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="30628-187">(구성 요소 및 사용자 관리 팩은 감시자 노드를 사용 하지 않습니다.) 그러나 활성 모니터링 관리 팩을 사용 하 여 종단 간 시나리오를 모니터링 하려는 경우에는 감시자 노드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30628-188">관리자는 또한 Operations Manager를 사용하거나 설치할 필요 없이 가상 트랜잭션을 수동으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="30628-189">다양 한 테스트-Cs cmdlet에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlet 인덱스</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="30628-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="30628-190">배포 크기에 따라 가상 트랜잭션에는 대량의 컴퓨터 메모리 및 프로세서 시간이 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="30628-191">따라서 전용 컴퓨터를 감시자 노드로 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="30628-192">예를 들어, 감시자 노드로 작동 하도록 프런트 엔드 서버를 구성 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30628-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="30628-193">감시자 노드는 다음 하드웨어 사양을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30628-194">Lync Server 2013 감시자 노드를 사용 하 여 레거시 Microsoft Lync Server 2010 감시자 노드를 같은 컴퓨터에 배치 된 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="30628-195">Lync Server 2010 및 Lync Server 2013의 핵심 시스템 파일을 같은 컴퓨터에 설치할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="30628-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="30628-196">그러나 Lync Server 2013 감시자 노드는 Lync Server 2013 및 Lync Server 2010을 동시에 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="30628-197">두 제품 버전 모두 기본 가상 트랜잭션이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="30628-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="30628-198">Lync Server 2013 감시자 노드를 엔터프라이즈 내부 또는 외부에 배포 하 여 확인 하는 데 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="30628-199">기업 내부의 사용자 풀에 대한 연결</span><span class="sxs-lookup"><span data-stu-id="30628-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="30628-200">기업 외부에서 근무하는 원격 사용자를 위한 경계 네트워크를 통한 연결</span><span class="sxs-lookup"><span data-stu-id="30628-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="30628-201">지점 사무소 기기에 대한 연결</span><span class="sxs-lookup"><span data-stu-id="30628-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="30628-202">기업 내부 및 경계 네트워크 내부의 Lync Server 2010에 대 한 연결</span><span class="sxs-lookup"><span data-stu-id="30628-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="30628-203">관리를 간소화할 수 있도록 기업 내부 및 외부에서 다양한 인증 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="30628-204">자세한 내용은 [Lync Server 2013에서 가상 트랜잭션을 실행 하도록 감시자 노드 구성을](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="30628-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="30628-205">컴퓨터가 감시자 노드로 작동 하도록 구성 하려면 System Center Operations Manager를 설치 하 고 Lync Server 2013 관리 팩을 가져온 후에 다음 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="30628-206">Lync Server 2013 코어 파일과 System Center 에이전트 파일을 설치 하기 전에, 감시자 노드 컴퓨터가 Lync Server 2013 설치를 위한 모든 필수 구성 요소를 충족 하는지도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="30628-207">또한 감시자 노드 컴퓨터에는 다음과 같은 항목도 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30628-208">하드웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="30628-208">Hardware component</span></span></th>
<th><span data-ttu-id="30628-209">최소 요구 사항</span><span class="sxs-lookup"><span data-stu-id="30628-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30628-210">CPU</span><span class="sxs-lookup"><span data-stu-id="30628-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="30628-211">다음 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="30628-212">64 비트 프로세서, 쿼드 코어, 2.33 GHz 이상</span><span class="sxs-lookup"><span data-stu-id="30628-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="30628-213">64 비트 2 방향 프로세서, 듀얼 코어, 2.33 GHz 이상</span><span class="sxs-lookup"><span data-stu-id="30628-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30628-214">메모리</span><span class="sxs-lookup"><span data-stu-id="30628-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="30628-215">8GB</span><span class="sxs-lookup"><span data-stu-id="30628-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30628-216">네트워크 운영 체제</span><span class="sxs-lookup"><span data-stu-id="30628-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="30628-217">1Gbps 네트워크 어댑터 1 개</span><span class="sxs-lookup"><span data-stu-id="30628-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="30628-218">Windows Server 2008 R2, Windows Server 2012 또는</span><span class="sxs-lookup"><span data-stu-id="30628-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="30628-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="30628-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="30628-220">전체 버전의 .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="30628-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="30628-221">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="30628-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="30628-222">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="30628-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="30628-223">이러한 모든 필수 구성 요소가 충족되었으면 다음을 통해 감시자 노드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30628-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="30628-224">감시자 노드 컴퓨터에 Lync Server 2013 코어 파일 설치</span><span class="sxs-lookup"><span data-stu-id="30628-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="30628-225">감시자 노드 컴퓨터에 System Center Operations Manager 에이전트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="30628-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="30628-226">Watchernode.msi executable 파일 실행</span><span class="sxs-lookup"><span data-stu-id="30628-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="30628-227">**CsWatcherNodeConfiguration** cmdlet을 사용하여 감시자 노드에 사용할 테스트 사용자 구성</span><span class="sxs-lookup"><span data-stu-id="30628-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

