---
title: 감시자 노드 설치 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype Server 가상 거래에 대 한 감시자 노드를 설치 하 고 구성 합니다.'
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816097"
---
# <a name="install-and-configure-watcher-nodes"></a><span data-ttu-id="d2c2a-103">감시자 노드 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="d2c2a-103">Install and configure watcher nodes</span></span>
 
<span data-ttu-id="d2c2a-104">**요약:** 비즈니스용 Skype Server 가상 거래에 대 한 감시자 노드를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-104">**Summary:** Install and configure watcher nodes for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="d2c2a-105">감시자 노드는 비즈니스용 Skype Server 가상 트랜잭션을 정기적으로 실행 하는 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-105">Watcher nodes are computers that periodically run Skype for Business Server synthetic transactions.</span></span> <span data-ttu-id="d2c2a-106">가상 트랜잭션은 로그인 또는 exchange 인스턴트 메시지와 같은 주요 사용자 시나리오가 예상 대로 작동 하는지 확인 하는 Windows PowerShell cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-106">Synthetic transactions are Windows PowerShell cmdlets that verify that key user scenarios, such as the ability to sign in or to exchange instant messages, are working as expected.</span></span> <span data-ttu-id="d2c2a-107">비즈니스용 Skype Server 2015의 경우 System Center Operations Manager는 다음 표에 표시 된 가상 트랜잭션을 실행할 수 있으며, 다음과 같은 세 가지 가상 트랜잭션 형식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-107">For Skype for Business Server 2015, System Center Operations Manager can run the synthetic transactions shown in the following table, which includes three synthetic transaction types:</span></span>
  
- <span data-ttu-id="d2c2a-108">**기본** 감시자 노드가 기본적으로 실행 하는 가상 트랜잭션입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-108">**Default** Synthetic transactions that a watcher node runs by default.</span></span> <span data-ttu-id="d2c2a-109">새 감시자 노드를 만들 때 노드가 실행 될 가상 트랜잭션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-109">When you create a new watcher node, you can specify which synthetic transactions that node will run.</span></span> <span data-ttu-id="d2c2a-110">(이는 CsWatcherNodeConfiguration cmdlet에 사용 되는 테스트 매개 변수의 목적입니다.) 감시자 노드를 만들 때 테스트 매개 변수를 사용 하지 않으면 모든 기본 가상 트랜잭션이 자동으로 실행 되 고 기본이 아닌 가상 트랜잭션은 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-110">(That's the purpose of the Tests parameter used by the New-CsWatcherNodeConfiguration cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="d2c2a-111">즉, 예를 들어, 감시자 노드는 테스트-CsAddressBookService 테스트를 실행 하도록 구성 되지만 테스트 CsExumConnectivity 테스트를 실행 하도록 구성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-111">This means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>
    
