---
title: 감시자 노드 설치 및 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: '요약: 비즈니스용 Skype 서버 가상 트랜잭션에 대한 감시자 노드를 설치하고 구성합니다.'
ms.openlocfilehash: f6d3db973291b8a41647a3c4a4d3c3530c7af019
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812760"
---
# <a name="install-and-configure-watcher-nodes"></a><span data-ttu-id="74307-103">감시자 노드 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="74307-103">Install and configure watcher nodes</span></span>
 
<span data-ttu-id="74307-104">**요약:** 비즈니스용 Skype 서버 가상 트랜잭션에 대한 감시자 노드를 설치하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-104">**Summary:** Install and configure watcher nodes for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="74307-105">감시자 노드는 주기적으로 비즈니스용 Skype 서버 가상 트랜잭션을 실행하는 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="74307-105">Watcher nodes are computers that periodically run Skype for Business Server synthetic transactions.</span></span> <span data-ttu-id="74307-106">가상 트랜잭션은 Windows PowerShell 인스턴트 메시지를 교환하는 등의 주요 사용자 시나리오가 예상대로 작동하고 있는지 확인하는 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="74307-106">Synthetic transactions are Windows PowerShell cmdlets that verify that key user scenarios, such as the ability to sign in or to exchange instant messages, are working as expected.</span></span> <span data-ttu-id="74307-107">비즈니스용 Skype 서버 2015의 경우 System Center Operations Manager는 다음 표에 나와 있는 가상 트랜잭션을 실행할 수 있습니다. 여기에는 세 가지 가상 트랜잭션 유형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="74307-107">For Skype for Business Server 2015, System Center Operations Manager can run the synthetic transactions shown in the following table, which includes three synthetic transaction types:</span></span>
  
