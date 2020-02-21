---
title: 'Lync Server 2013: 가상 트랜잭션에 대 한 특별 설치 지침'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: defed8a0356d489a628f883b42ae658aadd6442d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="b07ad-102">Lync Server 2013의 가상 트랜잭션에 대 한 특별 설치 지침</span><span class="sxs-lookup"><span data-stu-id="b07ad-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b07ad-103">_**마지막으로 수정 된 항목:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="b07ad-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="b07ad-p101">대부분의 가상 트랜잭션은 감시자 노드에서 있는 그대로 실행됩니다. 즉, 가상 트랜잭션이 감시자 노드 구성 설정에 추가되는 즉시, 감시자 노드가 테스트 진행 중 가상 트랜잭션을 즉시 사용할 수 있습니다. 하지만 이러한 방식이 모든 가상 트랜잭션에 적용되는 것은 아닙니다. 이러한 예외적인 특별한 설치 지침이 필요한 가상 트랜잭션은 다음 섹션에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-p101">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes. However, this is not true for all synthetic transactions. The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="b07ad-107">서버 시간 제한 오류 처리</span><span class="sxs-lookup"><span data-stu-id="b07ad-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="b07ad-108">경우에 따라 가상 트랜잭션이 서버 시간 제한 오류 (오류 코드 504)와 함께 실패 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="b07ad-109">이러한 오류는 일반적으로 방화벽 문제로 인해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="b07ad-110">가상 트랜잭션이 실행 되 면 해당 트랜잭션은 MonitoringHost 프로세스에서 실행 되 고, MonitoringHost는 debug.exe 프로세스의 인스턴스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="b07ad-111">MonitoringHost 또는 debug.exe가 방화벽에 의해 차단 되 면 가상 트랜잭션이 실패 하 고 504 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="b07ad-112">이 문제를 해결 하려면 로컬 컴퓨터에서 MonitoringHost 및 debug.exe 둘 다에 대해 인바운드 방화벽 규칙을 수동으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="b07ad-113">이 작업은 서버의 기존 구성에 따라 Windows 방화벽이 나 타사 로컬 방화벽 소프트웨어를 통해 수행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="b07ad-114">가상 트랜잭션 호스트 컴퓨터와 모니터링 하려는 Lync 서버 간에 네트워크 방화벽 장치를 사용할 경우에는 호스트를 클라이언트 컴퓨터로 취급 하 고 모든 방화벽 포트 요구 사항을 [Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜](lync-server-2013-ports-and-protocols-for-internal-servers.md)에서 관찰자로 다루어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="b07ad-115">데이터 회의 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="b07ad-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="b07ad-116">감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우에는 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 먼저 사용 하지 않도록 설정 하지 않는 한 데이터 회의 가상 트랜잭션을 실행할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="b07ad-117">이 서비스에 대해 프록시 설정을 사용하지 않도록 설정하려면 다음 절차를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="b07ad-118">감시자 노드 컴퓨터에서 **시작**, **모든 프로그램**, **보조프로그램**을 차례로 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="b07ad-119">콘솔 창에 다음 명령을 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="b07ad-120">명령 창에 다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="b07ad-121">이 메시지는 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 사용 하지 않도록 설정 했음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="b07ad-122">Exchange 통합 메시징 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="b07ad-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="b07ad-123">Exchange UM (통합 메시징) 가상 트랜잭션은 테스트 사용자가 Exchange에서 홈에 있는 음성 메일 계정에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="b07ad-124">이러한 테스트 사용자는 Exchange UM 테스트를 사용하기 전에 음성 메일 계정으로 미리 구성되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="b07ad-125">영구 채팅 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="b07ad-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="b07ad-126">영구 채팅 가상 트랜잭션을 사용 하려면 관리자가 먼저 채널을 만들고 사용자에 게이를 사용 하기 위한 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="b07ad-127">[Test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet은 이러한 테스트 사용자를 올바르게 구성 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="b07ad-128">이 설정 작업은 엔터프라이즈 내부에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="b07ad-129">서버가 아닌 컴퓨터에서 실행할 경우 cmdlet을 실행하는 사용자는 RBAC(역할 기반 액세스 제어)에 대한 PersistentChatAdministrators 역할의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="b07ad-130">서버 자체에서 실행할 경우 cmdlet을 실행하는 사용자는 RTCUniversalServerAdmins 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="b07ad-131">위 명령에서는 Setup 매개 변수가 포함되었으며 True($True)로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="b07ad-132">Setup 매개 변수를 포함 하면 Test-cspersistentchatmessage에서 특수 영구 대화방을 만들고 해당 대화방을 테스트 사용자에 게 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="b07ad-133">이러한 방식은 테스트 목적으로 사용할 수 있는 채팅방을 실제로 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="b07ad-134">Setup 매개 변수는 프런트 엔드 서버 에서만 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="b07ad-135">Test-CsPersistentChatMessage로 만든 채팅방은 관리자만 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="b07ad-136">PSTN 피어 투 피어 통화 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="b07ad-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="b07ad-137">[테스트-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) 가상 트랜잭션은 공중 전화망 (PSTN)을 통해 통화를 배치 하 고 수신 하는 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="b07ad-138">이 가상 트랜잭션을 실행하려면 관리자가 다음을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="b07ad-139">Enterprise Voice에 대해 두 개의 테스트 사용자 (발신자 및 수신자)가 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="b07ad-140">각 사용자 계정에 대한 DID(Direct Inward Dialing) 번호</span><span class="sxs-lookup"><span data-stu-id="b07ad-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="b07ad-141">수신자 번호에 대한 통화가 PSTN 게이트웨이에 연결되도록 하는 음성 정책 및 음성 경로</span><span class="sxs-lookup"><span data-stu-id="b07ad-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="b07ad-142">통화를 허용하는 PSTN 게이트웨이 및 사용된 번호를 기반으로 수신자의 홈 풀로 통화를 라우팅하는 미디어</span><span class="sxs-lookup"><span data-stu-id="b07ad-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="b07ad-143">통합 연락처 저장소 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="b07ad-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="b07ad-144">통합 연락처 저장소 가상 트랜잭션은 Lync Server 2013이 Microsoft Exchange Server 2013에서 사용자를 대신 하 여 연락처를 검색할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="b07ad-145">이 가상 트랜잭션을 사용하려면 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="b07ad-146">Lync server 2013 및 Exchange 2013 간에 [서버 간 인증 (OAuth) 및 파트너 응용 2013 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="b07ad-147">테스트 사용자에 게 유효한 Exchange 2013 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="b07ad-148">이러한 조건이 충족되었으면 관리자가 다음 명령을 실행하여 SIP 주소 kenmyer@litwareinc.com의 사용자가 통합 연락처 저장소에서 자신의 연락처를 검색할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="b07ad-149">이전 명령에서는 Setup 매개 변수가 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="b07ad-150">Test-CsUnifiedContactStore를 실행할 때 Setup 매개 변수가 포함되었으면 지정된 사용자의 연락처(이 경우 sip:kenmyer@litwareinc.com)가 통합 연락처 저장소로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="b07ad-151">물론, 사용자의 연락처가 통합 연락처 저장소에 이미 있는 경우에는 이동할 필요가 없습니다. Setup 매개 변수는 일반적으로 한 번만 사용 되며 (첫 번째 테스트-Test-csunifiedcontactstore 실행), 테스트 사용자 에게만 사용 해야 합니다. 즉, 사용자 계정을 사용 하 여 Lync Server에 실제로 로그온 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="b07ad-152">테스트 사용자가 통합 연락처 저장소로 마이그레이션된 후에는 Setup 매개 변수 없이 Test-CsUnifiedContactStore를 호출하여 사용자의 연락처를 검색할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="b07ad-153">XMPP 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="b07ad-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="b07ad-154">XMPP(Extensible Messaging and Presence Protocol) IM 가상 트랜잭션을 사용하려면 하나 이상의 페더레이션 도메인에 XMPP 기능이 구성되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="b07ad-155">XMPP 가상 트랜잭션을 사용하도록 설정하려면 라우팅 가능한 XMPP 도메인의 사용자 계정을 XmppTestReceiverMailAddress 매개 변수에 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="b07ad-156">예:</span><span class="sxs-lookup"><span data-stu-id="b07ad-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="b07ad-157">이 예에서는 litwareinc.com에 대 한 메시지를 XMPP 게이트웨이로 라우팅하도록 Lync Server 2013 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07ad-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