- <span data-ttu-id="d2c2a-112">**비기본** 감시자 노드가 기본적으로 실행 되지 않도록 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-112">**Non-default** Tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="d2c2a-113">(자세한 내용은 기본 형식에 대 한 설명을 참조 하세요.) 그러나 감시자 노드를 사용 하 여 기본이 아닌 가상 트랜잭션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-113">(For details, see the description of the Default type.) However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="d2c2a-114">CsWatcherNodeConfiguration cmdlet을 사용 하 여 감시자 노드를 만들거나, 감시자 노드가 만들어진 후에는 언제 든 지이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-114">You can do this when you create the watcher node (by using the New-CsWatcherNodeConfiguration cmdlet), or any time after the watcher node has been created.</span></span> <span data-ttu-id="d2c2a-115">대부분의 비 기본 가상 트랜잭션에는 추가 설정 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-115">Note that many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="d2c2a-116">이러한 단계에 대 한 자세한 내용은 [종합 거래에 대 한 특별 설정 지침](test-users-and-settings.md#special_synthetictrans)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-116">For more details about these steps, see [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).</span></span>
    
- <span data-ttu-id="d2c2a-117">**연장** 특별 한 유형의 기본이 아닌 가상 트랜잭션입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-117">**Extended** A special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="d2c2a-118">다른 가상 트랜잭션과 달리 확장 테스트는 각 단계에서 여러 번 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-118">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="d2c2a-119">이 기능은 풀의 여러 공공 PSTN (교환 전화 네트워크) 음성 경로와 같은 동작을 확인할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-119">This is useful when verifying behavior, such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="d2c2a-120">확장 테스트의 여러 인스턴스를 감시자 노드에 추가 하 여 간단 하 게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-120">You can configure this simply by adding multiple instances of an extended test to a watcher node.</span></span>
    
<span data-ttu-id="d2c2a-121">다른 가상 트랜잭션을 감시자 노드에 추가 하는 프로세스에 대 한 자세한 내용은 [감시자 노드를 구성 하 여 가상 트랜잭션을 실행 하](watcher-nodes.md#enable_synthetic_trans)는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-121">For details about the process for adding other synthetic transactions to a watcher node, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span> <span data-ttu-id="d2c2a-122">비즈니스용 Skype Server Management Shell을 사용 하 여 감시자 노드에서 가상 트랜잭션을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-122">You can also use Skype for Business Server Management Shell to remove synthetic transactions from a watcher node.</span></span>
  
<span data-ttu-id="d2c2a-123">감시자 노드에 사용할 수 있는 가상 트랜잭션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-123">The synthetic transactions available to watcher nodes include the following:</span></span>
  
|<span data-ttu-id="d2c2a-124">**Cmdlet 이름 (테스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="d2c2a-124">**Cmdlet Name (Test Name)**</span></span>|<span data-ttu-id="d2c2a-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="d2c2a-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d2c2a-126">ABS (테스트-CsAddressBookService)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-126">Test-CsAddressBookService (ABS)</span></span>  <br/> |<span data-ttu-id="d2c2a-127">사용자가 대화 상대 목록에 없는 사용자를 조회할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-127">Confirms that users are able to look up users who aren't in their contact list.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-128">테스트-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-128">Test-CsAddressBookWebQuery (ABWQ)</span></span>  <br/> |<span data-ttu-id="d2c2a-129">사용자가 HTTP를 통해 대화 상대 목록에 없는 사용자를 조회할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-129">Confirms that users are able to look up users who aren't in their contact list via HTTP.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-130">테스트-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-130">Test-CsAVConference (AvConference)</span></span>  <br/> |<span data-ttu-id="d2c2a-131">사용자가 음성/영상 회의를 만들고 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-131">Confirms that users are able to create and participate in an audio/video conference.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-132">테스트-CsGroupIM (IM 회의)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-132">Test-CsGroupIM (IM Conferencing)</span></span>  <br/> |<span data-ttu-id="d2c2a-133">사용자가 회의 중에 인스턴트 메시지를 보내고 세 명 이상의 사용자와 인스턴트 메시지 대화에 참여할 수 있음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-133">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-134">Test-CsIM (P2P IM)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-134">Test-CsIM (P2P IM)</span></span>  <br/> |<span data-ttu-id="d2c2a-135">사용자가 피어 투 피어 인스턴트 메시지를 보낼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-135">Confirms that users are able to send peer-to-peer instant messages.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-136">CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-136">Test-CsP2PAV (P2PAV)</span></span>  <br/> |<span data-ttu-id="d2c2a-137">사용자가 피어 투 피어 오디오 통화를 배치할 수 있는지 확인 합니다 (신호 전용).</span><span class="sxs-lookup"><span data-stu-id="d2c2a-137">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span>  <br/> |
|<span data-ttu-id="d2c2a-138">테스트-CsPresence 현재 상태)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-138">Test-CsPresence (Presence)</span></span>  <br/> |<span data-ttu-id="d2c2a-139">사용자가 다른 사용자의 현재 상태를 볼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-139">Confirms that users are able to view other users' presence.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-140">테스트-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-140">Test-CsRegistration (Registration)</span></span>  <br/> |<span data-ttu-id="d2c2a-141">사용자가 비즈니스용 Skype에 로그인 할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-141">Confirms that users are able sign in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-142">테스트-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-142">Test-CsPstnPeerToPeerCall (PSTN)</span></span>  <br/> |<span data-ttu-id="d2c2a-143">사용자가 엔터프라이즈 이외의 사용자와 전화를 걸고 받을 수 있는지 확인 합니다 (PSTN 번호).</span><span class="sxs-lookup"><span data-stu-id="d2c2a-143">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span>  <br/> |
|<span data-ttu-id="d2c2a-144">As컨퍼런스 (테스트-CsASConference)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-144">Test-CsASConference (ASConference)</span></span>  <br/> |<span data-ttu-id="d2c2a-145">사용자가 응용 프로그램 공유 회의를 만들고 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-145">Confirms that users are able to create and participate in an application sharing conference.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-146">CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-146">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span>  <br/> |<span data-ttu-id="d2c2a-147">오디오 비디오에 지 서버가 피어 투 피어 통화 및 전화 회의 통화에 대 한 연결을 수락할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-147">Confirms that the Audio Video Edge servers are able to accept connections for peer-to- peer calls and conference calls.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-148">CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-148">Test-CsDataConference (DataConference)</span></span>  <br/> |<span data-ttu-id="d2c2a-149">사용자가 데이터 공동 작업 회의 (예: 화이트 보드 및 설문 등의 활동을 포함 하는 온라인 모임)에 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-149">Confirms that users can participate in a data collaboration conference (an online meeting that includes activities such as whiteboards and polls).</span></span>  <br/> |
|<span data-ttu-id="d2c2a-150">CsDialinConferencing (DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-150">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="d2c2a-151">사용자에 게 전화를 걸 수 있는지 확인 하 고 회의에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-151">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-152">CsDialinConferencing (DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-152">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="d2c2a-153">사용자에 게 전화를 걸 수 있는지 확인 하 고 회의에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-153">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-154">CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-154">Test-CsExumConnectivity (ExumConnectivity)</span></span>  <br/> |<span data-ttu-id="d2c2a-155">사용자가 UM (통합 메시징)에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-155">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span>  <br/> |
|<span data-ttu-id="d2c2a-156">테스트-CsGroupIM-TestJoinLauncher 관리자 (Join시작 관리자)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-156">Test-CsGroupIM -TestJoinLauncher (JoinLauncher)</span></span>  <br/> |<span data-ttu-id="d2c2a-157">사용자가 예약 된 모임 (웹 주소 링크)을 만들고 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-157">Confirms that users are able to create and join scheduled meetings (by a web address link).</span></span>  <br/> |
|<span data-ttu-id="d2c2a-158">CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-158">Test-CsMCXP2PIM (MCXP2PIM)</span></span>  <br/> |<span data-ttu-id="d2c2a-159">모바일 장치 사용자가 인스턴트 메시지를 등록 하 고 보낼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-159">Confirms that mobile device users are able to register and send instant messages.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-160">CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-160">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span></span>  <br/> |<span data-ttu-id="d2c2a-161">비디오 Interop 서버가 켜져 있는지 확인 하 고 비디오 SIP 트렁크를 통해 들어오는 연결을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-161">Confirms that Video Interop Server is up and can handle incoming connections over a video SIP trunk.</span></span>  <br/> <span data-ttu-id="d2c2a-162">**참고:** 이전 모바일 클라이언트에 대 한 MCX 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-162">**Note:** MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> |
|<span data-ttu-id="d2c2a-163">CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-163">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span>  <br/> |<span data-ttu-id="d2c2a-164">사용자가 영구 채팅 서비스를 사용 하 여 메시지를 교환할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-164">Confirms that users can exchange messages by using the Persistent Chat service.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-165">CsUcwaConference (UcwaConference)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-165">Test-CsUcwaConference (UcwaConference)</span></span>  <br/> |<span data-ttu-id="d2c2a-166">사용자가 웹을 통해 회의에 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-166">Confirms that users can join conferences via the web.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-167">CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-167">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span>  <br/> |<span data-ttu-id="d2c2a-168">통합 된 대화 상대 저장소를 통해 사용자의 연락처에 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-168">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="d2c2a-169">통합 된 연락처 저장소는 사용자가 비즈니스용 Skype 서버 2015, Outlook messaging 및 공동 작업 클라이언트, Outlook Web Access를 사용 하 여 액세스할 수 있는 단일 연락처 집합을 유지 관리 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-169">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Skype for Business Server 2015, Outlook messaging and collaboration client, and/or Outlook Web Access.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-170">테스트-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-170">Test-CsXmppIM (XmppIM)</span></span>  <br/> |<span data-ttu-id="d2c2a-171">XMPP (확장 가능 메시지 및 현재 상태 프로토콜) 게이트웨이를 통해 인스턴트 메시지를 보낼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-171">Confirms that an instant message can be sent across the Extensible Messaging and Presence Protocol (XMPP) gateway.</span></span>  <br/> <span data-ttu-id="d2c2a-172">XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-172">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span>  |

<span data-ttu-id="d2c2a-173">System Center Operations Manager를 사용 하기 위해 감시자 노드를 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-173">You do not need to install watcher nodes to use System Center Operations Manager.</span></span> <span data-ttu-id="d2c2a-174">이러한 노드를 설치 하지 않은 경우에도 문제가 발생할 때마다 비즈니스용 Skype 서버 2015 구성 요소에서 실시간 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-174">If you do not install these nodes, you can still get real-time alerts from Skype for Business Server 2015 components whenever an issue occurs.</span></span> <span data-ttu-id="d2c2a-175">(구성 요소 및 사용자 관리 팩은 감시자 노드를 사용 하지 않습니다.) 그러나 활성 모니터링 관리 팩을 사용 하 여 종단 간 시나리오를 모니터링 하려면 감시자 노드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-175">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2c2a-176">또한 관리자는 Operations Manager를 사용 하거나 설치 하지 않고도 수동으로 가상 트랜잭션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-176">Administrators can also run synthetic transactions manually, without using or installing Operations Manager.</span></span> <span data-ttu-id="d2c2a-177">비즈니스용 Skype Server 배포의 크기에 따라 가상 트랜잭션은 많은 양의 컴퓨터 메모리와 프로세서 시간을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-177">Depending on the size of your Skype for Business Server deployment, synthetic transactions can use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="d2c2a-178">이 때문에 전용 컴퓨터를 감시자 노드로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-178">Because of this, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="d2c2a-179">예를 들어 감시자 노드 역할을 하는 비즈니스용 Skype 서버 프런트 엔드 서버를 구성 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-179">For example, you should not configure a Skype for Business Server Front End Server to act as a watcher node.</span></span> <span data-ttu-id="d2c2a-180">감시자 노드는 비즈니스용 Skype 서버 토폴로지에 있는 다른 컴퓨터와 동일한 기본 하드웨어 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-180">Watcher nodes should meet the same basic hardware requirements as any other computer in your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d2c2a-181">Lync Server 2013 및 비즈니스용 Skype server 2015의 핵심 시스템 파일은 동일한 컴퓨터에 설치할 수 없기 때문에 레거시 Lync Server 2013 감시자 노드는 비즈니스용 Skype Server 2015 감시자 노드와 같은 컴퓨터에서 collocated 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-181">A legacy Lync Server 2013 watcher node cannot be collocated on the same machine as a Skype for Business Server 2015 watcher node because the core system files for Lync Server 2013 and Skype for Business Server 2015 cannot be installed on the same computer.</span></span> <span data-ttu-id="d2c2a-182">그러나 비즈니스용 Skype 서버 2015 감시자 노드는 비즈니스용 Skype Server 2015 및 Lync Server 2013을 동시에 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-182">However, Skype for Business Server 2015 watcher nodes can simultaneously monitor Skype for Business Server 2015 and Lync Server 2013.</span></span> <span data-ttu-id="d2c2a-183">기본 가상 트랜잭션은 두 제품 버전 모두에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-183">Default synthetic transactions are supported for both product versions.</span></span> 
  
<span data-ttu-id="d2c2a-184">Lync Server 2013 감시자 노드는 엔터프라이즈 내부 또는 외부에 배포 되어 확인에 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-184">Lync Server 2013 watcher nodes may be deployed inside or outside an enterprise to help verify:</span></span>
  
- <span data-ttu-id="d2c2a-185">엔터프라이즈 내부의 사용자에 대 한 풀에 대 한 연결.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-185">Connectivity to pools for users inside the enterprise.</span></span>
    
- <span data-ttu-id="d2c2a-186">기업 외부에서 작업 하는 원격 사용자의 경계 네트워크를 통한 연결.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-186">Connectivity through perimeter networks for remote users working outside the enterprise.</span></span>
    
- <span data-ttu-id="d2c2a-187">지사 기기에 대 한 연결.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-187">Connectivity to branch office appliances.</span></span>
    
- <span data-ttu-id="d2c2a-188">기업 및 경계 네트워크 내부의 Lync Server 2013 연결</span><span class="sxs-lookup"><span data-stu-id="d2c2a-188">Connectivity to Lync Server 2013 inside the enterprise and through perimeter networks.</span></span>
    
<span data-ttu-id="d2c2a-189">관리를 간소화 하기 위해 엔터프라이즈 내부 및 외부에서 다양 한 인증 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-189">To help simplify administration, different authentication options are available for inside and outside of the enterprise.</span></span> <span data-ttu-id="d2c2a-190">자세한 내용은 [가상 트랜잭션을 실행 하도록 감시자 노드 구성을](watcher-nodes.md#enable_synthetic_trans)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-190">For details, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span>
  
<span data-ttu-id="d2c2a-191">컴퓨터가 감시자 노드로 작동 하도록 구성 하려면 먼저 다음 필수 구성 요소를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-191">To configure a computer to act as a watcher node, you must first complete the following prerequisites:</span></span> 
  
- <span data-ttu-id="d2c2a-192">System Center Operations Manager를 설치 하 고 비즈니스용 Skype 서버 2015 관리 팩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-192">Install System Center Operations Manager and import the Skype for Business Server 2015 management packs.</span></span> <span data-ttu-id="d2c2a-193">또한 먼저 감시자 노드 컴퓨터가 비즈니스용 Skype 서버 2015을 설치 하기 위한 모든 선행 조건을 충족 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-193">You must also first verify that the watcher node computer meets all prerequisites for installing Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="d2c2a-194">감시자 노드 컴퓨터에 다음 항목을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-194">Install the following items on the watcher node computer:</span></span>
    
  - <span data-ttu-id="d2c2a-195">전체 버전의 .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d2c2a-195">The full version of .NET Framework 4.5</span></span>
    
  - <span data-ttu-id="d2c2a-196">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="d2c2a-196">Windows Identity Foundation</span></span>
    
  - <span data-ttu-id="d2c2a-197">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="d2c2a-197">Windows PowerShell 3.0</span></span>
    
<span data-ttu-id="d2c2a-198">필수 조건이 충족 되 면 다음 단계에 따라 감시자 노드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-198">After the prerequisites are met, you can configure the watcher node by following these steps:</span></span>
  
1. <span data-ttu-id="d2c2a-199">감시자 노드 컴퓨터에 비즈니스용 Skype 서버 2015 core 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-199">Install the Skype for Business Server 2015 core files on the watcher node computer.</span></span>
    
2. <span data-ttu-id="d2c2a-200">감시자 노드 컴퓨터에 System Center Operations Manager 에이전트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-200">Install System Center Operations Manager agent on the watcher node computer.</span></span>
    
3. <span data-ttu-id="d2c2a-201">Watchernode 실행 파일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-201">Run the Watchernode.msi executable file.</span></span>
    
4. <span data-ttu-id="d2c2a-202">**새 CsWatcherNodeConfiguration** cmdlet을 사용 하 여 감시자 노드에서 사용할 테스트 사용자 계정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-202">Use the **New-CsWatcherNodeConfiguration** cmdlet to configure test user accounts to be employed by the watcher node.</span></span>
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a><span data-ttu-id="d2c2a-203">비즈니스용 Skype Server 2015 Core 파일 및 RTCLocal 데이터베이스 설치</span><span class="sxs-lookup"><span data-stu-id="d2c2a-203">Install the Skype for Business Server 2015 Core Files and the RTCLocal Database</span></span>

<span data-ttu-id="d2c2a-204">컴퓨터에 비즈니스용 Skype 서버 2015 core 파일을 설치 하려면 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-204">To install the Skype for Business Server 2015 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="d2c2a-205">RTCLocal 데이터베이스는 코어 파일을 설치할 때 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-205">The RTCLocal database will automatically be installed when you install the core files.</span></span> <span data-ttu-id="d2c2a-206">감시자 노드에 SQL Server를 설치 하지 않아도 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-206">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="d2c2a-207">SQL Server Express가 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-207">SQL Server Express will be automatically installed.</span></span>
  
<span data-ttu-id="d2c2a-208">비즈니스용 Skype 서버 2015 core 파일 및 RTCLocal 데이터베이스를 설치 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-208">To install the Skype for Business Server 2015 core files and the RTCLocal database:</span></span>
  
1. <span data-ttu-id="d2c2a-209">감시자 노드 컴퓨터에서 시작, 모든 프로그램, 액세서리를 차례로 클릭 하 고 명령 프롬프트를 마우스 오른쪽 단추로 클릭 한 다음 관리자 권한으로 실행을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-209">On the watcher node computer, click Start, click All Programs, click Accessories, right-click Command Prompt, and then click Run as administrator.</span></span>
    
2. <span data-ttu-id="d2c2a-210">콘솔 창에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-210">In the console window, type the following command and press ENTER.</span></span> <span data-ttu-id="d2c2a-211">비즈니스용 Skype Server 설치 파일에 대 한 적절 한 경로를 입력 해야 합니다. D:\Setup.exe/BootstrapLocalMgmtTo 주요 비즈니스용 Skype 서버 구성 요소가 설치 되어 있는지 확인 하 고, **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype server Management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-211">Be sure to enter the appropriate path to your Skype for Business Server setup files: D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype for Business Server components are successfully installed, click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Management Shell**.</span></span> <span data-ttu-id="d2c2a-212">비즈니스용 Skype 서버 관리 셸에서 다음 Windows PowerShell 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-212">In the Skype for Business Server Management Shell, type the following Windows PowerShell command and press ENTER:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> <span data-ttu-id="d2c2a-213">이 명령을 처음 실행할 때 감시자 노드 컴퓨터를 아직 구성 하지 않았기 때문에 데이터가 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-213">The first time you run this command, no data will be returned because you have not yet configured any watcher node computers.</span></span> <span data-ttu-id="d2c2a-214">오류가 반환 되지 않고 명령이 실행 되는 경우 비즈니스용 Skype 서버 설정이 성공적으로 완료 되었다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-214">If the command runs without returning an error, you can assume that the Skype for Business Server setup completed successfully.</span></span> 
  
<span data-ttu-id="d2c2a-215">감시자 노드 컴퓨터가 주변 네트워크 내에 있는 경우 다음 명령을 실행 하 여 비즈니스용 Skype Server 2015의 설치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-215">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Skype for Business Server 2015:</span></span>
  
<span data-ttu-id="d2c2a-216">CsPinPolicyYou는 조직에서 사용 하도록 구성 된 PIN 정책의 수에 따라 다음과 같은 정보를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-216">Get-CsPinPolicyYou will receive information similar to this, depending on the number of PIN policies configured for use in your organization:</span></span>
  
<span data-ttu-id="d2c2a-217">Id: 전역</span><span class="sxs-lookup"><span data-stu-id="d2c2a-217">Identity : Global</span></span>
  
<span data-ttu-id="d2c2a-218">설명은</span><span class="sxs-lookup"><span data-stu-id="d2c2a-218">Description :</span></span>
  
<span data-ttu-id="d2c2a-219">MinPasswordLength: 5</span><span class="sxs-lookup"><span data-stu-id="d2c2a-219">MinPasswordLength : 5</span></span>
  
<span data-ttu-id="d2c2a-220">PINHistoryCount: 0</span><span class="sxs-lookup"><span data-stu-id="d2c2a-220">PINHistoryCount : 0</span></span>
  
<span data-ttu-id="d2c2a-221">AllowCommonPatterns: False</span><span class="sxs-lookup"><span data-stu-id="d2c2a-221">AllowCommonPatterns : False</span></span>
  
<span data-ttu-id="d2c2a-222">PINLifetime: 0</span><span class="sxs-lookup"><span data-stu-id="d2c2a-222">PINLifetime : 0</span></span>
  
<span data-ttu-id="d2c2a-223">MaximumLogonAttempts:</span><span class="sxs-lookup"><span data-stu-id="d2c2a-223">MaximumLogonAttempts :</span></span>
  
<span data-ttu-id="d2c2a-224">PIN 정책에 대 한 정보가 표시 되는 경우 핵심 구성 요소가 성공적으로 설치 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-224">If you see information about your PIN policies, the core components have been successfully installed.</span></span>
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a><span data-ttu-id="d2c2a-225">감시자 노드에 Operation Manager 에이전트 파일 설치</span><span class="sxs-lookup"><span data-stu-id="d2c2a-225">Install the Operation Manager Agent Files on a Watcher Node</span></span>

<span data-ttu-id="d2c2a-226">비즈니스용 Skype 서버 설정과 유사 구성 요소 알림을 사용 하는 경우 비즈니스용 Skype 서버 2015 감시자 노드에는 System Center Operations Manager 에이전트 파일이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-226">Similar to Skype for Business Server setup for reporting component alerts, a Skype for Business Server 2015 watcher node requires System Center Operations Manager agent files to be installed.</span></span> <span data-ttu-id="d2c2a-227">이를 통해 가상 트랜잭션을 실행 하 고 알림을 System Center Operations Manager 루트 관리 서버에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-227">This enables the synthetic transactions to be run and alerts to be reported to the System Center Operations Manager Root Management Server.</span></span>
  
<span data-ttu-id="d2c2a-228">에이전트 파일을 설치 하려면 [모니터링할 비즈니스용 Skype 서버 구성](configure-computers-to-monitor.md)에 나열 된 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-228">To install the agent files, follow the procedures listed in [Configure the Skype for Business Server computers that will be monitored](configure-computers-to-monitor.md).</span></span>
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a><span data-ttu-id="d2c2a-229">가상 트랜잭션을 실행 하도록 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="d2c2a-229">Configure a Watcher Node to Run Synthetic Transactions</span></span>
<span data-ttu-id="d2c2a-230"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="d2c2a-230"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="d2c2a-231">System Center Operations Manager 에이전트 파일을 설치한 후에는 감시자 노드 자체를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-231">After the System Center Operations Manager agent files have been installed, you must configure the watcher node itself.</span></span> <span data-ttu-id="d2c2a-232">이 작업을 수행 하기 위해 수행 하는 단계는 감시자 노드 컴퓨터가 경계 네트워크 내에 있는지 아니면 경계 네트워크 외부에 있든에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-232">The steps you take to do this will vary, depending on whether your watcher node computer is inside your perimeter network or outside your perimeter network.</span></span> 
  
<span data-ttu-id="d2c2a-233">감시자 노드를 구성할 때는 해당 노드에서 사용할 인증 방법의 종류도 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-233">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="d2c2a-234">비즈니스용 Skype 서버 2015에서는 신뢰 된 서버 또는 자격 증명 인증 이라는 두 가지 인증 방법 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-234">Skype for Business Server 2015 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="d2c2a-235">다음 표에서는 이러한 두 메서드의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-235">The following table shows the differences between these two methods:</span></span>
  
||<span data-ttu-id="d2c2a-236">**설명**</span><span class="sxs-lookup"><span data-stu-id="d2c2a-236">**Description**</span></span>|<span data-ttu-id="d2c2a-237">**지원 되는 위치**</span><span class="sxs-lookup"><span data-stu-id="d2c2a-237">**Locations supported**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d2c2a-238">(가) 서버</span><span class="sxs-lookup"><span data-stu-id="d2c2a-238">TrustedServer</span></span>  <br/> |<span data-ttu-id="d2c2a-239">인증서를 사용 하 여 내부 서버를 가장 하 고 인증 챌린지를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-239">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span>  <br/> <span data-ttu-id="d2c2a-240">각 감시자 노드에 대 한 많은 사용자 암호 대신 단일 인증서를 관리 하려는 관리자에 게 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-240">Useful for administrators who prefer to manage a single certificate, instead of many user passwords on each watcher node.</span></span>  <br/> |<span data-ttu-id="d2c2a-241">엔터프라이즈 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-241">Inside the enterprise.</span></span>  <br/> <span data-ttu-id="d2c2a-242">이 메서드를 사용 하는 경우 감시자 노드는 모니터링 하는 풀과 동일한 도메인에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-242">With this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="d2c2a-243">감시자 노드와 풀이 서로 다른 도메인에 있는 경우 자격 증명 인증을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-243">If the watcher node and the pools are in different domains, use Credential Authentication instead.</span></span>  <br/> |
|<span data-ttu-id="d2c2a-244">협상</span><span class="sxs-lookup"><span data-stu-id="d2c2a-244">Negotiate</span></span>  <br/> |<span data-ttu-id="d2c2a-245">각 감시자 노드의 Windows 자격 증명 관리자에 사용자 이름 및 암호를 안전 하 게 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-245">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span>  <br/> <span data-ttu-id="d2c2a-246">이 모드는 더 많은 암호 관리가 필요 하지만 엔터프라이즈 외부의 감시자 노드에는 유일한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-246">This mode requires more password management, but is the only option for watcher nodes outside the enterprise.</span></span> <span data-ttu-id="d2c2a-247">이러한 감시자 노드는 인증을 위해 신뢰할 수 있는 끝점으로 취급할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-247">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span>  <br/> |<span data-ttu-id="d2c2a-248">기업 외부</span><span class="sxs-lookup"><span data-stu-id="d2c2a-248">Outside the enterprise.</span></span>  <br/> <span data-ttu-id="d2c2a-249">엔터프라이즈 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-249">Inside the enterprise.</span></span>  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a><span data-ttu-id="d2c2a-250">신뢰 된 서버 인증을 사용 하도록 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="d2c2a-250">Configure a Watcher Node to Use Trusted Server Authentication</span></span>
<span data-ttu-id="d2c2a-251"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="d2c2a-251"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="d2c2a-252">감시자 노드 컴퓨터가 경계 네트워크 내에 있는 경우 신뢰 된 서버 인증을 사용 하면 다양 한 사용자 계정 암호를 사용 하는 대신 단일 인증서를 유지 관리 하 여 관리 작업을 대폭 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-252">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration tasks by maintaining a single certificate, rather than using numerous user account passwords.</span></span>
  
<span data-ttu-id="d2c2a-253">신뢰 된 서버 인증을 구성 하려면 먼저 신뢰할 수 있는 응용 프로그램 풀을 만들어 감시자 노드 컴퓨터를 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-253">To configure Trusted Server authentication, you must first create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="d2c2a-254">신뢰할 수 있는 응용 프로그램 풀을 만든 후에는 신뢰할 수 있는 응용 프로그램으로 실행할 감시자 노드에서 가상 트랜잭션을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-254">After you've created the trusted application pool, you must then configure synthetic transactions on that watcher node to run as trusted applications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2c2a-255">신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype Server 2015의 일부로 실행할 신뢰할 수 있는 상태를 지정 하는 응용 프로그램 이지만 제품의 기본 제공 부분이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-255">A trusted application is an application that is given trusted status to run as part of Skype for Business Server 2015, but is not a built-in part of the product.</span></span> <span data-ttu-id="d2c2a-256">신뢰할 수 있는 상태는 응용 프로그램이 실행 될 때마다 인증에 대해 challenge 되지 않는다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-256">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>
  
<span data-ttu-id="d2c2a-257">신뢰할 수 있는 응용 프로그램 풀을 만들려면 비즈니스용 Skype Server Management Shell을 열고 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-257">To create a trusted application pool, open the Skype for Business Server Management Shell and run a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> <span data-ttu-id="d2c2a-258">이전 명령의 매개 변수에 대 한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-258">For details about the parameters in the preceding command, type the following from the Skype for Business Server Management Shell prompt:</span></span> 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

<span data-ttu-id="d2c2a-259">신뢰할 수 있는 응용 프로그램 풀을 만든 후에는 **새 CsTrustedApplication** cmdlet을 사용 하 여 신뢰할 수 있는 응용 프로그램으로 가상 트랜잭션을 실행 하도록 감시자 노드 컴퓨터를 구성 하 고 다음과 같은 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-259">After creating the trusted application pool, you can then configure the watcher node computer to run synthetic transactions as a trusted application by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

<span data-ttu-id="d2c2a-260">이 명령이 완료 되 고 신뢰할 수 있는 응용 프로그램이 생성 되 면 **CsTopology** cmdlet을 실행 하 여 변경 내용이 적용 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-260">When this command completes and the trusted application is created, you must then run the **Enable-CsTopology** cmdlet to make sure that the changes take effect:</span></span>
  
```PowerShell
Enable-CsTopology
```

<span data-ttu-id="d2c2a-261">감시자 노드 컴퓨터 계정에는 일부 가상 트랜잭션에 대해 CMS를 쿼리할 수 있는 기능이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-261">The watcher node computer account requires the ability to query CMS for some synthetic transactions.</span></span> <span data-ttu-id="d2c2a-262">이 기능을 허용 하려면 감시자 노드의 컴퓨터 계정을 RTCUniversalReadOnlyAdmins 보안 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-262">To allow this ability, add the computer account of the watcher node to the RTCUniversalReadOnlyAdmins security group.</span></span> <span data-ttu-id="d2c2a-263">AD 복제가 발생 한 후 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-263">Once AD replication has occurred, restart the computer.</span></span>
  
<span data-ttu-id="d2c2a-264">신뢰할 수 있는 새 응용 프로그램이 만들어졌는지 확인 하려면 비즈니스용 Skype 서버 관리 셸 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-264">To verify that the new trusted application has been created, type the following at the Skype for Business Server Management Shell prompt:</span></span>
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="d2c2a-265">감시자 노드에 대 한 기본 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="d2c2a-265">Configure a Default Certificate on the Watcher Node</span></span>
<span data-ttu-id="d2c2a-266"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="d2c2a-266"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="d2c2a-267">(비즈니스용 Skype Server 배포 마법사를 사용 하 여 지정 된 기본 인증서가 있어야 함) 서버 인증을 사용 하는 각 감시자 노드에</span><span class="sxs-lookup"><span data-stu-id="d2c2a-267">Each watcher node that uses TrustedServer authentication must have a Default certificate assigned by using the Skype for Business Server Deployment wizard.</span></span> 
  
<span data-ttu-id="d2c2a-268">기본 인증서를 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-268">To assign a Default certificate:</span></span>
  
1. <span data-ttu-id="d2c2a-269">시작을 클릭 하 고 모든 프로그램을 클릭 한 다음 비즈니스용 Skype 서버 2015을 클릭 하 고 비즈니스용 Skype 서버 배포 마법사를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-269">Click Start, click All Programs, click Skype for Business Server 2015, and then click Skype for Business Server Deployment Wizard.</span></span> 
    
2. <span data-ttu-id="d2c2a-270">비즈니스용 Skype 서버 배포 마법사에서 비즈니스용 Skype Server System 설치 또는 업데이트를 클릭 한 다음 제목 요청, 설치 또는 인증서 지정에서 실행을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-270">In the Skype for Business Server Deployment Wizard, click Install or Update Skype for Business Server System, and then click Run under the heading Request, Install, or Assign Certificate.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d2c2a-271">실행 단추를 사용할 수 없는 경우 먼저 로컬 구성 저장소 설치에서 실행을 클릭 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-271">If the Run button is disabled, you may need to first click Run under Install Local Configuration Store.</span></span> 
  
<span data-ttu-id="d2c2a-272">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-272">Do one of the following:</span></span>
  
- <span data-ttu-id="d2c2a-273">기본 인증서로 사용할 수 있는 인증서가 이미 있는 경우 인증서 마법사에서 기본값을 클릭 한 다음 할당을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-273">If you already have a certificate that can be used as the Default certificate, click Default in the Certificate wizard, and then click Assign.</span></span> <span data-ttu-id="d2c2a-274">인증서 할당 마법사의 단계에 따라 해당 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-274">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
- <span data-ttu-id="d2c2a-275">기본 인증서를 사용 하기 위해 인증서를 요청 해야 하는 경우 요청을 클릭 한 다음 인증서 요청 마법사의 단계에 따라 해당 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-275">If you need to request a certificate for use the Default certificate, click Request, and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="d2c2a-276">웹 서버 인증서에 대 한 기본값을 사용 하는 경우에는 기본 인증서로 할당할 수 있는 인증서를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-276">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>
    
## <a name="install-and-configure-a-watcher-node"></a><span data-ttu-id="d2c2a-277">감시자 노드 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="d2c2a-277">Install and Configure a Watcher Node</span></span>
<span data-ttu-id="d2c2a-278"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="d2c2a-278"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="d2c2a-279">감시자 노드 컴퓨터를 다시 시작 하 고 인증서를 구성한 후에는 Watchernode 파일을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-279">After you have restarted the watcher node computer and configured a certificate, you must run the file Watchernode.msi.</span></span> <span data-ttu-id="d2c2a-280">(Operations Manager 에이전트 파일과 비즈니스용 Skype Server 2015 core 구성 요소가 설치 되어 있는 모든 컴퓨터에서 Watchernode을 실행 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="d2c2a-280">(You must run Watchernode.msi on any computer where both the Operations Manager agent files and the Skype for Business Server 2015 core components are installed.)</span></span> 
  
<span data-ttu-id="d2c2a-281">감시자 노드를 설치 하 고 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-281">To install and configure a watcher node:</span></span>
  
1. <span data-ttu-id="d2c2a-282">시작을 클릭 하 고 모든 프로그램을 클릭 한 다음 비즈니스용 Skype Server 2015을 클릭 하 고 비즈니스용 Skype 서버 관리 셸을 클릭 하 여 비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-282">Open the Skype for Business Server Management Shell by clicking Start, clicking All Programs, clicking Skype for Business Server 2015, and then clicking Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="d2c2a-283">관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다 (Watchernode 복사본의 실제 경로를 지정 하 고 있어야 합니다.).</span><span class="sxs-lookup"><span data-stu-id="d2c2a-283">In the Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> <span data-ttu-id="d2c2a-284">명령 창에서 Watchernode n을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-284">You can also run Watchernode.msi n from a command window.</span></span> <span data-ttu-id="d2c2a-285">명령 창을 열려면 시작을 클릭 하 고 명령 프롬프트를 마우스 오른쪽 단추로 클릭 한 다음 관리자 권한으로 실행을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-285">To open a command window, click Start, right-click Command Prompt, and then click Run as administrator.</span></span> <span data-ttu-id="d2c2a-286">명령 창이 열리면 위의 2 단계에 표시 된 것과 같은 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-286">When the command window opens, type the same command shown in step 2, above.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d2c2a-287">앞의 명령에서 이름/값 쌍 인증 =로 서버는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-287">In the preceding command, the name/value pair Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="d2c2a-288">표시 된 대로 정확 하 게 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-288">It must be typed exactly as shown.</span></span> <span data-ttu-id="d2c2a-289">예를 들어 다음 명령은 올바른 문자 대/소문자를 사용 하지 않기 때문에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-289">For example, this command will fail because it does not use the correct letter casing:</span></span> 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

<span data-ttu-id="d2c2a-290">(외부 서버 모드)는 외곽 네트워크에 있는 컴퓨터에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-290">TrustedServer mode can be used only with computers that lie inside the perimeter network.</span></span> <span data-ttu-id="d2c2a-291">감시자 노드가 (가) 서버 모드에서 실행 되는 경우 관리자는 컴퓨터에서 테스트 사용자 암호를 유지 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-291">When a watcher node runs in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a><span data-ttu-id="d2c2a-292">협상을 사용 하도록 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="d2c2a-292">Configure a Watcher Node to Use Negotiate</span></span>
<span data-ttu-id="d2c2a-293"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="d2c2a-293"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="d2c2a-294">감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 약간 다른 절차를 따라 가상 트랜잭션을 실행 하도록 감시자 노드를 구성 해야 합니다. 특히, 신뢰할 수 있는 응용 프로그램 풀이나 신뢰할 수 있는 사용자를 만들지 마십시오. 프로그램.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-294">If your watcher node computer lies outside the perimeter network then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions: in particular, you should not create a trusted application pool or a trusted application.</span></span> <span data-ttu-id="d2c2a-295">즉, 다음 두 작업을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-295">That means that you will need to complete the next two tasks.</span></span>
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="d2c2a-296">RTC 로컬 읽기 전용 관리자 그룹의 구성원 업데이트</span><span class="sxs-lookup"><span data-stu-id="d2c2a-296">Update Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="d2c2a-297">감시자 노드가 경계 네트워크 외부에 있는 경우 감시자 노드에서 다음 절차를 완료 하 여 감시자 노드 컴퓨터의 RTC 로컬 읽기 전용 관리자 그룹에 네트워크 서비스 계정을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-297">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer by completing the following procedure on the watcher node:</span></span>
  
1. <span data-ttu-id="d2c2a-298">시작을 클릭 하 고 컴퓨터를 마우스 오른쪽 단추로 클릭 한 다음 관리를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-298">Click Start, right-click Computer, and then click Manage.</span></span>
    
2. <span data-ttu-id="d2c2a-299">서버 관리자에서 구성을 확장 하 고 로컬 사용자 및 그룹을 확장 한 다음 그룹을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-299">In Server Manager, expand Configuration, expand Local Users and Groups, and then click Groups.</span></span>
    
3. <span data-ttu-id="d2c2a-300">그룹 창에서 RTC 로컬 읽기 전용 관리자를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-300">In the Groups pane, double-click RTC Local Read-only Administrators.</span></span>
    
4. <span data-ttu-id="d2c2a-301">RTC 로컬 읽기 전용 관리자 속성 대화 상자에서 추가를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-301">In the RTC Local Read-only Administrators Properties dialog box, click Add.</span></span>
    
5. <span data-ttu-id="d2c2a-302">사용자, 컴퓨터, 서비스 계정 또는 그룹 선택 대화 상자에서 위치를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-302">In the Select Users, Computers, Service Accounts, or Groups dialog box, click Locations.</span></span>
    
6. <span data-ttu-id="d2c2a-303">위치 대화 상자에서 감시자 노드 컴퓨터의 이름을 선택한 다음 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-303">In the Locations dialog box, select the name of the watcher node computer, and then click OK.</span></span>
    
7. <span data-ttu-id="d2c2a-304">선택할 개체 이름 입력 상자에 네트워크 서비스를 입력 한 다음 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-304">In the Enter object names to select box, type Network Service, and then click OK.</span></span>
    
8. <span data-ttu-id="d2c2a-305">RTC 로컬 읽기 전용 관리자 속성 대화 상자에서 확인을 클릭 한 다음 서버 관리자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-305">In the RTC Local Read-only Administrators Properties dialog box, click OK, and then close Server Manager.</span></span>
    
9. <span data-ttu-id="d2c2a-306">감시자 노드 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-306">Restart the watcher node computer.</span></span>
    
### <a name="install-the-watcher-node-configuration-files"></a><span data-ttu-id="d2c2a-307">감시자 노드 구성 파일 설치</span><span class="sxs-lookup"><span data-stu-id="d2c2a-307">Install the Watcher Node Configuration Files</span></span>

<span data-ttu-id="d2c2a-308">다음 단계는 Watchernode 파일을 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-308">Your next step is to run the file Watchernode.msi:</span></span> 
  
1. <span data-ttu-id="d2c2a-309">Microsoft 비즈니스용 Skype Server 2015 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-309">Open the Microsoft Skype for Business Server 2015 Management Shell.</span></span> <span data-ttu-id="d2c2a-310">시작, 모든 프로그램, Microsoft 비즈니스용 Skype 서버 2015을 차례로 클릭 한 다음 비즈니스용 Skype Server Management Shell을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-310">Click Start, click All Programs, click Microsoft Skype for Business Server 2015, and then click Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="d2c2a-311">비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다 (Watchernode 복사본의 실제 경로를 지정 해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="d2c2a-311">In Skype for Business Server Management Shell, type the following command, and then press ENTER (be sure to specify the actual path to your copy of Watchernode.msi):</span></span>
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> <span data-ttu-id="d2c2a-312">앞에서 언급 했 듯이 Watchernode는 명령 창 에서도 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-312">As mentioned previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="d2c2a-313">명령 창을 열려면 **시작**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-313">To open a command window, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="d2c2a-314">명령 창이 열리면 위의 2 단계에 표시 된 것과 같은 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-314">When the command window opens, type the same command shown in step 2, above.</span></span> 
  
<span data-ttu-id="d2c2a-315">협상 모드는 감시자 노드가 신뢰 된 응용 프로그램 풀로 설정 될 수 없을 때마다 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-315">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="d2c2a-316">이 모드에서는 관리자가 감시자 노드에서 테스트 사용자 암호를 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2a-316">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>
  