- <span data-ttu-id="74307-108">**기본값** 감시자 노드가 기본적으로 실행되는 가상 트랜잭션입니다.</span><span class="sxs-lookup"><span data-stu-id="74307-108">**Default** Synthetic transactions that a watcher node runs by default.</span></span> <span data-ttu-id="74307-109">새 감시자 노드를 만들 때 해당 노드가 실행될 가상 트랜잭션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-109">When you create a new watcher node, you can specify which synthetic transactions that node will run.</span></span> <span data-ttu-id="74307-110">이 매개 변수는 이 cmdlet에서 사용되는 Tests 매개 New-CsWatcherNodeConfiguration 사용됩니다. 감시자 노드를 만들 때 Tests 매개 변수를 사용하지 않는 경우 모든 기본 가상 트랜잭션이 자동으로 실행되고 기본이 아닌 가상 트랜잭션이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-110">(That's the purpose of the Tests parameter used by the New-CsWatcherNodeConfiguration cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="74307-111">즉, 예를 들어 감시자 노드가 Test-CsAddressBookService 실행하도록 구성되지만 감시자 노드는 Test-CsExumConnectivity 실행하도록 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-111">This means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>
    
- <span data-ttu-id="74307-112">**기본값이 아닌 경우** 감시자 노드가 기본적으로 실행되지 않는 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="74307-112">**Non-default** Tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="74307-113">자세한 내용은 기본 형식에 대한 설명을 참조하세요. 그러나 감시자 노드를 사용하도록 설정하여 기본이 아닌 가상 트랜잭션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-113">(For details, see the description of the Default type.) However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="74307-114">감시자 노드를 만들 때(New-CsWatcherNodeConfiguration cmdlet을 사용하여) 감시자 노드를 만들 때 또는 감시자 노드가 만들어진 후 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-114">You can do this when you create the watcher node (by using the New-CsWatcherNodeConfiguration cmdlet), or any time after the watcher node has been created.</span></span> <span data-ttu-id="74307-115">기본이 아닌 가상 트랜잭션은 대부분 추가 설정 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-115">Note that many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="74307-116">이러한 단계에 대한 자세한 내용은 가상 트랜잭션에 대한 특수 [설치 지침을 참조하세요.](test-users-and-settings.md#special_synthetictrans)</span><span class="sxs-lookup"><span data-stu-id="74307-116">For more details about these steps, see [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).</span></span>
    
- <span data-ttu-id="74307-117">**확장** 기본이 아닌 가상 트랜잭션의 특별한 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="74307-117">**Extended** A special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="74307-118">다른 가상 트랜잭션과 달리 확장 테스트는 한 번의 테스트 과정 중에 여러 번 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-118">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="74307-119">이 기능은 풀의 여러 PSTN(Public Switched Telephone Network) 음성 경로와 같은 동작을 확인할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-119">This is useful when verifying behavior, such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="74307-120">감시자 노드에 확장 테스트의 여러 인스턴스를 추가하여 이 작업을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-120">You can configure this simply by adding multiple instances of an extended test to a watcher node.</span></span>
    
<span data-ttu-id="74307-121">감시자 노드에 다른 가상 트랜잭션을 추가하는 프로세스에 대한 자세한 내용은 가상 트랜잭션을 실행하도록 감시자 [노드 구성을 참조합니다.](watcher-nodes.md#enable_synthetic_trans)</span><span class="sxs-lookup"><span data-stu-id="74307-121">For details about the process for adding other synthetic transactions to a watcher node, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span> <span data-ttu-id="74307-122">비즈니스용 Skype 서버 관리 셸을 사용하여 감시자 노드에서 가상 트랜잭션을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-122">You can also use Skype for Business Server Management Shell to remove synthetic transactions from a watcher node.</span></span>
  
<span data-ttu-id="74307-123">감시자 노드에서 사용할 수 있는 가상 트랜잭션에는 다음 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="74307-123">The synthetic transactions available to watcher nodes include the following:</span></span>
  
|<span data-ttu-id="74307-124">**Cmdlet 이름(테스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="74307-124">**Cmdlet Name (Test Name)**</span></span>|<span data-ttu-id="74307-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="74307-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="74307-126">Test-CsAddressBookService(ABS)</span><span class="sxs-lookup"><span data-stu-id="74307-126">Test-CsAddressBookService (ABS)</span></span>  <br/> |<span data-ttu-id="74307-127">사용자가 자신의 연락처 목록에 없는 사용자를 확인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-127">Confirms that users are able to look up users who aren't in their contact list.</span></span>  <br/> |
|<span data-ttu-id="74307-128">Test-CsAddressBookWebQuery(ABWQ)</span><span class="sxs-lookup"><span data-stu-id="74307-128">Test-CsAddressBookWebQuery (ABWQ)</span></span>  <br/> |<span data-ttu-id="74307-129">사용자가 HTTP를 통해 연락처 목록에 없는 사용자를 확인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-129">Confirms that users are able to look up users who aren't in their contact list via HTTP.</span></span>  <br/> |
|<span data-ttu-id="74307-130">Test-CsAVConference(AvConference)</span><span class="sxs-lookup"><span data-stu-id="74307-130">Test-CsAVConference (AvConference)</span></span>  <br/> |<span data-ttu-id="74307-131">사용자가 오디오/비디오 회의를 만들고 참가할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-131">Confirms that users are able to create and participate in an audio/video conference.</span></span>  <br/> |
|<span data-ttu-id="74307-132">Test-CsGroupIM(IM 회의)</span><span class="sxs-lookup"><span data-stu-id="74307-132">Test-CsGroupIM (IM Conferencing)</span></span>  <br/> |<span data-ttu-id="74307-133">사용자가 회의 중 인스턴트 메시지를 보내고 3명 이상의 사용자가 포함된 인스턴트 메시지 대화에 참가할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-133">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span>  <br/> |
|<span data-ttu-id="74307-134">Test-CsIM(P2P IM)</span><span class="sxs-lookup"><span data-stu-id="74307-134">Test-CsIM (P2P IM)</span></span>  <br/> |<span data-ttu-id="74307-135">사용자가 피어 투 피어 인스턴트 메시지를 보낼 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-135">Confirms that users are able to send peer-to-peer instant messages.</span></span>  <br/> |
|<span data-ttu-id="74307-136">Test-CsP2PAV(P2PAV)</span><span class="sxs-lookup"><span data-stu-id="74307-136">Test-CsP2PAV (P2PAV)</span></span>  <br/> |<span data-ttu-id="74307-137">사용자가 피어 투 피어 음성 통화를 걸 수 있는지 확인합니다(신호만).</span><span class="sxs-lookup"><span data-stu-id="74307-137">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span>  <br/> |
|<span data-ttu-id="74307-138">Test-CsPresence(Presence)</span><span class="sxs-lookup"><span data-stu-id="74307-138">Test-CsPresence (Presence)</span></span>  <br/> |<span data-ttu-id="74307-139">사용자가 다른 사용자의 현재 상태 정보를 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-139">Confirms that users are able to view other users' presence.</span></span>  <br/> |
|<span data-ttu-id="74307-140">Test-CsRegistration(Registration)</span><span class="sxs-lookup"><span data-stu-id="74307-140">Test-CsRegistration (Registration)</span></span>  <br/> |<span data-ttu-id="74307-141">사용자가 비즈니스용 Skype에 로그인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-141">Confirms that users are able sign in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="74307-142">Test-CsPstnPeerToPeerCall(PSTN)</span><span class="sxs-lookup"><span data-stu-id="74307-142">Test-CsPstnPeerToPeerCall (PSTN)</span></span>  <br/> |<span data-ttu-id="74307-143">사용자가 기업 외부에 있는 사용자와 통화를 걸거나 받을 수 있는지 확인합니다(PSTN 번호).</span><span class="sxs-lookup"><span data-stu-id="74307-143">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span>  <br/> |
|<span data-ttu-id="74307-144">Test-CsASConference(ASConference)</span><span class="sxs-lookup"><span data-stu-id="74307-144">Test-CsASConference (ASConference)</span></span>  <br/> |<span data-ttu-id="74307-145">사용자가 응용 프로그램 공유 회의를 만들고 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-145">Confirms that users are able to create and participate in an application sharing conference.</span></span>  <br/> |
|<span data-ttu-id="74307-146">Test-CsAVEdgeConnectivity(AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="74307-146">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span>  <br/> |<span data-ttu-id="74307-147">오디오 비디오 에지 서버가 피어 투 피어 통화 및 전화 회의 통화에 대한 연결을 수락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-147">Confirms that the Audio Video Edge servers are able to accept connections for peer-to- peer calls and conference calls.</span></span>  <br/> |
|<span data-ttu-id="74307-148">Test-CsDataConference(DataConference)</span><span class="sxs-lookup"><span data-stu-id="74307-148">Test-CsDataConference (DataConference)</span></span>  <br/> |<span data-ttu-id="74307-149">사용자가 데이터 공동 작업 회의(화이트보드 및 설문 조사와 같은 활동을 포함하는 온라인 모임)에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-149">Confirms that users can participate in a data collaboration conference (an online meeting that includes activities such as whiteboards and polls).</span></span>  <br/> |
|<span data-ttu-id="74307-150">Test-CsDialinConferencing(DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="74307-150">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="74307-151">사용자가 전화 번호로 전화 회의에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-151">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="74307-152">Test-CsDialinConferencing(DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="74307-152">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="74307-153">사용자가 전화 번호로 전화 회의에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-153">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="74307-154">Test-CsExumConnectivity(ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="74307-154">Test-CsExumConnectivity (ExumConnectivity)</span></span>  <br/> |<span data-ttu-id="74307-155">사용자가 Exchange UM(통합 메시징)에 연결할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-155">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span>  <br/> |
|<span data-ttu-id="74307-156">Test-CsGroupIM -TestJoinLauncher(JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="74307-156">Test-CsGroupIM -TestJoinLauncher (JoinLauncher)</span></span>  <br/> |<span data-ttu-id="74307-157">사용자가 웹 주소 링크를 통해 예약된 모임을 만들고 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-157">Confirms that users are able to create and join scheduled meetings (by a web address link).</span></span>  <br/> |
|<span data-ttu-id="74307-158">Test-CsMCXP2PIM(MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="74307-158">Test-CsMCXP2PIM (MCXP2PIM)</span></span>  <br/> |<span data-ttu-id="74307-159">모바일 장치 사용자가 등록하고 인스턴트 메시지를 보낼 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-159">Confirms that mobile device users are able to register and send instant messages.</span></span>  <br/> |
|<span data-ttu-id="74307-160">Test-CsP2PVideoInteropServerSipTrunkAV(P2PVideoInteropServerSipTrunkAV)</span><span class="sxs-lookup"><span data-stu-id="74307-160">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span></span>  <br/> |<span data-ttu-id="74307-161">비디오 SIP 트렁크를 통해 비디오 Interop 서버가 설치 및 수신 연결을 처리할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-161">Confirms that Video Interop Server is up and can handle incoming connections over a video SIP trunk.</span></span>  <br/> <span data-ttu-id="74307-162">**참고:** 레거시 모바일 클라이언트에 대한 MCX 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-162">**Note:** MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> |
|<span data-ttu-id="74307-163">Test-CsPersistentChatMessage(PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="74307-163">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span>  <br/> |<span data-ttu-id="74307-164">사용자가 영구 채팅 서비스를 사용하여 메시지를 교환할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-164">Confirms that users can exchange messages by using the Persistent Chat service.</span></span>  <br/> |
|<span data-ttu-id="74307-165">Test-CsUcwaConference(UcwaConference)</span><span class="sxs-lookup"><span data-stu-id="74307-165">Test-CsUcwaConference (UcwaConference)</span></span>  <br/> |<span data-ttu-id="74307-166">사용자가 웹을 통해 전화 회의에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-166">Confirms that users can join conferences via the web.</span></span>  <br/> |
|<span data-ttu-id="74307-167">Test-CsUnifiedContactStore(UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="74307-167">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span>  <br/> |<span data-ttu-id="74307-168">통합 연락처 저장소를 사용해서 사용자의 연락처에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-168">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="74307-169">사용자는 통합 연락처 저장소를 통해 비즈니스용 Skype 서버 2015, Outlook 메시징 및 공동 작업 클라이언트 및/또는 Outlook Web Access를 사용하여 액세스할 수 있는 단일 연락처 집합을 유지 관리하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-169">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Skype for Business Server 2015, Outlook messaging and collaboration client, and/or Outlook Web Access.</span></span>  <br/> |
|<span data-ttu-id="74307-170">Test-CsXmppIM(XmppIM)</span><span class="sxs-lookup"><span data-stu-id="74307-170">Test-CsXmppIM (XmppIM)</span></span>  <br/> |<span data-ttu-id="74307-171">인스턴트 메시지를 XMPP(Extensible Messaging and Presence Protocol) 게이트웨이를 통해 보낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-171">Confirms that an instant message can be sent across the Extensible Messaging and Presence Protocol (XMPP) gateway.</span></span>  <br/> <span data-ttu-id="74307-172">XMPP 게이트웨이 및 XMPP 게이트웨이는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-172">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span>  |

<span data-ttu-id="74307-173">System Center Operations Manager를 사용하기 위해 감시자 노드를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-173">You do not need to install watcher nodes to use System Center Operations Manager.</span></span> <span data-ttu-id="74307-174">이러한 노드를 설치하지 않은 경우 문제가 발생할 때마다 비즈니스용 Skype 서버 2015 구성 요소에서 실시간 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-174">If you do not install these nodes, you can still get real-time alerts from Skype for Business Server 2015 components whenever an issue occurs.</span></span> <span data-ttu-id="74307-175">구성 요소 및 사용자 관리 팩은 감시자 노드를 사용하지 않습니다. 그러나 활성 모니터링 관리 팩을 사용하여 종단 내 시나리오를 모니터링하려면 감시자 노드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-175">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74307-176">관리자는 Operations Manager를 사용하지 않고 설치하지 않고도 가상 트랜잭션을 수동으로 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-176">Administrators can also run synthetic transactions manually, without using or installing Operations Manager.</span></span> <span data-ttu-id="74307-177">비즈니스용 Skype 서버 배포의 크기에 따라 가상 트랜잭션은 많은 양의 컴퓨터 메모리와 프로세서 시간을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-177">Depending on the size of your Skype for Business Server deployment, synthetic transactions can use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="74307-178">따라서 전용 컴퓨터를 감시자 노드로 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-178">Because of this, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="74307-179">예를 들어 감시자 노드 역할을 하도록 비즈니스용 Skype 서버 프런트 엔드 서버를 구성하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74307-179">For example, you should not configure a Skype for Business Server Front End Server to act as a watcher node.</span></span> <span data-ttu-id="74307-180">감시자 노드는 비즈니스용 Skype 서버 토폴로지의 다른 컴퓨터와 동일한 기본 하드웨어 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-180">Watcher nodes should meet the same basic hardware requirements as any other computer in your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="74307-181">Lync Server 2013 및 비즈니스용 Skype 서버 2015의 핵심 시스템 파일을 동일한 컴퓨터에 설치할 수 없는 경우 레거시 Lync Server 2013 감시자 노드를 비즈니스용 Skype 서버 2015 감시자 노드와 동일한 컴퓨터에 함께 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-181">A legacy Lync Server 2013 watcher node cannot be collocated on the same machine as a Skype for Business Server 2015 watcher node because the core system files for Lync Server 2013 and Skype for Business Server 2015 cannot be installed on the same computer.</span></span> <span data-ttu-id="74307-182">그러나 비즈니스용 Skype 서버 2015 감시자 노드는 비즈니스용 Skype 서버 2015 및 Lync Server 2013을 동시에 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-182">However, Skype for Business Server 2015 watcher nodes can simultaneously monitor Skype for Business Server 2015 and Lync Server 2013.</span></span> <span data-ttu-id="74307-183">기본 가상 트랜잭션은 두 제품 버전에서 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="74307-183">Default synthetic transactions are supported for both product versions.</span></span> 
  
<span data-ttu-id="74307-184">Lync Server 2013 감시자 노드는 다음을 확인하기 위해 엔터프라이즈 내부 또는 외부에 배포될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-184">Lync Server 2013 watcher nodes may be deployed inside or outside an enterprise to help verify:</span></span>
  
- <span data-ttu-id="74307-185">기업 내부의 사용자 풀에 대한 연결</span><span class="sxs-lookup"><span data-stu-id="74307-185">Connectivity to pools for users inside the enterprise.</span></span>
    
- <span data-ttu-id="74307-186">엔터프라이즈 외부에서 작업하는 원격 사용자를 위한 경계 네트워크를 통한 연결</span><span class="sxs-lookup"><span data-stu-id="74307-186">Connectivity through perimeter networks for remote users working outside the enterprise.</span></span>
    
- <span data-ttu-id="74307-187">지점 사무소 기기에 대한 연결</span><span class="sxs-lookup"><span data-stu-id="74307-187">Connectivity to branch office appliances.</span></span>
    
- <span data-ttu-id="74307-188">엔터프라이즈 내부 및 경계 네트워크를 통해 Lync Server 2013에 연결</span><span class="sxs-lookup"><span data-stu-id="74307-188">Connectivity to Lync Server 2013 inside the enterprise and through perimeter networks.</span></span>
    
<span data-ttu-id="74307-189">관리를 간소화하기 위해 기업 내부 및 외부에서 다양한 인증 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-189">To help simplify administration, different authentication options are available for inside and outside of the enterprise.</span></span> <span data-ttu-id="74307-190">자세한 내용은 가상 트랜잭션을 [실행하도록 감시자 노드 구성을 참조합니다.](watcher-nodes.md#enable_synthetic_trans)</span><span class="sxs-lookup"><span data-stu-id="74307-190">For details, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span>
  
<span data-ttu-id="74307-191">컴퓨터가 감시자 노드 역할을 하도록 구성하려면 먼저 다음의 선행 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-191">To configure a computer to act as a watcher node, you must first complete the following prerequisites:</span></span> 
  
- <span data-ttu-id="74307-192">System Center Operations Manager를 설치하고 비즈니스용 Skype 서버 2015 관리 팩을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-192">Install System Center Operations Manager and import the Skype for Business Server 2015 management packs.</span></span> <span data-ttu-id="74307-193">또한 먼저 감시자 노드 컴퓨터가 비즈니스용 Skype 서버 2015 설치를 위한 모든 선행 요구 사항을 충족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-193">You must also first verify that the watcher node computer meets all prerequisites for installing Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="74307-194">감시자 노드 컴퓨터에 다음 항목을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-194">Install the following items on the watcher node computer:</span></span>
    
  - <span data-ttu-id="74307-195">.NET Framework 4.5 정식 버전</span><span class="sxs-lookup"><span data-stu-id="74307-195">The full version of .NET Framework 4.5</span></span>
    
  - <span data-ttu-id="74307-196">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="74307-196">Windows Identity Foundation</span></span>
    
  - <span data-ttu-id="74307-197">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="74307-197">Windows PowerShell 3.0</span></span>
    
<span data-ttu-id="74307-198">선행 구성이 충족되면 다음 단계에 따라 감시자 노드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-198">After the prerequisites are met, you can configure the watcher node by following these steps:</span></span>
  
1. <span data-ttu-id="74307-199">감시자 노드 컴퓨터에 비즈니스용 Skype 서버 2015 핵심 파일을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-199">Install the Skype for Business Server 2015 core files on the watcher node computer.</span></span>
    
2. <span data-ttu-id="74307-200">감시자 노드 컴퓨터에 System Center Operations Manager 에이전트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-200">Install System Center Operations Manager agent on the watcher node computer.</span></span>
    
3. <span data-ttu-id="74307-201">실행 Watchernode.msi 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-201">Run the Watchernode.msi executable file.</span></span>
    
4. <span data-ttu-id="74307-202">**New-CsWatcherNodeConfiguration** cmdlet을 사용하여 감시자 노드에서 사용할 테스트 사용자 계정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-202">Use the **New-CsWatcherNodeConfiguration** cmdlet to configure test user accounts to be employed by the watcher node.</span></span>
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a><span data-ttu-id="74307-203">비즈니스용 Skype 서버 2015 핵심 파일 및 RTCLocal 데이터베이스 설치</span><span class="sxs-lookup"><span data-stu-id="74307-203">Install the Skype for Business Server 2015 Core Files and the RTCLocal Database</span></span>

<span data-ttu-id="74307-204">컴퓨터에 비즈니스용 Skype 서버 2015 핵심 파일을 설치하려면 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-204">To install the Skype for Business Server 2015 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="74307-205">핵심 파일을 설치할 때 RTCLocal 데이터베이스가 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="74307-205">The RTCLocal database will automatically be installed when you install the core files.</span></span> <span data-ttu-id="74307-206">감시자 노드에 SQL Server 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-206">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="74307-207">SQL Server Express가 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="74307-207">SQL Server Express will be automatically installed.</span></span>
  
<span data-ttu-id="74307-208">비즈니스용 Skype 서버 2015 핵심 파일 및 RTCLocal 데이터베이스를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="74307-208">To install the Skype for Business Server 2015 core files and the RTCLocal database:</span></span>
  
1. <span data-ttu-id="74307-209">감시자 노드 컴퓨터에서 시작, 모든 프로그램,  보조 프로그램을 차례로 클릭하고 명령 프롬프트를 마우스 오른쪽 단추로 클릭한 후 관리자로 실행을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-209">On the watcher node computer, click Start, click All Programs, click Accessories, right-click Command Prompt, and then click Run as administrator.</span></span>
    
2. <span data-ttu-id="74307-210">콘솔 창에서 다음 명령을 입력하고 Enter를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-210">In the console window, type the following command and press ENTER.</span></span> <span data-ttu-id="74307-211">비즈니스용 Skype 서버 설치 파일에 대한 적절한 경로를 입력해야 합니다. D:\Setup.exe /BootstrapLocalMgmtTo는 핵심 비즈니스용 Skype 서버 구성 요소가 성공적으로 설치되어 있는지 확인하고 시작, 모든 프로그램, 비즈니스용 **Skype 서버 2015를** 클릭한 다음 비즈니스용 **Skype** 서버 관리 셸을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-211">Be sure to enter the appropriate path to your Skype for Business Server setup files: D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype for Business Server components are successfully installed, click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Management Shell**.</span></span> <span data-ttu-id="74307-212">비즈니스용 Skype 서버 관리 셸에서 다음 Windows PowerShell 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-212">In the Skype for Business Server Management Shell, type the following Windows PowerShell command and press ENTER:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> <span data-ttu-id="74307-213">이 명령을 처음 실행할 때 감시자 노드 컴퓨터를 아직 구성하지 않았기 때문에 데이터가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-213">The first time you run this command, no data will be returned because you have not yet configured any watcher node computers.</span></span> <span data-ttu-id="74307-214">명령이 오류를 반환하지 않고 실행되는 경우 비즈니스용 Skype 서버 설치가 완료된 것으로 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-214">If the command runs without returning an error, you can assume that the Skype for Business Server setup completed successfully.</span></span> 
  
<span data-ttu-id="74307-215">감시자 노드 컴퓨터가 경계 네트워크 내부에 있는 경우 다음 명령을 실행하여 비즈니스용 Skype 서버 2015의 설치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-215">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Skype for Business Server 2015:</span></span>
  
<span data-ttu-id="74307-216">Get-CsPinPolicyYou 사용하도록 구성된 PIN 정책의 수에 따라 이와 유사한 정보가 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="74307-216">Get-CsPinPolicyYou will receive information similar to this, depending on the number of PIN policies configured for use in your organization:</span></span>
  
<span data-ttu-id="74307-217">ID : Global</span><span class="sxs-lookup"><span data-stu-id="74307-217">Identity : Global</span></span>
  
<span data-ttu-id="74307-218">설명 :</span><span class="sxs-lookup"><span data-stu-id="74307-218">Description :</span></span>
  
<span data-ttu-id="74307-219">MinPasswordLength : 5</span><span class="sxs-lookup"><span data-stu-id="74307-219">MinPasswordLength : 5</span></span>
  
<span data-ttu-id="74307-220">PINHistoryCount : 0</span><span class="sxs-lookup"><span data-stu-id="74307-220">PINHistoryCount : 0</span></span>
  
<span data-ttu-id="74307-221">AllowCommonPatterns : False</span><span class="sxs-lookup"><span data-stu-id="74307-221">AllowCommonPatterns : False</span></span>
  
<span data-ttu-id="74307-222">PINLifetime : 0</span><span class="sxs-lookup"><span data-stu-id="74307-222">PINLifetime : 0</span></span>
  
<span data-ttu-id="74307-223">MaximumLogonAttempts :</span><span class="sxs-lookup"><span data-stu-id="74307-223">MaximumLogonAttempts :</span></span>
  
<span data-ttu-id="74307-224">PIN 정책에 대한 정보가 표시되면 핵심 구성 요소가 성공적으로 설치되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-224">If you see information about your PIN policies, the core components have been successfully installed.</span></span>
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a><span data-ttu-id="74307-225">감시자 노드에 Operation Manager 에이전트 파일 설치</span><span class="sxs-lookup"><span data-stu-id="74307-225">Install the Operation Manager Agent Files on a Watcher Node</span></span>

<span data-ttu-id="74307-226">구성 요소 경고 보고를 위한 비즈니스용 Skype 서버 설정과 마찬가지로 비즈니스용 Skype 서버 2015 감시자 노드를 사용하려면 System Center Operations Manager 에이전트 파일을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-226">Similar to Skype for Business Server setup for reporting component alerts, a Skype for Business Server 2015 watcher node requires System Center Operations Manager agent files to be installed.</span></span> <span data-ttu-id="74307-227">이렇게 하면 가상 트랜잭션을 실행하고 경고를 System Center Operations Manager 루트 관리 서버에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-227">This enables the synthetic transactions to be run and alerts to be reported to the System Center Operations Manager Root Management Server.</span></span>
  
<span data-ttu-id="74307-228">에이전트 파일을 설치하려면 모니터링할 비즈니스용 Skype 서버 컴퓨터 구성에 나열된 절차를 [수행하십시오.](configure-computers-to-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="74307-228">To install the agent files, follow the procedures listed in [Configure the Skype for Business Server computers that will be monitored](configure-computers-to-monitor.md).</span></span>
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a><span data-ttu-id="74307-229">가상 트랜잭션을 실행하도록 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="74307-229">Configure a Watcher Node to Run Synthetic Transactions</span></span>
<span data-ttu-id="74307-230"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="74307-230"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="74307-231">System Center Operations Manager 에이전트 파일을 설치한 후 감시자 노드 자체를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-231">After the System Center Operations Manager agent files have been installed, you must configure the watcher node itself.</span></span> <span data-ttu-id="74307-232">이를 위해 수행되는 단계는 감시자 노드 컴퓨터가 경계 네트워크 내부에 있는지 또는 경계 네트워크 외부에 있는지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="74307-232">The steps you take to do this will vary, depending on whether your watcher node computer is inside your perimeter network or outside your perimeter network.</span></span> 
  
<span data-ttu-id="74307-233">감시자 노드를 구성할 때 해당 노드에서 사용할 인증 방법 유형도 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-233">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="74307-234">비즈니스용 Skype 서버 2015에서는 신뢰할 수 있는 서버 또는 자격 증명 인증의 두 가지 인증 방법 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-234">Skype for Business Server 2015 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="74307-235">다음 표에서는 이러한 두 방법 간의 차이점을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="74307-235">The following table shows the differences between these two methods:</span></span>
  
||<span data-ttu-id="74307-236">**설명**</span><span class="sxs-lookup"><span data-stu-id="74307-236">**Description**</span></span>|<span data-ttu-id="74307-237">**지원되는 위치**</span><span class="sxs-lookup"><span data-stu-id="74307-237">**Locations supported**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="74307-238">TrustedServer</span><span class="sxs-lookup"><span data-stu-id="74307-238">TrustedServer</span></span>  <br/> |<span data-ttu-id="74307-239">인증서를 사용하여 내부 서버를 가장하고 인증 챌린지 무시</span><span class="sxs-lookup"><span data-stu-id="74307-239">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span>  <br/> <span data-ttu-id="74307-240">각 감시자 노드에서 여러 사용자 암호 대신 단일 인증서를 관리하기를 원하는 관리자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-240">Useful for administrators who prefer to manage a single certificate, instead of many user passwords on each watcher node.</span></span>  <br/> |<span data-ttu-id="74307-241">엔터프라이즈 내부.</span><span class="sxs-lookup"><span data-stu-id="74307-241">Inside the enterprise.</span></span>  <br/> <span data-ttu-id="74307-242">이 방법을 사용하면 감시자 노드가 모니터링되는 풀과 동일한 도메인에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-242">With this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="74307-243">감시자 노드와 풀이 서로 다른 도메인에 있는 경우 자격 증명 인증을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-243">If the watcher node and the pools are in different domains, use Credential Authentication instead.</span></span>  <br/> |
|<span data-ttu-id="74307-244">협상</span><span class="sxs-lookup"><span data-stu-id="74307-244">Negotiate</span></span>  <br/> |<span data-ttu-id="74307-245">각 감시자 노드의 Windows 자격 증명 관리자에 사용자 이름과 암호를 안전하게 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-245">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span>  <br/> <span data-ttu-id="74307-246">이 모드에서는 더 많은 암호 관리가 필요하지만 엔터프라이즈 외부의 감시자 노드에 대한 유일한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="74307-246">This mode requires more password management, but is the only option for watcher nodes outside the enterprise.</span></span> <span data-ttu-id="74307-247">이러한 감시자 노드는 인증을 위해 신뢰할 수 있는 끝점으로 취급될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-247">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span>  <br/> |<span data-ttu-id="74307-248">기업 외부.</span><span class="sxs-lookup"><span data-stu-id="74307-248">Outside the enterprise.</span></span>  <br/> <span data-ttu-id="74307-249">엔터프라이즈 내부.</span><span class="sxs-lookup"><span data-stu-id="74307-249">Inside the enterprise.</span></span>  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a><span data-ttu-id="74307-250">신뢰할 수 있는 서버 인증을 사용하도록 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="74307-250">Configure a Watcher Node to Use Trusted Server Authentication</span></span>
<span data-ttu-id="74307-251"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="74307-251"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="74307-252">감시자 노드 컴퓨터가 경계 네트워크 내부에 있는 경우 신뢰할 수 있는 서버 인증을 사용하는 경우 많은 사용자 계정 암호를 사용하는 대신 단일 인증서를 유지 관리하여 관리 작업을 크게 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-252">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration tasks by maintaining a single certificate, rather than using numerous user account passwords.</span></span>
  
<span data-ttu-id="74307-253">신뢰할 수 있는 서버 인증을 구성하려면 먼저 감시자 노드 컴퓨터를 호스팅할 신뢰할 수 있는 응용 프로그램 풀을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-253">To configure Trusted Server authentication, you must first create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="74307-254">신뢰할 수 있는 응용 프로그램 풀을 만든 후 해당 감시자 노드에서 가상 트랜잭션을 신뢰할 수 있는 응용 프로그램으로 실행하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-254">After you've created the trusted application pool, you must then configure synthetic transactions on that watcher node to run as trusted applications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74307-255">신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버 2015의 일부로 실행하기 위한 신뢰할 수 있는 상태가 제공되지만 제품의 기본 제공 부분이 아닌 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="74307-255">A trusted application is an application that is given trusted status to run as part of Skype for Business Server 2015, but is not a built-in part of the product.</span></span> <span data-ttu-id="74307-256">신뢰 상태란 응용 프로그램이 실행될 때마다 응용 프로그램에 인증을 요청하지 않는 상태를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-256">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>
  
<span data-ttu-id="74307-257">신뢰할 수 있는 응용 프로그램 풀을 만들 경우 비즈니스용 Skype 서버 관리 셸을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-257">To create a trusted application pool, open the Skype for Business Server Management Shell and run a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> <span data-ttu-id="74307-258">이전 명령의 매개 변수에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-258">For details about the parameters in the preceding command, type the following from the Skype for Business Server Management Shell prompt:</span></span> 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

<span data-ttu-id="74307-259">신뢰할 수 있는 응용 프로그램 풀을 만들고 나면 **New-CsTrustedApplication** cmdlet 및 이와 유사한 명령을 사용하여 가상 트랜잭션을 신뢰할 수 있는 응용 프로그램으로 실행하도록 감시자 노드 컴퓨터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-259">After creating the trusted application pool, you can then configure the watcher node computer to run synthetic transactions as a trusted application by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

<span data-ttu-id="74307-260">이 명령이 완료되면 신뢰할 수 있는 응용 프로그램을 만들 때 **Enable-CsTopology** cmdlet을 실행하여 변경 내용이 적용될 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-260">When this command completes and the trusted application is created, you must then run the **Enable-CsTopology** cmdlet to make sure that the changes take effect:</span></span>
  
```PowerShell
Enable-CsTopology
```

<span data-ttu-id="74307-261">감시자 노드 컴퓨터 계정은 일부 가상 트랜잭션에 대해 CMS를 쿼리하는 기능을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-261">The watcher node computer account requires the ability to query CMS for some synthetic transactions.</span></span> <span data-ttu-id="74307-262">이 기능을 허용하려면 감시자 노드의 컴퓨터 계정을 RTCUniversalReadOnlyAdmins 보안 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-262">To allow this ability, add the computer account of the watcher node to the RTCUniversalReadOnlyAdmins security group.</span></span> <span data-ttu-id="74307-263">AD 복제가 발생한 후 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-263">Once AD replication has occurred, restart the computer.</span></span>
  
<span data-ttu-id="74307-264">신뢰할 수 있는 새 응용 프로그램이 만들어졌습니다. 비즈니스용 Skype 서버 관리 셸 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-264">To verify that the new trusted application has been created, type the following at the Skype for Business Server Management Shell prompt:</span></span>
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="74307-265">감시자 노드에서 기본 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="74307-265">Configure a Default Certificate on the Watcher Node</span></span>
<span data-ttu-id="74307-266"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="74307-266"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="74307-267">TrustedServer 인증을 사용하는 각 감시자 노드에는 비즈니스용 Skype 서버 배포 마법사를 사용하여 할당된 기본 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-267">Each watcher node that uses TrustedServer authentication must have a Default certificate assigned by using the Skype for Business Server Deployment wizard.</span></span> 
  
<span data-ttu-id="74307-268">기본 인증서를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-268">To assign a Default certificate:</span></span>
  
1. <span data-ttu-id="74307-269">시작, 모든 프로그램, 비즈니스용 Skype 서버 2015, 비즈니스용 Skype 서버 배포 마법사를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-269">Click Start, click All Programs, click Skype for Business Server 2015, and then click Skype for Business Server Deployment Wizard.</span></span> 
    
2. <span data-ttu-id="74307-270">비즈니스용 Skype 서버 배포 마법사에서 비즈니스용 Skype 서버 시스템 설치 또는 업데이트를 클릭한 다음 제목의 인증서 요청, 설치 또는 할당에서 실행을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-270">In the Skype for Business Server Deployment Wizard, click Install or Update Skype for Business Server System, and then click Run under the heading Request, Install, or Assign Certificate.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="74307-271">실행 단추가 해제된 경우 로컬 구성 저장소 설치 아래에서 먼저 실행을 클릭해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-271">If the Run button is disabled, you may need to first click Run under Install Local Configuration Store.</span></span> 
  
<span data-ttu-id="74307-272">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-272">Do one of the following:</span></span>
  
- <span data-ttu-id="74307-273">기본 인증서로 사용할 수 있는 인증서가 이미 있는 경우 인증서 마법사에서 기본값을 클릭한 다음 할당을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-273">If you already have a certificate that can be used as the Default certificate, click Default in the Certificate wizard, and then click Assign.</span></span> <span data-ttu-id="74307-274">인증서 지정 마법사의 단계에 따라 해당 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-274">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
- <span data-ttu-id="74307-275">기본 인증서를 사용하기 위해 인증서를 요청해야 하는 경우 요청을 클릭한 다음 인증서 요청 마법사의 단계에 따라 해당 인증서를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-275">If you need to request a certificate for use the Default certificate, click Request, and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="74307-276">웹 서버 인증서에 대한 기본값을 사용하면 기본 인증서로 지정할 수 있는 인증서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74307-276">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>
    
## <a name="install-and-configure-a-watcher-node"></a><span data-ttu-id="74307-277">감시자 노드 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="74307-277">Install and Configure a Watcher Node</span></span>
<span data-ttu-id="74307-278"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="74307-278"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="74307-279">감시자 노드 컴퓨터를 다시 시작하고 인증서를 구성한 후 이 파일을 실행해야 Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="74307-279">After you have restarted the watcher node computer and configured a certificate, you must run the file Watchernode.msi.</span></span> <span data-ttu-id="74307-280">Operations Manager Watchernode.msi 및 비즈니스용 Skype 서버 2015 핵심 구성 요소가 모두 설치된 모든 컴퓨터에서 이 파일을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-280">(You must run Watchernode.msi on any computer where both the Operations Manager agent files and the Skype for Business Server 2015 core components are installed.)</span></span> 
  
<span data-ttu-id="74307-281">감시자 노드를 설치하고 구성하려면</span><span class="sxs-lookup"><span data-stu-id="74307-281">To install and configure a watcher node:</span></span>
  
1. <span data-ttu-id="74307-282">시작, 모든 프로그램, 비즈니스용 Skype 서버 2015, 비즈니스용 Skype 서버 관리 셸을 클릭하여 비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-282">Open the Skype for Business Server Management Shell by clicking Start, clicking All Programs, clicking Skype for Business Server 2015, and then clicking Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="74307-283">관리 셸에서 다음 명령을 입력한 다음 Enter를 누를 수 있습니다(데이터베이스 복사본에 대한 실제 경로를 지정해야 Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="74307-283">In the Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> <span data-ttu-id="74307-284">명령 창에서 Watchernode.msi n을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-284">You can also run Watchernode.msi n from a command window.</span></span> <span data-ttu-id="74307-285">명령 창을 열려면 시작을 클릭하고 명령 프롬프트를 마우스 오른쪽 단추로 클릭한 후 관리자로 실행을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-285">To open a command window, click Start, right-click Command Prompt, and then click Run as administrator.</span></span> <span data-ttu-id="74307-286">명령 창이 열리면 위의 2단계에 표시된 동일한 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-286">When the command window opens, type the same command shown in step 2, above.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="74307-287">위의 명령에서 이름/값 쌍 Authentication=TrustedServer는 대/소문자 구분을 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-287">In the preceding command, the name/value pair Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="74307-288">표시된 그대로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-288">It must be typed exactly as shown.</span></span> <span data-ttu-id="74307-289">예를 들어 다음 명령은 올바른 문자 대/소문자를 사용하지 못하기 때문에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-289">For example, this command will fail because it does not use the correct letter casing:</span></span> 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

<span data-ttu-id="74307-290">TrustedServer 모드는 경계 네트워크 내부에 있는 컴퓨터에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-290">TrustedServer mode can be used only with computers that lie inside the perimeter network.</span></span> <span data-ttu-id="74307-291">감시자 노드가 TrustedServer 모드에서 실행되는 경우 관리자는 컴퓨터에서 테스트 사용자 암호를 유지 관리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-291">When a watcher node runs in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a><span data-ttu-id="74307-292">협상을 사용하도록 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="74307-292">Configure a Watcher Node to Use Negotiate</span></span>
<span data-ttu-id="74307-293"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="74307-293"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="74307-294">감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 가상 트랜잭션을 실행하도록 감시자 노드를 구성하려면 약간 다른 절차를 따라야 합니다. 특히 신뢰할 수 있는 응용 프로그램 풀 또는 신뢰할 수 있는 응용 프로그램을 만들면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74307-294">If your watcher node computer lies outside the perimeter network then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions: in particular, you should not create a trusted application pool or a trusted application.</span></span> <span data-ttu-id="74307-295">즉, 다음 두 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-295">That means that you will need to complete the next two tasks.</span></span>
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="74307-296">RTC Local Read-Only Administrators 그룹의 구성원 업데이트</span><span class="sxs-lookup"><span data-stu-id="74307-296">Update Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="74307-297">감시자 노드가 경계 네트워크 외부에 있는 경우 감시자 노드에서 다음 절차를 완료하여 감시자 노드 컴퓨터의 RTC 로컬 읽기 전용 Administrators 그룹에 네트워크 서비스 계정을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-297">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer by completing the following procedure on the watcher node:</span></span>
  
1. <span data-ttu-id="74307-298">시작을 클릭하고 컴퓨터를 마우스 오른쪽 단추로 클릭한 다음 관리를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-298">Click Start, right-click Computer, and then click Manage.</span></span>
    
2. <span data-ttu-id="74307-299">서버 관리자에서 구성, 로컬 사용자 및 그룹을 차례로 확장한 다음 그룹을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-299">In Server Manager, expand Configuration, expand Local Users and Groups, and then click Groups.</span></span>
    
3. <span data-ttu-id="74307-300">그룹 창에서 RTC Local Read-only Administrators를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-300">In the Groups pane, double-click RTC Local Read-only Administrators.</span></span>
    
4. <span data-ttu-id="74307-301">RTC Local Read-only Administrators 속성 대화 상자에서 추가를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-301">In the RTC Local Read-only Administrators Properties dialog box, click Add.</span></span>
    
5. <span data-ttu-id="74307-302">사용자, 컴퓨터, 서비스 계정 또는 그룹 선택 대화 상자에서 위치를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-302">In the Select Users, Computers, Service Accounts, or Groups dialog box, click Locations.</span></span>
    
6. <span data-ttu-id="74307-303">위치 대화 상자에서 감시자 노드 컴퓨터의 이름을 선택하고 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-303">In the Locations dialog box, select the name of the watcher node computer, and then click OK.</span></span>
    
7. <span data-ttu-id="74307-304">선택할 개체 이름을 입력하십시오. 상자에 네트워크 서비스를 입력하고 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-304">In the Enter object names to select box, type Network Service, and then click OK.</span></span>
    
8. <span data-ttu-id="74307-305">RTC Local Read-only Administrators 속성 대화 상자에서 확인를 클릭하고 서버 관리자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-305">In the RTC Local Read-only Administrators Properties dialog box, click OK, and then close Server Manager.</span></span>
    
9. <span data-ttu-id="74307-306">감시자 노드 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-306">Restart the watcher node computer.</span></span>
    
### <a name="install-the-watcher-node-configuration-files"></a><span data-ttu-id="74307-307">감시자 노드 구성 파일 설치</span><span class="sxs-lookup"><span data-stu-id="74307-307">Install the Watcher Node Configuration Files</span></span>

<span data-ttu-id="74307-308">다음 단계에서는 다음을 통해 파일을 Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="74307-308">Your next step is to run the file Watchernode.msi:</span></span> 
  
1. <span data-ttu-id="74307-309">Microsoft 비즈니스용 Skype 서버 2015 관리 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-309">Open the Microsoft Skype for Business Server 2015 Management Shell.</span></span> <span data-ttu-id="74307-310">시작, 모든 프로그램, Microsoft 비즈니스용 Skype 서버 2015를 클릭한 다음 비즈니스용 Skype 서버 관리 셸을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-310">Click Start, click All Programs, click Microsoft Skype for Business Server 2015, and then click Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="74307-311">비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 누르고(데이터베이스 복사본에 대한 실제 경로를 지정해야 Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="74307-311">In Skype for Business Server Management Shell, type the following command, and then press ENTER (be sure to specify the actual path to your copy of Watchernode.msi):</span></span>
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> <span data-ttu-id="74307-312">앞서 설명한 Watchernode.msi 창에서 실행될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74307-312">As mentioned previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="74307-313">명령 창을 열려면 **시작** 을 클릭하고 **명령 프롬프트** 를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-313">To open a command window, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="74307-314">명령 창이 열리면 위의 2단계에 표시된 동일한 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-314">When the command window opens, type the same command shown in step 2, above.</span></span> 
  
<span data-ttu-id="74307-315">감시자 노드를 신뢰할 수 있는 응용 프로그램 풀로 설정할 수 없는 경우에는 항상 협상 모드가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74307-315">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="74307-316">이 모드에서는 관리자가 감시자 노드에 대한 테스트 사용자 암호를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74307-316">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>
  

