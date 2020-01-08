---
title: 'Lync Server 2013: 종합 거래에 대 한 특별 한 설정 지침'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c2f0f45aa2187f1b47f8dfa81b3ba121388f6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="6ac16-102">Lync Server 2013의 종합 거래에 대 한 특별 한 설정 지침</span><span class="sxs-lookup"><span data-stu-id="6ac16-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ac16-103">_**마지막으로 수정한 주제:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="6ac16-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="6ac16-104">대부분의 가상 트랜잭션은 있는 그대로 감시자 노드에서 실행할 수 있습니다. 즉, 가상 트랜잭션이 감시자 노드 구성 설정에 추가 되는 즉시 감시자 노드는 해당 테스트를 통과 하는 동안 가상 트랜잭션을 사용 하 여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-104">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes.</span></span> <span data-ttu-id="6ac16-105">그러나 모든 가상 거래에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-105">However, this is not true for all synthetic transactions.</span></span> <span data-ttu-id="6ac16-106">특별 한 설정 지침이 필요한 가상 트랜잭션은 다음 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-106">The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="6ac16-107">서버 시간 초과 오류 처리</span><span class="sxs-lookup"><span data-stu-id="6ac16-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="6ac16-108">경우에 따라 가상 트랜잭션이 서버 시간 초과 오류로 인해 실패 하는 경우가 있을 수 있습니다 (오류 코드 504).</span><span class="sxs-lookup"><span data-stu-id="6ac16-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="6ac16-109">이러한 오류는 일반적으로 방화벽 문제 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="6ac16-110">가상 트랜잭션을 실행할 때 해당 트랜잭션은 MonitoringHost 프로세스에서 실행 됩니다. MonitoringHost는 debug.exe 프로세스의 인스턴스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="6ac16-111">MonitoringHost 또는 PowerShell이 방화벽에 의해 차단 되는 경우 가상 트랜잭션은 실패 하 고 504 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="6ac16-112">이 문제를 해결 하려면 로컬 컴퓨터에서 MonitoringHost 및 debug.exe 모두에 대해 수동으로 인바운드 방화벽 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="6ac16-113">이 작업은 서버의 기존 구성에 따라 Windows 방화벽이 나 타사 로컬 방화벽 소프트웨어를 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="6ac16-114">가상 트랜잭션 호스트 컴퓨터와 모니터링 하려는 Lync 서버 간에 네트워크 방화벽 장치를 채택 하는 경우 호스트를 클라이언트 컴퓨터로 처리 하 고 [Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜](lync-server-2013-ports-and-protocols-for-internal-servers.md)의 모든 방화벽 포트 요구 사항을 관찰자에 게 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="6ac16-115">데이터 회의 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="6ac16-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="6ac16-116">감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 먼저 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 사용 하지 않도록 설정 하지 않는 한 데이터 회의 가상 트랜잭션을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="6ac16-117">이 서비스에 대 한 프록시 설정을 사용 하지 않으려면 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="6ac16-118">감시자 노드 컴퓨터에서 **시작**, **모든 프로그램**, **액세서리**를 차례로 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="6ac16-119">콘솔 창에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="6ac16-120">명령 창에 다음 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="6ac16-121">이 메시지는 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 사용 하지 않도록 설정 했다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="6ac16-122">Exchange 통합 메시징 종합 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="6ac16-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="6ac16-123">UM (통합 메시징) 통합 트랜잭션은 테스트 사용자가 Exchange의 보이스 메일 계정에 연결할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="6ac16-124">이러한 테스트 사용자는 Exchange UM 테스트를 사용 하기 전에 먼저 보이스 메일 계정을 사용 하 여 미리 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="6ac16-125">영구 채팅 종합 거래</span><span class="sxs-lookup"><span data-stu-id="6ac16-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="6ac16-126">영구 채팅 종합 트랜잭션을 사용 하려면 관리자가 먼저 채널을 만들고 사용자에 게이를 사용할 수 있는 권한을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="6ac16-127">[테스트 CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet을 사용 하 여 이러한 테스트 사용자를 올바르게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="6ac16-128">이 설치 작업은 엔터프라이즈 내에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="6ac16-129">Nonserver 컴퓨터에서 실행 하는 경우 cmdlet을 실행 하는 사용자는 RBAC (역할 기반 액세스 제어)에 대해 PersistentChatAdministrators 역할의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="6ac16-130">서버 자체에서 실행 되는 경우 cmdlet을 실행 하는 사용자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="6ac16-131">위의 명령에서 Setup 매개 변수를 포함 하 고 True ($True)로 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="6ac16-132">설치 매개 변수를 포함 하는 경우 CsPersistentChatMessage에서 특수 영구 채팅방을 만들고 해당 룸을 테스트 사용자에 게 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="6ac16-133">이는 테스트 목적으로 실제로 채팅방을 사용할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="6ac16-134">설치 매개 변수는 프런트 엔드 서버 에서만 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="6ac16-135">CsPersistentChatMessage에서 생성 되는 채팅방은 관리자만 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="6ac16-136">PSTN 피어 투 피어 호출 종합 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="6ac16-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="6ac16-137">[테스트-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) 합성 트랜잭션은 PSTN (공용 전환 통신 네트워크)을 통해 전화를 걸고 받는 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="6ac16-138">이 가상 트랜잭션을 실행 하려면 관리자가 다음을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="6ac16-139">두 개의 테스트 사용자 (호출자와 받는 사람이 엔터프라이즈 음성에 대해 사용 하도록 설정 됨)</span><span class="sxs-lookup"><span data-stu-id="6ac16-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="6ac16-140">각 사용자 계정에 대 한 직접 안쪽 전화 걸기 (번호)</span><span class="sxs-lookup"><span data-stu-id="6ac16-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="6ac16-141">전화 번호를 통해 PSTN 게이트웨이에 연결할 수 있는 음성 정책 및 음성 경로</span><span class="sxs-lookup"><span data-stu-id="6ac16-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="6ac16-142">통화를 수락 하는 PSTN 게이트웨이 및 통화를 라우팅하는 미디어는 전화를 건 번호를 기준으로 받는 사람의 홈 풀로 백업 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="6ac16-143">통합 된 연락처 저장소 종합 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="6ac16-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="6ac16-144">통합 된 연락처 저장소 가상 트랜잭션은 Lync Server 2013에서 Microsoft Exchange Server 2013의 사용자를 대신 하 여 연락처를 검색할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="6ac16-145">이 가상 트랜잭션을 사용 하려면 다음 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="6ac16-146">Lync server [2013의 OAuth (서버 간 인증) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 는 lync server 2013 및 Exchange 2013 간에 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="6ac16-147">테스트 사용자는 유효한 Exchange 2013 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="6ac16-148">이러한 조건이 충족 되 면 관리자는 다음 명령을 실행 하 여 SIP 주소 kenmyer@litwareinc.com를 가진 사용자가 통합 대화 상대 저장소에서 해당 연락처를 검색할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="6ac16-149">앞의 명령에 사용 된 Setup 매개 변수의 사용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="6ac16-150">Test-CsUnifiedContactStore를 실행할 때 Setup 매개 변수가 포함 된 경우 지정 된 사용자의 연락처 (이 예에서는 sip:kenmyer@litwareinc.com)가 통합 연락처 저장소로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="6ac16-151">(물론, 사용자의 연락처가 이미 통합 된 연락처 저장소에 있는 경우에는 이동할 필요가 없습니다.) Setup 매개 변수는 일반적으로 한 번만 사용 되며 (테스트 CsUnifiedContactStore가 실행 되는 경우)에만 테스트 사용자와 함께 사용 해야 합니다. 즉, 사용자 계정이 Lync Server에 실제로 로그온 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="6ac16-152">테스트 사용자를 통합 대화 상대 저장소로 마이그레이션한 후에는 Setup 매개 변수 없이 CsUnifiedContactStore를 호출 하 여 사용자의 연락처를 검색할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="6ac16-153">XMPP 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="6ac16-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="6ac16-154">XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) IM 가상 트랜잭션을 사용 하려면 XMPP 기능을 하나 이상의 페더레이션 도메인으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="6ac16-155">XMPP 가상 트랜잭션을 사용 하도록 설정 하려면 XmppTestReceiverMailAddress 매개 변수를 라우팅할 수 있는 XMPP 도메인의 사용자 계정으로 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="6ac16-156">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="6ac16-157">이 예제에서는 litwareinc.com에 대 한 메시지를 XMPP 게이트웨이로 라우팅하기 위해 Lync Server 2013 규칙이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac16-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

